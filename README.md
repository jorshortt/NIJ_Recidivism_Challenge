# NIJ Recidivism Challenge

A five-assignment data science teaching project built around the National Institute of Justice's Recidivism Challenge dataset. Students take on the role of analysts hired by the NIJ and work through the full data science process: understanding the problem, cleaning and exploring the data, building machine learning models, explaining those models to a non-technical audience, and presenting a recommendation.

The repository contains student starter files, instructor example solutions, grading rubrics, and peer evaluation forms, so an instructor can run the project in a course with little additional preparation.

## The question

Prisons are meant to rehabilitate people and deter crime. If they succeed, recidivism (returning to crime and prison after release) should be low. The NIJ wants to know whether recidivism is a problem in Georgia, and which factors help predict whether a person on parole will be re-arrested.

## The data

The project uses the [NIJ's Recidivism Challenge Full Dataset](https://catalog.data.gov/dataset/nijs-recidivism-challenge-full-dataset), published on Data.gov.

- About 26,000 people released from Georgia prisons on discretionary parole to the Georgia Department of Community Supervision
- Releases between January 1, 2013 and December 31, 2015
- Variables cover demographics, criminal history, supervision conditions, parole violations, and whether the person was arrested for a new crime within three years
- Variable definitions are in the codebook in Appendix 2 of the [NIJ challenge page](https://nij.ojp.gov/funding/recidivism-forecasting-challenge)

> **Getting the data:** the CSV files in [`Data/`](Data/) are empty placeholders. Download the full dataset from Data.gov and save it in the same folder as the notebooks you are running. The notebooks expect the file to be named `NIJ_s_Recidivism_Challenge_Full_Dataset.csv` (the name it downloads with). Assignment 2 writes `cleaned_NIJ_Recidivism_Challenge.csv`, which Assignment 3 then reads.

## Project structure

The project follows five stages of the data science process. Assignments 1 and 4 are individual; 2, 3, and 5 are done in teams of 3–4.

| # | Stage | Format | What students do |
|---|-------|--------|------------------|
| 1 | **Understand** | Individual, Jupyter notebook | Research the data source and key vocabulary, define the NIJ's question, explore the dataset with pandas, and make a first visualization of recidivism |
| 2 | **The Data** | Team, Jupyter notebook | Find and fix "dirty" data (types, missing values, columns that would leak the answer or introduce bias), then run an exploratory analysis with Matplotlib and Seaborn |
| 3 | **Model** | Team, Jupyter notebook | Build three machine learning models of their choice with scikit-learn, and produce and interpret a confusion matrix for each |
| 4 | **Understand** | Individual, written paper (MLA/APA) | Explain the team's three models and their confusion matrices in plain language for NIJ staff, compare them, and recommend one |
| 5 | **Communicate** | Team, 10–12 minute presentation | Present the whole project to the class as if to the NIJ, using the "Answer First" format; every team member speaks |

Before the Assignment 5 presentations, each student completes a peer evaluation and a statement of contribution for every teammate. These are meant to be considered when grading the team assignments.

## Repository contents

```
├── Data/                      Placeholder CSVs (download the real data; see above)
├── Student_Materials/         Starter files handed to students
│   ├── Assignment1_Student.ipynb
│   ├── Assignment2_Student.ipynb
│   ├── Assignment3_Student.ipynb
│   ├── Assignment4_Student.docx
│   └── Assignment5_Student.docx;
├── Instructor_Materials/      Example solutions and instructor guidance
│   ├── Project_Overview.pdf          Summary of all five assignments and their objectives
│   ├── NoteToInstuctors.pdf          Grading philosophy
│   ├── Assignment1_Instuctor.ipynb
│   ├── Assignment2_Instructor.ipynb
│   ├── Assignment3_Instructor.ipynb
│   ├── Assignment4_Instructor.docx   Paper outline with section-by-section guidance
│   └── Assignment5_InstructorTemplate.pptx   Slide-by-slide presentation template
├── Rubrics/                   One 100-point rubric per assignment (PDF)
└── Peer_Evaluation_Docs/      Peer evaluation form and statement of contribution (Word)
```

## Running the notebooks

The notebooks need Python 3 with:

- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn (Assignment 3)

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook
```

Run the assignments in order: Assignment 2 produces the cleaned file that Assignment 3 depends on.

## Instructor example results

The instructor copy of Assignment 3 builds logistic regression, k-nearest neighbors, and random forest models. On its test split they score:

| Model | Accuracy | Precision | Recall | Specificity | F1 |
|-------|---------:|----------:|-------:|------------:|---:|
| Logistic regression | 71.5% | 72.8% | 79.9% | 60.2% | 76.2% |
| k-nearest neighbors | 62.5% | 65.4% | 72.8% | 48.6% | 68.9% |
| Random forest | 72.8% | 73.1% | 82.8% | 59.4% | 77.6% |

These are one possible answer, not a target. Student models are graded on how well the team understands and interprets them, not on how well they score.

## A note on grading

There is no single right answer to most questions in this project. The instructor copies show one reasonable approach among many. Grade students on how well they apply course concepts, explain their findings, and think critically about open-ended problems, rather than on how closely their work resembles the instructor copies. Each rubric scores content and approach on a 1–5 scale.

## Credits

Developed by the DART Program. Data provided by the National Institute of Justice and the Georgia Department of Community Supervision via Data.gov. The peer evaluation form is adapted from one developed at Carnegie Mellon University.

### References

Department of Justice. (2024, May 23). *NIJ's Recidivism Challenge Full Dataset*. Georgia; Data.gov.

MacKenzie, D. L. (2001). Corrections and sentencing in the 21st century: Evidence-based corrections and sentencing. *The Prison Journal, 81*(3), 299–312. https://doi.org/10.1177/0032885501081003001
