
# The Redacted Mueller Report

<!-- badges: start -->

<!-- badges: end -->

A (very unclean) text extraction of the [Redacted Mueller
Report](https://www.documentcloud.org/documents/5955210-Redacted-Mueller-Report.html).
The text [was extracted](process_report.R) using
[pdftools](https://github.com/ropensci/pdftools) from
[ROpenSci](https://ropensci.org).

The only cleaning of the data I’ve done was to replace references to
`Corney` with `Comey`.

``` r
library(tidyverse)

mueller_report <- read_csv("mueller_report.csv")

mueller_report %>% 
  filter(page == 195, between(line, 5, 18))
```

    ## # A tibble: 14 x 3
    ##     page  line text                                                        
    ##    <dbl> <dbl> <chr>                                                       
    ##  1   195     5 These authorities would support the view that candidate-rel…
    ##  2   195     6 to a campaign for the purpose of influencing an election co…
    ##  3   195     7 the foreign-source ban could apply. A campaign can be assis…
    ##  4   195     8 but also by the provision of derogatory information about a…
    ##  5   195     9 frequently conduct and pay for opposition research. A forei…
    ##  6   195    10 and provided resulting information to a campaign could exer…
    ##  7   195    11 a greater tendency to ingratiate the donor to the candidate…
    ##  8   195    12 of value. At the same time , no judicial decision has treat…
    ##  9   195    13 uncompensated opposition research or similar information as…
    ## 10   195    14 to a contribution under campaign -finance law. Such an inte…
    ## 11   195    15 beyond the foreign-source ban , see 52 U.S.C. § 30116(a) (i…
    ## 12   195    16 contributions), and raise First Amendment questions. Those …
    ## 13   195    17 where the information consisted simply of the recounting of…
    ## 14   195    18 uncertain how courts would resolve those issues.

The text in this repository was extracted from the redacted report available at:
<https://www.documentcloud.org/documents/5955210-Redacted-Mueller-Report.html>.

## Other Projects and Versions

There are a number of other projects and efforts to transcribe the DOJ's PDF version of the Mueller report into better text formats. The following projects are likely a better resources than this simple text extraction.

* [Factbase](https://factba.se) has published a human-reviewed text version of the report at [https://f2.link/mr-sheet](https://f2.link/mr-sheet).
* [Open Source Mueller Report](http://opensourcemuellerreport.com/) is an open source reproduction of the Mueller report into LaTex.
