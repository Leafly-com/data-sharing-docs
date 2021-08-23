# Strain Attribute Definitions

This doc provides a definition for each distinct strain attribute.

**Generic attribute type definitions**:

Unless otherwise specified, definitions for attributes of the following attribute types are the same.

- `condition_count`: Count of strain reviews where the strain is identified as helping with the given condition
- `condition_score`: Z-score of weighted rating (see [here](#weighted-rating-formula) for definition) using the count of strain reviews where the strain is identified as helping with the given condition
- `effect_count`: Count of strain reviews where the strain is identified as producing the given effect
- `effect_score`: Z-score of weighted rating (see [here](#weighted-rating-formula) for definition) using the count of strain reviews where the strain is identified as producing the given effect
- `flavor_count`: Count of strain reviews where the strain is identified as having the given flavor
- `flavor_score`: Z-score of weighted rating (see [here](#weighted-rating-formula) for definition) using the count of strain reviews where the strain is identified as having the given flavor
- `negative_count`: Count of strain reviews where the strain is identified as producing the given negative effect
- `negative_score`: Z-score of weighted rating (see [here](#weighted-rating-formula) for definition) using the count of strain reviews where the strain is identified as producing the given negative effect
- `symptom_count`: Count of strain reviews where the strain is identified as producing the given symptom
- `symptom_score`: Z-score of weighted rating (see [here](#weighted-rating-formula) for definition) using the count of strain reviews where the strain is identified as producing the given symptom

**Notes**:
- Any `*_count` or `*_score` type attribute is sourced from Leafly strain reviews that are publicly available, moderator-approved, and not deleted
- Any mention of "unique pageviews" refers to data from Google Analytics

| Type | Name | Standard tier | Pro tier | Definition |
| --- | --- | :---: | :---: | --- |
| `analytics` | `is_trending` |  | &check; | Boolean value indicating whether the given strain is trending according to unique pageview counts/growth (see [here](#what-does-is_trending-mean) for definition) |
| `analytics` | `percent_change` |  | &check; | Year-over-year percent change in the percentage of unique strain pageviews attributed to the given strain |
| `analytics` | `pop_rank` |  | &check; | Rank according to the count of unique pageviews attributed to the given strain for two consecutive years. The higher the count of unique pageviews, the lower the rank. |
| `analytics` | `unique_pageviews_y1` |  | &check; |  |
| `analytics` | `unique_pageviews_y2` |  | &check; |  |
| `cannabinoid` | `cbc_percentile_50` | &check; | &check; | 50% quantile of CBC measurements |
| `cannabinoid` | `cbd_percentile_25` |  | &check; | 25% quantile of CBD measurements |
| `cannabinoid` | `cbd_percentile_50` | &check; | &check; | 50% quantile of CBD measurements |
| `cannabinoid` | `cbd_percentile_75` |  | &check; | 75% quantile of CBD measurements |
| `cannabinoid` | `cbd_potency_score` |  | &check; | Median CBD measurement converted to a Z-score and binned |
| `cannabinoid` | `cbg_percentile_50` | &check; | &check; | 50% quantile of CBG measurements |
| `cannabinoid` | `thc_cbd_chemotype` |  | &check; | The mode of chemotypes. See [here](#how-is-the-chemotype-of-a-sample-determined) for details on how chemotype is determined. |
| `cannabinoid` | `thc_percentile_25` |  | &check; | 25% quantile of THC measurements |
| `cannabinoid` | `thc_percentile_50` | &check; | &check; | 50% quantile of THC measurements |
| `cannabinoid` | `thc_percentile_75` |  | &check; | 75% quantile of THC measurements |
| `cannabinoid` | `thc_potency_score` |  | &check; | Median THC measurement converted to a Z-score and binned |
| `cannabinoid` | `thcv_percentile_50` | &check; | &check; | 50% quantile of THCV measurements |
| `condition_count` | `add_adhd` |  | &check; | Condition: "ADD/ADHD" |
| `condition_count` | `alzheimers` |  | &check; | Condition: "Alzheimer's" |
| `condition_count` | `anorexia` |  | &check; | Condition: "Anorexia" |
| `condition_count` | `anxiety` |  | &check; | Condition: "Anxiety" |
| `condition_count` | `arthritis` |  | &check; | Condition: "Arthritis" |
| `condition_count` | `asthma` |  | &check; | Condition: "Asthma" |
| `condition_count` | `bipolar_disorder` |  | &check; | Condition: "Bipolar Disorder" |
| `condition_count` | `cachexia` |  | &check; | Condition: "Cachexia" |
| `condition_count` | `cancer` |  | &check; | Condition: "Cancer" |
| `condition_count` | `crohns_disease` |  | &check; | Condition: "Crohn's Disease" |
| `condition_count` | `epilepsy` |  | &check; | Condition: "Epilepsy" |
| `condition_count` | `fibromyalgia` |  | &check; | Condition: "Fibromyalgia" |
| `condition_count` | `gastrointestinal_disorder` |  | &check; | Condition: "Gastrointestinal Disorder" |
| `condition_count` | `glaucoma` |  | &check; | Condition: "Glaucoma" |
| `condition_count` | `hiv_aids` |  | &check; | Condition: "HIV/AIDS" |
| `condition_count` | `hypertension` |  | &check; | Condition: "Hypertension" |
| `condition_count` | `migraines` |  | &check; | Condition: "Migraines" |
| `condition_count` | `multiple_sclerosis` |  | &check; | Condition: "Multiple Sclerosis" |
| `condition_count` | `muscular_dystrophy` |  | &check; | Condition: "Muscular Dystrophy" |
| `condition_count` | `parkinsons` |  | &check; | Condition: "Parkinson's" |
| `condition_count` | `phantom_limb_pain` |  | &check; | Condition: "Phantom Limb Pain" |
| `condition_count` | `pms` |  | &check; | Condition: "PMS" |
| `condition_count` | `ptsd` |  | &check; | Condition: "PTSD" |
| `condition_count` | `spinal_cord_injury` |  | &check; | Condition: "Spinal Cord Injury" |
| `condition_count` | `tinnitus` |  | &check; | Condition: "Tinnitus" |
| `condition_count` | `tourettes_syndrome` |  | &check; | Condition: "Tourette's Syndrome" |
| `condition_score` | `add_adhd` |  | &check; | Condition: "ADD/ADHD" |
| `condition_score` | `alzheimers` |  | &check; | Condition: "Alzheimer's" |
| `condition_score` | `anorexia` |  | &check; | Condition: "Anorexia" |
| `condition_score` | `anxiety` |  | &check; | Condition: "Anxiety" |
| `condition_score` | `arthritis` |  | &check; | Condition: "Arthritis" |
| `condition_score` | `asthma` |  | &check; | Condition: "Asthma" |
| `condition_score` | `bipolar_disorder` |  | &check; | Condition: "Bipolar Disorder" |
| `condition_score` | `cachexia` |  | &check; | Condition: "Cachexia" |
| `condition_score` | `cancer` |  | &check; | Condition: "Cancer" |
| `condition_score` | `crohns_disease` |  | &check; | Condition: "Crohn's Disease" |
| `condition_score` | `epilepsy` |  | &check; | Condition: "Epilepsy" |
| `condition_score` | `fibromyalgia` |  | &check; | Condition: "Fibromyalgia" |
| `condition_score` | `gastrointestinal_disorder` |  | &check; | Condition: "Gastrointestinal Disorder" |
| `condition_score` | `glaucoma` |  | &check; | Condition: "Glaucoma" |
| `condition_score` | `hiv_aids` |  | &check; | Condition: "HIV/AIDS" |
| `condition_score` | `hypertension` |  | &check; | Condition: "Hypertension" |
| `condition_score` | `migraines` |  | &check; | Condition: "Migraines" |
| `condition_score` | `multiple_sclerosis` |  | &check; | Condition: "Multiple Sclerosis" |
| `condition_score` | `muscular_dystrophy` |  | &check; | Condition: "Muscular Dystrophy" |
| `condition_score` | `parkinsons` |  | &check; | Condition: "Parkinson's" |
| `condition_score` | `phantom_limb_pain` |  | &check; | Condition: "Phantom Limb Pain" |
| `condition_score` | `pms` |  | &check; | Condition: "PMS" |
| `condition_score` | `ptsd` |  | &check; | Condition: "PTSD" |
| `condition_score` | `spinal_cord_injury` |  | &check; | Condition: "Spinal Cord Injury" |
| `condition_score` | `tinnitus` |  | &check; | Condition: "Tinnitus" |
| `condition_score` | `tourettes_syndrome` |  | &check; | Condition: "Tourette's Syndrome" |
| `effect_count` | `aroused` |  | &check; | Effect: "Aroused" |
| `effect_count` | `creative` |  | &check; | Effect: "Creative" |
| `effect_count` | `energetic` |  | &check; | Effect: "Energetic" |
| `effect_count` | `euphoric` |  | &check; | Effect: "Euphoric" |
| `effect_count` | `focused` |  | &check; | Effect: "Focused" |
| `effect_count` | `giggly` |  | &check; | Effect: "Giggly" |
| `effect_count` | `happy` |  | &check; | Effect: "Happy" |
| `effect_count` | `hungry` |  | &check; | Effect: "Hungry" |
| `effect_count` | `relaxed` |  | &check; | Effect: "Relaxed" |
| `effect_count` | `sleepy` |  | &check; | Effect: "Sleepy" |
| `effect_count` | `talkative` |  | &check; | Effect: "Talkative" |
| `effect_count` | `tingly` |  | &check; | Effect: "Tingly" |
| `effect_count` | `uplifted` |  | &check; | Effect: "Uplifted" |
| `effect_score` | `aroused` |  | &check; | Effect: "Aroused" |
| `effect_score` | `ce_score` | &check; | &check; | Calming-Energizing ratio (see [here](#calming-energizing-ratio) for definition) converted to a Z-score |
| `effect_score` | `creative` |  | &check; | Effect: "Creative" |
| `effect_score` | `energetic` |  | &check; | Effect: "Energetic" |
| `effect_score` | `euphoric` |  | &check; | Effect: "Euphoric" |
| `effect_score` | `focused` |  | &check; | Effect: "Focused" |
| `effect_score` | `giggly` |  | &check; | Effect: "Giggly" |
| `effect_score` | `happy` |  | &check; | Effect: "Happy" |
| `effect_score` | `hungry` |  | &check; | Effect: "Hungry" |
| `effect_score` | `relaxed` |  | &check; | Effect: "Relaxed" |
| `effect_score` | `sleepy` |  | &check; | Effect: "Sleepy" |
| `effect_score` | `talkative` |  | &check; | Effect: "Talkative" |
| `effect_score` | `tingly` |  | &check; | Effect: "Tingly" |
| `effect_score` | `uplifted` |  | &check; | Effect: "Uplifted" |
| `flavor_count` | `ammonia` |  | &check; | Flavor: "Ammonia" |
| `flavor_count` | `apple` |  | &check; | Flavor: "Apple" |
| `flavor_count` | `apricot` |  | &check; | Flavor: "Apricot" |
| `flavor_count` | `berry` |  | &check; | Flavor: "Berry" |
| `flavor_count` | `blue_cheese` |  | &check; | Flavor: "Blue Cheese" |
| `flavor_count` | `blueberry` |  | &check; | Flavor: "Blueberry" |
| `flavor_count` | `butter` |  | &check; | Flavor: "Butter" |
| `flavor_count` | `cheese` |  | &check; | Flavor: "Cheese" |
| `flavor_count` | `chemical` |  | &check; | Flavor: "Chemical" |
| `flavor_count` | `chestnut` |  | &check; | Flavor: "Chestnut" |
| `flavor_count` | `citrus` |  | &check; | Flavor: "Citrus" |
| `flavor_count` | `coffee` |  | &check; | Flavor: "Coffee" |
| `flavor_count` | `diesel` |  | &check; | Flavor: "Diesel" |
| `flavor_count` | `earthy` |  | &check; | Flavor: "Earthy" |
| `flavor_count` | `flowery` |  | &check; | Flavor: "Flowery" |
| `flavor_count` | `grape` |  | &check; | Flavor: "Grape" |
| `flavor_count` | `grapefruit` |  | &check; | Flavor: "Grapefruit" |
| `flavor_count` | `honey` |  | &check; | Flavor: "Honey" |
| `flavor_count` | `lavender` |  | &check; | Flavor: "Lavender" |
| `flavor_count` | `lemon` |  | &check; | Flavor: "Lemon" |
| `flavor_count` | `lime` |  | &check; | Flavor: "Lime" |
| `flavor_count` | `mango` |  | &check; | Flavor: "Mango" |
| `flavor_count` | `menthol` |  | &check; | Flavor: "Menthol" |
| `flavor_count` | `mint` |  | &check; | Flavor: "Mint" |
| `flavor_count` | `nutty` |  | &check; | Flavor: "Nutty" |
| `flavor_count` | `orange` |  | &check; | Flavor: "Orange" |
| `flavor_count` | `peach` |  | &check; | Flavor: "Peach" |
| `flavor_count` | `pear` |  | &check; | Flavor: "Pear" |
| `flavor_count` | `pepper` |  | &check; | Flavor: "Pepper" |
| `flavor_count` | `pine` |  | &check; | Flavor: "Pine" |
| `flavor_count` | `pineapple` |  | &check; | Flavor: "Pineapple" |
| `flavor_count` | `plum` |  | &check; | Flavor: "Plum" |
| `flavor_count` | `pungent` |  | &check; | Flavor: "Pungent" |
| `flavor_count` | `rose` |  | &check; | Flavor: "Rose" |
| `flavor_count` | `sage` |  | &check; | Flavor: "Sage" |
| `flavor_count` | `skunk` |  | &check; | Flavor: "Skunk" |
| `flavor_count` | `spicy_herbal` |  | &check; | Flavor: "Spicy/Herbal" |
| `flavor_count` | `strawberry` |  | &check; | Flavor: "Strawberry" |
| `flavor_count` | `sweet` |  | &check; | Flavor: "Sweet" |
| `flavor_count` | `tar` |  | &check; | Flavor: "Tar" |
| `flavor_count` | `tea` |  | &check; | Flavor: "Tea" |
| `flavor_count` | `tobacco` |  | &check; | Flavor: "Tobacco" |
| `flavor_count` | `tree_fruit` |  | &check; | Flavor: "Tree Fruit" |
| `flavor_count` | `tropical` |  | &check; | Flavor: "Tropical" |
| `flavor_count` | `vanilla` |  | &check; | Flavor: "Vanilla" |
| `flavor_count` | `violet` |  | &check; | Flavor: "Violet" |
| `flavor_count` | `woody` |  | &check; | Flavor: "Woody" |
| `flavor_score` | `ammonia` |  | &check; | Flavor: "Ammonia" |
| `flavor_score` | `apple` |  | &check; | Flavor: "Apple" |
| `flavor_score` | `apricot` |  | &check; | Flavor: "Apricot" |
| `flavor_score` | `berry` |  | &check; | Flavor: "Berry" |
| `flavor_score` | `blue_cheese` |  | &check; | Flavor: "Blue Cheese" |
| `flavor_score` | `blueberry` |  | &check; | Flavor: "Blueberry" |
| `flavor_score` | `butter` |  | &check; | Flavor: "Butter" |
| `flavor_score` | `cheese` |  | &check; | Flavor: "Cheese" |
| `flavor_score` | `chemical` |  | &check; | Flavor: "Chemical" |
| `flavor_score` | `chestnut` |  | &check; | Flavor: "Chestnut" |
| `flavor_score` | `citrus` |  | &check; | Flavor: "Citrus" |
| `flavor_score` | `coffee` |  | &check; | Flavor: "Coffee" |
| `flavor_score` | `diesel` |  | &check; | Flavor: "Diesel" |
| `flavor_score` | `earthy` |  | &check; | Flavor: "Earthy" |
| `flavor_score` | `flowery` |  | &check; | Flavor: "Flowery" |
| `flavor_score` | `grape` |  | &check; | Flavor: "Grape" |
| `flavor_score` | `grapefruit` |  | &check; | Flavor: "Grapefruit" |
| `flavor_score` | `honey` |  | &check; | Flavor: "Honey" |
| `flavor_score` | `lavender` |  | &check; | Flavor: "Lavender" |
| `flavor_score` | `lemon` |  | &check; | Flavor: "Lemon" |
| `flavor_score` | `lime` |  | &check; | Flavor: "Lime" |
| `flavor_score` | `mango` |  | &check; | Flavor: "Mango" |
| `flavor_score` | `menthol` |  | &check; | Flavor: "Menthol" |
| `flavor_score` | `mint` |  | &check; | Flavor: "Mint" |
| `flavor_score` | `nutty` |  | &check; | Flavor: "Nutty" |
| `flavor_score` | `orange` |  | &check; | Flavor: "Orange" |
| `flavor_score` | `peach` |  | &check; | Flavor: "Peach" |
| `flavor_score` | `pear` |  | &check; | Flavor: "Pear" |
| `flavor_score` | `pepper` |  | &check; | Flavor: "Pepper" |
| `flavor_score` | `pine` |  | &check; | Flavor: "Pine" |
| `flavor_score` | `pineapple` |  | &check; | Flavor: "Pineapple" |
| `flavor_score` | `plum` |  | &check; | Flavor: "Plum" |
| `flavor_score` | `pungent` |  | &check; | Flavor: "Pungent" |
| `flavor_score` | `rose` |  | &check; | Flavor: "Rose" |
| `flavor_score` | `sage` |  | &check; | Flavor: "Sage" |
| `flavor_score` | `skunk` |  | &check; | Flavor: "Skunk" |
| `flavor_score` | `spicy_herbal` |  | &check; | Flavor: "Spicy/Herbal" |
| `flavor_score` | `strawberry` |  | &check; | Flavor: "Strawberry" |
| `flavor_score` | `sweet` |  | &check; | Flavor: "Sweet" |
| `flavor_score` | `tar` |  | &check; | Flavor: "Tar" |
| `flavor_score` | `tea` |  | &check; | Flavor: "Tea" |
| `flavor_score` | `tobacco` |  | &check; | Flavor: "Tobacco" |
| `flavor_score` | `tree_fruit` |  | &check; | Flavor: "Tree Fruit" |
| `flavor_score` | `tropical` |  | &check; | Flavor: "Tropical" |
| `flavor_score` | `vanilla` |  | &check; | Flavor: "Vanilla" |
| `flavor_score` | `violet` |  | &check; | Flavor: "Violet" |
| `flavor_score` | `woody` |  | &check; | Flavor: "Woody" |
| `lab_summary` | `data_completeness` |  | &check; | A measure of the presence of cannabinoid and terpene data after aggregating samples (see [here](#data-completeness) for definition) |
| `lab_summary` | `total_cannabs` |  | &check; | Average sum of cannabinoid measurements (i.e. sum the cannabinoid measurements for each sample and then average across all samples of the given strain) |
| `lab_summary` | `total_terps` |  | &check; | Average sum of terpene measurements (i.e. sum the terpene measurements for each sample and then average across all samples of the given strain) |
| `lab_summary` | `variability_score` |  | &check; | Average pairwise euclidean distance between cannabinoid and terpene measurement vectors for samples identified as the given strain |
| `leafly_summary` | `indica_sativa_balance` |  | &check; | Label indicating where the given strain falls on the indica-sativa spectrum. Label will be one of the following:  "indica", "indica-dominant-hybrid", "hybrid", "sativa-dominant-hybrid", "sativa" |
| `leafly_summary` | `top_effect` | &check; | &check; | The effect with the highest `effect_score` |
| `negative_count` | `anxious` |  | &check; | Negative effect: "Anxious" |
| `negative_count` | `dizzy` |  | &check; | Negative effect: "Dizzy" |
| `negative_count` | `dry_eyes` |  | &check; | Negative effect: "Dry Eyes" |
| `negative_count` | `dry_mouth` |  | &check; | Negative effect: "Dry Mouth" |
| `negative_count` | `headache` |  | &check; | Negative effect: "Headache" |
| `negative_count` | `paranoid` |  | &check; | Negative effect: "Paranoid" |
| `negative_score` | `anxious` |  | &check; | Negative effect: "Anxious" |
| `negative_score` | `dizzy` |  | &check; | Negative effect: "Dizzy" |
| `negative_score` | `dry_eyes` |  | &check; | Negative effect: "Dry Eyes" |
| `negative_score` | `dry_mouth` |  | &check; | Negative effect: "Dry Mouth" |
| `negative_score` | `headache` |  | &check; | Negative effect: "Headache" |
| `negative_score` | `paranoid` |  | &check; | Negative effect: "Paranoid" |
| `symptom_count` | `cramps` |  | &check; | Symptom: "Cramps" |
| `symptom_count` | `depression` |  | &check; | Symptom: "Depression" |
| `symptom_count` | `eye_pressure` |  | &check; | Symptom: "Eye Pressure" |
| `symptom_count` | `fatigue` |  | &check; | Symptom: "Fatigue" |
| `symptom_count` | `headaches` |  | &check; | Symptom: "Headaches" |
| `symptom_count` | `inflammation` |  | &check; | Symptom: "Inflammation" |
| `symptom_count` | `insomnia` |  | &check; | Symptom: "Insomnia" |
| `symptom_count` | `lack_of_appetite` |  | &check; | Symptom: "Lack of Appetite" |
| `symptom_count` | `muscle_spasms` |  | &check; | Symptom: "Muscle Spasms" |
| `symptom_count` | `nausea` |  | &check; | Symptom: "Nausea" |
| `symptom_count` | `pain` |  | &check; | Symptom: "Pain" |
| `symptom_count` | `seizures` |  | &check; | Symptom: "Seizures" |
| `symptom_count` | `spasticity` |  | &check; | Symptom: "Spasticity" |
| `symptom_count` | `stress` |  | &check; | Symptom: "Stress" |
| `symptom_score` | `cramps` |  | &check; | Symptom: "Cramps" |
| `symptom_score` | `depression` |  | &check; | Symptom: "Depression" |
| `symptom_score` | `eye_pressure` |  | &check; | Symptom: "Eye Pressure" |
| `symptom_score` | `fatigue` |  | &check; | Symptom: "Fatigue" |
| `symptom_score` | `headaches` |  | &check; | Symptom: "Headaches" |
| `symptom_score` | `inflammation` |  | &check; | Symptom: "Inflammation" |
| `symptom_score` | `insomnia` |  | &check; | Symptom: "Insomnia" |
| `symptom_score` | `lack_of_appetite` |  | &check; | Symptom: "Lack of Appetite" |
| `symptom_score` | `muscle_spasms` |  | &check; | Symptom: "Muscle Spasms" |
| `symptom_score` | `nausea` |  | &check; | Symptom: "Nausea" |
| `symptom_score` | `pain` |  | &check; | Symptom: "Pain" |
| `symptom_score` | `seizures` |  | &check; | Symptom: "Seizures" |
| `symptom_score` | `spasticity` |  | &check; | Symptom: "Spasticity" |
| `symptom_score` | `stress` |  | &check; | Symptom: "Stress" |
| `terpene` | `caryophyllene` |  | &check; | Average measurement of caryophyllene |
| `terpene` | `humulene` |  | &check; | Average measurement of humulene |
| `terpene` | `limonene` |  | &check; | Average measurement of limonene |
| `terpene` | `linalool` |  | &check; | Average measurement of linalool |
| `terpene` | `myrcene` |  | &check; | Average measurement of myrcene |
| `terpene` | `ocimene` |  | &check; | Average measurement of ocimene |
| `terpene` | `pinene` |  | &check; | Average measurement of pinene |
| `terpene` | `terpinolene` |  | &check; | Average measurement of terpinolene |


## Extra clarification

### Terpene measurements

Average terpene measurements are calculated after grouping samples into clusters using [DBSCAN clustering](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.DBSCAN.html) and then averaging terpene measurements of samples that are assigned to the dominant cluster(s)

### How is the chemotype of a sample determined?

```
if CBD is null or THC is null or CBD and THC are both 0
    chemotype => null
else if (CBD is equal to 0 and THC > 0) or THC/CBD >= 5
    chemotype => 1
else if THC/CBD >= 0.2
    chemotype => 3
else
    chemotype => 2
```

### Data completeness

```
if sample has terpene data
    data_completeness => 1
else if sample has cannabinoid data
    data_completeness => 0.5
else
    data_completeness => 0
```

where:
- `has terpene data` means pinene measurement is non-null and > 0
- `has cannabinoid data` means total CBD & total THC are both non-null and their sum > 0

### Calming-Energizing ratio

```
(sum of energizing effect votes - sum of calming effect votes) /
(energizing effect votes + calming effect votes)
```

where:
- calming effects: "Relaxed", "Sleepy"
- energizing effects: "Energetic", "Uplifted"

### Weighted rating formula

Taken from IMDb (see [here](https://help.imdb.com/article/imdb/track-movies-tv/ratings-faq/G67Y87TFYYP6TWAV#calculatetop))

```
(
    ((v ÷ (v + m)) × r) +
    ((m ÷ (v + m)) × c)
)
```

where:
- `r` = average vote for given trait category/slug
- `v` = number of votes for the given slug
- `m` = minimum votes required
- `c` = average for given trait category for all slugs

### What does "is_trending" mean?

```
if unique pageviews for the given strain >= median unique pageviews for all strains
    and percent change (see 'percent_change' definition above) for the given strain >= (
        average percentage change for all strains +
        one standard deviation of percentage change for all strains
    )
    is_trending => true
else
    is_trending => false
```
