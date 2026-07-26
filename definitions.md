[Back to README](../README.md) · [Open the Excel workbook](../template/manufacturing-estimating-quoting-cpq-requirements-matrix.xlsx) · [Use the online decision tool](https://configure.win/resources/manufacturing-software-decision-tool)

# Definitions

Use these definitions consistently in the Decision tool, Requirements matrix, Process ownership worksheet and project documentation.

## Assessment terms

| Term | Definition |
| --- | --- |
| **Requirement** | A capability or decision responsibility that the manufacturing quote process may need. |
| **Not required** | The capability is not required for the assessed process. Numerical answer value: 0. |
| **Helpful** | The capability would add value but is not treated as essential. Numerical answer value: 1. |
| **Essential** | The capability is necessary for the assessed process. Numerical answer value: 2. |
| **Requirement score** | A category’s weighted answer total divided by its maximum possible weighted score, expressed from 0 to 100. |
| **Requirement intensity** | The score band Low, Moderate or High. |
| **Category role** | The role assigned from the score and number of core categories: Core, Supporting, Requirement to validate or No dedicated component indicated. |
| **Recommendation** | The software scope returned by the workbook from category roles, scores and permitted context logic. |
| **Primary bottleneck** | The current process constraint selected by the user. It does not change scores. |
| **Architecture preference** | The user’s preferred platform pattern. It changes architecture wording, not scores. |
| **Existing-system flag** | A Yes/No indication that a named system already covers part of the process. |
| **Primary system** | A separate output identifying the leading system responsibility after applying the workbook’s primary-system logic. |
| **Supporting system or systems** | Categories between 50 and 64 when exactly one category is core, or the core categories listed when the recommendation is a combination. |

## Intensity terms

| Score | Intensity |
| ---: | --- |
| 0–39 | Low requirement |
| 40–64 | Moderate requirement |
| 65–100 | High requirement |

## Category-role terms

| Role | Meaning |
| --- | --- |
| **Core category** | Score of 65 or higher. |
| **Supporting category** | Score of 50–64 when exactly one other category is core. |
| **Requirement to validate** | Score of 40–49 when the category is not core or supporting. |
| **No dedicated component indicated** | Score below 40. |

A category can score 50–64 and remain **Requirement to validate** when the workbook does not contain exactly one core category.

## Software-scope terms

| Term | Definition |
| --- | --- |
| **Manufacturing estimating software** | Software focused on expected manufacturing cost from production inputs and assumptions. |
| **CPQ/product configurator** | Software focused on guiding and validating a technically valid product or solution configuration. |
| **Manufacturing quoting software** | Software focused on commercial pricing, margin, approvals, validation and customer-ready quote release. |
| **Combination of systems** | A recommendation that two or more assessed decision layers require core ownership, or that the no-core context logic identifies a connected multi-category need. |
| **No dedicated component indicated** | The current scores do not reach the workbook’s validation threshold for a dedicated assessed component. |
| **Connected specialist systems** | Separate components connected through governed data and decision handoffs. |
| **Integrated platform** | One platform that may cover several assessed layers while preserving explicit ownership. |

See [Software-category definitions](software-category-definitions.md).

## Requirements-matrix terms

| Term | Definition |
| --- | --- |
| **Requirement ID** | Stable identifier such as EST-01, CFG-01, QUO-01 or ADJ-01. |
| **Requirement group** | Cost estimating, Product configuration, Commercial quoting or Adjacent system. |
| **Capability** | A specific functional responsibility represented by one matrix row. |
| **Need level** | Not required, Helpful or Essential. Core category rows inherit this from Decision tool; adjacent rows can be completed directly. |
| **Current coverage** | Not covered, Partially covered or Covered. |
| **Current system** | The system that currently provides some or all of the capability. |
| **Gap** | The difference between stated need and current coverage, classified by the workbook. |
| **Primary software category** | The category expected to own the capability. |
| **Adjacent system** | A system that may supply or receive data without owning the assessed decision. |
| **Business owner** | The business role accountable for the requirement or decision. |
| **Technical owner** | The technical role accountable for implementation or system behavior. |
| **Priority** | Low, Medium, High or Critical. |
| **Evidence or example** | A concrete quote, rule, drawing, calculation, handoff or other proof that clarifies the requirement. |

## Coverage values

- Not covered
- Partially covered
- Covered

## Priority values

- Low
- Medium
- High
- Critical

## Gap categories

The Definitions sheet lists:

- No gap
- Process gap
- Data gap
- Calculation gap
- Configuration gap
- Governance gap
- Integration gap
- Other

The current Requirements matrix formulas automatically return:

- No gap
- Calculation gap
- Configuration gap
- Governance gap
- Integration gap

The Process ownership worksheet automatically returns:

- No gap
- Process gap

Data gap and Other remain reference categories and are not automatically assigned by the current formulas.

## Process-ownership terms

| Term | Definition |
| --- | --- |
| **Stage** | Estimate, Configure, Price, Approve or Release. |
| **Core decision** | The principal question that must be resolved at that stage. |
| **Required inputs** | The data required to make the decision. |
| **Calculations or rules** | The logic used to produce or govern the decision. |
| **Recommended owner** | The owner generated from the Decision tool’s category role. |
| **Current owner** | The system or process that owns the decision today. |
| **Source system** | The authoritative origin of required data. |
| **Target system** | The system intended to receive data or own the future decision. |
| **Handoff method** | The way data or decision context moves between systems or teams. |
| **Decision evidence** | The retained inputs, calculations, validations, approvals or output that explain the decision. |
| **Process gap** | A nonblank Current owner that does not exactly match the Recommended owner text. |

## Adjacent-system terms

| System | Typical role in this workbook |
| --- | --- |
| **ERP/MRP** | Master data, inventory, planning, purchasing, orders and manufacturing-resource requirements |
| **MES** | Actual manufacturing execution and shop-floor outcomes |
| **CAD/PLM** | Technical design, engineering data, BOMs, revisions and product lifecycle information |
| **CRM** | Customer, opportunity and sales-pipeline context |
| **Proposal/document software** | Customer-facing presentation, delivery and e-signature-related workflows |

## Process-stage definitions

| Stage | Core decision |
| --- | --- |
| **Estimate** | What will it cost to make? |
| **Configure** | What technical solution is valid? |
| **Price** | What customer price and margin apply? |
| **Approve** | Does the commercial exception require review? |
| **Release** | Which approved data becomes customer-facing output? |

## Scenario terms

| Term | Definition |
| --- | --- |
| **Contract manufacturer** | Fictional scenario driven by detailed manufacturing-cost estimation, with limited product configuration and supporting commercial quoting. |
| **Configurable industrial-equipment manufacturer** | Fictional scenario requiring connected estimating, technical configuration and commercial quoting. |
| **Manufacturer of standard products** | Fictional scenario with stable product structures and cost, but core commercial pricing and approval requirements. |
| **Worked example** | The configurable industrial-equipment scenario presented as a consolidated illustrative result. |

## Related documentation

- [Methodology](methodology.md)
- [Scoring methodology](scoring-methodology.md)
- [Software-category definitions](software-category-definitions.md)
- [Process ownership guide](process-ownership-guide.md)
- [Limitations](limitations.md)
