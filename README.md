
# **World Bank Global Education Analysis**

The World Bank EdStats All Indicator Query holds over 4,000 internationally comparable indicators that describe education access, progression, completion, literacy, teachers, population, and expenditures. The indicators cover the education cycle from pre-primary to vocational and tertiary education.The query also holds learning outcome data from international and regional learning assessments (e.g. PISA, TIMSS, PIRLS), equity data from household surveys, and projection/attainment data to 2050.

# **Objective**
I have been provided with a World bank global education analysis dataset.

Our main objective is to perform EDA on the given dataset and draw useful conclusions about general trends in education, including how factors influence the education system and its outcomes.

# **Dataset**
The World Bank Global Education Analysis dataset comprises five distinct datasets, each contributing valuable insights into the educational landscape across countries. These datasets encompass a broad range of indicators, providing a comprehensive perspective on the evolution of education-related metrics over time.

1. **EdStatsData**

  **Variables**: ['Country Name', 'Country Code', 'Indicator Name', 'Indicator Code', ... '2100', 'Unnamed: 69']

  **Key Features**: The primary dataset serves as the backbone, containing crucial information such as country names, codes, indicator details, and yearly data spanning from 1970 to 2100.

  **Scope**: This dataset covers a wide array of indicators, facilitating in-depth analyses of educational trends and developments on a global scale.


2. **EdStatsCountry**

  **Variables**: ['Country Code', 'Short Name', 'Table Name', 'Long Name', ... 'Unnamed: 31']

  **Key Features**: This dataset offers detailed country-specific information, including economic groupings, national accounts, lending categories, and demographic details.

  **Usage**: It serves as a reference for contextualizing education-related indicators within broader economic and demographic contexts.


3. **EdStatsCountrySeries**

  **Variables**: ['CountryCode', 'SeriesCode', 'DESCRIPTION', 'Unnamed: 3']

 **Key Features**: Focused on categorizing indicators, this dataset provides a bridge between countries and specific series, facilitating streamlined access to relevant data points.

  **Facilitation**: Helps organize and streamline the accessibility of indicators based on series classifications.


4. **EdStatsSeries**

  **Variables**: ['Series Code', 'Topic', 'Indicator Name', 'Short definition', ... 'Unnamed: 20']

 **Key Features**: This dataset delves into the details of individual indicators, offering comprehensive information on topics, definitions, units of measure, and data sources.

  **Insight Generation**: Essential for understanding the nuances of each educational indicator and its relevance within the global education landscape.


5. **EdStatsFootNote**

  **Variables**: ['CountryCode', 'SeriesCode', 'Year', 'DESCRIPTION', 'Unnamed: 4']

  **Key Features**: This dataset contains footnotes related to specific indicators, providing additional context, limitations, and exceptions associated with the data.

  **Clarification**: Offers insights into the intricacies of the dataset and enhances transparency by highlighting relevant contextual information.


**Utilization and Impact:**

  The World Bank Global Education Analysis dataset, with its multi-faceted structure, empowers researchers, policymakers, and analysts to conduct detailed examinations of educational trends, compare country-level performances, and draw meaningful conclusions to inform global education strategies.

  This dataset, rich in historical and contextual information, opens avenues for in-depth exploration of the intricate dynamics shaping education worldwide. Its meticulous organization and thorough documentation ensure transparency and reliability, making it a valuable resource for evidence-based decision-making in the field of education policy and planning.


# **Data Cleaning**
In our dataset, we encounter various indicators such as total population, literacy rates, government expenditure, and a country's GDP, among others. To address different problem statements, a repetitive process involves extracting data for a specific indicator, cleaning the DataFrame by dropping columns with all NaN values, filling missing values using the linear interpolation method in both directions, and handling outliers using the IQR method. To streamline and enhance our workflow, we aim to develop functions that facilitate these tasks. These functions will provide a systematic approach to extract indicator-specific data, perform efficient data cleaning, and handle outliers consistently across multiple problem statements, contributing to a more organized and robust exploratory data analysis (EDA) process.

## **Handling null values**
Column with all the null values dropped and we set a threshold for each indicator for both the axis to drop NaN values if more then the threshold.

## **Converting columns to appropriate data types**
Changed data type of years into data time then extracted years from that. Changed the data type of all the Numerical columns when required to float.

## **Filling Missing Values**
Filled missing values using the pandas interpolation method linearly in both directions, i.e., backward fill (bfill) and forward fill (ffill).

## **Hnadling Outliers**
Outliers were addressed using the IQR method. If any value exceeded the interquartile range, the entire row was removed.

# **Exploratory Data Analysis**
Performed EDA and tried answering the following questions:

1. Literacy Rate Disparities: Analyze the literacy rate disparities between genders (e.g., adult male vs. adult female) in different countries.

2. Youth Literacy Progress: Investigate the change in youth literacy rates over time and assess whether these changes are consistent across countries.

3. Gender Gap in Youth Literacy: Examine the gender gap in youth literacy rates and determine if there has been progress in closing this gap.

4. Preprimary Education Impact: Explore the correlation between the percentage of teachers in preprimary education and literacy rates in countries.

5. Primary Education Enrollment: Determine if there's a relationship between primary education enrollment rates and overall literacy rates in countries.

6. New Entrants in Primary Education: Investigate trends in the number of new entrants to primary education and their impact on educational outcomes.

7. Secondary Education Enrollment Trends: Analyze variations in secondary education enrollment ratios among countries..

8. Tertiary Education Access: Explore changes in tertiary education enrollment rates and examine how government expenditure on tertiary education impacts access.

9. Government Spending on Education: Investigate the relationship between government spending on education and educational outcomes, such as literacy rates.

10. Gender Parity in Primary Education: Assess the gender parity index (GPI) in primary education and identify some countries where gender disparities exist.

11. Teacher-Student Ratios in Secondary Education: Analyze teacher-student ratios in secondary education and assess their impact on enrollment and educational outcomes.

12. Literacy and Economic Development: Investigate the correlation between adult literacy rates and a country's level of economic development, as measured by GDP per capita.

Mainly performed using pandas for dataframes and Matplotlib and Seaborn library for visualization and the following graph and plots were used:

Bar Plot. Scatter Plot.  Line Plot. Heatmap. Pair Plot

# **Conclusion**
As we conclude this comprehensive exploration of global education trends through the lens of the World Bank's dataset, it becomes evident that education is a dynamic and multifaceted domain with intricacies that extend far beyond traditional metrics. The synthesis of insights derived from twelve distinct problem statements has provided nuanced perspectives on various facets of education, allowing us to draw meaningful conclusions and propose actionable recommendations.

The Gender Parity Index (GPI) has been a vital tool in uncovering gender-based disparities in literacy rates globally. Notable progress has been made, exemplified by Afghanistan's challenges and Nepal's strides towards gender equality. However, persistent disparities in countries like Pakistan and South Africa underscore the ongoing need for targeted interventions.

While global literacy rates have shown a positive trajectory, the analysis emphasizes the imperative for sustained governmental commitment and intensified efforts to further enhance youth literacy. Education emerges as a pivotal driver for societal advancement, demanding continuous focus and investments.

Insights into the gender gap in youth literacy rates reveal that income levels correlate with gender disparities. Though progress is observed, especially in the lower-middle-income group, there remains a need for nuanced strategies to address persisting gaps, particularly in regions with lower income levels.

The unexpected inverse relationship between preprimary education teacher percentages and literacy rates prompts a deeper exploration of early education's quality and effectiveness. Variances across countries underscore the need for tailored approaches, considering diverse educational landscapes.

The unexpected correlation between decreasing primary education enrollment rates and increasing literacy rates challenges conventional expectations. The findings advocate for a shift towards quality-focused initiatives, targeted interventions, and an understanding of evolving demographics.

While most countries maintain relatively constant numbers of new entrants, standout cases like Costa Rica, the UAE, and Lao PDR showcase positive trends in primary education enrollment. These success stories emphasize the impact of strategic initiatives in enhancing educational access.

Analyzing variations in secondary education enrollment rates across income groups reveals disparities. The income-enrollment correlation accentuates the pivotal role of economic development in fostering educational access. Noteworthy improvements, especially in lower secondary education, suggest positive strides, but challenges persist in low-income settings.

Global disparities in secondary education underscore the role of economic prosperity in facilitating access. The observed income-enrollment correlation highlights the critical link between economic development and educational accessibility, guiding strategies to bridge gaps on a global scale.

The intricate relationship between tertiary education enrollment rates and economic conditions emphasizes the need for robust education systems. Economic dependency and incomplete enrollment in low-income countries highlight the importance of targeted governmental efforts to improve education and socioeconomic standing.

A clear positive correlation between government spending on education and literacy rates underscores the significance of strategic resource allocation. Increased government investment not only enhances literacy rates but contributes to overall educational effectiveness, emphasizing the need for continued financial commitments.

Analyzing the gender parity index in primary education reveals progress in minimizing disparities. While regions like Latin America and the European Union exhibit minimal gender disparities, challenges persist in the Middle East, North Africa, and South Asia. A multi-faceted approach is essential to address complex socio-economic and cultural factors influencing gender disparities.

The inverse proportionality between teacher-student ratios and literacy rates highlights the dynamic impact of teacher distribution on educational effectiveness. Recognizing this correlation is crucial for optimizing resource allocation and enhancing educational outcomes.

Exploring the correlation between adult literacy rates and GDP per capita reaffirms the interconnectedness of education and economic prosperity. Promoting literacy emerges as a catalyst for economic growth, emphasizing the positive feedback loop between literacy rates and economic development.

In conclusion, this EDA project serves as a robust foundation for evidence-based policymaking, offering insights into diverse aspects of global education. The recommendations derived from these insights underscore the need for targeted interventions, continuous investments, and a holistic approach to address the evolving challenges in the educational landscape. As we navigate the complex realm of education, this analysis lays the groundwork for fostering equitable, accessible, and effective educational systems worldwide.

## **Challenges:**
1. I had to search for each indicator for each problem, which was taking too much time.

2. There were a lot of NaN values, around 90%. To overcome that, I only chose countries where there were fewer missing values.

3. To convert the years into datetime format, each time I had to transpose it to make it a column or index, and then after doing that, I had to transpose it back to its original form.

4. While filling missing values according to the country, each time I had to transpose it, and after filling, I had to transpose it back.

5. There was no further information about the data given; that's why it took me almost 7 days to understand how to do this EDA project.

6. Although it was a difficult task because I was working alone, I got to learn a lot.
