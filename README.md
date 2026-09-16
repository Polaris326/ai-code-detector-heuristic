---
license: cc0-1.0
language: en
source: https://ismycodeai.com/
author: Polaris326
---

# Code Style Heuristic Rules Dataset

This dataset is a source-backed table of the configured code-style rules used by the AI Code Detector browser interface. Each row documents one rule, its configured weight, the code pattern it evaluates, the report fields it can populate, and its interpretation boundary.

## Files

- `data/code_style_heuristic_rules.csv` contains the rule table.

## Provenance

The rows are exported from the public default rule configuration in `src/heuristic.js`. The live browser implementation is available at [ismycodeai.com](https://ismycodeai.com/).

## Fields

- `rule_id`: Stable identifier for the rule row.
- `rule_name`: Human-readable rule name used in reports.
- `default_weight`: Configured contribution when the rule matches one or more lines.
- `match_scope`: Code element evaluated by the rule.
- `match_pattern`: Pattern or structural condition used by the default implementation.
- `description`: Plain-language description of the signal.
- `report_field`: Report fields associated with a match.
- `limitations`: Boundary for interpreting the signal.

## Report shape

The implementation returns `score`, `lines`, `matches`, and `flaggedLines`. The score is the sum of matched configured rule weights with a cap. A `matches` entry identifies the rule, its weight, and the matching line indexes. `flaggedLines` contains every line index involved in a match.

## Limitations

These are code-style signals, not evidence of authorship. A matching signal cannot establish who wrote code or whether an AI tool was involved. Similar patterns can arise from shared templates, project conventions, linters, formatters, generators, and ordinary descriptive code. Use the table to support contextual review rather than a final decision.

## License

This dataset is dedicated to the public domain under [CC0 1.0](LICENSE).
