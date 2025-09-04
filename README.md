# Library Management System

A comprehensive Django-based library management system with features for book management, borrowing, reservations, QR code generation, and analytics.

## Features

- **Book Management**: Add, edit, delete, and categorize books
- **User Management**: Student, Teacher, and Staff registration and management
- **Borrowing System**: Track book borrowings with due dates and penalties
- **Reservation System**: Allow users to reserve books
- **QR Code Generation**: Generate QR codes for borrowing tracking
- **Analytics Dashboard**: View borrowing statistics and trends
- **Book Cover Images**: Automatic cover image fetching from URLs
- **Responsive Design**: Modern UI with Bootstrap styling

## System Requirements

- Python 3.8 or higher
- pip (Python package installer)
- Virtual environment (recommended)

## Installation Instructions

### 1. Clone or Download the Project

```bash
# If using git
git clone <repository-url>
cd Lib

# Or download and extract the project files
```

### 2. Create a Virtual Environment (Recommended)

```bash
# On Windows
python -m venv venv
venv\Scripts\activate

# On macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Navigate to the Django Project

```bash
cd myproject
```

### 5. Run Database Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Create a Superuser (Admin Account)

```bash
python manage.py createsuperuser
```

### 7. Run the Development Server

```bash
python manage.py runserver
```

### 8. Access the Application

Open your web browser and go to:
- Main application: http://127.0.0.1:8000/
- Admin panel: http://127.0.0.1:8000/admin/

## Project Structure

```
Lib/
├── myproject/                 # Django project root
│   ├── main/                  # Main application
│   │   ├── models.py         # Database models
│   │   ├── views.py          # View functions
│   │   ├── forms.py          # Form definitions
│   │   ├── urls.py           # URL routing
│   │   ├── backend/          # Backend views and forms
│   │   ├── templates/        # HTML templates
│   │   ├── static/           # Static files (CSS, JS)
│   │   └── management/       # Custom management commands
│   ├── myproject/            # Project settings
│   │   ├── settings.py       # Django settings
│   │   ├── urls.py           # Main URL configuration
│   │   └── wsgi.py           # WSGI configuration
│   ├── book_covers/          # Book cover images
│   ├── db.sqlite3            # SQLite database
│   └── manage.py             # Django management script
└── requirements.txt          # Python dependencies
```

## Key Dependencies

- **Django 5.2.1**: Web framework
- **django-jazzmin**: Enhanced admin interface
- **django-widget-tweaks**: Form enhancement
- **Pillow**: Image processing for book covers
- **qrcode**: QR code generation
- **requests**: HTTP requests for fetching book covers
- **matplotlib**: Data visualization for analytics

## Usage

### For Librarians/Staff

1. **Login to Admin Panel**: Use your superuser credentials
2. **Manage Books**: Add, edit, or remove books from the library
3. **Register Users**: Create accounts for students, teachers, and staff
4. **Process Borrowings**: Handle book checkouts and returns
5. **View Analytics**: Monitor borrowing patterns and statistics

### For Users (Students/Teachers/Staff)

1. **Register/Login**: Create an account or login with existing credentials
2. **Browse Books**: Search and filter available books
3. **Borrow Books**: Check out books with automatic due date calculation
4. **Reserve Books**: Reserve books that are currently unavailable
5. **View History**: Check your borrowing history and current loans

## Management Commands

The project includes several custom management commands:

```bash
# Fix returned status for borrowings
python manage.py fix_returned_status

# Set cover image URLs for books
python manage.py set_cover_image_url

# Force update cover image URLs
python manage.py force_cover_image_url
```

## Data Import

You can import sample data using the provided CSV file:

1. Navigate to the admin panel
2. Use the CSV upload feature to import `returns_data.csv`
3. The system will automatically create users, books, and borrowing records

## Configuration

### Environment Variables

Create a `.env` file in the project root for sensitive settings:

```env
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1
```

### Database Configuration

The default configuration uses SQLite. For production, consider using PostgreSQL or MySQL:

```python
# In settings.py
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'your_db_name',
        'USER': 'your_db_user',
        'PASSWORD': 'your_db_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

## Security Considerations

- Change the default `SECRET_KEY` in production
- Set `DEBUG=False` in production
- Use HTTPS in production
- Regularly update dependencies
- Implement proper user authentication and authorization

## Troubleshooting

### Common Issues

1. **Port Already in Use**: Change the port number
   ```bash
   python manage.py runserver 8001
   ```

2. **Database Errors**: Delete `db.sqlite3` and run migrations again
   ```bash
   rm db.sqlite3
   python manage.py migrate
   ```

3. **Static Files Not Loading**: Collect static files
   ```bash
   python manage.py collectstatic
   ```

4. **Image Upload Issues**: Ensure Pillow is installed
   ```bash
   pip install Pillow
   ```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is open source and the property of White-Templar.

## Support

For support or questions, please just cry cause I dont even know how I manage to code this. 
