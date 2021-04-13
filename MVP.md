# Minimum Viable Product

The goal of my project is to see if we can predict the film rating of the renowned late movie critic Roger Ebert if he were alive today.

My baseline model has 9 features with p-values less than 0.05. The stats model has R2 of 0.941, which is unexpectedly good. However, the cross validation testing showed a average score of 0.38, and the RMSE is 0.7, which is about more than a half star off the Ebert rating.

![](https://github.com/crystal-ctrl/regression_project/blob/b5794a651863d492eb039ab6401cc1fa7cd2981a/Image/baseline%20model%20stats.png)



The scores on the training set and testing set are close but low, which indicates an underfitting model.

![](/Image/baseline_comparison.png)

The above model visualization depects the model plotted predicted rating against the actual data points. 

This result suggested that this model loses some accuracy as Ebert rating decreases. It could definitely be improved.

I will continue with model refinement, tuning and selection to find the best performing model on validation.
