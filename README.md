# Guide
ngdonna2020 Tabl SUM([Profit])/SUM([Sales]) Bar site:help.tableau.com Table down (rank chaque col)
# Field
- Field, or col, is a single piece of info from a record in a data set
- If  titles  of  fields /col names changed  in  the  source  data,  we  need  to replace the references as Tableau won’t understand these changes. To fix this, right click on the broken field and click on replace references and tell Tableau which is the new field name.
- To concatenate fields, they must be of same data type

# Role and Type
- Data fields are automatically assigned a role (Dim/ independent var or Measure/ dependent var) and a type (string, integer, date ...)
- Geo region type is also String
# Dim and Measure (auto generate 1 dim (Measur. names) and 4 measu (Lat, Long, num of records, Measu. values)
- Dim: break down aggregated total into smaller totals by category
- Dim only create header. Measure create header+axis
- Can  drop  1 dimension  on  another dim to  replace it and drop 1 measure on another to replace it. The opposite is not true.

# Discrete and Continuous (green)
- Discrete create label. Continuous create axis
- 
# Quantitaive and Qualitative data
- Qualitative: slice quantit., describe or categorize, tell what/when/where, cant perform calc like sum, avg, mean
- Quantitative: provide measurement for qualit., numerical, can perform calc.
- Quantit. (usually measure) create axis which show range of values. Qualit. create axis with headers that have labels for categorical data

# Date
- For relative date filter, the default anchor is today’s date
- Date part gives data aggregated to the lvl of a specific part of a date, such as the month of May for ANY year, or the 8th of ANY MONTH (only 1 part) (discrete)
- Date values give the actual date, truncated to a specific level, such as May 2015 or May 8, 2015 (continuous)
- Can create custom dates when we don’t want customer to drill  down below  a certain level and can provide the user with  a custom  date  to  show them the required view. We can create a hierarchy of these custom dates. ( Date part )
# Path/File (Packaged workbooks have no data security so data can be seen w/o encryption)
- Default path for supporting files, data source, icon, log: Documents/My Tableau Repository
- 4 tableau file types - tds, tde, twb, twbx
- TDS  contains  the  info to  connect to the  original data source and does NOT contain the actual data. It can contain groups, calculated fields
- TWB contains worksheets and dashboards and info necessary to connect to data source and info needed to build the view, but NOT the actual data. A link is rather established to the data source. The next time we open the TWB file, the views will automatically update wrt. to the changes in the underlying data source
- TWBX is all  in 1.  It contains  viz,  info  needed  to  build the  viz, and a copy ofthe  data source. It doesn’t contain extracts of the data but can contain both live and data extracts. Best if want to eliminate the barrier of data access
- TDE is a snapshot of the data that Tableau stores locally. Good for very large datasets of which we only need few fields. Performance is optimised because it queries  its  own database engine instead of the local data source.
# Data source/ Tableau Reader/ Publish/ Export
- can add filter in Data Source window to filter data (Data Source filter)
- can  either  embed  data  source  in  the workbook for others to use, or publish it separately. Include external files means that there are things like custom geo encoding that the server wont have access to and would want to include those.
- save new data source as .tds :go to data menu on top. choose current connected data source. Then click on Add to Saved Data sources. This will save all calculated fields, changes to fields ... It  will  be  saved  in  My  Tableau  Repository  ->  Mydatasources and also appear on Tableau Home Page under saved data sources like SampleSuperStore.
- can publish viz to tableau online (hosted by Tableau) or server (hosted by our organisation). Tableau public is free, good for making public viz that contain non sensitive data. Before we can publish on Tableau online, we need to be invited by admin and create username and password. The URL for tableau online is http://online.tableau.com
- Tableau reader is free  and less powerful version of Desktop with limited viewing capabilities.  Doesn’t have full editing features  -  can  sort etc only basic things.  Can open .twbx files and view the vizzes.
- Data can be exported to an MS Access DB (Data is the option name ) or Excel.
# Metadata
- Use metadata to create custom names for cols
# Granularity = lvl of detail (LOD)
- Determine LOD: select a mark, right click to view underlying data
# Aggregration = how data is combined
- By default, aggregation is done on row-lvl detail
# Blend/Union
- Blending (done per sheet basis). allows combine data from different data sources (primary data src is blue, secondary is orange)
- Union: combine row wise into single sheet
# Join
- join max 32 tables
-
# Group
- group  dim or measur: In Data pane menu, click  group  by  folder. Then right click and create group. Drag-drop relevant dim or measures into the group.
- group data: 3 ways - marks  and  labels(visually) and  dimensions shelf.  When  we visually group data, if we select data points directly and group - they will be grouped via colour on the chart (they remain separate marks) and a new dim is also created but not moved into columns tab. But if we select their labels and then click on group - a new  dim is  created  and  the  group  is  shown  on  chart  as  a  single  mark  by aggregating value of all group members
# Action/ Web Page Object
- 3  types  of  dashboard  actions - select, hover and menu. Hover is best for highlighting, select for filtering. Menu action is added to the tooltip and user can decide whether to run that action or not (best for URL actions)
- A dashboard can have multiple Web page objects.
- To interactively display info from the web inside a dashboard, you can use a URL action with a web page object
- Can view display max 10k rows when click on view data. This  can  be increased

# Filter
- In filter range of values, upper bound is excluded

# Calculation/ Parameters (variables which can be added)
- Quick table calc can be pane down/across or table down/across

# Chart/Plot
- Combined axis charts are useful when I want  to  see  multiple  measures  for 1 dimension. (If  i  want  to  see  a  columns  discount,  sales  etc  I  just  have  to  drag  and drop the extra measures to the y axis until a double green bar appears)
- Pie chart should be <= 5 dim. if not, use treemap (note: these dont have axis)
- Tree chart can be changed to a text cloud or bubble chart by just changing the shape of marks
# Color (max 7 in visualization/ view)
- Can separate color legends be displayed for multiple measure in a viz: Add measure values to color legend and select use separate legends option
- Orange-Blue  diverging  palette  is  an  excellent  choice  for  both  colour  blind  and  sound-vision people.

# Map
- Can edit the map background etc using Map Layers
