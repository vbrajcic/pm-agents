# Profico Internal Inventory Management System — Strategic Project PRD
*Project Type: Internal Tool | Priority: P0*
*Status: Requirements Complete - Ready for Architecture Phase*

## Executive Summary

### Project Vision & Strategic Rationale
Build a unified internal inventory management platform that consolidates equipment tracking and software license management, eliminating manual Google Sheets processes and enabling efficient asset management, budget planning, and compliance reporting for Profico's growing team (current ~30 employees, projected 300 in 3 years).

### Expected Business Impact
- **Primary Objective**: Eliminate manual inventory tracking effort (currently scattered across Google Forms, Sheets, and email chains)
- **Secondary Objectives**:
  - Enable accurate budget planning for equipment purchases (eliminate "rule of thumb" 15 laptops/year approach)
  - Ensure compliance with Croatian accounting/tax requirements (ZOPI fund reporting, VAT documentation)
  - Support company scaling from 30 to 300 employees with systematic asset management
  - Reduce time spent on invoice collection and subscription tracking (currently requires manual outreach to each person)
- **Success Timeline**: Replace current manual processes within 6 months, with immediate impact on equipment request workflows

### Project Scope & Boundaries
**Definitively In Scope:**
- **Hardware Inventory Management** - Laptops, displays, phones, tablets, keyboards, mice, dongles, office furniture
- **Software License Tracking** - Individual and team subscriptions with invoice management
- **Equipment Request & Approval Workflow** - User requests, team lead approval, admin ordering
- **Role-Based Access Control** - Regular users, team leads, admin levels with appropriate permissions
- **Compliance Reporting** - Export capabilities for accounting and tax inspection requirements
- **Equipment Lifecycle Management** - Assignment, transfer, checkout, condition tracking, disposal

**Definitively Out of Scope:**
- **Financial Integration** - No direct integration with accounting software or payment processing
- **Advanced Inventory Optimization** - No automated reorder points or AI-driven recommendations
- **External Vendor Management** - No vendor catalogs or purchasing workflow integration
- **Time Tracking Integration** - No connection to Harvest or other productivity tools

**Scope Decision Points** (Require explicit approval to include):
- **Advanced OCR Invoice Processing** - Automatic data extraction from uploaded invoices (depends on implementation complexity)
- **Mobile Native App** - Dedicated mobile application vs responsive web (decision based on QR scanning requirements)
- **Automated Depreciation Tracking** - Complex accounting calculations vs simple date-based reporting

## Stakeholder Analysis & Requirement Synthesis

### Stakeholder Requirement Matrix

#### Confirmed Consensus Requirements
**Business Requirements:**
- **Equipment Request Workflow**: Supported by Mira (admin) to reduce manual equipment ordering coordination
- **Budget Planning Capability**: Validated by annual planning needs and current "rule of thumb" inadequacy
- **Compliance Reporting**: Required for Croatian tax inspection, ZOPI fund reporting, and VAT documentation
- **Software License Consolidation**: Consensus on need to track scattered subscriptions and invoice collection

**Operational Requirements:**
- **Role-Based Access Control**: Security requirement from admin with three clear user levels identified
- **Equipment Transfer Tracking**: Confirmed need to handle device reassignment between employees
- **Annual Inventory Checkup**: Process requirement for verifying actual vs recorded equipment
- **QR Code Integration**: Efficiency requirement for quick equipment identification and processing

#### Conflicting Requirements & Resolutions

**Conflict 1: Equipment Detail Level (Hardware vs Office Furniture)**
- **Admin Position (Mira)**: Focus on electronic equipment only for MVP, add furniture later
- **Compliance Position (Matteo)**: Need office furniture tracking for ZOPI fund compliance
- **Resolution**: Two-tier approach - "Work Equipment" (electronic devices) for Phase 1, "Office Equipment" (furniture) for Phase 2
- **Rationale**: Electronic equipment has higher turnover and immediate workflow impact, furniture tracking needed for compliance
- **Decision Owner**: Admin with compliance team input

**Conflict 2: Request Scope (Electronic Only vs Everything)**
- **Process Position**: Limit requests to electronic equipment to avoid scope creep
- **User Experience Position**: Allow requests for any equipment type for consistency
- **Resolution**: Open request system with equipment categorization - users can request anything, approval workflow handles appropriateness
- **Implementation**: Free-text equipment requests with category selection and approval workflow
- **Success Criteria**: <5% rejected requests due to inappropriate equipment type

**Conflict 3: Small Item Tracking (Individual vs Bulk)**
- **Detailed Tracking Position**: Each dongle/cable should be individually tracked
- **Practical Position**: Small items (dongles, cables) tracked in bulk quantities
- **Resolution**: Hybrid approach - items >€150 tracked individually with serial numbers, items <€150 tracked as bulk inventory with quantities
- **Rationale**: Croatian accounting law requires individual tracking only for items >€150, bulk tracking sufficient for small items
- **Implementation**: Equipment type determines tracking method (individual vs quantity-based)

### Open Decisions & Research Needed

#### Technical Decisions (Blocking Implementation)
**Decision**: QR Code/Barcode Integration Approach
**Options**: Generate custom QR codes vs scan existing manufacturer barcodes vs hybrid approach
**Current Assumption**: Custom QR code generation with printed stickers for equipment identification
**Validation Needed**: Cost-benefit analysis of printer/sticker approach vs existing barcode scanning
**Decision Timeline**: Week 2 of Phase 1
**Decision Owner**: Admin (Mira) with input from operations team
**Impact if Delayed**: Manual equipment check-in/check-out processes, reduced efficiency

**Decision**: Mobile Access Implementation
**Options**: Responsive web app vs progressive web app vs native mobile app
**Research Needed**: QR code scanning requirements and camera API capabilities across platforms
**Decision Timeline**: Week 4 of Phase 1
**Fallback Plan**: Start with responsive web, enhance to PWA if camera functionality insufficient

#### Product Decisions (Can proceed with assumptions)
**Decision**: OCR Invoice Processing Implementation
**Current Assumption**: Manual invoice upload and data entry for MVP
**Validation Needed**: Feasibility and accuracy of OCR for Croatian invoices
**Decision Timeline**: Phase 2 planning
**Fallback Plan**: Continue manual data entry with structured upload forms

## Product Requirements

### Core Feature Areas

#### Feature Area 1: Hardware Inventory Management
**Business Purpose**: Comprehensive tracking of all physical equipment from acquisition to disposal
**Stakeholder Champions**: Mira (Admin), Operations Team
**User Stories:**
- As an admin, I want to register new equipment upon arrival so that it's immediately available for assignment
- As an employee, I want to view my assigned equipment so that I know what I'm responsible for
- As a team lead, I want to see all equipment assigned to my team so that I can manage resources effectively
- As an admin, I want to track equipment history so that I can identify patterns and plan replacements

**Functional Requirements:**
- **Equipment Registration** - Serial number, brand/model, purchase date, purchase method (direct/ZOPI/leasing), condition notes
- **Assignment Management** - Assign/unassign equipment to users, transfer between users with approval workflow
- **Equipment Categories** - Laptop, display, phone, tablet, keyboard, mouse, dongle, office furniture with individual vs bulk tracking
- **Condition Tracking** - Equipment condition reporting, issue reporting, repair/replacement workflow
- **QR Code Integration** - Generate QR codes for equipment, mobile scanning for quick access
- **Equipment Lifecycle** - Status tracking (Available, Assigned, In Repair, Disposed) with timestamp history

**Implementation Priority**: Phase 1 (Core functionality for immediate workflow improvement)

#### Feature Area 2: Software License Management
**Business Purpose**: Centralized tracking of software subscriptions and license obligations
**Stakeholder Champions**: Mira (Admin), Development Team
**User Stories:**
- As an admin, I want to track all software licenses so that I know who to contact for invoice collection
- As an employee, I want to register personal subscriptions eligible for reimbursement so that I receive proper compensation
- As a team lead, I want to see team software licenses so that I can avoid duplicate purchases
- As an admin, I want to categorize payment methods so that I can properly handle accounting requirements

**Functional Requirements:**
- **License Registration** - Software name, license type (individual/team/company), associated email, payment method
- **Payment Method Tracking** - Company card with company invoice, company card with personal invoice, personal card with reimbursement
- **Subscription Management** - Monthly/yearly frequency, price tracking, renewal date tracking
- **Invoice Collection** - Upload capability for invoices, reminder system for missing invoices
- **Access Control** - Individual licenses vs team licenses with appropriate visibility

**Implementation Priority**: Phase 2 (After hardware workflow established)

#### Feature Area 3: Request & Approval Workflow
**Business Purpose**: Streamlined equipment request process with appropriate approval gates
**Stakeholder Champions**: All Users, Team Leads, Admin
**User Stories:**
- As an employee, I want to request new equipment so that I can get necessary tools without manual coordination
- As a team lead, I want to approve/reject team requests so that I can control team resource allocation
- As an admin, I want to see approved requests so that I can efficiently order and assign equipment
- As an employee, I want to see my request status so that I know when to expect equipment

**Functional Requirements:**
- **Equipment Request Form** - Open-text equipment description, business justification, urgency level
- **Multi-Level Approval** - Team lead approval followed by admin approval with rejection feedback
- **Request Status Tracking** - Pending, team lead approved, admin approved, ordered, fulfilled, rejected
- **Order Management** - Convert approved requests to purchase orders with vendor and delivery tracking
- **Request History** - Track request patterns for budget planning and approval decision making

**Implementation Priority**: Phase 1 (Essential for eliminating manual request coordination)

### Cross-Cutting Requirements

#### User Management & Access Control
**Role-Based Access Matrix:**
- **Regular User**: View own equipment, request new equipment, report equipment issues, view own software licenses
- **Team Lead**: All user permissions + view team equipment, approve/reject team requests, assign equipment within team
- **Admin**: All permissions + system configuration, all equipment/license visibility, user management, compliance reporting

**User Management:**
- **Invitation System** - Admin creates user accounts with role assignment and team association
- **Team Structure** - Hierarchical team organization with team lead relationships
- **Inactive User Handling** - User deactivation maintains historical data while preventing system access

#### Compliance & Reporting
**Croatian Accounting Compliance:**
- **Asset Classification** - Equipment >€150 with individual tracking, <€150 with bulk tracking
- **Depreciation Tracking** - Purchase date tracking for 2-year depreciation period calculation
- **Export Capabilities** - PDF/Excel export for tax inspection and ZOPI fund reporting
- **Audit Trail** - Complete change history for equipment assignments and transfers

**Reporting Requirements:**
- **Budget Planning Reports** - Equipment age analysis, replacement recommendations, cost projections
- **Compliance Reports** - Asset lists by purchase method, depreciation status, location tracking
- **Operational Reports** - Equipment utilization, request patterns, approval metrics

#### Data Management & Integration
**Equipment Data Sources:**
- **Manual Entry** - Equipment registration form with required fields and validation
- **Barcode/QR Scanning** - Mobile scanning for equipment identification and data retrieval
- **Invoice Upload** - PDF invoice storage with manual data extraction (OCR consideration for Phase 2)

**Data Quality & Validation:**
- **Required Fields** - Serial number, purchase date, purchase method for equipment >€150
- **Data Validation** - Serial number uniqueness, date validation, price range validation
- **Change Audit** - All equipment/license changes logged with user, timestamp, and reason

## Technical Implementation Strategy

### Architecture Decision Summary
**Selected Approach**: Web-first responsive application with progressive enhancement for mobile features
- **Frontend**: Modern web application with responsive design for desktop and mobile access
- **Backend**: REST API with role-based authentication and comprehensive audit logging
- **Database**: Relational database with equipment, users, licenses, and audit tables
- **Mobile Enhancement**: Progressive Web App (PWA) capabilities for QR code scanning and offline access

**Alternative Considered**: Native mobile app rejected due to development complexity and maintenance overhead
**QR Code Strategy**: Custom QR code generation with printed stickers, fallback to manual serial number entry
**Integration Pattern**: Self-contained system with export capabilities for external tool integration

### Build vs. Buy Analysis
**Custom Development Areas:**
- **Core Inventory Management** - Specific workflow and compliance requirements unique to Profico
- **Request/Approval Workflow** - Custom business logic for multi-level approvals and equipment categorization
- **Compliance Reporting** - Croatian-specific accounting and tax requirements

**Third-Party Considerations:**
- **Existing Solutions Evaluated**: Open-source inventory tools (too complex, poor user management)
- **SaaS Options**: Generic inventory tools lack software license management and Croatian compliance features
- **Decision Rationale**: Custom development provides better user experience and exact workflow match

**Infrastructure & Tools:**
- **Authentication**: Standard web authentication with session management
- **File Storage**: Cloud storage for invoice uploads and QR code generation
- **Reporting**: Built-in export functionality with PDF/Excel generation

## Implementation Roadmap

### Phase 1: Core Hardware Inventory & Request Workflow (Months 1-4)
**Primary Goal**: Replace current Google Forms/Sheets with functional equipment management
**Success Criteria:**
- [ ] All current equipment migrated from Google Sheets to new system
- [ ] Equipment request workflow operational (request → team lead approval → admin approval → fulfillment)
- [ ] User authentication and role-based access working correctly
- [ ] QR code generation and scanning functional for equipment identification
- [ ] Annual inventory checkup process implemented and tested

**Key Deliverables:**
- **User Management System** - Registration, authentication, role assignment, team structure
- **Equipment Registration** - Add new equipment with all required fields and category classification
- **Request Workflow** - Complete request/approval process with status tracking and notification
- **Basic Reporting** - Equipment lists, user assignments, request status reports
- **QR Code Integration** - Generate QR codes for equipment, mobile scanning capability

**Dependencies:**
- **QR Code Implementation Decision** - Custom generation vs existing barcode scanning by Week 2
- **Team Structure Definition** - Current team organization and lead assignments by Week 2
- **Equipment Data Migration** - Export current Google Sheets data and clean for import by Week 3

**Phase Gate Criteria**: All current equipment tracked in system, request workflow handles >95% of equipment requests, admin and team leads trained on system usage

### Phase 2: Software License Management & Advanced Features (Months 5-8)
**Primary Goal**: Complete inventory management with software tracking and advanced equipment features
**Success Criteria:**
- [ ] Software license tracking operational with invoice management
- [ ] Equipment condition reporting and maintenance tracking functional
- [ ] Advanced reporting available for budget planning and compliance
- [ ] Equipment transfer workflow handles reassignments and departures
- [ ] System handles projected user growth to 50+ employees

**Key Deliverables:**
- **Software License Module** - License registration, payment method tracking, invoice upload
- **Advanced Equipment Features** - Condition reporting, maintenance tracking, equipment history
- **Enhanced Reporting** - Budget planning reports, compliance exports, utilization analytics
- **Workflow Optimization** - Equipment transfer process, bulk operations, automation

**Scope Decision Points in Phase 2:**
- [ ] **OCR Invoice Processing** - Implement if manual data entry becomes bottleneck (>20 invoices/month)
- [ ] **Office Furniture Tracking** - Add if ZOPI compliance requirements confirmed by accounting
- [ ] **Advanced Mobile Features** - Native app development if PWA limitations discovered

### Phase 3: Optimization & Scaling (Months 9-12)
**Primary Goal**: Performance optimization and feature enhancement for projected company growth
*Only proceed if Phase 1-2 success criteria met and user adoption >90%*

**Advanced Features**:
- Predictive equipment replacement recommendations
- Advanced analytics and reporting dashboards
- External integration capabilities (accounting system sync)
- Automated inventory optimization

## Scope Management & Change Control

### Scope Creep Prevention Framework
**Change Request Process:**
1. **Business Impact Assessment** - All feature requests must include resource impact and business justification
2. **Stakeholder Priority Voting** - Conflicting requests resolved through admin decision with team lead input
3. **Timeline Impact Communication** - Explicit delivery impact for any scope additions
4. **Resource Allocation Review** - Changes requiring >40 hours trigger formal project review

**Scope Expansion Triggers** (Automatic review required):
- **New Equipment Categories** - Each category adds complexity to tracking and reporting
- **Additional User Roles** - Security and workflow implications require careful review
- **External System Integration** - API development and maintenance overhead
- **Advanced Analytics Features** - Data processing and performance implications

**Change Authority Matrix:**
- **UI/UX Improvements** (<16 hours): Admin approval with user feedback
- **New Features or Reports** (16-40 hours): Admin + key stakeholder approval
- **Architecture Changes** (>40 hours): Full stakeholder review with business case

### Success Gates & Quality Controls
**Phase 1 Success Gate:**
- [ ] Equipment migration completed with data accuracy verification
- [ ] Request workflow processes 100% of test scenarios successfully
- [ ] User authentication and access control verified through security review
- [ ] QR code scanning works reliably across target devices and browsers
- [ ] Admin and team lead training completed with >80% satisfaction scores

**Project Success Criteria:**
- [ ] Manual Google Sheets process eliminated completely (measured by system usage vs manual processes)
- [ ] Equipment request time reduced from "days/weeks" to same-day approval for standard requests
- [ ] Budget planning accuracy improved through data-driven equipment age and replacement analysis
- [ ] Compliance reporting generated automatically without manual data compilation

## Risk Assessment & Mitigation Strategy

### High-Priority Risks

**Risk: User Adoption Resistance**
**Probability**: Medium | **Impact**: High
**Indicators**: Low system usage, continued use of manual processes, training feedback indicating complexity
**Mitigation**: Phased rollout with superuser training, immediate replacement of painful manual processes, regular feedback collection
**Contingency**: Simplified interface development, additional training sessions, workflow adjustment based on user feedback

**Risk: Data Migration Complexity**
**Probability**: Medium | **Impact**: Medium
**Indicators**: Data quality issues in current Google Sheets, missing equipment information, duplicate/conflicting records
**Mitigation**: Data audit and cleanup before migration, manual verification of critical equipment, gradual migration with parallel processes
**Contingency**: Accept data gaps for non-critical equipment, manual data entry for missing information

**Risk: Mobile/QR Code Technical Challenges**
**Probability**: Medium | **Impact**: Medium
**Indicators**: Camera API limitations, QR code scanning accuracy issues, mobile performance problems
**Mitigation**: Early technical prototype of scanning functionality, fallback to manual serial number entry
**Contingency**: Delayed mobile features, focus on desktop workflow with manual equipment identification

### External Dependencies & Risks
**Team Structure Changes**: Rapid company growth could require role and permission model adjustments
**Compliance Requirement Changes**: Croatian accounting law changes could impact tracking requirements
**Hardware Environment**: New equipment types or unique identification challenges

## Success Measurement & Validation

### Primary Success Metrics
- **Process Efficiency**: Eliminate manual Google Sheets usage (Target: 100% system usage within 3 months)
- **Request Workflow Speed**: Equipment request resolution time (Target: <3 business days for standard requests)
- **Data Accuracy**: Inventory accuracy during annual checkup (Target: >95% accuracy of tracked equipment)
- **User Satisfaction**: System usability rating (Target: >4/5 stars from regular users)

### Operational Metrics
**Equipment Management:**
- Equipment registration time per device (Target: <5 minutes including QR code generation)
- Request approval processing time (Target: <24 hours for team lead, <48 hours for admin)
- Annual inventory checkup completion rate (Target: 100% employee participation)

**Software License Management:**
- License tracking completeness (Target: 100% of company-paid subscriptions tracked)
- Invoice collection efficiency (Target: >90% invoice submission within 30 days)

### Long-term Success Indicators
- **Budget Planning Improvement**: Data-driven equipment replacement planning replaces "rule of thumb" approach
- **Compliance Readiness**: Tax inspection preparation time reduced from days to hours
- **Scaling Support**: System handles 3x user growth (30 to 90+ employees) without performance degradation

---

## Critical Success Factors

### What Will Make This Project Succeed
1. **Strong Admin Champions** - Mira's direct involvement ensures practical workflow design and user training
2. **Immediate Manual Process Relief** - Replacing painful Google Sheets processes creates immediate user value
3. **Phased Implementation** - Hardware first approach establishes user habits before adding software complexity
4. **Practical Feature Focus** - Solving real operational problems rather than building theoretical ideal system
5. **Compliance Integration** - Meeting actual Croatian accounting requirements ensures long-term adoption

### What Will Make This Project Fail
- **Feature Scope Expansion** - Adding nice-to-have features before core workflows are stable
- **User Training Neglect** - Insufficient change management and user education
- **Technical Over-Engineering** - Complex architecture that's difficult to maintain and modify
- **Mobile Feature Dependencies** - QR code scanning requirements blocking core functionality
- **Data Migration Perfectionism** - Delaying launch for complete historical data migration

## Appendices

### A. Stakeholder Input Summary
**Mira (Admin)**: Equipment tracking efficiency, request workflow automation, compliance reporting, budget planning capability
**Employees**: Simple equipment request process, clear visibility of assigned equipment, easy issue reporting
**Team Leads**: Team equipment oversight, efficient request approval process, resource allocation control
**Operations (Matteo)**: Compliance with Croatian accounting requirements, ZOPI fund reporting, tax inspection readiness

### B. Current Process Analysis
**Equipment Management**: Google Forms → Google Sheets → Manual coordination → Email communication
**Software Licenses**: Manual tracking → Individual invoice collection → Spreadsheet compilation
**Budget Planning**: Rule-of-thumb estimates → Manual equipment age calculation → Inadequate replacement planning

### C. Technical Requirements Summary
**Core Platform**: Web application with responsive mobile design
**Authentication**: Role-based access with user invitation system
**Data Storage**: Relational database with audit logging and export capabilities
**Mobile Features**: QR code scanning, camera integration, offline capability consideration

### D. Implementation Dependencies
**Immediate**: Team structure definition, current equipment data export, QR code approach decision
**Phase 1**: User training materials, equipment labeling process, approval workflow testing
**Phase 2**: Software license data collection, invoice processing workflow, compliance requirement validation