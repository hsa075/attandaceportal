KGFIPL EMPLOYEE ATTENDANCE PORTAL - RENDER FREE / LOCAL PACKAGE

RENDER WEB SERVICE SETTINGS
  Service type: Web Service
  Runtime: Python 3
  Plan: Free
  Build Command: echo "No dependencies to install"
  Start Command: python server.py
  Environment variable: TZ_HOURS=5.5
  Optional environment variable: INITIAL_STAFF_PASSWORD=KGFIPL@2026!
  If you use a different INITIAL_STAFF_PASSWORD, set the same value before first startup.
  Do NOT set DATA_DIR on Render Free. Do NOT add a Persistent Disk.

EMPLOYEE LOGIN FLOW
  The public landing page has an Employee login button.
  Clicking it opens the 12 business segments. Selecting a segment opens that segment's
  employee login form (Employee ID, registered full name and password).
  Employee accounts can only log in to the segment assigned to their employee record.
  Segment cards no longer display the internal HR-1 / HR-2 routing labels. HR staff
  permissions remain enforced internally.
  After login, employees see their attendance screen for their assigned segment only.
  After login, the employee sees two clear choices: PRESENT and ABSENT.
  PRESENT requests camera and GPS permission, captures a time-stamped photo with coordinates,
  and records check-in. The same Present action can be used later to capture check-out.
  ABSENT records the employee's absence and time for the day; once marked absent, PRESENT is
  locked for that day and HR must correct any mistake.
  Today's and historical attendance statuses are green for PRESENT and red for ABSENT.

DEMO EMPLOYEE CREDENTIALS
  These 12 accounts are assigned one-to-one to Segments 1-12. Login requires Employee ID,
  exact registered name, password, and the matching segment selection.

  Segment  Employee ID  Name           Password
  1        KGF001       Ravi Kumar     Demo@001
  2        KGF002       Priya Sharma   Demo@002
  3        KGF003       Arjun Reddy    Demo@003
  4        KGF004       Sneha Patil    Demo@004
  5        KGF005       Imran Khan     Demo@005
  6        KGF006       Anita Rao      Demo@006
  7        KGF007       Vikram Singh   Demo@007
  8        KGF008       Meena Iyer     Demo@008
  9        KGF009       Suresh Naik    Demo@009
  10       KGF010       Kavya Menon    Demo@010
  11       KGF011       Rahul Das      Demo@011
  12       KGF012       Divya Nair     Demo@012

  On an existing database, the first startup with this version performs a one-time migration
  that updates KGF001-KGF012 with these names, segments and passwords. It does not reset
  these demo passwords on subsequent restarts. Change the demo credentials before real use.

STAFF / ADMIN ACCESS
  Staff / Admin login is intentionally hidden from the public landing page. To access it,
  open https://YOUR-RENDER-SERVICE.onrender.com/?staff=1 directly. Replace the domain with
  your actual Render service URL.

  All seeded staff accounts use the temporary password: KGFIPL@2026!
  Staff must set a personal password after their first login.

  Username  Registered name
  HR1       HR - Segments 1 to 8 and 12
  HR2       HR - Segments 9 to 11
  MD        Managing Director
  ACC01     Accounts - Construction, Mining & Wood Work
  ACC02     Accounts - KGFIPL Renewable Energy
  ACC03     Accounts - KGFIPL Manufacturing
  ACC04     Accounts - KGFIPL Agriculture & Farming
  ACC05     Accounts - KGFIPL Electrical & Electronic Equipment Manufacturing
  ACC06     Accounts - KGFIPL Import & Export
  ACC07     Accounts - KGFIPL Financial & Educational Services
  ACC08     Accounts - KGFIPL Security Services & Manpower Supply
  ACC09     Accounts - Hospitality
  ACC10     Accounts - Adventures
  ACC11     Accounts - Courier

  HR can add employees to the segments assigned to that HR account. Accounts users and MD
  retain their existing reports and Excel export functions.

ACCOUNTS STAFF ATTENDANCE
  ACC01 through ACC11 can now also record their own attendance in their assigned segment.
  After Accounts login, the My Attendance panel appears at the top of the assigned segment page.
  Accounts staff use their ACC username as the employee ID and must allow camera and location
  access to complete check-in and check-out. Their attendance is included in segment reports.

LOCAL RUN
  python3 server.py
  Open http://localhost:8000

IMPORTANT FREE-TIER DATA WARNING
  The app uses SQLite and local file storage. Render Free files are ephemeral and may be lost
  after restarts or redeploys. Use only sample/test data on Render Free. Do not store actual
  employee or attendance records until database and photo storage are moved to persistent
  services.
