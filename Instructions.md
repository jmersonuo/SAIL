

# UOregon SAIL Program - Cartography Workshop
## **Interactive Web Mapping with CARTO**

Ten to fifteen years ago, creating maps on the web required doing some challenging things, such as setting up server computers and using text-based markup code to specify how you wanted your map to be styled. This worked out for big corporations and governments who could afford the software and hardware and personnel to set it all up, but it made mapping difficult for journalists, small businesses, educators, and others who just wanted to visualize simple tabular data interactively.

As interactive web technologies have improved, companies like Mapbox and CARTO stepped in to fill the needs of these nontraditional GIS consumers, providing mapping solutions wherein you can upload your dataset to the cloud and style it within the web browser. The tools are convenient enough that they have also become popular with professionals in the geospatial industry. Today, you'll use a tool called CARTO to make a web-based interactive map yourself.

# **1. Create a CARTO account**

The first thing you need to do is to create a 30-day trial account with CARTO. Go to [https://carto.com/](https://carto.com/) and click the "Sign Up" button at the top. 
Then click: 

![Getting Started](/Images/GetStarted.png).

Sign up using any email address, or an existing google or github account.
It takes a few seconds to create your account, and once this is finished, you'll see your CARTO Dashboard.

# **2. Connecting a table to a map**

Once you're logged in and on your dashboard, click **"New Map"** in the middle (you may need to click the "Maps" link at the top if you don't see this).

Next, click **"Create Empty Map"** (on the upper right). If it's your first time, it will ask if you want to Take a Tour. It's up to you, but for now, let's just **"edit your map"**. At this point, you should see a nice, simple world map.

It's possible you'll see a window asking if you want to add points, lines, or areas. If this is the case, click "Skip" to bypass the window. Click the **"Add New Layer"** button in the upper left pane.

Select **"DATA LIBRARY"** This is CARTO's public library of open data that is a good starting place for many maps you will create. The dataset we will be using is called "Populated Places". Find it by clicking the **"search"** button on the left, and type in *"Populated Places"*. The search may take awhile (I had to wait almost a minute). If it takes too long you can also browse available datasets and find this one on page 5 of the results. Once the search loads, you may see multiple datasets here, but make sure to select the one called "Populated Places" with the subtitle "Most populated places" made by "Natural Earth Data".

Click the table's name and then click **"Add Layer"** at the bottom right of the interface to import the table into your account. Again, this may take a moment to complete.

After the file processes and inputs, you will be taken straight to the "Map View" of this dataset. Click on the layer ("ne\_10m\_populated..."), then click on the link under the title ("ne\_10m\_populated\_places\_simple") at the top of your screen to see the full data in this table in a *new tab*. Take a minute to explore it, see what columns you have available to you, and what kinds of data the table contains. *Each row in this table is a dot on the map!*

As you look at the table, take note of the second column from the left called the\_geom. It contains the latitude and longitude coordinates required to display data on a map. Without values in this column you wouldn't be able to map these data.

![The Geom](/Images/theGeom.png)

Now go back to your map *tab* to begin designing your map.


# **3. Making a basic thematic map**

When you view your map, you should see something like this:

![Inital Map](/Images/Map1.png)

**A. Change the basemap**

First, let's take a look at the available basemaps by clicking the *"Voyager"* layer at the bottom left. There are lots to choose from.

![Basemaps](/Images/Basemaps.png)

Change the basemap a few times to see what's available. Each *Source* has a few *Styles*. Choose a basemap that isn't too busy, like Positron - Positron (lite), or Carto - World Antique, or Here - Reduced Day. After that's finished, click the back arrow in the top left, to go back to the main menu.

**B. Style your data layer**

We are going to make the points that are nations' capitals a different color than the rest of the points. Click your "ne\_10m\_populated" layer, and click on "STYLE" to take a look at the symbolization settings.
![Style](/Images/Style.png)

Once there, keep "aggregation" as "POINTS". then set the "POINT COLOR" to "By value", then scroll to the bottom of the list to select the table column **'adm0cap'**, which contains data about which cities are *capitals* (represented by 1 in the color-selector) and which aren't (represented by 0). 

Click where it says "Quintiles" and scroll down to select "Category", then try different color schemes. You should have a few points showing the nations' capitols in one color, and the rest a different color. 

Can you identify Washington, D.C., and Ottawa, Canada on the map?

![Style By Value](/Images/StyleByValue.png)

# **C. Add a legend**

To show what the colors mean on the map, you need to add a legend. Still in the "ne\_10m\_populated" layer options, click on the **"LEGEND"** tab. Choose the custom legend. 

Give it the title **"Populated Places"**. Leave the first item as **"Places"**, the second **"Capitals"**, and the third **"Others"**.

![Legend](/Images/CityLegend.png)

Congratulations, you've made your first map!

# **4. Interactive Visualization in CARTO**

Note: If you need to, you can get back to your CARTO dashboard at any time by clicking the circle icon in the top left.

Now, we'll try some different ways to symbolize data. You'll be exploring tornados. To get started, go back up to the map layers pane and then click on "+Add new Layer"  and choose the "Connect Dataset" tab. Highlight and **Copy** the link below:

https://github.com/jmersonuo/SAIL/blob/master/Data/Tornados.csv

Then paste the link you copied above into the link field, and click "Submit."
Under "Sync my data", choose **"Never"**.

The map may look similar to the population points, but this time each dot represents a recorded tornado in 2013, not a city. 

In the data view of the Tornados layer, you'll see columns for damage, date, latitude, and longitude. Another column is called "the\_geom". It contains the latitude and longitude coordinates required to display data on a map. CARTO found the two columns in your CSV labeled "latitude" and "longitude" and turned them into points.

CARTO also lets you see the _types_ of data for each column. For example, you can see that **damage** is a number, and not a string data type (because it has numerical data, not text). You can also see that **date** was imported as a string (or text), rather than a date type.

It's easy — and important — for you to change the data types, because they affect what kinds of visualizations you can create. For example, using the date type, you can do some things that you can't do with a string type. Therefore, click on the snowman menu next to **"date"** to pull down a menu, click on **"Change data type…"** and select "date." You'll be asked to confirm and let the software know that it's okay to make the change. Below you can see that we're changing the "date" column from a "string" to a "date" data type.

![Date Format](/Images/dateformat.png)


# **5. Making a Thematic Map**

Now lets symbolize the data. In the data view, click "Create map" in the bottom right. This will make a new map for this dataset. Go to style the layer by clicking on the layer name and the "style" link; note that by default you're on the simple visualization. Now you're ready to play around with modifying the markers.

A marker has multiple elements you can change. The point size, a number that represents the overall size of the marker. The second is the color and opacity (transparent or not) of the marker. The third element, blending, allows you to modify how overlapping markers are displayed.

A marker "Stroke" has size (thickness of each marker's border), color, and opacity elements. To make changes to these marker features, click on the number values to make changes with a slider control.

While these simple point markers can be useful in some situations, CARTO offers many other options. Let's start by looking at adding Graduated Symbols.

![Graduated Symbols](/Images/graduatedSymbols.png)

Set the point size to "By value", then choose 'damage' as the field you want to visualize. In this case graduated symbols require numerical data. The map then shows markers with different sizes based on the amount of damage caused by the tornado.

Now you'll change the point symbol settings (point size, color, and stroke) to clean up the visualization. Try setting the point size min to 5 and a max to 20. Change the stroke size to 0.5. You can play with this and the other parameters—like fill and stroke—until you get a visualization that displays the patterns in the data.

# **6. Density Map**

Another CARTO visualization method we'll take a look at is "density". This visualization creates a gridded system over your data, counts the number of points in each grid cell, and gives each cell a color based on the number of points inside the cell. The grid is made using hexagons, and maps like these are often called Hexbin maps. They're a nice way to handle point data when you have thousands of points and would like highlight the density of those points.

To show density in CARTO, under "Aggregation", click the "Squares" or "Hexbins". In CARTO you have the option to change the cell size and method (using hexagons or rectangles). You can also change the number of buckets, which is the number of classes that your data is split into. Finally, as with the other visualizations, you can change the stroke, fill and opacity to suit your needs.

What do you notice about this view and its ability to show you the density of tornadoes?

![Hexbins](/Images/Hexbins.png)

**Add a legend**

Want to display what the colors mean? We need a legend! Still in the "tornadoes" layer options, click on the **"LEGEND"** tab. Choose the Choropleth legend. 

Give it the title **"No. of Tornados"**. Leave the labels as default.

![Legend-hex](/Images/Legend-hex.png)


# **7. Adding Labels**

Labels can be added to most symbolization method. But here let's label our hexbins.

Under the style section, click the box for "labels", then select "agg\_value" for the column field. This value is the aggregated count of all points within a bin.

There are many parameters that affect how text is displayed — font, halo, offset, overlap, and placement. You can play with the font and halo to see the visual effects these have. Make sure the "Offset" field is set to "0" to have our labels show up in the center of each bin. The "label overlap" parameter changes whether the labels are allowed to overlap one another or not. You can turn the labels off again by unchecking the "Labels."

![Labels-hex](/Images/Labels-hex.png)

# **8. Let's Make Maps That Move**
Now it's time for the really fun stuff. Animating the points on the map!!

Go back up to the map layers pane and turn off the tornados layer by clicking it's eye symbol ![Eye](/Images/eye.png).

We are going to add the another copy of the same dataset to the map because we want to play around with the tornados dataset some more, but don't want to lose the awesome stylization you just did! Click on the **"+Add New Layer"** button. Then, in the "Your Dataset" tab, add the tornadoes dataset. Let's rename this new layer so we don't confuse the two though. Click on the snowman menu next to the layer to bring up the layer menu. Click "rename" and name it something like "Animated twisters." 

"Animation" is a CARTO style that allows you to visualize geographic data over time. You can access it just like you would other styles. Go to the layer's style menu, and under aggregation, scroll to the right and select **"Animated"**.

![Animation](/Images/Animation.png)

Once you select Animation, it's probable that the column that CARTO picked to visualize is the **CARTO\_id** column. This column is an arbitrarily assigned ID number that CARTO uses and assigns based on the order of the data in your spreadsheet. In terms of mapping, it's meaningless, so we should go ahead instead the animation **column** to **date** since that makes the most sense here for driving an animation.

As with the other visualizations, you can change the stroke and fill of the markers. Experiment now with changing opacity and colors until you're happy with what you see. You may want to remove the marker stroke to clean things up a bit further.

**Adjust the timing**
There are other useful parameters in the Animation visualization as well. "Steps" refer to the number of bins that the data are broken up into when it's visualized, each becomes a frame in the animation. You can also change the duration of the visualization, which changes the length of the entire animation from beginning to end. 

Try setting a **Duration - 30** and **Steps - 365** (You'll see 1 frame per *day* in 30 seconds!).
Try setting a **Duration - 6** and **Steps - 12** (You'll see 1 frame per *month* in 6 seconds!).

Finally, you can change the trails setting for your visualization. These are the burst effects that happen after the point first appears, and leave a visual "trail" after the point disappears.

Try out some of these controls and take a look at what impact they have on your visualization.

**Accumulate the points**
In the standard Animation visualization, data points disappear after they appear on the map. If you switch the **"Accum."** toggle on, points will stay on the map, and build upon each other (*and might freeze your computer*). Often, it's best to reduce the opacity of your markers when you're using the cumulative visualization so that the effect of points layering over one another becomes noticeable. Change the **"Blending"** to **"multiply"**.

![Animation](/Images/Animation.png)

It's up to you regarding when to use the cumulative function, and when to allow your points to disappear. When you are highlighting accumulation or intensity over time, the cumulative function may be very helpful.

# **9. Publishing Our Maps**

Before you publish your map, you should change the name. You can do this in the top left of your screen by clicking the snowman menu next to next to the name "Tornados". Click "Rename" to change the title and "Edit metadata" to include details on what the data is, or where you found it.

Publish and share your map by clicking the blue "publish" button in the bottom left. Click on the red **"PRIVATE"** button to change the privacy to "Public". If you have a full-access CARTO account, in this window you can also change other parameters about your shared map. We're using the free version, so we've got fewer options. Keep in mind that because this is the free version, all maps made will be public. 

If you make any changes to the map, the "Publish" button will change to an "Update" button, so make sure you update the map here every time you make any changes.

Click **"Get the link"** to copy a link to your map to your clipboard. View it in a new tab and, if you want, email it to a friend or family member!

![Publish](/Images/Publish.png)

# **10. Takeaways**

In this workshop you got a look at a wide range of mapping possibilities with CARTO. Now is your chance to think about all of the data that could be mapped. What data would you need to collect in order to display it on a map? What use those tools to make a map that you feel best communicates the message of where tornados are historically most prevalent in the US.


## **Bonus #1: Sharing your Webmap Online**

When you click publish, you are given an option to generate an embeddable link to your map. This link allows you to embed the webmap on to your website or online portfolio. To do so, make sure your map is published, then copy the "Embed it" link. Now you can plate this link into any HTML webpage.

![Embed](/Images/Embed.png)

You will want to make sure you map is at the right zoom level and extent for the webpage format you intend on embedding it on, otherwise your map may be too zoomed in or off-centered.

IMAGE 18

## **Bonus #2: Making a Choropleth Map**

A choropleth map uses differences in shading, coloring, within predefined areas (such as county, state, or national boundaries) to indicate the average values of a property or quantity in those areas. To make your first choropleth map, you'll be using U.S. county population data. First, highlight and *copy* this link (don't click to download): http://academy.CARTO.com/d/counties.zip

If you need to you can get back to your CARTO dashboard at any time by clicking the circle icon in the top left ![Circle](/Images/circle.png).

On your map, turn off the populated place layer by clicking the eye symbol ![Eye](/Images/eye.png).

Now click on **"+ADD NEW LAYER"**

In the dialog box that appears, click **"Connect Dataset"** then *paste* the link you copied above into the link field, and click "Submit."

![Connect Dataset](/Images/ConnectDataset.png)

Let's now look at the data in the Data View. Click on the new layer, then click on the link under the layer name. This will bring up a new tab in your web browser. Take a look through the data columns. Note that this time the the\_geom column indicates "Polygon" values. This means that the geometry that CARTO will map is a polygon format rather than the point features you worked with last time. Any changes you make to the dataset here will be carried over the any of your maps using the dataset.

Going back to the map, in the layer you added ("us\_counties"), and click "STYLE". Here you can change the polygon fill and stroke (outline) color and thickness.

![Polygon Fill](/Images/PolygonFill.png)

In the same area where we have been styling the layer, click on "POP-UP". Here you'll create the information that will appear whenever a viewer clicks on a county.

Choose the "pop-up light" style.

Each column of data can have its own label or display, and you can choose which you'd like to show by clicking the check boxes to the left of the listed column names. Turn on the name, pop, and pop\_sqkm fields by selecting their toggle buttons. You can also reorder or rename the columns that you want to show. You can check your choices in real time by clicking on a county in the map after you make a change.

![Popup](/Images/Popup.png)

Next, we're going to make this into a choropleth map. Each county will be a different color based on its population. Return to "style" and change the "POLYGON COLOR" to **"by value"**.

In the selector list you can change the table column used to make the choropleth map, but remember that only columns with numerical data can be used in such a map. With this particular table data you can go ahead and choose to show "pop\_sqkm", which maps population density per square kilometer.

In the "choropleth" visualization you can also change the fill colors, county borders, and color opacity, just like you could in the "simple" visualization. Go ahead and play around with these! Also try out the different classification schemes (where it says "Quantile") and the number of buckets. These are different ways of classifying the numerical data into groups.

If you click the back arrow and "public" in the upper left of the interface, you can then click "Publish" in the upper left of the interface to share it using the link method we used earlier.

![County Population](/Images/CountyPopulation.png)

# **Note about Working with Multiple Layers in CARTO**

We already did this part as part of the instruction above but it's good to keep this in mind if you are working on your own.

In order to create a multi-layer visualization, start by creating a visualization from one of the layers you'd like to include. We start with the US Counties table that we loaded earlier, but you could just as easily start with the Tornados table. Once you've created your visualization from one table, you can add another layer from the column of icons on the right. At the top of the left menu, click the "add" button. There, you can select the table you'd like to add. In our case, it would be the us\_counties layer. Additionally, CARTO has file limits depending on your account type. Typically on a free account, you can only upload datasets with at most 500k rows of data with a max file size of 150MB (Read more [HERE](https://carto.com/docs/faqs/carto-engine-usage-limits/)).

Styling your map visualizations when you have multiple layers of data functions the same as if you had only one layer. Each layer can be styled independently of the others. It is important to remember, however, that the order of the layers reflects the order in which they rendered or displayed. So if you have one fully opaque layer over another one, you may be unable to see the data under the opaque layer. Also, if you have infowindows enabled for both layers, only the top layer's infowindows will show in areas where the bottom layer is covered by the top layer.

You can continue to play around with the visualization settings on both layers, and use the things you've learned in the previous lessons to create a good-looking visualization to share with anyone. Send a link to your parents and show them the cool stuff you're doing. This would be a great way to break the ice before you tell them you're changing your major to Geography.

# **Credit Where It's Due**

This workshop instruction was adapted from content by Bill Limpisathian from lab materials that was developed by Dr. Anthony Robinson, Dr. Peter Koby, and Dr. Sterling Quinn at Penn State based on a tutorial contributed by [CARTO](http://academy.carto.com/).

