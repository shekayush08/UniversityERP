# University ERP System – CSE4019 Advanced Java Programming
### VIT Bhopal University

---

## Project Structure

```
UniversityERP/
└── src/
    └── erp/
        ├── Main.java                          ← Entry point
        ├── beans/
        │   └── StudentBean.java               ← JavaBean with PropertyChangeSupport
        ├── exceptions/
        │   ├── ERPException.java              ← Custom base exception
        │   ├── DuplicateEntryException.java   ← Duplicate ID handling
        │   └── StudentNotFoundException.java  ← Student not found
        ├── model/
        │   ├── Person.java                    ← Abstract base class
        │   ├── Student.java                   ← Extends Person
        │   ├── Faculty.java                   ← Extends Person
        │   ├── Course.java                    ← Course entity
        │   ├── Attendance.java                ← Attendance record
        │   ├── Grade.java                     ← Grade with letter + GPA points
        │   └── Reportable.java                ← Interface
        ├── util/
        │   ├── DataStore.java                 ← Singleton in-memory store + Serialization
        │   ├── AutoSaveThread.java            ← Background thread (daemon)
        │   └── ReportGenerator.java           ← Implements Reportable
        └── view/
            └── ERPMainFrame.java              ← Full Swing GUI (MVC pattern)
```

---

## Syllabus Coverage (CSE4019)

| Unit | Concepts Used |
|------|--------------|
| **Unit 1** | Classes, Objects, Interfaces, Inheritance (Person→Student/Faculty), Access Modifiers, Packages, Exception Handling (try/catch/throws), Custom Exceptions, Multithreading (AutoSaveThread, Thread Life Cycle, Daemon thread), Object Serialization |
| **Unit 2** | JavaBeans (StudentBean with PropertyChangeSupport, bound properties), GUI using Swing |
| **Unit 4** | Swing + MVC Pattern, BorderLayout, GridLayout, GridBagLayout, FlowLayout, BoxLayout, JSplitPane, JTabbedPane, JMenuBar with Mnemonics & Accelerators, JToolBar with Tooltips, JTable, JComboBox, JCheckBox, JRadioButton, ButtonGroup, JSpinner, JProgressBar, JScrollPane, JOptionPane dialogs, TitledBorder, MatteBorder, EmptyBorder, Custom Colors/Fonts |

> **No JDBC/Database used** – all data stored in-memory with Java Object Serialization (erp_data.ser)

---

## How to Compile & Run

### Requirements
- **Java JDK 11 or higher** (JDK 17/21 recommended)
- Download from: https://www.oracle.com/java/technologies/downloads/

### Windows
```bat
compile.bat
run.bat
```

### Linux / macOS
```bash
chmod +x compile.sh run.sh
./compile.sh
./run.sh
```

### Manual (any OS)
```bash
# From inside the UniversityERP/ folder:
mkdir -p out
javac -d out -sourcepath src $(find src -name "*.java")   # Linux/Mac
# OR on Windows PowerShell:
# javac -d out -sourcepath src (Get-ChildItem -Recurse -Filter *.java src | % { $_.FullName })

java -cp out erp.Main
```

---

## Features

- **Student Management** – Add, Update, Delete, Search students; form auto-populates on table row click; double-click for full detail dialog
- **Course Management** – Add/Delete courses, link to faculty
- **Faculty Management** – Full faculty directory
- **Grades** – Record marks per student per course; auto-calculates letter grade (O/A+/A/B+/B/C/F) and CGPA
- **Attendance** – Mark present/absent per session (Lecture/Lab/Tutorial); live progress bars show attendance %
- **Reports** – All-students table report, per-student detail report, course summary — all via `Reportable` interface
- **AutoSave** – Background daemon thread saves data every 60 seconds to `erp_data.ser`
- **Persistence** – Data survives across runs via Java Object Serialization
- **Demo Data** – 5 students, 4 courses, 3 faculty pre-loaded on first run

- Contributors
  
•	23BCE11349 – PARITOSH KATIYAR
  
•	23BCE11756 – KARTIKEY VERMA

•	24BCE11369 – AAYUSH SHEKHAWAT

•	24BCE10699 – ATHARVA KATARE

•	23BCE11768 – NIKHIL PILLAI

