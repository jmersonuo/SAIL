

# UOregon SAIL
**Interactive Web Mapping with CARTO**

Ten to fifteen years ago, creating maps on the web required doing some challenging things, such as setting up server computers and using text-based markup code to specify how you wanted your map to be styled. This worked out for big corporations and governments who could afford the software and hardware and personnel to set it all up, but it made mapping difficult for journalists, small businesses, educators, and others who just wanted to visualize simple tabular data interactively.

As interactive web technologies have improved, companies like Mapbox and CARTO stepped in to fill the needs of these nontraditional GIS consumers, providing mapping solutions wherein you can upload your dataset to the cloud and style it within the web browser. The tools are convenient enough that they have also become popular with professionals in the geospatial industry, and back near the beginning of GEOG 160 you saw how even the traditional heavyweight GIS company Esri has provided ways to do simple browser-based data uploading and map design using ArcGIS Online. Today, you&#39;ll use a similar tool called CARTO and exercise some of the map design principles that you&#39;ve learned between then and now. You can complete this lab from any computer with a web browser and Internet connection.

# **1. Create a CARTO Account**

The first thing you need to do is to create a trial account with CARTO. Go to [https://carto.com/](https://carto.com/) and click the &quot;Sign Up&quot; button at the top. Then click the blue &quot;Get Started Today&quot; button.

Use any email address, or an existing google account to sign up. Then

It takes a few seconds to create your account, and once this is finished, you&#39;ll see your CARTO Dashboard.

# **2. Connecting a Table to a Map**

Once you&#39;re logged in and on your dashboard, click &quot;New Map&quot; in the middle (you may need to click the &quot;Maps&quot; link at the top if you don&#39;t see this).

Next, click &quot;Create Empty Map&quot; (on the right). (If it&#39;s your first time, it will ask if you want to Take a Tour; it&#39;s up to you, but for now, let&#39;s just edit your map.) It&#39;s possible you&#39;ll see a window asking if you want to add points, lines, or areas. If this is the case, click &quot;Skip&quot; to bypass the window and then click the &quot;Add New Layer&quot; button in the left pane.

Select &quot;Data Library.&quot; This is CARTO&#39;s public library of open data that is a good starting place for many maps you will create. The dataset we will be using is called &quot;Populated Places&quot;. Find it by clicking the &quot;search&quot; button on the left, and search for &quot;Populated Places&quot;. The search may take awhile (I had to wait almost a minute). If it takes too long you can also browse available datasets and find this one on page 5 of the results. Once the search loads you may see multiple datasets here, but make sure to select the one called &quot;Populated Places&quot; with the subtitle &quot;Most populated places&quot; made by &quot;Natural Earth Data&quot;.

Click the table&#39;s name and then click &quot;Add Layer&quot; at the bottom right of the interface to import the table into your account.

After the file processes and inputs, you will be taken straight to the &quot;Map View&quot; of this dataset. Click on the layer (&quot;ne\_10m\_populated...&quot;), then click on the link under the title (&quot;ne\_10m\_populated\_places\_simple&quot;) at the top of your screen to see the full data in this table in a new tab. Take a minute to explore it, see what columns you have available to you, and what kinds of data the table contains.

As you look at the table, take note of the second column from the left called the\_geom. It contains the latitude and longitude coordinates required to display data on a map. Without values in this column you wouldn&#39;t be able to map these data.

IMAGE 1

Now go back to your map to begin designing your visualization.



# **3. Making A Basic Thematic Map**

When you view your map, you should see something like this:

IMAGE 2

First, let&#39;s take a look at the available basemaps by clicking the &quot;Positron&quot; layer at the bottom left. There are lots to choose from, and if you wanted to, you could change settings under the hood in CARTO to bring in additional basemaps from other sources.

IMAGE 3

Play around and change the basemap a few times to see what&#39;s available. Then choose a basemap that isn&#39;t too busy, like Positron, Positron (lite), or Carto World Antique. After that&#39;s finished, click the back arrow in the top left, click your &quot;ne\_10m\_populated&quot; layer, and click on &quot;style&quot; to take a look at visualization.

IMAGE 4

Once there, keep &quot;aggregation&quot; the same, then click the &quot;fill&quot; button (the one with the yellow line in it). Click &quot;by value&quot;, then scroll to the bottom of the list to select the table column &#39;adm0cap&#39;, which contains data about which cities are capitals (represented by 1 in the legend at the bottom-right corner of the map) and which aren&#39;t (represented by 0). Click where it says &quot;Quantiles&quot; and select &quot;Category&quot;, then play around with the colors. You should have a few points showing the country capitols, and then the rest a different color.

IMAGE 5

Now you could share your map by clicking the back arrow in the top left, then by clicking &quot;public&quot; and then the blue &quot;publish&quot; button that appears in the top left.

# **4. Making a Choropleth Map**

To make your first choropleth map, you&#39;ll be using U.S. county population data. First, go ahead and copy this link:

http://academy.CARTO.com/d/counties.zip

On the same map, turn off the populated place layer by clicking the eye symbol.

Now click on &quot;+Add new Layer&quot;

If you need to you can get back to your CARTO dashboard at any time by clicking the circle icon in the top left.

In the dialog box that appears, click &quot;Connect Dataset&quot; then just paste the link you copied above into the link field, and click &quot;Submit.&quot;

IMAGE 6

Let&#39;s now look at the data in the Data View. Click on the new layer, then click on the link under the layer name. This will bring up a new tab in your web browser. Take a look through the data columns. Note that this time the the\_geom column indicates &quot;Polygon&quot; values. This means that the geometry that CARTO will map is a polygon format rather than the point features you worked with last time. Any changes you make to the dataset here will be carried over the any of your maps using the dataset.

Going back to the map, in the layer you added (&quot;us\_counties&quot;), and click &quot;style&quot;. Here you can change the polygon fill and stroke.

IMAGE 7

In the same area where we have been styling the layer, click on &quot;pop-up,&quot;. Here you&#39;ll create the information that will appear whenever a viewer clicks on a county.

Choose the &quot;light&quot; style.

Each column of data can have its own label or display, and you can choose which you&#39;d like to show by clicking the check boxes to the left of the listed column names. Turn on the name, pop, and pop\_sqkm fields by selecting their toggle buttons. You can also reorder or rename the columns that you want to show. You can check your choices in real time by clicking on a county in the map after you make a change.

IMAGE 8

Next, we&#39;re going to make this into a choropleth map. Return to &quot;style&quot; and click the &quot;fill&quot; button. Again, choose &quot;by value&quot;.

In the selector list you can change the table column used to make the choropleth map, but remember that only columns with numerical data can be used in such a map. With this particular table data you can go ahead and choose to show &quot;pop\_sqkm&quot;, which maps population density per square kilometer.

In the &quot;choropleth&quot; visualization you can also change the fill colors, county borders, and color opacity, just like you could in the &quot;simple&quot; visualization. Go ahead and play around with these! Also try out the different classification schemes (where it says &quot;Quantile&quot;) and the number of buckets. &quot;Jenks&quot; classification is the same as the &quot;Natural Breaks&quot; you learned about in class.

If you click the back arrow and &quot;public&quot; in the upper left of the interface, you can then click &quot;Publish&quot; in the upper left of the interface to share it using the link method we used earlier.

# **5. Interactive Visualization in CARTO**

In this lesson you&#39;ll be exploring tornados. To get started, copy the link below:

http://academy.CARTO.com/d/tornadoes.zip

Going back up to the map layers pane, click on &quot;+Add new Layer&quot;

If you need to you can get back to your CARTO dashboard at any time by clicking the circle icon in the top left.

In the dialog box that appears, click &quot;Connect Dataset&quot; then just paste the link you copied above into the link field, and click &quot;Submit.&quot;

If you want, you can examine the information by opening the CSV file from the link provided with Excel or another spreadsheet software. If you do, you&#39;ll see four columns: damage, date, latitude, and longitude.

In the data view on CARTO, you have all of these columns in addition to a few created by the software. One of these columns is called &quot;the\_geom,&quot; which we have mentioned in previous lessons. This time, &quot;the\_geom&quot; contains the two columns in your CSV labeled &quot;latitude&quot; and &quot;longitude&quot; — CARTO knows how to take these columns and turn them into points.

CARTO also lets you see the _types_ of data for each column. For example, you can see that **damage** is a number, and not a string data type (because it has numerical data, not text). You can also see that **date** was imported as a string, rather than a date type.

It&#39;s easy — and important — for you to change the data types, because they affect what kinds of visualizations you can create. For example, using the date type, you can do some things that you can&#39;t do with a string type. Therefore, click on the small dots menu next to &quot;date&quot; to pull down a menu, click on &quot;Change data type…&quot; and select &quot;date.&quot; You&#39;ll be asked to confirm and let the software know that it&#39;s okay to make the change. Below you can see that we&#39;re changing the &quot;date&quot; column from a &quot;string&quot; to a &quot;date&quot; data type.

IMAGE 9

# **6. Making a Thematic Map**

Now, click &quot;Create map&quot;. Go to style the layer by clicking on the layer name and the &quot;style&quot; link; note that you&#39;re by default on the simple visualization. Now you&#39;re ready to play around with modifying the markers.

A marker &quot;Fill&quot; has three elements you can change. The first represents the overall size of the marker. The second is the fill color of the marker, and the third element allows you to modify the opacity of the fill color (transparent or not).

A marker &quot;Stroke&quot; also allows you to change three marker elements. The first controls the thickness of each marker&#39;s border, the second their color, and the third the opacity of the markers&#39; border color.

To make changes to these marker features, click on the number values to make changes with a slider control.

While these simple point markers can be useful in some situations, CARTO offers many other options. Let&#39;s start by looking at adding Graduated Symbols.

IMAGE 10

Click on the number next to &quot;fill&quot; (probably &quot;7&quot;), click &quot;by value&quot;, then choose &#39;damage&#39; as the field you want to visualize. In this case graduated symbols require numerical data. The map then shows markers with different sizes based on the amount of damage caused by the tornado.

Now you&#39;ll change the parameters you are already familiar with (marker radius, fill, and stroke) to clean up the visualization. In our example above we just bumped down the stroke width to 0.5 on top of the &quot;Positron&quot; basemap, and changed the colors. You can play with this and the other parameters—like fill and stroke—until you get a visualization you like.

# **7. Density Map**

Another CARTO visualization method we&#39;ll take a look at is &quot;density&quot;. This visualization creates a gridded system over your data, counts the number of points in each grid cell, and gives each cell a color based on the number of points inside the cell. The grid is made using hexagons, and maps like these are often called Hexbin maps. Hexbin maps avoid the problem associated with most choropleth maps—counties and countries can be very different sizes, and bigger places will look more visually dominant than smaller areas. Hexbins solve the area problem by standardizing the area for each filled object. They&#39;re a nice way to handle point data when you have thousands of points and would like highlight the density of those points.

IMAGE 11

To show density in CARTO, click the &quot;Squares&quot; or &quot;Hexbins&quot; under &quot;Aggregation&quot;. In CARTO you have the option to change the cell size and method (using hexagons or rectangles). You can also change the number of buckets, which is the number of classes that your data is split into. Finally, as with the other visualizations, you can change the stroke, fill and opacity to suit your needs.

Give the hexbin wizard a try. What do you notice about this view and its ability to show you the density of tornadoes?

# **8. Adding Labels**

Labels can be added to most symbolization method. But here let&#39;s label our hexbins

Under the style section, click the box for &quot;labels&quot;, then select &quot;agg\_value&quot; for the column field. This value is the aggregated count of all points within a bin.

IMAGE 12

There are many parameters that affect how text is displayed — font, halo, offset, overlap, and placement. You can play with the font and halo to see the visual effects these have. Make sure the &quot;Offset&quot; field is set to &quot;0&quot; to have our labels show up in the center of each bin. The &quot;label overlap&quot; parameter changes whether the labels are allowed to overlap one another or not. You can turn the labels off again by unchecking the &quot;Labels.&quot;

# **9. Data Filtering**

The final thing to check out is data filtering. To get started, click the &quot;analysis&quot; button at the top-left (next to &quot;style&quot;). Click the &quot;Add analysis&quot; button, then find the &quot;Filter by column value&quot; analysis, then click the big blue button &quot;add analysis&quot; at the bottom right. This will pull up a pane that allows you to select a column to filter the data by. Choose &quot;damage&quot; and select some values to sort by. It might be useful to browse your data to see what values might be good to filter by. Once you apply your filter, it will create a sort of new layer which you can then restyle like the other ones you&#39;ve made (change the color, sizes, labels).

IMAGE 13

By looking at the &quot;damage&quot; column of the tornado data you can see that there are many tornados causing only a small amount damage and just a few very damaging tornados.

If you filter by the &quot;date&quot; column, you can see an interesting variance in when tornados occur with higher and lower frequency. What do you think is happening there?

# **10. Let&#39;s Make Maps That Move**

Go back up to the map layers pane. Click on the &quot;+Add New Layer&quot; button. Then, in the &quot;Your Dataset&quot; tab, add the tornadoes dataset. We are adding the same dataset to the map again because we want to play around with the dataset some more but don&#39;t want to lose the awesome stylization you just did! Let&#39;s rename this new layer so we don&#39;t confuse the two though. Click on the 3 dots next to the layer to bring up the layer menu. Click &quot;rename&quot; and name it something like &quot;animated twisters.&quot; Let&#39;s also turn off the old tornado layer.

&quot;Animation&quot; is a CARTO style that allows you to visualize geographic data over time. You can access it just like you would other styles, by selecting &quot;animation&quot; under &quot;aggregation&quot; in the style menu.

IMAGE 14

Once you select Animation, it&#39;s probable that the column that CARTO picked to visualize is the **CARTO\_id** column. This column is an arbitrarily assigned ID number that CARTO uses and assigns based on the order of the data in your spreadsheet. In terms of mapping, it&#39;s meaningless, so we should go ahead and select the column labeled **date** since that makes the most sense here for driving an animation.

As with the other visualizations, you can change the stroke and fill of the markers. Experiment now with changing opacity and colors until you&#39;re happy with what you see. You may want to remove the marker stroke to clean things up a bit further.

There are other useful parameters in the Animation visualization as well. &quot;Steps&quot; refer to the number of bins that the data are broken up into when it&#39;s visualized. You can also change the duration of the visualization, which changes the length of the entire animation from beginning to end. Finally, you can change the trails setting for your visualization. These are the burst effects that happen after the point first appears, and leave a visual &quot;trail&quot; after the point disappears.

Try out some of these controls and take a look at what impact they have on your visualization.

In the standard Animation visualization, data points disappear after they appear on the map. If you switch the &quot;Accum.&quot; toggle on, points will stay on the map, and build upon each other (and might freeze your computer). Often, it&#39;s best to reduce the opacity of your markers when you&#39;re using the cumulative visualization so that the effect of points layering over one another becomes noticeable.

IMAGE 15

It&#39;s up to you regarding when to use the cumulative function, and when to allow your points to disappear. When you are highlighting accumulation or intensity over time, the cumulative function may be very helpful.

# **11. Publishing Our Maps**

Before you publish your map, you may want to change the name. You can do this in the top left of your screen by clicking the three dots next to the name. This is a good place to include details on what the data is, or where you found it.

Once you&#39;ve included that, you can publish and share your visualization. To do so, click &quot;Publish&quot; at the bottom of the left pane of your visualization. If you have a full-access CARTO account, in this window you can also change other parameters about your shared map. We&#39;re using the free version, so we&#39;ve got fewer options. Keep in mind that because this is the free version, all maps made will be public.

IMAGE 16

On this publication page click &quot;Publish&quot; at the top left under the map title to save and publish it. Additionally, if you make any changes to the map, the &quot;Publish&quot; button will change to an &quot;Update&quot; button, so make sure you update the map here every time you make any changes.

## **Bonus: Sharing your Webmap Online**

When you click publish, you are given an option to generate an embeddable link to your map. This link allows you to embed the webmap on to your website or online portfolio. To do so, make sure your map is published, then copy the &quot;Embed it&quot; link. Now you can plate this link into any HTML webpage.

IMAGE 17

You will want to make sure you map is at the right zoom level and extent for the webpage format you intend on embedding it on, otherwise your map may be too zoomed in or off-centered.

IMAGE 18

# **12. Note about Working with Multiple Layers in CARTO**

We already did this part as part of the instruction above but it&#39;s good to keep this in mind if you are working on your own.

In order to create a multi-layer visualization, start by creating a visualization from one of the layers you&#39;d like to include. We start with the US Counties table that we loaded earlier, but you could just as easily start with the Tornados table. Once you&#39;ve created your visualization from one table, you can add another layer from the column of icons on the right. At the top of the left menu, click the &quot;add&quot; button. There, you can select the table you&#39;d like to add. In our case, it would be the us\_counties layer. Additionally, CARTO has file limits depending on your account type. Typically on a free account, you can only upload datasets with at most 500k rows of data with a max file size of 150MB (Read more [HERE](https://carto.com/docs/faqs/carto-engine-usage-limits/)).

Styling your map visualizations when you have multiple layers of data functions the same as if you had only one layer. Each layer can be styled independently of the others. It is important to remember, however, that the order of the layers reflects the order in which they rendered or displayed. So if you have one fully opaque layer over another one, you may be unable to see the data under the opaque layer. Also, if you have infowindows enabled for both layers, only the top layer&#39;s infowindows will show in areas where the bottom layer is covered by the top layer.

You can continue to play around with the visualization settings on both layers, and use the things you&#39;ve learned in the previous lessons to create a good-looking visualization to share with anyone. Send a link to your parents and show them the cool stuff you&#39;re doing. This would be a great way to break the ice before you tell them you&#39;re changing your major to Geography.

# **13. Takeaways**

In this workshop you got a look at a wide range of mapping possibilities with CARTO. Now is your chance to use those tools to make a map that you feel best communicates the message of where tornados are historically most prevalent in the US.

# **14. Credit Where It&#39;s Due**

This workshop instruction was adapted from content by Bill Limpisathian from lab materials that was developed by Dr. Anthony Robinson, Dr. Peter Koby, and Dr. Sterling Quinn at Penn State based on a tutorial contributed by [CARTO](http://academy.carto.com/).

