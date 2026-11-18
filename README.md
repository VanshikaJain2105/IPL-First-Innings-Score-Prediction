# 🏏 IPL First Innings Score Prediction

### Predicting IPL first innings scores using Machine Learning

This project uses Machine Learning to predict the final first innings score of an IPL match based on the current match situation, including runs scored, wickets lost, overs completed, and performance in the last five overs.

The idea is simple: **Can we estimate how many runs a team will finish with, even before their innings is over?**

To explore this, I trained and compared different regression models using historical IPL match data.

## 📌 Project Overview

In T20 cricket, the final score depends on several factors, such as the batting team's performance, wickets remaining, and the number of overs left.

This project analyzes historical IPL data to understand these patterns and predict the final first innings total.

**The model takes the following inputs:**
- Batting team
- Bowling team
- Current runs scored
- Wickets lost
- Overs completed
- Runs scored in the last 5 overs
- Wickets lost in the last 5 overs

**Output:** Predicted final first innings score.

## 📊 Dataset

The project uses a historical IPL dataset (`ipl.csv`) containing **76,014 records and 15 columns**, covering matches from 2008 to 2017.

Each record represents a match situation during an innings.

The dataset includes information about teams, players, venues, runs, wickets, overs, recent performance, and the final innings total.

### Data Preprocessing

Before training the models, I performed the following steps:

1. Removed unnecessary columns and selected relevant features.
2. Filtered the dataset to retain the teams included in the analysis.
3. Converted cricket-style overs into the number of balls bowled.
4. Removed observations from the first five overs to focus on innings with more match information.
5. Encoded categorical features such as batting and bowling teams.
6. Split the data chronologically into training, validation, and testing sets.

## 🔍 Exploratory Data Analysis

I explored the dataset to better understand the relationship between match conditions and final innings scores.

The analysis includes:

- Distribution of final innings scores
- Relationship between runs scored and the final total
- Impact of wickets lost
- Performance across different stages of an innings
- Correlation between numerical features

Visualizations were created using Matplotlib and Seaborn.

## 🤖 Machine Learning Models

I experimented with five regression algorithms to compare their performance.

| Algorithm | Description |
|---|---|
| Linear Regression | Predicts the final score using linear relationships between features |
| Decision Tree Regressor | Uses decision rules to estimate the final score |
| Random Forest Regressor | Combines multiple decision trees to improve predictions |
| AdaBoost Regressor | Combines weak learners to create a stronger prediction model |
| Gradient Boosting Regressor | Builds models sequentially to reduce prediction errors |

The models were evaluated and compared to select the most suitable one.

## 📈 Model Evaluation

Since predicting a cricket score is a regression problem, I evaluated the models using three metrics:

**Mean Absolute Error (MAE)**

Measures the average difference between actual and predicted scores. A lower MAE means better predictions.

**Root Mean Squared Error (RMSE)**

Measures prediction errors while penalizing larger mistakes more heavily.

**R² Score**

Indicates how much of the variation in final innings scores is explained by the model.

These metrics help compare the models and understand how reliably they predict unseen match situations.

## 🏏 Making Predictions

After training, the selected model can estimate the final first innings score using the current match statistics.

For example, consider a match situation where:

| Feature | Value |
|---|---|
| Batting Team | Chennai Super Kings |
| Bowling Team | Mumbai Indians |
| Overs Completed | 10.2 |
| Current Score | 85 |
| Wickets Lost | 2 |
| Runs in Last 5 Overs | 43 |
| Wickets in Last 5 Overs | 1 |

The model uses these details to estimate the final score at the end of the innings.

Actual predictions may vary depending on the trained model.

## 🛠️ Technologies Used

- **Python** — Programming language
- **Pandas** — Data manipulation and preprocessing
- **NumPy** — Numerical operations
- **Matplotlib** — Data visualization
- **Seaborn** — Statistical visualizations
- **Scikit-learn** — Machine Learning models and evaluation
- **Google Colab / Jupyter Notebook** — Development environment

## 🚀 How to Run the Project

**1. Clone the repository**

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

**2. Navigate to the project directory**

```bash
cd YOUR_REPOSITORY
```

**3. Install the required libraries**

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib
```

**4. Run the notebook**

Open the `.ipynb` file in Google Colab, Jupyter Notebook, or VS Code.

Make sure `ipl.csv` is available in the correct directory, then execute the cells in order.

## 💡 What I Learned

Through this project, I explored:

- How regression algorithms work on real-world datasets
- The importance of cleaning and preprocessing data
- How to handle categorical features using encoding
- Why chronological splitting is useful for historical datasets
- How to compare different regression algorithms
- How MAE, RMSE, and R² help evaluate model performance
- How to turn match statistics into meaningful predictions

One interesting takeaway was that more complex models do not necessarily perform better. Comparing different algorithms helped me understand why evaluating models is just as important as training them.

## 🔮 Future Improvements

Some improvements I would like to explore:

- Including venue and pitch conditions
- Using more recent IPL data
- Adding player performance statistics
- Building an interactive Streamlit application
- Experimenting with additional regression algorithms
- Improving predictions during the final overs

## ⚠️ Limitations

Cricket is unpredictable, and factors such as sudden wickets, aggressive batting, weather, and unexpected changes in momentum can significantly affect the final score.

The model identifies patterns from historical data, but its predictions are estimates rather than guaranteed outcomes.

---

## 👩‍💻 About This Project

This is **Day 2 of my 100 Days, 100 Machine Learning Projects challenge**, where I'm building and documenting one ML project at a time to improve my practical understanding of Machine Learning.

The goal is not just to train models, but to understand how they work, experiment with different approaches, and share what I learn along the way.

**100 Days and 100 ML Projects. A lot of learning ahead! 🚀**

⭐ If you find this project helpful, consider starring the repository!
