---
title: Process Map
weight: 6
---

The ProcessMap operation allows the user to request a map. Depending on the input parameter, different map images will be returned. This method allows a user to request a map, or a map with visual representation of a route between points/locations.

#### Schema

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:m0="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
  <SOAP-ENV:Header>
    <m:AuthHeader xmlns:m="http://www.alk.com">
      <m:Authorization>String</m:Authorization>
      <m:Date>String</m:Date>
    </m:AuthHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <m:ProcessMap xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
        <m:Body>
          <m:Map>
            <m:Viewport>
              <m:Center>
                <m:Lat>String</m:Lat>
                <m:Lon>String</m:Lon>
              </m:Center>
              <m:ScreenCenter>
                <m:X>0</m:X>
                <m:Y>0</m:Y>
              </m:ScreenCenter>
              <m:ZoomRadius>3.14159265358979E0</m:ZoomRadius>
              <m:CornerA>
                <m:Lat>String</m:Lat>
                <m:Lon>String</m:Lon>
              </m:CornerA>
              <m:CornerB>
                <m:Lat>String</m:Lat>
                <m:Lon>String</m:Lon>
              </m:CornerB>
              <m:Region>NA</m:Region>
            </m:Viewport>
            <m:Projection>Default</m:Projection>
            <m:Style>Default</m:Style>
            <m:ImageOption>Both</m:ImageOption>
            <m:Width>0</m:Width>
            <m:Height>0</m:Height>
            <m:Drawers>
              <m:DrawerType>Airports</m:DrawerType>
            </m:Drawers>
            <m:LegendDrawer>
              <m:Legend>
                <m:Type>ScaleOfMiles</m:Type>
                <m:DrawOnMap>true</m:DrawOnMap>
              </m:Legend>
            </m:LegendDrawer>
            <m:GeometryDrawer>
              <m:Geometry>
                <m:Color>
                  <m:Red>255</m:Red>
                  <m:Green>255</m:Green>
                  <m:Blue>255</m:Blue>
                </m:Color>
              </m:Geometry>
            </m:GeometryDrawer>
            <m:PinDrawer>
              <m:PointGroupDensity>Average</m:PointGroupDensity>
              <m:PointSpreadInGroup>Average</m:PointSpreadInGroup>
              <m:DrawOnMap>true</m:DrawOnMap>
              <m:Pins>
                <m:Pin>
                  <m:ID>0</m:ID>
                  <m:Point>
                    <m:Lat>String</m:Lat>
                    <m:Lon>String</m:Lon>
                  </m:Point>
                  <m:Image>String</m:Image>
                  <m:Category>String</m:Category>
                  <m:Label>String</m:Label>
                </m:Pin>
              </m:Pins>
            </m:PinDrawer>
            <m:PinCategories>
              <m:PinCategory>
                <m:ImageName>String</m:ImageName>
                <m:ImageNameForIndividual>String</m:ImageNameForIndividual>
                <m:Name>String</m:Name>
                <m:PinType>PDW_BMP</m:PinType>
                <m:Style>
                  <m:Font>
                    <m:Color>
                      <m:Red>255</m:Red>
                      <m:Green>255</m:Green>
                      <m:Blue>255</m:Blue>
                    </m:Color>
                    <m:Height>255</m:Height>
                    <m:Weight>255</m:Weight>
                  </m:Font>
                  <m:Pen>
                    <m:Color>
                      <m:Red>255</m:Red>
                      <m:Green>255</m:Green>
                      <m:Blue>255</m:Blue>
                    </m:Color>
                    <m:Widths>255</m:Widths>
                    <m:Widths1>255</m:Widths1>
                    <m:Widths2>255</m:Widths2>
                    <m:Widths3>255</m:Widths3>
                  </m:Pen>
                  <m:Brush>
                    <m:Color>
                      <m:Red>255</m:Red>
                      <m:Green>255</m:Green>
                      <m:Blue>255</m:Blue>
                    </m:Color>
                    <m:Opacity>65535</m:Opacity>
                  </m:Brush>
                  <m:ImageShadow>
                    <m:Color>
                      <m:Red>255</m:Red>
                      <m:Green>255</m:Green>
                      <m:Blue>255</m:Blue>
                    </m:Color>
                    <m:Opacity>255</m:Opacity>
                    <m:OffsetX>127</m:OffsetX>
                    <m:OffsetY>127</m:OffsetY>
                  </m:ImageShadow>
                  <m:IndividualImageName>String</m:IndividualImageName>
                  <m:GroupImageName>String</m:GroupImageName>
                </m:Style>
                <m:ZOrder>0</m:ZOrder>
              </m:PinCategory>
            </m:PinCategories>
            <m:TrafficDrawer>
              <m:Type>Congestion</m:Type>
              <m:TimeType>Actual</m:TimeType>
              <m:DateAndTime>
                <m:CalendarDate>String</m:CalendarDate>
                <m:DayOfWeek>Sunday</m:DayOfWeek>
                <m:TimeOfDay>String</m:TimeOfDay>
                <m:TimeZone>Local</m:TimeZone>
              </m:DateAndTime>
            </m:TrafficDrawer>
            <m:MapLayering>MapAndPointsOneLayer</m:MapLayering>
          </m:Map>
          <m:Routes>
            <m:MapRoute>
              <m:RouteId>String</m:RouteId>
              <m:Stops>
                <m:StopLocation>
                  <m:Address>
                    <m:StreetAddress>String</m:StreetAddress>
                    <m:City>String</m:City>
                    <m:State>String</m:State>
                    <m:Zip>String</m:Zip>
                    <m:County>String</m:County>
                    <m:Country>String</m:Country>
                    <m:SPLC>String</m:SPLC>
                    <m:CountryPostalFilter>US</m:CountryPostalFilter>
                    <m:AbbreviationFormat>FIPS</m:AbbreviationFormat>
                  </m:Address>
                  <m:Coords>
                    <m:Lat>String</m:Lat>
                    <m:Lon>String</m:Lon>
                  </m:Coords>
                  <m:Region>Unknown</m:Region>
                  <m:Label>String</m:Label>
                  <m:PlaceName>String</m:PlaceName>
                  <m:Costs>
                    <m:CostOfStop>3.14159265358979E0</m:CostOfStop>
                                       <m:HoursPerStop>3.14159265358979E0</m:HoursPerStop>
                    <m:Loaded>true</m:Loaded>
                    <m:OnDuty>true</m:OnDuty>
                    <m:UseOrigin>true</m:UseOrigin>
                  </m:Costs>
                  <m:IsViaPoint>true</m:IsViaPoint>
                </m:StopLocation>
              </m:Stops>
              <m:Options>
                <m:BordersOpen>true</m:BordersOpen>
                <m:ClassOverrides>None</m:ClassOverrides>
                <m:DistanceUnits>Miles</m:DistanceUnits>
                <m:FuelRoute>true</m:FuelRoute>
                <m:HazMatType>None</m:HazMatType>
                <m:HighwayOnly>true</m:HighwayOnly>
                <m:HubRouting>true</m:HubRouting>
                <m:OverrideRestrict>true</m:OverrideRestrict>
                <m:RouteOptimization>None</m:RouteOptimization>
                <m:RoutingType>Practical</m:RoutingType>
                <m:TollDiscourage>true</m:TollDiscourage>
                <m:TruckCfg>
                  <m:Axles>0</m:Axles>
                  <m:Height>String</m:Height>
                  <m:LCV>true</m:LCV>
                  <m:Length>String</m:Length>
                  <m:Units>English</m:Units>
                  <m:Weight>String</m:Weight>
                  <m:Width>String</m:Width>
                </m:TruckCfg>
                <m:UseAvoidsAndFavors>true</m:UseAvoidsAndFavors>
                <m:VehicleType>Truck</m:VehicleType>
              </m:Options>
              <m:FuelOptions>
                <m:UserID>String</m:UserID>
                <m:Password>String</m:Password>
                <m:Account>String</m:Account>
                <m:FuelCap>3.14159265358979E0</m:FuelCap>
                <m:Level>3.14159265358979E0</m:Level>
                <m:MPG>3.14159265358979E0</m:MPG>
              </m:FuelOptions>
              <m:AFOptions>
                <m:AFSetIDs>
                  <m0:int>0</m0:int>
                </m:AFSetIDs>
                <m:APIKey>String</m:APIKey>
                <m:Tags>
                  <m0:string>String</m0:string>
                </m:Tags>
              </m:AFOptions>
              <m:DrawLeastCost>true</m:DrawLeastCost>
              <m:RouteLegOptions>
                <m:LineOptions>
                  <m:RouteLineOptions>
                    <m:Color>
                      <m:Red>255</m:Red>
                      <m:Green>255</m:Green>
                      <m:Blue>255</m:Blue>
                    </m:Color>
                    <m:Width>0</m:Width>
                  </m:RouteLineOptions>
                </m:LineOptions>
                <m:TextOptions>
                  <m:RouteLabelOptions>
                    <m:Color>
                      <m:Red>255</m:Red>
                      <m:Green>255</m:Green>
                      <m:Blue>255</m:Blue>
                    </m:Color>
                    <m:FontSize>0</m:FontSize>
                  </m:RouteLabelOptions>
                </m:TextOptions>
              </m:RouteLegOptions>
              <m:StopLabelDrawer>Name</m:StopLabelDrawer>
            </m:MapRoute>
          </m:Routes>
        </m:Body>
      </m:Request>
    </m:ProcessMap>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### ProcessMap Request

**Request Body Members**

Gets or sets the request body which contains specific information associated with creating the map.

| Element  | Definition                                                                                                                                                                                                                                                                                                                                                                                      | Required |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `Map`    | A MapSettings System Object. Gets or sets the map settings which control options for drawing the map.<br>Usage:<br><small>MapRequestBody mapArea = new MapRequestBody();<br>mapArea.Height = 768;<br>mapArea.Width = 1024;<br>mapArea.Viewport = new MapViewport()<br>{<br> Region = MapRegion.NA,<br> RegionSpecified = true,<br> ZoomRadius = 0,<br> ZoomRadiusSpecified = true<br>};</small> | Y        |
| `Routes` | A list<> of MapRoute object (inherited by the Routes object). Gets or sets the map settings which control options for drawing the map.<br>Usage:<br><small>MapRoute route = new MapRoute();<br>route.Stops = stops;</small>                                                                                                                                                                     | Y        |

**MapSettings Members**

Represents various settings associated with requesting a map.

<table class="table table-sm">
                <thead>
                    <tr>
                        <th>Element</th>
                        <th>Definition</th>
                        <th>Required</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><code>Drawer</code></td>
                        <td>A list&lt;&gt; of <a href="#DrawerType">DrawerType</a> enumeration object. Gets or sets the collection of drawers which controls which feature layers are drawn on the map. See <a href="#DrawerType">DrawerType</a> for a list of possible drawers.
                            <br>
                            Usage:<br>
                            <span>DrawerType[] dt = new DrawerType[6];</span>
                            <br>
                            <span>dt[0] = DrawerType.Water;</span>
                            <br>
                            <span>dt[1] = DrawerType.Route;</span>
                            <br>
                            <span>dt[2] = DrawerType.City;</span>
                            <br>
                            <span>dt[3] = DrawerType.StateBoundaries;</span>
                            <br>
                            <span>dt[4] = DrawerType.Stop;</span>
                            <br>
                            <span>dt[5] = DrawerType.Land;</span>
                            <br>
                            <span>mapArea.Drawers=dt;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>GeometryDrawer</code></td>
                        <td>A list&lt;&gt; of <a href="#Geometry">Geometry</a> object. Gets or sets the collection of geometries to draw on the map.
                            <br>
                            Usage: <span>var geom = new RegionGeometry()</span> <br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;Color = new RGB();</span><br>
                            <span>&nbsp;&nbsp;{</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;Red = 150,</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;RedSpecified = true</span><br>
                            <span>&nbsp;&nbsp;}</span><br>
                            <span>};</span><br>
                            <span>var geometry = new Geometry[]{geom}</span><br>
                            <span>mapArea.GeometryDrawer = geometry;</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Height</code></td>
                        <td>An integer value. Gets or sets the map heigh in pixels with a max value of 2048.
                            <br>
                            Usage:<span>mapArea.Height = 768;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>ImageOption</code></td>
                        <td>An enumeration of MapImageOption. Gets or sets image preference for Satellite and Terrain Style. <strong>Note:</strong> Terrain style is only available for Tile request.
                            <br>
                            Values:<br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td><code>Both</code></td>
                                        <td>0</td>
                                        <td>Basemap is overlayed on background image.</td>
                                    </tr>
                                    <tr>
                                        <td><code>Background</code></td>
                                        <td>1</td>
                                        <td>Pure image underlay with no basemap overlay.</td>
                                    </tr>
                                    <tr>
                                        <td><code>Foreground</code></td>
                                        <td>2</td>
                                        <td>Pure basemap transparent image with no underlay.</td>
                                    </tr>
                                </tbody>
                            </table>
                            Usage:<span>mapArea.ImageOption = MapImageOption.Both;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>LegendDrawer</code></td>
                        <td>A list&lt;&gt; of <a href="#Legend">Legend</a> object. Gets or sets the collection of legends to include with this map request. Legends may be drawn on the map or on a separate layer.
                            <br>
                            Usage: <span>Legend[] legend = new Legend[1];</span> <br>
                            <span>legend[0] = new Legend()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;DrawOnMap = true,</span><br>
                            <span>&nbsp;&nbsp;Type = LegendType.RouteLegend,</span><br>
                            <span>&nbsp;&nbsp;TypeSpecified = true</span><br>
                            <span>};</span><br>
                            <span>mapArea.LegendDrawer = legend;</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>MapLayering</code></td>
                        <td>An enumeration of MapLayering. Gets or sets a value which controls how to map and points layer are drawn.
                            <br>
                            Values:<br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td><code>MapAndPointsOneLayer</code></td>
                                        <td>0</td>
                                        <td>Indicates that the map and points layer is returned as one layer.</td>
                                    </tr>
                                    <tr>
                                        <td><code>MapLayer</code></td>
                                        <td>1</td>
                                        <td>Indicates that only the map layer is returned.</td>
                                    </tr>
                                    <tr>
                                        <td><code>PointsLayer</code></td>
                                        <td>2</td>
                                        <td>Indicates that only the points layer is returned.</td>
                                    </tr>
                                    <tr>
                                        <td><code>MapAndPointsTwoLayer</code></td>
                                        <td>3</td>
                                        <td>Indicates that the map and points layer are returned on separate layers.</td>
                                    </tr>
                                    <tr>
                                        <td><code>BackgroundOnly</code></td>
                                        <td>4</td>
                                        <td>Indicates that only the background layer is returned.</td>
                                    </tr>
                                    <tr>
                                        <td><code>NoBackground</code></td>
                                        <td>5</td>
                                        <td>Indicates that no background layer is returned as part of the map.</td>
                                    </tr>
                                </tbody>
                            </table>
                            Usage:<span>mapArea.MapLayering = MapLayering.MapAndPointsTwoLayers;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>PinCategories</code></td>
                        <td>
                            A list&lt;&gt; of <a href="#PinCategory">PinCategory</a> object. Gets or sets the point categories which is needed when grouping points.
                            <br>
                            Usage:<br>
                            <span>PinCategory[] pc = new PinCategory[1];</span> <br>
                            <span>pc[0] = new PinCategory()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;PinType = PinTpye.PDW_CIRCLE,</span><br>
                            <span>&nbsp;&nbsp;PinTypeSpecified = true</span><br>
                            <span>};</span><br>
                            <span>mapArea.PinCategories = pc;</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>PinDrawer</code></td>
                        <td>
                            A <a href="#PinDrawer">PinDrawer</a> system object. Gets or sets the pin drawer for the map which controls what points are drawn on the map and how they are drawn.
                            <br>
                            Usage: <br>
                            <span>PinDrawer pd = new PinDrawer();</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;DrawOnMap = true,</span><br>
                            <span>&nbsp;&nbsp;DrawOnMapSpecified = true,</span><br>
                            <span>&nbsp;&nbsp;Pins = new Pin[]{ pin1, pin2 }</span><br>
                            <span>};</span><br>
                            <span>mapArea.PinDrawer = pd;</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Projection</code></td>
                        <td>An enumeration of Projection Type. Gets or sets the projection of the map.
                            <br>
                            Values:<br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td><code>Default</code></td>
                                        <td>0</td>
                                        <td>Indicates the default projection.</td>
                                    </tr>
                                    <tr>
                                        <td><code>FixedLat</code></td>
                                        <td>1</td>
                                        <td>Indicates the fixed latitude projection, ie. ESPG:4326.</td>
                                    </tr>
                                    <tr>
                                        <td><code>Mercator</code></td>
                                        <td>2</td>
                                        <td>Indicates the mercator projection, ie. ESPG:900913.</td>
                                    </tr>
                                </tbody>
                            </table>
                            Usage:<span>mapArea.Projection = ProjectionType.Mercator;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Style</code></td>
                        <td>An enumeration of <a href="#MapStyle">MapStyle</a>. Gets or sets the map style.
                            <br>
                            Usage: <span>mapArea.Style = MapStyle.Contemporary;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>TrafficDrawer</code></td>
                        <td>
                            A <a href="#TrafficDrawer">TrafficDrawer</a> system object. Gets or sets the pin drawer for the map.
                            <br>
                            Usage: <br>
                            <span>TrafficDrawer td = new TrafficDrawer();</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;DateAndTime = new DateTimeType(){</span><br>
                            <span>&nbsp;&nbsp;CalendarDate = "01/13/2015",</span><br>
                            <span>},</span><br>
                            <span>TimeType = TrafficTime.Actual,</span><br>
                            <span>TimeTypeSpecified=true</span><br>
                            <span>};</span><br>
                            <span>mapArea.TrafficDrawer = td;</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Viewport</code></td>
                        <td>A <a href="#MapViewPort">MapViewport</a> system object. Gets or sets the map's view port.
                            <br>
                            Usage: <span>mapArea.Viewport = new MapViewport()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;Region = MapRegion.NA,</span><br>
                            <span>&nbsp;&nbsp;RegionSpecified = true</span><br>
                            <span>};</span><br>
                        </td>
                        <td>Y</td>
                    </tr>
                    <tr>
                        <td><code>Width</code></td>
                        <td>An integer value. Gets or sets the map width in pixels with a max value of 2048.
                            <br>
                            Usage: <span>mapArea.Width = 1024;</span>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

#### MapViewPort Members

Represents the geographic display settings of a map as part of a MapSettings object.

<table class="table table-sm">
                <thead>
                    <tr>
                        <th>Element</th>
                        <th>Definition</th>
                        <th>Required</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><code>Center</code></td>
                        <td>A coordinate system object. Gets or sets the geographic coordinates for the desired center point of the map.
                            <br>
                            Usage:<br>
                            <span>Center = new Coordinates()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;Lat = "40.194214",</span><br>
                            <span>&nbsp;&nbsp;Lon = "-74.882612"</span><br>
                            <span>};</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>CornerA</code></td>
                        <td>A coordinate system object. Gets or sets the geographic coordinates for the first corner of the map which should be diagonally across the second corner.
                            <br>
                            Usage:<br>
                            <span>CornerA = new Coordinates()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;Lat = "40.194214",</span><br>
                            <span>&nbsp;&nbsp;Lon = "-74.882612"</span><br>
                            <span>};</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>CornerB</code></td>
                        <td>A coordinate system object. Gets or sets the geographic coordinates for the second corner of the map which should be diagonally across the first corner.
                            <br>
                            Usage:<br>
                            <span>CornerA = new Coordinates()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;Lat = "40.194214",</span><br>
                            <span>&nbsp;&nbsp;Lon = "-74.882612"</span><br>
                            <span>};</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Region</code></td>
                        <td>An enumeration of DataRegion. Gets or sets the Region that the location is in.
                            <br>
                            Usage:<span>Region = DataRegion.NA;</span>
                        </td>
                        <td>Y</td>
                    </tr>
                    <tr>
                        <td><code>ScreenCenter</code></td>
                        <td>A <a href="#Point">Point</a> system object. Gets or sets the desired center of the map in pixels.
                            <br>
                            Usage:<br>
                            <span>ScreenCenter = new Point()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;x = 3,</span><br>
                            <span>&nbsp;&nbsp;y = 2</span><br>
                            <span>};</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>ZoomRadius</code></td>
                        <td>A double value. Gets or sets the zoom radius(in miles) which is a numeric entry representing the radius of the circle which defines the map to be displayed.
                            <br>
                            Usage:<span>ZoomRadius = 15;</span>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

#### Legend Members

Represents a request for a map legend including the type of legend and whether or not it should be drawn on the map or a separate layer.

<table class="table table-sm">
                <thead>
                    <tr>
                        <th>Element</th>
                        <th>Definition</th>
                        <th>Required</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><code>DrawOnMap</code></td>
                        <td>A boolean value. Gets or sets a value indicating whether to draw legend on map or on a separate layer.
                            <br>
                            Usage:<br>
                            <span>DrawOnMap = true;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Type</code></td>
                        <td>An enumeration of LegendType. Gets or sets the type of legend. <!-- See <a href="https://pcmiler.alk.com/APIs/SOAP/v1.0/help/html/c5f0c95c-a6ff-ff46-2a32-2332698dddad.htm">LegendType</a> for what legends are supported. -->
                            <br>
                            Values:<br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td><code>ScaleOfMiles</code></td>
                                        <td>0</td>
                                        <td>Indicates a Scale of miles (or kms) legend.</td>
                                    </tr>
                                    <tr>
                                        <td><code>RouteLegend</code></td>
                                        <td>1</td>
                                        <td>Indicates a route legend.</td>
                                    </tr>
                                    <tr>
                                        <td><code>RoadLegend</code></td>
                                        <td>2</td>
                                        <td>Indicates a road class legend.</td>
                                    </tr>
                                    <tr>
                                        <td><code>HazMatLegend</code></td>
                                        <td>3</td>
                                        <td>Indicates a hazardous material restrictions legend.</td>
                                    </tr>
                                    <tr>
                                        <td><code>TrafficLegend</code></td>
                                        <td>4</td>
                                        <td>Indicates a traffic congestion legend.</td>
                                    </tr>
                                </tbody>
                            </table>
                            Usage:<span>Type = LegendType.RouteLegend;</span>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

#### DrawerType Enumeration Members

Represents the types of layers that can be drawn on a map.

| Member name              | Value | Description                                                          |
| ------------------------ | ----- | -------------------------------------------------------------------- |
| `Airport`                | 0     | Indicates a airports.                                                |
| `AvoidFavor`             | 1     | Indicates that avoids and favors should be shown on the map.         |
| `City`                   | 2     | Indicates cities.                                                    |
| `CommerciallyProhibited` | 4     | Indicates commercially prohibited roads.                             |
| `CountryBoundaries`      | 5     | Indicates country boundaries.                                        |
| `CountyBoundaries`       | 6     | Indicates county boundaries.                                         |
| `HazMat`                 | 7     | Indicates hazardous material restrictions.                           |
| `Land`                   | 8     | Indicates land masses and in general this should always be included. |
| `LinkLabel`              | 9     | Indicates road names.                                                |
| `MilitarBases`           | 10    | Indicates military bases.                                            |
| `Network`                | 11    | Indicates roads.                                                     |
| `Ortholmage`             | 12    | Indicates satellite imagery.                                         |
| `Parks`                  | 13    | Indicates parks.                                                     |
| `Place`                  | 14    | Indicates points of interest.                                        |
| `PointDrawerWeb`         | 15    | Indicates user supplied points.                                      |
| `Railroads`              | 16    | Indicates rail roads.                                                |
| `Route`                  | 17    | Indicates user supplied routes.                                      |
| `Shield`                 | 18    | Indicates road shields.                                              |
| `StaaDesignation`        | 20    | Indicates truck designations.                                        |
| `StateBoundaries`        | 21    | Indicates state and country boundaries.                              |
| `Stop`                   | 22    | Indicates the name of stops along a route.                           |
| `TimeZone`               | 23    | Indicates time zone dividers.                                        |
| `TruckRestrictions`      | 24    | Indicates truck restrictions.                                        |
| `UrbanAreas`             | 25    | Indicates urban areas.                                               |
| `Water`                  | 26    | Indicates Water bodies such as oceans, lakes, river, etc.            |
| `ExitLabel`              | 27    | Indicates exit labels for roads.                                     |
| `PolygonLabel`           | 28    | Indicates polygon labels.                                            |

#### MapStyle Enumeration Members

Represents the visual look and feel of a map.

| Member name    | Value | Description                                               |
| -------------- | ----- | --------------------------------------------------------- |
| `Default`      | 0     | Indicates the default map style.                          |
| `Classic`      | 1     | Indicates a classic motif style.                          |
| `Monochrome`   | 2     | Indicates a monochrome style.                             |
| `RoadAtlas`    | 3     | Indicates a style that mimics a road atlas look and feel. |
| `Darkness`     | 4     | Indicates a dark style.                                   |
| `Modern`       | 5     | Indicates a modern style.                                 |
| `Contemporary` | 6     | Indicates a contemporary style.                           |
| `Night`        | 7     | Indicates a style optimized for night viewing.            |
| `Satellite`    | 8     | Indicates the style for satellite imagery.                |
| `Lightness`    | 9     | Indicates the style for lightness style.                  |
| `Smooth`       | 10    | Indicates the style for smooth style.                     |
| `Terrain`      | 11    | Indicates the style of terrain imagery.                   |

#### Geometry Members

Represents a general geometry as used in drawing shapes on a map.

<table class="table table-sm">
  <thead>
    <tr>
      <th>Element</th>
      <th>Definition</th>
      <th>Required</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>Color</code></td>
      <td>
        A list &lt;&gt; of <a href="#RGB">RGB</a> object. Gets or sets the color
        of the geometry.
        <br />
        Usage:<br />
        <span>var geom = new RegionGeometry()</span><br />
        <span>{</span><br />
        <span>&nbsp;&nbsp;Color = new RGB();</span><br />
        <span>&nbsp;&nbsp;{</span><br />
        <span>&nbsp;&nbsp;&nbsp;&nbsp;Red = 150,</span><br />
        <span>&nbsp;&nbsp;&nbsp;&nbsp;RedSpecified = true</span
        ><br />
        <span>&nbsp;&nbsp;}</span><br />
        <span>};</span><br />
        <span>var geometry = new Geometry[]</span><br />
        <span>{</span><br />
        <span>&nbsp;&nbsp;geom</span><br />
        <span>};</span><br />
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

#### RGB Members

Represents a color made up of its red, green and blue components.

| Element | Definition                                                                                      | Required(at least one color below is required when using color structure.) |
| ------- | ----------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `Blue`  | A byte value. Gets or sets the blue component of the color from 0 to 255<br>Usage:Blue = 200;   | N                                                                          |
| `Green` | A byte value. Gets or sets the green component of the color from 0 to 255<br>Usage:Green = 150; | N                                                                          |
| `Red`   | A byte value. Gets or sets the red component of the color from 0 to 255<br>Usage:Red = 220;     | N                                                                          |

#### TrafficDrawer Members

The TrafficDrawer structure will be used to control the road speed or congestion overlay on a map.

<table class="table table-sm">
                <thead>
                    <tr>
                        <th>Element</th>
                        <th>Definition</th>
                        <th>Required</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><code>DateAndTime</code></td>
                        <td>A <a href="#DateTimeType">DateTimeType</a> system object. Gets or sets the date, time, day of week and time zone information.
                            <br>
                            Usage: <span>DateAndTime = new DateTimeType();</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>TimeType</code></td>
                        <td>An enumeration of TrafficTime. Gets or sets the value indicating the type of time to display for traffic. Acceptable entries are Historic, Actual or Default.
                            <br>
                            Values:<br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td><code>Actual</code></td>
                                        <td>0</td>
                                        <td>Indicates that the traffic feed is using real time data.</td>
                                    </tr>
                                    <tr>
                                        <td><code>Historic</code></td>
                                        <td>2</td>
                                        <td>Indicates that a traffic information is using historical data.</td>
                                    </tr>
                                    <tr>
                                        <td><code>Default</code></td>
                                        <td>4</td>
                                        <td>Indicates that traffic information is using default data. This value is not valid when the trafficType is Congestion.
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                            Usage:<span>TimeType = TrafficTime.Actual;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Type</code></td>
                        <td>An enumeration of TrafficTime. Gets or sets the type of traffic overlay. Acceptable entries are RoadSpeed, Congestion or Neither.
                            <br>
                            Values:<br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td><code>Congestion</code></td>
                                        <td>0</td>
                                        <td>Indicates that the traffic information is for congestion data.</td>
                                    </tr>
                                    <tr>
                                        <td><code>RoadSpeed</code></td>
                                        <td>1</td>
                                        <td>Indicates that traffic information is of road speed data.</td>
                                    </tr>
                                    <tr>
                                        <td><code>Neither</code></td>
                                        <td>3</td>
                                        <td>Indicates that no traffic information is requested.
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                            Usage:<span>Type = TrafficType.RoadSpeed;</span>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

#### Point Members

Represents a screen point's pixel coordinates.

| Element | Definition                                                                       | Required |
| ------- | -------------------------------------------------------------------------------- | -------- |
| `X`     | An integer value. Gets or sets the horizontal pixel coordinates.<br>Usage:X = 3; | Y        |
| `Y`     | An integer value. Gets or sets the vertical pixel coordinate.<br>Usage:Y = 2;    | Y        |

#### PinDrawer Members

Represents the point drawer for the map which contains the pins as well as properties related to grouping.

<table class="table table-sm">
                <thead>
                    <tr>
                        <th>Element</th>
                        <th>Definition</th>
                        <th>Required</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><code>DrawOnMap</code></td>
                        <td>A boolean value. Gets or sets a value indicating whether or not the pins are to be drawn on the map.
                            <br>
                            Usage: <span>DrawOnMap = true;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Pins</code></td>
                        <td>A list &lt;&gt; of <a href="#Pin">Pin</a> object. Gets or sets the collection of pins.
                            <br>
                            Usage:<span>var pin1 = new Pin()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;Point = new Coordinates();</span><br>
                            <span>&nbsp;&nbsp;{</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;Lat = "40.388144",</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;Lon = "-74.655566"</span><br>
                            <span>&nbsp;&nbsp;}</span><br>
                            <span>&nbsp;&nbsp;Image = "ltruck_g"</span><br>
                            <span>};</span><br>
                            <span>Pins = new Pin[] { pin1, pin2 }</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>PointGroupDensity</code></td>
                        <td>An enumeration of PointGroupDensity. Gets or sets the point group density.
                            <br>
                            Values:<br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td><code>Average</code></td>
                                        <td>0</td>
                                        <td>Indicates an average density. This is the default value.</td>
                                    </tr>
                                    <tr>
                                        <td><code>Few</code></td>
                                        <td>1</td>
                                        <td>Indicates a low density. This means that the group will be large and few.</td>
                                    </tr>
                                    <tr>
                                        <td><code>Most</code></td>
                                        <td>2</td>
                                        <td>Indicates a high density. This means that the group will be small and numerous.
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                            Usage:<span>PointGroupDensity = PointGroupDensity.Average;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>PointSpreadInGroup</code></td>
                        <td>An enumeration of PointSpread. Gets or sets the point spread within a group.
                            <br>
                            Values:<br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td><code>Average</code></td>
                                        <td>0</td>
                                        <td>Indicates that the system will define the points spread.</td>
                                    </tr>
                                    <tr>
                                        <td><code>Most</code></td>
                                        <td>1</td>
                                        <td>Indicates a most spread between the points. This indicates the farther the images in a group will be drawn.</td>
                                    </tr>
                                    <tr>
                                        <td><code>Cluster</code></td>
                                        <td>2</td>
                                        <td>Indicates a most cluster between points.
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                            Usage:<span>PointSpreadInGroup = PointSpread.Cluster;</span>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

#### Pin Members

Represents the location of a point on a map and all data specific to it.

<table class="table table-sm">
  <thead>
    <tr>
      <th>Element</th>
      <th>Definition</th>
      <th>Required</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>Category</code></td>
      <td>
        A string value. Gets or sets the pin's category name.
        <br />
        Usage: <span>Category = "Category1";</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>ID</code></td>
      <td>
        An int value. Gets or sets the unique pin identifier. Use this unique identifier so that when the rendered map is created, the geographic coordinates and pixel coordinates of the pin can be traced back to the original point.
        <br />
        Usage: <span>ID = 1;</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Image</code></td>
      <td>
        A string value. Gets or sets the name of the image to be displayed at the supplied coordinates.
        <br />
        Usage: <span>Image = "ltruck_bl";</span>
        <br />
        Here is a list of available icons. For each icon, it supports multiple colors. For example, bldg_r for red warehouse icon, bldg_g for green, bldg_y for yellow and so on. Note PointDrawerWeb - 15 must be provided in <code>DrawerType</code> Enum to display icons on map.
        <br />
        <img src="/soap-apis/img/available-icons.png" alt="icons" loading="lazy" />
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Label</code></td>
      <td>
        A string value. Gets or sets the text to draw next to the point on the map.
        <br />
        Usage: <span>Label = "Stop1Label";</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Point</code></td>
      <td>
        A coordinates system object. Gets or sets the geographic coordinates of the point.
        <br />
        Usage:<br />
        <span>Center = new Coordinates()</span><br />
        <span>{</span><br />
        <span>&nbsp;&nbsp;Lat = "40.388144",</span><br />
        <span>&nbsp;&nbsp;Lon = "-74.655566"</span><br />
        <span>}</span><br />
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

#### PinCategory Members

Represents a category for grouping points on a map.

<table class="table table-sm">
                <thead>
                    <tr>
                        <th>Element</th>
                        <th>Definition</th>
                        <th>Required</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><code>ImageName</code></td>
                        <td>A string value. A string value. Gets or sets the image names to use when more than one pin or points in the same category are clustered.
                            <br>
                            Usage: <span>ImageName = "ClusteredImage";</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>ImageNameForIndividual</code></td>
                        <td>A string value. Gets or sets the name of the image to use when there is only one pin or point in a group.
                            <br>
                            Usage: <span>ImageNameForIndividual = "soloImage";</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Name</code></td>
                        <td>A string value. Gets or sets the name of the image to use when there is only one pin or point in a group. Gets or sets a unique name that can be used to identify each group.
                            <br>
                            Usage: <span>Name = "groupName";</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>PinType</code></td>
                        <td>An enumeration of PinType. Gets or sets the type of pin to draw. Use PDW_BMP when using an image.
                            <br>
                            Values:<br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td><code>PDW_BMP</code></td>
                                        <td>0</td>
                                        <td>Indicates that the pin should be an image.</td>
                                    </tr>
                                    <tr>
                                        <td><code>PDW_CIRCLE</code></td>
                                        <td>1</td>
                                        <td>Indicates that the pin should be drawn as a circle.</td>
                                    </tr>
                                    <tr>
                                        <td><code>PDW_SQUARE</code></td>
                                        <td>2</td>
                                        <td>Indicates that the pin should be drawn as a square.
                                        </td>
                                    </tr>
                                    <tr>
                                        <td><code>PDW_DIAMOND</code></td>
                                        <td>3</td>
                                        <td>Indicates that the pin should be drawn as a diamond.
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                            Usage:<span>PinType=PinType.PDW_CIRCLE;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Style</code></td>
                        <td>An <a href="#ALKStyle">ALKStyle</a> object. Gets or sets the style for the pin category.
                            <br>
                            Usage:<span>Style = new ALKStyle()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;Brush = new ALKBrush()</span><br>
                            <span>&nbsp;&nbsp;{</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;Color = new RGB()</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;{</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Blue = 222</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;}</span><br>
                            <span>&nbsp;&nbsp;},</span><br>
                            <span>&nbsp;&nbsp;Font = new ALKFont()</span><br>
                            <span>&nbsp;&nbsp;{</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;Color = new RGB()</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;{</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Blue = 130</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;BlueSpecified = true</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;},</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;Height = 100,</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;HeightSpecified = true,</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;Weight = 250</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;WeightSpecified = true</span><br>
                            <span>&nbsp;&nbsp;},</span><br>
                            <span>}</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>ZOrder</code></td>
                        <td>An integer value. Gets or sets the stack order of a group. When more than one pin category exists, this value controls the z-order where a higher value will appear on top of a lower value.
                            <br>
                            Usage: <span>Zorder = 1;</span>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

#### ALKStyle Members

Represents the style for a PinCategory.

<table class="table table-sm">
                <thead>
                    <tr>
                        <th>Element</th>
                        <th>Definition</th>
                        <th>Required</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><code>Brush</code></td>
                        <td>An <a href="#ALKBrush">ALKBrush</a> system object. Gets or sets the brush used for filling in the rectangles for the pin category when no image is used.
                            <br>
                            Usage:<span>Brush = new ALKBrush()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;Color = new RGB()</span><br>
                            <span>&nbsp;&nbsp;{</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;Blue = 222</span><br>
                            <span>&nbsp;&nbsp;};</span><br>
                            <span>}</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Font</code></td>
                        <td>
                            An <a href="#ALKFont">ALKFont</a> system object. Gets or sets the font
                            <br>
                            Usage:<br>
                            <span>Font = new ALKFont()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;Color = new RGB()</span><br>
                            <span>&nbsp;&nbsp;{</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;Blue = 130</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;BlueSpecified = true</span><br>
                            <span>&nbsp;&nbsp;},</span><br>
                            <span>&nbsp;&nbsp;Height = 100,</span><br>
                            <span>&nbsp;&nbsp;HeightSpecified = true,</span><br>
                            <span>&nbsp;&nbsp;Weight = 250,</span><br>
                            <span>&nbsp;&nbsp;WeightSpecified = true</span><br>
                            <span>};</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>GroupImageName</code></td>
                        <td>A string value. Gets or sets image name to use for the group icon.
                            <br>
                            Usage: <span>GroupImageName = "groupImage";</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Brush</code></td>
                        <td>
                            An <a href="#ALKShadow">ALKShadow</a> system object. Gets or sets the image shadow of the pin category.
                            <br>
                            Usage:<br>
                            <span>ImageShadow = new ALKShadow()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;Color = new RGB()</span><br>
                            <span>&nbsp;&nbsp;{</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;Blue = 100</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;BlueSpecified = true</span><br>
                            <span>&nbsp;&nbsp;},</span><br>
                            <span>&nbsp;&nbsp;OffsetX = 100,</span><br>
                            <span>&nbsp;&nbsp;OffsetXSpecified = true,</span><br>
                            <span>&nbsp;&nbsp;OffsetY = 127,</span><br>
                            <span>&nbsp;&nbsp;OffsetYSpecified = true</span><br>
                            <span>&nbsp;&nbsp;Opacity = 10,</span><br>
                            <span>&nbsp;&nbsp;OpacitySpecified = true</span><br>
                            <span>};</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>IndividualImageName</code></td>
                        <td>A string value. Gets or sets name of the image name to use for the pin category icon.
                            <br>
                            Usage: <span>IndividualImageName = "soloImage";</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Pen</code></td>
                        <td>
                            Gets or sets the pen used for drawing the borders of rectangles for the pin category when no image is used.
                            <br>
                            Usage:<br>
                            <span>Pen = new ALKPen()</span><br>
                            <span>{</span><br>
                            <span>&nbsp;&nbsp;Color = new RGB()</span><br>
                            <span>&nbsp;&nbsp;{</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;Red = 100</span><br>
                            <span>&nbsp;&nbsp;&nbsp;&nbsp;RedSpecified = true</span><br>
                            <span>&nbsp;&nbsp;},</span><br>
                            <span>&nbsp;&nbsp;Widths = 50,</span><br>
                            <span>&nbsp;&nbsp;WidthsSpecified = true,</span><br>
                            <span>&nbsp;&nbsp;Widths1 = 100,</span><br>
                            <span>&nbsp;&nbsp;Widths1Specified = true,</span><br>
                            <span>&nbsp;&nbsp;Widths2 = 150,</span><br>
                            <span>&nbsp;&nbsp;Widths2Specified = true,</span><br>
                            <span>&nbsp;&nbsp;Widths3 = 200,</span><br>
                            <span>&nbsp;&nbsp;Widths3Specified = true,</span><br>
                            <span>};</span><br>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

#### ALKBrush Members

Represents a painting brush that controls color and opacity to fill in rectangles used as part of an ALKStyle for pin categories.

<table class="table table-sm">
  <thead>
    <tr>
      <th>Element</th>
      <th>Definition</th>
      <th>Required</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>Color</code></td>
      <td>
        A list &lt;&gt; of <a href="#RGB">RGB</a> system object. Gets or sets the brush color.
        <br>
        Usage:<br>
        <span>Color = new RGB()</span><br>
        <span>{</span><br>
        <span>&nbsp;&nbsp;Red = 100,</span><br>
        <span>&nbsp;&nbsp;RedSpecified = true</span><br>
        <span>};</span><br>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Opacity</code></td>
      <td>A ushort value. Gets or sets the opacity of the brush ranging from 0(transparent) to 255(opaque).
        <br>
        Usage:<span>Opacity = 10;</span>
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

#### ALKFont Members

Represents a font and its associated properties such as height, weight and color as used within ALKStyle.

<table class="table table-sm">
  <thead>
    <tr>
      <th>Element</th>
      <th>Definition</th>
      <th>Required</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>Color</code></td>
      <td>
        A list &lt;&gt; of <a href="#RGB">RGB</a> system object. Gets or sets
        the font color.
        <br />
        Usage:<br />
        <span>Color = new RGB()</span><br />
        <span>{</span><br />
        <span>&nbsp;&nbsp;Red = 100,</span><br />
        <span>&nbsp;&nbsp;RedSpecified = true</span><br />
        <span>};</span><br />
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Height</code></td>
      <td>
        A byte value. Gets or sets the font height ranging from 0 to 255.
        <br />
        Usage:<span>Height = 100;</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Weight</code></td>
      <td>
        A byte value. Gets or sets the font weight ranging from 0 to 255.
        <br />
        Usage:<span>Weight = 250;</span>
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

#### ALKShadow Members

Represents an image shadow that is part of the ALKStyle for a pin category.

<table class="table table-sm">
  <thead>
    <tr>
      <th>Element</th>
      <th>Definition</th>
      <th>Required</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>Color</code></td>
      <td>
        A list &lt;&gt; of <a href="#RGB">RGB</a> system object. Gets or sets
        the font color.
        <br />
        Usage:<br />
        <span>Color = new RGB()</span><br />
        <span>{</span><br />
        <span>&nbsp;&nbsp;Red = 100,</span><br />
        <span>&nbsp;&nbsp;RedSpecified = true</span><br />
        <span>};</span><br />
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>OffsetX</code></td>
      <td>
        A sbyte value. Gets or sets horizontal offset of the shadow ranging from
        -128 to 127.
        <br />
        Usage:<span>OffsetX = 100;</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>OffsetY</code></td>
      <td>
        A sbyte value. Gets or sets vertical offset of the shadow ranging from
        -128 to 127.
        <br />
        Usage:<span>OffsetY = 127;</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Opacity</code></td>
      <td>
        A byte value. Gets or sets the shadow opacity ranging from
        0(transparent) to 255(opaque).
        <br />
        Usage:<span>Opacity = 100;</span>
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

#### Calling ProcessMap

```js
// Specify an origin and destination
StopLocation origin = new StopLocation();
origin.Address = new Address() { StreetAddress = "1000 Herrontown Road", City = "Princeton", State = "NJ", Zip = "08540" };
origin.Region = DataRegion.NA;
origin.RegionSpecified = true;
StopLocation destination = new StopLocation();
destination.Address = new Address() { Zip = "19123" };
destination.Region = DataRegion.NA;
destination.RegionSpecified = true;
StopLocation[] stops = new StopLocation[2];
stops[0] = origin;
stops[1] = destination;

// Specify map settings
MapRequestBody mapArea = new MapRequestBody();
mapArea.Height = 900;
mapArea.Width = 1024;

mapArea.Projection = ProjectionType.Mercator;
mapArea.ProjectionSpecified = true;
TrafficDrawer td = new TrafficDrawer()
{
    DateAndTime = new DateTimeType()
    {
        CalendarDate = "01/13/2015",
        DayOfWeek =  DayOfWeek.Monday,
        DayOfWeekSpecified = true,
        TimeOfDay = "07:00",
        TimeZone =TimeZone.Eastern,
        TimeZoneSpecified = true
    },
    TimeType = TrafficTime.Actual,
    TimeTypeSpecified = true,
    Type = TrafficType.RoadSpeed,
    TypeSpecified = true
};
mapArea.TrafficDrawer = td;

Legend[] legend = new Legend[1];
legend[0] = new Legend()
{
    DrawOnMap = true,
    Type = LegendType.RouteLegend,
    TypeSpecified = true
};
mapArea.LegendDrawer = legend;

mapArea.Viewport = new MapViewport()
{
    Region = MapRegion.NA,
    RegionSpecified = true,
    ZoomRadius = 15,
    ZoomRadiusSpecified = true,

    ScreenCenter = new Point()
    {
        X = 3,
        Y = 2
    },
    Center = new Coordinates()
    {
        Lat = "40.194214",
        Lon = "-74.882612"
    }
};
MapRoute route = new MapRoute();   // Set the route
route.Stops = stops;
// Create the authentication and authorization header
AuthHeader soapHeader = this.Caller.GenerateAuthHeader(APIName);
// Create the service client
BasicHttpBinding binding = new BasicHttpBinding();
binding.MaxBufferPoolSize = Int32.MaxValue;
binding.MaxReceivedMessageSize = Int32.MaxValue;
apRoutesRequest request = new MapRoutesRequest();  // Create the request
request.Header = new RequestHeader() { DataVersion =  DataVersion.ToString(), RequestType = "ProcessMap" };
request.Body = new MapRoutesRequestBody() { Map = mapArea, Routes = new MapRoute[1] { route } };

// Call API
MapRoutesResponse response = service.ProcessMap(soapHeader, request);
```

### Request

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">https://pcmiler.alk.com/APIs/v1.0/IService/ProcessMap</Action>
    <h:AuthHeader xmlns="http://www.alk.com" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:h="http://www.alk.com">
      <Authorization>A77097D2D202A743BB1660E15794D7CA</Authorization>
      <Date>Thu, 21 Aug 2014 16:23:26 GMT</Date>
    </h:AuthHeader>
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
       <ProcessMap xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <Request>
        <Header>
          <DataVersion>current</DataVersion>
          <RequestType>MapRoute</RequestType>
        </Header>
        <Body>
          <Map>
            <Viewport>
              <Center>
                <Lat>32.859577</Lat>
                <Lon>-115.606428</Lon>
              </Center>
              <ScreenCenter>
                <X>594</X>
                <Y>594</Y>
              </ScreenCenter>
              <ZoomRadius>650</ZoomRadius>
              <CornerA xsi:nil="true" />
              <CornerB xsi:nil="true" />
              <Region>NA</Region>
            </Viewport>
            <Projection>FixedLat</Projection>
            <Style>Default</Style>
            <Width>1094</Width>
            <Height>1094</Height>
            <Drawers xsi:nil="true" />
            <LegendDrawer>
              <Legend>
                <Type>ScaleOfMiles</Type>
                <DrawOnMap>true</DrawOnMap>
              </Legend>
            </LegendDrawer>
            <GeometryDrawer>
              <Geometry xsi:type="RegionGeometry">
                <Color>
                  <Red>200</Red>
                </Color>
                <Name>NA</Name>
              </Geometry>
              <Geometry xsi:type="ShapeGeometry">
                <Color>
                  <Green>200</Green>
                </Color>
                <Type>Circle</Type>
                <Coordinates>34066401,-118466694</Coordinates>
                <Fill>false</Fill>
                <RadiusHorizontal>100</RadiusHorizontal>
              </Geometry>
            </GeometryDrawer>
            <PinDrawer>
              <PointGroupDensity>Average</PointGroupDensity>
              <PointSpreadInGroup>Average</PointSpreadInGroup>
              <DrawOnMap>true</DrawOnMap>
              <Pins>
                <Pin>
                  <ID>1</ID>
                  <Point>
                    <Lat>34.420831</Lat>
                    <Lon>-119.698190</Lon>
                  </Point>
                  <Image>ltruck_g</Image>
                  <Category xsi:nil="true" />
                  <Label>point1</Label>
                </Pin>
                <Pin>
                  <ID>0</ID>
                  <Point>
                    <Lat>33.448377</Lat>
                    <Lon>-112.074037</Lon>
                  </Point>
                  <Image>ltruck_r</Image>
                  <Category xsi:nil="true" />
                  <Label>point2</Label>
                </Pin>
              </Pins>
            </PinDrawer>
            <PinCategories xsi:nil="true" />
            <TrafficDrawer xsi:nil="true" />
            <MapLayering>MapAndPointsTwoLayers</MapLayering>
          </Map>
          <Routes>
            <MapRoute>
              <RouteId xsi:nil="true" />
              <Stops>
                <StopLocation>
                  <Address>
                    <StreetAddress xsi:nil="true" />
                    <City xsi:nil="true" />
                    <State xsi:nil="true" />
                    <Zip>93101</Zip>
                    <County xsi:nil="true" />
                    <Country xsi:nil="true" />
                    <SPLC xsi:nil="true" />
                    <CountryPostalFilter>US</CountryPostalFilter>
                  </Address>
                  <Coords xsi:nil="true" />
                  <Region>NA</Region>
                  <Label>Santa Barbara</Label>
                  <PlaceName xsi:nil="true" />
                  <Costs xsi:nil="true" />
                </StopLocation>
                <StopLocation>
                  <Address>
                    <StreetAddress xsi:nil="true" />
                    <City>Las Vegas</City>
                    <State>NV</State>
                    <Zip xsi:nil="true" />
                    <County xsi:nil="true" />
                    <Country xsi:nil="true" />
                    <SPLC xsi:nil="true" />
                    <CountryPostalFilter>US</CountryPostalFilter>
                  </Address>
                  <Coords xsi:nil="true" />
                  <Region>NA</Region>
                  <Label>Las Vegas</Label>
                  <PlaceName xsi:nil="true" />
                  <Costs xsi:nil="true" />
                </StopLocation>
                <StopLocation>
                  <Address>
                    <StreetAddress xsi:nil="true" />
                    <City>Phoenix</City>
                    <State xsi:nil="true" />
                    <Zip>85003</Zip>
                    <County xsi:nil="true" />
                    <Country xsi:nil="true" />
                    <SPLC xsi:nil="true" />
                    <CountryPostalFilter>US</CountryPostalFilter>
                  </Address>
                  <Coords xsi:nil="true" />
                  <Region>NA</Region>
                  <Label>Phoenix</Label>
                  <PlaceName xsi:nil="true" />
                  <Costs xsi:nil="true" />
                </StopLocation>
              </Stops>
              <Options>
                <BordersOpen>false</BordersOpen>
                <DistanceUnits>Miles</DistanceUnits>
                <TruckCfg xsi:nil="true" />
              </Options>
              <FuelOptions xsi:nil="true" />
              <AFOptions xsi:nil="true" />
              <RouteLegOptions xsi:nil="true" />
              <StopLabelDrawer>Name</StopLabelDrawer>
            </MapRoute>
          </Routes>
        </Body>
      </Request>
    </ProcessMap>
 </s:Body>
</s:Envelope>
```

### Response

Represents the output response to a request for generating a map.

#### MapRoutesResponseBody Members

Represents the request body of a MapRouteResponse encapsulating the rendered map and associated information.

| Element | Definition                                                   |
| ------- | ------------------------------------------------------------ |
| `Map`   | A RenderedMaps system object. Gets or sets the rendered map. |

#### RenderedMap Members

Represents a rendered map and all associated information.

| Element   | Definition                                                                                                                                                                                                              |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Center`  | A coordinates system object. Gets or sets the center of the map as the geographic coordinates.                                                                                                                          |
| `CornerA` | A coordinates system object. Gets or sets the upper left geographic coordinates of the map.                                                                                                                             |
| `CornerB` | A coordinates system object. Gets or sets the lower right geographic coordinates of the map.                                                                                                                            |
| `Groups`  | A list <> of MapGroupInfo system object. Gets or sets the collection of groups that points have been clustered in. In MapSettings if no PinCategory was supplied for the PinCategories, then no group will be returned. |
| `Height`  | A integer value. Gets or sets the image height of the map in pixels.                                                                                                                                                    |
| `Layer`   | A list<> of Layer system object. Gets or sets the layers of the map where each layer contains the byte buffer or base 64 hex string of the image.                                                                       |
| `Points`  | Gets or sets the collection of points along with their associated information.                                                                                                                                          |
| `Region`  | An enumeration of MapRegion. Gets or sets the region of the map.                                                                                                                                                        |
| `Width`   | An integer value. Gets or sets the image width of the map in pixels.                                                                                                                                                    |

#### Layer Members

Represents a single layer of a RenderedMap; this can contain the map image, the points or one of the legends.

| Element  | Definition                                                                                                    |
| -------- | ------------------------------------------------------------------------------------------------------------- |
| `Buffer` | A byte value. Gets or sets the byte array representing the bytes that make up the image.                      |
| `Image`  | A string value. Gets or sets the base64 encoded string of the bytes that make up the image.                   |
| `Size`   | An integer value. Gets or sets the size of the buffer byte array or the base64 encoded image string.          |
| `Type`   | A LayerType enumeration. Gets or sets the type of the layer, i.e. whether it is a map, legend or point layer. |

#### LayerType Enumeration

| Member name     | Value | Description                                                                                      |
| --------------- | ----- | ------------------------------------------------------------------------------------------------ |
| `BaseMap`       | 0     | Indicates the image layer is the base map.                                                       |
| `ScaleOfMiles`  | 1     | Indicates that the image layer is the scale of miles (or kms) legend.                            |
| `RouteLegend`   | 2     | Indicates that the image layer is the route legend.                                              |
| `RoadLegend`    | 3     | Indicates that the image layer is the road class legend.                                         |
| `HazMatLegend`  | 4     | Indicates that the image layer is the hazardous material restriction legend.                     |
| `TrafficLegend` | 5     | Indicates that the image layer is the traffic congestion legend.                                 |
| `PointMap`      | 6     | Indicates that the image layer contains only the points that would be overlayed on the base map. |

#### MapRegion Enumeration

| Member name  | Value | Description                             |
| ------------ | ----- | --------------------------------------- |
| `NA`         | 0     | Indicates the North American continent. |
| `Bermuda`    | 1     | Indicates Bermuda                       |
| `Canada`     | 2     | Indicates Canada                        |
| `Mexico`     | 3     | Indicates Mexico                        |
| `PuertoRico` | 4     | Indicates Puerto Rico.                  |
| `US`         | 5     | Indicates the United States             |
| `EU`         | 6     | Indicates Europe.                       |
| `OC`         | 7     | Indicates Oceania.                      |
| `ME`         | 8     | Indicates the Middle East               |
| `AF`         | 9     | Indicates Africa.                       |
| `SA`         | 10    | Indicates South America                 |
| `AS`         | 11    | Indicates Asia.                         |

#### Sample Response

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <ProcessMapResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <ProcessMapResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>MapRoute</Type>
          <Success>true</Success>
          <DataVersion>28.3.26.9224</DataVersion>
          <Errors />
        </Header>
        <Body>
          <Map>
            <Center>
              <Lat>32.86137</Lat>
              <Lon>-115.605258</Lon>
            </Center>
            <CornerA>
              <Lat>44.067835</Lat>
              <Lon>-126.812361</Lon>
            </CornerA>
            <CornerB>
              <Lat>21.654906</Lat>
              <Lon>-104.398156</Lon>
            </CornerB>
            <Groups i:nil="true" />
            <Height>1094</Height>
            <Layers>
              <Layer>
                <Buffer>iVBORw0KGgoAAAANSUhEUgAABEYAAARGCAYAAAA1uLUVAAAgAElEQVR4nOy9eXhb5Zn//TlH0tFiS95jO46z2Fkc2yUkGEhCCQlhJwyQQqZsfVOWlsK0tC+/KZSB6bTT6TBlOi+lQ6F0mZSWTn+ZNi0DCVtDNrIAAROSmCzY2UjsxHYcW7LWo3PeP+QjS7JkS7ZsSbY+15Ur1lkfSUfnPM/3ue/vLbzT0qOSJQugW3U5F/72S7x/14tMe/t3STlmLiVJOU4sfF5f8O9/+t4P+OY3v0VVVVVwWUtLCz/5/vf4/gXzADDO1OE7//P4pCnBbYx6Gb3jAHp7U2BBwTwoWgiCrv88Pjc+nyfudjloD/4d7TMIXZ8JPHTPE6xdu5ZVq1YF/3/+uZ9idu5B6j2It2gJsqlyTNs0Gp/hcT/XTmK6iIS/eebbJlCXSl+yR1tYgxSNLshprqt5EFomdQdLfb8pTVR09wg+/fg8A8xYu4ryL0tfHKCgqIr+oiP/4v9+jrTUIQFNDA2MmTMTj8fL4rx9mzvkL+L//8XO8Ph9Olyvt+HPOPY9YNEbV0SPs2bUzcb7dO3YQi0b51+98K3HO6mPHmDFnzoBdK3R0rDl06AgLF57PyJFFGcf29HteW3uK4uLM+58pTpciq9nOQ/eMg8JLcdVtRu9jC1+15yFCCCGEEEKIdPz++LfHkUi4h5GDz1S9GP5p8ZvlbswuiiX+E303EBk5diHP5Do12YrmzkvUl8mpeoKcqif6NAfLssgvLKKpoQE9FmPM+AmsfGY9Fy25Coi3mDWNrrVuXvnzevbs3MkP7/8lK59ZD4BpGBSOHMm//OrXzF+4kG1vvM4/3fNlQq2tGcerqsq8hYvYvWMHu3fs4NyLLo4XXzUM8vLzWfnM+sR/V12/PKu6O70xffrU9hbFFm+++U7aMdkWXH3rrW2JQMuZ6nQIikSjYVpaGno1Dzs4qIUr+3ROCYwIIYQQQgjRD3bWyOnAUjT0QPdLAnp7Qy9BlO4lPz/Jz1M2z3N/C3lGc+fRNubWRMFWO0DSm5tD09QpnzWbgqIi1jz0Sxrq6qg7eZITx+LHGFlaSiwaZe+unRzevz+xPRaL4nTFr/HV5/6cON6Wl17gv37wT8w5fwE33nY7TQ0NNDU2ZBxvWSYXXHop2996k7bWIFNnVGCaBhVz59LU0MCWl14g2NLMe1vf6NQdZ6CUl09l2bLPUFRUwMIL5qUdk+3rZJomRUWFBIOtAzrHoXI6BEWgo65JIJDfq3nYgcK+BEccd977f37Y672EEEIIIYQ4y5TkdO0uA+ByuWkNBhPZI8PF1bwdrWU30cJLsBQnJTkmNW2OtGNr2hwZH0tlX3e2488Ws4tind4Tqe+PkhyTD085M75vIH7DnTdiYDqcxHJnE8udjYKBs3EbzpadWK58TC2v2/1M08TpcjN/4YVsf+tNnl7zGK9ueI6xEyfxt3f+PaPGjqWlqYk//u4xDn2ylxEFheQXFHLF0qV88O47PPvUkxQWF1NTdZyy8nIWLb6CQ5/s4/FfP8y2N97gms9+jvmLLmTUmDFpx4+bNJmRpaP5w2OruXDxFcyYM5totI3C4lHkFxbylz/8nr/84fe0NDVxzrx5uNyuAQ+OAIwfP5bWYJDWYBCn00k4HKKhvp7WYJDaUw3s3LmbmpqTnDxZi9vtJiena/Hb8vKpjBs3BrfbleYMp7fTJShiz8Xr9fV6P8Ndmnj/Z/PeT6a8frBZmpYLIYQQQgjRg9lFsYw1JOzCjMNRa8QOiEDXYpwDsdyjt1kQZ7vU90d3dUdqTlQP2numI1DWcw2SeCtdLw5H59dX16NYlonT2bW4cLx1b9fWrfE2vo5O43Q9jKo629vxdhaLRdA0Z6ItbywWJhaL4HBouFw5nc5hGDGi0RCWNXi3sMFgC63BeA0Ur9dLbt6ItMtjli+/dtDmMJRyqp6gJjd+LYMdFFFVFUVRMU0j42toB2gCgb4HDO33frj0xqy7N0nxVSGEEEIIIbKU6Qa3ZFRpIjgylHpz8yuGRnLwqLtlSNnWreirRJvfus24gJu/vyXtuFWrfoVlWUQibSiKgqo6sCwLyzITN6+6Hk1stwMVhqEnbnQty0wENgxDR1GUxL87jhPNOF7XI4nj29kghqETCjWjqg4URen2Znog2ZlfrcEguXkjALjkkkUcOnSUSCRCNBrF43EP+jyGUiCQn3jt00l+XfrK4dBwu33txzMJhdK//+2slf6w3/tacE/i555IYEQIIYQQQogs9dR1JBIJD0nr3u6yRJLZWS790ZdOKyKuuza+rcEgVa0OsutH0zfJHWxgC2vXru30+IoVKzr927KstK1wM203TROwlwqZncZbVtcb6e7GZ2rBOxjLZtKpra1j69a3gXg2SPLSuIKCfAoKBmbJ0+kk/r6I83j8iWBVOpFIG4bR988BVdU4fuQwG9ev49Z77k0EyFL1J1MkWW+7dElgRAghhBBCiCx1FyAYita9qhnCU/000H1AJJk95/4ESGQJTf8kP39v7a1p/ymedbDtRH3isS9cVDAo50/+1twOhqQGSc52b70V70hTVFQ4zDMZOlrLbvRARSLD58mHHqC2umvm2w133Mmo8ePaM306sndSM4BSs3qSs31SqaoD07Q6Hcfe3+HQElkq6bKPsjqvI4CROzPR0trwjk+TxZT0XAzIMyqEEEIIIcRZoLvsCb8/QGswOKhZI1pwD3qgIuv08GQDkT0i+s4OiNjBjw9POXlrb023wZDuMk4GihauPOuXYb388iZMM36jXFY2aZhnM3Qsd1F8KV7uPCzL5OavfA2AAx/v5oM3t3LjnX/fMdaycDrtJUQWuh5D07oWmY3FIpimjsvlTcpAsTBSWj673TlAvCuSqmrt5zAxDD1xXMPQcTgcgJI4Tqbz6noUw4h1Pm/JpaC5ccVqoGBm4jiWZRKNhjplKUlgRAghhBBCiCz1dIM6mFkjyQUF+2ogskdE73RkiMDC6SVAR2vft/Zmdww7INfXQElyPZPUTBFX3WbUQAW6vzzrQpWfNldeuZh16/7C9OlTGDVq5HBPZ0i4mrejRE4RLbwUgHA4iKo6ugQdotEQLpeXA7s/YvNfnsPQY8xasJCFS67k+JHDvPHC85imQX1tLWUVM7nqhs+iON3s/2hXl/EARkznhd//Pw7u+ZjSceNZdtvtHDtykC0bnuPmr3wNh8PJa8+tx+ +/mgze3cuOdf584bsyEse3fYOsmNIYN6EX2uV1U8kRlJX9avYovfe/7zB6VmmKtMf/i+LeLPpfK5IKO+dpcDoX5Y7w4U7afbDXIdXcEUXQTDjdEOdXaNWr0+vMbuPVr03A4+ +z43K5At9dLheOiPBOjKhlubnD+eMf/4TJZCIyMrJV5/S/qR+LFn/A6jVrGTp0CHv27GXo0JtZu3YdK1as4lcvPEdqajdefPFlKisqCQsNw6xeuaqRel7d1exkrAAWi4UpUybTs2cGANnZmRw/XkZCwuAGfRcR4Wh3LI2maiY98nMcUTE4K86yaskCHFHRZPS/mTUfv0tqZj9G3vMQ506XsW7pQsIjo6g77yQyOg6z1capkkMAhEV0AaCmqgKv24XF5i9zKSnagyMqul3B1sdVr67GGbT9dOkR1v7tfWKTUolPzQgcd6xoD4Xb8rlj2pOYzGaWL5pHbFIqUfFJ7NiwgrEPPIYjKobli+ZRtGMzWYNzA+dqXk+T952UntWu+2iJPTKKIePubff5m1csZdTkGY0mRtbnLcLu6MLE6U9jC7NztuwoW1Yu5eZx9wY9s4sd3rMdW5idI4UFgcRIa+g+jbX/8z6Jab2CkiIAd818Bl3XKdyaT3FhAXfOfAYAs8Xahju9Nlxuf9Vr6ncal5LOxq8+ZvSUmTiiYvj6r/OJiksiNbMfn7/7JkCj/6eOFe3h2IE9KKoUhgkhhBBCCHGp3tmZOKur2bp1G8nJSezcuZt/nDmjs8NqVmxMLF6vl1tzR7T6nLTu3XniiVksXbqMhQsXk9mrF9m9ezNq1Ej27dvPz37+SywWC1On3k9SUhIAmq50SHLEMC60oep16Goo4B9SoxnuJidjrVdZWcmLL77ECy88R3JyEoWFBxgzZhTZ2VlUVzuD+m7mzOntjrPRxIjJbMFssRIVl0RcShrnTpUR5ijCXVfD4NF3oZrMJKVn0Tsnl7rzTlRVZevqPCrPnGTnxtX0veW2QFtJPbIoPbg38EJ9dN9OUnr24WzZ0TYHWx9XU9uT0rOwOyI5d7os6CXfFmrn5nGTA5UI4ZFdOV9VQUxydxRVxWQyY7FYUVUVs8UW1PaJ4qbvG+BAwXfs3rQGn08LVNeUHixk66o8IqPjOFN2lMS0Xoy852HW/u19rC </Buffer>
                <Image i:nil="true" />
                <Size>426750</Size>
                <Type>BaseMap</Type>
              </Layer>
            </Layers>
            <Points>
              <MapPointInfo>
                <ClassName>ltruck_r</ClassName>
                <DevX>-112074037</DevX>
                <DevY>33448377</DevY>
                <GroupID>-1</GroupID>
                <ID>0</ID>
                <Latitude>33448377</Latitude>
                <Longitude>-112074037</Longitude>
              </MapPointInfo>
              <MapPointInfo>
                <ClassName>ltruck_g</ClassName>
                <DevX>-119698190</DevX>
                <DevY>34420831</DevY>
                <GroupID>-1</GroupID>
                <ID>1</ID>
                <Latitude>34420831</Latitude>
                <Longitude>-119698190</Longitude>
              </MapPointInfo>
            </Points>
            <Region>NA</Region>
            <Width>1094</Width>
          </Map>
        </Body>
      </ProcessMapResult>
    </ProcessMapResponse>
  </s:Body>
</s:Envelope>
```
