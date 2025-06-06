### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 12.04.2025
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
# Visitor segmentation based on characteristics
# read the data
import pandas as pd
import matplotlib.pyplot as plt
visitor_df = pd.read_csv("/content/clustervisitor.csv")

# Perform segmentation based on characteristics (e.g., age groups)
age_groups = {
    'Young': visitor_df['Age'] <= 30,
    'Middle-aged': (visitor_df['Age'] > 30) & (visitor_df['Age'] <= 50),
    'Elderly': visitor_df['Age'] > 50
}

for group, condition in age_groups.items():  
    visitors_in_group = visitor_df[condition] 
    print(f"Visitors in {group} age group:")
    print(visitors_in_group)

```
### Output:

![Screenshot 2025-04-12 142843](https://github.com/user-attachments/assets/2e32e1c3-a65e-42d8-b7bf-db84718e5768)


### Visualization:
```python
# Create a list to store counts of visitors in each age group
visitor_counts=[]

# Count visitors in each age group
for group,condition in age_groups.items():
    visitors_in_group=visitor_df[condition]
    visitor_counts.append(len(visitors_in_group))
    
# Define age group labels and plot a bar chart
age_group_labels=list(age_groups.keys())
plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()


```
### Output:

![Screenshot 2025-04-12 142852](https://github.com/user-attachments/assets/bd21c83b-abe4-473c-9feb-10724b45bf89)

### Result:
Thus the code was executed successfully.
