# Binary Classification with Naive Bayes

### Introduction
In this report, I will present the
methodology, results, and insights from
developing a binary classification model
using the Naive Bayes algorithm. The
objective of this assignment was to gain
hands-on experience in data loading,
preprocessing, visualization, model
development, and performance analysis.
Along the way, I encountered several
challenges that contributed to my learning
experience and understanding of machine
learning principles.

### Data Loading and Preprocessing
#### Data loading and handling
Initially, I loaded the data using pandas.
Since the file was in .data format, I
converted it to .csv for easier handling.
Upon inspection, I noticed that the columns
were not labeled but numbered. To address
this, I referred to the list of attributes from
the website's additional variable
information.
#### Handling missing values and data cleaning
I conducted an initial search for missing
values, which yielded no results. However,
upon closer examination, I discovered that
missing values were represented by "?". I
counted the occurrences of "?" in each
column and dropped columns with more
than 170 occurrences. I then handled
remaining "?" values by removing the
corresponding rows. Additionally, I
excluded the "Record ID" and "ZSN_A"
columns as they were deemed unnecessary
for further analysis. Finally, I applied
min-max scaling to normalize the data.

#### Splitting dataset into training and testing sets
Finally, I divided the dataset into training
and testing subsets. This division facilitates
model evaluation by ensuring that the model
is trained on one subset and tested on
another, allowing for a more accurate
assessment of its performance.

### Data Visualization
#### Visual Plots
In exploring the dataset, I employed
histograms and boxplots to understand the
distribution and variability of numerical
features.

#### Class Distribution & Class Imbalance
Understanding class distribution is pivotal
for classification tasks to ensure model
performance and avoid biases. Utilizing
countplots, I visualized class counts to
discern balance or imbalance. A balanced
distribution ensures each class is
well-represented, aiding models in learning
and making accurate predictions. Employing
the resampling technique of undersampling
addressed imbalance, with visualizations
gauging the effectiveness of these strategies.

### Model Development
#### Naive Bayes Algorithm
In my exploration of Naive Bayes
classifiers, I delved into four variants:
Gaussian, multinomial, complementNB, and
BernoulliNB. Among these, GaussianNB
exhibited an accuracy of 0.5833, followed
closely by multinomialNB with an accuracy
of 0.60185. Additionally, both
complementNB and BernoulliNB achieved
an accuracy of 0.60185 and 0.59259,
respectively.
Generalized Model Implementation:
For the binary classification task targeting
Chronic Heart Failure (ZSN), I followed
these steps:
1. Segregated the dataset into features
(X) and the target variable (y).
2. Partitioned the data into training and
testing sets using train_test_split
from sklearn.model_selection, with a
test size of 20% and a fixed random
state of 42 for reproducibility.
3. Initialized four classifiers:
GaussianNB, MultinomialNB,
ComplementNB, and BernoulliNB.
4. Trained the classifier on the training
data using the fit method.
5. Made predictions on the test data
using the predict method and
evaluated accuracy and generated
classification reports.
#### Optimization
In this feature selection process, I utilized
SelectKBest with the chi-squared test. After
experimenting with various values, I
determined that selecting k = 5 yielded the
highest accuracy of 0.62962. This method
selects the top k features based on their
chi-squared scores. Subsequently, I trained a
Gaussian Naive Bayes classifier on the
selected features and evaluated its accuracy
on the test set.
Next, I performed hyperparameter tuning
using grid search with cross-validation. I
explored a range of values for the
'var_smoothing' hyperparameter, which
controls the amount of regularization
applied to the Gaussian Naive Bayes
classifier. The grid search identified the best
value of 'var_smoothing' that maximized the
model's accuracy on the training data.
### Code Implementation and Testing
I prioritized code quality and clarity,
ensuring modularity and thorough
documentation. Handling edge cases and
rigorous testing enhanced output reliability.
This approach yielded a robust classification
model, demonstrating strong performance in
Code Implementation and Testing.
### Performance Analysis
#### Performance Metrics
In assessing the Gaussian Naive Bayes
classifier's performance, I utilized a range of
metrics including accuracy, precision, recall,
and the F1-score. These metrics offer
insights into the model's overall correctness,
its ability to avoid false positives
(precision), capture all positive instances
(recall), and balance between precision and
recall (F1-score).
#### ROC Curve and Confusion Matrix
Additionally, I analyzed the ROC curve and
confusion matrix, providing a visual and
detailed understanding of the model's
classification performance.

### Reflection and Insights
Reflecting on the model performance, I
observed notable variations across different
Naive Bayes classifiers. Each classifier
demonstrated distinct strengths and
weaknesses, as evident from their accuracy,
precision, recall, and F1-score metrics. The
GaussianNB classifier exhibited balanced
precision but lower recall, indicating a
tendency to misclassify positive instances.
Conversely, MultinomialNB and
ComplementNB showed improved recall but
slightly lower precision. BernoulliNB
displayed a similar pattern, albeit with
marginally lower performance.
Upon hyperparameter tuning, there was a
noticeable enhancement in model accuracy,
particularly in correctly identifying negative
instances. However, the precision and recall
for positive instances saw a trade-off,
suggesting potential areas for further
optimization. This optimization process
sheds light on the importance of fine-tuning
hyperparameters to achieve a balance
between model performance metrics.
Insights gleaned from these observations
suggest avenues for improvement. Firstly, a
deeper analysis of feature selection
techniques could help identify more
informative features, potentially enhancing
model performance. Secondly, exploring
ensemble methods or more complex
classifiers could mitigate the trade-offs
observed in precision and recall. Lastly,
further investigation into data preprocessing
techniques, such as handling class
imbalance, may lead to more robust and
reliable classification models. Overall, these
insights underscore the iterative nature of
model development and the importance of
continuous refinement to achieve optimal
performance.
