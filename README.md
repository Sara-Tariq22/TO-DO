# TO-DO

# Project Title
**T-TRACK: Personal Task Management Web App**

# Research Problem
People often lose track of pending tasks because they rely on memory or scattered notes, with no central place to log, update, or mark items as done. Existing task apps are either feature-heavy or require account creation, creating a need for a simple, zero-login, browser-based tracker.

# Motivation
This project provides a lightweight, privacy-focused tool for everyday task management. By letting users manually add, edit, and complete tasks through a clean interface — with no account, no syncing, and no data sharing — the app ensures anyone can stay organized instantly, helping to prevent missed responsibilities and mental overload.

# Control Flow
- **Launch:** App opens to the Dashboard. User sees their current task list (empty on first use) and an input field at the top.
- **Add Task:** User types a task title and clicks "Add". The app validates the input and instantly appends the new task to the list below.
- **View Tasks:** Dashboard displays all tasks ordered newest-first. Completed tasks appear faded with strikethrough; pending tasks appear with a purple left border.
- **Update Task:** User clicks ✏️ on any task, navigating to the Update Screen. They can edit the title and/or tick "Mark as Completed", then save to return to the Dashboard with changes applied.
- **Delete Task:** User clicks 🗑️, navigating to a confirmation screen showing the task name. Confirming permanently removes it; cancelling returns to the Dashboard unchanged.

# Implementation Strategy
- **Tech Stack:** Built using Python and the Django framework, with SQLite as the database and plain HTML/CSS for the frontend.
- **File Structure:** Code is divided into modular files (`models.py`, `views.py`, `forms.py`, `urls.py`, templates) to keep logic, data, and presentation cleanly separated.
- **Data Model:** Uses a single `Task` class with three fields — `title`, `completed`, and `created` — to store everything the app needs.
- **Architecture:** Follows Django's MVT (Model-View-Template) pattern. Views handle request logic, templates handle display, and the model handles data — each layer independent.
- **Data Flow:** Uses Django's ModelForm (`TaskForm`) to pass data between the user and the database. Form validation, saving, and updating all flow through the form, keeping views thin and logic centralized.
