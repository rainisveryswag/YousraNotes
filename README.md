# 📝 Yousra's Notes App

A personal Android notes manager built with **MVVM + Room**, by **rainisveryswag** (Yousra Azarri).

---

## ✨ Features

- ➕ Add a note with a title and description
- 🗑️ Long-press any note to delete it
- 🧹 Wipe all notes in one tap
- 💾 Fully offline — data persists via Room (SQLite)
- 🔄 Live list updates via LiveData — no manual refresh needed
- 📱 Survives screen rotation thanks to ViewModel

---

## 🏗️ Architecture

Follows the **MVVM** pattern recommended by Google for modern Android.

```
MainActivity (View)
     │
     ▼
NoteViewModel
     │
     ▼
NoteRepository
     │
     ▼
NoteDao ──► NoteDatabase (Room / SQLite)
```

---

## 📁 Project Structure

```
com.example.roommvvmdemo
│
├── data
│   ├── local
│   │   ├── Note.java          # Room Entity
│   │   ├── NoteDao.java       # DAO interface
│   │   └── NoteDatabase.java  # Room Singleton
│   └── NoteRepository.java    # Data access layer
│
├── ui
│   ├── MainActivity.java      # Main view
│   └── NoteAdapter.java       # RecyclerView adapter
│
└── viewmodel
    └── NoteViewModel.java     # ViewModel
```

---

## 🛠️ Tech Stack

| Technology | Role |
|---|---|
| Room 2.6.1 | Local SQLite persistence |
| LiveData | Reactive data observation |
| ViewModel | UI state survival across rotation |
| RecyclerView | Efficient list rendering |
| CardView | Clean per-note card UI |
| ExecutorService | Off-main-thread DB operations |

---

## 🚀 Getting Started

1. Clone the repo:
```bash
git clone https://github.com/rainisveryswag/RoomMVVMDemo.git
```

2. Open in **Android Studio**

3. Sync Gradle and hit **Run ▶️** on an emulator or physical device

> Min SDK: 24 — Target SDK: 36

---

## 🧪 Test Results

| Test | Status |
|---|---|
| Insert a note | ✅ |
| Delete by long-press | ✅ |
| Delete all notes | ✅ |
| Persistence after app close | ✅ |
| Screen rotation survival | ✅ |

---

## 👩‍💻 Author

**rainisveryswag** · Yousra Azarri · [yousraazarri@gmail.com](mailto:yousraazarri@gmail.com)
