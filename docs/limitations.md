[Back to README](../README.md) · [Open the Excel workbook](../template/manufacturing-estimating-quoting-cpq-requirements-matrix.xlsx) · [Use the online decision tool](https://configure.win/resources/manufacturing-software-decision-tool)

# Limitations

The Manufacturing Software Decision Tool is a practical assessment, requirements-planning and process-ownership workbook. The following boundaries should be considered when interpreting or reporting its outputs.

## No vendor ranking or software benchmark

The scores measure only the intensity of the requirements entered.

They do not compare:

- vendors;
- products;
- implementation quality;
- total cost of ownership;
- industry fit;
- product maturity;
- integration effort;
- implementation risk;
- expected return.

A score of 100 means that the fictional or user-entered answers produced the maximum weighted requirement score for that category. It does not mean that a product scores 100.

## Incomplete answers are treated as zero in Excel

The workbook instructions require one answer for every requirement.

However, the score formulas treat any value other than Helpful or Essential—including a blank—as zero.

Consequences:

- an incomplete assessment can display low scores;
- the workbook can display a recommendation before all questions are answered;
- linked Need level cells in Requirements matrix can display `0` when the source answer is blank.

Complete all twelve answers before interpreting the result.

The browser-based decision tool separately requires completion of all twelve questions before presenting the final recommendation.

## Requirement categories can overlap

Estimating, configuration and quoting are conceptual responsibilities.

The result does not prove that:

- each category requires a separate product;
- one integrated platform is always preferable;
- specialist systems are always preferable;
- a specific vendor architecture is correct.

The essential design question is which system owns each source value, calculation, rule, approval and output.

## Scores do not reflect current coverage

Existing-system flags do not change scores.

A high requirement can therefore coexist with an existing system that appears to cover it.

The workbook separates:

- requirement intensity;
- current coverage;
- gap interpretation.

Do not lower a requirement answer merely because a current system exists.

## Architecture preference does not change the recommendation

Architecture preference changes the architecture subtitle only when the recommendation is Combination of systems.

It does not:

- alter scores;
- alter category roles;
- add or remove a core category;
- prove that the preferred architecture is feasible.

## Primary bottleneck is contextual

The bottleneck does not change scores.

It can influence:

- the recommendation in no-core cases where at least one category reaches 40;
- the Primary system output when no score reaches 65;
- the Primary system output when the two highest scores differ by seven points or less.

It is not a substitute for answering the requirements.

## Tie behavior is deterministic

When no category is core and the recommendation falls back to the highest score:

- Estimating wins a tie involving Estimating;
- Configuration wins a tie with Quoting when Estimating is not tied for the maximum;
- Quoting is selected only when it is strictly above the earlier categories.

This is formula order, not a policy that Estimating is inherently more important.

## Existing-system gap logic is simplified

The Decision tool’s gap summary checks only selected core-category coverage conditions:

- Estimating core → covered when Estimating software is marked Yes;
- Configuration core → covered when Product configurator or CPQ is marked Yes;
- Quoting core → covered when Product configurator or CPQ or CRM or quoting software is marked Yes.

It does not inspect:

- product scope;
- implementation quality;
- module availability;
- data quality;
- adoption;
- rule depth;
- integration maturity.

The `None of these` flag does not itself change the score, gap or adjacent-system formulas. The individual Yes flags drive those outputs.

## Adjacent-system notes are selective

The automatic adjacent-system notes use:

- ERP or MRP;
- MES;
- CAD or PLM;
- CRM or quoting software;
- Proposal or document software.

When none of those five flags is Yes, the workbook returns a generic instruction to validate adjacent ownership.

The notes do not represent a complete integration architecture.

## Requirements-matrix need levels are grouped

One high-level answer populates several detailed capabilities.

This is useful for planning, but it assumes those capabilities share the same initial need level.

Review and refine the detailed rows rather than assuming every capability in a group has identical importance.

## Requirements-matrix gap categories are coarse

The automated matrix gap is based on:

- Need level;
- Current coverage;
- Requirement group.

It does not inspect the Current system, Evidence, owner fields or implementation notes.

For uncovered or partially covered rows, it returns one group-based category:

- Calculation gap
- Configuration gap
- Governance gap
- Integration gap

The Definitions sheet lists additional categories such as Process gap, Data gap and Other, but the current formulas do not assign them automatically.

## Process-ownership gap uses exact text equality

The Process ownership Gap formula compares Current owner with Recommended owner.

- exact match → No gap;
- any other nonblank value → Process gap.

Semantically similar values can therefore produce a gap.

For example:

```text
Manufacturing quoting software
```

does not exactly equal:

```text
Manufacturing quoting software (supporting)
```

Review the formula output and use Notes to explain valid exceptions.

## Release ownership is derived from quoting role

The Release stage uses the Commercial quoting category role:

- Core or Supporting → Manufacturing quoting or document system
- Requirement to validate → Release ownership to validate
- No dedicated component indicated → Document/proposal system or existing process

The workbook does not independently score document-generation or release-management requirements beyond question 12.

## Scenario library uses simplified context

The three scenarios demonstrate the score and role model.

They do not contain the full Decision tool context set of:

- bottleneck;
- architecture preference;
- existing-system flags.

Their recommendation formulas therefore demonstrate the category logic without the full contextual wording used in Decision tool.

The scenario Architecture formula has explicit labels for:

- Combination of systems;
- Manufacturing estimating software;
- Manufacturing quoting software.

Other recommendation states fall back to **Ownership to validate**.

## No implementation validation

The workbook does not validate:

- API availability;
- data volumes;
- technical architecture;
- security;
- regulatory requirements;
- migration complexity;
- vendor roadmap;
- implementation partner capability;
- budget;
- timeline;
- organisational readiness.

## No professional advice

The workbook does not provide legal, financial, engineering, procurement or implementation advice.

## User responsibility

The user remains responsible for:

- the accuracy of all answers;
- the process boundary assessed;
- the interpretation of category definitions;
- validation of current system coverage;
- integration and data-handoff design;
- vendor and product evaluation;
- target architecture;
- implementation decisions.

For exact formulas, see [Scoring methodology](scoring-methodology.md). For category boundaries, see [Software-category definitions](software-category-definitions.md).
