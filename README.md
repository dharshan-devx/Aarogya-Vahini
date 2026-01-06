# HMS

<img src="static/images/doctors-animate.svg" align="right" height="300px">

HMS is a web application developed using Flask, a web framework in Python that aims to assist patients in obtaining the necessary medical care for their needs. The system allows users to register as patients or doctors, book appointments, and predict diseases based on symptoms. Doctors can view and manage appointments, while patients can track their appointments and update their profiles. Additionally, the system provides information on various health-related topics through blog posts and also analyses mental health conditiion of patients.

## Features
# HMS (Health Management System)

HMS is a Flask-based web app that lets patients register, book appointments, and track diagnoses while doctors manage their schedules and send prescriptions. A symptom-based ML model (Decision Tree) provides quick disease predictions from the built-in dataset.

## Problem Statement

Access to timely, organized, and personalized healthcare remains a major challenge, especially in regions where medical resources are fragmented and overloaded. Patients often struggle with scattered health information, delayed appointments, lack of early disease awareness, and minimal mental health support. On the other side, doctors face inefficient appointment management, poor patient history visibility, and limited digital tools to streamline diagnosis and follow-ups.

Existing healthcare platforms are either too complex, expensive, or narrowly focused, failing to provide an integrated solution that connects patients, doctors, diagnostics, and awareness in one place. Early-stage symptom neglect and mental health conditions often go unnoticed due to the absence of accessible, intelligent screening tools.

There is a strong need for a unified, lightweight, and intelligent health management system that enables patients to easily book appointments, track their health journey, receive preliminary disease insights, and access reliable medical content—while empowering doctors with efficient scheduling, patient data management, and digital prescription support.

This problem calls for an affordable, scalable, and technology-driven solution that bridges the gap between patients and healthcare providers, improves early detection, and promotes proactive healthcare management through data, automation, and machine learning.

## Features

- Patient and doctor registration/login with separate dashboards
- Appointment booking, doctor approvals, and email notifications via Flask-Mail
- Symptom-based disease prediction powered by scikit-learn
- Prescription PDF generation (ReportLab/pdfkit) and storage
- Blog pages and basic video call placeholder view
- SQLite persistence through Flask-SQLAlchemy

## Tech Stack

- Python 3.13, Flask 3, Flask-SQLAlchemy 3, SQLite
- ML: scikit-learn (Decision Tree), NumPy, pandas
- PDF/exports: ReportLab, pdfkit (requires wkhtmltopdf installed locally)
- Viz: Plotly

## Project Layout

- app.py: Main Flask app, routes, models, and ML utilities
- templates/: Jinja2 HTML templates (dashboards, auth, blogs, appointment flows)
- static/: CSS, JS, images, prescriptions, and training/testing CSVs
- database.db: Local SQLite database (created at runtime)
- notebooks/: Exploratory notebooks for related ML tasks (brain/lung/pneumonia, etc.)

## Prerequisites

- Python 3.13+
- wkhtmltopdf on PATH for pdfkit to render PDFs (https://wkhtmltopdf.org/)

## Setup (Windows PowerShell)

```powershell
python -m venv venv
venv\Scripts\Activate.ps1
pip install --upgrade pip
pip install -r requirements.txt
```

Create a .env file (used for email notifications):

```
MAIL_SERVER=smtp.example.com
MAIL_PORT=465
MAIL_USERNAME=you@example.com
MAIL_PASSWORD=your-password
MAIL_DEFAULT_SENDER=you@example.com
```

## Running the App

```powershell
python app.py
```

Visit http://localhost:5000 to use the app.

## Data and Models

- Symptom training/testing CSVs live in static/Data/Training.csv and static/Data/Testing.csv.
- The Decision Tree model is fit at startup inside app.py and used for predictions without an external model file.

## Notes

- The development secret key and database path are hard-coded for local use; set secure values and a persistent database URI before production.
- Email features require valid SMTP credentials in .env; without them, mailing will fail.

## License

Licensed under the MIT License. See LICENSE.


<!-- ## Contributors


