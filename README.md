📽️ Video Authentication & Upload System (Django)

A complete Django-based project that includes User Registration, Login/Logout, and an advanced Video Upload System with duplicate detection using SHA-256 hashing, file validation, and Bootstrap UI.

📌 Features
🔐 Authentication System

User Registration

User Login / Logout

Form validation with custom error messages

Navbar updates dynamically based on authentication state

🎞️ Video Upload System

Upload videos using Django FileField

Save file metadata: size, hash, uploader

SHA-256 hash computation for duplicate video detection

Video preview player

Stores files inside /media/videos/

Only logged-in users can upload

🗂️ Project Structure Includes

Django apps: accounts, videos

Templates system (with Bootstrap UI)

Static & media configuration

ModelForms for registration & uploads

🛠️ Installation & Setup
1️⃣ Create & Activate Virtual Environment
Windows (PowerShell)
.\venv\Scripts\Activate

macOS / Linux
source venv/bin/activate

2️⃣ Install Django
pip install django
python -m django --version

3️⃣ Apply Initial Migrations
python manage.py migrate

4️⃣ Create Superuser
python manage.py createsuperuser

📁 Project Apps
accounts app

Handles:

Registration (ModelForm)

Login / Logout (Django Auth)

Templates: login, register

videos app

Handles:

Video model

Video upload

Duplicate detection

Video listing

📂 Important Files Overview
Templates

layout.html → main layout with navbar

home.html → homepage

register.html → registration page

login.html → login page

videos/home.html → video display + upload form

⚙️ Authentication System
Django Settings
LOGIN_URL = 'login'
LOGIN_REDIRECT_URL = 'videos:home'
LOGOUT_REDIRECT_URL = 'accounts:login'

URL Routing

accounts/urls.py includes:

/register/

/login/ (LoginView)

/logout/ (custom logout view)

📤 Video Upload System
Video Model (videos/models.py)

Includes:

title, description

file (stored in /media/videos/)

file size

SHA-256 hash

uploader (ForeignKey to User)

File Validation

Max size: 500 MB

Ensures file exists

Computes SHA-256 to detect duplicates

Hash Logic (videos/utils.py)

Reads file in chunks to avoid memory issues — efficient for large videos.

Upload Flow (videos/views.py)

Validate form

Compute file hash

Check duplicate

Save video

Show success/failure message

🖥️ Video Preview

Each uploaded video is shown as:

<video width="320" controls>
    <source src="{{ v.file.url }}" type="video/mp4">
</video>

🌐 Running the Development Server
python manage.py runserver

📦 Database Migrations
python manage.py makemigrations
python manage.py migrate

📸 Screens Included (if any)

Homepage with videos

Upload form

Registration page

Login page

Navbar for authenticated users

🚀 Summary

This Django project provides:

Full authentication

Secure video upload

Duplicate detection

Clean UI using Bootstrap

Modular, scalable architecture

Perfect for:

Learning Django

Building video-based applications

Creating authentication + file upload systems
