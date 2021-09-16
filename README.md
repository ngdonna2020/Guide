# Guide
ngdonna2020 Tabl
# Field
- Field, or col, is a single piece of info from a record in a data set
- If  titles  of  fields /col names changed  in  the  source  data,  we  need  to replace the references as Tableau won’t understand these changes. To fix this, right click on the broken field and click on replace references and tell Tableau which is the new field name.

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
# Path
- Default path for supporting files, data source, icon, log: Documents/My Tableau Repository
# Data source
- can add filter in Data Source window to filter data (Data Source filter)
- save new data source as .tds :go to data menu on top. choose current connected data source. Then click on Add to Saved Data sources. This will save all calculated fields, changes to fields ... It  will  be  saved  in  My  Tableau  Repository  ->  Mydatasources and also appear on Tableau Home Page under saved data sources like SampleSuperStore.
# Metadata
- Use metadata to create custom names for cols
# Granularity = lvl of detail (LOD)
- Determine LOD: select a mark, right click to view underlying data
# Aggregration = how data is combined
# Blend/Union
- Blending allows combine data from different data sources (primary data src is blue, secondary is orange)
- Union: combine row wise into single sheet
# Join
- join max 32 tables
-
# Group
- group  dim or measur: In Data pane menu, click  group  by  folder. Then right click and create group. Drag-drop relevant dim or measures into the group.
- group data: 3 ways - marks  and  labels(visually) and  dimensions shelf.  When  we visually group data, if we select data points directly and group - they will be grouped via colour on the chart (they remain separate marks) and a new dim is also created but not moved into columns tab. But if we select their labels and then click on group - a new  dim is  created  and  the  group  is  shown  on  chart  as  a  single  mark  by aggregating value of all group members
# Action/ Web Page Object
- A dashboard can have multiple Web page objects.
- To interactively display info from the web inside a dashboard, you can use a URL action with a web page object
- Can view display max 10k rows when click on view data. This  can  be increased

# Filter
- In filter range of values, upper bound is excluded

# Chart/Plot
- Combined axis charts are useful when I want  to  see  multiple  measures  for 1 dimension. (If  i  want  to  see  a  columns  discount,  sales  etc  I  just  have  to  drag  and drop the extra measures to the y axis until a double green bar appears)
# Color
- Can separate color legends be displayed for multiple measure in a viz: Add measure values to color legend and select use separate legends option
- Orange-Blue  diverging  palette  is  an  excellent  choice  for  both  colour  blind  and  sound-vision people.

# Map
- Can edit the map background etc using Map Layers
