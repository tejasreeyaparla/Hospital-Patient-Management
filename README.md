# CarePoint — Hospital Patient Management System

A responsive HTML/CSS/JavaScript hospital administration interface inspired by the supplied screenshots. It includes a dashboard, patient admission, records/search/filter/edit/delete, care rounds, a priority-ordered treatment queue implemented as a singly linked list in JavaScript for demonstration, ICU transfer, discharge restrictions, supporting hospital modules, and ten separate flowcharts.

## Run locally

1. Extract the project folder.
2. Open `index.html` in a modern browser (Chrome, Edge, Firefox).
3. No package installation or build step is required. For a local server, run `python -m http.server 8000` from this folder and visit `http://localhost:8000`.

## Demo data and persistence

- The first load includes five fictional sample patients.
- Patient records are saved in this browser's `localStorage` and remain after refresh.
- Use the Patient Records page to search, filter, view, edit and delete patients.
- Use Patient Admission to create new patient records and auto-generate IDs.
- The dashboard statistics are calculated from the current patient data.
- Use the Treatment Queue page to see the linked-list priority order. Emergency is highest, Serious is medium, Normal is lowest. `Treat next patient` removes the head node and updates that patient's status to `In Treatment`.
- ICU transfer updates ward to ICU and status to `In ICU` after confirmation.
- Emergency-priority patients are blocked from discharge. A non-emergency discharge requires a summary and confirmation.

## Important academic / technical note

The original college project is implemented in **C using a linked list**. This website is a visual interface and browser-based demonstration. Its `LinkedPatientQueue` JavaScript class demonstrates singly linked-list insertion and head removal for the treatment queue; it is not the original C program and does not call a C backend. Browser `localStorage` is only the demonstration persistence layer.

For the original C implementation, retain the patient structure with fields such as patient ID, name, age, gender, illness, phone, priority, ward and `next` pointer. The C application should remain responsible for the authoritative linked-list add/display/search/update/delete operations and priority insertion. A production deployment would need a backend/API and database, authentication, authorization, audit logging, secure hosting and privacy/security review. This prototype is not suitable for real patient data or clinical use.

## Folder structure

```text
hospital-patient-management-system/
├── index.html       # Application shell and sidebar navigation
├── styles.css       # Responsive visual system and component styling
├── app.js           # Modules, patient operations, linked-list queue and demo state
└── README.md        # Setup and technical notes
```

## Flowcharts

Open **System Design & Flowcharts** from the sidebar. It contains ten individually labelled flowcharts: Add Patient, Display Patients, Search Patient, Update Patient, Delete Patient, Treatment Queue, ICU Transfer, Discharge, Main Menu / Main Controller, and Overall UI/UX Navigation.

## Reset sample data

In the browser developer console, run:

```js
localStorage.removeItem('carepoint_demo_patients_v1');
location.reload();
```

All patient names and records in the starter data are fictional.
