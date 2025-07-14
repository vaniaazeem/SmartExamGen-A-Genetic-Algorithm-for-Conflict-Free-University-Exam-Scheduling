# 🧬 University Exam Scheduling using Genetic Algorithm

This project implements a **Genetic Algorithm (GA)** from scratch in Python (using only `pandas` and `numpy`) to generate optimized and conflict-free university exam schedules. The algorithm evolves candidate solutions (schedules) over generations to meet strict exam-related constraints while also maximizing overall efficiency and convenience.

---

## 🧠 Project Objective

The core objective of this project is to create a generic and automated scheduling system that:
- **Ensures all exams are scheduled properly.**
- **Avoids conflicts between students, teachers, and classroom availability.**
- **Adheres to time, day, and invigilation policies.**
- **Optimizes soft preferences to improve comfort and manageability.**

This solution leverages the power of **evolutionary computing** by using a **Genetic Algorithm**, an intelligent search technique inspired by the process of natural selection.

---

## ⚙️ Features & Highlights

- Developed **entirely from scratch** — no use of external GA libraries
- **Roulette Wheel Selection** mechanism to choose fitter individuals for crossover
- Supports any **crossover strategy** (e.g., one-point, two-point, uniform) with justification
- Mutation operation with a **tunable and explainable rate**
- Detailed **fitness evaluation system** based on real-world academic scheduling needs
- Displays:
  - Fittest schedules per generation (top 2–3)
  - Fitness values over iterations
  - Final solution with hard and soft constraints listed

---

## 📊 Fitness Function Breakdown

The **fitness function** determines how "good" a schedule is. It evaluates both **hard (essential)** and **soft (optimization)** constraints.

### ✅ Hard Constraints (Must be satisfied)
These are strict rules that, if violated, result in a penalty or invalid solution:
- Each course must have exactly one scheduled exam.
- No student should have overlapping exams (each is enrolled in ≥3 courses).
- Exams only scheduled on weekdays (Monday–Friday), between **9 AM – 5 PM**.
- Every exam must be assigned exactly one invigilating teacher.
- No teacher should invigilate multiple exams simultaneously.
- Teachers should not be assigned **consecutive** exam duties.

### 🌟 Soft Constraints (Improve fitness if fulfilled)
These are preferences that enhance schedule quality:
- A **common break** on Friday from **1–2 PM** for all.
- Students should not have **back-to-back exams**.
- If a student takes both Management (MG) and CS courses, MG exams should come first.
- A two-hour **faculty meeting slot**, ensuring half of faculty is free in one and the rest in another.

The fitness score rewards schedules that fulfill more soft constraints, and penalizes violations of hard constraints.

---

## 📥 Input Data Format

The algorithm takes structured input from CSV/Excel files:
- **Courses** with codes and durations
- **Students** and their enrolled courses
- **Teachers** and their assigned subjects
- **Classrooms** available for exams (e.g., C301–C310)

---

## 📤 Output Schedule

The final schedule includes:
- **Course Code**
- **Exam Day and Start Time**
- **Classroom Assignment**
- **Invigilating Teacher**

It ensures all constraints are met and highlights which optimization criteria were successfully applied.

---

## 🧪 Genetic Algorithm Design

- **Representation**: Each individual (chromosome) represents a full exam schedule.
- **Population**: A set of candidate schedules.
- **Selection**: Roulette Wheel Selection for choosing parents.
- **Crossover**: Swaps parts of parent schedules to produce offspring.
- **Mutation**: Random modifications to maintain genetic diversity.
- **Evaluation**: Each individual is scored using the custom fitness function.

---

## 🖥️ Technology Stack

- Python 3.x
- pandas
- numpy
- Jupyter Notebook (`.ipynb` format)

---

## 📁 Project Files

- `Exam_Scheduler.ipynb`: Full code with step-by-step documentation
- `data/`: Folder containing all input files (teachers, students, classrooms, etc.)
- `output/`: Generated exam schedules
- `Report.pdf`: Detailed explanation of the algorithm design, logic, and results

---

## ✅ Key Output Requirements

- Show **top 2–3 fittest individuals** per generation
- Display **fitness values per generation**
- Final output must:
  - Satisfy **all hard constraints**
  - Satisfy **at least three** soft constraints
  - List constraints satisfied


