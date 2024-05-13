# What can be contributed?

There are 3 keys ways one can contribute to ARC

1) Add a new asset
2) Add new instruments for an asset
3) Add new classification tags

To facilitate high-quality and timely collaboration, we request that

- Contributors open **individual** pull requests for adding new assets versus adding classification tags versus adding new instruments. This will ensure that all reviews are accurate and timely.
- Contributors share Amberdata’s mission and vision to make ARC an industry-leading, verified, and trusted dataset for digital asset users, which requires that contributors adhere to the Code of Conduct (`CODE_OF_CONDUCT.md`) described in the repository
- Contributors adhere to the guidelines listed here below

## Adding New Assets
1) The contributor must open a pull request with a branch name formatted like

`new_asset(<asset_name>)` e.g. `new_asset(ASDFCoin)`

2) In the pull request, the contributor must submit a JSON file that completes the required fields listed in `packages/schemas/asset.json` for the new asset. Pull requests that are missing the required fields will be not be considered for review
3) For classification tags on the asset

    a) If the asset will be tagged with existing tags, the contributor must provide supporting documents, text, website links and evidence in the pull request description/comments that demonstrate why the asset should be classified with the suggested tags

    b) If the asset will be tagged with brand new classification tags, one must complete the process of [Adding New Classification Tags](#adding-new-classification-tags) first

Amberdata will review the pull request with additional feedback. The turnaround time for this review process will be five business days. Amberdata will automatically generate the Arc Id upon acceptance of the new asset.

## Adding New Classification Tags
1) The contributor must open a pull request with a branch name formatted like

`new_classification_tag(<tag_name>)` e.g. `new_classification_tag(DeAutomotiveMesh)`

2) In the pull request, the contributor must submit a JSON file that describes and summarizes that new classification tag in 3-5 sentences
3) In the pull request description/comments, the contributor must provide supporting documentation, text, website links and evidence to generate a new classification tag. The documentation and evidence will be processed via text analysis to validate the classification suggestion. The outputs of the text analysis will be compared with other public information sources

Amberdata will review the pull request with additional feedback. The turnaround time for this review process will be five business days.

## Adding New Instruments
1) The contributor must open a pull request with a branch name formatted like

`new_instrument(type=<instrument_type>)/<asset_arc_id>` e.g. `new_instrument(type=spot)/AMB:BBB00000000`

2) In the pull request, the contributor must submit a JSON file that completes the required fields for the spot, options, or futures instrument for the asset. The required fields for each instrument type can be found in `packages/schemas/instrument*.json`. Pull requests that are missing the required fields will be not be considered for review

    a) Please note that one may contribute spot instruments from multiple exchanges in one pull request, but cannot mix instrument types in a single pull request. We ask that different instrument types are split into appropriate pull requests

    b) Please note that because adding new instruments requires an Arc Id, one must complete the process of [Adding New Assets](#adding-new-assets) first

3) In the pull request description/comments, the contributor must also provide reference information from the exchanges these instruments trade on. This reference information can take the form of exchange API requests and responses, exchange listing documentation and articles, and so on


Amberdata will review the pull request with additional feedback. The turnaround time for this review process will be five business days.
