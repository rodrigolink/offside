Developing a Model to Detect Offsides in a Football Match

A player is in an “offside position” if they are in the opposing team’s half of the field and also “nearer to the opponents’ goal line than both the ball and the second-last opponent.” This is a brief description, and we can develop it a little further by stating the five conditions that must be met.

    A teammate touches the ball, either by a pass, a headbutt or kicking towards the goal;
    The pass is not from a corner kick, a goal kick or a throw-in;
    The receiving player is in the offensive half of the field;
    The receiving player is closer to the goal line than the ball;
    There is only one player from the other team between the receiving player and the goal line.

When all five conditions happen in a given play, the game must be stopped and a free kick is given to the defensive team.

Input data: We found data from a Under-19 match with the position of the ball and the players with a frequency of 10Hz. We are going to explore and clean it to get a set of real match situations. 

Working data set: After getting rid of missing and erroneous data, we generate several plays by choosing randomly a number of pairs passer x receiver. We use the rules stated before to tag each play as an offside or not. We also balance the data set so that half of the plays are of each class.

Classification models: Two different classification models will be evaluated: Random Forest and Support Vector Classifier. For the RF model, we will vary the number of decision trees (1, 10, 100, 1.000 and 10.000). For the SVC model, much more computation-intensive, we will vary the size of the training set (25%, 50% and 75%). We will evaluate the performance using ROC, Accuracy and Confusion Matrix.  

Evaluation of results: To our surprise, the Random Forest Classifier, with 1000 trees, was the best model! We were expecting the SVC to be a better fit, because the offside conditions use the relative position of the players and a higher dimensional method would be able to get a better understanding of the data. When we compare the best RF to the best SVC, our RF performance is way better, with an error smaller than 2%! Very impressive result with such a simple model.

Lesson learned: we created a model to make a decision based on the position of the players without explicitly setting the rules with an accuracy of 98.5%.
