[Back to README](../README.md) · [Open the Excel workbook](../template/manufacturing-estimating-quoting-cpq-requirements-matrix.xlsx) · [Use the online decision tool](https://configure.win/resources/manufacturing-software-decision-tool)

# Scoring methodology

This document specifies the numeric scoring, intensity thresholds, category-role logic and recommendation branches used in the Excel workbook.

## Answer values

| Answer | Numeric value |
| --- | ---: |
| Not required | 0 |
| Helpful | 1 |
| Essential | 2 |

In the Excel formulas, a blank or any value other than Helpful or Essential is treated as 0.

## Requirement weights

### Estimating

| No. | Requirement | Weight |
| ---: | --- | ---: |
| 1 | Calculate material, labor, machine, tooling, setup, subcontracting and overhead cost | 3 |
| 2 | Use routings, operation times, batch sizes, scrap, yield and setup assumptions | 2 |
| 3 | Compare alternative materials, processes or estimate revisions | 1 |
| 4 | Compare estimated cost with actual manufacturing cost | 2 |

Maximum weighted score:

```text
(3 + 2 + 1 + 2) × 2 = 16
```

### Configuration

| No. | Requirement | Weight |
| ---: | --- | ---: |
| 5 | Enforce valid product options, dependencies and compatibility rules | 3 |
| 6 | Use CAD, BOM or engineering-rule logic | 3 |
| 7 | Guide users through configurable or engineer-to-order products | 2 |
| 8 | Manage configuration revisions and technical validation | 1 |

Maximum weighted score:

```text
(3 + 3 + 2 + 1) × 2 = 18
```

### Quoting

| No. | Requirement | Weight |
| ---: | --- | ---: |
| 9 | Apply price lists, customer-specific pricing, currencies, discounts and margins | 3 |
| 10 | Trigger approval from margin, discount, floor price, deal value or commercial risk | 3 |
| 11 | Validate quote completeness and preserve an explainable decision trace | 2 |
| 12 | Produce customer-ready quote output from approved data | 1 |

Maximum weighted score:

```text
(3 + 3 + 2 + 1) × 2 = 18
```

## Category-score formula

For each category:

```text
Category score
= Weighted answer total
÷ Maximum weighted score
× 100
```

The workbook rounds the result to two decimal places.

### Estimating formula

```text
(
  Q1 value × 3
+ Q2 value × 2
+ Q3 value × 1
+ Q4 value × 2
)
÷ 16 × 100
```

### Configuration formula

```text
(
  Q5 value × 3
+ Q6 value × 3
+ Q7 value × 2
+ Q8 value × 1
)
÷ 18 × 100
```

### Quoting formula

```text
(
  Q9 value × 3
+ Q10 value × 3
+ Q11 value × 2
+ Q12 value × 1
)
÷ 18 × 100
```

## Intensity thresholds

| Score | Intensity |
| ---: | --- |
| 0–39.99 | Low requirement |
| 40–64.99 | Moderate requirement |
| 65–100 | High requirement |

The workbook formulas use:

```text
score >= 65 → High
else score >= 40 → Moderate
else → Low
```

## Category-role logic

For each category:

```text
If score >= 65:
    Core category

Else if exactly one category is core
and this score >= 50:
    Supporting category

Else if score >= 40:
    Requirement to validate

Else:
    No dedicated component indicated
```

Because Core is evaluated first, Supporting effectively applies from 50 through 64.99.

A score of 50–64.99 is not Supporting when:

- no category is core; or
- two or more categories are core.

In those cases it becomes Requirement to validate.

## Core-category count

```text
Core count
= number of category scores >= 65
```

This count drives the first recommendation branches.

## Recommendation logic

### Branch 1: two or more core categories

```text
Recommendation = Combination of systems
```

### Branch 2: exactly one core category

The core category becomes the recommendation:

- Estimating core → Manufacturing estimating software
- Configuration core → CPQ/product configurator
- Quoting core → Manufacturing quoting software

A bottleneck does not replace this Recommendation output.

### Branch 3: no core categories

#### 3A. All scores below 40

```text
Recommendation = No dedicated component indicated
```

#### 3B. At least one score is 40 or higher

The workbook evaluates the primary bottleneck.

If bottleneck is:

```text
Connecting all three decisions
```

and at least two scores are 40 or higher:

```text
Recommendation = Combination of systems
```

If bottleneck is one category and that category scores at least 40:

```text
Recommendation = the bottleneck category
```

Otherwise:

```text
Recommendation = category with the highest score
```

## Highest-score tie behavior

The fallback formula checks Estimating first, then Configuration, then Quoting.

Therefore:

- Estimating wins any tie for the maximum that includes Estimating.
- Configuration wins a tie with Quoting when Estimating is lower.
- Quoting is selected only when it exceeds both earlier categories.

This is deterministic formula order.

## Architecture subtitle

### Combination of systems

The subtitle depends on Architecture preference.

| Preference | Subtitle |
| --- | --- |
| One integrated platform where practical | Integrated platform where practical, with explicit ownership for estimating, configuration and quoting. |
| Connected specialist systems are acceptable | Connected specialist systems with governed data and decision handoffs. |
| No preference — recommend the clearest ownership model | Use the clearest ownership model across estimating, configuration and quoting. |

### No dedicated component indicated

```text
Validate requirements before selecting a dedicated software component.
```

### Single-category recommendation

```text
Primary ownership in [recommendation] with adjacent systems connected as needed.
```

## Primary system output

The Primary system is separate from Recommendation.

First calculate the difference between the highest and second-highest score.

If:

- no score reaches 65; or
- the two highest scores differ by seven points or less;

and a bottleneck has been selected, Primary system follows the bottleneck:

| Bottleneck | Primary system |
| --- | --- |
| Cost to make | Manufacturing estimating software |
| Technically valid configuration | CPQ/product configurator |
| Customer price, margin and approval | Manufacturing quoting software |
| Connecting all three | Shared ownership across estimating, configuration and quoting |

Otherwise:

- Combination of systems → Shared ownership across the required categories
- Single-category recommendation → that recommendation
- No dedicated component → No dedicated component indicated

A selected bottleneck can therefore affect Primary system wording even when exactly one category remains the formal Recommendation.

## Supporting-system output

### Recommendation is Combination of systems

The output lists every category with a score of 65 or higher.

### Exactly one category is core

The output lists non-core categories with scores from 50 through 64.99.

### No core categories

```text
None indicated by current thresholds
```

The no-core Recommendation can still be one category or Combination of systems, but the Supporting system field remains None indicated by current thresholds.

## Existing-system gap summary

Existing-system flags do not change scores.

The formula reports:

### No core category

```text
No core category is currently indicated.
```

### Estimating core

- Estimating software = Yes → Estimating core requirement appears covered by existing estimating software.
- Otherwise → Uncovered estimating core requirement.

### Configuration core

- Product configurator or CPQ = Yes → Configuration core requirement appears covered by an existing configurator or CPQ.
- Otherwise → Uncovered configuration core requirement.

### Quoting core

- Product configurator or CPQ = Yes, or CRM or quoting software = Yes → Commercial quoting core requirement appears covered by an existing CPQ or quoting system.
- Otherwise → Uncovered commercial quoting core requirement.

The formula does not assess degree or quality of coverage.

## Adjacent-system notes

The output concatenates notes for each Yes flag:

- ERP or MRP → may remain owner of planning, inventory, procurement and orders
- MES → may remain source for actual production execution and realised outcomes
- CAD or PLM → may remain owner of engineering master data, BOMs and revisions
- CRM or quoting software → may remain owner of customer and opportunity context
- Proposal or document software → may remain owner of presentation, delivery or e-signature

When none of those five flags is Yes:

```text
Validate adjacent ownership for ERP/MRP, MES, CAD/PLM, CRM and document systems.
```

## Scenario-library scoring

The Scenario library uses the same:

- answer values;
- weights;
- category scores;
- intensity thresholds;
- role thresholds.

Its recommendation formula uses core count and highest score but does not use bottleneck, architecture preference or existing-system flags.

For the actual scenario inputs and results, see [Scenario library](scenario-library.md).

## Interpretation boundary

The score is a requirement index derived from entered answers.

It is not:

- a probability;
- a product score;
- a vendor score;
- a benchmark;
- an implementation recommendation by itself.
