+++
author = "Olivier Boisvert"
title = "Punch"
date = "2026-02-01"
description = "Some bench tests that I made"
tags = [
    "Bench test",

]
categories = [
    "Mechatronic",
   
]
series = ["Themes Guide"]
aliases = ["migrate-from-jekyl"]
image = "/img/pun_01.jpg"
+++





# Febuary 01, 2026

Technical Description – RFID Time and Attendance System for Task and Time Management

This project consists of an automated time and attendance system designed to record employee activities and facilitate tracking of working time per task.

The hardware is based on an ESP32 microcontroller with an integrated touchscreen and RFID reader. The ESP32 manages the user interface, screen animations, and RFID card reading. The user first selects the task to be performed via the touchscreen, then presents their RFID card to the reader for identification.

Upon reading the card, the system generates an entry containing the employee's information, the selected task, and the corresponding timestamp. Each entry is associated with a unique identifier to ensure data traceability. The information is then transmitted via the internet and automatically saved to a Google Sheets spreadsheet.

The spreadsheet is configured with scripts that sort and organize data according to various criteria, including employee, date, and tasks performed. This structure allows for the calculation of hours worked, the management of hours per task, and simplified payroll preparation.

The system is also connected to a database containing employee information, including their employee number, available sick hours, banked hours, and other time management parameters.

This solution thus centralizes the recording of employee activities and automates a large portion of the administrative tasks related to managing working hours.


{{< video label="this is a label" mp4="/img/punchm_0.mov" >}}

{{< image src="/img/punchce_0.jpg" caption="electronic">}}