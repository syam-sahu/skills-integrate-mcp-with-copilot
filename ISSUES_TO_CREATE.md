# Proposed GitHub Issues to Create

The repository: syam-sahu/skills-integrate-mcp-with-copilot

Below are eight issues (title, detailed description, acceptance criteria, and suggested labels) ready to create in GitHub. You can copy these into GitHub Issues or run the GitHub CLI to create them.

---

## 1) Add role-based authentication and session support (STUDENT / FACULTY / ADMIN)

Description:
Implement server-side authentication and session management so the application supports three roles: STUDENT, FACULTY, and ADMIN. Allow login/logout, protect role-specific endpoints, and store role in the session or token.

Acceptance criteria:
- Login endpoint that accepts credentials and returns a session (cookie) or token.
- Role is stored and used to authorize dashboard routes.
- Unauthenticated requests to protected routes return 401.

Suggested labels: `feature`, `auth`, `backend`

---

## 2) Implement multi-role dashboards and navigation (admin/faculty/student)

Description:
Add separate dashboard pages or API routes for each role with role-specific actions (e.g., admin: manage students; faculty: view assigned students; student: view & sign up for activities). Update frontend navigation to show relevant links.

Acceptance criteria:
- Three dashboards exist and are accessible only by the correct role.
- Frontend shows/hides links depending on role.

Suggested labels: `feature`, `ui`, `frontend`

---

## 3) Replace in-memory store with persistent MySQL backend + schema import

Description:
Introduce a persistent database (MySQL) for activities, students, and signups. Add configuration (environment variables) and provide the SQL schema (from the third-repo example) and migration/import instructions.

Acceptance criteria:
- App reads DB credentials from env vars and connects to MySQL.
- Activities, students, and signups persist across restarts.
- A `student.sql` or migrations file is included and documented.

Suggested labels: `backend`, `database`, `infra`

---

## 4) Add full student profile model and enrollment DB (stud_adm, extra tables)

Description:
Extend the data model to include detailed student profiles (personal info, DOB, address, class, faculty assignment), and tables to track enrollments and extras similar to `stud_adm`, `extra1`, `extra2`, `extra3`, and `extra_cirr`.

Acceptance criteria:
- DB tables exist for student profile and enrollments.
- API endpoints or admin UI to create/update student profiles.

Suggested labels: `feature`, `database`, `api`

---

## 5) Implement profile management: search, view, edit, delete students

Description:
Provide UI and API endpoints to search students (by ID or name+class), view full profiles, edit profile fields, and delete student records with appropriate confirmation.

Acceptance criteria:
- Search endpoint and UI work.
- View, edit, delete endpoints exist and respect authorization.

Suggested labels: `feature`, `ui`, `api`

---

## 6) Add photo upload and storage for student profiles

Description:
Enable uploading a profile photo for students, store images on disk or object storage, and serve them securely. Integrate with profile view UI.

Acceptance criteria:
- Upload endpoint accepts images and validates type/size.
- Stored images are retrievable via public URLs used in the profile view.

Suggested labels: `feature`, `files`, `backend`

---

## 7) Add admin utilities: last_entry tracking, enrollment management UIs

Description:
Add admin convenience features such as showing the last admission entry, bulk enrollment actions, and admin screens to manage enrollments and extras.

Acceptance criteria:
- `last_entry` tracking is persisted and displayed in admin UI.
- Admin pages exist for bulk enrollment and managing extras/tables.

Suggested labels: `enhancement`, `admin`, `ui`

---

## 8) Security & migration: move from `mysql_*` to modern DB API, hash passwords, use env config, add input validation/CSRF

Description:
Refactor legacy DB access to use a modern DB library (e.g., `mysql.connector`, `pymysql`, or SQLAlchemy for Python), store passwords hashed (bcrypt), move sensitive config to environment variables, and add input validation and CSRF protection for forms.

Acceptance criteria:
- No `mysql_*` usage remains in server code.
- Passwords are stored hashed and login checks use secure comparison.
- Config is read from env vars and documented in README.

Suggested labels: `security`, `refactor`, `backend`

---

### Next steps
- If you want, I can attempt to create these issues directly in the repository using the GitHub API / CLI if you provide credentials, or I can open a pull request that adds this file and a suggested `ISSUES_TO_CREATE.md` as a record (already added).
