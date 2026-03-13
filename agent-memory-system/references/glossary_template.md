# Project Glossary Template

This file documents key business terms and their corresponding code implementations.
Use this to ensure consistency between domain language and variable/function naming.

Note: The example entries in this template are generic. Adapt terms and code references to match your repository's actual entities, modules, and tables.

## Term Format

- **Term**: The business term (e.g., "Customer")
- **Definition**: What it means in the business context.
- **Code Usage**: How it is represented in the codebase (variable names, types, database tables).
- **Synonyms/Notes**: Other terms used or things to avoid.

## Examples

| Term | Definition | Code Usage | Synonyms/Notes |
| :--- | :--- | :--- | :--- |
| **Order** | A confirmed request for products by a customer. | `Order` (class), `orders` (table), `orderId` | NOT "Cart" (pre-checkout) |
| **SKU** | Stock Keeping Unit - unique identifier for a product variant. | `sku` (string field), `ProductVariant.sku` | Product Code |
| **Ledger** | The record of all financial transactions. | `GeneralLedger` (model), `gl_entries` (table) | Journal |
| **Invoice** | A bill sent to a customer for payment. | `Invoice` (entity), `billing.invoice` | NOT "Receipt" (proof of payment) |

## Adding New Terms

- Check if the term already exists or has a synonym.
- Add the term in alphabetical order.
- Ensure the "Code Usage" reflects the actual implementation.
