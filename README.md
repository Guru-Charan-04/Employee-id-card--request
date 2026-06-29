# Employee ID Card Request System in ServiceNow

## Overview

The **Employee ID Card Request System** is a comprehensive ServiceNow-based solution designed to streamline the request, approval, and issuance process for new or replacement employee identification cards. This project implements an intelligent catalog fulfillment workflow that automates the lifecycle of an ID card request from submission to final administrative task resolution within the ServiceNow platform.

## Project Objectives

- **Automate request intake** through an intuitive self-service portal catalog item
- **Improve operational efficiency** through automated manager approval routing
- **Enhance service quality** by ensuring timely processing and clear status tracking
- **Provide real-time visibility** into request status and fulfillment metrics
- **Reduce manual intervention** in cross-departmental coordination and task creation

## Key Features

- **Automated Request Creation**: Intelligent catalog item capturing structured inputs (Employee Name, Department, Reason)
- **Smart Routing**: Automated assignment of approval tasks directly to the employee's designated manager
- **Status Tracking**: Real-time updates and phase tracking on the Requested Item (RITM) lifecycle
- **Integration Support**: Seamless integration with the core ServiceNow User (`sys_user`) and Department (`cmn_department`) structures
- **Reporting & Analytics**: Comprehensive tracking of average fulfillment times and request volumes
- **Scalability**: Designed to handle rapid organizational growth or routine organizational credential renewals

## Technology Stack

- **Platform**: ServiceNow
- **Languages**: JavaScript, Glide Script
- **Architecture**: ServiceNow Platform as a Service (PaaS)

## Project Phases

### 1. Ideation Phase
Conceptualization and initial requirements gathering for the employee credentialing lifecycle.

### 2. Requirement Analysis
Detailed analysis of form fields, approval criteria, and administrative fulfillment needs.

### 3. Project Design Phase
System architecture, variable schema design, flow logic mapping, and technical specifications.

### 4. Project Planning Phase
Project timeline, instance resource configuration, and testing milestones definition.

### 5. Project Development Phase
Implementation of catalog variables, execution of Flow Designer logic, and task routing modules.

### 6. Project Documentation
Comprehensive documentation including technical specifications, flow pathways, and user guides.

### 7. Project Demonstration
Demo scripts, validation cases, and presentation materials showcasing end-to-end request lifecycle capabilities.

## Installation & Setup

### Prerequisites
- ServiceNow instance
- Administrative or Catalog Administrator access to ServiceNow platform
- Basic understanding of ServiceNow Catalog Items, Variables, and Flow Designer

### Deployment Steps

1. **Access your ServiceNow instance**
2. **Import the application**
- Navigate to System Import Sets > Import > Load a file
- Select the application update set package

3. **Configure system settings**
- Set up Flow Designer trigger paths and business logic
- Configure notification templates and preferences
- Define catalog task assignment routing rules

4. **Test the system**
- Submit test catalog requests
- Verify dynamic manager approval triggers
- Validate administrative fulfillment task generation

## Usage

### Creating a Request
1. Navigate to Self-Service Portal or Service Catalog
2. Click "Employee ID Card Request"
3. Fill in required fields (employee name, department, reason for request)
4. System automatically identifies the manager and routes the approval
5. Track request status through the portal My Requests dashboard

### Dashboard Features
- Real-time active request metrics
- Reason-wise request distribution (New Hire vs. Lost/Damaged)
- Approval SLA compliance tracking
- Average card processing and issuance time analytics

## Architecture
┌─────────────────────────────────────────────┐
│       ServiceNow Platform                   │
├─────────────────────────────────────────────┤
│  Request Generation & Intake Layer          │
│  ├─ Service Catalog Item                    │
│  ├─ Variable Set UI & Validation            │
│  └─ Default Value Scripts                   │
├─────────────────────────────────────────────┤
│  Workflow & Governance Layer                │
│  ├─ Flow Designer Engine                    │
│  ├─ Dynamic Manager Approval Logic          │
│  └─ Email Notification Service              │
├─────────────────────────────────────────────┤
│  Fulfillment & Tracking Layer               │
│  ├─ Catalog Task [sc_task] Generation       │
│  ├─ Admin Team Assignment Routing           │
│  └─ RITM State Management                   │
└─────────────────────────────────────────────┘
## Configuration

### Key Configuration Areas

- **Catalog Variables**: Configuration of reference fields linking to user data structures
- **Approval Routing Rules**: Dynamic scripting to fetch the requester's supervisor dynamically
- **Fulfillment Policies**: Define target completion timelines for the physical printing team
- **Notifications**: Configure transactional email alerts for approval, rejection, and completion events
- **Custom Choices**: Add or modify selection parameters for card loss or structural modification updates

## API Reference

For detailed API documentation regarding underlying Glide APIs used in variables or custom scripts, refer to the ServiceNow developer documentation and the project's configurations in the `6. Project Documentation` folder.

## Testing

Comprehensive test cases and validation scripts are available in the project documentation folder. Test coverage includes:
- Unit tests for auto-population client scripts
- Integration tests for Flow Designer approval loops
- End-to-end request-to-fulfillment lifecycle scenarios
- Edge-case testing for users missing active manager profiles

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Approval does not route to manager | Verify that the selected employee has a valid manager configured in the `sys_user` table |
| Flow does not execute on submission | Check that the Flow is set to "Active" and mapped inside the Catalog Item configuration |
| Notification emails are skipped | Review execution logs in `sys_email` to verify system notification preferences are enabled |
| Fulfillment task missing field details | Ensure catalog variables are explicitly added to the Catalog Task action layout inside Flow Designer |

## Support & Maintenance

- **Documentation**: See the `6. Project Documentation` folder for detailed guides
- **Demonstrations**: Review `7. Project Demonstration` for system walkthroughs
- **Issues**: Report configuration bugs through the internal project track repository

## Future Enhancements

- Mobile-first catalog submission via ServiceNow Mobile Agent app
- Integration with smart-badge printing hardware via REST API integrations
- Direct image attachment variable for live user passport photo updates
- Automatic temporal digital pass provisioning while physical cards are being printed
- Asset management tracking integration to log card serial numbers against employee profiles

## Contributing

To contribute to this project:
1. Update localized configurations inside a unique Update Set
2. Run automated Instance Scan rule validation
3. Complete rigorous peer-review validations
4. Export and submit the Update Set XML payload package

## License

This project is provided as-is for corporate workplace administration and operations implementation.

## Authors & Contributors

**Project Lead**: Akhilesh

## Acknowledgments

This project represents a comprehensive implementation of ServiceNow best practices for automated employee service lifecycle and operational request tracking.

---

**Last Updated**: June 2026  
**Version**: 1.0  
**Repository**: [Employee-ID-Card-Request-System-in-ServiceNow]https://github.com/Guru-Charan-04/Employee-id-card--request.git
