# Case 3. Sirius GlobalCertHub: Certificate Generation Service

## Background
The Sirius federal territory is a venue for scientific conferences, educational programmes, and sports competitions. Each event concludes with summarising results and presenting diplomas, certificates, and letters of appreciation. Many guests return to the Sirius federal territory, and information about them accumulates in local databases. There is a need to automate the routine tasks of creating reporting documents.

**Goal:** To develop a service that imports a list of participants from a CSV (XLSX) file and generates digital certificates for participants of educational programmes, scientific conferences, and sporting events.

## Core Functional Requirements

- Provide a mechanism for **uploading participant personal data** in .CSV (minimum) or .XLSX (desirable) format.
  - List of fields: Full name, email, role (participant, speaker, winner, prize-winner), place (1/2/3).
- Provide users with an interface for **adding and selecting graphical certificate templates**. Possible template formats: SVN or HTML+CSS with placeholders.
  - Some fields may relate not to a specific user, but to the generated certificate: issue_date, event_name, certificate_id.
- **Generation of a certificate** specifying personal data (PDF file).
- Implement **service integration with email** for the automatic distribution of generated certificates to participants.
- **Data storage security** and information confidentiality.

## Work Plan

### Checkpoint 1: Certificate Rendering
- **Goal:** To guarantee that the "template -> placeholder substitution -> PDF" pipeline works.
- **Expected Outcomes:** 
  - A PDF document can be obtained, for example, by running a script from the command line.
  - The substitution of at least one placeholder must work. Placeholder values can be hardcoded or passed from the command line.
  - The document is generated with Russian fonts, and Cyrillic characters are displayed correctly.

### Checkpoint 2: Mini-UI + CSV (XLSX) Import + Single/Several Certificate(s) Generation
- **Goal:** To link data input and the template through a simple interface.
- **Expected Outcomes:** 
  - It is possible to upload a template and a valid CSV or XLSX file with at least one record (preferably several) and receive the generated template.

### Checkpoint 3: Email Integration + UI Polishing + Docker
- **Goal:** To create a full "production-ready" workflow for certificate issuance.
- **Expected Outcomes:**
  - The UI is visually pleasing and allows for the input of all necessary data.
  - A batch of PDF files can be generated (preferably in a ZIP archive).
  - Optional functional capabilities are implemented (sending via email).
  - System access is restricted to authorised users (login+password).
 

---

### Rules:
- **At the time of the start of development, share the project's git repository with experts.**
- **Upload the code to your git after stop-coding.**
- **Upload the presentation to your git.**
- **Provide the code with a brief description of how to deploy the proposed solution.**
