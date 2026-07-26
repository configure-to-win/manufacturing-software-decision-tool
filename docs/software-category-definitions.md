[Back to README](../README.md) · [Open the Excel workbook](../template/manufacturing-estimating-quoting-cpq-requirements-matrix.xlsx) · [Use the online decision tool](https://configure.win/resources/manufacturing-software-decision-tool)

# Software-category definitions

The decision tool separates three assessed software responsibilities and five adjacent system roles.

The categories can overlap. The purpose is to clarify ownership, not to prove that every category must be implemented as a separate product.

## Manufacturing estimating software

### Core question

```text
What will the product, part or project cost to make?
```

### Definition

Software that calculates the expected manufacturing cost of a product, part or project using inputs such as:

- material;
- labor;
- machine time;
- setup;
- tooling;
- subcontracting;
- overhead.

### Requirements assessed

- manufacturing cost build-up;
- routings and production assumptions;
- alternative materials or processes;
- estimate revisions;
- estimated-versus-actual cost comparison.

### Detailed capability coverage in the matrix

- Material cost
- Labor cost
- Machine cost
- Setup cost
- Tooling
- Subcontracting
- Overhead allocation
- Scrap and yield
- Routings
- Cycle time
- Batch or lot size
- Estimate revisions
- Alternative-process comparison
- Estimated-versus-actual variance

### Boundary

Manufacturing estimating software determines expected cost.

It does not automatically own:

- technically valid product configuration;
- customer-specific commercial price;
- discount governance;
- approval routing;
- customer-ready quote output.

Manufacturing quoting software can use an estimated cost value, but it does not replace specialist estimating when detailed material, labor, machine, tooling, routing or overhead calculations are required.

## CPQ/product configurator

### Core question

```text
What technical product or solution configuration is valid?
```

### Definition

Software that guides and validates technically valid:

- products;
- options;
- dependencies;
- configurations;
- compatibility;
- engineering rules.

### Requirements assessed

- valid options and dependencies;
- compatibility rules;
- CAD, BOM or engineering-rule logic;
- guided selection;
- configurable products;
- engineer-to-order products;
- revisions;
- technical validation.

### Detailed capability coverage in the matrix

- Product options
- Option dependencies
- Compatibility rules
- Guided selection
- Configure-to-order
- Engineer-to-order
- CAD integration
- BOM generation or validation
- Engineering constraints
- Configuration revisions
- Technical validation

### Boundary

A product configurator determines technical validity.

It does not automatically own:

- detailed manufacturing cost;
- production execution;
- customer-specific price and margin;
- approval policy;
- final commercial quote control.

Some products can cover configuration and commercial quoting. The workbook still separates the underlying responsibilities so that ownership can be explicit.

## Manufacturing quoting software

### Core question

```text
What customer price and terms can be offered, approved and released?
```

### Definition

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

### Requirements assessed

- commercial pricing and margin;
- approval rules and governance;
- quote completeness;
- explainable decision trace;
- approved customer-ready output.

### Detailed capability coverage in the matrix

- Price lists
- Customer-specific pricing
- Multi-currency pricing
- Discount calculation
- Margin calculation
- Floor-price control
- Approval rules
- Approval matrix
- Quote validation
- Decision trace
- Customer-ready quote output

### Boundary

Manufacturing quoting software governs the commercial decision.

It can consume:

- estimated cost from estimating software;
- valid configuration from a configurator;
- customer context from CRM;
- source prices and master data from ERP/MRP;
- output services from proposal/document software.

It is not positioned by this tool as:

- CAD;
- BOM management;
- MRP;
- MES;
- specialist manufacturing cost-estimating software.

## Relationship between the assessed categories

| Responsibility | Main question | Typical result |
| --- | --- | --- |
| Estimating | What will it cost to make? | Expected manufacturing cost |
| Configuration | What technical solution is valid? | Validated technical configuration |
| Quoting | What price and terms can be offered and approved? | Controlled commercial quote |

A connected process can use:

```text
Estimated cost
→ Valid technical configuration
→ Commercial price and margin
→ Approval
→ Customer-ready release
```

The exact sequence and ownership depend on the assessed process.

## ERP/MRP

### Typical role

- master data;
- inventory;
- planning;
- purchasing;
- orders;
- manufacturing-resource requirements.

### Matrix examples

- material-cost source;
- routing or lot-size context;
- production planning;
- inventory;
- procurement;
- order management.

### Boundary

ERP/MRP can remain authoritative for operational and transactional data while another component owns estimating, technical configuration or commercial quote control.

## MES

### Typical role

- actual manufacturing execution;
- shop-floor outcomes;
- realised production data.

### Matrix examples

- machine and labor actuals;
- cycle time;
- scrap and yield;
- estimated-versus-actual comparison;
- actual production execution.

### Boundary

MES can provide actual outcomes without owning the expected estimate, technical configuration or commercial quote decision.

## CAD/PLM

### Typical role

- technical design;
- engineering data;
- BOMs;
- revisions;
- product lifecycle information.

### Matrix examples

- CAD integration;
- BOM generation or validation;
- engineering constraints;
- configuration revisions;
- technical validation.

### Boundary

CAD/PLM can own engineering master data while a configurator guides selection and a quoting system governs the commercial outcome.

## CRM

### Typical role

- customer information;
- opportunity context;
- sales pipeline.

### Matrix example

- opportunity management;
- customer-specific context used by quoting.

### Boundary

CRM can remain the customer and opportunity system of record without owning manufacturing cost, technical validity or complete commercial governance.

## Proposal/document software

### Typical role

- customer-facing documents;
- presentation;
- delivery;
- e-signature-related workflows.

### Matrix examples

- customer-ready quote output;
- e-signature.

### Boundary

Document software can render and deliver approved output. It does not necessarily own the calculations, validation, approvals or decision trace behind that output.

## Combination of systems

A Combination of systems is recommended when the model indicates multiple core decision layers, or when the no-core context logic identifies a connected multi-category need.

Possible implementation patterns include:

- one integrated platform where practical;
- connected specialist systems;
- a mixed architecture with adjacent authoritative systems.

The workbook does not decide how many products should be purchased.

## Configure to WIN scope

The published decision tool describes Configure to WIN as focused on commercial quote control:

- price lists;
- configurable calculations;
- margins;
- validation;
- approval rules;
- traceable quote decisions.

It is not positioned as CAD, BOM, MRP, MES or specialist manufacturing cost-estimating software.

## Boundary-validation questions

Before selecting software, confirm:

- Who owns product master data?
- Who owns cost values?
- Who owns the valid configuration?
- Who owns customer-specific pricing?
- Who owns margin calculations?
- Who owns approval policy?
- Who owns quote output?
- Which system stores the decision trace?

See [Process ownership guide](process-ownership-guide.md).
