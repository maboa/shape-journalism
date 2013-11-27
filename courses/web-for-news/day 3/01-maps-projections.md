# MAPS

## The map is not the territory

![René Magritte, La trahison des images, 1928–29](http://upload.wikimedia.org/wikipedia/en/b/b9/MagrittePipe.jpg)

Read more: [Map–territory relation](http://en.wikipedia.org/wiki/Map–territory_relation)

### Map projections

Map projections are necessary for creating maps. _All map projections **distort** the surface_ in some fashion. Depending on the _purpose_ of the map, some distortions are acceptable and others are not; therefore different _map projections exist in order to **preserve** some properties_ of the sphere-like body _at the expense of other properties._

![xkcd #977](http://imgs.xkcd.com/comics/map_projections.png)

See [Dymaxion Maps, Jason Davies](http://www.jasondavies.com/maps/airocean/)

#### Mercator projection

The Mercator projection is a cylindrical map projection presented by the Flemish geographer and cartographer Gerardus Mercator in 1569.

It is the standard map projection for nautical purposes because of its ability to represent lines of constant course, known as rhumb lines or **loxodromes**, as straight segments which conserve the angles with the meridians. 

See [Loxodrome, Jason Davies](http://www.jasondavies.com/maps/loxodrome/)

### Map projection distortions 

#### Mercator distortion

The classic way of showing the distortion inherent in a projection is to use _Tissot's indicatrix._

* Greenland takes as much space on the map as Africa, when in reality Africa's area is 14 times greater.
* Alaska takes as much area on the map as Brazil, when Brazil's area is nearly 5 times that of Alaska.
* Finland appears with a greater north-south extent than India, although India's is greater.
* Antarctica appears as the biggest continent, although it is actually the fifth in terms of area.

See [Tissot’s Indicatrix, Jason Davies](http://www.jasondavies.com/maps/tissot/)

#### BBC, [How potent are North Korea's threats?](http://www.bbc.co.uk/news/world-asia-21710644)

![North Korean missile ranges](http://news.bbcimg.co.uk/media/images/59119000/jpg/_59119706_north_korea_ranges_2.jpg)

Jason Davies in [Distances from North Korea](http://www.jasondavies.com/maps/north-korea-distance/) notes:

> BBC News has been illustrating North Korean missile ranges using an _orthographic projection_ centered at North Korea. Unfortunately, this is slightly misleading, as _distances measured relative to the centre are not preserved under this projection, particularly near the edges._ Furthermore, the orthographic projection is limited to a single hemisphere at a time, and so _much of the U.S. mainland is not shown, despite it being of interest to the story._

Check [Jason Davies and Mike Bostock's projections for D3](https://github.com/d3/d3-geo-projection/blob/master/README.md)

## Types of Maps

### Thematic Maps

A thematic map is a map that focuses on a specific theme or subject area, whereas in a general map the variety of phenomena—geological, geographical, political—regularly appear together.

The contrast between them lies in the fact that _thematic maps use the base data, such as coastlines, boundaries and places, only as points of reference for the phenomenon being mapped_. 

General maps portray the base data, such as landforms, lines of transportation, settlements, and political boundaries, for their own sake.

A thematic map is **univariate** if the non-location data is all of the same kind. Examples: population density, cancer rates, and annual rainfall.

**Bivariate** mapping shows the geographical distribution of two distinct sets of data. For example, a map showing both rainfall and cancer rates may be used to explore a possible correlation between the two phenomena.

More than two sets of data leads to **multivariate** mapping. For example, a single map might show population density in addition to annual rainfall and cancer rates.

#### Methods of thematic mapping

* **Choropleth** mapping shows statistical data aggregated over predefined regions, such as counties or states, by colouring or shading these regions. 
* **Proportional symbol** mapping uses symbols of different sizes to represent data associated with different areas or locations within the map. For example, a disc may be shown at the location of each city in a map, with the area of the disc being proportional to the population of the city.
* **Isarithmic** or **Isopleth** or **contour maps** depict smooth continuous phenomena such as precipitation or elevation
* **Dot distribution** map are used to locate each occurrence of a phenomenon.
* **Dasymetric** maps are similar to a choropleth maps, but ones in which the regions are not predefined but chosen so that the distribution of the measured phenomenon within each region is relatively uniform.

#### Cartograms

A cartogram is a map in which some _thematic mapping variable_, such as travel time, population, is substituted for land area or distance. The geometry or space of the map is _distorted_ in order to convey the information of this alternate variable.

* Area cartograms (density-equalizing maps), see [world population cartogram](http://www2.imperial.ac.uk/~mgastner/cartogram/cartogram.html)
* Distance cartograms ![Distance cartogram of the London Underground from High Barnet station](http://wiki.gis.com/wiki/images/3/32/Travel_Time_Tube_Map_-_High_Barnet.png) 

Check d3 [area cartograms](http://prag.ma/code/d3-cartogram/#popest/2010).

## Precession of Simulacra

> "Today abstraction is no longer that of the map, the double, the mirror, or the concept. Simulation is no longer that of a territory, a referential being or substance. It is the generation by models of a real without origin or reality: A hyperreal. The territory no longer precedes the map, nor does it survive it. It is nevertheless the map that precedes the territory - precession of simulacra - that engenders the territory." -- Baudrillard, [Simulacra and Simulation](http://en.wikipedia.org/wiki/Simulacra_and_Simulation)

1. The first stage is a faithful image/copy
2. The second stage is perversion of reality
3. The third stage masks the absence of a profound reality, where the simulacrum pretends to be a faithful copy, but it is a copy with no original. 
4. The fourth stage is pure simulation, in which the simulacrum has no relationship to any reality whatsoever. 

---

> "we now use the country itself, as its own map, and I assure you it does nearly as well." -- Lewis Carroll, Sylvie and Bruno Concluded 
