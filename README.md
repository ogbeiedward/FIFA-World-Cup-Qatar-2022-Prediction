![image](https://github.com/ogbeiedward/FIFA-World-Cup-Qatar-2022-Prediction/blob/main/images/Qatar-bg.jpg?raw=true)

# # FIFA-World-Cup-Qatar-2022-Prediction: Project Overview

Using international matches played since the 1990s, the countries' qualifiers from recent matches, and the potential of each side, this project aims to forecast the outcomes of the QATAR 2022 World Cup.

## Resources

* Python Version: 3.10
* Packages: Pandas, NumPy, Sklearn, Tensorflow, and Seaborn.
* Data: 
  * [international_matches.csv](https://www.kaggle.com/datasets/brenda89/fifa-world-cup-2022) - This dataset provides a complete overview of all international soccer matches played since the 90s. On top of that, the strength of each team is provided by incorporating actual FIFA rankings as well as player strengths based on the EA Sport FIFA video game.
  * [players_22.csv](https://www.kaggle.com/datasets/stefanoleone992/fifa-22-complete-player-dataset) - The datasets provided include the player data for FIFA 22 Career Mode.

## Data preparation and dataset creation

* Both datasets [international_matches.csv](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/data/international_matches.csv) and [players_22.csv](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/data/players_22.csv) were prepared for analysis and the creation of the training dataset of the Machine learning model. The data preparation involved removing the iformation of teams that will not participate in the cup and fixing the na's values.

* From dataset [international_matches.csv](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/data/international_matches.csv), create training dataset [training.csv](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/data/training.csv) and inference dataset [last_team_scores.csv](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/data/last_team_scores.csv). [training.csv](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/data/training.csv) contains the names of the teams facing each other, the FIFA ranking of each team, and the rating of both teams' defense, midfield, and offense. On the other hand, the inference dataset contains the qualification of each team on its last FIFA date.

## Exploratory Data Analysis

From datasets [international_matches.csv](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/data/international_matches.csv) and [players_22.csv](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/data/players_22.csv), the notebooks [QATAR22_EDA+Data_Preparation.ipynb](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/QATAR22_EDA%2BData_Preparation.ipynb) and [Getting_Squads_Stats.ipynb](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/Getting_Squads_Stats.ipynb) answer the questions listed below. These questions allow us to get an idea of the favorites to win the cup according to statistics.

* National soccer teams with the best offense

![image](https://github.com/ogbeiedward/FIFA-World-Cup-Qatar-2022-Prediction/blob/main/images/offense_score.png?raw=true)

* National soccer teams with the best defense

![image](https://github.com/ogbeiedward/FIFA-World-Cup-Qatar-2022-Prediction/blob/main/images/defense_score.png?raw=true)

* National soccer team with the best midfield

![image](https://github.com/ogbeiedward/FIFA-World-Cup-Qatar-2022-Prediction/blob/main/images/midfield_score.png?raw=true)

* Teams with the highest winning percentage

![image](https://github.com/ogbeiedward/FIFA-World-Cup-Qatar-2022-Prediction/blob/main/images/win_average.png?raw=true)


* The best players in Qatar 2022

![image](https://github.com/ogbeiedward/FIFA-World-Cup-Qatar-2022-Prediction/blob/main/images/overall_rating.png?raw=true)

* The most promising teams

![image](https://github.com/ogbeiedward/FIFA-World-Cup-Qatar-2022-Prediction/blob/main/images/team_potential.png?raw=true)

* Is there any advantage to be the local team?

This question is fundamental. The pie chart below highlights that home teams win more than 50% of the home games. This is due to different reasons, e.g., players are more comfortable in familiar surroundings, additional support from a home crowd, home comforts/lack of travel, configuration of the playing area to suit the home team. When the Colombian National Team visits the Maracana stadium to play against Brazil, they tend to lose the match or draw. However, they tend to tie or win when Colombia is local in the Metropolitano stadium. For this reason, to predict the result of the matches from a Machine Learning model, one must define the home team and the visiting team.

![image](https://github.com/ogbeiedward/FIFA-World-Cup-Qatar-2022-Prediction/blob/main/images/pie.png?raw=true)

## Modeling and Tuning

The [Modeling+Tuning.ipynb](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/Modeling%2BTuning.ipynb) notebook aims to train the Machine learning model that will predict the outcome of the World Cup matches. This notebook chooses one ML model to predict the group stage matches and another for the knockout stage. the difference is that the result of the group stage matches can be a loss, a draw, or a win. On the other hand, in the direct elimination stage, there is only defeat or victory. The best model for each stage is chosen among the algorithms:

* Random Forest
* Ada Boost Classifier
* XGB Boost
* Neural Networks

The XGB Boost model presents the best performance in both stages. Therefore it is tuned, validated, and exported as a pipeline to perform easy inferences.

* Confusion matrix of the group stage model tuned and validated

![image](https://github.com/ogbeiedward/FIFA-World-Cup-Qatar-2022-Prediction/blob/main/images/confusion1.png?raw=true)

* Confusion matrix of the knockout stage model tuned and validated

![image](https://github.com/ogbeiedward/FIFA-World-Cup-Qatar-2022-Prediction/blob/main/images/confusion2.png?raw=true)

## Predictions

Finally, notebook [Predictions.ipynb](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/Predictions.ipynb) employs the inference datasets and the trained models to predict the World Cup matches and thus find the winner of the World Cup. It is essential to mention that to choose who is the home team in each World Cup match, use dataset [squad_stats.csv](https://github.com/davidcamilo0710/QATAR_2022_Prediction/blob/master/data/squad_stats.csv), which provides the potential of each team; therefore, the team with more significant potential will be the home team.
