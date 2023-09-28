# [Gun violence in the United States by state](https://en.wikipedia.org/wiki/Gun_violence_in_the_United_States_by_state)

Sources:

- Census.gov: [State Population Totals: 2010-2019](https://www.census.gov/data/datasets/time-series/demo/popest/2010s-state-total.html)
- UCR.FBI.gov: [Murder by State, Types of Weapons, 2019](https://ucr.fbi.gov/crime-in-the-u.s/2019/crime-in-the-u.s.-2019/tables/table-20)
- Rand.org [Gun Ownership in America](https://www.rand.org/research/gun-policy/gun-ownership.html)

# Reproduce the Data Output

Run `2019-analysis.ipynb` to see the munging and intermediate data.

Examine the full table of joined data, where indicated midway through the notebook.

To create the Wikitext output, copy the final cell print output to separate file, such as
`wikipedia_2019_gun_violence_by_state_data.wikitext`. Concatenate all files into your clipboard:

```
cat \
    wikipedia_2015_2019_gun_violence_by_state_header.wikitext \
    wikipedia_2019_gun_violence_by_state_data.wikitext \
    wikipedia_2019_gun_violence_by_state_footer.wikitext \
    | pbcopy
```

For paste into the Wikipedia editor.

# Future Years' Updates

~~Future updates could require changes to munging (such as changing skipheader/skipfooter constants,
for a different header style or a different number of footnotes), changes to the footnote annotation
(if substantial ommisions in data from FBI UCR tables 4 or 20 change on per-state basis), renewal of data
from more current sources (such as using most recent census state populations, or gathering new household
firearm ownership rates), or other unforeseen changes.~~

**NOTE**: The data format for states to report these data to the FBI has changed as of 2020, so completely
new data wrangling will be needed, and it will yet be another year or more until a preponderance of states
are accurately reporting incident data. Per the FBI:

> As the UCR Program transitions to a NIBRS-only data collection, changes have been implemented at the national level,
> though not all have been adopted by state and local agencies at this time.

At the time of writing, the most recent NIBRS data is only available for 2022. "As of June 2022...
66% of the U.S. population is covered by NIBRS-reporting law enforcement agencies". Ommissions include
the entirety of Florida and almost the entirety of California.
(Although I'm not holding my breath for Florida... If my memory serves they were the only state to completely omit
categorizing murders by weapon for all of the past couple years.)

Sources:
- https://ucr.fbi.gov/nibrs/2019
- https://thecrimereport.org/2022/10/11/was-crime-up-or-down-in-2021-why-the-fbi-cant-tell-us/
- https://bjs.ojp.gov/national-incident-based-reporting-system-nibrs
