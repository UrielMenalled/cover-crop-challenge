# Cover Crop Challenge

Analysis and data for the publication: **"The Cover Crop Challenge: An experiential learning activity for teaching students about cover crop mixtures"**

## Background

Cover crop mixtures can provide a broader range of ecosystem services than monocultures, but designing effective mixtures is difficult due to competitive imbalances among species. The Cover Crop Challenge is an experiential learning activity where students design, grow, and evaluate cover crop mixtures. It was implemented across six universities in the Eastern and Midwestern United States (Cornell University, Clemson University, University of Nebraska–Lincoln, University of Kentucky, University of New Hampshire, and Michigan State University) during the 2022 and 2023 academic years.

A post-course survey (n = 78) found that 97% of respondents considered the Cover Crop Challenge a valuable activity. Students reported improved understanding of ecological, agronomic, and economic principles related to cover cropping, and positive correlations were found between perceived value of the activity and accomplishment of course-wide learning objectives.

The protocol, report instructions, and excel file given to students for this activity can be found in the "student_materials" folder. 

## Data

All raw data are in the `data/` folder, organized by year:

```
data/
├── 2022 Data/
│   ├── CoverCropChallenge_Results2022.xlsx   # Greenhouse and field performance data (2022)
│   ├── CoverCropSurvey2022_Cleaned.xlsx      # Cleaned student survey responses (2022)
│   └── Figs/                                 # Figures generated for 2022 analysis
└── 2023 Data/
    ├── CoverCropChallenge_Results2023.xlsx   # Greenhouse and field performance data (2023)
    ├── CoverCropChallenge23_data.xlsx        # Additional 2023 challenge data
    └── CoverCropSurvey2023_Cleaned.xlsx      # Cleaned student survey responses (2023)
```

**Challenge results workbooks** contain multiple sheets:
- `Greenhouse` — total biomass (g/pot and lb/a), family-level biomass, family evenness, economic efficiency, and expense per acre for greenhouse-grown mixtures
- `Outside` — same metrics for field-grown mixtures (biomass in g/0.25m²)
- `Ecosystem services axes` — student ratings across eight ecosystem service dimensions (used for radar/spider plots)

**Survey workbooks** contain Likert-scale and binary-choice responses covering:
- Overall course satisfaction and learning objective achievement (9 items, 5-point scale)
- Most and least effective lab modules
- Most and least effective multi-site meeting activities
- Cover Crop Challenge-specific agreement statements (7 items, 5-point scale)
- Student growth ratings and correlation items

## Analysis

All analysis is in `code/CC_Challenge.Rmd`. The main sections are:

| Section | Description |
|---|---|
| Loading | Read and merge 2022/2023 survey data; assign university-to-state mapping |
| Map of students | Choropleth map of participating universities by year |
| Overall satisfaction | Likert plots of course-level learning objective agreement, split by setting (greenhouse-only vs. greenhouse + field) |
| Lab effectiveness | Diverging bar charts of most/least effective lab modules by year |
| Multi-site activity | Diverging bar charts of most/least effective multi-site meeting activities by year |
| Cover crop activity | Likert plots of Cover Crop Challenge-specific statements, by year and setting |
| Cover crop ratings | Density plots of student growth ratings; correlation analysis between value ratings and learning objectives |
| Correlation analysis | Spearman correlations between challenge value and course learning objectives; normality testing; split by cohort (both years, 2022, 2023) |
| Challenge results plots | Dot plots of greenhouse and field biomass, evenness, and economic efficiency by student/year |
| Spider/radar plots | Radar charts of ecosystem service scores for selected students |
| Range table | Summary table of min/max biomass (kg/ha), evenness, and economic efficiency by setting and year, formatted with `gt` |

Key packages: `tidyverse`, `likert`, `ggstats`, `patchwork`, `openxlsx`, `janitor`, `fmsb`, `gt`

All student names have been removed from the data uploaded to GitHub.


