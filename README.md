# Implement Client Script & UI Policy (Incident)

## Project Overview

This project demonstrates the implementation of **Client Scripts and UI Policies in ServiceNow Incident Management**.

The main purpose is to improve data accuracy and consistency in Incident records by controlling field behavior, automating values, and validating information before saving.

## Objective

The objective of this project is to use ServiceNow client-side controls to:

- Make fields mandatory based on conditions.
- Automatically populate field values.
- Control field behavior such as read-only.
- Validate Incident records before submission.
- Control changes made through list editing.

## Technologies Used

- ServiceNow
- Incident Management
- UI Policy
- UI Policy Actions
- Client Scripts
- JavaScript

## Implementation

### 1. UI Policy – High Impact Control

A UI Policy named **High Impact Control** was created on the Incident table.

**Condition:**

- Impact is **1 – High**

**Action:**

- Assignment Group is made mandatory.
- Reverse if false is enabled.

### 2. UI Policy Action – Urgency

A UI Policy Action was configured for the **Urgency** field.

When Impact is High:

- Urgency becomes **Read-only**.

### 3. onChange Client Script

An **onChange Client Script** was created for the Impact field.

When Impact is changed to High:

- Urgency is automatically set to High.
- An information message is displayed.

### 4. onSubmit Client Script

An **onSubmit Client Script** was created to validate the Assigned To field.

When Impact is High and Assigned To is empty:

- The Incident cannot be saved.
- An error message is displayed.

### 5. onCellEdit Client Script

An **onCellEdit Client Script** was configured for the State field to control State changes through list editing.

## Testing

The configuration was tested using:

- Mandatory field validation.
- Successful Incident save.
- Reverse condition testing.
- List edit testing.
- Form-based State update.

## Result

The project demonstrates how UI Policies and Client Scripts can work together to control Incident form behavior, automate field values, validate records, and maintain data integrity.

## Documentation

The complete project report is available in:

**Implement_Client_Script_UI_Policy_Incident_Report.docx**

## Team ID

**SWDID-2026-6471**

## Project Title

**Implement Client Script & UI Policy (Incident)**
