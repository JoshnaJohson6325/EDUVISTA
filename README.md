 (cd "$(git rev-parse --show-toplevel)" && git apply --3way <<'EOF' 
diff --git a/README.md b/README.md
new file mode 100644
index 0000000000000000000000000000000000000000..de4a127838aeaad4c796b4646623432dee07163d
--- /dev/null
+++ b/README.md
@@ -0,0 +1,68 @@
+# EDUVISTA Student Course Registration System
+
+EDUVISTA is a web-based Student Course Registration System designed to help students plan, enroll in, and manage courses with confidence. The stack uses React + Tailwind CSS for the client experience, Express for the API layer, and MySQL for the data store.
+
+## Highlights
+
+- **Secure authentication** for students and administrators with role-based access.
+- **Course catalog management** with prerequisites, credits, and live seat tracking.
+- **Registration workflow** to add/drop courses, prevent duplicates, and enforce credit limits.
+- **Schedule awareness** with conflict detection and semester-based registration.
+- **Admin tools** to manage courses, prerequisites, seat limits, and registration periods.
+
+## Repository Structure
+
+```
+EDUVISTA/
+├── backend/             # Express API
+├── frontend/            # React + Tailwind UI
+└── database/            # MySQL schema and seed data
+```
+
+## Getting Started
+
+### Backend
+
+```bash
+cd backend
+npm install
+npm run dev
+```
+
+Create a `.env` file in `backend/` with:
+
+```
+DB_HOST=localhost
+DB_USER=root
+DB_PASSWORD=yourpassword
+DB_NAME=eduvista
+JWT_SECRET=replace-with-secure-key
+CLIENT_ORIGIN=http://localhost:5173
+```
+
+### Frontend
+
+```bash
+cd frontend
+npm install
+npm run dev
+```
+
+### Database
+
+Use the schema in `database/schema.sql` to create the database tables.
+
+## Suggested API Endpoints
+
+| Method | Route | Purpose |
+| ------ | ----- | ------- |
+| POST | `/api/auth/login` | Authenticate students/admins |
+| GET | `/api/courses` | List courses and seat availability |
+| POST | `/api/courses/register` | Register for a course |
+
+## Next Enhancements
+
+- Smart prerequisite validation and degree audits
+- Notification system for registration deadlines
+- PDF timetable export for semester schedules
+- Analytics dashboard for administrators
 
EOF
)
