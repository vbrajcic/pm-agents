# PM Agents - Product Management Tool Suite

This repository contains specialized agents for product management workflows and organized project documentation.

## Structure

```
pm-agents/
├── agents/                     # AI Agent Specifications (14 agents)
│   ├── project-prd-writer.md              # Comprehensive project PRD creation
│   ├── project-prd-writer-enhanced-v2.md  # Enhanced PRD writer v2
│   ├── concise-feature-prd-writer.md      # Individual feature PRDs
│   ├── prd-feature-extractor.md           # Feature extraction from PRDs
│   ├── feature-chat-agent.md              # Interactive feature refinement
│   ├── questions-assessment-agent.md      # PRD completeness analysis
│   ├── feature-brainstorm.md              # Feature ideation & evaluation
│   ├── idea-collector.md                  # Idea collection & documentation
│   ├── research-expert.md                 # UX research & user studies
│   ├── jira-ticket-writer.md              # Outcome-focused JIRA tickets
│   ├── ticket-writer.md                   # Development ticket creation
│   ├── design-to-jira-agent.md            # Design handoff management
│   ├── bug-reporter.md                    # Bug collection & documentation
│   └── communication-optimizer.md         # Stakeholder communication
├── docs/                       # Generated Documentation
│   ├── prds/                      # Product Requirements Documents
│   │   ├── project/                   # Complete project PRDs (4 projects)
│   │   └── features/                  # Individual feature PRDs by project (60 total)
│   │       ├── inventory-management/     # 10 feature PRDs
│   │       ├── employee-onboarding/      # 8 feature PRDs
│   │       ├── personal-expense/         # 16 feature PRDs
│   │       ├── team-lunch/               # 8 feature PRDs
│   │       └── team-lunch-planner/       # 18 feature PRDs
│   └── feature-extractions/        # Feature extraction documents (4 projects)
├── transcripts/                # Source Materials (7 transcripts)
│   ├── transcript.txt                                  # Original inventory management
│   ├── employee-onboarding-portal-transcript.txt       # Medium complexity
│   ├── personal-expense-tracking-transcript.txt        # Simple project
│   ├── team_lunch_transcript_example.txt               # Simple feature
│   ├── customer-support-platform-transcript.txt        # Complex project
│   ├── marketing-automation-platform-transcript.txt    # Very complex project
│   └── event-management-system-transcript.txt          # Simple project
└── README.md                   # This file
```

## Completed Projects

### 1. Inventory Management System (Complex)
**Source**: `transcripts/transcript.txt`
- **Project PRD**: `docs/prds/project/comprehensive-inventory-management-system-prd.md`
- **Feature Extraction**: `docs/feature-extractions/inventory-management-system-feature-extraction.md`
- **Feature PRDs**: 10 documents in `docs/prds/features/inventory-management/`
- **Scope**: Equipment tracking, software subscriptions, QR scanning, approval workflows
- **Timeline**: 18-22 weeks, 162 story points

### 2. Employee Onboarding Portal (Medium)
**Source**: `transcripts/employee-onboarding-portal-transcript.txt`
- **Project PRD**: `docs/prds/project/employee-onboarding-portal-comprehensive-prd-v1.0.md`
- **Feature Extraction**: `docs/feature-extractions/employee-onboarding-portal-feature-extraction.md`
- **Feature PRDs**: 8 documents in `docs/prds/features/employee-onboarding/`
- **Scope**: Digital onboarding workflows, task automation, system integration
- **Timeline**: 27-34 weeks, 233 story points

### 3. Personal Expense Tracking App (Simple)
**Source**: `transcripts/personal-expense-tracking-transcript.txt`
- **Project PRD**: `docs/prds/project/personal-expense-tracking-app-comprehensive-prd.md`
- **Feature Extraction**: `docs/feature-extractions/personal-expense-tracking-feature-extraction.md`
- **Feature PRDs**: 16 documents in `docs/prds/features/personal-expense/`
- **Scope**: Personal finance tracking, receipt scanning, budget management, analytics

### 4. Team Lunch Planner & Expense Tracker (Simple)
**Source**: `transcripts/team_lunch_transcript_example.txt`
- **Project PRD**: `docs/prds/project/team-lunch-planner-expense-tracker-comprehensive-prd.md`
- **Feature Extraction**: `docs/feature-extractions/team-lunch-planner-feature-extraction.md`
- **Feature PRDs**: 18 documents in `docs/prds/features/team-lunch-planner/` and 8 in `docs/prds/features/team-lunch/`
- **Scope**: Team lunch coordination, expense splitting, polling, restaurant integration

## Agent Workflow Demonstrated

**Complete End-to-End Process**:
1. **project-prd-writer** → Creates comprehensive project PRD from transcript
2. **questions-assessment-agent** → Identifies gaps and generates clarifying questions
3. **prd-feature-extractor** → Extracts features with development breakdown
4. **feature-chat-agent** → Refines complex features through targeted conversation
5. **concise-feature-prd-writer** → Generates individual feature PRDs
6. **jira-ticket-writer** → Creates outcome-focused development tickets
7. **bug-reporter** → Tracks and documents bugs during development

**Additional Supporting Agents**:
- **feature-brainstorm** → Generates and evaluates new feature ideas
- **idea-collector** → Collects and documents feature requests
- **research-expert** → Designs user research studies and interviews
- **design-to-jira-agent** → Manages design-to-development handoff
- **communication-optimizer** → Optimizes stakeholder communication

**Scalability Proven**: Agents handle different complexity levels (simple to very complex) while maintaining methodology consistency across 4 completed projects and 60 feature PRDs.

## Test Transcripts Available

### Complex Projects (Ready for Testing):
- **Customer Support Platform** (`customer-support-platform-transcript.txt`) - Enterprise omnichannel system with AI features
- **Marketing Automation Platform** (`marketing-automation-platform-transcript.txt`) - ML-powered multi-channel automation

### Simple Projects (Ready for Testing):
- **Event Management System** (`event-management-system-transcript.txt`) - Basic community event registration and management

## Features Documented

### Inventory Management (10 features):
1. User Authentication & Role Management
2. Equipment Registration & Management
3. Software Subscription Management
4. Request & Approval Workflow
5. Reporting & Analytics Dashboard
6. QR Code Scanning Integration
7. File Management & Invoice Storage
8. Notification & Communication System
9. Advanced Search & Filtering System
10. Audit Trail & Compliance System

### Employee Onboarding (8 features):
1. Employee Profile Management
2. Task Workflow Engine
3. Document Management System
4. System Integration Hub
5. Manager Dashboard & Oversight
6. Notification & Communication System
7. Analytics & Reporting Dashboard
8. Mobile Optimization & Responsive Design

### Personal Expense Tracking (16 features):
- Expense tracking and categorization
- Receipt scanning with OCR
- Budget management and alerts
- Multi-currency support
- Analytics and reporting
- Cloud sync and backup
- And 10 more features...

### Team Lunch Planner (26 features across both feature sets):
- Restaurant recommendation system
- Polling and voting mechanisms
- Expense splitting and calculation
- Calendar integration
- Payment processing
- Group management
- And 20 more features...

## Usage
Each agent has specific capabilities and templates. See individual agent files in `/agents/` for detailed specifications and usage instructions. Test with provided transcripts to explore different project complexity levels.