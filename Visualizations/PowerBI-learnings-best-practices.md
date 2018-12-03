A summarization of my learnings from working with Microsoft PowerBI for almost one year

### Executive summary:
PBI is a very effective tool to quickly get started with analysis. Just during the relatively short time I worked with it, 
an enormous amount of new features where released. This verifies that it's a product that Microsoft is putting a lot of 
resources into. 
There are still some improvements (mainly with shared data between different reports) that need to be fixed before the 
full potential can be reach. But it's getting there. 

- Remember that the report will be maintained. Shortcuts quickly become a burden.
- Start to think what questions the user want to answer. How can that be communicated.
- Less is often more. Use easily interpreted visualizations
- Use measures over calculated columns
- Take time to learn new things. This is easy to forget, but in the long run, you'll be much more effective.

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
  - Avoid columns with high cardinality (many unique values). They increase the size of the report and slow down performance.
  - Long and narrow tables over short and wide. Power Pivot compresses over columns, which makes this much more efficient
  - Store as integer over string. Strings are stored in a separate hash table which is slower and requires more space. 
  - 1M rows are loaded at a time. So to make the compression more effective sort on relavant column before loading the data, if the table is large. 
  
- #### Visualizations
  - Use measures over calculated columns. The reason is heavily decreased performance with many calculated columns. It takes longer time to create in the beginning but you'll get payback from your invested time. Manyfold. 
  - Write easily interpreted DAX code. It's IMPOSSIBLE to understand complex formulas unless they are structured inuitively. Use VAR and possibly [this link](https://www.daxformatter.com/)
  - Do a measure in small steps. Using variables and display the pieces as you progress. [A great example](https://exceleratorbi.com.au/how-to-solve-a-complex-dax-problem/)
  - Use a calendar table
  - Create a separate table for the measures
  - Name measures intuitively, e.g. %_SalesLY or #_CarsSold
  
- #### Distribution
  - Use Apps to distribute to a large audience. This way you can test the newly created app without affecting the end users. [White paper from Microsoft](https://aka.ms/pbienterprisedeploy)
  - Create a new workspace when distributing a new project. This way you can control the access for users. It's not yet (at time of writing) possible to create multiplicate Apps from the same workspace
Other
  - Save the report on Onedrive for automatic version control. Doing this manually gets problematic when distributing new versions of a report. If they don't have the same name, it will we published as a separate report and all the access need to be redone. 
  - Use templates and themes. This give all the users a common ground and improves efficiency. 
  
Links and blogs to follow:
- https://exceleratorbi.com.au/
- https://guyinacube.com/
- https://pbicheatsheet.blob.core.windows.net/pbicheatsheet/Macaw%20Power%20BI%20cheat%20sheet%20EN.pdf
- http://tinylizard.com/power-pivot-performance-gotchas/
- https://www.flaticon.com/

