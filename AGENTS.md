# Project Development and File Management Guidelines

These guidelines apply throughout the project, including code generation, modification, review, experiments with multiple models, large-scale data processing, and file management.

Goal: complete explicit requirements with the smallest correct and maintainable implementation while keeping the project structure, current progress, and final results easy to understand and locate.

## 1. Core Principles

1. Implement only what is explicitly requested. Do not add speculative features.
2. Prefer the simplest correct solution. Avoid overengineering and premature optimization.
3. Reuse existing code, directories, and conventions instead of creating parallel implementations of the same functionality.
4. Minimize unnecessary abstractions, classes, wrappers, configuration options, and dependencies.
5. Do not refactor unrelated code or rewrite working implementations merely for style.
6. Avoid duplication without introducing complex frameworks for small amounts of similar code.
7. Handle realistic errors. Never silently ignore failures, invalid data, or missing results.
8. Prioritize readability, correctness, and maintainability before evidence-based performance optimization.
9. Before creating a file, consider whether an existing file can be updated and whether the new file needs to be retained.
10. Keep documentation, configuration, and experiment records concise. Project management should not create unnecessary overhead.

## 2. Before Starting Work

- Read this file and existing project documentation to understand the current stage, completed work, and unresolved issues.
- Inspect relevant code, directories, and existing artifacts to identify the smallest necessary change. Do not immediately generate a replacement implementation.
- For complex tasks, explain the objective, main steps, expected file changes, and validation approach before proceeding incrementally.
- First complete a small workflow that validates the approach, then expand to multiple models or the full dataset.
- Do not overwrite the user's existing changes or delete files whose origin or purpose is unclear.
- When continuing with a different model or conversation, read existing records and verify actual files to avoid duplicate implementation and repeated runs.

## 3. Directory Organization

Follow any reasonable existing structure. New projects may use the layout below, but create directories only when needed. Do not generate empty directories or placeholder files in advance.

```text
project_root/
├── AGENTS.md              # Long-term collaboration and development guidelines
├── README.md              # Project overview, navigation, run instructions, and progress
├── src/                   # Reusable project code and execution entry points
├── configs/               # Model, data, and experiment configuration when needed
├── data/
│   ├── raw/               # Original data; read-only by default
│   └── processed/         # Reusable processed data worth retaining
├── outputs/
│   ├── runs/<run_id>/      # Essential records, results, and checkpoints for one experiment
│   └── summary/            # Experiment comparisons, summary tables, and selected figures
├── tests/                 # Necessary tests
├── docs/                  # Topic-specific documentation when README is insufficient
└── tmp/                   # Disposable temporary files; clean up when the task ends
```

- Keep the root directory limited to project entry documentation, necessary dependency and tool configuration, and main directories.
- Separate source code, data, experiment artifacts, and temporary files. Do not scatter results across source directories or the project root.
- Group similar files together. Reuse an existing directory rather than creating another with the same purpose.
- Share data processing and evaluation logic across models. Do not copy the entire project for each model.
- Do not move existing files solely to match this example. Limit necessary structural changes and update affected references.
- Use relative paths or centrally configured data paths instead of scattering machine-specific absolute paths throughout the code.

## 4. File Naming and Intermediate Artifacts

- Use descriptive, consistent names. Avoid names such as `final_v2`, `new_new`, or `test123` that do not explain a file's purpose.
- Update existing maintained files instead of repeatedly copying them to preserve editing history.
- Maintain a clear authoritative location for each type of documentation, configuration, and summary to prevent inconsistent duplicates.
- Put temporary scripts, debugging output, and one-off conversion files in `tmp/` or the system temporary directory. Move logic into maintained code only when it needs to be reused.
- Do not write intermediate results to disk by default. When memory limits, reuse across stages, computation cost, or recovery require persistence, use an appropriate directory and record the purpose. Do not force large datasets into memory merely to reduce file counts.
- Do not retain multiple formats or copies of the same data without a specific compatibility, delivery, or performance requirement.
- Do not create separate documentation for every batch, debugging attempt, or conversation. Maintain logs, run records, and summaries centrally.
- Keep only the logging needed for diagnosis and reproduction. Avoid printing every data record or allowing logs to grow without bounds.
- At the end of the task, remove temporary files created by that task only when they are confirmed to be unnecessary. Preserve original data, final results, expensive reusable caches, and existing files with unclear purposes.
- Configure appropriate ignore rules for temporary files, caches, and generated artifacts so they are not inadvertently treated as source code.

## 5. Large-Scale Data Processing

- Treat original data as immutable by default. Write cleaned, filtered, or transformed data separately without overwriting source files.
- Inspect dataset size, format, fields, missing values, duplicates, and key constraints before choosing a processing approach.
- For large datasets, prefer chunked reads, streaming, or reading only required fields. Avoid loading or copying the entire dataset unnecessarily.
- Validate the workflow, resource usage, and output on a representative sample before processing the full dataset.
- Record the filtering, deduplication, missing-value, and outlier rules actually applied, along with record counts before and after processing.
- Do not silently discard failed records. Retain error counts, reasons, and limited examples as needed rather than duplicating the entire failed dataset.
- Support staged execution or recovery for long-running workflows when justified. Do not introduce complex scheduling systems for simple tasks.
- Before reusing validated processing results, confirm that the input data, processing code, and configuration still match to avoid stale caches.
- Estimate storage needs before tasks that may produce many files. Use sensible partitioning or consolidated outputs instead of large numbers of tiny files.

## 6. Model and Experiment Management

- Establish a simple baseline when applicable, then add models or complexity incrementally.
- Reuse common data loading, preprocessing, and evaluation logic. Implement separate paths only where models genuinely differ.
- Centralize parameters that actually need adjustment instead of maintaining the same values in multiple scripts. Small tasks do not require a separate configuration system.
- Compare models using consistent data versions, evaluation samples, metric definitions, and calculations. Record any necessary differences.
- For training and evaluation, fix dataset splits and prevent test information from entering training, preprocessing fitting, or parameter selection.
- Assign a unique `run_id` to each experiment worth retaining. Do not overwrite existing experiment results or create permanent experiment directories for every small debugging attempt.
- Keep the following together in the experiment directory: model name and version, data version or source identifier, actual configuration, execution command, code version or change identifier, random seed when applicable, status, and key metrics. Prefer saving these automatically in one record file over maintaining duplicate records manually.
- Distinguish running, successful, failed, and interrupted experiments. Do not label failed or partially processed runs as complete results.
- Retain only necessary model files and checkpoints, such as the selected best result and the latest checkpoint needed for recovery. Do not save every training epoch by default.
- Maintain one comparison table for retained experiments, linking each entry to its `run_id` and result path. Do not copy the same results into multiple documents.
- Estimate runtime, memory, disk usage, and applicable API costs before full runs. Validate at a small scale first and avoid repeating expensive runs without justification.

## 7. Project Documentation and Progress

- Use `AGENTS.md` for long-term guidelines, not experiment logs or daily progress entries.
- When project implementation begins, use `README.md` as the main entry point. Reuse an existing equivalent document instead of creating duplicate documentation.
- Make the project goal, directory purposes, environment setup, execution instructions, current stage, validated results, pending work, and blockers easy to find.
- Track progress through stages with concrete outputs, such as data preparation, baseline validation, model comparison, and result organization. Adapt stages to the actual project.
- Clearly distinguish planned, in progress, verified complete, and blocked work. Written code alone does not mean results have been validated.
- Update existing progress records when a meaningful stage is completed or a change affects subsequent work. Do not create a new summary for every operation.
- Record only decisions and reasons that affect future work. Avoid copying conversation history or terminal output into documentation.
- Link to final results and experiment summaries from README rather than duplicating full metrics, logs, or data.
- If the project genuinely needs a separate progress document, link it from README and maintain progress in only one place.

## 8. Code Changes and Validation

- Keep changes minimal and avoid modifying unrelated modules.
- Avoid unused variables, imports, and dependencies. Check actual call sites when removing or changing interfaces.
- Use comments to explain necessary reasoning, assumptions, and limitations rather than restating obvious code.
- Run relevant tests or small-scale checks appropriate to the change. Prioritize critical data processing, metric calculations, and interface behavior over tests that merely repeat the implementation.
- When changing data workflows, check key fields, record-count changes, output formats, and error handling against expectations.
- When changing model or evaluation workflows, verify a small sample first, then check metric calculations and consistency of comparison conditions.
- If validation cannot be completed, state what remains unverified, why, and the implications. Do not claim that checks passed.
- After validation passes, broaden testing only when new changes, failures, or unresolved concerns justify it. Avoid unnecessary repeated full runs.
- Before finishing, review newly created files, remove confirmed disposable artifacts, and update execution instructions and progress when needed.

## 9. Code Review

Focus on:

- Redundant functions, wrappers, and unnecessary abstractions.
- Unused variables, imports, dependencies, and configuration.
- Duplicated data processing, model invocation, or evaluation logic.
- Excessive defensive code, configuration options, and unnecessary complexity.
- Duplicate files, outdated documentation, broken paths, and intermediate artifacts without a clear purpose.

Review requirements:

- First report specific issues, the smallest proposed simplifications, and their risks. Obtain approval before making those changes.
- Preserve existing behavior. Do not rewrite working code merely for style or remove necessary validation.
- State uncertainty when a file's purpose or a change's impact is unclear. Do not delete it without justification.
- This approval requirement applies to additional changes proposed during review. Implement changes already explicitly requested by the user within the authorized scope without asking for approval again.

## 10. Completion Reports

Keep completion reports concise and focused on:

- What was completed and which key files changed.
- What was validated, the results, and anything still unverified.
- Where final results are stored, with directly accessible paths when useful.
- Current progress, remaining issues, and next steps only when relevant.

Do not present tool-call history, complete logs, or temporary-file inventories as deliverables. When the user asks to see an updated file, show the content actually saved.

## 11. Language Requirements

- Use Chinese for direct communication with the user, including explanations, questions, progress updates, and completion reports in the conversation.
- Use English for all content authored or edited within the project, including this file, source code identifiers, comments, docstrings, documentation, descriptions, reports, configuration descriptions, logs, error messages, table headings, chart labels, and interface text.
- Use descriptive English names for newly created files and directories where names contain natural language.
- When displaying or quoting project content in the conversation, preserve its English text; accompanying explanations should remain in Chinese.
- Preserve raw data, external identifiers, and source material that must remain verbatim. Do not alter them solely to satisfy the language requirement.
