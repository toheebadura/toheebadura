### The Little Educational Background
National Diploma in Mathematics and Statistics, Moshood Abiola Polytechnic - $2014$ <br>
Bachelor's degree in Statistics from the University of Ibadan - $2019$ <br>
Master of Science degree in Mathematical Sciences, African Institute for Mathematical Sciences, Rwanda - $2021$ <br>
Doctor of Philosophy in Data Science, University of Limerick (Ongoing) <br>

### My Research Interests??
I'm interested in _Statistical Modelling_, _Natural Language Processing_, _Machine Learning_, _Deep Learning_ and _Finance_. <be>

### My Hobbies
I love literature, writing and football.


<!DOCTYPE html>
<html>
<head>
  <script async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML" integrity="sha384-R7txlRab6t0M3wTq8YKu60/K6jsn+xy2/9veL9F/Hi3XO+zdfLQ0l83CXTtekbH8" crossorigin="anonymous"></script>
</head>
<body>
  <h2>Logistic Regression: Brief Overview</h2>
  <p>Logistic Regression represents a machine learning algorithm commonly employed in supervised learning scenarios, specifically tailored for situations with binary categorical outcomes. This means that the response variable's categories typically comprise two possibilities, such as yes/no, true/false, good/bad, and benign/malignant, among others. While logistic regression shares a mathematical framework similar to linear regression, its primary application lies in classification learning rather than regression. In essence, when aiming to predict categorical variables like <code>credit score</code> (good/bad), <code>breast cancer type</code> (benign/malignant), or <code>customer returning</code> (yes/no), logistic regression serves as the suitable algorithm, as opposed to scenarios where the outcome variable is continuous.</p>
  <p>For context, continuous variables are obtained through measurements, often expressed as decimal values, encompassing attributes such as weight and height. On the other hand, categorical variables consist of distinct categories, such as skill levels (beginner, intermediate, and expert) and credit scores (good, bad). The former is seen as ordinal, involving a specific order, while the latter is nominal, signifying an absence of order.</p>

  <h2>Task of Logistic Regression</h2>
  <p>In linear regression, it is required to minimize the empirical risk, usually referred to as the average squared error loss or simply, the mean squared error (MSE). In Logistic regression, we minimize the empirical risk by maximizing the likelihood of training the dataset. We have the task of estimating the probability that an instance belongs to a particular class. If the estimated probability is greater than \(0.5\) or \(50\%\), then the model predicts that the instance belongs to the positive class (labelled as \(1\)), and otherwise, it belongs to the other class (labelled as \(0\)).</p>
  <p>The logistic regression model is written as
    <br>
    \[
    \log\left(\frac{f(x)}{1 - f(x)}\right) = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \cdots  + \beta_k x_k.
    \]
  </p>
  <p>The logistic regression model prediction discussed above is also represented mathematically as
    <br>
    \[
    \begin{align}
      \hat{y}(x) = 
      \begin{cases} 
            1 & \hat{f}(x) \geq 0.5 \\
            0 & \hat{f}(x) < 0.5 
      \end{cases}
    \end{align}
    \]
  </p>
  <p>Here, \(\hat{f}(x)\) represents the Logistic Regression model estimated probability &mdash; which is usually accompanied by a bias term &mdash; producing the logistic output. The summary of the logistic regression model is a weight coefficient for the individual features of the dataset plus a bias unit.</p>
  <p>Furthermore, the Logistic Regression model utilizes a <em>sigmoid function</em>, also known as the <em>logistic function</em>, to map the <em>logistic</em> as mentioned earlier to a value between \(0\) and \(1\). The sigmoid function is mathematically expressed as:
    <br>
    \[
    \begin{align}
    \sigma(t) &= \frac{e^t}{1 + e^t} \\
    \sigma(t) & = \frac{1}{1 + e^{-t}}
    \end{align}
    \]
  </p>

  <h2>Cross Validation</h2>
  <p>This is a technique for improving the accuracy of the model whilst ensuring that possible discrepancies between the training and testing set are minimized. It typically helps to avoid overfitting in the model. Overfitting in a model is the scenario whereby the model does not generalize well on unseen data (test set) but performs better on the training data as a result of picking too much noise from the training data. Thus, to have an idea about how the model would generalize on unseen data, <strong>Cross Validation</strong> techniques are utilized. Two instances of this technique are Leave-One-Out Cross-Validation and \(k\)-fold Cross-Validation, with the latter being perhaps the most common one, so we would talk about it, especially since the model utilized that.</p>

  <h3>\(K\)-Fold Cross-Validation</h3>
  <p>This uses part of the dataset for modeling and another different part for testing. This approach gives each sample in the dataset the chance of being tested since it involves iteration through the dataset over a number of times. Iteration is done over the dataset \(k\) number of times, and for each iteration, the dataset is split into \(K\) roughly equal subsets, using one part for validation, and the remaining \(K - 1\) is combined into a training subset for model evaluation. This is done for the \(k = 1, 2, \cdots, K\) whilst calculating the prediction error when predicting the \(k\)-th data part. Common choices for values of \(k\) are usually \(5\) or \(10\), and when \(K = N\), it is the case of the <strong>Leave-One-Out Cross-Validation</strong>.</p>

  <h2>Performance Evaluation Metrics</h2>
  <p>These are metrics used to access the classification model with respect to different considerations. The prominent ones relevant to the model are discussed as follows:</p>

  <ul>
    <li><strong>Confusion Matrix:</strong> The table below gives the representation of the components of the evaluation metrics, defining the predicted and actual labels. It is referred to as the <em>confusion matrix</em>.</li>
  </ul>

  <table>
    <thead>
      <tr>
        <th></th>
        <th></th>
        <th>Reference/Actual \((\text{y})\)</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td></td>
        <td></td>
        <td>Positive</td>
        <td>Negative</td>
      </tr>
      <tr>
        <td><strong>Prediction \(\widehat{f}(\text{x})\)</strong></td>
        <td>Positive</td>
        <td>True Positive \((\widehat{\text{TP}})\)</td>
        <td>False Positive \((\widehat{\text{FN}})\)</td>
      </tr>
      <tr>
        <td></td>
        <td>Negative</td>
        <td>False Negative \((\widehat{\text{FP}})\)</td>
        <td>True Negative \((\widehat{\text{TN}})\)</td>
      </tr>
    </tbody>
  </table>

  <p>For each of the four representative cells, we have:</p>
  <ul>
    <li>True Positive (TP): Positive observation, and predicted as positive.</li>
    <li>True Negative (TN): Negative observation, and predicted as negative.</li>
    <li>False Positive (FP): Negative observation, but predicted as positive.</li>
    <li>False Negative (FN): Positive observation, but predicted as negative.</li>
  </ul>

  <ul>
    <li><strong>Accuracy:</strong> Measures the total correct classification. For instance, considering the case of determining the credit score of a client, <em>accuracy</em> measures the number of classifications correctly output as a <code>good</code> credit score.</li>
  </ul>

  \[
  \begin{align}
  \text{Accuracy} = \frac{\widehat{\text{TP}} + \widehat{\text{TN}}}{\widehat{\text{TP}} + \widehat{\text{FP}} + \widehat{\text{TN}} + \widehat{\text{FN}}}
  \end{align}
  \]

  <ul>
    <li><strong>Precision:</strong> Also known as <strong>positive predictive value</strong>. The ratio of true positives to all the predicted positives by the model.</li>
  </ul>

  \[
  \begin{align}
  \text{Precision} = \frac{\widehat{\text{TP}}}{\widehat{\text{TP}} + \widehat{\text{FP}}}
  \end{align}
  \]

  <p>In the context of predicting clients with good or bad credit scores, with <strong>Good</strong> as the positive class, it can also be expressed as</p>

  \[
  \begin{align}
  \text{Recall} = \frac{\text{Number of customers predicted as GOOD given that they are GOOD}}{\text{Total number predicted as GOOD}}
  \end{align}
  \]

  <ul>
    <li><strong>Sensitivity or Recall:</strong> Also referred to as the <strong>true positive rate</strong>; that is, the ratio of true positives to all the positives.</li>
  </ul>

  \[
  \begin{align}
  \text{Recall} = \frac{\widehat{\text{TP}}}{\widehat{\text{TP}}+ \widehat{\text{FN}}}
  \end{align}
  \]

  <p>Also, using the same context as above, it can also be expressed as</p>

  \[
  \begin{align}
  \text{Recall} = \frac{\text{Number of customers predicted as GOOD given that they are GOOD}}{\text{Total number that is actually GOOD}}
  \end{align}
  \]

  <ul>
    <li><strong>Specificity:</strong> Also referred to as the <strong>true negative rate</strong>; that is, the ratio of true negatives to all the negatives.</li>
  </ul>

  \[
  \begin{align}
  \text{Recall} = \frac{\widehat{\text{TN}}}{\widehat{\text{TN}}+ \widehat{\text{FP}}}
  \end{align}
  \]

  <ul>
    <li><strong>F-Score:</strong> This estimates the classification model based on predictions for the positive class.</li>
  </ul>

  \[
  \begin{align}
  \text{F-Score}  = \frac{2 \times \text{Recall} \times \text{Precision}}{\text{Recall}+ \text{Precision}}
  \end{align}
  \]

  <h2>Pros and Cons of the Algorithm</h2>
  <p>A few of the advantages and limitations of the logistic regression algorithm are listed below:</p>

  <h3>Pros</h3>
  <ul>
    <li>Logistic regression is suitable in the need for a quick initial benchmark as it's easy to implement.</li>
    <li>With lower-dimensional datasets, it is less prone to overfitting.</li>
  </ul>

  <h3>Cons</h3>
  <ul>
    <li>It is applicable only when the response variable is a discrete function.</li>
    <li>It assumes the condition of linearity between the response variable and the feature variables.</li>
  </ul>

  <h2>Useful References</h2>
  <ul>
    <li><a href="https://www.amazon.co.uk/Elements-Statistical-Learning-Springer-Statistics/dp/0387848576#:~:text=Book%20details&text=This%20book%20describes%20the%20important,liberal%20use%20of%20colour%20graphics.">The Elements of Statistical Learning</a></li>
    <li><a href="https://arxiv.org/pdf/1811.12808.pdf">Model Evaluation, Model Selection, and Algorithm Selection in Machine Learning</a></li>
    <li><a href="https://www.amazon.co.uk/Hands-Machine-Learning-Scikit-Learn-TensorFlow/dp/1098125975">Hands-on Machine Learning with Scikit-Learn, Keras & TensorFlow</a></li>
    <li><a href="https://www.amazon.co.uk/Data-Science-Scratch-Joel-Grus/dp/1492041130">Data Science from Scratch</a></li>
  </ul>
</body>
</html>
