# Simple-Linear-Regression-on-Predicting-Student-Outcomes
Using historical data from roughly 200 students from a cohort of Year 12 students and creating a simple linear regression to try and predict their final year mark based on the average of their 4 interim assessments.

Situation- in my previous career I had a big spreadsheet of student data and their weekly and half termly assessment marks. Each of the half term assessments would be reported home to parents and what this simple linear regression aims to do (rather crudely) is to try to predict the end of Year 12 exam mark based on the average of the 4 half term assessments.

Of course it is a crude way to predict an end of year 12 exam mark as the 4 half termly assessments are all different in nature, varying in terms of complexity and length. There are also other factors that may be worth investigating (study hours, homework completion rate, attendance) but this is a very simple model.

The data is 3 years old and all student data is anonymised to protect identity of students. Only student IDs are kept and its impossible to use this to find information as these are churned every 2 years and in the final analysis shown these will be redacted. 

Ideally I would like this model to be used at the end of the teaching cycle for departments to use to predict marks and hence can be used to define grade boundaries and plan ahead for Year 13 resources, class sizes as well as potential students who may fail based on the average of their 4 half termly assessments.

Description of steps:

1. I already had the full dataset of results and focussed on the Average of Key Assessments column and Final Progression Exam marks.
2. In my jupyter notebook I used this as my dataframe called student_data.
3. I checked this for nulls.
4. I then made a scatter graph to see the relationship between the variables which showed a clear positive correlation between average KA1-4 marks and final end of year exam mark. I used a correlation matrix to determine the strength of this correlation to be 0.80846.
5. I then initialised a train test split and then made an instance of linear regression to fit the training data to.
6. After this I could find the intercept and gradient- In context it shows that an average KA1-4 mark of 0 would result in 4 marks in the final exam. For the gradient it showed for every 1 mark increase in average KA1-4 mark a student can gain 0.95 marks in final end of year exam.
7. I then fitted this regression line onto the scatter graph to assess goodness of fit visually.

Evaluation after calculating metrics:
1. R-squared (R²) Score: 0.606
The model achieved an R² score of 0.606, indicating that approximately 60.6% of the variability in final exam scores can be explained by students' average assessment marks.
This suggests a moderate strength of relationship: assessment performance is a meaningful predictor of final exam outcomes, although other factors likely contribute to the remaining 39.4% of variance.

2. Root Mean Squared Error (RMSE): 12.53
The Root Mean Squared Error was calculated as 12.53, meaning that, on average, the model's predictions differ from the actual final exam scores by about 12.5 marks.
Depending on the exam's total mark range, this level of error may be considered significant and suggests there is room to enhance the model's predictive accuracy.

Interpretation
The results demonstrate that students' average assessment marks are a reasonably strong indicator of their final exam performance. However, the model's performance could potentially be improved by:

Including additional features (e.g., attendance rates, homework completion, participation).

Exploring non-linear models or interaction effects.

Conducting further feature engineering or applying regularization techniques.

Model Generalization and Overfitting Check:
To evaluate the model’s generalization performance, I compared its R² scores on the training and test datasets:

Training R²: 0.661

Test R²: 0.606

The training score is slightly higher than the test score, which is expected when fitting a model to data. However, the difference between the two is relatively small (~5.5%), indicating that the model generalizes well to unseen data and is not significantly overfitting.

This suggests that the linear relationship captured by the model between students' average assessment marks and final exam marks is stable across different data samples.
