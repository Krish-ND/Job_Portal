# JobPortal — Node.js + SQL (Students & Employers)

A clean, responsive job portal with separate portals for **students (internships)** and **employers** to **post/manage/delete** listings.

## Quickstart

1) Clone & install
```bash
npm i
```

2) Configure env
```bash
cp .env.example .env
# Edit DATABASE_URL to your Postgres connection string
```

3) Create DB schema
```bash
# Example using psql after creating a database named jobportal
# psql postgres -c "CREATE DATABASE jobportal;"
psql "$DATABASE_URL" -f db/schema.sql
```

4) Run the server
```bash
npm run dev
# Open http://localhost:3000
```

## API (high-level)

- `POST /api/auth/register {name,email,password,role}`
- `POST /api/auth/login {email,password}`
- `GET  /api/jobs` (public list/search)
- `POST /api/jobs` (employer) create
- `PATCH /api/jobs/:id` (employer) update
- `DELETE /api/jobs/:id` (employer) delete
- `POST /api/applications/:id/apply` (student)
- `GET  /api/applications/me` (student)
- `GET  /api/applications/job/:id` (employer) list applicants
- `PATCH /api/applications/:appId/status` (employer) update status
