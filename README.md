# Fall 2026 Course Schedule for the NUIST Fang Class 

Copyright @Xuan Yao

This repository contains a maintainable LaTeX version of the original Excel course schedule. It is designed to preserve the layout and visual style of the original spreadsheet as closely as possible, including the landscape A4 format, blue session headers, alternating light-blue rows, eight-column structure, and merged cells used for debate sessions.

## Files

- `main.tex`: Contains the page layout, colours, column widths, fonts, and macro definitions. This file generally does not need to be modified frequently.

- `schedule-data1.tex`: Contains the academician commentary sessions, where all students attend together as one combined class.

- `schedule-data2.tex`: Contains the parallel teaching sessions for three small groups, with the three classes running concurrently.

Most routine schedule updates should be made in `schedule-data1.tex` and `schedule-data2.tex`.

## Overleaf

1. Create a new **Blank Project**.
2. Upload `main.tex`, `schedule-data1.tex`, and `schedule-data2.tex`.
3. Set the compiler to **XeLaTeX**.
4. Set `main.tex` as the main document.

## Updating the Schedule

For a standard presentation row, use:

```tex
\ReportBlue{时间}{报告人}{题目}{论文编号}{辅导老师}{质疑同学}{提问老师}{巡回点评}
```

For a row with a white background, use:

```tex
\ReportWhite{...}
```

For a break:

```tex
\BreakRow{19:40-19:50}{课间休息}
```

The session title, table header, and presentation rows for each session are contained within the same `tabularx` environment. To add a new session, simply copy a neighbouring session and use it as a template.

## GitHub

GitHub displays `.tex` source files directly, making it convenient for collaborative review and pull requests.

To generate the PDF locally, install TeX Live and run:

```bash
latexmk -xelatex main.tex
```