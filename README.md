# Introduction
📊 This project analyzes manufacturing defects to uncover patterns in defect types ⚡, severity levels 🚦, and inspection methods 🔍.  
Using Power BI 💻, I built an interactive dashboard to visualize repair costs 💰, defect distribution 📈, and quality control efficiency ✅.  
The goal is to provide clear insights for improving production quality 🏭 and reducing repair expenses 📉.
🔗 Want to explore the project?  
- 📊 **Interactive Dashboard:** [defectsDashboard.pbix](defectsDashboard.pbix)  
- 📄 **Quick Preview (PDF):** [defectsDashboard.pdf](defectsDashboard.pdf)  
- 📑 **Dataset:** [defects_data_clean.xlsx](defects_data_clean.xlsx)  
# Background
### The questions I wanted to answer through this project were:
1. What is the distribution of defects across the different defect types?
2. What is the distribution of defects across the different defect locations?
3. What is the distribution of defects across the different severity levels?
4. What is the total number of defects?
5. What is the total number of defective products?
6. What is the total repair cost?
7. What is the repair cost by inspection method and severity level?
8. What is the repair cost by severity level and defect type?
# Tools I used
For my analysis of manufacturing defects, I harnessed the power of several key tools:
- **📊 Kaggle**: The source of my raw dataset, providing real-world manufacturing defect data to work with.
- **📑 Microsoft Excel**: My workspace for cleaning and preparing the data, ensuring consistency and accuracy before analysis.
- **💡 Power BI**: The powerhouse for creating interactive dashboards and visualizations, transforming raw numbers into actionable insights.
# The Analysis
Each visualization in this project was designed to answer a specific business question about manufacturing defects. Here's how I approached it:
## 1. What is the distribution of defects across the different defect types?
To assess the distribution of product defects, I created a stacked column chart in Power BI. The visualization plots the number of defects on the Y-axis and categorizes them by defect type (Structural, Functional, and Cosmetic) on the X-axis. Data labels were enabled to provide precise counts, and the chart was titled "Defects by Type" for clarity. This representation allows for a straightforward comparison across categories and highlights which defect types are most prevalent.
### Insights
The analysis shows that the majority of defects are Structural (352 cases), followed closely by Functional defects (339 cases) and Cosmetic defects (309 cases). While the distribution is relatively balanced, structural issues represent the largest share, suggesting that improvements in structural quality control could have the most significant impact on reducing overall defect rates.

![Stacked Column Chart](/assets/visual2.png)

*The stacked column chart displays the different categories of defects, with each column representing a defect type and its corresponding count.*

## 2. What is the distribution of defects across the different defect locations?
In order to analyze the distribution of defects by location, I created the following Treemap. The category field was set to Defect Location, distinguishing between surface, component, and internal defects, while the values field was set to Defects to represent their frequency. This visualization makes it easier to compare the relative occurrence of each defect type.
### Insights
The Treemap shows that surface defects are the most frequent, with 353 occurrences, slightly higher than component defects at 326 and internal defects at 321. While surface issues stand out as the largest category, the relatively small gap between the three suggests that defects are fairly evenly distributed across locations, with no single area overwhelmingly dominant.

![Treemap](/assets/Treemap.png)

*The treemap presents the categories surface, component, and internal, each represented by a proportional area corresponding to its number of defects.*

## 3. What is the distribution of defects across the different severity levels?
To analyze the distribution of defect severity levels, I created three gauge visualizations in Power BI. Each gauge is dedicated to one severity category: Minor Defects, Moderate Defects, and Critical Defects. For each category, I defined a specific DAX measure that counts the number of defects falling into that severity group using the `CALCULATE` and `COUNTROWS` functions. For instance, the Minor Defects gauge is driven by the measure `Minor Defects = CALCULATE(COUNTROWS('defects_data'),'defects_data'[severity] = "Minor")` while the other two gauges follow the same logic with "Moderate" and "Critical" as filters. To provide context for the gauge scale, I set the minimum value to the lowest "defect_id" and the maximum value to the highest "defect_id", ensuring that each gauge is aligned with the dataset’s overall defect range. This approach allows for a clear and immediate visualization of how many defects of each severity level are present relative to the dataset.

### Insights
The three gauges provide a distribution of product defects by severity level out of a total of 1,000 defective products. The Minor Defects gauge indicates 358 cases, representing 35.8% of the total. The Moderate Defects gauge shows 309 cases, accounting for 30.9%. The Critical Defects gauge highlights 333 cases, corresponding to 33.3%. This balanced distribution reveals that defects are spread relatively evenly across severity levels, with minor defects being slightly more frequent, while critical defects remain a significant portion, underscoring the need for prioritization in addressing higher-severity issues.

![Gauge](/assets/Gauge2.png)

*The three gauges indicate a balanced distribution of defects across all severity levels.*

## 4 - 5 - 6. What is the total number of defects, defective products & the total repair cost?
I developed three card visualizations to highlight key performance indicators (KPIs). The first card, Total Defects, presents the overall count of defect IDs recorded in the dataset. The second card, Total Defective Products, reflects the distinct number of products affected by defects. The third card, Total Cost of Repairs, represents the aggregate repair expenses derived from the repair cost data.

### Insights
The KPIs provide a clear overview of the production quality and financial impact of defects. The Total Defects value of 1,000 indicates a significant number of individual defects across all products. The Total Defective Products count of 100 shows that these defects are concentrated across a relatively small number of products, suggesting multiple defects per item. The Total Cost of Repairs, amounting to $507,630, highlights the substantial financial burden associated with addressing these defects, emphasizing the importance of targeted quality control measures to reduce both defect frequency and repair expenses.

![KPIs](/assets/KPIs.png)

*Key Performance Indicators Displaying Total Defects, Total Defective Products, and Total Cost of Repairs*

## 7. What is the repair cost by inspection method and severity level?
To assess how repair costs vary across different inspection methods and severity levels, I created a stacked column chart in Power BI. The x-axis represents the inspection methods (manual testing, visual inspection, and automated testing), and the y-axis shows the total repair costs by summing the repair_cost column. Data labels were enabled to provide a clear view of the exact values for each segment, allowing for an immediate comparison across methods and severity levels.

### Insights
This stacked column chart analyzes repair costs across three inspection methods (Manual Testing, Visual Inspection, Automated Testing) by severity level (Critical, Moderate, Minor). Visual Inspection incurs the highest total costs ($184K), driven by steep Critical repairs ($71K), suggesting it may detect more severe issues—or overestimate them. Automated Testing has the lowest Critical costs ($52K) but higher Moderate/Minor expenses, hinting at early issue detection. Manual Testing is the most cost-efficient ($158K total), though its lower Critical costs raise questions about thoroughness. Key takeaway: method choice significantly impacts cost distribution, with trade-offs between severity detection and expense efficiency. Further analysis of error rates and combined approaches could optimize outcomes.

![CSCSI](/assets/ColumnStackedChartSeverityInspection.png)

*Comparative Analysis of Repair Cost Distributions Across Inspection Methods by Severity Level*

## 8. What is the repair cost by severity level and defect type?
To generate the grouped bar chart, the Severity Level (Minor, Moderate, Critical) and Defect Type (Cosmetic, Functional, Structural) fields were assigned to the x-axis, while the y-axis displayed the aggregated sum of Repair Cost from the dataset. The Severity Level field was applied to the legend to enable color-coded grouping, and data labels were activated to display exact cost values for precise comparison. This visualization was selected to effectively analyze cost distributions across defect categories and severity levels.

### Insights
This grouped bar chart compares repair costs across three defect types, segmented by severity level. Critical defects incur the highest costs (peaking at $74K for structural issues), while moderate defects show more uniform cost distribution ($47K–$57K). Structural defects consistently dominate costs across all severity levels, suggesting they are the primary cost driver. Notably, cosmetic defects have the lowest costs for minor/moderate severity but escalate sharply for critical cases, indicating a severity-dependent cost profile. Functional defects follow a mid-range pattern, warranting further investigation into root causes.

![Grouped Bar Chart](/assets/GroupedBarChart.png)

*Comparative Analysis of Repair Costs by Severity Level and Defect Type*

# What I learned
- **🔧 Data-Driven Prioritization**: Structural defects and surface issues require urgent QC focus due to high frequency/cost.

- **⚖️ Inspection Trade-Offs**: Automated Testing reduces Critical defect costs but may miss minor issues; Visual Inspection is thorough but expensive.

- **📊 DAX Measures Matter**: Proper use of `CALCULATE` and `COUNTROWS` enabled dynamic severity analysis.

# Conclusions

### Insights
1. **Cost Drivers:**
Structural defects and Critical severity levels contribute disproportionately to repair expenses.

3. **Inspection Optimization:**
Combine Automated Testing (for early detection) with targeted Manual Testing to balance cost and accuracy.

5. **Quality Control:**
Surface and component defects, though frequent, are less costly than structural issues—focus improvements accordingly.

### Closing Thoughts
This project strengthened my Power BI skills while revealing critical insights for manufacturing quality control. The analysis identifies high-impact areas like structural defects and inspection method trade-offs, providing actionable strategies to reduce costs. For quality teams, these data-driven insights enable smarter resource allocation and process improvements. The experience reinforced how analytics transforms operational data into real business value—a powerful tool for any manufacturing environment.
