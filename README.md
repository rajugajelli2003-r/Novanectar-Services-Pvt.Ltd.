# Correlation Matrix - Visualize relationships

corr_matrix = df.corr()
plt.figure(figsize=(12, 8))
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Matrix')
plt.show()
![Screenshot 2024-12-27 170630](https://github.com/user-attachments/assets/6afee0c2-2938-461c-909e-dc32fa15a299)


 We get Issue Title: **Warning for DataFrame.corr() default behavior with numeric_only parameter**
 The default behavior of DataFrame.corr() includes numeric columns by default, but this is being deprecated. 
 If you call the method without explicitly handling non-numeric columns, a FutureWarning is raised.
 
C:\Users\rajug\AppData\Local\Temp\ipykernel_924\320333733.py:3: FutureWarning: The default value of numeric_only in DataFrame.corr is deprecated. In a future version, it will default to False. Select only valid columns or specify the value of numeric_only to silence this warning.
   corr_matrix = df.corr()
   so we can too solve it by
   
   df = pd.DataFrame(data)

# Compute the correlation matrix explicitly for numeric columns
corr_matrix = df.select_dtypes(include=['number']).corr()

 # Visualize the correlation matrix as a heatmap
 plt.figure(figsize=(12, 8))
 
  sns.heatmap(corr_matrix, annot=True, cmap='coolwarm', fmt=".2f")
  
 plt.title('Correlation Matrix')
 
 plt.show()
