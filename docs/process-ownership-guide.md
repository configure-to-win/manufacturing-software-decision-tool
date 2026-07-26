[Back to README](../README.md) · [Open the Excel workbook](../template/manufacturing-estimating-quoting-cpq-requirements-matrix.xlsx) · [Use the online decision tool](https://configure.win/resources/manufacturing-software-decision-tool)

# Process ownership guide

Use the **Process ownership** worksheet to define which system owns each decision from expected manufacturing cost through customer-ready release.

Recommended ownership is linked to the Decision tool. Current and target ownership remain implementation decisions.

## The five stages

| Stage | Core decision | Required inputs | Calculations or rules |
| --- | --- | --- | --- |
| **Estimate** | What will it cost to make? | Material, labor, machine, setup, tooling, subcontracting and overhead | Cost model, routings, batch, scrap, yield and estimate assumptions |
| **Configure** | What technical solution is valid? | Product options, engineering data, CAD/BOM context and constraints | Dependencies, compatibility, engineering rules and technical validation |
| **Price** | What customer price and margin apply? | Cost, price lists, customer terms, currency and commercial conditions | Price, discount, floor price and margin calculations |
| **Approve** | Does the commercial exception require review? | Calculated commercial outcome, approval thresholds and risk context | Approval rules, matrix, routing and decision logging |
| **Release** | Which approved data becomes customer-facing output? | Approved configuration, price, terms and quote data | Final validation, document generation and controlled release |

## Worksheet columns

### Recommended owner

Generated from the Decision tool’s category role.

#### Estimate

| Estimating role | Recommended owner |
| --- | --- |
| Core category | Manufacturing estimating software |
| Supporting category | Manufacturing estimating software (supporting) |
| Requirement to validate | Ownership to validate |
| No dedicated component indicated | No dedicated component indicated |

#### Configure

| Configuration role | Recommended owner |
| --- | --- |
| Core category | CPQ/product configurator |
| Supporting category | CPQ/product configurator (supporting) |
| Requirement to validate | Ownership to validate |
| No dedicated component indicated | No dedicated component indicated |

#### Price and Approve

| Quoting role | Recommended owner |
| --- | --- |
| Core category | Manufacturing quoting software |
| Supporting category | Manufacturing quoting software (supporting) |
| Requirement to validate | Ownership to validate |
| No dedicated component indicated | No dedicated component indicated |

#### Release

| Quoting role | Recommended owner |
| --- | --- |
| Core or Supporting | Manufacturing quoting or document system |
| Requirement to validate | Release ownership to validate |
| No dedicated component indicated | Document/proposal system or existing process |

### Current owner

Record the system or process that owns the decision today.

Use one sufficiently precise name. The Gap formula compares this text with Recommended owner.

### Source system

Record the authoritative source of the required input.

Examples already represented elsewhere in the workbook include:

- ERP/MRP
- MES
- CAD/PLM
- CRM
- Estimating software
- Product configurator or CPQ
- Quoting software
- Proposal/document software

Source ownership does not necessarily equal decision ownership.

### Target system

Record the intended future owner or recipient.

Use this field to describe the proposed boundary rather than overwriting the current-state record.

### Handoff method

Document how data and decision context move between systems or teams.

The workbook does not prescribe a technical method. Record the method selected for the project.

At minimum, define:

- source;
- target;
- timing;
- values transferred;
- revision or version;
- error or exception behavior.

### Decision evidence

Record what must be retained to explain the stage outcome.

Examples derived from the workbook model include:

- estimate inputs and assumptions;
- routing and production assumptions;
- configuration options and rules;
- technical validation;
- cost and price sources;
- margin and floor-price calculations;
- approval conditions and decisions;
- approved quote output;
- decision trace.

### Gap

The formula applies:

```text
If Current owner is blank:
    blank

Else if Current owner exactly equals Recommended owner:
    No gap

Else:
    Process gap
```

This is exact text matching.

A Current owner of:

```text
Manufacturing quoting software
```

does not equal:

```text
Manufacturing quoting software (supporting)
```

Use Notes to explain a valid existing owner that differs only in wording.

### Priority

Use:

- Low
- Medium
- High
- Critical

Set priority from business need, risk and implementation context. The worksheet does not calculate priority automatically.

### Notes

Use Notes for:

- exceptions;
- temporary ownership;
- manual controls;
- unresolved system boundaries;
- planned migration;
- evidence-location details;
- reasons a calculated Process gap is acceptable.

## Recommended process flow

The worksheet links its five-stage flow to the Recommended owner cells:

```text
Estimate
→ Configure
→ Price
→ Approve
→ Release
```

The displayed owner at each stage changes when Decision tool category roles change.

This is an ownership flow, not proof that every stage requires a separate application or integration.

## How to complete the worksheet

### Step 1: Complete Decision tool

Do not plan ownership from incomplete scores. Blank answers are treated as zero.

### Step 2: Review recommended ownership

Check whether the role labels reflect the assessed requirements:

- Core
- Supporting
- Validate
- No dedicated component

### Step 3: Document current ownership

Record the current system or process for every stage.

Include manual or spreadsheet-based ownership where that is the actual current state.

### Step 4: Identify source systems

For each decision, identify the authoritative data sources.

Examples:

- Estimate may use ERP/MRP and MES inputs.
- Configure may use CAD/PLM and engineering data.
- Price may use cost, price lists, customer and currency context.
- Approve may use calculated commercial outcomes and policy.
- Release may use approved configuration, price and terms.

### Step 5: Define the target boundary

Record the future owner and any source-to-target handoffs.

Do not use one system name as a substitute for defining:

- data ownership;
- calculation ownership;
- rule ownership;
- approval ownership;
- output ownership.

### Step 6: Define evidence

For each stage, state what must be retained to reproduce or explain the decision.

### Step 7: Review calculated gaps

Treat Process gap as a prompt for analysis.

It can indicate:

- a genuine ownership change;
- a wording difference;
- a supporting-role suffix;
- an intentional current-state exception.

### Step 8: Prioritise and document

Set priority and add Notes.

## System boundaries to validate

The worksheet explicitly asks:

1. Who owns product master data?
2. Who owns cost values?
3. Who owns the valid configuration?
4. Who owns customer-specific pricing?
5. Who owns margin calculations?
6. Who owns approval policy?
7. Who owns quote output?
8. Which system stores the decision trace?

Answer all eight before finalising a target architecture.

## Adjacent ownership

The decision model allows:

- ERP/MRP to remain authoritative for planning, inventory, procurement and orders;
- MES to remain authoritative for actual execution;
- CAD/PLM to remain authoritative for engineering and BOM data;
- CRM to remain authoritative for customer and opportunity context;
- Proposal/document software to remain responsible for presentation, delivery or e-signature.

The target architecture should define how those systems interact with the assessed decision layers.

## Reporting the ownership model

When sharing the completed worksheet, include:

- assessment scores and roles;
- current owner;
- recommended owner;
- target owner;
- source system;
- handoff;
- evidence;
- calculated gap;
- priority;
- unresolved boundary questions.

## Related documentation

- [Methodology](methodology.md)
- [Scoring methodology](scoring-methodology.md)
- [Software-category definitions](software-category-definitions.md)
- [Limitations](limitations.md)
