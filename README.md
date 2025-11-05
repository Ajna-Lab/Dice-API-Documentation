# DiceSMS Gateway API Documentation

This repository contains the documentation for the DiceSMS Gateway API, a comprehensive SMS solution for businesses to send and receive SMS via a web-based API.

## Setup Instructions

### 1. Clone the Repository

```bash
git clone git@github.com:Ajna-Lab/Dice-API-Documentation.git
cd docs/
```

### 2. Create Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Linux/Mac:
source venv/bin/activate

# On Windows:
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
# Install MkDocs Material theme
pip install mkdocs-material
```

### 4. Serve Documentation Locally

```bash
# Run the development server
mkdocs serve
```

The documentation will be available at `http://127.0.0.1:8000/`

### 5. Build Static Site

```bash
# Generate static HTML files
mkdocs build
```

The built site will be in the `site/` directory.

## Project Structure

```
.
├── mkdocs.yml                          # MkDocs configuration file
├── docs/
│   ├── index.md                        # Homepage
│   ├── getting_started.md              # Getting started guide
│   ├── assets/
│   │   ├── dice_logo.png              # Logo
│   │   └── favicon.ico                # Favicon
│   ├── img/                           # Images
│   ├── sms/
│   │   ├── authentication.md          # API authentication
│   │   ├── send_sms.md                # SMS sending endpoints
│   │   └── sms_delivery_report.md     # SMS reporting
│   └── transactions/
│       └── transaction_report.md      # Transaction reports
└── .gitignore                         # Git ignore file
```

## Documentation Sections

- **Overview**: Introduction to DiceSMS Gateway API ([docs/index.md](docs/index.md))
- **Getting Started**: Account setup and API token generation ([docs/getting_started.md](docs/getting_started.md))
- **API Authentication**: Token-based authentication ([docs/sms/authentication.md](docs/sms/authentication.md))
- **Send SMS**: SMS sending endpoints ([docs/sms/send_sms.md](docs/sms/send_sms.md))
- **Report**: Batch IDs and delivery reports ([docs/sms/report.md](docs/sms/report.md))
- **Transaction Report**: Credit purchase transactions ([docs/transactions/transaction_report.md](docs/transactions/transaction_report.md))

## Theme and Features

This documentation uses the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme with:

- Light/Dark mode toggle
- Navigation path breadcrumbs
- Responsive design
- Social media links (GitHub, LinkedIn)
- Custom logo and favicon

## Configuration

The site configuration is managed in [mkdocs.yml](mkdocs.yml). Key configurations include:

- Site name and navigation structure
- Material theme settings
- Color schemes
- Logo and favicon
- Social media links

