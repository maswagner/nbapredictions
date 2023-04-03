# NBA Salary Predictions using Player Statistics

![alt text](basketballgame.jpg)

Professional Basketball players are expensive. With the NBA League minimum salary being 1.1 Million, owners need to understand how much a player is worth. On the flip side of things, a player should be fairly evaluated for their productions on the court. Building a model can help solve this issue by taking player's career statistics and salaries through the years. 

### Business Understanding
As mentioned above, NBA players are pricey. Especially with the mean salary sitting around 3.5 Million. From the perspective of an owner and their NBA team, saving money and properly evaluating talent is important. 

### Data Understanding
Data came from two sources:
    - Basketballreferance.com - Player Salaries and Salary Cap both from 1984-2018
    - Kaggle.com - Player Statistics from 1984-2018

### Model and Evaluation
For making predictions, I chose to start with a linear regression model. 

The first model started off looking to predict salaries with the following statistics:
    - Points Per Game
    - Career Assists
    - Career FG Percentage
    - Career FG3 Percentage
    - Career FT Percentage 
    - Career Games
    - Career Points

Here are the metrics for the first model:
    R^2: 0.216 
    MAE: 2,514,196.182
    RMSE: 3,636,710.986
    
The R^2 tells us that the model explains the variance about 21.6% of the time. Essentially this model isn't very accurate. 
The Mean Absolute Error shows us that when our model makes a prediction, it on average is $2,514,196.18 off in a particular prediction. With the mean for salaries being $3,244,537, our predictions of off quite a significant amount. 

In finding out the inaccuracy of the first model, I realized that the US Dollar has inflated in value since 1984. In thinking of the best way, I remembered that every year the NBA institutes a salary cap preventing teams from spending too much on players. So instead of predicting the specific dollar salary, I standardized the target variable by dividing the salary by the salary cap of that year. Then I created a new linear regression predicting percent of salary cap. This model increased the accuracy by two-fold. 

Here are the metrics of the second model:
    R^2: 0.405
    MAE: 0.044
    RMSE: 0.063
    
The R^2 increased significantly, now sitting at 40.5%. The MAE is only 4.4% and with the mean for % of salary cap being 7.9%, meaning we're off by 4.4% on the average prediction. 

### Conclusion
Simply taking into account the inflation of the dollar and standardizing the target variable jurasically improved the model's performance. However, looking into other models such as XG Boost or Decision Tree's could potentially improve the model even more. 

### Repository Navigation