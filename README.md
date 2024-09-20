# 🌍 Meteorite Data Analysis Project 🌠

📚 Overview
This project analyzes a dataset of meteorite landings to explore various patterns and distributions. The dataset, obtained from NASA's Open Data Portal, contains information about all known meteorite landings, including their masses, locations, and whether they were seen falling or found after impact.

This project is split into multiple sections, each examining different aspects of the meteorite data, such as the geographical distribution of meteorite landings, hypothesis tests to check if observed trends are significant, and the creation of confidence intervals for meteorite masses. The key tools used for analysis include hypothesis testing, permutation tests, bootstrapping, and interactive visualization of the data.

##🗂 Dataset Description
The dataset includes 38,094 rows and 9 columns, with each row representing a meteorite. The columns are as follows:

id: Unique identifier for each meteorite.
name: Name of the meteorite.
recclass: Classification of the meteorite.
seen_falling: Boolean indicating if the meteorite was observed while falling.
mass: The mass of the meteorite in grams.
year: The year when the meteorite was recorded.
decade: The decade in which the meteorite was recorded.
latitude: Latitude of the location where the meteorite was found.
longitude: Longitude of the location where the meteorite was found.
🗺 Additional Dataset:
Continents Data: Provides a mapping between meteorite IDs and the continents where they were found.

##🔍 Key Analyses

###1. 🌍 Geographical Distribution of Meteorites
The dataset contains precise latitude and longitude coordinates for each meteorite, which were mapped to their respective continents. Visualizations were created to map meteorite locations and to compare where meteorites were seen falling vs. where they were found after the fall.

We analyzed how many meteorites were seen falling vs. those found later and calculated the density of meteorites recorded per continent by normalizing by land area.

2. 🎲 Probability Analysis
We examined the relationship between the number of meteorites seen falling and the population density of different continents. Assuming meteorites are more likely to be seen in populated areas, we computed the probabilities of meteorites falling in each continent using population data from satellite images.

Several probability-based questions were tackled using both theoretical probability models and simulations. This included the likelihood of seeing meteorites land in specific continents, calculating probabilities of meteorites falling in specific combinations of continents, and using Monte Carlo simulations to explore distributions.

3. 🧪 Hypothesis Testing with TVD (Total Variation Distance)
Null Hypothesis: Meteorites seen falling since 1980 were drawn from the same distribution as the population densities of different continents.
Alternative Hypothesis: Meteorites seen falling were not drawn from this distribution, and differences are not due to chance alone.
We used the Total Variation Distance (TVD) as the test statistic to measure the difference between observed and theoretical proportions of meteorites seen falling in each continent. Simulated test statistics were generated through Monte Carlo simulations, and a p-value was computed to assess the significance of the observed differences.

4. ✈️ Long-Distance Relationship: Permutation Tests
We examined the hypothesis that meteorites seen falling in Asia are heavier than those seen falling in North America. We used a permutation test to compare the medians of the meteorite masses between the two continents:
Null Hypothesis: The masses of meteorites seen falling in Asia and North America come from the same distribution.
Alternative Hypothesis: The median mass of meteorites in Asia is higher than in North America.
After performing 1,000 simulations, we observed that the difference in medians could be due to chance. The permutation test was optimized using a faster permutation method to handle large datasets efficiently.
5. 📊 Confidence Intervals for Meteorite Masses
We used bootstrapping to estimate confidence intervals for the true median mass of meteorites seen falling in each continent. Bootstrapping allowed us to create a large number of resamples and compute medians for each, ultimately constructing a 95% confidence interval for the median.

Additionally, we constructed confidence intervals for the mean mass of meteorites in each continent using the Central Limit Theorem (CLT). We used normal approximation to calculate these intervals, leveraging the properties of large sample sizes.

6. 📅 Decadal Trends in Meteorite Masses
We analyzed the trend of meteorite masses over time by calculating the median mass of meteorites seen falling in each decade since 1900. We then visualized these "decadal medians" to observe any potential patterns.

A hypothesis test was performed to check whether the unusually high median mass in the 2000s decade could be attributed to random chance:

Null Hypothesis: The mass distribution of meteorites is independent of the decade.
Alternative Hypothesis: The high median mass in the 2000s is not due to chance.
We performed 1,000 simulations by randomly selecting meteorites from the entire dataset to generate a distribution of median masses. The p-value indicated whether the observed median in the 2000s was significantly higher than expected by chance.

7. 🎛 Interactive Widgets for Exploratory Analysis
To further investigate potential trends in meteorite masses by decade, we incorporated interactive visualizations that allowed us to test the hypothesis for different decades dynamically.
For each decade, we assessed whether the median mass was unexpectedly high or low compared to random samples drawn from the entire period.

##📂 Project Structure
Code Implementation: The project is implemented using Python with key packages like pandas, numpy, matplotlib, folium, and scipy.stats. babypandas was used to simplify certain DataFrame manipulations.
Visualizations: Various plots, including histograms, line plots, and geographical maps, were created to visualize the meteorite data and results from hypothesis tests.
Statistical Techniques: Hypothesis testing, permutation tests, bootstrapping, and confidence interval calculations are key methods used to explore the data and test assumptions.

##🎯 Conclusion
This project comprehensively analyzed a large dataset of meteorite landings, explored trends in their geographical and temporal distributions, and used various statistical methods to test hypotheses about the data. The results provide insights into the potential factors that affect meteorite sightings and the characteristics of the meteorites themselves.
