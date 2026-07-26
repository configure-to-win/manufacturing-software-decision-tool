[Back to README](../README.md) · [Open the Excel workbook](../template/manufacturing-estimating-quoting-cpq-requirements-matrix.xlsx) · [Use the online decision tool](https://configure.win/resources/manufacturing-software-decision-tool)

# Methodology

The Manufacturing Software Decision Tool uses a requirement-led method to distinguish three decision layers in a manufacturing quote process and then translate the result into capability, gap and ownership planning.

This document describes the complete assessment workflow. The numeric formulas and exact recommendation branches are documented separately in [Scoring methodology](scoring-methodology.md).

## Method objective

The method is designed to answer:

```text
Which software responsibilities are required by this manufacturing quote process?
```

It is not designed to answer:

```text
Which vendor or product should be purchased?
```

The three assessed responsibilities are:

1. Manufacturing cost estimation
2. Technical product configuration
3. Commercial quote control

The categories can overlap. A recommendation for several categories does not prove that each category requires a separate product.

## Step 1: Define the process being assessed

Assess one sufficiently coherent manufacturing quote process.

Before completing the questions, define:

- the product or project type;
- whether the process is standard, configurable, configure-to-order or engineer-to-order;
- how manufacturing cost is determined;
- how the technically valid solution is determined;
- how customer price, margin and approvals are determined;
- which systems currently participate.

Avoid combining materially different operating models into one answer set unless the result is intentionally meant to describe a shared future architecture.

## Step 2: Assess the twelve requirements

Rate every requirement as:

- Not required
- Helpful
- Essential

### Cost-estimation requirements

These determine whether expected manufacturing cost must be constructed from production resources, routings and realised outcomes.

1. Calculate material, labor, machine, tooling, setup, subcontracting and overhead cost.
2. Use routings, operation times, batch sizes, scrap, yield and setup assumptions.
3. Compare alternative materials, processes or estimate revisions.
4. Compare estimated cost with actual manufacturing cost.

### Product-configuration requirements

These determine whether the technically valid product or solution must be guided, constrained and preserved.

5. Enforce valid product options, dependencies and compatibility rules.
6. Use CAD, BOM or engineering-rule logic.
7. Guide users through configurable or engineer-to-order products.
8. Manage configuration revisions and technical validation.

### Commercial-quote-control requirements

These determine whether cost, configuration and customer context must be converted into governed commercial output.

9. Apply price lists, customer-specific pricing, currencies, discounts and margins.
10. Trigger approval from margin, discount, floor price, deal value or commercial risk.
11. Validate quote completeness and preserve an explainable decision trace.
12. Produce customer-ready quote output from approved data.

Complete all twelve. The Excel score formulas treat any answer other than Helpful or Essential—including a blank—as zero.

## Step 3: Calculate requirement intensity

Each answer value is multiplied by the question’s category weight.

The weighted total is divided by the maximum possible weighted total for that category and displayed on a scale from 0 to 100.

The result represents **requirement intensity**. It does not represent:

- vendor quality;
- software maturity;
- probability of success;
- market fit;
- implementation readiness.

## Step 4: Assign category roles

The workbook translates each score into:

### Intensity

- 0–39: Low requirement
- 40–64: Moderate requirement
- 65–100: High requirement

### Role

- 65 or higher: Core category
- 50–64: Supporting category, but only when exactly one other category is core
- 40–49: Requirement to validate
- below 40: No dedicated component indicated

A score can therefore be a Moderate requirement without becoming Supporting. The supporting role depends on the total number of core categories.

## Step 5: Determine software scope

The recommendation first uses the number of core categories.

- Two or more core categories → Combination of systems
- Exactly one core category → that core category becomes the recommendation
- No core categories → evaluate the remaining moderate requirements and the primary bottleneck

When no category is core:

- if every score is below 40, no dedicated component is indicated;
- if the bottleneck is Connecting all three decisions and at least two categories score 40 or higher, the result is Combination of systems;
- if the bottleneck names one category and that category scores 40 or higher, that category becomes the recommendation;
- otherwise, the highest score becomes the recommendation.

See [Scoring methodology](scoring-methodology.md) for tie behavior and the separate Primary system output.

## Step 6: Add process and system context

### Primary bottleneck

The primary bottleneck helps interpret a close or non-core result. It does not change the numeric scores.

Use it to identify the present decision constraint:

- cost;
- technical validity;
- customer price, margin and approval;
- connection across all three.

### Architecture preference

The workbook records whether:

- one integrated platform is preferred;
- connected specialist systems are acceptable;
- the clearest ownership model should be recommended without a platform preference.

This preference changes architecture wording for a Combination of systems. It does not change the underlying requirement result.

### Existing systems

Record systems that already cover part of the process.

The workbook uses individual Yes flags to generate:

- a core-category gap summary;
- adjacent-system notes.

Existing systems do not reduce a requirement score. A high requirement remains high even when a current system appears to cover it.

## Step 7: Translate scores into detailed capabilities

Use **Requirements matrix** after the assessment.

The matrix converts the twelve high-level questions into 36 detailed capabilities across the three assessed categories:

- 14 cost-estimating capabilities;
- 11 product-configuration capabilities;
- 11 commercial-quoting capabilities.

It adds seven adjacent-system capabilities, for a total of 43 rows.

For each capability:

1. confirm the inherited or directly entered need level;
2. record current coverage;
3. identify the current system;
4. review the calculated gap category;
5. confirm the primary and adjacent system;
6. assign business and technical ownership;
7. set priority;
8. attach evidence or an example;
9. document assumptions and exceptions.

## Step 8: Define process ownership

Use **Process ownership** to define the system responsible for each main decision.

| Stage | Decision |
| --- | --- |
| Estimate | What will it cost to make? |
| Configure | What technical solution is valid? |
| Price | What customer price and margin apply? |
| Approve | Does the commercial exception require review? |
| Release | Which approved data becomes customer-facing output? |

For each stage, distinguish:

- source ownership;
- calculation or rule ownership;
- approval ownership;
- output ownership;
- evidence retained at the handoff.

A system can provide source data without owning the final decision.

## Step 9: Validate adjacent-system boundaries

The tool treats these systems as adjacent:

- ERP/MRP
- MES
- CAD/PLM
- CRM
- Proposal/document software

They can remain authoritative for their own data and processes.

A recommended estimating, configuration or quoting component should not automatically replace them.

Validate:

- source data;
- target data;
- handoff timing;
- transformation or calculation logic;
- version or revision used;
- decision evidence retained;
- failure and exception handling.

## Step 10: Use scenarios correctly

Use the Scenario library to understand the scoring model.

Do not use a scenario as:

- an industry benchmark;
- a preselected target architecture;
- a reason to overwrite the actual answers;
- a vendor recommendation.

The worked scenarios show that similar manufacturing organisations can require different ownership patterns depending on their actual requirements.

## Step 11: Report within scope

When sharing a result, state:

- the process assessed;
- all twelve answers;
- the three scores;
- category intensities and roles;
- selected bottleneck;
- architecture preference;
- existing systems recorded;
- recommendation and primary-system wording;
- unresolved gaps and ownership decisions;
- that the result is requirement-based and not a vendor benchmark.

## Interpretation principle

Treat the recommendation as a starting architecture.

The final implementation decision requires validation of:

- product and cost data ownership;
- technical configuration ownership;
- pricing and margin logic;
- approval policy;
- quote output;
- integration boundaries;
- total implementation context.
