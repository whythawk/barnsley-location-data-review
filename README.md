# Barnsley Metropolitan Borough Council commercial ratepayer location data review

## Abstract

In February 2021, [Whythawk](https://whythawk.com), an open data research service, was asked to provide a [standard quarterly-aggregated extract of commercial location data](https://whythawk.com/index.php/research-reports/24-sqwyre-commercial-location-data-aggregations-for-england-and-wales-as-of-july-2020) for local authorities in England and Wales. These data are derived from our [Sqwyre](https://sqwyre.com) commercial location data longitudinal study which integrates data from the master database of commercial hereditaments maintained by the Valuations Office Agency (VOA), and regularly-updated commercial ratepayers registers published by local authorities. During subsequent review, a potential anomoly was discovered in the quarterly aggregation for Barnsley Metropolitan Borough Council.

This research report was initiated to investigate these data transitions and answer the following questions:

- What aggregate VOA changes occurred during updates between April to December 2019 in terms of hereditaments added, withdrawn, or recategorised?
- Were there any meaningful changes during the 2019 calendar year which may have influenced estimates for hereditament vacancy?
- Within each series, what proportion of hereditaments can be unambiguously classified in terms of occupation status, and how does ambiguity arise?
- What proportion of the total count of the hereditament base, as defined by the VOA, are represented in ratepayer data updates?
- What proportion of Barnsley data, in terms of reference numbers and matching quality, can be merged into the VOA master database?
- How are matches, and misses, reflected in vacancy tallies in general, temporally, and for each of the main categories of use (retail, office, industrial and leisure) considered in the initial study?

The objective for the Sqwyre commercial location database is to produce a well-structured, standardised dataset for research and analysis. The specific defaults used to aggregate the historical record for a quarterly report for each hereditament are designed to ensure that restatements and corrections provided via regular updates from the Valuations Office Agency and local authorities take precedence over previous updates. Each successive update takes precedence over the ones which came before. This ensures corrections happen, but can also leave long-term errors in place if no subsequent updates, or corrections, are released.

Sources of ambiguity which prevent integration of these datasets include:

- Unclear, or missing, hereditament reference codes,
- Duplicate rows with conflicting dates and occupation status,
- Provided data not covering the complete list of VOA hereditaments,
- Provided data for hereditaments not yet registered with VOA.

After a thorough review process, this research was able to replicate the results produced for the original quarterly-aggregated extract, and answer the research questions.

The core deflators of Barnsley's stated vacancy rate in their October 2019 commercial ratepayer data release are:

- Understating the total number of hereditaments (declaring 8,765 vs 9,630 in the VOA register),
- Ambiguous or irreconcilable hereditaments (138 out of 767 are ambiguous),
- Including non-retail, office, industrial or leisure hereditaments in the total (55 hereditaments classified as `other` in the total).

While overall vacancy in the earliest two Barnsley updates were 7.2% and 6.5% respectively, the fall in occupation seems to be precipitated by an enormous rise in the number of hereditaments as 2,000 new records are introduced. This increased the total hereditament count from 7,000 to 9,000, deflating the vacancy rate even as the absolute number of voids remained relatively consistent.

A subsequent update, not available at the time of the initial generation of the aggregation data, increased overall vacancy rates to 7.6%. However, a period of 18 months passed between updates published by Barnsley, and this lack of data access meant that changes were not reflected as expected.

Our recommendations for limiting the impact of such challenges are that local authorities must publish their register of commercial ratepayers quarterly and continuously, and that ambiguity can be limited by adoption of universal definitions and data structure standards through a defined schema.

## Installation and dependencies

You will require [Jupyter Notebook](https://jupyter.org/) and Python to replicate the analysis performed in this review. All source data - as provided by both the VOA and Barnsley Metropolitan Borough Council - are in the `data/` subfolder. Other than the dependencies below, all data and code are provided in this repository.

- [Pyenv](https://github.com/pyenv/pyenv) to manage Python version
- Upgrade Pyenv, and install the working Python environment for this Notebook:

    ```  
    cd /full/path/to/.pyenv/plugins/python-build/../.. && git pull && cd -
    pyenv install 3.9.4
    pyenv local 3.9.4
    ```


- Then [Poetry](https://python-poetry.org/docs/managing-environments/#switching-between-environments) for environment management, and install the dependencies:

    ```
    pyenv which python3.9.4
    poetry env use /full/path/to/python
    poetry install
    ```

If you wish to use your own environment, then dependencies are:

    python = "^3.9.4"
    jupyterlab = "^3.0.14"
    numpy = "^1.20.2"
    pandas = "^1.2.4"
    matplotlib = "^3.4.1"

## Whois

My name is [Gavin Chait](https://gavinchait.com), and I am a data scientist at [Whythawk](https://whythawk.com), specialising in economic development, public health, and data curation. I spent more than a decade in economic and development initiatives in South Africa. I was the commercial lead of open data projects at the Open Knowledge Foundation, leading the open source CKAN development team, and led the implementation of numerous open data technical and research projects around the world. [Sqwyre.com](https://sqwyre.com) is an initiative to develop a commercial location data longitudinal study which integrates data from the master database of commercial hereditaments maintained by the Valuations Office Agency (VOA), and regularly-updated commercial ratepayers registers published by local authorities.

I have extensive experience in leading research projects, implementing open source software initiatives, and developing and leading seminars and workshops. I have taught for 25 years, including for undergraduates, adult education, and technical and analytical teaching at all levels.

## Licensing and release

Research content, materials and methodology are copyright Whythawk, and released under both the [Creative Commons Attribution-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/) and the [BSD 3-Clause](https://opensource.org/licenses/BSD-3-Clause) licences.

The objective is to ensure reuse, replication and review, and I recommend - but do not require - that any modifications or adaptations of the source material should be released under an equivalent licence.