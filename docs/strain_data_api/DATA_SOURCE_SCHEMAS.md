# Data Source Schemas

Use this doc to determine the composition of each data source per subscription tier.

**Tiers:**
- Any (meaning all tiers receive these exports)
- Standard
- Pro

**Notes:**
- A strain's slug is unique whereas a strain's name is not necessarily unique

## Tier: Any

**Data Source:** Info

| Column name | Data type | Is nullable? | Description |
| --- | --- | :---: | --- |
| `strain_slug` | `varchar` | | Unique name associated with a given strain |
| `strain_name` | `varchar` | | Presentation name associated with a given strain |
| `strain_page_url` | `varchar` | | URL to the given strain's page on Leafly.com |
| `strain_category` | `varchar` | &check; | One of the following strain type designations: indica, sativa, hybrid |
| `strain description` | `varchar` | &check; | Text description used on the given strain's page on Leafly.com |
| `parent_strain_slugs` | `varchar` | &check; | JSON array of slugs of strains that are biological parents of the given strain |
| `child_strain_slugs` | `varchar` | &check; | JSON array of slugs of strains that are biological descendants of the given strain |

## Tier: Standard

 **Data Source:** Attributes

| Column name | Data type | Is nullable? | Description |
| --- | --- | :---: | --- |
| `strain_slug` | `varchar` | | Unique name associated with a given strain |
| `strain_name` | `varchar` | | Presentation name associated with a given strain |
| `attribute_name` | `varchar` | | Name of the strain attribute measured |
| `attribute_value` | `float` | &check; | Value of the strain attribute measured |
