A summarization of my learnings from working with Microsoft PowerBI for almost one year

### Executive summary:
PBI is a very effective tool to quickly get started with analysis. Just during the short amount of time I worked with it, 
an enormous amount of new features where released. This verifies that it's a product that Microsoft is putting a lot of 
resources into. 
There are still some improvements (mainly with shared data between different reports) that need to be fixed before the 
full potential can be reach. But it's getting there. 

- Remember that the report will be maintained. Shortcuts quickly become a burden.
- Start to think what questions the user want to answer. How can that be communicated.
- Less is often more. Use easily interpreted visualizations
- 

### Topics:
- #### Data loading
  - Create views in the database before loading the data even if no logic is put in the view. This will make the report more robust,
  easier to understand and easier to maintain. Name them something like PBI_*.
  - Don't put any customized SQL-logic in Power BI. This prevents "Query Folding" which makes the report less efficient, and
  makes the report harder to maintain.
  - Only keep columns needed in the view. 
  - Put excels in the cloud for access and automatic update
- #### Data preparation (Power Query)
  - Learn the M-language! It's powerful and possible to customize functions to your own demand. [Functions Reference](https://docs.microsoft.com/en-us/powerquery-m/power-query-m-reference)
  - Use functions (and parameters) when loading similarly structured data from different sources or different tabs in an excel file
  - If copying a query - reference is to be prefered.
- #### Visualizations
  Measures
  Use VAR and write easily interpreted code
Distribution
  Workspaces
  Using apps
Other
  Save the report on Onedrive for version handling
  Use templates and themes
  
