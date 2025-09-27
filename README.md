# PM Agents - Product Management Tool Suite

This repository contains specialized agents for product management workflows and organized project documentation.

## Structure

```
pm-agents/
├── agents/                     # AI Agent Specifications (14 agents)
│   ├── project-prd-writer.md      # Comprehensive project PRD creation
│   ├── concise-feature-prd-writer.md  # Individual feature PRDs
│   ├── prd-feature-extractor.md    # Feature extraction from PRDs
│   └── [other agents]...
├── docs/                       # Generated Documentation
│   ├── prds/                      # Product Requirements Documents
│   │   ├── project/                   # Complete project PRDs (2 projects)
│   │   └── features/                  # Individual feature PRDs by project
│   │       ├── inventory-management/     # 10 feature PRDs
│   │       └── employee-onboarding/      # 8 feature PRDs
│   ├── extractions/                # Feature extraction documents (2 projects)
│   └── examples/                   # Sample PRDs and references (5 files)
├── transcripts/                # Source Materials (4 transcripts)
│   ├── transcript.txt              # Original inventory management discussion
│   ├── customer-support-platform-transcript.txt    # Complex project test
│   ├── marketing-automation-platform-transcript.txt # Very complex project test
│   ├── employee-onboarding-portal-transcript.txt   # Medium complexity test
│   └── event-management-system-transcript.txt      # Simple project test
└── README.md                   # This file
```

## Completed Projects

### 1. Inventory Management System (Complex)
**Source**: `transcripts/transcript.txt`
- **Project PRD**: `docs/prds/project/comprehensive-inventory-management-system-prd.md`
- **Feature Extraction**: `docs/extractions/inventory-management-system-feature-extraction.md`
- **Feature PRDs**: 10 documents in `docs/prds/features/inventory-management/`
- **Scope**: Equipment tracking, software subscriptions, QR scanning, approval workflows
- **Timeline**: 18-22 weeks, 162 story points

### 2. Employee Onboarding Portal (Medium)
**Source**: `transcripts/employee-onboarding-portal-transcript.txt`
- **Project PRD**: `docs/prds/project/employee-onboarding-portal-comprehensive-prd-v1.0.md`
- **Feature Extraction**: `docs/extractions/employee-onboarding-portal-feature-extraction.md`
- **Feature PRDs**: 8 documents in `docs/prds/features/employee-onboarding/`
- **Scope**: Digital onboarding workflows, task automation, system integration
- **Timeline**: 27-34 weeks, 233 story points

## Agent Workflow Demonstrated

**Complete End-to-End Process**:
1. **project-prd-writer** → Creates comprehensive project PRD from transcript
2. **prd-feature-extractor** → Extracts features with development breakdown
3. **concise-feature-prd-writer** → Generates individual feature PRDs

**Scalability Proven**: Agents handle different complexity levels while maintaining methodology consistency.

## Test Transcripts Available

### Complex Projects (Ready for Testing):
- **Customer Support Platform** - Enterprise omnichannel system with AI features
- **Marketing Automation Platform** - ML-powered multi-channel automation

### Simple Projects (Ready for Testing):
- **Event Management System** - Basic community event registration and management

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

## Usage
Each agent has specific capabilities and templates. See individual agent files in `/agents/` for detailed specifications and usage instructions. Test with provided transcripts to explore different project complexity levels.