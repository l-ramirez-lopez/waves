# waves 0.2.0

* Update all files to conform to the tidyverse style guide (#6).
* All functions renamed to match tidystyle. Old functions names work will be dropped after this version: 
    - `AggregateSpectra` -> `aggregate_spectra()`
    - `DoPreprocessing` -> `pretreat_spectra()`
    - `FilterSpectra` -> `filter_spectra()`
    - `FormatCV`-> `format_cv()`
    - `PlotSpectra()`-> `plot_spectra()`
    - `SaveModel()`-> `save_model()`
    - `TestModelPerformance()`-> `test_spectra()`
    - `TrainSpectralModel()`-> `train_spectra()`
* "Preprocessing" has been renamed "Pretreatment" to minimize confusion with physical preprocessing of samples prior to scanning. Arguments have been renamed to reflect these changes (`preprocessing` is now `pretreatment`).
* Added more informative error message and documentation for random forest tune length (`tune.length` must be set to 5 when `model.algorithm == "rf"`).
* Additional flexibility for `plot_spectra()` including color and title customization and the option to forgo filtering (#5).
* Named list output for all functions to enable easier access to individual elements.
* Always return model and variable importance results with `train_spectra()` and `test_spectra()`.
* Add variable importance for PLSR (#9).
* Enable selection of k for k-fold cross-validation within the training set. Previously, k was fixed at 5 (#10).
* `save_model()` now automatically selects the best model if provided with multiple pretreatments.
* Code simplified and streamlined to facilitate future updates.
* Export predicted values as well as performance statistics for each training iteration (#11).
* `wavelengths` is no longer a required argument for any of the *waves* functions.
* The proportion of samples to include in the training set can now be selected with the argument `proportion.train`. Previously, this proportion was fixed at 0.7 (#13).
* Bug fix: `aggregate_spectra()` now allows for aggregation by a single grouping column (#14).
* The parameter `save.model` in the function `save_model()` has been renamed to `write.model` for clarity.


# waves 0.1.1

* Bug fix: SVM Linear and SVM Radial algorithms no longer return errors in `TrainSpectralModel()`.
* Bug fix: Random Forest variable importance no longer returns error in `TrainSpectralModel()` or when `preprocessing = TRUE` in `TestModelPerformance()` (#7). 
* Output for random forest variable importance now includes "Pretreatment" and "Iteration" columns.
* `PlotSpectra()` now allows for missing data in non-spectral columns of the input data frame.
* *waves* now has an [associated paper in the Plant Phenome Journal](https://doi.org/10.1002/ppj2.20012)! The citation for this paper should be used if *waves* is used in a paper - see citation("waves") for details.

# waves 0.1.0

Initial package release
