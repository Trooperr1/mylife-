# My Life OS: requirements check

This document checks every part of the original prompt against the application in `index.html`.
✅ means the feature is built and was tested in a real browser (Chromium via Playwright), with the file opened directly from disk. ⚠️ marks a limit set by the browser, which the app explains to the user.

**Automated verification (latest run)**
- 70 end-to-end feature tests, 23 tests for later additions and 1 journal-category test: all passing, no JavaScript errors.
- Every page and every tab renders without errors.
- "No fake buttons" scan: 102 screens and all 29 forms opened. All 116 buttons/actions, 24 change handlers, 8 Enter-key handlers and every search box are connected to working code.
- Mobile check (iPhone 13 size): no horizontal scrolling; the menu slides in from the side.

| Part | Requirement | Status | Where in the app |
|---|---|---|---|
| 1 | Premium, minimal design; dark/light mode; responsive; animations; icons; charts; sidebar; search; custom dashboard | ✅ | Whole app. Moon/sun button in the top bar; Settings → Appearance (theme and accent colour) |
| 2 | Dashboard: greeting, date, live clock, priorities, today's tasks, completion %, schedule, appointments, deadlines, important dates, birthdays, goals, long-term progress, active businesses, business performance, budget, payments, habits, journal, quick notes, quote, weekly stats, quick-add menu | ✅ | Dashboard (27 widgets) |
| 2 | Rearrange / hide / resize / pin widgets; choose what comes first; quick-access button everywhere | ✅ | Dashboard → Customize; Settings → Dashboard; the floating **+** button |
| 3 | My Day: tasks, priorities, morning and evening routines, personal/school/business groups, appointments, time blocks, schedule, shopping list, things to remember, reminders, daily goals, reflection | ✅ | My Day |
| 3 | Task fields: title, description, due date and time, priority, category, tags, subtasks, notes, status, repeat, reminder, project, business, goal | ✅ | Task form |
| 3 | Task operations: create, edit, delete, complete, duplicate, postpone, archive, search, filter, sort, drag & drop | ✅ | Tasks (⋯ menu, toolbar, drag handle) |
| 3 | Views: today, tomorrow, upcoming, overdue, all, completed, priority, by project, by business; automatic progress | ✅ | Tasks chips; list or board layout |
| 4 | Calendar: day, week, month and year views; 13 categories; recurring events; custom reminders; locations; colours; countdowns; upcoming list; search; links to projects, businesses, goals and contacts | ✅ | Calendar |
| 5 | Journal: 10 daily prompts, automatic date and time, multiple entries per day, rich text, search, edit/delete, tags **and categories**, optional mood, attached notes, links to tasks and projects, calendar navigation, monthly and yearly reflections, statistics, private section, life timeline | ✅ | My Journal |
| 6 | My Future: 9 planning periods, 12 life categories, vision, ambitions, goals, milestones, target dates, progress, action plans, challenges, opportunities, notes, dependencies, success criteria, completion history, vision board, timeline | ✅ | My Future, Goals |
| 6 | Vision → Goal → Milestones → Project → Tasks → daily actions | ✅ | **Plan an ambition** (My Future / Goals) |
| 7 | Business Hub: unlimited businesses with full profiles (logo, vision, mission, partners, team, status, launch date…) | ✅ | Business Hub |
| 7 | Business planning: market research, competitors, target market, customer profiles, products, services, pricing, marketing, sales, operations, growth, risks/opportunities/strengths/weaknesses, business plan, contacts, meeting notes | ✅ | Business → Planning, and Contacts & meetings |
| 7 | Business finances: investment, capital contributions, startup and operating costs, revenue, profit/loss, cash flow, customer payments, unpaid invoices, supplier payments, monthly and annual reports, projections | ✅ | Business → Finances, and Reports |
| 7 | Performance: revenue, expense and profit charts, monthly comparisons, growth, sales targets, customer statistics, project progress | ✅ | Business → Overview |
| 7 | 7 statuses; each business's finances separate from personal money and from other businesses | ✅ | Tested |
| 8 | Idea vault: all listed fields, including difficulty and category; search, categorise, compare, rank, favourites, archive; convert to project or business; evaluation system | ✅ | Business Ideas |
| 9 | Projects: all fields; tasks, subtasks, milestones, progress, deadlines, calendar, budget, team, responsibilities, activity history; list, Kanban, calendar, timeline and overview views; the 5 required Kanban columns | ✅ | Projects |
| 10 | Personal finance: income and expense categories, monthly totals, remaining balance, daily spending, budgets, savings goals, emergency fund, history, charts, comparisons, annual reports, upcoming and recurring payments, projections; CHF by default; multiple currencies; personal and business kept separate | ✅ | Finance |
| 11 | Notes: 13 categories, rich text (headings, lists, checklists), tags, folders, search, pin, favourite, archive, auto-save, version history, links to businesses, projects and goals, quick notes from anywhere | ✅ | Notes; **Q** key; dashboard Quick notes |
| 12 | School: timetable, subjects, teachers, homework, assignments, exams, grades, study sessions, deadlines, revision schedules, objectives, courses, certificates, skills, study hours, progress; dashboard of upcoming exams and assignments | ✅ | School |
| 13 | Habits: categories, custom habits, daily completion, weekly and monthly overviews, streaks, completion %, reminders, history, charts | ✅ | Habits |
| 13 | Fitness (history, exercises, sessions, goals, notes, progress); reading, language, water and sleep trackers | ✅ | Fitness; Habits → tabs |
| 14 | Contacts CRM: all fields and categories, links to businesses and projects, follow-up reminders | ✅ | Contacts |
| 15 | Documents: 9 categories, upload, tags, description, dates, search, preview, download, delete, links to projects and businesses; no passwords stored in plain text | ✅ | Documents (stored in IndexedDB) |
| 16 | Shopping: lists, categories, quantities, prices, purchased status, priority, history, planned purchases, wishlist, purchase budget, link to personal budget | ✅ | Shopping |
| 17 | Travel: destinations, dates, budgets, transport, accommodation, packing list, documents, itinerary, activities, reservations, notes, expenses, upcoming trips | ✅ | Travel |
| 18 | Reminders: all 10 types, notification centre, browser notifications, custom times, snooze, mark as completed, history | ✅ ⚠️ | Notifications. They only work while the app is open in a tab, and this is explained on screen. |
| 19 | Global search across all required sections (and more), with categorised results; Quick Add for all 11 types | ✅ | **Ctrl K** or **/**; **Q** or the **+** button |
| 20 | Analytics: personal, business and financial; daily, weekly, monthly and yearly reports; charts, tables, comparisons; real data only | ✅ | Analytics |
| 21 | Weekly and monthly reviews with every listed question; automatic summary from real data | ✅ | Weekly Review, Monthly Review |
| 22 | Settings: themes, dashboard, currency, language (EN/DE/FR), date format, 12/24 h, week start, notifications, default priority, preferences, app information | ✅ | Settings |
| 23 | Local storage (localStorage + IndexedDB), auto-save, validation, error handling; JSON export and import with validation and confirmation; CSV for tasks and expenses; business reports; notes and journal export; document download; backup reminder; protection against injected code; warnings about data loss and no sync | ✅ ⚠️ | Backup & Restore. Data lives in one browser only, and this is explained on screen. |
| 24 | Sidebar with the 25 items in the 6 required groups, icons, collapsible groups, active state, mobile menu | ✅ | Sidebar |
| 25 | All 20 smart features (overdue detection, warnings, auto progress, countdowns, smart overview, daily and weekly suggestions, conversions, links, auto-categorisation, search, recent, favourites, archive, recently completed, custom categories and tags) | ✅ | Throughout; **Favorites & archive** (★ at the bottom of the sidebar) |
| 25 | No false claims about AI | ✅ | Suggestions are labelled "rule-based" |
| 26 | One `index.html`, vanilla JavaScript, no frameworks, build tools, Node.js or server; organised modules; graceful fallbacks | ✅ | Icons and charts are built in; Google Fonts is optional, with a system-font fallback |
| 27 | Quality-assurance checklist | ✅ | See "Automated verification" above |
| 28 | The working application plus a getting-started guide | ✅ | `index.html`, `README.md`, and Settings → Getting started |

## Limits set by the browser (stated honestly in the app)
- Reminders and browser pop-up notifications only fire while the app is open in a tab. Any that were missed appear in Notifications the next time you open it.
- Data stays in one browser on one device. Clearing browser data deletes it. Back up regularly using Backup & Restore.
- Exchange rates are entered by hand; the app doesn't fetch live rates.
- The journal PIN hides private entries on screen but doesn't encrypt them.
- German and French translations cover the menus, headings, tabs, buttons and dashboard titles. Text you type stays as you wrote it.
- Drag and drop works with a mouse. On touch screens, the same actions are available through buttons and menus.
