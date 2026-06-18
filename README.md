# AI Classroom Intelligence Glasses

**Supervisor:** Dr. Bourne Hu, Associate Professor, School of Information Science and Technology, Hangzhou Normal University

**Author:** Bawuah Nuru-deen | Incoming MSc Student, Electronic Information, HZNU 2026

**Project Type:** Summer Research Project (Pre-arrival assignment)

**Timeline:** June 20 - August 30, 2026

---

## Project Overview

This project develops an AI-powered prototype system capable of analyzing classroom activities and student engagement from pre-recorded classroom video footage. The system is built as a four-phase sequential pipeline where the output of each phase feeds directly into the next.

This is my first time working with face recognition, object tracking, and behavior analysis tools. I expect this project to be a significant learning experience before arriving at HZNU, and I will be documenting my progress, difficulties, and solutions honestly through weekly reports.

The system is designed to:

- Detect all students present in each frame of a classroom video
- Track students consistently across frames using unique IDs
- Recognize student identities using a custom face dataset
- Analyze student behavior and classify it into five categories: Attentive, Looking away, Sleepy, Using phone, or Distracted
- Generate per-student engagement scores and a class summary report
- Display all results through a simple teacher-facing dashboard

### Example Output

```
Student_A
Attendance: Present
Status: Attentive
Participation Score: 85%

Student_C
Attendance: Present
Status: Distracted
Phone Usage: 3 minutes

Class Summary:
Total Students: 30
Average Engagement: 78%
Most Attentive Students: [Student_A, Student_F, Student_J]
Most Distracted Students: [Student_C, Student_M, Student_B]
```

---

## System Architecture

The system is a sequential four-stage pipeline:

```
Video Input (.mp4)
    |
    v
Phase 1: Student Detection and Tracking
(YOLOv8 detects persons, ByteTrack assigns consistent IDs)
    |
    v
Phase 2: Student Identity Recognition
(InsightFace matches each tracked face to a student name)
    |
    v
Phase 3: Behavior Analysis
(MediaPipe head pose + eye tracking + YOLOv8 phone detection)
    |
    v
Phase 4: Teacher Dashboard
(Streamlit displays attendance, behavior, and engagement report)
```

---

## Project Structure

```
ai-classroom-intelligence-glasses/
|
|-- phase1_detection/
|   |-- detect_students.py        # Student detection and tracking script
|
|-- phase2_recognition/
|   |-- build_database.py         # Builds face embedding database from dataset
|   |-- recognize_students.py     # Identifies students by name in real time
|
|-- phase3_behavior/
|   |-- behavior_analyzer.py      # Classifies student behavior per frame
|
|-- phase4_dashboard/
|   |-- dashboard.py              # Streamlit teacher dashboard
|   |-- save_results.py           # Aggregates results to CSV
|
|-- dataset/                      # Student face photos (not pushed to GitHub)
|-- weekly_reports/               # Weekly progress reports (Markdown)
|-- requirements.txt              # All Python dependencies
|-- README.md                     # This file
|-- .gitignore
```

---

## Development Phases and Timeline

| Phase | Description | Timeline | Status |
|-------|-------------|----------|--------|
| Phase 1 | Student Detection and Tracking | Weeks 1-2 (Jun 20 - Jul 3) | In progress |
| Phase 2 | Student Identity Recognition | Weeks 3-4 (Jul 4 - Jul 17) | Not started |
| Phase 3 | Behavior Analysis | Weeks 5-8 (Jul 18 - Aug 14) | Not started |
| Phase 4 | Teacher Dashboard and Reporting | Weeks 9-10 (Aug 15 - Aug 28) | Not started |
| Final | Technical report, demo video, submission | Week 11 (Aug 29 - Aug 30) | Not started |

---

## Installation

> This section will be updated as each phase is completed. Full installation instructions will be available by end of Week 2.

### Prerequisites

- Python 3.10 or higher
- pip
- Git
- A classroom video file for testing (.mp4 format)

### Setup

```bash
# Clone the repository
git clone https://github.com/bawuah-nuru-deen/ai-classroom-intelligence-glasses.git

# Navigate into the project folder
cd ai-classroom-intelligence-glasses

# Install required packages
pip install -r requirements.txt
```

> Note: `requirements.txt` will be populated as each phase is built and tested.

---

## Usage

> This section will be updated phase by phase as the system is built. Complete usage instructions will be available by end of Week 9.

### Phase 1: Run Student Detection (available from Week 2)

```bash
python phase1_detection/detect_students.py --video path/to/classroom.mp4
```

### Phase 2: Build Face Database and Run Recognition (available from Week 4)

```bash
python phase2_recognition/build_database.py --dataset path/to/dataset/
python phase2_recognition/recognize_students.py --video path/to/classroom.mp4
```

### Phase 3: Run Behavior Analysis (available from Week 8)

```bash
python phase3_behavior/behavior_analyzer.py --video path/to/classroom.mp4
```

### Phase 4: Launch Teacher Dashboard (available from Week 9)

```bash
streamlit run phase4_dashboard/dashboard.py
```

---

## Weekly Progress Reports

Progress reports are submitted every week documenting what was learned, problems encountered, current progress, and the plan for the following week. Reports are stored in the `weekly_reports/` folder.

| Week | Report | Date |
|------|--------|------|
| Week 1 | Coming soon | Jun 20 - Jun 26 |
| Week 2 | Coming soon | Jun 27 - Jul 3 |
| Week 3 | Coming soon | Jul 4 - Jul 10 |
| Week 4 | Coming soon | Jul 11 - Jul 17 |
| Week 5 | Coming soon | Jul 18 - Jul 24 |
| Week 6 | Coming soon | Jul 25 - Jul 31 |
| Week 7 | Coming soon | Aug 1 - Aug 7 |
| Week 8 | Coming soon | Aug 8 - Aug 14 |
| Week 9 | Coming soon | Aug 15 - Aug 21 |
| Week 10 | Coming soon | Aug 22 - Aug 28 |
| Week 11 | Coming soon | Aug 29 - Aug 30 |

---

## Technologies and Tools

| Phase | Tools |
|-------|-------|
| Detection and Tracking | Python, OpenCV, YOLOv8 / YOLOv11, ByteTrack |
| Face Recognition | InsightFace, ONNX Runtime, Python |
| Behavior Analysis | MediaPipe, YOLOv8, Python |
| Dashboard | Streamlit, Pandas, Plotly, Python |

---

## Deliverables

- GitHub Repository (this repo — maintained throughout development)
- Technical Report (5-10 pages, English) — due August 30, 2026
- Demonstration Video (5-10 minutes, English) — due August 30, 2026
- Weekly Progress Reports (11 reports total)

---

## Acknowledgements

This project is assigned and supervised by Dr. Bourne Hu, Associate Professor, School of Information Science and Technology, Hangzhou Normal University, as a pre-arrival summer research project for the MSc Electronic Information programme.
