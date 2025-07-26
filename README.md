# Volleyball Nations League 2023 - Exploratory Data Analysis (EDA) Report

This document provides a detailed report of the exploratory data analysis (EDA) performed on the Volleyball Nations League (VNL) 2023 dataset (`VNL2023.csv`). The dataset contains performance statistics for volleyball players, including their attack, block, serve, set, dig, receive, and position, along with their country and age. The analysis was conducted using Python with libraries such as `pandas`, `numpy`, `matplotlib`, and `seaborn`. Below are the key findings from the EDA, organized by section.


![image alt](https://github.com/Raka-Deb/Volleyball-Analysis-/blob/b131f716d2e7522279d8610462bb7daa6eea138d/Vollyball.avif)




## Dataset Overview

- **Source**: The dataset is stored in `VNL2023.csv`.
- **Shape**: The dataset consists of **131 rows** and **10 columns**.
- **Columns**:
  - `Player`: Player's name (string).
  - `Country`: Country of the player (string).
  - `Age`: Player's age (integer).
  - `Attack`: Average attack points per match (float).
  - `Block`: Average blocks per match (float).
  - `Serve`: Average serve points per match (float).
  - `Set`: Average sets per match (float).
  - `Dig`: Average digs per match (float).
  - `Receive`: Average receptions per match (float).
  - `Position`: Player's position (string, e.g., OH - Outside Hitter, OP - Opposite, L - Libero).

## Data Quality Assessment

### Missing Values
- **Finding**: There are **no missing values** in any of the columns. This indicates that the dataset is complete and does not require imputation or removal of rows due to missing data.

### Duplicate Rows
- **Finding**: There are **no duplicate rows** in the dataset. Each row represents a unique player, ensuring data integrity for analysis.

## Summary Statistics

The summary statistics for the numeric columns (`Age`, `Attack`, `Block`, `Serve`, `Set`, `Dig`, `Receive`) provide insights into the distribution of player performance metrics:

- **Age**:
  - Mean: 27.81 years
  - Standard Deviation: 4.19 years
  - Min: 19 years
  - Max: 41 years
  - Interpretation: The players' ages range widely, with most players being in their mid-20s to early 30s, but some outliers (e.g., 41 years) suggest veteran players in the league.

- **Attack**:
  - Mean: 5.64 points
  - Standard Deviation: 4.26 points
  - Min: 0.00 points
  - Max: 15.80 points
  - Interpretation: Attack performance varies significantly, with top attackers (e.g., Ichikawa Yuki from Japan with 15.80 points) contributing substantially more than others. A minimum of 0 suggests some players, likely liberos, do not contribute to attack points.

- **Block**:
  - Mean: 0.85 blocks
  - Standard Deviation: 0.70 blocks
  - Min: 0.00 blocks
  - Max: 4.08 blocks
  - Interpretation: Blocking performance also shows variability, with some players excelling (max of 4.08) while others, likely non-defensive positions like liberos, have zero blocks.

- **Serve**:
  - Mean: 0.54 points
  - Standard Deviation: 0.45 points
  - Min: 0.00 points
  - Max: 2.08 points
  - Interpretation: Serve points are generally low, with a few players (e.g., Abdel-Aziz Nimir from Nederland with 2.08) standing out for their serving ability.

- **Set**:
  - Mean: 2.19 sets
  - Standard Deviation: 6.03 sets
  - Min: 0.00 sets
  - Max: 26.89 sets
  - Interpretation: The high standard deviation and maximum value suggest that setters (players responsible for setting the ball) have significantly higher values, while most players (non-setters) have zero or near-zero sets.

- **Dig**:
  - Mean: 3.43 digs
  - Standard Deviation: 2.08 digs
  - Min: 0.53 digs
  - Max: 11.44 digs
  - Interpretation: Digs, a defensive metric, show moderate variability. Players like Balaso Fabio from Italy (10.00 digs) excel in this area, likely due to their libero position.

- **Receive**:
  - Mean: 1.68 receptions
  - Standard Deviation: 1.99 receptions
  - Min: 0.00 receptions
  - Max: 6.69 receptions
  - Interpretation: Reception performance varies, with some players (likely outside hitters or liberos) having high values, while others (e.g., opposites) have minimal or no receptions.

## Correlation Analysis

A correlation matrix was computed for the numeric columns to identify relationships between performance metrics:

- **Key Correlations**:
  - **Attack ↔ Serve (0.77)**: A strong positive correlation indicates that players who excel in attacking also tend to perform well in serving. This may reflect the aggressive playing style of players in offensive positions (e.g., opposites or outside hitters).
  - **Dig ↔ Receive (0.62)**: A strong positive correlation suggests that players who are good at digging (defensive plays) are also proficient at receiving serves, which aligns with the role of liberos and defensive players.
  - **Block ↔ Attack (0.34)**: A moderate positive correlation indicates that players who contribute to attacks often also contribute to blocks, likely due to their front-row positions (e.g., middle blockers or opposites).
  - **Set ↔ Attack (-0.43)**: A moderate negative correlation suggests that players who focus on setting (setters) contribute less to attacks, reflecting their specialized role.
  - **Dig ↔ Block (-0.35)**: A moderate negative correlation indicates that players who excel at digging (e.g., liberos) are less likely to contribute to blocks, as liberos typically play in the back row.

## Data Visualizations

### Stacked Bar Chart: Total Attack and Block by Country
- A stacked bar chart was created to visualize the total attack and block points by country, sorted by attack values in descending order.
- **Key Findings**:
  - **France and Japan** stand out with the highest combined attack and block values, indicating strong offensive and defensive capabilities.
  - Countries like Italy, Nederland, and Cuba also show significant contributions, particularly in attack points.
  - The chart highlights the dominance of certain teams in offensive (attack) and defensive (block) metrics, with France and Japan leading.

## Player Performance Highlights

### Top Performers
- **Attack**:
  - Ichikawa Yuki (Japan): 15.80 points
  - Abdel-Aziz Nimir (Nederland): 15.33 points
  - Herrera Jaime Jesus (Cuba): 15.00 points
- **Block**:
  - (Not explicitly listed, but max block is 4.08, indicating strong blockers in the dataset).
- **Serve**:
  - Abdel-Aziz Nimir (Nederland): 2.08 points
  - Herrera Jaime Jesus (Cuba): 1.75 points
- **Dig**:
  - Balaso Fabio (Italy): 10.00 digs
  - Takahashi Ran (Japan): 6.40 digs
- **Receive**:
  - Ichikawa Yuki (Japan): 5.60 receptions
  - Takahashi Ran (Japan): 5.07 receptions

### Positional Insights
- **Outside Hitters (OH)**: Players like Ichikawa Yuki and Takahashi Ran show high attack and receive values, reflecting their dual role in offense and defense.
- **Opposites (OP)**: Players like Romano Yuri, Abdel-Aziz Nimir, and Herrera Jaime Jesus excel in attack and serve but have low or zero receive values, consistent with their primarily offensive role.
- **Liberos (L)**: Players like Balaso Fabio, Graven Leonard, and Salparov Teodor have high dig and receive values but zero contributions in attack, block, or serve, aligning with their defensive specialization.

## Key Insights

1. **Team Performance**:
   - France and Japan are leading teams in terms of combined attack and block performance, suggesting they have well-rounded players contributing to both offensive and defensive plays.
   - Other notable teams include Italy, Nederland, and Cuba, particularly in attack metrics.

2. **Player Roles**:
   - The dataset clearly differentiates player roles based on performance metrics:
     - **Setters**: High set values, low attack and block.
     - **Liberos**: High dig and receive values, zero attack and block.
     - **Outside Hitters**: Balanced attack, dig, and receive.
     - **Opposites**: High attack and serve, low receive.
     - **Middle Blockers**: Likely contributing to high block values, though specific players are not highlighted in the provided output.

3. **Performance Variability**:
   - Metrics like attack, set, and dig show high variability (large standard deviations), indicating significant differences in player contributions based on their roles.
   - The wide range in age (19 to 41) suggests a mix of young talent and experienced veterans in the league.

4. **Correlations**:
   - The strong correlation between attack and serve highlights the importance of versatile offensive players.
   - The dig-receive correlation underscores the defensive synergy in players like liberos and outside hitters.
   - Negative correlations (e.g., set vs. attack) reflect the specialized nature of certain positions.

## Recommendations for Further Analysis

1. **Positional Analysis**:
   - Group players by position (OH, OP, L, etc.) and compute average performance metrics to better understand role-specific contributions.
   - Investigate whether certain positions dominate specific metrics (e.g., middle blockers for blocks).

2. **Team-Level Analysis**:
   - Analyze team performance by aggregating individual player stats to identify which countries have the most balanced or specialized rosters.
   - Compare top-performing countries (e.g., France, Japan) to identify strategic differences.

3. **Age and Performance**:
   - Explore the relationship between age and performance metrics to determine if younger or older players excel in specific areas (e.g., attack vs. dig).
   - Use scatter plots or regression analysis to visualize trends.

4. **Additional Visualizations**:
   - Create box plots for each performance metric to visualize outliers and distributions.
   - Use heatmaps to further explore the correlation matrix visually.
   - Plot individual player performance (e.g., top 10 attackers) to highlight standout performers.

5. **Performance Trends**:
   - If additional data (e.g., match-by-match stats) is available, analyze trends over time to identify improving or declining players.
   - Investigate whether certain countries or positions show consistent performance across matches.

## Conclusion

The VNL 2023 dataset provides a comprehensive view of player performance across various metrics, highlighting the diversity of roles and contributions in professional volleyball. France and Japan emerge as top-performing teams, with players like Ichikawa Yuki, Abdel-Aziz Nimir, and Balaso Fabio standing out in their respective roles. The absence of missing values and duplicates ensures a clean dataset for analysis. The correlations and visualizations reveal key relationships between metrics, offering insights into player specialization and team strengths. Further analysis, particularly by position and team, could provide deeper insights into strategic trends and player development in the Volleyball Nations League.
