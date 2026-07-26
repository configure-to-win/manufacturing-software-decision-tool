[Back to README](../README.md) · [Open the Excel workbook](../template/manufacturing-estimating-quoting-cpq-requirements-matrix.xlsx) · [Use the online decision tool](https://configure.win/resources/manufacturing-software-decision-tool)

# Workbook guide

This guide explains how to use the six worksheets in the **Manufacturing Software Decision Tool — Excel Requirements Matrix** and how the assessment, planning and ownership views relate to each other.

## Workbook structure

| Worksheet | Primary purpose | Main outputs |
| --- | --- | --- |
| **Decision tool** | Assess twelve manufacturing-software requirements and add process context | Three requirement scores, category intensity, category roles, software-scope recommendation, architecture wording, primary and supporting systems, gap summary and adjacent-system notes |
| **Requirements matrix** | Translate the assessment into detailed capability planning | Need level, current coverage, current system, calculated gap, software category, adjacent system, ownership, priority, evidence and notes |
| **Process ownership** | Define which system owns each decision from estimate through customer-ready release | Recommended owner, current and target ownership, handoffs, decision evidence, gap and priority |
| **Scenario library** | Demonstrate how different manufacturing operating models produce different results | Three complete fictional assessments, scores, category roles, recommendations and ownership patterns |
| **Worked example** | Present one fictional configurable-equipment result as a consolidated example | Scores, recommendation, process ownership, adjacent-system notes and illustrative process flow |
| **Definitions** | Provide the canonical model reference | Category definitions, answer values, weights, thresholds, recommendation logic, adjacent-system boundary, limitations and workbook information |

## Recommended sequence

Use the workbook in this order:

1. Complete all twelve requirements in **Decision tool**.
2. Add the primary bottleneck, architecture preference and existing-system flags.
3. Review the three requirement scores and category roles.
4. Review the recommendation, architecture wording and system-gap summary.
5. Open **Requirements matrix** and document detailed coverage, gaps, owners and evidence.
6. Open **Process ownership** and define current and target ownership for each process stage.
7. Compare the result with the fictional scenarios only to understand the method—not as a benchmark.
8. Record assumptions, unresolved boundaries and implementation decisions.

## Worksheet 1: Decision tool

### Requirement questions

The assessment contains three groups of four questions:

- **Cost estimation**
- **Product configuration**
- **Commercial quote control**

For every requirement, select:

- Not required
- Helpful
- Essential

The workbook instructions require one answer for every question.

The formulas calculate immediately. A blank answer is numerically treated as zero in the score formulas, so an incomplete assessment can display low scores and a recommendation. Do not interpret the final result until all twelve answers have been completed.

### Context inputs

The worksheet provides three types of context.

#### Primary bottleneck

Select one:

- Determining what the product or project will cost to make
- Determining which product configuration is technically valid
- Determining the customer price, margin and approval path
- Connecting all three decisions

The bottleneck does not change category scores. It can influence the recommendation when no category is core and can influence the displayed primary-system wording when the leading categories are close.

#### Architecture preference

Select one:

- One integrated platform where practical
- Connected specialist systems are acceptable
- No preference — recommend the clearest ownership model

Architecture preference does not change scores or category roles. In the workbook, it changes the architecture subtitle only when the recommendation is **Combination of systems**.

#### Existing-system flags

Record whether the current environment contains:

- Estimating software
- ERP or MRP
- MES
- CAD or PLM
- Product configurator or CPQ
- CRM or quoting software
- Proposal or document software
- None of these

The individual system flags do not change the requirement scores. They affect the existing-system gap summary and adjacent-system notes.

### Assessment result

The result dashboard displays:

- Estimating score, intensity and category role
- Configuration score, intensity and category role
- Quoting score, intensity and category role
- Recommendation
- Architecture subtitle
- Primary system
- Supporting system or systems
- Existing-system gap summary
- Adjacent-system notes

For the exact formulas and decision branches, see [Scoring methodology](scoring-methodology.md).

## Worksheet 2: Requirements matrix

The matrix contains 43 detailed capability rows:

| Requirement group | Number of capabilities |
| --- | ---: |
| Cost estimating | 14 |
| Product configuration | 11 |
| Commercial quoting | 11 |
| Adjacent system | 7 |
| **Total** | **43** |

### Matrix columns

For each capability, the worksheet provides:

- Requirement ID
- Requirement group
- Capability
- Description
- Need level
- Current coverage
- Current system
- Gap
- Primary software category
- Adjacent system
- Business owner
- Technical owner
- Priority
- Evidence or example
- Notes

### Linked need levels

The cost-estimating, product-configuration and commercial-quoting rows inherit their **Need level** from the relevant Decision tool answer.

One assessment answer can therefore populate several detailed capabilities. For example, the first estimating question populates the detailed rows for material, labor, machine, setup, tooling, subcontracting and overhead.

The adjacent-system rows are not linked to the twelve-question assessment and can be completed directly.

Complete the Decision tool before interpreting linked need levels. When the source answer is blank, the direct Excel reference can display `0` rather than one of the three text labels.

### Current coverage and calculated gap

The Current coverage vocabulary is:

- Not covered
- Partially covered
- Covered

For the core requirement groups, the Gap formula returns:

- No gap, when the need is Not required;
- blank, when coverage has not been entered;
- No gap, when coverage is Covered;
- Calculation gap, for an uncovered or partially covered cost-estimating capability;
- Configuration gap, for an uncovered or partially covered product-configuration capability;
- Governance gap, for an uncovered or partially covered commercial-quoting capability;
- Integration gap, for an uncovered or partially covered adjacent-system capability.

The Definitions sheet also lists Process gap, Data gap and Other as reference categories. The current Requirements matrix formulas do not assign those three categories automatically.

### Priority and evidence

Use:

- Low
- Medium
- High
- Critical

Add evidence that makes the requirement testable, such as an actual quote, drawing, routing, approval condition, pricing rule, BOM issue or system handoff.

## Worksheet 3: Process ownership

The worksheet covers five stages:

1. Estimate
2. Configure
3. Price
4. Approve
5. Release

For each stage, document:

- Core decision
- Required inputs
- Calculations or rules
- Recommended owner
- Current owner
- Source system
- Target system
- Handoff method
- Decision evidence
- Gap
- Priority
- Notes

The Recommended owner is linked to the category role in Decision tool.

The Gap field compares Current owner with Recommended owner:

- blank Current owner → blank gap;
- exact text match → No gap;
- any other nonblank value → Process gap.

Because this is an exact text comparison, descriptions such as `(supporting)` are significant. Review the result rather than assuming semantically similar labels will match.

See [Process ownership guide](process-ownership-guide.md).

## Worksheet 4: Scenario library

The library contains three fictional scenarios:

- Contract manufacturer
- Configurable industrial-equipment manufacturer
- Manufacturer of standard products

Each scenario contains:

- all twelve answers;
- category scores;
- intensities;
- category roles;
- recommendation;
- architecture;
- recommended stage ownership;
- a short adjacent-system or support note.

These scenarios demonstrate the model. They are not customer data, vendor recommendations, market benchmarks or universal implementation patterns.

See [Scenario library](scenario-library.md).

## Worksheet 5: Worked example

The worked example uses the configurable industrial-equipment assessment.

It produces:

- Estimating: 81.25 — Core category
- Configuration: 100 — Core category
- Quoting: 100 — Core category
- Recommendation: Combination of systems
- Architecture: Estimating + configurator + quoting

The worksheet also presents:

```text
Manufacturing estimating software
→ CPQ/product configurator
→ Manufacturing quoting software
→ Manufacturing quoting software
→ Manufacturing quoting or document system
```

ERP/MRP, CAD/PLM and CRM remain adjacent owners in the example.

## Worksheet 6: Definitions

Use the Definitions sheet as the canonical workbook reference for:

- software-category boundaries;
- answer values;
- requirement weights;
- maximum weighted scores;
- intensity thresholds;
- category-role thresholds;
- recommendation logic;
- adjacent-system roles;
- limitations;
- workbook version and publisher;
- official Configure to WIN resources.

## Related documentation

- [Methodology](methodology.md)
- [Scoring methodology](scoring-methodology.md)
- [Definitions](definitions.md)
- [Software-category definitions](software-category-definitions.md)
- [Process ownership guide](process-ownership-guide.md)
- [Scenario library](scenario-library.md)
- [Limitations](limitations.md)
