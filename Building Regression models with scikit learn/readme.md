This folder contains files and folder related to regression models with scikit learn. <br>

Difference between fit_transform and transform. <br>
### fit:

** 

*  The fit method is typically used to compute and learn parameters from the data.
*  For example, when using a standard scaler, it calculates the mean and standard deviation of the data to standardize it.
*  The fit method is used on the training data to calculate these parameters.
*  After fitting, the transformer object retains the learned parameters.

### fit_transform:

** 

*  The fit_transform method combines both fitting and transforming in a single step.
*  It calculates the parameters on the training data just like fit, but it also applies the transformation to the data.
*  The result of fit_transform is the transformed data, which you can directly use for further processing or modeling.
*  This method is often used on the training data, and the same parameters are later used to transform the test or validation data to ensure consistency.

* transform:

**  

*  transform method is applied on test data, which uses the parameters from fitting on train data.


## Why do we use transform and not fit_transform on test data?
* When you use fit_transform on the training data, you're learning and applying the preprocessing steps (e.g., scaling, encoding) specific to the training data. These preprocessing steps should be based solely on the training data to avoid contaminating the model with information from the test set.
* By using fit_transform on the training data, we're simulating this situation of unknown-ness, and we try to get the model's performance on the test data that reflects its generalization ability to new, unseen data.
* we are trying to fit the parameters learned from the training data alone to transform the test data, this is also a factor for estimation of overfitting scenario.
