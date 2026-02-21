# Project Title: Salary-Prediction-using-Ensemble-Learning
"The data used is from the 2023 Stack Overflow Developer Survey."            
https://drive.google.com/file/d/1LiqLOB6Cg-AhMK45j3uWMj04cQOQA-1Q/view?usp=sharing          
(link to the data file)

## Project Overview:
This project is designed to predict a software developer’s annual income based on their professional background. Instead of relying on a single calculation, it uses Ensemble Learning—a method that combines multiple "expert" models to reach a more accurate and reliable answer. The system is built using a professional "Data-to-Insight" pipeline powered by the Python data science stack.

## The Goal
The objective is to create an "AI Brain" capable of analyzing a developer's profile—including their country, years of experience, age, and technical stack (e.g., Python or AWS)—to provide a realistic estimate of their annual salary.

## Phase 1: Data Preparation (The Cleanup)
Real-world data is often messy and incomplete. Before the AI can learn, the data must be refined using Pandas and NumPy.         

- **Data Cleaning:** We removed columns with more than 50% missing information and filtered out responses that lacked salary details.
- **Filling in the Blanks:** For minor missing values, we either removed the row or used "imputation" (making a smart guess) to keep the data consistent.
- **Turning Words into Numbers:** Computers cannot process words like "USA" or "Python." We used Encoding to turn these into numbers (0s and 1s) that the model can understand.
- **Ranking (Ordinal Encoding):** For categories with a natural order, like "Age" or "Company Size," we assigned ranks (e.g., 1 for small, 2 for medium, 3 for large).
- **Outlier Management:** To keep predictions realistic for most roles, we focused on salaries capped at $500,000.

## Phase 2: Feature Engineering
To make the model "smarter," we created custom features that highlight high-value skills and technical breadth.       

- **Skill Extraction:** We identified specialized languages like Python, Rust, and Go to measure how much of a "salary boost" these skills provide.
- **Complexity Scoring:** We calculated the number of languages and databases a developer uses to determine their technical breadth.

## Phase 3: The Secret Sauce (Ensemble Learning)
The heart of this project is Ensemble Learning. Rather than following one single rule, ensemble models use a "team of experts" to make a prediction.     

### A. Random Forest (The Group Vote)
Imagine asking 100 experts to guess a salary. Some focus on your location, while others focus on your experience. We take all their guesses and find the average. Because this "forest" of decision trees looks at different parts of the data, the final answer is robust and less likely to be skewed by weird data points.

### B. Gradient Boosting (The Improvement Team)
This team works sequentially. The first expert makes an initial guess. The second expert looks at the errors made by the first and tries to fix them. The third expert fixes the second’s mistakes, and so on. This "trial and error" process makes the model extremely sharp and accurate.

## Phase 4: Results & Discoveries
After analyzing the results using Matplotlib and Seaborn, several key trends emerged:       

- **The Sweet Spot:** The model is most accurate for "typical" salaries between  50,000and 150,000, where it has the most examples to learn from.    
- **The US Variance:** Predicting salaries in the USA is more challenging due to high variance. A developer in San Francisco may earn much more than a developer in a smaller city, even with identical skills.    
- **Primary Drivers:** The most significant factors for a high salary are Years of Experience and Geographic Location. Specialized languages like Rust or Go also act as significant salary multipliers.    

## Evaluation: Strengths & Weaknesses
### Strengths
- **High Performance:** Because it is an Ensemble model, it is much more powerful than basic linear models. \
- **Handles Complexity:** It captures "interactions," such as how knowing Python is worth more when combined with 10 years of experience than as a beginner skill.
### Weaknesses
- **The High-Earner Gap:** Because there are fewer survey responses for salaries over $300,000, the model tends to "underestimate" extremely high salaries.
- **Regional Blindness:** The model knows the "Country," but lacks specific "City" data, which can lead to slight inaccuracies in countries with high cost-of-living differences.

## Conclusion
This project demonstrates that Ensemble Learning is a superior approach for navigating the fragmented global tech market. By combining multiple data-driven perspectives, the model provides a robust framework for understanding and predicting developer compensation in 2026.
