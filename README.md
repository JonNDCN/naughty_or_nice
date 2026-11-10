# naughty_or_nice

Code for our simulation study for the Christmas issue of The BMJ.

The paper uses Father Christmas's list to illustrate three statistical errors that keep turning up in clinical research: cutting a continuous measurement into two groups, treating a second look at the same data as independent confirmation, and mistaking regression to the mean for real improvement. All three come from treating a noisy measurement as if it were a clean label.

## The code

`analysis.Rmd` runs the simulations and draws the three figures in the paper. All the data are simulated, so there is nothing to download.

Each child's score is their underlying niceness plus random error, with a reliability of 0.7. Figure 1 comes straight from the normal distribution. Figure 2 simulates 251,226 children and compares how often two lists agree with how accurate they are. Figure 3 follows 400 children over two years.

## Using it

You will need R and a few packages:

```r
install.packages(c("dplyr", "tidyr", "ggplot2", "ggpubr", "patchwork", "rmarkdown"))
```

Open `analysis.Rmd` in RStudio and click Knit. The seeds are set, so you should get the same numbers as the paper. The counts are printed as tables alongside Figures 2 and 3. We ran it on R 4.6.1.

To try other assumptions, change `rel` for the reliability and `v_u` for how much the assessors differ. The "slope R = 0.7" label on Figure 3 is typed in, so that needs changing by hand.
