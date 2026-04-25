# DLC-EPM-Analysis
A Python pipeline for semi-automated behavioral analysis of Elevated Plus Maze (EPM) videos using DeepLabCut pose estimation output (GNU GPL-3.0 License).


Developed by Pernashee Dave in the Serrano Lab, Department of Psychology, Hunter College, CUNY. 
Principal Investigator, Dr. Peter Serrano


Overview

This pipeline takes filtered CSV output from a trained DeepLabCut model and extracts standard EPM behavioral metrics including zone occupancy, arm entries, and habituation effects. It was developed as part of a validation study comparing automated tracking to frame-by-frame manual behavioral coding in Sprague-Dawley rats.

Pipeline Overview
```
DLC filtered CSV output
        │
        ▼
Likelihood filtering (threshold = 0.60)
        │
        ▼
Frame-based zone calibration (pixel space)
        │
        ▼
Zone occupancy classification (body center keypoint)
        │
        ▼
Arm entry detection (boundary crossing + minimum duration threshold)
        │
        ▼
Discrete behavior detection (rule-based keypoint trajectory analysis)
        │
        ▼
Behavioral metrics output (CSV + figures)
