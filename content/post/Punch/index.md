+++
author = "Olivier Boisvert"
title = "Punch"
date = "2026-02-01"
description = "Punch design "
tags = [
    "Bench test",

]
categories = [
    "Mechatronic",
   
]
series = ["Themes Guide"]
aliases = ["migrate-from-jekyl"]
image = "/img/punch_1111.jpg"
+++



# Febuary 01, 2026

Paper timesheets, hours copied by hand, payroll rebuilt every two weeks. I built a
touchscreen time clock that makes all of that disappear: the employee picks a task,
taps their RFID tag, and their hours are logged and sorted automatically.

{{< image src="/img/02_accueil.png" caption="Home screen">}}

## Clock in with three taps

Touch the screen, choose the task you're starting (roads, snow removal, garbage,
water plant), and present your tag. A confirmation shows your name, the task and
the time. Lunch breaks work the same way, with the length of the break.

{{< image src="/img/04_menu_principal.png" caption="Task menu">}}
{{< image src="/img/06_pointage_scan.png" caption="Waiting for the tag">}}
{{< image src="/img/08_pointage_confirme.png" caption="Punch recorded">}}

Employees can also check their last punches with their own tag, which ends the
"did I really clock in this morning?" questions.

{{< image src="/img/11_historique_affiche.png" caption="Personal history">}}

## Works even without internet

If the WiFi drops, the clock keeps working. Punches are stored on the device and
sent to the server automatically when the connection comes back. Status lights on
the home screen show the network, sync and clock state at a glance.

{{< image src="/img/03_accueil_hors_ligne.png" caption="Offline mode, 3 punches waiting to sync">}}

## Managed right on the device

A password-protected menu lets a supervisor add an employee by scanning a new tag,
rename or remove employees, edit the task buttons and change WiFi networks, with no
computer and no reprogramming.

{{< image src="/img/17_liste_employes.png" caption="Employee management">}}

## From punch to payroll

Every punch gets a unique ID and lands in an online database with the employee,
task and timestamp. A web admin portal sorts it all by employee, date and task,
calculates hours worked and cost per task, and keeps track of each employee's
sick hours and banked time, turning payroll into a quick review instead of a
data-entry job.

## Under the hood

- ESP32 microcontroller
- 480 × 320 touchscreen
- RFID reader for employee tags
- Offline queue with automatic sync
- Online database and web admin portal
- Custom 3D-printed enclosure

{{< video label="Punch demo" mp4="/img/Punch_mov_2.mov" >}}

{{< image src="/img/punchce_0.jpg" caption="Electronics">}}


# February 15, 2026

The punch clock catches every tap, but someone still had to look at all of it. I
built a web admin portal that opens the database, groups the punches by employee
and week, and lets the supervisor approve or fix them without leaving the browser.
Employees can log in too and see their own week — no more phone calls to ask if
their hours are in.

## Reports that write themselves

Pick a date range and the portal counts every punch: number of sessions, total
hours worked, lunch minutes. The full list follows below with date, employee,
task, in, out, lunch, duration (both in hours-minutes and decimal for payroll).
One click exports the whole thing to Excel, grouped by employee, ready to hand
off to the comptroller.

{{< image src="/img/voirie_rapports.png" caption="Reports tab with totals and per-session detail">}}

## Tasks live in the database, not the code

The four work tasks — Voirie, Snow removal, Garbage, Water plant — and the special
"Dinner" tag are managed from their own tab. Add a new task, rename one, toggle
one active or not, and the touch clock picks up the change the next time it syncs.
No firmware update, no code push.

{{< image src="/img/voirie_taches.png" caption="Task management">}}

## Every employee, their own hour budget

Each employee has a card with their RFID UID, category (full-time, part-time
minimum, contract), weekly max hours, sick hours remaining and hour bank balance.
Editing is inline — click, change, save.

{{< image src="/img/voirie_employes.png" caption="Employee management">}}

## Hour bank that follows the rule

Anything over 40 hours gets multiplied by 1.5 and dropped into the employee's bank.
Anything short pulls from that same bank, with a confirmation before it does. The
math runs in Postgres, uses the exact seconds worked (no rounding fudging the
number the DG signed off on) and refuses to run until every session in the week is
approved.

## Notes on the line, not on a Post-it

Employees have their own view of the week. Next to each punch there's a small 💬
button — one click adds a note ("I forgot to punch out at 4pm"). The note shows up
in orange on the supervisor's screen the moment they open the dashboard, and stays
attached to the session even after approval. No more sticky notes on the office
door.

## Roles that make sense

Administrators run everything. Observers (the treasurer, the DG) only see the
reports — read-only, no approvals, no edits. Both are created from the same
Administration tab with a single email and a couple of checkboxes.

## Under the hood

- Supabase (Postgres + Auth + Realtime)
- Vanilla HTML/CSS/JS front-end, PWA-installable on iPhone and Android
- Vercel deployment with GitHub auto-deploy
- Row Level Security per employee
- SMTP2GO for password reset & welcome emails
- Excel exports through SheetJS



# March 05, 2026

The fire department was still filling out paper time sheets after every call and
practice, then re-typing everything into an Excel workbook with dozens of VBA
macros. I rebuilt the workbook as a web app the firefighters use directly from
their phones, and the whole payroll now generates itself.

## One sheet, several rules

Every activity has its own pay rule: interventions pay a minimum of 3 hours even
if the call was shorter, first-responder shifts pay a $50 flat rate, heavy
mechanics work bills at a fixed $35/h. The firefighter picks the activity, enters
start, end, and dinner minutes; the app computes the total on the spot and stores
the raw times for later payroll math.

{{< image src="/img/pompier_saisie.png" caption="Time sheet entry — activity, hours, dinner">}}

## Fill it in once, for the whole crew

When five firefighters answer the same call, the person filling the sheet ticks
"Sélection multiple de pompiers", picks the crew, and one identical sheet gets
created for every name — same date, same activity, same hours. Vehicles used,
addresses, aid received or billed, all captured in the same form.

## Approvals before payroll

The captain reviews every sheet before it hits payroll. The approval screen lists
what's pending with the firefighter's number, the activity, the GL code, start,
end, lunch, hours and any comment they left. Filters by date, firefighter or GL
code narrow the list; one button approves the whole filter at once. Approved
sheets are locked and can no longer be edited by the firefighter.

{{< image src="/img/pompier_approbations.png" caption="Approval screen with filters and bulk approve">}}

## Kilometers when they use their own car

If a firefighter drove their own vehicle to the station or the scene, they log the
distance separately on the Kilométrage tab. The kilometer report exports per
firefighter with totals and sits next to the payroll.

## Payroll in two clicks

Pick a firefighter and a date range, and the app spits out an Excel file with
totals by GL code, applying the 3-hour minimum, the flat rates and the 4%
vacation top-up. There is also a global export — one workbook, one sheet per
firefighter — for the entire pay period.

## Billing aid to other towns

An intervention where a neighboring town helped, or an intervention where we
went to help them, is flagged on the sheet with the towns involved. The
"Report by activity" filter groups every intervention of a given type over a
range, lists the towns to bill, and exports the whole thing to Excel for the
comptroller.

## Two apps, one login

The web app runs both modules from the same URL. A firefighter who is also a
municipal admin picks their side at login. Auth accounts are shared, but each
module has its own tabs, its own permissions and its own visual identity — red
for the fire service, navy for city hall.

## Under the hood

- Same stack as the Voirie module (Supabase + Vercel + Vanilla JS)
- PostgreSQL functions for payroll math (3h min, flat rates, 4% vacation)
- Automatic Auth account creation when a firefighter is added
- Excel exports through SheetJS
- Real-time updates when a sheet is approved
- Installable as a PWA on personal phones