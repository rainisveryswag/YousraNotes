<div align="center">

# YousraNotes

**A clean, offline-first Android notes app built with MVVM architecture and Room persistence.**


*by [rainisveryswag](https://github.com/rainisveryswag) · Yousra*

</div>

---

## Overview

YousraNotes is a lightweight Android application for managing personal notes locally on-device. No accounts, no sync, no internet required — just fast, persistent note-taking backed by a SQLite database via Room.

Built as part of a **Mobile Programming: Android with Java** course, the project demonstrates clean separation of concerns using the MVVM pattern as recommended by Google's Android architecture guidelines.

---

## Features

| | Feature | Detail |
|---|---|---|
| ➕ | **Add notes** | Title + description, saved instantly to local DB |
| 🗑️ | **Delete a note** | Long-press any note card to remove it |
| 🧹 | **Clear all notes** | One-tap wipe of the entire notes list |
| 💾 | **Offline persistence** | Data survives app restarts via Room (SQLite) |
| 🔄 | **Reactive UI** | LiveData auto-updates the list — no manual refresh |
| 📱 | **Rotation-safe** | ViewModel preserves state across configuration changes |

---

## Architecture

Follows the **MVVM (Model-View-ViewModel)** pattern, ensuring a clean separation between UI, business logic, and data access.

```
┌─────────────────────────────────┐
│         MainActivity            │  ← View layer
│    (observes LiveData)          │
└────────────┬────────────────────┘
             │
             ▼
┌─────────────────────────────────┐
│         NoteViewModel           │  ← ViewModel layer
│  (survives configuration change)│
└────────────┬────────────────────┘
             │
             ▼
┌─────────────────────────────────┐
│        NoteRepository           │  ← Data access layer
│    (single source of truth)     │
└────────────┬────────────────────┘
             │
             ▼
┌───────────────────────────────────────────┐
│   NoteDao  ──►  NoteDatabase (Room/SQLite) │  ← Persistence layer
└───────────────────────────────────────────┘
```

---

## Project Structure

```
com.example.roommvvmdemo
│
├── data
│   ├── local
│   │   ├── Note.java           # @Entity — mapped to notes_table
│   │   ├── NoteDao.java        # @Dao — insert, delete, query
│   │   └── NoteDatabase.java   # @Database — Room singleton
│   └── NoteRepository.java     # Abstracts data access from ViewModel
│
├── ui
│   ├── MainActivity.java       # Main screen — observe + interact
│   └── NoteAdapter.java        # RecyclerView adapter with click/long-press
│
└── viewmodel
    └── NoteViewModel.java      # Bridges UI and repository
```

---

## Tech Stack

| Technology | Version | Purpose |
|---|---|---|
| **Room** | 2.6.1 | SQLite abstraction and local persistence |
| **LiveData** | AndroidX | Lifecycle-aware reactive data streams |
| **ViewModel** | AndroidX | UI state retention across rotation |
| **RecyclerView** | AndroidX | Efficient, scrollable notes list |
| **CardView** | AndroidX | Material card layout per note |
| **ExecutorService** | Java | Background threading for DB operations |

---

## Getting Started

**Prerequisites:** Android Studio Hedgehog or later, JDK 11+

```bash
# 1. Clone the repository
git clone https://github.com/rainisveryswag/YousraNotes.git

# 2. Open in Android Studio
#    File → Open → select the YousraNotes folder

# 3. Let Gradle sync, then run
#    Run → Run 'app'  (or press Shift+F10)
```

> **Min SDK:** 24 (Android 7.0 Nougat) · **Target SDK:** 36

---

## Test Coverage

| Scenario | Result |
|---|---|
| Insert a new note | ✅ Pass |
| Delete note by long-press | ✅ Pass |
| Delete all notes at once | ✅ Pass |
| Data persistence after app close | ✅ Pass |
| UI state after screen rotation | ✅ Pass |

---

## Author

**Yousra Azarri** · [@rainisveryswag](https://github.com/rainisveryswag) · [yousraazarri@gmail.com](mailto:yousraazarri@gmail.com)
