# My Life OS

A private personal operating system that lives in a single file: **`index.html`**.
You can use it for tasks, planning your day, the calendar, a journal, long-term goals, businesses, business ideas, projects, finances, notes, documents, school, habits, fitness, shopping, travel, contacts, reminders, analytics and reviews.

It doesn't need a server, an account or a build step. Everything you enter stays in your browser.

## Getting started

1. Download `index.html` and save it somewhere permanent, for example `Documents/MyLifeOS/index.html`.
2. Double-click it to open it in Chrome, Edge, Firefox or Safari.
3. Enter your name, currency (CHF by default) and theme.
4. Open the built-in guide from the **?** button at the bottom of the sidebar, or go to **Settings → About → Getting started guide**.

### Suggested setup order
1. **Settings**: date format, 12/24-hour clock, first day of the week, theme.
2. **My Future**: write your life vision and your 1/3/5/10-year horizons. Then use **Plan an ambition** to turn a big ambition into a goal, its milestones, a project and the first tasks.
3. **Business Hub**: create one workspace per business. Record investments, revenue and expenses in its **Finances** tab. These records are kept separate from your personal money and from your other businesses.
4. **Finance**: add recurring payments (rent, insurance, subscriptions) and monthly budgets.
5. **Habits**, **School**, **Contacts**: add your habits, your subjects and timetable, and the people who matter to you (with birthdays).

### Daily use
- Each morning, check the **Dashboard**, then open **My Day** to pick your priorities, tick off your morning routine and add time blocks.
- Press **Q** (or click the **+** button) to quick-add a task, event, note, journal entry, idea, business, project, goal, contact, expense or reminder.
- Press **Ctrl/Cmd + K** or **/** to search everything.
- Each evening, write in **My Journal**. Each week and month, do the **Weekly Review** and **Monthly Review**. Their summaries are built only from data you entered.

## Your data: please read
- Data is stored **only in this browser**: IndexedDB holds your records and uploaded files, and localStorage holds your settings.
- It can be **lost** if you clear browsing data, use private/incognito mode, or the browser frees up storage.
- It is **not synced** between devices or browsers. To move to another computer, export a JSON backup and import it there.
- Go to **Backup & Restore** to export a full JSON backup (it can include your documents) and to import one. Before anything is overwritten, the import checks the file and asks whether to merge or replace. The same page has CSV exports for tasks, expenses, business transactions and reports, and contacts, plus Markdown/text exports for notes and the journal.
- Under **Settings → About** you can ask the browser for *persistent storage*, which reduces the chance of the browser clearing your data.
- Don't store passwords or banking credentials in notes or documents. The journal PIN only hides private entries on screen. It's stored as a SHA-256 hash and does **not** encrypt your entries.

## Reminders and notifications
Reminders are checked every 30 seconds **while the app is open in a browser tab**. Browser pop-up notifications also need that tab to be open. Without a server, alerts can't be delivered while the browser is closed. Any you missed show up in **Notifications** the next time you open the app.

## Honest notes
- Suggestions, transaction categorisation and review summaries come from simple rules applied to your own data. The app doesn't use any AI service.
- Exchange rates are entered by hand (**Settings → Currency**). Amounts in a currency that has no rate are left out of totals, and the app tells you when that happens.
- Charts and icons are drawn by the file itself, so the app also works offline. The Inter font loads from Google Fonts when you're online; offline, your system font is used instead.

## Technical overview
- One `index.html` written in HTML5, CSS3 and vanilla JavaScript. It doesn't use frameworks, build tools or Node.js.
- The code is split into sections inside the file:
  - core utilities, dates, icons and an HTML sanitiser
  - storage (an IndexedDB wrapper with a localStorage fallback, plus settings)
  - schemas, which define the fields of every record type
  - UI kit: modal, form builder, rich-text editor and SVG charts
  - domain logic: tasks and recurrence, calendar, goals, finance, business, reminders
  - app shell: router, sidebar, search, quick add
  - one view object per section, and the boot code
- Text you type is escaped before it's displayed. Rich text goes through a whitelist sanitiser.
