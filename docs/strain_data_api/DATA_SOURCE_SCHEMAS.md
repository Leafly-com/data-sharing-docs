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
| `strain_slug` | `str` | | Unique name associated with a given strain |
| `strain_name` | `str` | | Presentation name associated with a given strain |
| `attribute_category` | `str` | | Category of strain attribute measured |
| `attribute_name` | `str` | | Name of the strain attribute measured |
| `attribute_value` | `str` | &check; | Value of the strain attribute measured |

> Note: The specific attributes that are included differs between tiers. See [here](STRAIN_ATTRIBUTE_DELINEATIONS.md "Strain attribute delineations") to find out which attributes are included in each tier and for attribute definitions.

**Data Source:** Info

| Column name | Data type | Is nullable? | Description |
| --- | --- | :---: | --- |
| `strain_slug` | `str` | | Unique name associated with a given strain |
| `strain_name` | `str` | | Presentation name associated with a given strain |
| `strain_page_url` | `str` | | URL to the given strain's page on Leafly.com |
| `strain_category` | `str` | &check; | One of the following designations: indica, sativa, hybrid |
| `strain description` | `str` | &check; | Text description used on the given strain's page on Leafly.com |
| `parent_strain_slugs` | `str` | &check; | JSON array of slugs of strains that are the putative biological parents of the given strain |
| `child_strain_slugs` | `str` | &check; | JSON array of slugs of strains that are the putative biological descendants of the given strain |
| `keywords` | `str` | &check; | JSON array of keywords extracted from the strain's Leafly description |

## Tier: Standard

**Data Source:** Reviews

| Column name | Data type | Is nullable? | Description |
| --- | --- | :---: | --- |
| `strain_slug` | `str` | | Unique name associated with a given strain |
| `strain_name` | `str` | | Presentation name associated with a given strain |
| `num_reviews` | `int` | | Number of reviews of the given strain|

## Tier: Pro

**Data Source:** Reviews

| Column name | Data type | Is nullable? | Description |
| --- | --- | :---: | --- |
| `strain_slug` | `str` | | Unique name associated with a given strain |
| `strain_name` | `str` | | Presentation name associated with a given strain |
| `user_id` | `str` | | Anonymized ID of the user who left the given review |
| `review_date` | `timestamp` | | UTC timestamp indicating when the review was created |
| `review_text` | `str` | &check; | Text of the review detailing the user's opinion of the strain |
| `review_rating` | `int` | | 0-5 rating. The higher rating, the more the user enjoyed the strain |
| `consumption_form` | `str` | &check; | The form in which the strain was consumed by the user (e.g. "flower", "concentrate") |
| `consumption_method` | `str` | &check; | The method by which the strain was consumed by the user (e.g. "smoke", "vaporize") |
