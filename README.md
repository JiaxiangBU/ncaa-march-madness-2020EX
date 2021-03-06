
<!-- README.md is generated from README.Rmd. Please edit that file -->

# ncaa-march-madness-2020

<!-- badges: start -->

<!-- badges: end -->

The goal of ncaa-march-madness-2020 is to store the notebooks for this
[Kaggle
Competition](https://www.kaggle.com/c/google-cloud-ncaa-march-madness-2020-division-1-mens-tournament/overview),
see
[GitBook](https://jiaxiangbu.github.io/ncaa-march-madness-2020/cookbook.html)
including

  - Baseline
  - XGBOOST 超参数调整
  - Target encoding
  - ID embedding
  - GBDT + LR
  - GBDT + LR k-fold
  - 变量重要性
  - Linear vs. Tree linear?
  - Auto-encoder 查询异常值
  - Python 包说明

We publish our package with some internal functions, install with

``` bash
pip install ncaa-march-madness-2020
```

## How to use

All notebooks work in the `analysis` directory, and save all data files
in `input`, `output` and `data` directories.

``` r
fs::dir_tree("analysis", recurse = TRUE, regexp = "ipynb")
#> analysis
#> +-- baseline.ipynb
#> +-- evaluate-features.ipynb
#> +-- gbdt_lr.ipynb
#> +-- gbdt_lr_CV.ipynb
#> +-- id2vec.ipynb
#> +-- linear-base-learner.ipynb
#> +-- march-madness-2020-ncaam-simple-lightgbm-on-kfold.ipynb
#> +-- Obtain_Answer.ipynb
#> +-- outliers.ipynb
#> +-- params_tuning.ipynb
#> +-- paris-madness.ipynb
#> +-- pkg_test.ipynb
#> \-- target-encoding.ipynb
fs::dir_tree(recurse = TRUE, regexp = "input|output|data")
#> .
#> +-- data
#> |   +-- feature_importances.csv
#> |   +-- id2vec.npy
#> |   +-- NCAA2020_Kenpom.csv
#> |   +-- outlier_df.csv
#> |   +-- submission_True.csv
#> |   +-- team_strength_embedding.csv
#> |   +-- Tourney_Reuslt.csv
#> |   \-- Tourney_Reuslt_inputs.csv
#> +-- input
#> |   +-- google-cloud-ncaa-march-madness-2020-division-1-mens-tournament
#> |   |   +-- MDataFiles_Stage1
#> |   |   |   +-- Cities.csv
#> |   |   |   +-- Conferences.csv
#> |   |   |   +-- MConferenceTourneyGames.csv
#> |   |   |   +-- MGameCities.csv
#> |   |   |   +-- MMasseyOrdinals.csv
#> |   |   |   +-- MNCAATourneyCompactResults.csv
#> |   |   |   +-- MNCAATourneyDetailedResults.csv
#> |   |   |   +-- MNCAATourneySeedRoundSlots.csv
#> |   |   |   +-- MNCAATourneySeeds.csv
#> |   |   |   +-- MNCAATourneySlots.csv
#> |   |   |   +-- MRegularSeasonCompactResults.csv
#> |   |   |   +-- MRegularSeasonDetailedResults.csv
#> |   |   |   +-- MSeasons.csv
#> |   |   |   +-- MSecondaryTourneyCompactResults.csv
#> |   |   |   +-- MSecondaryTourneyTeams.csv
#> |   |   |   +-- MTeamCoaches.csv
#> |   |   |   +-- MTeamConferences.csv
#> |   |   |   +-- MTeams.csv
#> |   |   |   \-- MTeamSpellings.csv
#> |   |   +-- MEvents2015.csv
#> |   |   +-- MEvents2016.csv
#> |   |   +-- MEvents2017.csv
#> |   |   +-- MEvents2018.csv
#> |   |   +-- MEvents2019.csv
#> |   |   +-- MPlayers.csv
#> |   |   \-- MSampleSubmissionStage1_2020.csv
#> |   \-- google-cloud-ncaa-march-madness-2020-division-1-mens-tournament.zip
#> +-- large_data
#> \-- output
#>     \-- paris-submission.csv
```

## Download Data

From <https://github.com/Kaggle/kaggle-api>

``` bash
kaggle competitions download -c google-cloud-ncaa-march-madness-2020-division-1-mens-tournament -p input
mkdir input/google-cloud-ncaa-march-madness-2020-division-1-mens-tournament
unzip input/google-cloud-ncaa-march-madness-2020-division-1-mens-tournament.zip -d input/google-cloud-ncaa-march-madness-2020-division-1-mens-tournament
```

## More

1.  Do the feature engineering on goal and spots with
    distance(Nandakumar 2020)
2.  We ignore the multicollinearity detection in the feature, we choose
    XGBoost, thus it handles this problem itself, see more
    <https://datascience.stackexchange.com/a/39806/60879>.

<h4 align="center">

**Code of Conduct**

</h4>

<h6 align="center">

Please note that the `ncaa-march-madness-2020` project is released with
a [Contributor Code of
Conduct](https://github.com/JiaxiangBU/ncaa-march-madness-2020/blob/master/CODE_OF_CONDUCT.md).<br>By
contributing to this project, you agree to abide by its terms.

</h6>

<h4 align="center">

**License**

</h4>

<h6 align="center">

Apache License (\>= 2.0) © [Jiaxiang Li;Jiatao Li;Zhipeng Liang;Yue
Pan](https://github.com/JiaxiangBU/ncaa-march-madness-2020/blob/master/LICENSE.md)

</h6>

## Reference

<div id="refs" class="references">

<div id="ref-Nandakumar2020">

Nandakumar, Namita. 2020. “R + Tidyverse in Sports.” RStudio Conference
2020. 2020.
<https://resources.rstudio.com/rstudio-conf-2020/r-tidyverse-in-sports-namita-nandakumar>.

</div>

</div>
