Changelog
=========

All notable changes to this project will be documented in this file. We keep track of changes in this file since v0.4.0. The format is based on `Keep a Changelog <https://keepachangelog.com/en/1.0.0/>`_ and we adhere to `Semantic Versioning <https://semver.org/spec/v2.0.0.html>`_. The source code for all `releases <https://github.com/alan-turing-institute/sktime/releases>`_ is available on GitHub.


[0.7.0] - 2021-07-12
--------------------

Added
~~~~~
* new module (experimental): Time Series Clustering (#1049) @TonyBagnall
* new module (experimental): Pairwise transformers, kernels/distances on tabular data and panel data - base class, examples, extension templates (#1071) @fkiraly @chrisholder
* new module (experimental): Series annotation and PyOD adapter (#1021) @fkiraly @satya-pattnaik
* Clustering extension templates, docstrings & get_fitted_params (#1100) @fkiraly
* New Classifier: Implementation of signature based methods.  (#714) @jambo6
* New Forecaster: Croston's method (#730) @Riyabelle25
* New Forecaster: ForecastingPipeline for pipelining with exog data (#967) @aiwalter
* New Transformer: Multivariate Detrending (#1042) @SveaMeyer13
* New Transformer: ThetaLines transformer (#923) @GuzalBulatova
* sktime registry (#1067) @fkiraly
* Feature/information criteria get_fitted_params (#942) @ltsaprounis
* Add plot_correlations() to plot series and acf/pacf (#850) @RNKuhns
* Add doc-quality tests on changed files (#752) @mloning
* Docs: Create add_dataset.rst (#970) @Riyabelle25
* Added two new related software packages (#1019) @aiwalter
* Added orbit as related software (#1128) @aiwalter
* adding fkiraly as codeowner for forecasting base classes (#989) @fkiraly
* added mloning and aiwalter as forecasting/base code owners (#1108) @fkiraly

Changed
~~~~~~~
* Update metric to handle y_train (#858) @RNKuhns
* TSC base template refactor (#1026) @fkiraly
* Forecasting refactor: base class refactor and extension template (#912) @fkiraly
* Forecasting refactor: base/template docstring fixes, added fit_predict method (#1109) @fkiraly
* Forecasters refactor: NaiveForecaster (#953) @fkiraly
* Forecasters refactor: BaseGridSearch, ForecastingGridSearchCV, ForecastingRandomizedSearchCV (#1034) @GuzalBulatova
* Forecasting refactor: polynomial trend forecaster (#1003) @thayeylolu
* Forecasting refactor: Stacking, Multiplexer, Ensembler and TransformedTarget Forecasters (#977) @thayeylolu
* Forecasting refactor: statsmodels and  theta forecaster (#1029) @thayeylolu
* Forecasting refactor: reducer (#1031) @Lovkush-A
* Forecasting refactor: ensembler, online-ensembler-forecaster and descendants (#1015) @thayeylolu
* Forecasting refactor: TbatAdapter (#1017) @thayeylolu
* Forecasting refactor: PmdArimaAdapter (#1016) @thayeylolu
* Forecasting refactor: Prophet (#1005) @thayeylolu
* Forecasting refactor: CrystallBall Forecaster (#1004) @thayeylolu
* Forecasting refactor: default tags in BaseForecaster; added some new tags (#1013) @fkiraly
* Forecasting refactor: removing _SktimeForecaster and horizon mixins (#1088) @fkiraly
* Forecasting tutorial rework (#972) @fkiraly
* Added tuning tutorial to forecasting example notebook - fkiraly suggestions on top of #1047 (#1053) @fkiraly
* Classification: Kernel based refactor (#875) @MatthewMiddlehurst
* Classification: catch22 Remake (#864) @MatthewMiddlehurst
* Forecasting: Remove step_length hyper-parameter from reduction classes (#900) @mloning
* Transformers: Make OptionalPassthrough to support multivariate input (#1112) @aiwalter
* Transformers: Improvement to Multivariate-Detrending (#1077) @SveaMeyer13
* Update plot_series to handle pd.Int64 and pd.Range index uniformly (#892) @Dbhasin1
* Including floating numbers as a window length (#827) @thayeylolu
* update docs on loading data (#885) @SveaMeyer13
* Update docs (#887) @mloning
* [DOC] Updated docstrings to inform that methods accept ForecastingHorizon (#872) @julramos

Fixed
~~~~~
* Fix use of seasonal periodicity in naive model with mean strategy (from PR #917) (#1124) @mloning
* Fix ForecastingPipeline import (#1118) @mloning
* Bugfix - forecasters should use internal interface _all_tags for self-inspection, not _has_tag (#1068) @fkiraly
* bugfix: Prophet adapter fails to clone after setting parameters (#911) @Yard1
* Fix seeding issue in Minirocket Classifier (#1094) @Lovkush-A
* fixing soft dependencies link (#1035) @fkiraly
* Fix minor typos in docstrings (#889) @GuzalBulatova
* Fix manylinux CI (#914) @mloning
* Add limits.h to ensure pip install on certain OS's (#915) @tombh
* Fix side effect on input for Imputer and HampelFilter (#1089) @aiwalter
* BaseCluster class issues resolved (#1075) @chrisholder
* Cleanup metric docstrings and fix bug in _RelativeLossMixin (#999) @RNKuhns
* minor clarifications in forecasting extension template preamble (#1069) @fkiraly
* Fix fh in imputer method based on in-sample forecasts (#861) @julramos
* Arsenal fix, extended capabilities and HC1 unit tests (#902) @MatthewMiddlehurst
* minor bugfix - setting _is_fitted to False before input checks in forecasters (#941) @fkiraly
* Properly process random_state when fitting Time Series Forest ensemble in parallel (#819) @kachayev
* bump nbqa (#998) @MarcoGorelli
* datetime: Construct Timedelta from parsed pandas frequency (#873) @ckastner

All contributors: @Dbhasin1, @GuzalBulatova, @Lovkush-A, @MarcoGorelli, @MatthewMiddlehurst, @RNKuhns, @Riyabelle25, @SveaMeyer13, @TonyBagnall, @Yard1, @aiwalter, @chrisholder, @ckastner, @fkiraly, @jambo6, @julramos, @kachayev, @ltsaprounis, @mloning, @thayeylolu and @tombh


[0.6.1] - 2021-05-14
--------------------

Fixed
~~~~~
* Exclude Python 3.10 from manylinux CI (#870) @mloning
* Fix AutoETS handling of infinite information criteria (#848) @ltsaprounis
* Fix smape import (#851) @mloning

Changed
~~~~~~~
* ThetaForecaster now works with initial_level (#769) @yashlamba
* Use joblib to parallelize ensemble fitting for Rocket classifier (#796) @kachayev
* Update maintenance tools (#829) @mloning
* Undo pmdarima hotfix and avoid pmdarima 1.8.1 (#831) @aaronreidsmith
* Hotfix pmdarima version (#828) @aiwalter

Added
~~~~~
* Added Guerrero method for lambda estimation to BoxCoxTransformer (#778) (#791) @GuzalBulatova
* New forecasting metrics (#801) @RNKuhns
* Implementation of DirRec reduction strategy (#779) @luiszugasti
* Added cutoff to BaseGridSearch to use any grid search inside evaluate… (#825) @aiwalter
* Added pd.DataFrame transformation for Imputer and HampelFilter (#830) @aiwalter
* Added default params for some transformers (#834) @aiwalter
* Added several docstring examples (#835) @aiwalter
* Added skip-inverse-transform tag for Imputer and HampelFilter (#788) @aiwalter
* Added a reference to alibi-detect (#815) @satya-pattnaik

All contributors: @GuzalBulatova, @RNKuhns, @aaronreidsmith, @aiwalter, @kachayev, @ltsaprounis, @luiszugasti, @mloning, @satya-pattnaik and @yashlamba


[0.6.0] - 2021-04-15
--------------------

Fixed
~~~~~
* Fix counting for Github's automatic language discovery (#812) @xuyxu
* Fix counting for Github's automatic language discovery (#811) @xuyxu
* Fix examples CI checks (#793) @mloning
* Fix TimeSeriesForestRegressor (#777) @mloning
* Fix Deseasonalizer docstring (#737) @mloning
* SettingWithCopyWarning in Prophet with exogenous data (#735) @jschemm
* Correct docstrings for check_X and related functions (#701) @Lovkush-A
* Fixed bugs mentioned in #694  (#697) @AidenRushbrooke
* fix typo in CONTRIBUTING.md (#688) @luiszugasti
* Fix duplicacy in the contribution's list (#685) @afzal442
* HIVE-COTE 1.0 fix (#678) @MatthewMiddlehurst

Changed
~~~~~~~
* Update sklearn version (#810) @mloning
* Remove soft dependency check for numba (#808) @mloning
* Modify tests for forecasting reductions (#756) @Lovkush-A
* Upgrade nbqa (#794) @MarcoGorelli
* Enhanced exception message of splitters (#771) @aiwalter
* Enhance forecasting model selection/evaluation (#739) @mloning
* Pin PyStan version (#751) @mloning
* master to main conversion in docs folder closes #644 (#667) @ayan-biswas0412
* Update governance (#686) @mloning
* remove MSM from unit tests for now (#698) @TonyBagnall
* Make update_params=true by default (#660) @pabworks
* update dataset names (#676) @TonyBagnall

Added
~~~~~
* Add support for exogenous variables to forecasting reduction (#757) @mloning
* Added forecasting docstring examples (#772) @aiwalter
* Added the agg argument to EnsembleForecaster (#774) @Ifeanyi30
* Added OptionalPassthrough transformer (#762) @aiwalter
* Add doctests (#766) @mloning
* Multiplexer forecaster (#715) @koralturkk
* Upload source tarball to PyPI during releases (#749) @dsherry
* Create developer guide (#734) @mloning
* Refactor TSF classifier into TSF regressor (#693) @luiszugasti
* Outlier detection with HampelFilter (#708) @aiwalter
* changes to contributing.md to include directions to installation (#695) @kanand77
* Evaluate (example and fix) (#690) @aiwalter
* Knn unit tests (#705) @TonyBagnall
* Knn transpose fix (#689) @TonyBagnall
* Evaluate forecaster function (#657) @aiwalter
* Multioutput reduction strategy for forecasting (#659) @Lovkush-A

All contributors: @AidenRushbrooke, @Ifeanyi30, @Lovkush-A, @MarcoGorelli, @MatthewMiddlehurst, @TonyBagnall, @afzal442, @aiwalter, @ayan-biswas0412, @dsherry, @jschemm, @kanand77, @koralturkk, @luiszugasti, @mloning, @pabworks and @xuyxu


[0.5.3] - 2021-02-06
--------------------

Fixed
~~~~~
* Fix reduced regression forecaster reference (#658) @mloning
* Address Bug #640 (#642) @patrickzib
* Ed knn (#638) @TonyBagnall
* Euclidean distance for KNNs (#636) @goastler

Changed
~~~~~~~
* Pin NumPy 1.19 (#643) @mloning
* Update CoC committee (#614) @mloning
* Benchmarking issue141 (#492) @ViktorKaz
* Catch22 Refactor & Multithreading (#615) @MatthewMiddlehurst

Added
~~~~~
* Create new factory method for forecasting via reduction (#635) @Lovkush-A
* Feature ForecastingRandomizedSearchCV (#634) @pabworks
* Added Imputer for missing values (#637) @aiwalter
* Add expanding window splitter (#627) @koralturkk
* Forecasting User Guide (#595) @Lovkush-A
* Add data processing functionality to convert between data formats (#553) @RNKuhns
* Add basic parallel support for `ElasticEnsemble` (#546) @xuyxu

All contributors: @Lovkush-A, @MatthewMiddlehurst, @RNKuhns, @TonyBagnall, @ViktorKaz, @aiwalter, @goastler, @koralturkk, @mloning, @pabworks, @patrickzib and @xuyxu

[0.5.2] - 2021-01-13
--------------------

Fixed
~~~~~
* Fix ModuleNotFoundError issue (#613) @Hephaest
* Fixes _fit(X) in KNN (#610) @TonyBagnall
* UEA TSC module improvements 2 (#599) @TonyBagnall
* Fix sktime.classification.frequency_based not found error (#606) @Hephaest
* UEA TSC module improvements 1 (#579) @TonyBagnall
* Relax numba pinning (#593) @dhirschfeld
* Fix fh.to_relative() bug for DatetimeIndex (#582) @aiwalter

All contributors: @Hephaest, @MatthewMiddlehurst, @TonyBagnall, @aiwalter and @dhirschfeld

[0.5.1] - 2020-12-29
--------------------

Added
~~~~~
* Add ARIMA (#559) @HYang1996
* Add fbprophet wrapper (#515) @aiwalter
* Add MiniRocket and MiniRocketMultivariate (#542) @angus924
* Add Cosine, ACF and PACF transformers (#509) @afzal442
* Add example notebook Window Splitters (#555) @juanitorduz
* Add SlidingWindowSplitter visualization on doctrings (#554) @juanitorduz

Fixed
~~~~~
* Pin pandas version to fix pandas-related AutoETS error on Linux  (#581) @mloning
* Fixed default argument in docstring in SlidingWindowSplitter (#556) @ngupta23

All contributors: @HYang1996, @TonyBagnall, @afzal442, @aiwalter, @angus924, @juanitorduz, @mloning and @ngupta23

[0.5.0] - 2020-12-19
--------------------

Added
~~~~~
* Add tests for forecasting with exogenous variables (#547) @mloning
* Add HCrystalBall wrapper (#485) @MichalChromcak
* Tbats (#527) @aiwalter
* Added matrix profile using stumpy  (#471) @utsavcoding
* User guide (#377) @mloning
* Add GitHub workflow for building and testing on macOS (#505) @mloning
* [DOC] Add dtaidistance (#502) @mloning
* Implement the `feature_importances_` property for RISE (#497) @AaronX121
* Add scikit-fda to the list of related software (#495) @vnmabus
* [DOC] Add roadmap to docs (#467) @mloning
* Add parallelization for `RandomIntervalSpectralForest` (#482) @AaronX121
* New Ensemble Forecasting Methods  (#333) @magittan
* CI run black formatter on notebooks as well as Python scripts (#437) @MarcoGorelli
* Implementation of catch22 transformer, CIF classifier and dictionary based clean-up (#453) @MatthewMiddlehurst
* Added write dataset to ts file functionality (#438) @whackteachers
* Added ability to load from csv containing long-formatted data (#442) @AidenRushbrooke
* Transform typing (#420) @mloning

Changed
~~~~~~~
* Refactoring utils and transformer module (#538) @mloning
* Update README (#454) @mloning
* Clean up example notebooks (#548) @mloning
* Update README.rst (#536) @aiwalter
* [Doc]Updated load_data.py (#496) @Afzal-Ind
* Update forecasting.py (#487) @raishubham1
* update basic motion description (#475) @vollmersj
* [DOC] Update docs in benchmarking/data.py (#489) @Afzal-Ind
* Edit Jupyter Notebook 01_forecasting (#486) @bmurdata
* Feature & Performance improvements of SFA/WEASEL (#457) @patrickzib
* Moved related software from wiki to docs (#439) @mloning

Fixed
~~~~~
* Fixed issue outlined in issue 522 (#537) @ngupta23
* Fix plot-series (#533) @gracewgao
* added mape_loss and cosmetic fixes to notebooks (removed kernel) (#500) @tch
* Fix azure pipelines (#506) @mloning
* [DOC] Fix broken docstrings of `RandomIntervalSpectralForest` (#473) @AaronX121
* Add back missing bibtex reference to classifiers (#468) @whackteachers
* Avoid seaborn warning (#472) @davidbp
* Bump pre-commit versions, run again on notebooks (#469) @MarcoGorelli
* Fix series validation (#463) @mloning
* Fix soft dependency imports (#446) @mloning
* Fix bug in AutoETS (#445) @HYang1996
* Add ForecastingHorizon class to docs (#444) @mloning

Removed
~~~~~~~
* Remove manylinux1 (#458) @mloning

All contributors: @AaronX121, @Afzal-Ind, @AidenRushbrooke, @HYang1996, @MarcoGorelli, @MatthewMiddlehurst, @MichalChromcak, @TonyBagnall, @aiwalter, @bmurdata, @davidbp, @gracewgao, @magittan, @mloning, @ngupta23, @patrickzib, @raishubham1, @tch, @utsavcoding, @vnmabus, @vollmersj and @whackteachers

[0.4.3] - 2020-10-20
--------------------

Added
~~~~~
* Support for 3d numpy array (#405) @mloning
* Support for downloading dataset from UCR UEA time series classification data set repository (#430) @Emiliathewolf
* Univariate time series regression example to TSFresh notebook (#428) @evanmiller29
* Parallelized TimeSeriesForest using joblib. (#408) @kkoziara
* Unit test for multi-processing (#414) @kkoziara
* Add date-time support for forecasting framework (#392) @mloning

Changed
~~~~~~~
* Performance improvements of dictionary classifiers (#398) @patrickzib

Fixed
~~~~~
* Fix links in Readthedocs and Binder launch button (#416) @mloning
* Fixed small bug in performance metrics (#422) @krumeto
* Resolved warnings in notebook examples (#418) @alwinw
* Resolves #325 ModuleNotFoundError for soft dependencies (#410) @alwinw

All contributors: @Emiliathewolf, @alwinw, @evanmiller29, @kkoziara, @krumeto, @mloning and @patrickzib


[0.4.2] - 2020-10-01
--------------------

Added
~~~~~
* ETSModel with auto-fitting capability (#393) @HYang1996
* WEASEL classifier (#391) @patrickzib
* Full support for exogenous data in forecasting framework (#382) @mloning, (#380) @mloning
* Multivariate dataset for US consumption over time (#385) @SebasKoel
* Governance document (#324) @mloning, @fkiraly

Fixed
~~~~~
* Documentation fixes (#400) @brettkoonce, (#399) @akanz1, (#404) @alwinw

Changed
~~~~~~~
* Move documentation to ReadTheDocs with support for versioned documentation (#395) @mloning
* Refactored SFA implementation (additional features and speed improvements) (#389) @patrickzib
* Move prediction interval API to base classes in forecasting framework (#387) @big-o
* Documentation improvements (#364) @mloning
* Update CI and maintenance tools (#394) @mloning

All contributors: @HYang1996, @SebasKoel, @fkiraly, @akanz1, @alwinw, @big-o, @brettkoonce, @mloning, @patrickzib


[0.4.1] - 2020-07-09
--------------------

Added
~~~~~
- New sktime logo @mloning
- TemporalDictionaryEnsemble (#292) @MatthewMiddlehurst
- ShapeDTW (#287) @Multivin12
- Updated sktime artwork (logo) @mloning
- Truncation transformer (#315) @ABostrom
- Padding transformer (#316) @ABostrom
- Example notebook with feature importance graph for time series forest (#319) @HYang1996
- ACSF1 data set (#314) @BandaSaiTejaReddy
- Data conversion function from 3d numpy array to nested pandas dataframe (#304) @vedazeren

Changed
~~~~~~~
- Replaced gunpoint dataset in tutorials, added OSULeaf dataset (#295) @marielledado
- Updated macOS advanced install instructions (#306) (#308) @sophijka
- Updated contributing guidelines (#301) @Ayushmaanseth

Fixed
~~~~~
- Typos (#293) @Mo-Saif, (#285) @Pangoraw, (#305) @hiqbal2
- Manylinux wheel building (#286) @mloning
- KNN compatibility with sklearn (#310) @Cheukting
- Docstrings for AutoARIMA (#307) @btrtts

All contributors: @Ayushmaanseth, @Mo-Saif, @Pangoraw, @marielledado,
@mloning, @sophijka, @Cheukting, @MatthewMiddlehurst, @Multivin12,
@ABostrom, @HYang1996, @BandaSaiTejaReddy, @vedazeren, @hiqbal2, @btrtts


[0.4.0] - 2020-06-05
--------------------

Added
~~~~~
- Forecasting framework, including: forecasting algorithms (forecasters),
  tools for composite model building (meta-forecasters), tuning and model
  evaluation
- Consistent unit testing of all estimators
- Consistent input checks
- Enforced PEP8 linting via flake8
- Changelog
- Support for Python 3.8
- Support for manylinux wheels


Changed
~~~~~~~
- Revised all estimators to comply with common interface and to ensure scikit-learn compatibility

Removed
~~~~~~~
- A few redundant classes for the series-as-features setting in favour of scikit-learn's implementations: :code:`Pipeline` and :code:`GridSearchCV`
- :code:`HomogeneousColumnEnsembleClassifier` in favour of more flexible :code:`ColumnEnsembleClassifier`

Fixed
~~~~~
- Deprecation and future warnings from scikit-learn
- User warnings from statsmodels
