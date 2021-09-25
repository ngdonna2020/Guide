# Guide
ngdonna2020 Tabl SUM([Profit])/SUM([Sales]) Bar site:help.tableau.com Table down (rank chaque col)
# Field Field Names = [ORANGE]
- Field, or col, is a single piece of info from a record in a data set
- If  titles  of  fields /col names changed  in  the  source  data,  we  need  to replace the references as Tableau won’t understand these changes. To fix this, right click on the broken field and click on replace references and tell Tableau which is the new field name.
- Remote field name is the original name of the column, field name is the custom name created in tableau
- To concatenate fields, they must be of same data type

# Role and Type
- Data fields are automatically assigned a role (Dim/ independent var or Measure/ dependent var) and a type (string, number, geo, date, date & time, boolean)
- Geo region type is also String
- To manually assign geo role: Right click the DIMENSION -> geo role -> assign
# Dim and Measure (auto generate 1 dim (Measur. names) and 4 measu (Lat, Long, num of records, Measu. values)
- Dim: break down aggregated total into smaller totals by category. Adding a dim to the marks area will increase granularity of the view
- When you increase number of dimensions, number of marks in the visualization will increase
- Dim: can contain qualitative values and affect lvl of detail (granularity). For relational data sources, date and time are auto placed in dimensions area of data pane
- Dim only create header. Measure create header+axis
- Can  drop  1 dimension  on  another dim to  replace it and drop 1 measure on another to replace it. The opposite is not true.
- When you drop a continuous measure in color, you get a continuous range of colors
- Countd will make a string into a measure
- bin can be created on a continuous measure or numeric dimension

# Discrete and Continuous (green)
- Discrete create label. Continuous create axis
- A continuous field creates color gradient, while a discrete field creates color palette
- When the only numeric fields is discrete, we can still create text table/cross tab
- 
# Quantitaive and Qualitative data
- Qualitative: slice quantit., describe or categorize, tell what/when/where, cant perform calc like sum, avg, mean
- Quantitative: provide measurement for qualit., numerical, can perform calc.
- Quantit. (usually measure) create axis which show range of values. Qualit. create axis with headers that have labels for categorical data
- You get different filtering options when filtering for categorical and quantitative data

# Default properties
- Comment,	Color,	Number format,	Aggregation,	Total using.	But not include sort (sort is applicable to measures but not dimensions)

# Date (when data type is mapped as number, text is treated as null and dates treated as # of days since 1/1/1900)
- Dates are by default dimensions
- For relative date filter, the default anchor is today’s date
- A line chart requires a date field
- Slider filters work best with date fields
- Date part gives data aggregated to the lvl of a specific part of a date, such as the month of May for ANY year, or the 8th of ANY MONTH (only 1 part) (discrete)
- Date values give the actual date, truncated to a specific level, such as May 2015 or May 8, 2015 (continuous)
- Can create custom dates when we don’t want customer to drill  down below  a certain level and can provide the user with  a custom  date  to  show them the required view. We can create a hierarchy of these custom dates. (Date part)
- DateParse help deal with incorrect date format issues
- Tableau automatically puts date/time into hierarchy
# Path/File (Packaged workbooks have no data security so data can be seen w/o encryption)
- Default path for supporting files, data source, icon, log: Documents/My Tableau Repository
- Tableau recognizes csv files as text files
- 4 tableau file types - tds, tde, twb, twbx
- TDS (shortcut to quickly connect to original data) contains  the  info to  connect to the  original data source and does NOT contain the actual data. It can contain modifications you've made on top of the actual data. TDS file contains: calculated fields, Data source type, Default field properties, Connection info, Groups and sets. 
- TWB contains >=1 worksheets and >=0 dashboards & stories and info necessary to connect to data source and info needed to build the view, but NOT the actual data. A link is rather established to the data source. The next time we open the TWB file, the views will automatically update wrt. to the changes in the underlying data source
- TWBX is all  in 1.  Single zip file contains workbook, viz,  info needed to  build the  viz, and a copy of the data source. It doesn’t contain extracts of the data but can contain both live and data extracts. Best if want to eliminate the barrier of data access/sharing your work with ppl who don’t have access to the original data.
- TDE is a snapshot of the data that Tableau stores locally (local copy of a subset or entire data set that you can use to share data with ppl/ need to work offline, performance is optimised because it queries its own database engine instead of the local data source) Good for very large datasets of which we only need few fields.  
- .hyper: Create larger extracts with billions of rows of data. Because .hyper extracts can support more data, you can consolidate .tde extracts into a single .hyper extract. Create and refresh extracts faster, version 2020.3 supports faster extract creation and refreshes for even larger data sets. Experience better performance when interacting with views that use extract data sources: Although smaller extracts continue to perform efficiently, larger extracts perform more efficiently.
# Data source (Google firebase is not valid server-lvl data source) / Tableau Reader/ Publish
- can add filter in Data Source window to filter data (Data Source filter)
- can  either  embed  data  source  in  the workbook for others to use, or publish it separately. Include external files means that there are things like custom geo encoding that the server wont have access to and would want to include those.
- save new data source as .tds :go to data menu on top. choose current connected data source. Then click on Add to Saved Data sources. This will save all calculated fields, changes to fields ... It  will  be  saved  in  My  Tableau  Repository  ->  Mydatasources and also appear on Tableau Home Page under saved data sources like SampleSuperStore.
- can publish viz to tableau online (hosted by Tableau) or server (hosted by our organisation). Tableau public is free, good for making public viz that contain non sensitive data. Before we can publish on Tableau online, we need to be invited by admin and create username and password. The URL for tableau online is http://online.tableau.com
- Tableau reader is free  and less powerful version of Desktop with limited viewing capabilities.  Doesn’t have full editing features  -  can  sort etc only basic things.  Can open .twbx files and view the vizzes.
# Cube data source
- Cube data source can only be used as primary in a blend and supported only for Tableau Desktop on windows
- For cube data sources, you canNOT use parameter values to filter dimensions in an MDX calculation.
# Export / Share
- Data can be exported to an MS Access DB (Data is the option name ) or Excel.
- Available image formats when exporting as image:Jpeg, Bmp, Png
- Export dashboard as image: copy just 1 of the worksheets not the entire dashboard (Right click on the dashboard, choose Copy, then image OR Click on Worksheet in the Menu bar followed by Export, then choose Image)
- NOT exist: Using the floating export worksheet option on the Dashboard
- Share twbx as PDF: select File > Print to PDF.
- Share twbx as an image: Select Worksheet > Export> Image. In the Copy Image dialog box, select the contents you want to include in the image and legend layout (if the view contains a legend). Click Save. In the Save Image dialog box, navigate to where you want to save the image file and type a file name into the text box. Select a file format from the Save as type drop-down menu. Click Save.

# Extract & Refresh
- Extract=saved subsets of data that can improve performance or take advantage of Tableau functionality not available or supported in the original data. When creating extract of your data, you can reduce the total amount of data by using filters and configuring other limits. After you create an extract, you can refresh it with data from the original data.
- When refreshing the data, you can either do a full refresh, which replaces all of the contents in the extract, or you can do an incremental refresh, which only adds rows that are new since the previous refresh.

# Metadata (Ex: Which fields are hidden, Default aggregation etc)
- Use metadata to create custom names for cols
# View/ Story / Dashboard 
- Can view display max 10k rows when click on view data. This  can  be increased
- Device options available in Device Preview: Default, desktop, Tablet, Phone
- To add phone view, Select Device Preview, then select Phone for Device Type, then click the button labeled "Add Phone Layout"
- Stories but NOT dashboards can include multiple versions of same sheet. CanNOT add a dashboard and a worksheet at the same time both to a story point
- Valid objects when creating dashboard: Text, Image, Extension, Webpage
# Size/Layout
- Dashboard size options: Fixed (default), Range, Automatic
- Valid layout container types: Vertical and Horizontal
# Granularity = lvl of detail (LOD)
- Determine LOD: select a mark, right click to view underlying data
# Aggregration = how data is combined, NOT table calc
- By default, aggregation is done on row-lvl detail
- Change default aggregation for a measure: Right click on the measure -> default properties -> aggregation
- Values are always aggregated at level of granularity of the worksheet
- Fields used in blends must first be aggregated
- Disaggregate: break down all records in underlying source to see all of the marks in the view at most detailed level of granularity
# Blend/Union
- Blending (done per sheet basis) allows combine data from different data sources (primary data src is blue, secondary is orange). 
- Blending (~ LEFT join) is established when a field from a second data source is used in the view.
- To create blend: Add at least 1 field from the primary data source to sheet/ view. Then, in the Data pane, click the data source that you want to designate as the secondary data source and click the broken link icon.
- Fields used in blends must first be aggregated
- Union: combine row wise into single sheet
# Join/ Relationship
- join max 32 tables
- 1-to-many relationship is represented by a *
# Group / Set
- group  dim or measur: In Data pane menu, click  group  by  folder. Then right click and create group. Drag-drop relevant dim or measures into the group.
- group data: 3 ways - marks  and  labels(visually) and  dimensions shelf.  When  we visually group data, if we select data points directly and group - they will be grouped via colour on the chart (they remain separate marks) and a new dim is also created but not moved into columns tab. But if we select their labels and then click on group - a new dim is created  and  the group is shown on chart as a single mark by aggregating value of all group members
- To remove member from group: In the Data pane, right-click the group and select Edit Group
- To compare members, it is better to use combined set

# Action/ Web Page Object
- 3  types  of  dashboard  actions - select, hover and menu. Hover is best for highlighting, select for filtering. Menu action is added to the tooltip and user can decide whether to run that action or not (best for URL actions)
- To create dashboard action:	Click "More Options" arrow on the Worksheet included in the dashboard layout, then select Actions (Ctrl+Shift+A)
- Proportional brushing can be created with set action
- A dashboard can have multiple Web page objects.
- To interactively display info from the web inside a dashboard, you can use a URL action with a web page object
- url formats allowed with Tableau url action: ftp, http, https
- go-to-url action = a hyperlink that points to a webpage outside of tableau

# Filter (Slider filter works best with date field)
- In filter range of values, upper bound is excluded
- Order of filters: Extract filter, data source filter, context filter, Filter on dimension, Filter on measures
- To create context filter: Click "More Options" arrow on the worksheet included in the dashboard layout, then	select "use as Filters" and select the filter that you'd like to apply to the whole	dashboard. Then go to the filter menu, right click, and select "apply to all using this data source"
- CONTEXT filter usage: set a context filter to include only the data of interest, THEN set a (dependent) numerical or a top N filter. CONTEXT filter will mprove performance (If you set a lot of filters or have a large data source, the queries can be slow)
- Quick filters: Single / multiple value (list, drop-down, slider), Multiple values (custom list) and Wildcard match
- You get different filtering options when filtering for categorical and quantitative data

# Calculation/ Parameters = [PURPLE] (variables which can be added)
- Quick table calc can be pane down/across or table down/across
- Param = global placeholder value such as number, date, or string that can replace a constant value in a calculation, filter, or reference line.

# Function
- Collect function can only be used with spatial fields
- SIZE() returns number of rows in the partition
- Zn function helps replace missing values. only works for numeric fields and changes Null to 0

# Chart/Bin
- Combined axis charts are useful when I want  to  see  multiple  measures  for 1 dimension. (If  i  want  to  see  a  columns  discount,  sales  etc  I  just  have  to  drag  and drop the extra measures to the y axis until a double green bar appears). possible to blend axes for multiple measures into a single 1
- Pie chart should be 2-5 dim. if not, use treemap (note: these dont have axis)
- Tree chart can be changed to a text cloud or bubble chart by just changing the shape of marks
- Histogram shows the distribution of continuous data by creating bins that are discrete (bin can be created on a continuous measu or numeric dim). Histogram must include a bin and a count and requires a minimum of 1 measure to be created
- A line chart requires a date field. Reference line can only be added to a continuous axis IN THE VIEW
- Bar chart: if we group labels in a view, a new mark (bar) is created, which consolidates all members of the group. A bar chart can be used a floating item. To create a stacked bar chart from existing bar chart, drag another dimension into Color mark
- Heatmap default shape = square
# Color (max 7 in visualization/ view) and Font
- Can separate color legends be displayed for multiple measure in a viz: Add measure values to color legend and select use separate legends option
- When you drop a continuous measure in color, you get a continuous range of colors
- To format font color: Right-click on the view, select "Format" and select the dropdown next to tooltip. Then select the color. OR Click on the tooltip button in the Marks area, highlight the text, and select desired color using the dropdown
- When format the font at worksheet lvl, all fonts will be changed except for the ones in tooltip
- Orange-Blue  diverging  palette  is  an  excellent  choice  for  both  colour  blind  and  sound-vision people.
- When there are both + and – values for a field, the default range of values will use 2 color ranges. This is Diverging Palette
- Field Names = [ORANGE], Parameters = [PURPLE]
- Recommended file format when using color to encode shape: PNG, GIF
# How to...
- format axis bold: Right click on axis, choose format, and then set to bold
- bold tooltip: Right click format, and then under default worksheet formatting, choose tooltip and make it bold OR Click on tooltip in the marks card, and then make it bold OR Click on worksheet in menu bar, then tooltip, and then select bold option
- italicize tooltip: Click on tooltip, select text, and use italics option OR Click Format from Menu bar, choose Font, and then edit tooltip option OR Click on worksheet in Menu, select tooltip, then use italic option
- make row or col bold w/o affecting others: Choose format from Menu bar, select row or column, and select Bold under header option OR Right click row or column, choose format. In font option click on bold
- format numbers to currency: Right click measure or axis and select Format. Then click Numbers drop-down menu
- Manually assign geo role: Right click the DIMENSION -> geo role -> assign
- show mark labels in viz: Click on analysis and choose Show Marks labels OR Drag measure to Text in the marks card OR Click on Show Marks label icon in the tool bar at top
# Animate visualizations in workbook (Animation not supported on IE)
- Choose Format > Animations. To animate every sheet, under Workbook Default, click On. Then for Duration, choose a preset, or specify a custom duration of up to 10 seconds. For Style, choose Simultaneous to play all animations at once or Sequential to fade out marks, move and sort them, and then fade them in. 
- To override workbook defaults for a particular sheet, change the settings under Selected Sheet.

# Wildcard search (*)
- use Wildcard Search to set up search criteria to automatically include tables in your union. Use the wildcard character, which is an asterisk (*), to match a sequence or pattern of characters in the Excel workbook and worksheet names, Google Sheets workbook and worksheet names, text file names, JSON file names, .pdf file names, and database table names. When working with Excel, text file data, JSON file, .pdf file data, you can also use this method to union files across folders, and worksheets across workbooks.
- Search is scoped to the selectedconnection. The connection and the tables available in a connection are shown on the left pane of the Data source page
# Map
- Can edit the map background etc using Map Layers
