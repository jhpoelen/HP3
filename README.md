# HP3 Analysis files

This repository contains code and data to replicate analyses in Olival et. al.
(2016) *Host and Viral Traits Predict Zoonotic Spillover from Mammals.*

-  `data/` contains data used in these analyses, including
    -   our primary database of host-viral associations (`associations.csv`)
    -   databases of host (`hosts.csv`) and viral (`viruses.csv`) traits
    -   2 phylogenetic tree files in Newick format (`*.tree`) format. One (`supertree_mammals.tree`) is a
        pruned version of the mammallian supertree (Bininda-Emonds et. al. 2007), for the
        subset of mammals in our database.  The other (`cytb-supertree.tree`) is a custom-built
        cytochrome-B phylogeny constrained to the order-level topology of the mammalian supertree
        (see supplementary methods).
    -   full references for all associations in our database (`references.txt`)
    -   An `intermediates/` directory with derived data (species phylogenetic
        distance matrices and PVR-corrected host mass), and a script to generate
        these values
    -   A `metadata.csv` file that describes variables in our database and derived
        variables used in model-fitting
    -   `IUCN_taxonomy_23JUN2016.csv` is data from IUCN used to harmonize our data with IUCN spatial data (see Supplementary Methods)
-  `model_fitting/` contains an R markdown document which fits all the GAMs in
    the paper, and its output HTML document which includes tables comparing model
    AIC, plot and summaries of top models, relative influence of variables, and
    cross-validation results. Compiling this document runs all the
    models referred to in the paper, and saves the R objects needed for the 
    figures in `figures/` and `maps/`.
-  `figures/` contains figures and tables in the paper and extended data and
    the scripts to generate them, except for maps.
-  `maps/` contains a script to generate the map outputs in the paper and extended
    data, and the final outputs of all maps used in multi-panel map figures in the paper and Extended Data.
-   `R/` contains files with functions used in other scripts.    
-   `misc/` contains small scripts used for other calculations

---

### Listing of all files

```
├── README.md
├── HP3.Rproj
├── data
│   ├── associations.csv
│   ├── cytb_supertree.tree
│   ├── hosts.csv
│   ├── intermediate
│   │   ├── generate_phylogenetic_intermediate_data.R
│   │   ├── HP3-cytb_PDmatrix-12Mar2016.csv
│   │   ├── HP3-ST_PDmatrix-12Mar2016.csv
│   │   └── PVR_cytb_hostmass.csv
│   ├── IUCN_taxonomy_23JUN2016.csv
│   ├── metadata.csv
│   ├── references.txt
│   ├── supertree_mammals.tree
│   └── viruses.csv
├── figures
│   ├── ExtendedFigure01-heatmap.R
│   ├── ExtendedTable01-models.docx
│   ├── ExtendedTable01-models.R
│   ├── Figure01A-boxplots.pdf
│   ├── Figure01B-boxplots.pdf
│   ├── Figure01-boxplots.R
│   ├── Figure02-all-gams.R
│   ├── Figure02-all-gams.svg
│   ├── Figure04-viral-traits.R
│   └── Figure04-viral-traits.svg
├── maps
│   ├── create_maps.R
│   └── output
│       └── png
│           ├── all_viruses/
│           ├── host/
│           └── zoonoses/
├── misc
│   ├── calc-bat-special.R
│   └── zoonotic_dev_explained_w_offset.R
├── model_fitting
│   ├── gam_supp_info.Rmd
│   ├── gam_supp_info.md
│   ├── gam_supp_info.html
│   ├── gam_supp_info_files/figure-html/
│   ├── postprocessed_database.rds
│   ├── preprocess_data.R
│   ├── all_viruses_model.rds
│   ├── all_zoonoses_model.rds
│   ├── top_models.rds
│   ├── viral_traits_model.rds
│   └── virus_data_processed.rds
├── R
│   ├── avg_gam_vis.R
│   ├── cross_validation.R
│   ├── fit_gam.R
│   ├── model_reduction.R
│   └── relative_contributions.R
```
