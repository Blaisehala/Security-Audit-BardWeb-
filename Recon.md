# BardWeb Django Application Reconnaissance

## Application Purpose
The Bard Alumni Website is a membership-based social platform designed to connect Barding High school alumni. It provids a centralized  hub for alumni to network, share updated, organize events, donate to school initiatives and maintain conncections. Importantly it helps in tracking  financial investment  by members. The platform features member verification through M-pesa payment intergration, ensures only registerded alumni can access community features and includes administrative tools for managing membershp, events and donations

## Technology Stack
- Django version: 5.1.3
- Django version:3.11+
- Database:PostgreSQL 16 (Production: Render PostgreSQL, Development: Local PostgreSQL)
- Authentication:Django's built-in authentication system with custom User model
- Web Server : Gunicorn (production)
- Static Files: WhiteNoise + Cloudinary
- Key Libraries: 

    - **psycopg2-binary==2.9.9** -- PostgreSQL adapter
  

    - **python-decouple==3.8** -- Environment variable management
  

    - **dj-database-url==2.2.0** -- Database URL parsing

    - **whitenoise==6.8.2** --   Static file serving
 
    - **cloudinary==1.41.0** --  Cloud media storage

    - **django-cloudinary-storage==0.3.0** --Django integration for Cloudinary
    - **Pillow==10.4.0**  -- Image processing
 

## User Roles & Permissions
- [ ] Anonymous users can: 
- [ ] Authenticated users can: 
- [ ] Admin users can: 

## Data Models
1. User - fields: 
2. Task - fields: 
3. [etc]

## API Endpoints Map
### Authentication
- POST /api/register/ - Creates new user
- POST /api/login/ - Returns JWT token
[complete this for EVERY endpoint]

## Data Flow Example
"User registers -> receives JWT -> creates task -> task saved with user_id -> user queries their tasks"

## Potential Attack Surface (Initial Thoughts)
- User input points: registration form, login, task creation, search
- Database queries: search functionality looks suspicious
- Authentication: need to test authorization on task endpoints
- File uploads: [if applicable]