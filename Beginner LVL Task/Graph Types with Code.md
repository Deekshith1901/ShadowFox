# 🎨 Visualization Gallery: Matplotlib & Seaborn Masterpieces 🖼️

---

## 📊 Matplotlib Creations

### 1. 🌊 Ocean Waves Simulation - Advanced Line Plot
**Description**: Simulates ocean wave patterns with mathematical precision, showing wave interference  
**Use Case**: Time series analysis, wave physics, signal processing 🌊  
```python
import matplotlib.pyplot as plt
import numpy as np

# Generate ocean wave data
x = np.linspace(0, 4*np.pi, 200)
wave1 = np.sin(x) * 2
wave2 = np.sin(2*x + np.pi/4) * 1.5
combined = wave1 + wave2

# Create ocean visualization
plt.figure(figsize=(14, 8), facecolor='#001f3f')
plt.fill_between(x, combined, alpha=0.6, color='#0074D9', label='Combined Waves')
plt.plot(x, wave1, '--', color='#39CCCC', linewidth=2, label='Primary Wave')
plt.plot(x, wave2, ':', color='#7FDBFF', linewidth=2, label='Secondary Wave')
plt.fill_between(x, combined, -2, alpha=0.3, color='#001f3f')

# Styling
plt.title('🌊 Ocean Wave Simulation: Wave Interference Patterns', 
          fontsize=18, color='white', pad=20)
plt.xlabel('Distance (meters) 📏', fontsize=14, color='white')
plt.ylabel('Wave Height (meters) 📊', fontsize=14, color='white')
plt.legend(loc='upper right', framealpha=0.9)
plt.grid(True, alpha=0.2, color='white')
plt.ylim(-4, 4)
plt.gca().set_facecolor('#003366')
plt.tight_layout()
plt.show()
```

### 2. 🌌 Galaxy Cluster - Advanced Scatter Plot
**Description**: Visualizes astronomical data with color and size mapping, showing star distributions

**Use Case**: Astronomy data analysis, clustering visualization, spatial data mapping 🌌

```
import matplotlib.pyplot as plt
import numpy as np

# Generate galaxy data
np.random.seed(42)
n_stars = 300
x = np.random.normal(0, 10, n_stars)
y = np.random.normal(0, 8, n_stars)
sizes = np.random.uniform(10, 200, n_stars)
colors = np.random.uniform(0, 1, n_stars)

# Create galaxy visualization
plt.figure(figsize=(16, 10), facecolor='black')
scatter = plt.scatter(x, y, c=colors, s=sizes, alpha=0.7, 
                     cmap='plasma', edgecolors='white', linewidth=0.5)

# Add annotations
plt.annotate('🌟 Supergiant', xy=(x[0], y[0]), 
             xytext=(x[0]+3, y[0]+3),
             arrowprops=dict(facecolor='yellow', shrink=0.05),
             fontsize=12, color='yellow')

# Styling
plt.colorbar(scatter, label='Star Temperature (K) 🔥', shrink=0.8)
plt.title('🌌 Galaxy Cluster: Star Distribution Analysis', 
          fontsize=20, color='white', pad=20)
plt.xlabel('Distance (light-years) 🌠', fontsize=14, color='white')
plt.ylabel('Distance (light-years) 🌠', fontsize=14, color='white')
plt.grid(True, alpha=0.2, color='white')
plt.gca().set_facecolor('#0a0a0a')
plt.tight_layout()
plt.show()
```
### 3. 🏆 Olympic Medal Standings - Advanced Bar Chart
**Description**: Visualizes Olympic medal counts with stacked bars and custom styling

**Use Case**: Sports analytics, ranking visualization, categorical comparisons 🏆

```
import matplotlib.pyplot as plt
import numpy as np

# Olympic data
countries = ['🇺🇸 USA', '🇨🇳 China', '🇯🇵 Japan', '🇬🇧 UK', '🇷🇺 Russia']
gold = np.array([39, 38, 27, 22, 20])
silver = np.array([41, 32, 14, 21, 28])
bronze = np.array([33, 18, 17, 22, 23])

# Create stacked bar chart
plt.figure(figsize=(14, 8), facecolor='#f8f8ff')
bar_width = 0.6

plt.bar(countries, gold, bar_width, label='Gold 🥇', color='#FFD700', edgecolor='black')
plt.bar(countries, silver, bar_width, bottom=gold, label='Silver 🥈', color='#C0C0C0', edgecolor='black')
plt.bar(countries, bronze, bar_width, bottom=gold+silver, label='Bronze 🥉', color='#CD7F32', edgecolor='black')

# Add value labels
for i, country in enumerate(countries):
    total = gold[i] + silver[i] + bronze[i]
    plt.text(i, total + 1, str(total), ha='center', fontweight='bold')

# Styling
plt.title('🏆 Olympic Medal Standings: Total Medal Count', fontsize=18, pad=20)
plt.xlabel('Countries 🌍', fontsize=14)
plt.ylabel('Number of Medals 🏅', fontsize=14)
plt.legend(loc='upper right')
plt.grid(axis='y', alpha=0.3)
plt.tight_layout()
plt.show()
```

### 4. 🥧 Digital Life Pie Chart - Advanced Pie Chart
**Description**: Visualizes digital device usage with exploded slices and custom styling

**Use Case**: Market share analysis, usage statistics, proportional data 🥧

```
import matplotlib.pyplot as plt

# Digital device usage data
devices = ['📱 Smartphone', '💻 Laptop', '🖥️ Desktop', '📺 Tablet', '⌚ Smartwatch']
usage = [45, 30, 15, 7, 3]
colors = ['#1f77b4', '#ff7f0e', '#2ca02c', '#d62728', '#9467bd']
explode = (0.1, 0.05, 0, 0, 0)

# Create pie chart
plt.figure(figsize=(12, 10))
wedges, texts, autotexts = plt.pie(usage, explode=explode, labels=devices, 
                                  colors=colors, autopct='%1.1f%%',
                                  shadow=True, startangle=90,
                                  wedgeprops={'linewidth': 2, 'edgecolor': 'white'})

# Customize text
for autotext in autotexts:
    autotext.set_color('white')
    autotext.set_fontweight('bold')
    autotext.set_fontsize(12)

# Styling
plt.title('📱 Digital Life: Daily Device Usage Distribution', fontsize=18, pad=20)
plt.axis('equal')

# Add donut effect
centre_circle = plt.Circle((0,0), 0.70, fc='white')
fig = plt.gcf()
fig.gca().add_artist(centre_circle)

plt.tight_layout()
plt.show()
```

### 5. 📊 City Climate Profiles - Advanced Histogram
**Description**: Analyzes temperature distributions with statistical overlays for different cities

**Use Case**: Climate analysis, weather data visualization, distribution comparison 🌡️

```
import matplotlib.pyplot as plt
import numpy as np
from scipy.stats import norm

# Generate temperature data
np.random.seed(42)
nyc_temps = np.random.normal(12, 8, 365)
miami_temps = np.random.normal(25, 4, 365)
reykjavik_temps = np.random.normal(4, 6, 365)

# Create histogram with statistical overlays
plt.figure(figsize=(14, 8), facecolor='#f0f0f0')

# Plot histograms
plt.hist(nyc_temps, bins=30, alpha=0.6, color='#1f77b4', 
         label='🗽 New York', density=True)
plt.hist(miami_temps, bins=30, alpha=0.6, color='#ff7f0e', 
         label='🌴 Miami', density=True)
plt.hist(reykjavik_temps, bins=30, alpha=0.6, color='#2ca02c', 
         label='🏔️ Reykjavik', density=True)

# Add normal distribution curves
xmin, xmax = plt.xlim()
x = np.linspace(xmin, xmax, 100)
plt.plot(x, norm.pdf(x, 12, 8), 'b-', linewidth=3)
plt.plot(x, norm.pdf(x, 25, 4), 'orange', linewidth=3)
plt.plot(x, norm.pdf(x, 4, 6), 'g-', linewidth=3)

# Styling
plt.title('🌡️ City Climate Profiles: Temperature Distribution Analysis', 
          fontsize=18, pad=20)
plt.xlabel('Temperature (°C) 🌡️', fontsize=14)
plt.ylabel('Probability Density 📊', fontsize=14)
plt.legend(loc='upper right')
plt.grid(alpha=0.3)
plt.tight_layout()
plt.show()
```

## 🎨 Seaborn Masterpieces

### 1. 🎻 Orchestra Performance Analysis - Advanced Violin Plot
**Description**: Analyzes instrument volume distributions in a symphony orchestra with section categorization

**Use Case**: Audio analysis, performance metrics, categorical distribution comparison 🎼

```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np

# Create musical performance data
np.random.seed(42)
data = pd.DataFrame({
    'Instrument': np.repeat(['🎻 Violin', '🎺 Trumpet', '🥁 Drums', '🎹 Piano', '🎷 Saxophone'], 80),
    'Volume': np.concatenate([
        np.random.normal(75, 12, 80),
        np.random.normal(88, 8, 80),
        np.random.normal(92, 15, 80),
        np.random.normal(70, 10, 80),
        np.random.normal(85, 9, 80)
    ]),
    'Section': np.tile(['String', 'Brass', 'Percussion', 'String', 'Woodwind'], 80)
})

# Create orchestra visualization
plt.figure(figsize=(16, 10), facecolor='#1a1a1a')
sns.violinplot(x='Instrument', y='Volume', hue='Section', data=data,
               palette=['#8B4513', '#FFD700', '#4B0082', '#32CD32', '#FF6347'],
               inner='box', linewidth=2, split=False)

# Add performance annotations
plt.axhline(y=85, color='red', linestyle='--', alpha=0.7, label='Target Volume')
plt.text(2, 87, '🎯 Target Volume', color='red', fontsize=12)

# Styling
plt.title('🎼 Orchestra Performance: Volume Distribution by Instrument Section', 
          fontsize=18, color='white', pad=20)
plt.xlabel('Instruments 🎻', fontsize=14, color='white')
plt.ylabel('Volume (dB) 🔊', fontsize=14, color='white')
plt.legend(title='Section', loc='upper right')
plt.grid(axis='y', alpha=0.2, color='white')
plt.gca().set_facecolor('#2b2b2b')
plt.tight_layout()
plt.show()
```

### 2. 🔥 Climate Change Heatmap - Advanced Correlation Analysis
**Description**: Visualizes temperature and precipitation correlations across decades with temporal trends

**Use Case**: Environmental science, climate research, temporal pattern analysis 🌡️

```
import seaborn as sns
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd

# Create climate data over decades
years = [f'199{i}' for i in range(10)] + [f'200{i}' for i in range(10)] + [f'201{i}' for i in range(14)]
metrics = ['Temperature', 'Precipitation', 'Humidity', 'Wind Speed', 'Pressure']

# Generate correlation matrix with trends
data = np.random.randn(34, 5)
data[:, 0] += np.linspace(0, 2, 34)  # Temperature increasing
data[:, 1] -= np.linspace(0, 1.5, 34)  # Precipitation decreasing
data[:, 3] += np.linspace(0, 1, 34)   # Wind speed increasing

corr_matrix = np.corrcoef(data.T)

# Create climate heatmap
plt.figure(figsize=(14, 12), facecolor='#000814')
mask = np.triu(np.ones_like(corr_matrix, dtype=bool))

sns.heatmap(corr_matrix, mask=mask, annot=True, fmt='.2f', 
            cmap='RdYlBu_r', center=0, square=True,
            linewidths=2, cbar_kws={'shrink': 0.8, 'label': 'Correlation Coefficient'})

# Add climate annotations
plt.title('🌡️ Climate Change: Environmental Factors Correlation (1990-2023)', 
          fontsize=18, color='white', pad=20)
plt.xticks(np.arange(len(metrics)) + 0.5, metrics, rotation=45, ha='right', color='white')
plt.yticks(np.arange(len(metrics)) + 0.5, metrics, rotation=0, color='white')
plt.tight_layout()
plt.show()
```

### 3. 🌸 Botanical Garden Analysis - Advanced Pair Plot
**Description**: Analyzes relationships between plant characteristics in a botanical garden with species categorization

**Use Case**: Biology research, agricultural science, multivariate analysis 🌺

```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np

# Create botanical garden data
np.random.seed(42)
n_plants = 150
data = pd.DataFrame({
    '🌹 Petal Length': np.random.normal(5.5, 1.8, n_plants),
    '🌿 Leaf Width': np.random.normal(3.2, 0.9, n_plants),
    '🌻 Stem Height': np.random.normal(18.5, 4.2, n_plants),
    '🌺 Bloom Size': np.random.normal(8.8, 2.1, n_plants),
    'Species': np.random.choice(['Rose', 'Sunflower', 'Tulip', 'Orchid'], n_plants)
})

# Create garden pair plot
g = sns.PairGrid(data, hue='Species', palette='Set2',
                 diag_sharey=False, height=2.5)

# Map different plot types
g.map_upper(sns.scatterplot, alpha=0.7, s=50)
g.map_lower(sns.kdeplot, fill=True, alpha=0.6)
g.map_diag(sns.histplot, kde=True, alpha=0.7)

# Add styling
g.fig.suptitle('🌸 Botanical Garden: Multivariate Plant Analysis', 
               y=1.02, fontsize=16, fontweight='bold')
g.add_legend(title='Plant Species', bbox_to_anchor=(1.05, 1), loc='upper left')

# Adjust layout
plt.tight_layout()
plt.show()
```

### 4. 📦 E-commerce Product Analysis - Advanced Box Plot
**Description**: Analyzes customer ratings across product categories and price ranges with swarm overlay

**Use Case**: Business analytics, customer satisfaction analysis, market research 🛍️

```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np

# Create e-commerce data
np.random.seed(42)
categories = ['Electronics', 'Clothing', 'Books', 'Home & Garden', 'Sports']
price_ranges = ['Budget', 'Mid-range', 'Premium']

# Generate rating data
data = []
for category in categories:
    for price_range in price_ranges:
        n_products = 40
        if category == 'Electronics':
            ratings = np.random.normal(4.2, 0.8, n_products)
        elif category == 'Clothing':
            ratings = np.random.normal(3.8, 1.0, n_products)
        else:
            ratings = np.random.normal(4.0, 0.9, n_products)
        
        for rating in ratings:
            data.append([category, price_range, rating])

df = pd.DataFrame(data, columns=['Category', 'Price Range', 'Rating'])

# Create comprehensive box plot
plt.figure(figsize=(16, 10))
sns.boxplot(x='Category', y='Rating', hue='Price Range', data=df,
            palette='viridis', width=0.7, linewidth=2)

# Add swarm plot for individual data points
sns.swarmplot(x='Category', y='Rating', hue='Price Range', data=df,
              palette='viridis', dodge=True, alpha=0.7, size=4)

# Add rating benchmarks
plt.axhline(y=4.5, color='gold', linestyle='--', linewidth=2, label='Excellent')
plt.axhline(y=3.5, color='orange', linestyle='--', linewidth=2, label='Good')

# Styling
plt.title('📦 E-commerce Analysis: Customer Ratings by Category and Price Range', 
          fontsize=16, pad=20)
plt.xlabel('Product Categories 🛍️', fontsize=12)
plt.ylabel('Customer Ratings ⭐', fontsize=12)
plt.legend(title='Price Range', bbox_to_anchor=(1.05, 1), loc='upper left')
plt.grid(axis='y', alpha=0.3)
plt.ylim(0, 5.5)
plt.tight_layout()
plt.show()
```

### 5. 📈 Fitness Progress Tracking - Advanced Regression Plot
**Description**: Analyzes the relationship between workout duration and fitness progress with polynomial fitting

**Use Case**: Health analytics, performance tracking, trend analysis 🏃‍♂️

```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
from scipy import stats

# Create fitness tracking data
np.random.seed(42)
n_participants = 100
workout_duration = np.random.uniform(20, 120, n_participants)

# Create non-linear relationship with noise
fitness_progress = 20 + 0.8 * workout_duration - 0.003 * workout_duration**2 + np.random.normal(0, 8, n_participants)
fitness_progress = np.clip(fitness_progress, 0, 100)

# Add participant categories
age_group = np.random.choice(['18-25', '26-35', '36-45'], n_participants)

df = pd.DataFrame({
    'Workout Duration (min)': workout_duration,
    'Fitness Progress (%)': fitness_progress,
    'Age Group': age_group
})

# Create advanced regression plot
plt.figure(figsize=(14, 10))

# Plot with polynomial regression
sns.regplot(x='Workout Duration (min)', y='Fitness Progress (%)', data=df,
            scatter_kws={'alpha': 0.6, 's': 50, 'color': '#4CAF50'},
            line_kws={'color': '#FF5722', 'linewidth': 3},
            order=2, ci=95, truncate=False)

# Add confidence interval shading
x_grid = np.linspace(df['Workout Duration (min)'].min(), df['Workout Duration (min)'].max(), 100)
y_pred = 20 + 0.8 * x_grid - 0.003 * x_grid**2
residuals = np.std(df['Fitness Progress (%)'] - (20 + 0.8 * df['Workout Duration (min)'] - 0.003 * df['Workout Duration (min)']**2))
plt.fill_between(x_grid, y_pred - 1.96*residuals, y_pred + 1.96*residuals, 
                 alpha=0.2, color='#FF5722', label='95% Confidence Interval')

# Add optimal workout zone
plt.axvspan(60, 90, alpha=0.2, color='yellow', label='Optimal Duration')
plt.text(75, 90, '🎯 Optimal\nZone', ha='center', fontsize=12, fontweight='bold')

# Styling
plt.title('🏃‍♂️ Fitness Progress Analysis: Workout Duration vs Results', 
          fontsize=16, pad=20)
plt.xlabel('Workout Duration (minutes) ⏱️', fontsize=12)
plt.ylabel('Fitness Progress (%) 📈', fontsize=12)
plt.legend(loc='upper right')
plt.grid(alpha=0.3)
plt.xlim(15, 125)
plt.ylim(0, 105)
plt.tight_layout()
plt.show()
```
