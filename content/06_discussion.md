## 6. Discussion

### 6.1 Key Takeaways

The first takeaway from the results of this project is that artificial neural networks are the best option for binary classification problems like this project. This is not surprising, given the popularity of ANNs. They are one of the most widely applied and useful machine learning algorithms and are able to take on most, if not all, machine learning problems and give a great result.

The second takeaway is that datasets such as ours that have very sparse data may result in poor learning of the model. In our case, the dataset had barely any damaged datapoints in comparison to undamaged, so the model was not able to learn how to identify between the two. Our solution to this was to add copies of the damaged data that we did have in order to allow the model to see them more. This is dangerous, however, because this does run the possibility of overfitting to those specific datapoints. Therefore, there is a limit to how many copies should be included in the dataset to avoid these issues.

### 6.2 Applications

The results of this project show that machine learning has a place in structural health monitoring. A team with more machine learning experience and more data can create a model that can determine structural damage in real time and thus may be able to prevent or predict a structural collapse and save lives. The idea can be taken even further and can be adapted and expanded to allow for detection of damage in specific regions or even specific structural members in the structure, as well as predicting useful structural life. This can save large amounts of money that are spent on structural inspections, repairs, and rebuilding after catastrophic failures.

