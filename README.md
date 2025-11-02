# CallCore CRM

<div align="center">

![Django](https://img.shields.io/badge/Django-5.0.6-green.svg)
![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)
![Status](https://img.shields.io/badge/Status-Active-success.svg)

**A comprehensive, enterprise-grade CRM solution designed specifically for call center operations**

</div>

---

## 📋 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [System Architecture](#system-architecture)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Module Details](#module-details)
- [API Documentation](#api-documentation)
- [Database Schema](#database-schema)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

---

## 🎯 Overview

**CallCore CRM** is a full-stack, production-ready Customer Relationship Management system built with Django, specifically engineered for call center environments. It provides a complete suite of tools to manage leads, track agent performance, process customer payments, generate invoices, and monitor real-time operations.

The platform supports multi-role access (Team Leaders, Agents, Admins), real-time WebSocket communication, comprehensive reporting, and automated workflows to streamline call center operations.

---

## ✨ Key Features

### 🔹 Lead Management
- **Lead Import & Assignment**: Bulk import leads and intelligent assignment to agents/teams
- **Disposition Tracking**: Multi-level disposition system (Fresh, Connected, Not Connected) with sub-dispositions
- **Lead History**: Complete audit trail of all lead interactions and modifications
- **Lead Transfer**: Seamless lead transfer between agents with full record-keeping
- **Reminder System**: Automated follow-up reminders with date/time scheduling
- **Duplicate Detection**: Unique contact validation to prevent duplicate leads

### 🔹 Sales & Customer Management
- **Payment Processing**: Multi-payment method support with transaction tracking
- **Package Management**: Flexible package system with start/end date tracking
- **GST Calculation**: Automated tax computation (18% GST) with amount breakdowns
- **Customer Verification**: Payment verification workflow with attachment support
- **Invoice Generation**: Automated PDF invoice generation with company branding
- **Customer ID System**: Unique customer identification across multiple transactions

### 🔹 Team & User Management
- **Role-Based Access Control**: Three-tier access system (Admin, Team Leader, Agent)
- **Team Structure**: Hierarchical team organization with leader assignment
- **User Profiles**: Comprehensive profile management with status tracking
- **User Limits**: Built-in system for managing user capacity (25-user default limit)
- **Status Management**: Track employee status (Active, Inactive, On Resign Period, Absconded)

### 🔹 Attendance & Break Management
- **Automated Attendance**: Clock-in/clock-out system with status calculation
- **Break Tracking**: Multiple break types with duration monitoring
- **Working Hours Calculation**: Automatic computation of effective working time
- **Late Login Detection**: Grace period management and late marking
- **Half-Day Logic**: Intelligent attendance status based on working hours
- **Real-Time Status**: Live tracking of logged-in users and break status

### 🔹 Performance Analytics
- **Sales Commitments**: Agent-level sales targets with tracking
- **Sales History**: Historical performance data for trend analysis
- **Team Performance**: Aggregate team statistics and comparisons
- **Real-Time Dashboards**: Live metrics for monitoring operations
- **Custom Reports**: Generate detailed reports for various metrics

### 🔹 Complaint Management
- **Ticket System**: Full-featured complaint tracking with priorities
- **Status Workflow**: Multi-stage resolution process (Pending → In Progress → Resolved → Closed)
- **Priority Levels**: Four-tier priority system (Low, Medium, High, Urgent)
- **Resolution Tracking**: Automatic timestamp for resolved complaints

### 🔹 Document & Invoice Generation
- **PDF Invoice Generation**: Automated invoice creation with wkhtmltopdf
- **Company Branding**: Customizable company details, logo, and tagline
- **Amount in Words**: Automatic numeric-to-text conversion for invoices
- **Attachment Support**: File upload for payment proofs and documents

---

## 🛠 Technology Stack

### **Backend**
- **Framework**: Django 5.0.6
- **Language**: Python 3.8+
- **ORM**: Django ORM
- **Database**: PostgreSQL (psycopg2-binary)
- **Task Queue**: Channels 4.1.0 (WebSocket support)
- **ASGI Server**: Daphne 4.1.2

### **Frontend**
- **Templating**: Django Templates
- **Styling**: HTML5, CSS3
- **Interactivity**: JavaScript (included in templates)

### **Key Dependencies**
- **Authentication**: Django Auth System
- **File Storage**: Django Storage (Media files)
- **Static Files**: WhiteNoise 6.7.0
- **PDF Generation**: pdfkit 1.0.0
- **Data Processing**: Pandas 2.2.2, NumPy 2.0.0
- **Excel Support**: openpyxl 3.1.5, xlrd 2.0.1
- **Database Backup**: django-dbbackup 4.1.0
- **Number Conversion**: num2words 0.5.13
- **Environment Variables**: python-decouple 3.8
- **WebSockets**: Twisted 24.3.0, Autobahn 23.6.2

---

## 🏗 System Architecture

```
CallCore-CRM/
│
├── CallCenter_App/          # Main Django application
│   ├── models.py            # Database models (Lead, User, Payment, etc.)
│   ├── views.py             # Business logic and view handlers
│   ├── urls.py              # URL routing
│   ├── forms.py             # Form definitions
│   ├── admin.py             # Django admin configuration
│   └── migrations/          # Database migrations
│
├── InitCore_CallCenter_CRM/ # Project configuration
│   ├── settings.py          # Django settings
│   ├── urls.py              # Root URL configuration
│   ├── asgi.py              # ASGI configuration
│   └── wsgi.py              # WSGI configuration
│
├── template/                # HTML templates
│   ├── base.html
│   ├── dashboard.html
│   ├── leads/
│   ├── sales/
│   └── reports/
│
├── media/                   # User-uploaded files
│   ├── attachments/
│   ├── logos/
│   └── invoice_pdfs/
│
├── requirements.txt         # Python dependencies
├── manage.py               # Django management script
└── wkhtmltopdf.exe         # PDF generation binary
```

---

## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- PostgreSQL 12+ (or SQLite for development)
- pip (Python package manager)
- Virtual environment tool (venv/virtualenv)
- Git

### Step-by-Step Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/hamzakhan0712/CallCore-CRM.git
   cd CallCore-CRM
   ```

2. **Create Virtual Environment**
   ```bash
   # Windows
   python -m venv venv
   venv\Scripts\activate

   # Linux/Mac
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Environment Configuration**
   Create a `.env` file in the project root:
   ```env
   SECRET_KEY=your-secret-key-here
   DEBUG=True
   DATABASE_URL=postgresql://user:password@localhost:5432/callcore_db
   ALLOWED_HOSTS=localhost,127.0.0.1
   ```

5. **Database Setup**
   ```bash
   # Create database migrations
   python manage.py makemigrations

   # Apply migrations
   python manage.py migrate

   # Create superuser
   python manage.py createsuperuser
   ```

6. **Collect Static Files**
   ```bash
   python manage.py collectstatic
   ```

7. **Run Development Server**
   ```bash
   python manage.py runserver
   ```

8. **Access the Application**
   - URL: `http://localhost:8000`
   - Admin Panel: `http://localhost:8000/admin`

---

## ⚙️ Configuration

### Database Configuration (PostgreSQL)

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'callcore_db',
        'USER': 'your_db_user',
        'PASSWORD': 'your_db_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

### WebSocket Configuration

For real-time features, configure ASGI:

```python
# asgi.py
import os
from django.core.asgi import get_asgi_application
from channels.routing import ProtocolTypeRouter, URLRouter
from channels.auth import AuthMiddlewareStack

os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'InitCore_CallCenter_CRM.settings')

application = ProtocolTypeRouter({
    "http": get_asgi_application(),
    "websocket": AuthMiddlewareStack(
        URLRouter(
            # Your WebSocket URL patterns
        )
    ),
})
```

### Company Settings

Configure your company details in the Django admin panel:
- Company Name
- Address
- GSTIN (Tax ID)
- Email & Phone
- Logo (for invoices)
- About & Tagline

---

## 📖 Usage

### For Administrators

1. **Initial Setup**
   - Configure company details in admin panel
   - Create break types (Lunch, Tea Break, Personal, etc.)
   - Set up packages and pricing
   - Add payment methods
   - Create sub-dispositions

2. **User Management**
   - Create Team Leader accounts
   - Create Agent accounts
   - Assign agents to teams
   - Set sales commitments

### For Team Leaders

1. **Lead Management**
   - Import leads via CSV/Excel
   - Assign leads to agents
   - Monitor team performance
   - Review lead history
   - Transfer leads between agents

2. **Sales Tracking**
   - Review team sales
   - Verify payments
   - Generate reports

### For Agents

1. **Daily Operations**
   - Clock in/out
   - Manage break time
   - Call leads
   - Update dispositions
   - Add remarks and reminders

2. **Sales Processing**
   - Convert leads to customers
   - Record payment details
   - Upload payment proofs
   - Generate invoices

---

## 📊 Module Details

### Lead Model
- **Fields**: Name, Contact, State, Capital, Assignment, Disposition, Reminder
- **Features**: Auto sub-disposition, history tracking, transfer records
- **Validation**: Unique contact numbers with regex validation

### User Profile Model
- **Roles**: Team Leader, Agent
- **Status**: Active, Inactive, On Resign Period, Absconded
- **Features**: Break status, commitment tracking, team relationships

### Payment & Invoice System
- **Customer ID**: Auto-generated 12-digit unique ID
- **GST Calculation**: 18% tax with automatic breakdown
- **Invoice Number**: 8-digit unique invoice identifier
- **PDF Generation**: Branded invoice PDFs with company details

### Attendance System
- **Shift Timing**: 9:00 AM - 6:00 PM
- **Grace Period**: 10 minutes
- **Half-Day Threshold**: 4.5 hours
- **Auto Status**: Based on effective working hours

---

## 🗄️ Database Schema

### Core Models
1. **UserProfile**: Extended user information with role and status
2. **Team**: Team structure with leader and agents
3. **Lead**: Lead information with disposition tracking
4. **LeadHistory**: Audit trail for lead changes
5. **LeadTransferRecord**: Transfer history between agents
6. **PaidCustomer**: Customer payment records
7. **Invoice**: Invoice generation records
8. **InvoicePDF**: PDF storage for invoices
9. **Attendance**: Daily attendance tracking
10. **Break**: Break time management
11. **Complaint**: Customer complaint system
12. **Company**: Organization details (singleton)
13. **Package**: Service packages
14. **PaymentMethod**: Payment options
15. **SubDisposition**: Lead sub-categories
16. **BreakType**: Break categories
17. **AgentSalesHistory**: Sales performance tracking

---

## 🔌 API Documentation

The application uses Django's built-in views. For custom API endpoints, refer to the `views.py` file in the CallCenter_App directory.

### Authentication
- Session-based authentication
- CSRF protection enabled
- Role-based access control

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/YourFeatureName
   ```
3. **Commit your changes**
   ```bash
   git commit -m "Add: Your feature description"
   ```
4. **Push to your fork**
   ```bash
   git push origin feature/YourFeatureName
   ```
5. **Create a Pull Request**

### Code Standards
- Follow PEP 8 style guide
- Write descriptive commit messages
- Add comments for complex logic
- Update documentation for new features

---

## 📝 License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## 🆘 Support

### Documentation
- [Django Documentation](https://docs.djangoproject.com/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)

### Contact
- **Developer**: Hamza Khan
- **GitHub**: [@hamzakhan0712](https://github.com/hamzakhan0712)
- **Repository**: [CallCore-CRM](https://github.com/hamzakhan0712/CallCore-CRM)

### Reporting Issues
Please report bugs and feature requests through [GitHub Issues](https://github.com/hamzakhan0712/CallCore-CRM/issues)

---

## 🎯 Roadmap

- [ ] REST API implementation
- [ ] Mobile app integration
- [ ] Advanced analytics dashboard
- [ ] Email notification system
- [ ] SMS integration
- [ ] Multi-language support
- [ ] Dark mode theme
- [ ] Export reports to PDF/Excel
- [ ] WhatsApp integration
- [ ] Call recording integration

---

## 📸 Screenshots

*Add screenshots of your application here*

---

## 🙏 Acknowledgments

- Django Software Foundation
- PostgreSQL Global Development Group
- All contributors and users of CallCore CRM

---

<div align="center">

**Made with ❤️ for Call Centers Worldwide**

⭐ Star this repository if you find it helpful!

</div>
