# API Data

This folder contains the JSON Server database for the Job Portal application.

## File Structure

- `db.json` - Main database file containing all API data

## Database Collections

### Jobs
- Complete job listings with details
- Fields: title, company, location, type, workMode, experience, salary, etc.
- Sample: 6 job listings

### Companies
- Company information
- Fields: name, logo, description, size, industry, website
- Sample: 6 companies

### Applications
- Job applications submitted by users
- Fields: jobId, userId, name, email, phone, resume, coverLetter, status
- Sample: 1 application

### Categories
- Job categories
- Fields: name, icon, jobCount
- Sample: 6 categories

## Running JSON Server

From the project root:

```bash
# Start JSON Server only
npm run server

# Or start both frontend and backend
npm run dev:full
```

## API Endpoints

Base URL: `http://localhost:3000`

### Jobs
- `GET /jobs` - Get all jobs
- `GET /jobs/:id` - Get job by ID
- `POST /jobs` - Create new job
- `PATCH /jobs/:id` - Update job
- `PUT /jobs/:id` - Replace job
- `DELETE /jobs/:id` - Delete job

### Companies
- `GET /companies` - Get all companies
- `GET /companies/:id` - Get company by ID
- `POST /companies` - Create company
- `PATCH /companies/:id` - Update company
- `DELETE /companies/:id` - Delete company

### Applications
- `GET /applications` - Get all applications
- `GET /applications/:id` - Get application by ID
- `POST /applications` - Submit application
- `PATCH /applications/:id` - Update application
- `DELETE /applications/:id` - Delete application

### Categories
- `GET /categories` - Get all categories
- `GET /categories/:id` - Get category by ID

## Query Parameters

JSON Server supports various query parameters:

```bash
# Filter
GET /jobs?type=Full-time
GET /jobs?workMode=Remote&experience=Mid Level

# Pagination
GET /jobs?_page=1&_limit=10

# Sort
GET /jobs?_sort=postedDate&_order=desc

# Full-text search
GET /jobs?q=developer

# Relationships
GET /jobs?_expand=company
GET /applications?_embed=job
```

## Adding New Data

1. Edit `db.json` file
2. JSON Server will automatically reload
3. No restart needed

## Backup

It's recommended to keep a backup of `db.json`:

```bash
cp api/db.json api/db.backup.json
```
