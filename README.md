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
7. What is the repair cost by severity level?
8. What is the repair cost by defect type?
9. What is the repair cost by inspection method?
# Tools I used
For my analysis of manufacturing defects, I harnessed the power of several key tools:
- **Kaggle**: The source of my raw dataset, providing real-world manufacturing defect data to work with.
- **Microsoft Excel**: My workspace for cleaning and preparing the data, ensuring consistency and accuracy before analysis.
- **Power BI**: The powerhouse for creating interactive dashboards and visualizations, transforming raw numbers into actionable insights.
# The Analysis
Each visualization in this project was designed to answer a specific business question about manufacturing defects. Here's how I approached it:
## 1. What is the distribution of defects across the different defect types?
To assess the distribution of product defects, I created a stacked column chart in Power BI. The visualization plots the number of defects on the Y-axis and categorizes them by defect type (Structural, Functional, and Cosmetic) on the X-axis. Data labels were enabled to provide precise counts, and the chart was titled "Defects by Type" for clarity. This representation allows for a straightforward comparison across categories and highlights which defect types are most prevalent.
### Insights
The analysis shows that the majority of defects are Structural (352 cases), followed closely by Functional defects (339 cases) and Cosmetic defects (309 cases). While the distribution is relatively balanced, structural issues represent the largest share, suggesting that improvements in structural quality control could have the most significant impact on reducing overall defect rates.

![Stacked Column Chart](/visual2.png)
*The stacked column chart displays the different categories of defects, with each column representing a defect type and its corresponding count.*
