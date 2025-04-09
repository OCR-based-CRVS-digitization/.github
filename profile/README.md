# OCR-Based CRVS Form Digitalization

A comprehensive web platform built with Node.js, React.js, and PostgreSQL, designed to streamline the digitization of Civil Registration and Vital Statistics (CRVS) forms. This system utilizes Optical Character Recognition (OCR) to process handwritten forms, extract information, and enable accurate digitalization with built-in correction capabilities.

## System Overview

This platform consists of three integrated components that work together to provide a complete form digitization solution:

1. **Frontend Application**: A React-based user interface for uploading, reviewing, validating, and managing CRVS forms.
2. **Main Backend API**: An Express.js service handling authentication, workspace management, and workflow orchestration.
3. **OCR Processing Service**: A specialized microservice for form data extraction and correction.

Together, these components create a workflow that transforms paper CRVS forms into structured digital data that can be validated, corrected, and stored.

## Project Repositories

### 1. [OCR-Based CRVS Digitization Frontend](https://github.com/OCR-based-CRVS-digitization/OCR_Based_CRVS__Form_Digitalization)

The frontend application provides a user-friendly interface for the entire digitization process:

- Secure JWT-based authentication
- Workspace management for organizing forms
- Form upload and lifecycle tracking
- Side-by-side validation of OCR data with original form images
- Responsive design built with Bootstrap

**Tech Stack**: React v18, React Router, Context API, Bootstrap v5, CSS Modules

### 2. [OCR-Based CRVS Digitization Backend](https://github.com/OCR-based-CRVS-digitization/CRVS_BackEnd)

The main backend API manages the core business logic and coordinates the overall system:

- User and admin authentication
- Workspace organization and statistics
- Form lifecycle management (Upload → Validate → Draft → Finalize)
- Integration with Firebase for file storage
- Communication with the OCR service

**Tech Stack**: Node.js, Express.js, Prisma ORM, PostgreSQL, JWT, Firebase Storage

### 3. [OCR-Correction Service](https://github.com/OCR-based-CRVS-digitization/OCR-Correction)

A specialized microservice that handles the OCR processing and data extraction:

- Form processing from PDFs or images
- Tesseract.js OCR engine integration
- Support for various field types (text, numeric, date, checkbox)
- Automated correction and validation of extracted data
- Schema-driven configuration for form fields

**Tech Stack**: Node.js, Express.js, Tesseract.js, Jimp, Prisma ORM, node-poppler

## System Architecture

```
┌─────────────────┐       ┌─────────────────┐       ┌─────────────────┐
│                 │       │                 │       │                 │
│  React Frontend │◄─────►│  Backend API    │◄─────►│  OCR Service    │
│                 │  JWT  │                 │  API  │                 │
└─────────────────┘       └─────────────────┘       └─────────────────┘
        ▲                         ▲                         ▲
        │                         │                         │
        ▼                         ▼                         ▼
┌─────────────────┐       ┌─────────────────┐       ┌─────────────────┐
│                 │       │                 │       │                 │
│  User Interface │       │   PostgreSQL    │       │ Form Processing │
│    Workflow     │       │    Database     │       │    & Schema     │
│                 │       │                 │       │                 │
└─────────────────┘       └─────────────────┘       └─────────────────┘
```

## Workflow

1. **Form Upload**: Users upload scanned CRVS forms (PDFs) through the frontend
2. **Storage**: Forms are stored in Firebase via the main backend
3. **OCR Processing**: The backend triggers the OCR service to extract data
4. **Validation**: Users review and correct extracted data in the frontend
5. **Finalization**: Corrected data is stored in the database as validated records

## Getting Started

To set up the complete system:

1. Clone all three repositories
2. Follow the installation instructions in each repository's README
3. Configure the environment variables to ensure proper communication between services
4. Start the services in this order:
   - OCR Service
   - Main Backend API
   - Frontend Application

Detailed setup instructions are available in each repository's documentation.

## Use Cases

- **Educational Institutions**: Digitize student registration forms
- **Government Agencies**: Process civil registration documents
- **Healthcare Organizations**: Convert patient intake forms
- **Research Institutions**: Digitize survey responses
- **NGOs**: Process beneficiary registration forms

