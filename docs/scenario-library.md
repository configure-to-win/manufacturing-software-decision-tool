[Back to README](../README.md) · [Open the Excel workbook](../template/manufacturing-estimating-quoting-cpq-requirements-matrix.xlsx) · [Use the online decision tool](https://configure.win/resources/manufacturing-software-decision-tool)

# Scenario library

The workbook contains three fictional scenarios that demonstrate how the same scoring model produces different software-scope and ownership results.

The scenarios are not customer data, market benchmarks, product recommendations or implementation advice.

## Scenario 1 — Contract manufacturer

### Situation

Customer drawings drive material, labor, machine, setup and subcontracting estimates. Technical product configuration is limited, but margin and approval remain relevant.

### Answers

| No. | Requirement | Answer |
| ---: | --- | --- |
| 1 | Calculate material, labor, machine, tooling, setup, subcontracting and overhead cost | Essential |
| 2 | Use routings, operation times, batch sizes, scrap, yield and setup assumptions | Essential |
| 3 | Compare alternative materials, processes or estimate revisions | Helpful |
| 4 | Compare estimated cost with actual manufacturing cost | Essential |
| 5 | Enforce valid product options, dependencies and compatibility rules | Not required |
| 6 | Use CAD, BOM or engineering-rule logic | Not required |
| 7 | Guide users through configurable or engineer-to-order products | Not required |
| 8 | Manage configuration revisions and technical validation | Not required |
| 9 | Apply price lists, customer-specific pricing, currencies, discounts and margins | Helpful |
| 10 | Trigger approval from margin, discount, floor price, deal value or commercial risk | Helpful |
| 11 | Validate quote completeness and preserve an explainable decision trace | Helpful |
| 12 | Produce customer-ready quote output from approved data | Helpful |

### Result

| Category | Score | Intensity | Role |
| --- | ---: | --- | --- |
| Estimating | 93.75 | High requirement | Core category |
| Configuration | 0 | Low requirement | No dedicated component indicated |
| Quoting | 50 | Moderate requirement | Supporting category |

### Recommendation

```text
Manufacturing estimating software
```

### Architecture

```text
Estimating-led with commercial quoting support
```

### Ownership

| Stage | Owner |
| --- | --- |
| Estimate | Manufacturing estimating software |
| Configure | No dedicated component indicated |
| Price | Manufacturing quoting software (supporting) |
| Approve | Manufacturing quoting software (supporting) |
| Release | Manufacturing quoting or document system (supporting) |

### Scenario note

Commercial quoting support may be useful for pricing, margin and approval.

## Scenario 2 — Configurable industrial-equipment manufacturer

### Situation

Technical options, engineering rules, BOM, manufacturing cost, customer pricing and approvals must remain connected.

### Answers

| No. | Requirement | Answer |
| ---: | --- | --- |
| 1 | Calculate material, labor, machine, tooling, setup, subcontracting and overhead cost | Essential |
| 2 | Use routings, operation times, batch sizes, scrap, yield and setup assumptions | Essential |
| 3 | Compare alternative materials, processes or estimate revisions | Helpful |
| 4 | Compare estimated cost with actual manufacturing cost | Helpful |
| 5 | Enforce valid product options, dependencies and compatibility rules | Essential |
| 6 | Use CAD, BOM or engineering-rule logic | Essential |
| 7 | Guide users through configurable or engineer-to-order products | Essential |
| 8 | Manage configuration revisions and technical validation | Essential |
| 9 | Apply price lists, customer-specific pricing, currencies, discounts and margins | Essential |
| 10 | Trigger approval from margin, discount, floor price, deal value or commercial risk | Essential |
| 11 | Validate quote completeness and preserve an explainable decision trace | Essential |
| 12 | Produce customer-ready quote output from approved data | Essential |

### Result

| Category | Score | Intensity | Role |
| --- | ---: | --- | --- |
| Estimating | 81.25 | High requirement | Core category |
| Configuration | 100 | High requirement | Core category |
| Quoting | 100 | High requirement | Core category |

### Recommendation

```text
Combination of systems
```

### Architecture

```text
Estimating + configurator + quoting
```

### Ownership

| Stage | Owner |
| --- | --- |
| Estimate | Manufacturing estimating software |
| Configure | CPQ/product configurator |
| Price | Manufacturing quoting software |
| Approve | Manufacturing quoting software |
| Release | Manufacturing quoting or document system |

### Scenario note

ERP/MRP and CAD/PLM remain important adjacent systems for production, inventory, engineering data and BOM control.

### Worked-example relationship

The workbook’s **Worked example** uses this scenario and presents the same:

- 81.25 estimating score;
- 100 configuration score;
- 100 quoting score;
- Combination of systems recommendation;
- five-stage ownership flow.

It also notes that CRM may own customer and opportunity data.

## Scenario 3 — Manufacturer of standard products

### Situation

Product structures and costs are stable, but customer-specific pricing, discounts, currencies, margins and approvals are complex.

### Answers

| No. | Requirement | Answer |
| ---: | --- | --- |
| 1 | Calculate material, labor, machine, tooling, setup, subcontracting and overhead cost | Not required |
| 2 | Use routings, operation times, batch sizes, scrap, yield and setup assumptions | Not required |
| 3 | Compare alternative materials, processes or estimate revisions | Not required |
| 4 | Compare estimated cost with actual manufacturing cost | Not required |
| 5 | Enforce valid product options, dependencies and compatibility rules | Not required |
| 6 | Use CAD, BOM or engineering-rule logic | Not required |
| 7 | Guide users through configurable or engineer-to-order products | Not required |
| 8 | Manage configuration revisions and technical validation | Not required |
| 9 | Apply price lists, customer-specific pricing, currencies, discounts and margins | Essential |
| 10 | Trigger approval from margin, discount, floor price, deal value or commercial risk | Essential |
| 11 | Validate quote completeness and preserve an explainable decision trace | Essential |
| 12 | Produce customer-ready quote output from approved data | Essential |

### Result

| Category | Score | Intensity | Role |
| --- | ---: | --- | --- |
| Estimating | 0 | Low requirement | No dedicated component indicated |
| Configuration | 0 | Low requirement | No dedicated component indicated |
| Quoting | 100 | High requirement | Core category |

### Recommendation

```text
Manufacturing quoting software
```

### Architecture

```text
Quoting-led with adjacent ERP/MRP and CRM
```

### Ownership

| Stage | Owner |
| --- | --- |
| Estimate | No dedicated component indicated |
| Configure | No dedicated component indicated |
| Price | Manufacturing quoting software |
| Approve | Manufacturing quoting software |
| Release | Manufacturing quoting or document system |

### Scenario note

ERP/MRP and CRM may remain adjacent owners of product, cost, customer and opportunity data.

## Cross-scenario comparison

| Scenario | Estimating | Configuration | Quoting | Recommendation |
| --- | ---: | ---: | ---: | --- |
| Contract manufacturer | 93.75 | 0 | 50 | Manufacturing estimating software |
| Configurable industrial equipment | 81.25 | 100 | 100 | Combination of systems |
| Standard products | 0 | 0 | 100 | Manufacturing quoting software |

## What the scenarios demonstrate

### Similar processes can require different ownership

Manufacturing is not one software pattern.

The result depends on whether the process must:

- construct expected manufacturing cost;
- validate technical configuration;
- control commercial price, margin and approvals.

### Supporting does not mean absent

In the contract-manufacturer scenario, Quoting scores 50 and becomes Supporting because Estimating is the only core category.

### Stable cost and structure can shift the core to quoting

In the standard-products scenario, Estimating and Configuration are not required, while Quoting is core.

### Multiple core categories produce a combination

In the configurable-equipment scenario, all three layers are core, so the result is Combination of systems.

## Scenario-model boundaries

The Scenario library uses the same score, intensity and category-role rules as Decision tool.

It does not include:

- a selected primary bottleneck;
- architecture preference input;
- existing-system Yes/No flags;
- the Decision tool’s detailed gap-summary wording.

The scenarios are intended to explain the score model, not to represent every context branch.

## How to use the scenarios

Use them to:

- explain the category boundaries;
- test understanding of the scoring method;
- compare ownership patterns;
- facilitate a project-team discussion.

Do not:

- choose the closest scenario and copy its answers;
- treat a scenario score as a benchmark;
- treat its architecture as a vendor recommendation;
- assume the same pattern applies to every company in that manufacturing segment.

## Related documentation

- [Scoring methodology](scoring-methodology.md)
- [Software-category definitions](software-category-definitions.md)
- [Process ownership guide](process-ownership-guide.md)
- [Limitations](limitations.md)
