# Effective Running Distance

A football analytics project in preparation for the [SkillCorner and PySport Analytics Cup 2.0](https://skillcorner.com/analytics-cup-2027), with finals in 2027.

## Research direction

The project will investigate how to distinguish useful player movement from total distance covered using the competition's SkillCorner football data. The definition of effective running, methodology, and evaluation remain to be developed.

## Current status

**Preparation stage; not ready for competition submission.**

The competition requirements have been reviewed and documented. This repository currently contains documentation only. No analysis pipeline, experiments, validated results, or pitch video are available yet.

## Repository contents

- [Competition requirements](docs/competition_requirements.md): eligibility, authorized data, submission materials, judging criteria, dates, and unresolved details.
- [Development guidelines](AGENTS.md): project organization and development conventions.
- [MIT license](LICENSE.md): license for the project's original contributions.
- [.gitignore](.gitignore): excludes datasets, local secrets, temporary files, and development caches.

## Data

Use only SkillCorner datasets authorized for this competition or previous Analytics Cups. Do not supplement them with external video, tracking, or event data.

Start with the [official competition dataset page](https://pysport.org/analytics-cup/editions/analytics-cup2/datasets) and [SkillCorner football repository](https://github.com/SkillCorner/opendata). Confirm the allocated matches and access instructions after registration. Store local datasets under `data/`, which is excluded from version control.

SkillCorner provides the data and retains the applicable dataset rights. The project's MIT license does not relicense those datasets.

## Setup and reproducibility

To obtain the current documentation:

```bash
git clone https://github.com/Terreturn/SkillCorner-competition.git
cd SkillCorner-competition
```

No runtime dependencies are required to read this repository. There is currently no analysis command to run and no result to reproduce. Before submission, this section must document the tested environment, dependency installation, authorized data acquisition and placement, and exact commands that reproduce the reported results without proprietary software.

## Remaining work before submission

- Define the research question, metric, baseline, and evaluation procedure.
- Verify authorized data coverage and document preprocessing decisions.
- Implement and validate the analysis, including a clean-environment reproduction check.
- Report evidence, limitations, and any reused code or libraries with appropriate attribution and license compliance.
- Update this README with the completed method and results while keeping it within **1,000 words** and **two figures or tables combined**.
- Add a publicly accessible YouTube pitch of **at most 60 seconds**, presented and voiced by a team member.
- Confirm registration, the selected region, team membership, and in-person finalist availability; submit through the official platform before its deadline.

These requirements are tracked in the [competition reference](docs/competition_requirements.md). Synchronizing this repository does not register the team or submit an entry.

## License

Original project contributions are released under the [MIT License](LICENSE.md). Any reused third-party materials remain subject to their respective licenses and must be attributed.
