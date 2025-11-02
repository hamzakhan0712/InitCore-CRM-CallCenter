InitCore CRM - Call Center Management Platform
<div align="center">
Show Image
Show Image
Show Image
Show Image

A comprehensive Django-powered CRM solution designed specifically for call center operations, lead management, and customer engagement.

Features • Installation • Usage • Documentation • Contributing

</div>
📋 Overview
InitCore CRM is a full-stack Customer Relationship Management platform built with Django that streamlines call center operations. It provides a centralized system for managing customer interactions, tracking leads, monitoring agent performance, and generating actionable insights through comprehensive analytics.

Whether you're running a sales team, customer support center, or lead generation operation, InitCore CRM offers the tools needed to organize workflows, improve team productivity, and deliver exceptional customer experiences.

✨ Features
Core Functionality
📞 Customer Management - Complete customer lifecycle tracking with detailed interaction history
📱 Call Logging System - Record, categorize, and analyze all customer calls
👥 Lead Management - Capture, assign, and convert leads through customizable pipelines
📊 Real-time Analytics - Comprehensive dashboards with performance metrics and KPIs
🔔 Activity Tracking - Monitor all customer touchpoints and agent activities
User Management
🔐 Role-Based Access Control (RBAC) - Three-tier permission system
Superadmin - Full system access and configuration
Manager - Team oversight, reporting, and resource allocation
Agent - Customer interaction and lead handling
👤 User Profiles - Customizable agent profiles with performance tracking
Communication Tools
📧 Email Integration - Send follow-ups, reminders, and notifications directly from the platform
📝 Notes & Comments - Collaborative customer notes for team alignment
🔄 Task Management - Create and assign follow-up tasks with deadlines
Technical Features
🌐 Responsive Design - Fully optimized for desktop, tablet, and mobile devices
🚀 Performance Optimized - Fast load times with efficient database queries
🔒 Secure Authentication - Django's built-in security with session management
🧩 Modular Architecture - Easy to extend and customize for specific business needs
📤 Data Export - Export reports and customer data in multiple formats
🛠️ Technology Stack
Layer	Technologies
Backend	Python 3.8+, Django 4.x
Frontend	HTML5, CSS3, JavaScript, Bootstrap 5
Database	PostgreSQL (Production), SQLite (Development)
Server	Gunicorn, Nginx
Authentication	Django Auth System
Version Control	Git, GitHub
📦 Installation
Prerequisites
Before you begin, ensure you have the following installed:

Python 3.8 or higher
pip (Python package manager)
Git
PostgreSQL (for production) or SQLite (for development)
Virtual environment tool (venv or virtualenv)
Step 1: Clone the Repository
bash
git clone https://github.com/hamzakhan0712/InitCore-CRM-CallCenter.git
cd InitCore-CRM-CallCenter
Step 2: Create Virtual Environment
bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate

# On macOS/Linux:
source venv/bin/activate
Step 3: Install Dependencies
bash
pip install -r requirements.txt
Step 4: Configure Environment Variables
Create a .env file in the root directory:

env
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1

# Database Configuration
DB_ENGINE=django.db.backends.postgresql
DB_NAME=initcore_crm
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_HOST=localhost
DB_PORT=5432

# Email Configuration
EMAIL_BACKEND=django.core.mail.backends.smtp.EmailBackend
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USE_TLS=True
EMAIL_HOST_USER=your-email@gmail.com
EMAIL_HOST_PASSWORD=your-email-password
Step 5: Database Setup
bash
# Run migrations
python manage.py makemigrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser
Step 6: Collect Static Files
bash
python manage.py collectstatic
Step 7: Run Development Server
bash
python manage.py runserver
Visit http://127.0.0.1:8000 in your browser.

🚀 Usage
Initial Setup
Login as Superadmin
Navigate to http://127.0.0.1:8000/admin
Use the superuser credentials created during setup
Create User Roles
Add Managers and Agents through the admin panel
Assign appropriate permissions to each role
Configure System Settings
Set up call disposition types
Configure lead sources and status categories
Customize email templates
Daily Operations
For Agents
Log customer calls with detailed notes
Update lead status and progression
Schedule follow-up tasks
Access assigned customer records
For Managers
Monitor team performance metrics
Assign leads to agents
Review call logs and quality
Generate performance reports
For Superadmins
Manage user accounts and permissions
Configure system-wide settings
Access complete analytics dashboard
Export comprehensive reports
📁 Project Structure
InitCore-CRM-CallCenter/
├── crm/                    # Main CRM application
│   ├── models.py          # Database models
│   ├── views.py           # View controllers
│   ├── forms.py           # Form definitions
│   ├── urls.py            # URL routing
│   └── templates/         # HTML templates
├── initcore/              # Project configuration
│   ├── settings.py        # Django settings
│   ├── urls.py            # Root URL configuration
│   └── wsgi.py            # WSGI configuration
├── static/                # Static files (CSS, JS, images)
├── media/                 # User-uploaded files
├── requirements.txt       # Python dependencies
├── manage.py             # Django management script
└── README.md             # Documentation
🔧 Configuration
Database Configuration
For PostgreSQL (Recommended for Production):

python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'initcore_crm',
        'USER': 'your_username',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
For SQLite (Development Only):

python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}
Email Configuration
Update settings.py with your email provider settings for sending notifications and reminders.

🐳 Docker Deployment (Optional)
bash
# Build Docker image
docker build -t initcore-crm .

# Run container
docker run -p 8000:8000 initcore-crm
📊 API Documentation
InitCore CRM provides RESTful API endpoints for integration with external systems. Documentation is available at /api/docs after running the server.

🧪 Testing
Run the test suite:

bash
# Run all tests
python manage.py test

# Run specific app tests
python manage.py test crm

# Run with coverage
coverage run --source='.' manage.py test
coverage report
🤝 Contributing
We welcome contributions! Please follow these steps:

Fork the repository
Create a feature branch (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add some AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a Pull Request
Coding Standards
Follow PEP 8 style guide for Python code
Write descriptive commit messages
Add tests for new features
Update documentation as needed
📝 License
This project is licensed under the MIT License - see the LICENSE file for details.

👨‍💻 Author
Hamza Khan

GitHub: @hamzakhan0712
LinkedIn: Connect with me
🙏 Acknowledgments
Django community for excellent documentation
Bootstrap for responsive UI components
All contributors who help improve this project
📞 Support
For support, questions, or feature requests:

Open an issue on GitHub
Email: support@initcore.com
Documentation: Wiki
🗺️ Roadmap
 Mobile application (iOS/Android)
 Advanced AI-powered lead scoring
 WhatsApp and SMS integration
 Voice call recording and transcription
 Multi-language support
 Custom report builder
 Third-party CRM integrations
<div align="center">
⭐ Star this repository if you find it helpful!

Made with ❤️ by Hamza Khan

</div>
