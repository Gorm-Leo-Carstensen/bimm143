Untitled
================

## PDB statistics

Here we inspect the types of structures in the main database for 3D
biomolecular data - the PDB

``` r
# read in file
stats <- read.csv("Data Export Summary.csv",row.names=1)

# calculate precentage values for each "method"
stats
```

    ##                     Proteins Nucleic.Acids Protein.NA.Complex Other  Total
    ## X-Ray                 133756          2086               6884     8 142734
    ## NMR                    11308          1317                265     8  12898
    ## Electron Microscopy     3241            35               1095     0   4371
    ## Other                    284             4                  6    13    307
    ## Multi Method             146             5                  2     1    154

``` r
ans <- stats$Total/sum(stats$Total)*100 
names(ans) <- rownames(stats)
round(ans,2)
```

    ##               X-Ray                 NMR Electron Microscopy               Other 
    ##               88.95                8.04                2.72                0.19 
    ##        Multi Method 
    ##                0.10

> Q1: determine the percentage of structures solved by X-Ray and
> Electron Microscopy.

For X-ray: 88.950 %

For Electron microscopy: 2.72 %

> Q2: determine what proportion of structures are protein? Aim to have a
> rendered GitHub document with working code that yields your answers.

``` r
# Propertion of structures are proteins 
round(sum(stats$Proteins)/sum(stats$Total)*100,2)
```

    ## [1] 92.69

> Q2: Type HIV in the PDB website search box on the home page and
> determine how many HIV-1 protease structures are in the current PDB?
