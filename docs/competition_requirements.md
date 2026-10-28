# Analytics Cup 2027 Competition Requirements

Last verified: **2026-10-27**.

This document summarizes the published requirements for **Analytics Cup 2.0**, the second edition organized by SkillCorner and PySport, whose finals take place in 2027. It supports the **Effective Running Distance** project. The organizers' current rules and subsequent clarifications remain authoritative. [SkillCorner announcement](https://skillcorner.com/analytics-cup-2027)

## 1. Competition scope and eligibility

- Participation is worldwide, including students, independent analysts, researchers, developers, and professionals.
- Enter alone or with one teammate: **two people maximum**. Each person registers individually.
- Choose **Europe or USA**, regardless of residence; entering both regions is prohibited.
- Within that region, submit at most **one Football project and one Basketball project**, separately.
- Projects can be analyses, research, methods, visualizations, or practical tools. There are no compulsory thematic tracks.
- Suggested themes are **Defensive Positioning** for football and **Shot Quality** for basketball. Other research questions are permitted.

These conditions and themes are described in the [official overview](https://pysport.org/analytics-cup/editions/analytics-cup2/overview).

## 2. Dates and submission route

| Milestone | Published date |
| --- | --- |
| Registration and challenge opening | 2026-09-09 |
| Project submission deadline | 2026-12-18 |
| Finalist announcement | 2027-01-08 |
| Europe final, Paris, France | 2027-02-17 |
| USA final, Boston, Massachusetts | 2027-02-24 |

Dates above follow the [official schedule](https://pysport.org/analytics-cup/editions/analytics-cup2/key-dates).

The submission platform specifies **2026-12-19 00:01 UTC**, equivalent to **2026-12-18 18:01 America/Chicago (CST)**. Recheck before submitting. [Official call for proposals](https://pretalx.pysport.org/analytics-cup-2/cfp)

1. [Register individually](https://pysport.org/analytics-cup/editions/analytics-cup2/register), choosing the sport and region. Registration provides access to the competition Discord.
2. Submit the completed project through [submissions.analytics-cup.org](https://submissions.analytics-cup.org/), which redirects to the official pretalx platform. Registration must precede submission. [Official FAQ](https://pysport.org/analytics-cup/editions/analytics-cup2/faq)
3. The initial [submission form](https://pretalx.pysport.org/analytics-cup-2/submit/) requests a project title, track, and optional teammate email. Further submission steps were not completed during this review.

## 3. Available data

The competition advertises the following datasets. Counts describe different data layers; they do not imply full tracking coverage for every season match. [Official dataset description](https://pysport.org/analytics-cup/editions/analytics-cup2/datasets)

| Sport and season | Published coverage |
| --- | --- |
| Football: Australia A-League 2024/25 | Season-level physical aggregates covering 175 matches; XY tracking for 20 matches, including 10 new matches; Game Intelligence Dynamic Events for those 10 matches; body pose for two matches; documentation, tutorials, and visualization tools. |
| Basketball: Liga Endesa ACB 2025/26 | Season-level shot, pick, and drive event aggregates covering 327 matches; XY tracking and Game Intelligence Dynamic Events for 10 matches; documentation. |

Official entry points: [Football data](https://github.com/SkillCorner/opendata) and [Basketball data](https://github.com/SkillCorner/opendata-basketball).

**Availability discrepancy:** the football repository README currently describes **10 tracking matches**, whereas the competition page advertises **20**. Verify the competition distribution and match IDs after registration; do not assume the public repository alone contains the full competition allocation. [Football repository README](https://github.com/SkillCorner/opendata/blob/master/README.md)

For distance calculations, that README documents tracking at **10 Hz**, coordinates in **meters**, and a flag distinguishing detected from extrapolated player positions. It warns about tracking errors and recommends speed/acceleration smoothing. These are technical considerations for this project, not additional competition rules. [Tracking documentation](https://github.com/SkillCorner/opendata/blob/master/README.md)

## 4. Required submission materials

| Deliverable | Requirement |
| --- | --- |
| YouTube pitch | Publicly accessible; **60 seconds maximum**; presented and voiced by the entrant or teammate. Explain the problem, contribution, and significance. |
| GitHub repository | Public; include all necessary project code and resources, **excluding competition datasets**, with an open-source license and **`LICENSE.md`**. |
| `README.md` | **1,000 words maximum**; **two figures/tables combined maximum**; provide evidence and technical explanation supporting the pitch. |

Submission specifications come from the [official call for proposals](https://pretalx.pysport.org/analytics-cup-2/cfp). Reproduction obligations are summarized below.

## 5. Mandatory research, reproducibility, and licensing rules

- Create substantial new work for this competition; resubmitting or lightly modifying completed projects is insufficient. Disclose reused libraries/frameworks and comply with their licenses.
- Use only SkillCorner datasets supplied for this or previous Analytics Cups. External video, matches, tracking, or event data cause immediate disqualification.
- Reproduce results without proprietary software, including Excel, Tableau, or Power BI. Ensure immediate execution and document clean-environment setup in the README.
- Keep submissions open source permanently, using MIT, Apache 2.0, or a similar license.
- Contributors retain their original work; SkillCorner retains dataset rights. Participation permits promotional use, case studies, and presentations. Obtain necessary employer, university, or other third-party permissions.
- Respectful, inclusive, professional conduct is required. Plagiarism, false registration information, review manipulation, late delivery, broken execution, and rule violations can disqualify an entry.
- SkillCorner/PySport employees may participate but cannot receive prizes or present at the finals.
- Finalists may receive additional organizer-provided data under a separate EULA between selection and the final; this does not authorize external data beforehand.

Source: [Official competition rules](https://pysport.org/analytics-cup/editions/analytics-cup2/rules).

## 6. Evaluation

All five criteria carry **20%**:

| Criterion | Emphasis |
| --- | --- |
| Relevance | Sporting usefulness. |
| Methodology | Appropriate, transparent, technically sound analysis. |
| Originality | Novel contribution. |
| Communication | Clear explanation and evidence. |
| Open-source potential | Reusable methods and code. |

Source: [Official judging criteria](https://pretalx.pysport.org/analytics-cup-2/cfp).

## 7. Finals, travel, and awards

- Each region selects **six finalist submissions**.
- Each selected submission receives **EUR 500** in Europe or **USD 500** in the USA, regardless of team size.
- Each regional winner receives a further **EUR 1,500 / USD 1,500** open-source grant, paid after completing the agreed package, contribution, or other open-source deliverable.

Award conditions: [Official competition details](https://pysport.org/analytics-cup/editions/analytics-cup2/competition).

Remote presentations are prohibited. Travel and accommodation are not reimbursed; the finalist award may cover costs. [Attendance and travel rules](https://pysport.org/analytics-cup/editions/analytics-cup2/rules)

The submission platform says **at least one team member** must attend. [Team attendance requirement](https://pretalx.pysport.org/analytics-cup-2/cfp)

## 8. Implications and items to confirm

The following are project planning conclusions, not additional organizer requirements:

- **Topic fit:** Effective Running Distance can be pursued without adopting the suggested defensive theme. Define what makes running "effective" and demonstrate its sporting value.
- **Data inventory:** Record the authorized match IDs and data layers actually received before designing the full experiment. Resolve the 10-versus-20-match discrepancy.
- **Reproduction:** Keep source data outside the submission repository and document authorized acquisition, setup, and execution. Test the workflow in a clean environment before submission.
- **Submission packaging:** Reserve the limited README space for the question, method, strongest evidence, limitations, and reproduction steps. This requirements document is an internal reference, not the competition pitch.
- **Unspecified details:** The reviewed public pages do not specify a submission language, final presentation duration, or separate registration closing date. Do not infer these from this project's English-language convention.
- **Rule updates:** Revisit the official rules and registered-participant Discord before finalizing the submission. Treat new organizer clarifications as the controlling source.
