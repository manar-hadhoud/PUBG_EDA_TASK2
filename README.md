# PUBG Weapon Analysis 
Analysis of weapons information to get full details about weapon and bullet type


Welcome to the **PUBG Weapon Analysis** project! This notebook is designed to explore and analyze weapon performance data from the popular game **PlayerUnknown's Battlegrounds (PUBG)**. The focus is on extracting actionable insights about weapon performance, damage drop, and suitability for various combat scenarios.

## Project Goals
- Perform **Exploratory Data Analysis (EDA)** on the PUBG weapon dataset.
- Identify weapons with minimal damage drop over long distances.
- Highlight weapons with significant differences between headshot and base damage.
- Compare weapon types to determine their performance across various conditions.
- Provide insights to players and developers for optimizing gameplay and weapon balancing.

---

## Dataset Overview

The dataset contains information about 44 PUBG weapons with 20 columns, including:
- **Weapon Attributes**: Name, Type, Magazine Capacity, Rate of Fire, etc.
- **Damage Metrics**:
  - Base Damage (BDMG) and Headshot Damage (HDMG) across different ranges.
  - Specific columns like `BDMG_0`, `BDMG_3`, `HDMG_0`, `HDMG_3` represent damage at close and long distances.

### Key Columns:
| Column Name            | Description                                   |
|------------------------|-----------------------------------------------|
| `Weapon Name`          | The name of the weapon.                      |
| `Weapon Type`          | The category or classification of the weapon (e.g., rifle, handgun, shotgun). |
| `Bullet Type`          | The type of bullet used with the weapon, represented as a numerical value (float). |
| `Damage`               | The amount of damage the weapon can inflict in one shot, represented as an integer. |
| `Magazine Capacity`    | The maximum number of rounds the weapon's magazine can hold, represented as an integer. |
| `Range`                | The effective distance (in meters or another unit) the weapon can hit a target, represented as a float. |
| `Bullet Speed`         | The speed at which the bullet travels after being fired, represented as a float. |
| `Rate of Fire`         | The number of shots the weapon can fire per minute, represented as a float. |
| `Shots to Kill (Chest)`| The number of shots required to kill an enemy target if the shots hit the chest area, represented as an integer. |
| `Shots to Kill (Head)` | The number of shots required to kill an enemy target if the shots hit the head area, represented as an integer. |
| `Damage Per Second`    | The total amount of damage the weapon can deal per second, calculated from damage and rate of fire, represented as a float. |
| `Fire Mode`            | The firing mechanism or mode of the weapon (e.g., semi-automatic, automatic), represented as an object/string. |
| `BDMG_0`               | Base damage at the closest range or under default conditions. |
| `BDMG_1`               | Base damage at a slightly longer range or different condition. |
| `BDMG_2`               | Base damage at an even longer range or another condition. |
| `BDMG_3`               | Base damage at the farthest range or extreme condition. |
| `HDMG_0`               | Headshot damage at the closest range or under default conditions. |
| `HDMG_1`               | Headshot damage at a slightly longer range or different condition. |
| `HDMG_2`               | Headshot damage at an even longer range or another condition. |
| `HDMG_3`               | Headshot damage at the farthest range or extreme condition. |

---

### Key Analysis:

#### 1. What are the different types of weapons (Weapon Type) and their counts?
- **Analysis**: Count the occurrences of each weapon type.
- **Findings**: The dataset includes weapon types such as Rifles, Snipers, SMGs, and Pistols, with varying counts for each category. For example, Rifles might dominate with the highest count.

#### 2. What are the key metrics for weapon performance?
- **Analysis**: Focus on `Damage`, `Rate of Fire`, `Damage Per Second`, and `Range` to determine the effectiveness of a weapon.
- **Findings**: Weapons with higher `Damage Per Second` and long `Range` are ideal for mid-to-long-range combat scenarios.

#### 3. How does bullet type affect performance?
- **Analysis**: Compare `Bullet Type` with metrics such as `Damage`, `Bullet Speed`, and `Range` to identify performance variations.
- **Findings**: Bullet types with higher speed may enhance accuracy, while those with higher damage values are more lethal at close range.

#### 4. Are there differences in Rate of Fire or Shots to Kill across Fire Mode?
- **Analysis**: Group by `Fire Mode` (e.g., semi-automatic, automatic) and analyze differences in `Rate of Fire` and `Shots to Kill` metrics.
- **Findings**: Automatic weapons generally have a higher `Rate of Fire` but may require more shots to kill compared to semi-automatic weapons.

#### 5. Compare Damage Across Weapon Types
- **Goal**: Find which weapon types (e.g., Rifle, Sniper) perform better at long ranges or for headshots.
- **Analysis**: Group data by `Weapon Type` and calculate the average `BDMG` and `HDMG` for each range level.
- **Visualization**: Use bar plots or heatmaps to compare.
- **Findings**: Snipers excel at long-range headshots, while SMGs are more effective at close-range combat.

#### 6. Identify Weapons with Minimal Damage Drop Over Long Distances
- **Goal**: Highlight weapons with consistent damage output at varying ranges.
- **Analysis**: Calculate the difference between `BDMG_0` and `BDMG_3` (Base Damage Drop) and `HDMG_0` and `HDMG_3` (Headshot Damage Drop).
- **Findings**: Weapons like `P18C` and `Uzi` exhibit minimal damage drop, making them reliable for longer engagements.

#### 7. Highlight Weapons with a Significant Gap Between Headshot and Base Damage
- **Goal**: Identify weapons optimized for headshots.
- **Analysis**: Compute the difference between `HDMG_0` and `BDMG_0`.
- **Findings**: Weapons with a larger gap favor skilled players aiming for headshots, such as Snipers and specific Rifles.

---

## Notebook Structure
1. **Introduction**: Overview of the project and objectives.
2. **Data Preparation**:
   - Loading and cleaning the dataset.
   - Handling missing values and outliers.
3. **Exploratory Data Analysis (EDA)**:
   - Analyzing base and headshot damage metrics.
   - Visualizing damage drops using line plots and bar charts.
4. **Insights and Conclusions**:
   - Summarizing findings.
   - Highlighting recommendations for players and developers.
5. **Visualizations**:
   - Interactive dashboards for storytelling.
   - Static visualizations for key metrics.

---

## How to Use
1. **Environment Setup**:
   - Ensure you have Python 3.8+ installed.
   - Install required libraries using the command:
     ```bash
     pip install pandas matplotlib seaborn jupyter
     ```
2. **Run the Notebook**:
   - Open the notebook `PUBG_EDA.ipynb` using Jupyter Notebook or JupyterLab.
   - Execute each cell sequentially to perform the analysis.
3. **Explore the Visualizations**:
   - Use the plots and dashboards to gain insights into weapon performance.

---

## Sample Insights
- **Weapons with Minimal Damage Drop**:
  - P18C, Uzi, Vector show the least damage loss over long distances.
- **Headshot Efficiency**:
  - Weapons like Snipers exhibit significant gaps between headshot and base damage, making them ideal for precision combat.
- **Weapon Type Comparison**:
  - Rifles tend to perform well at mid-range, while Snipers dominate long-range engagements.

---

## Future Work
- Integrate advanced visualizations using tools like Plotly or Dash.
- Perform predictive modeling to estimate weapon effectiveness in hypothetical scenarios.
- Explore player behavior data to correlate weapon preferences with performance.

---

## Contributing
We welcome contributions! If you have suggestions or enhancements, feel free to:
- Fork this repository.
- Submit a pull request with your improvements.

---

## License
This project is licensed under the MIT License. See the LICENSE file for more details.

---

Happy analyzing! 🎮
