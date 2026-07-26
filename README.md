[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21601701.svg)](https://doi.org/10.5281/zenodo.21601701)
# Manufacturing Software Decision Tool — Excel Requirements Matrix

Assess whether a manufacturing quote process needs cost estimating, product configuration, commercial quote control or a connected combination of systems.

This workbook accompanies the [Manufacturing Software Decision Tool by Configure to WIN](https://configure.win/resources/manufacturing-software-decision-tool), where you can answer the same twelve requirements online and receive a requirement-based recommendation in your browser.

## Get the tool

- [Download the latest Excel release](../../releases/latest)
- [Open the Excel workbook](template/manufacturing-estimating-quoting-cpq-requirements-matrix.xlsx)
- [Use the online decision tool](https://configure.win/resources/manufacturing-software-decision-tool)
- [Read the decision methodology](docs/methodology.md)

## What this workbook assesses

The workbook helps manufacturing teams distinguish three related but different software responsibilities:

- **Manufacturing estimating software** — what will the product, part or project cost to make?
- **CPQ/product configurator** — what technical product or solution configuration is valid?
- **Manufacturing quoting software** — what customer price and terms can be offered, approved and released?

The categories can overlap. The workbook recommends process ownership from the requirements entered; it does not prove that every capability must be delivered by a separate product or that one specific software architecture is correct.

The assessment evaluates twelve requirements across three categories:

1. Cost estimation
2. Product configuration
3. Commercial quote control

It then calculates:

- an estimating requirement score;
- a configuration requirement score;
- a quoting requirement score;
- requirement intensity for each category;
- the role of each category in the recommendation;
- a recommended software scope;
- an architecture description;
- recommended ownership across estimate, configure, price, approve and release;
- an existing-system gap summary;
- adjacent-system notes.

The scores measure only the intensity of the requirements entered. They are not vendor ratings, software benchmarks, probability estimates or implementation guarantees.

## Workbook contents

| Sheet | Purpose |
| --- | --- |
| **Decision tool** | Repeats the twelve-question assessment in Excel, captures process context and existing-system flags, calculates category scores and returns a software-scope and ownership recommendation. |
| **Requirements matrix** | Converts the assessment into a detailed capability inventory covering estimating, configuration, commercial quoting and adjacent systems. It supports coverage, gap, ownership, priority, evidence and implementation notes. |
| **Process ownership** | Maps the decisions, inputs, calculations, rules, handoffs and evidence required from estimate through customer-ready release. |
| **Scenario library** | Demonstrates how the same scoring model produces different recommendations for a contract manufacturer, a configurable industrial-equipment manufacturer and a manufacturer of standard products. |
| **Worked example** | Shows a fictional configurable industrial-equipment assessment, its scores, recommendation, ownership model and adjacent-system notes. |
| **Definitions** | Documents software-category boundaries, scoring weights, thresholds, recommendation logic, adjacent-system roles, limitations, workbook information and official resources. |

## How to use the workbook

### Option 1: Complete the twelve-question assessment

Use the **Decision tool** when you want a structured first view of the software responsibilities required by your manufacturing quote process.

1. Select one answer for every requirement:
   - **Not required**
   - **Helpful**
   - **Essential**
2. Add the primary bottleneck.
3. Select the preferred architecture.
4. Record which systems already cover part of the process.
5. Review the requirement scores and category roles.
6. Review the recommended software scope, architecture and process ownership.
7. Use the **Requirements matrix** for detailed project planning.

The assessment should be completed from the requirements of the process, not from a preferred vendor or predetermined system architecture.

### Option 2: Build a detailed requirements and gap matrix

Use the **Requirements matrix** to translate the assessment into implementation detail.

For each capability, document:

- requirement ID;
- requirement group;
- capability;
- description;
- need level;
- current coverage;
- current system;
- gap;
- primary software category;
- adjacent system;
- business owner;
- technical owner;
- priority;
- evidence or example;
- notes.

The matrix includes detailed capabilities for:

- cost estimating;
- product configuration;
- commercial quoting;
- adjacent systems and processes.

The matrix is a planning aid. Need levels can be linked to the Decision tool or completed directly for adjacent-system capabilities.

### Option 3: Define process ownership

Use **Process ownership** to determine which system should own each decision from initial estimate through controlled release.

The worksheet covers five stages:

1. Estimate
2. Configure
3. Price
4. Approve
5. Release

For each stage, document:

- the core decision;
- required inputs;
- calculations or rules;
- recommended owner;
- current owner;
- source system;
- target system;
- handoff method;
- decision evidence;
- gap;
- priority;
- notes.

The recommended owner is linked to the assessment. Current and target ownership remain implementation decisions.

## The twelve assessment requirements

### Cost estimation

These requirements test whether manufacturing cost must be calculated from production resources and operating assumptions.

| No. | Requirement | Estimating weight |
| ---: | --- | ---: |
| 1 | Calculate material, labor, machine, tooling, setup, subcontracting and overhead cost | 3 |
| 2 | Use routings, operation times, batch sizes, scrap, yield and setup assumptions | 2 |
| 3 | Compare alternative materials, processes or estimate revisions | 1 |
| 4 | Compare estimated cost with actual manufacturing cost | 2 |

### Product configuration

These requirements test whether the technically valid solution must be guided, constrained or validated.

| No. | Requirement | Configuration weight |
| ---: | --- | ---: |
| 5 | Enforce valid product options, dependencies and compatibility rules | 3 |
| 6 | Use CAD, BOM or engineering-rule logic | 3 |
| 7 | Guide users through configurable or engineer-to-order products | 2 |
| 8 | Manage configuration revisions and technical validation | 1 |

### Commercial quote control

These requirements test whether cost and product context must be converted into controlled customer pricing, approvals and output.

| No. | Requirement | Quoting weight |
| ---: | --- | ---: |
| 9 | Apply price lists, customer-specific pricing, currencies, discounts and margins | 3 |
| 10 | Trigger approval from margin, discount, floor price, deal value or commercial risk | 3 |
| 11 | Validate quote completeness and preserve an explainable decision trace | 2 |
| 12 | Produce customer-ready quote output from approved data | 1 |

## Answer values and scoring

Each answer is converted to a numerical value:

| Answer | Value |
| --- | ---: |
| Not required | 0 |
| Helpful | 1 |
| Essential | 2 |

For each category:

```text
Category score
= Weighted answer total
÷ Maximum possible weighted score
× 100
```

The maximum weighted scores are:

| Category | Maximum weighted score |
| --- | ---: |
| Estimating | 16 |
| Configuration | 18 |
| Quoting | 18 |

Existing-system selections do not change the requirement scores. They change the architecture, gap and implementation wording.

## Requirement intensity and category role

### Requirement intensity

| Score | Intensity |
| ---: | --- |
| 0–39 | Low requirement |
| 40–64 | Moderate requirement |
| 65–100 | High requirement |

### Category role

- A score of **65 or higher** indicates a **Core category**.
- A category scoring **50–64** can become a **Supporting category** when only one other category is core.
- A score of **40–49** indicates a **Requirement to validate**.
- A score below **40** indicates **No dedicated component indicated**.

These labels describe the entered requirement pattern. They are not product-quality ratings.

## Recommendation logic

The workbook applies the following rules:

- **Two or more core categories** → **Combination of systems**
- **Exactly one core category** → that core category becomes the recommendation; a category at 50–64 can become supporting
- **No core category** → validate the highest requirement and, where permitted, use the primary bottleneck as a tie-breaker

The primary bottleneck is used only when:

- the top two scores differ by seven points or less; or
- no score reaches 65.

Architecture preference and existing-system flags influence the recommendation wording, gap analysis and implementation context. They do not alter the category scores.

## Context inputs

### Primary bottleneck

Select the issue that best represents the current process constraint:

- Determining what the product or project will cost to make
- Determining which product configuration is technically valid
- Determining the customer price, margin and approval path
- Connecting all three decisions

### Architecture preference

Select one:

- One integrated platform where practical
- Connected specialist systems are acceptable
- No preference — recommend the clearest ownership model

### Existing-system flags

Record whether the current environment includes:

- Estimating software
- ERP or MRP
- MES
- CAD or PLM
- Product configurator or CPQ
- CRM or quoting software
- Proposal or document software
- None of these

These selections help frame system gaps and ownership boundaries. They do not reduce or increase the calculated requirement intensity.

## Software-category definitions

### Manufacturing estimating software

Software that calculates the expected manufacturing cost of a product, part or project using inputs such as:

- material;
- labor;
- machine time;
- setup;
- tooling;
- subcontracting;
- overhead.

### CPQ/product configurator

Software that guides and validates technically valid:

- products;
- options;
- dependencies;
- configurations;
- compatibility;
- engineering rules.

### Manufacturing quoting software

Software that turns product, cost and customer context into a controlled commercial quote using:

- price lists;
- customer-specific pricing;
- currencies;
- discounts;
- margins;
- floor-price controls;
- approval rules and matrices;
- quote validation;
- decision trace;
- customer-ready quote output.

## Detailed requirements coverage

The **Requirements matrix** expands the twelve assessment questions into a more detailed capability inventory.

### Cost-estimating capabilities

The matrix includes:

- material cost;
- labor cost;
- machine cost;
- setup cost;
- tooling;
- subcontracting;
- overhead allocation;
- scrap and yield;
- routings;
- cycle time;
- batch or lot size;
- estimate revisions;
- alternative-process comparison;
- estimated-versus-actual variance.

### Product-configuration capabilities

The matrix includes:

- product options;
- option dependencies;
- compatibility rules;
- guided selection;
- configure-to-order;
- engineer-to-order;
- CAD integration;
- BOM generation or validation;
- engineering constraints;
- configuration revisions;
- technical validation.

### Commercial-quoting capabilities

The matrix includes:

- price lists;
- customer-specific pricing;
- multi-currency pricing;
- discount calculation;
- margin calculation;
- floor-price control;
- approval rules;
- approval matrix;
- quote validation;
- decision trace;
- customer-ready quote output.

## Adjacent systems

The workbook treats several systems as adjacent to the estimating, configuration and quoting decision layers.

| System | Typical role |
| --- | --- |
| **ERP/MRP** | Master data, inventory, planning, purchasing, orders and manufacturing-resource requirements |
| **MES** | Actual manufacturing execution and shop-floor outcomes |
| **CAD/PLM** | Technical design, engineering data, BOMs, revisions and product lifecycle information |
| **CRM** | Customer, opportunity and sales-pipeline information |
| **Proposal/document software** | Customer-facing documents, presentation, delivery and e-signature-related workflows |

The Requirements matrix also includes adjacent capabilities for:

- opportunity management;
- production planning;
- inventory;
- actual production execution;
- e-signature;
- procurement;
- order management.

A recommendation for estimating, configuration or quoting software does not automatically mean these adjacent systems should be replaced.

The implementation must define:

- source data;
- target data;
- handoff timing;
- decision evidence retained at each boundary.

## Process ownership

The workbook separates the manufacturing quote process into five decisions.

| Stage | Core decision | Typical owner indicated by the model |
| --- | --- | --- |
| **Estimate** | What will it cost to make? | Manufacturing estimating software when estimating is required |
| **Configure** | What technical solution is valid? | CPQ/product configurator when configuration is required |
| **Price** | What customer price and margin apply? | Manufacturing quoting software when commercial quoting is required |
| **Approve** | Does the commercial exception require review? | Manufacturing quoting software when commercial governance is required |
| **Release** | Which approved data becomes customer-facing output? | Manufacturing quoting or document system |

Use the Process ownership worksheet to validate:

- who owns product master data;
- who owns cost values;
- who owns the valid configuration;
- who owns customer-specific pricing;
- who owns margin calculations;
- who owns approval policy;
- who owns quote output;
- which system stores the decision trace.

## Scenario library

The workbook includes three fictional scenarios.

### Contract manufacturer

Customer drawings drive material, labor, machine, setup and subcontracting estimates. Technical product configuration is limited, while margin and approval remain relevant.

Illustrative result:

- Estimating: 93.75 — Core category
- Configuration: 0 — No dedicated component indicated
- Quoting: 50 — Supporting category
- Recommendation: **Manufacturing estimating software**
- Architecture: **Estimating-led with commercial quoting support**

### Configurable industrial-equipment manufacturer

Technical options, engineering rules, BOM, manufacturing cost, customer pricing and approvals must remain connected.

Illustrative result:

- Estimating: 81.25 — Core category
- Configuration: 100 — Core category
- Quoting: 100 — Core category
- Recommendation: **Combination of systems**
- Architecture: **Estimating + configurator + quoting**

### Manufacturer of standard products

Product structures and costs are stable, but customer-specific pricing, discounts, currencies, margins and approvals are complex.

Illustrative result:

- Estimating: 0 — No dedicated component indicated
- Configuration: 0 — No dedicated component indicated
- Quoting: 100 — Core category
- Recommendation: **Manufacturing quoting software**
- Architecture: **Quoting-led with adjacent ERP/MRP and CRM**

The scenarios demonstrate the calculation model only. They are not vendor recommendations, market benchmarks or universal implementation patterns.

## Worked example

The **Worked example** uses the configurable industrial-equipment scenario.

Its fictional scores are:

| Category | Score | Intensity | Role |
| --- | ---: | --- | --- |
| Estimating | 81.25 | High requirement | Core category |
| Configuration | 100 | High requirement | Core category |
| Quoting | 100 | High requirement | Core category |

The resulting recommendation is:

```text
Combination of systems
```

The illustrative architecture is:

```text
Manufacturing estimating software
→ CPQ/product configurator
→ Manufacturing quoting software
→ Manufacturing quoting software
→ Manufacturing quoting or document system
```

The example preserves adjacent ownership:

- ERP/MRP may own production planning and inventory.
- CAD/PLM may own engineering master data and BOM control.
- CRM may own customer and opportunity data.

This example is fictional and is not a benchmark, vendor recommendation, advice or implementation guarantee.

## Assessment guidance

For consistent results:

- **Answer from process requirements.** Do not select answers to justify a preferred product.
- **Complete all twelve requirements.** An incomplete assessment does not support the final recommendation.
- **Use the category boundaries consistently.** Estimating, technical configuration and commercial quote control answer different questions.
- **Keep adjacent-system ownership visible.** ERP/MRP, MES, CAD/PLM, CRM and document systems may remain authoritative.
- **Separate requirement intensity from current coverage.** Existing systems do not change the scores.
- **Validate system boundaries.** Define who owns each source value, calculation, rule, approval and output.
- **Record evidence.** Use the Requirements matrix to add examples, ownership, gaps, priorities and implementation notes.
- **Treat the result as a starting architecture.** Validate the recommendation before selecting software.

## Limitations and disclaimer

This workbook is a practical assessment, requirements-planning and process-ownership tool. It does **not** provide:

- a vendor ranking;
- a market benchmark;
- a product comparison;
- an implementation guarantee;
- a total-cost-of-ownership analysis;
- a measure of product maturity;
- proof that a particular architecture is correct;
- proof that each category requires a separate software product;
- legal, financial, engineering, procurement or implementation advice.

The scores measure only the intensity of the requirements entered. They do not compare vendors, implementation quality, industry fit or software performance.

The user remains responsible for:

- the accuracy of the selected answers;
- the interpretation of category boundaries;
- validation of current and target ownership;
- assessment of integrations and data handoffs;
- evaluation of vendors and products;
- final architecture and implementation decisions.

## License

This repository is licensed under the terms described in [LICENSE.md](LICENSE.md).

When reusing or adapting the workbook or documentation, follow the attribution and modification requirements stated in that file.

## Citation

Please cite the archived release using its Zenodo DOI:

https://doi.org/10.5281/zenodo.21601701

## About Configure to WIN

Configure to WIN develops tools and software for B2B quote control, pricing governance, commercial calculation and approval management.

Learn more at [Configure to WIN](https://configure.win/).
