# Data Source Schemas

Use this doc to determine the composition of each data source per subscription tier.

**Tiers:**
- [Any](#tier-any) (meaning all tiers receive these exports)
- [Standard](#tier-standard)
- [Pro](#tier-pro)

**Notes:**
- A strain's slug is unique whereas a strain's name is not necessarily unique
- Review exports use Leafly strain review data that is publicly available, moderator-approved, and not deleted

## Tier: Any

**Data Source:** Attributes

| Column name | Data type | Is nullable? | Description |
| --- | --- | :---: | --- |
| `strain_slug` | `varchar` | | Unique name associated with a given strain |
| `strain_name` | `varchar` | | Presentation name associated with a given strain |
| `attribute_type` | `varchar` | | Type/category of strain attribute measured |
| `attribute_name` | `varchar` | | Name of the strain attribute measured |
| `attribute_value` | `varchar` | &check; | Value of the strain attribute measured |

> See [here](STRAIN_ATTRIBUTE_DEFINTIONS.md "Strain attribute definitions") for definitions of strain attributes.

**Data Source:** Info

| Column name | Data type | Is nullable? | Description |
| --- | --- | :---: | --- |
| `strain_slug` | `varchar` | | Unique name associated with a given strain |
| `strain_name` | `varchar` | | Presentation name associated with a given strain |
| `strain_page_url` | `varchar` | | URL to the given strain's page on Leafly.com |
| `strain_category` | `varchar` | &check; | One of the following designations: indica, sativa, hybrid |
| `strain description` | `varchar` | &check; | Text description used on the given strain's page on Leafly.com |
| `parent_strain_slugs` | `varchar` | &check; | JSON array of slugs of strains that are the putative biological parents of the given strain |
| `child_strain_slugs` | `varchar` | &check; | JSON array of slugs of strains that are the putative biological descendants of the given strain |
| `keywords` | `varchar` | &check; | JSON array of keywords extracted from the strain's Leafly description |

## Tier: Standard

**Data Source:** Reviews

| Column name | Data type | Is nullable? | Description |
| --- | --- | :---: | --- |
| `strain_slug` | `varchar` | | Unique name associated with a given strain |
| `strain_name` | `varchar` | | Presentation name associated with a given strain |
| `num_reviews` | `integer` | | Number of reviews of the given strain|

## Tier: Pro

**Data Source:** Reviews

| Column name | Data type | Is nullable? | Description |
| --- | --- | :---: | --- |
| `strain_slug` | `varchar` | | Unique name associated with a given strain |
| `strain_name` | `varchar` | | Presentation name associated with a given strain |
| `user_id` | `varchar` | | Anonymized ID of the user who left the given review |
| `review_date` | `timestamp` | | UTC timestamp indicating when the review was created |
| `review_text` | `varchar` | &check; | Text of the review detailing the user's opinion of the strain |
| `review_rating` | `integer` | | 0-5 rating. The higher rating, the more the user enjoyed the strain |
| `consumption_form` | `varchar` | &check; | The form in which the strain was consumed by the user (e.g. "flower", "concentrate") |
| `consumption_method` | `varchar` | &check; | The method by which the strain was consumed by the user (e.g. "smoke", "vaporize") |
