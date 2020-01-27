---
title: Get POIs Along Route
weight: 8
hideToc: true
---

The getPoisAlongRoute operation allows the user to search for point of interest, including fuel stops, along a route. It's required that at least one of the stops on the route must be within US borders.

**Schema**

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:alk="http://www.alk.com" xmlns:v1="https://pcmiler.alk.com/APIs/v1.0" xmlns:arr="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
  <soapenv:Header>
    <alk:AuthHeader>
      <alk:Authorization>YOUR API KEY HERE</alk:Authorization>
      <alk:Date>Tue, 25 Aug 02015 22:57:03 GMT</alk:Date>
    </alk:AuthHeader>
  </soapenv:Header>
  <soapenv:Body>
    <v1:GetPoisAlongRoute>
      <!--Optional:-->
      <v1:Request>
        <!--Optional:-->
        <v1:Header>
          <!--Optional:-->
          <v1:DataVersion/>
          <!--Optional:-->
          <v1:RequestType/>
        </v1:Header>
        <!--Optional:-->
        <v1:Body>
          <!--Optional:-->
          <v1:PoiRoute>
            <!--Optional:-->
            <v1:RouteId>PrincetonToMiami</v1:RouteId>
            <!--Optional:-->
            <v1:Stops>
              <!--Zero or more repetitions:-->
              <v1:StopLocation>
                <!--Optional:-->
                <v1:Address>
                  <!--Optional:-->
                  <v1:StreetAddress/>
                  <!--Optional:-->
                  <v1:City/>
                  <!--Optional:-->
                  <v1:State/>
                  <!--Optional:-->
                  <v1:Zip>08540</v1:Zip>
                  <!--Optional:-->
                  <v1:County/>
                  <!--Optional:-->
                  <v1:Country/>
                  <!--Optional:-->
                  <v1:SPLC/>
                  <!--Optional:-->
                  <!--<v1:CountryPostalFilter></v1:CountryPostalFilter>-->
                  <!--Optional:-->
                  <!--<v1:AbbreviationFormat></v1:AbbreviationFormat>-->
                </v1:Address>
                <!--Optional:-->
                <!--<v1:Coords>-->
                <!--Optional:-->
                <!--<v1:Lat></v1:Lat>-->
                <!--Optional:-->
                <!--<v1:Lon></v1:Lon>-->
                <!--</v1:Coords>-->
                <!--Optional:-->
                <v1:Region>NA</v1:Region>
                <!--Optional:-->
                <v1:Label/>
                <!--Optional:-->
                <v1:PlaceName/>
                <!--Optional:-->
              </v1:StopLocation>
              <v1:StopLocation>
                <!--Optional:-->
                <v1:Address>
                  <!--Optional:-->
                  <v1:StreetAddress/>
                  <!--Optional:-->
                  <v1:City>Charleston</v1:City>
                  <!--Optional:-->
                  <v1:State>SC</v1:State>
                  <!--Optional:-->
                  <v1:Zip/>
                  <!--Optional:-->
                  <v1:County/>
                  <!--Optional:-->
                  <v1:Country/>
                  <!--Optional:-->
                  <v1:SPLC/>
                  <!--Optional:-->
                  <!--<v1:CountryPostalFilter></v1:CountryPostalFilter>-->
                  <!--Optional:-->
                  <!--<v1:AbbreviationFormat></v1:AbbreviationFormat>-->
                </v1:Address>
                <!--Optional:-->
                <!--<v1:Coords>-->
                <!--Optional:-->
                <!--<v1:Lat></v1:Lat>-->
                <!--Optional:-->
                <!--<v1:Lon></v1:Lon>-->
                <!--</v1:Coords>-->
                <!--Optional:-->
                <v1:Region>NA</v1:Region>
                <!--Optional:-->
                <v1:Label/>
                <!--Optional:-->
                <v1:PlaceName/>
                <!--Optional:-->
              </v1:StopLocation>
              <v1:StopLocation>
                <!--Optional:-->
                <v1:Address>
                  <!--Optional:-->
                  <v1:StreetAddress/>
                  <!--Optional:-->
                  <v1:City>Miami</v1:City>
                  <!--Optional:-->
                  <v1:State>FL</v1:State>
                  <!--Optional:-->
                  <v1:Zip/>
                  <!--Optional:-->
                  <v1:County/>
                  <!--Optional:-->
                  <v1:Country/>
                  <!--Optional:-->
                  <v1:SPLC/>
                  <!--Optional:-->
                  <!--<v1:CountryPostalFilter></v1:CountryPostalFilter>-->
                  <!--Optional:-->
                  <!--<v1:AbbreviationFormat></v1:AbbreviationFormat>-->
                </v1:Address>
                <!--Optional:-->
                <!--<v1:Coords>-->
                <!--Optional:-->
                <!--<v1:Lat></v1:Lat>-->
                <!--Optional:-->
                <!--<v1:Lon></v1:Lon>-->
                <!--</v1:Coords>-->
                <!--Optional:-->
                <v1:Region>NA</v1:Region>
                <!--Optional:-->
                <v1:Label/>
                <!--Optional:-->
                <v1:PlaceName/>
                <!--Optional:-->
              </v1:StopLocation>
            </v1:Stops>
            <!--Optional:-->
            <v1:Options>
              <!--Optional:-->
              <v1:HighwayOnly>false</v1:HighwayOnly>
              <!--Optional:-->
            </v1:Options>
          </v1:PoiRoute>
          <!--Optional:-->
          <v1:RouteLegIndex>0</v1:RouteLegIndex>
          <v1:SearchType>HoS</v1:SearchType>
          <!--Optional:-->
          <!--<v1:GenericPOICategories>-->
          <!--Zero or more repetitions:-->
          <!--<v1:POIGenericType>All</v1:POIGenericType>-->
          <!--<v1:POIGenericType>VehicleRepair</v1:POIGenericType>-->
          <!--</v1:GenericPOICategories>-->
          <!--Optional:-->
          <v1:HoSPOICategories>
            <!--Zero or more repetitions:-->
            <v1:POIHosType>All</v1:POIHosType>
          </v1:HoSPOICategories>
          <!--Optional:-->
          <v1:SearchWindowUnits>Minutes</v1:SearchWindowUnits>
          <!--Optional:-->
          <v1:SearchWindowStart>50</v1:SearchWindowStart>
          <!--Optional:-->
          <v1:SearchWindowEnd>150</v1:SearchWindowEnd>
          <!--Optional:-->
          <v1:AirDistanceThreshold>2.0</v1:AirDistanceThreshold>
        </v1:Body>
      </v1:Request>
    </v1:GetPoisAlongRoute>
  </soapenv:Body>
</soapenv:Envelope>
```

#### GetPoisAlongRoute Request

**PoisAlongRouteRequestBody Members**

Represents the request body of a PoisAlongRouteRequest allowing user to control various settings relevant to finding POIs with a given route leg.

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
      <td><code>PoiRoute</code></td>
      <td>
        A <a href="#ExtendedRoute">ExtendedRoute</a> System Object. Indicate the route to search for POIs.
        <br>
        Usage:
        <div class="code">
          <pre class="prettyprint">
ExtendedRoute extRoute = new ExtendedRoute();
extRoute.Stops = new List<​Stop​Location​>();
extRoute.Stops.Add(new StopLocation()
  { Address = new Address() { City = "Philadelphia", State = "PA" } });
extRoute.Stops.Add(new StopLocation()
  { Address = new Address() { Zip = "08540" } });
extRoute.Options = new RouteOptions() { HighwayOnly = false };</pre>
        </div>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>RouteLegIndex</code></td>
      <td>
        An Integer value. Indicate the route leg index to search.
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>SearchType</code></td>
      <td>
        An enumeration of POISearchType. Indicate the type of search to perform. If you choose Generic, fill in the
        array of GenericPOICategories, if you choose HoS, fill the in the array of HosPOICategories.
        For a Fuel search, we just return everything.
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
              <td><code>FuelStop</code></td>
              <td>1</td>
              <td>Represents that search type is fuel stop.</td>
            </tr>
            <tr>
              <td><code>HoS</code></td>
              <td>2</td>
              <td>Represents that search type is HoS.</td>
            </tr>
            <tr>
              <td><code>Generic</code></td>
              <td>4</td>
              <td>Represents that search type is Generic.</td>
            </tr>
          </tbody>
        </table>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>GenericPOICategories</code></td>
      <td>
        List of enumerations of POIGenericType. Indicate the list POI categories for a generic POI search.
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
              <td><code>All</code></td>
              <td>0</td>
              <td>All POI categories</td>
            </tr>
            <tr>
              <td><code>WeightStation</code></td>
              <td>146</td>
              <td>Weight Station category</td>
            </tr>
            <tr>
              <td><code>CatScale</code></td>
              <td>110</td>
              <td>Cat Scale location category</td>
            </tr>
            <tr>
              <td><code>LCVLot</code></td>
              <td>149</td>
              <td>LCV Lot category</td>
            </tr>
            <tr>
              <td><code>Hotel</code></td>
              <td>25</td>
              <td>Hotel category</td>
            </tr>
            <tr>
              <td><code>IntermodalRamp</code></td>
              <td>52</td>
              <td>IntermodalRamp category</td>
            </tr>
            <tr>
              <td><code>Parking</code></td>
              <td>34</td>
              <td>Parking category</td>
            </tr>
            <tr>
              <td><code>RestAreaHoS</code></td>
              <td>1510</td>
              <td>Rest area of HoS category</td>
            </tr>
            <tr>
              <td><code>TruckStop</code></td>
              <td>151</td>
              <td>Truck stop category</td>
            </tr>
            <tr>
              <td><code>TruckServiceHoS</code></td>
              <td>1600</td>
              <td>Truck service of HoS category</td>
            </tr>
            <tr>
              <td><code>HighwayExit</code></td>
              <td>1607</td>
              <td>Highway Exit category</td>
            </tr>
            <tr>
              <td><code>MajorAirport</code></td>
              <td>101</td>
              <td>Major airport category</td>
            </tr>
            <tr>
              <td><code>EventFacility</code></td>
              <td>18</td>
              <td>Event facility category</td>
            </tr>
            <tr>
              <td><code>DistributionCenter</code></td>
              <td>1800</td>
              <td>Distribution category</td>
            </tr>
          </tbody>
        </table>
      </td>
      <td></td>
    </tr>
    <tr>
      <td><code>HoSPOICategories</code></td>
      <td>
        List of enumerations of POIHosType. Indicate the list HoS categories for a HoS POI search.
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
              <td><code>All</code></td>
              <td>0</td>
              <td>All POI Hos type </td>
            </tr>
            <tr>
              <td><code>TruckServiceHoS</code></td>
              <td>1600</td>
              <td>Truck Service HoS type</td>
            </tr>
            <tr>
              <td><code>RestAreaHoS</code></td>
              <td>1510</td>
              <td>Rest Area HoS type</td>
            </tr>
          </tbody>
        </table>
      </td>
      <td></td>
    </tr>
    <tr>
      <td><code>SearchWindowUnits</code></td>
      <td>
        An enumeration of PoiSearchWindowUnits. Indicate the search window units.
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
              <td><code>Miles</code></td>
              <td>0</td>
              <td>Use Miles for Search Windows units</td>
            </tr>
            <tr>
              <td><code>Minutes</code></td>
              <td>1</td>
              <td>Use Minutes for Search Windows units</td>
            </tr>
          </tbody>
        </table>
      </td>
      <td></td>
    </tr>
    <tr>
      <td><code>SearchWindowStart</code></td>
      <td>
        A Double value. Indicate the route leg mileage to begin the search at. For longer routes on generic POI
        searches, the search window will automatically be trimmed to be the maximum allowed length.
      </td>
      <td></td>
    </tr>
    <tr>
      <td><code>SearchWindowEnd</code></td>
      <td>
        A Double value. Indicate the route leg mileage to end the search at. Set to null to automatically select the end
        of the leg or the maximum allowed length, whichever is smaller
      </td>
      <td></td>
    </tr>
    <tr>
      <td><code>AirDistanceThreshold</code></td>
      <td>
        A Double value. The maximum air distance between the POI and the nearest intersection on the route. Default and
        maximum allowed is 2.5 miles.
      </td>
      <td></td>
    </tr>
  </tbody>
</table>

#### ExtendedRoute Members

ExtendedRoute System class inherited from Route class. It has a SharedOption System class member named ExtendedOptions. It contains:

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
      <td><code>EstimatedTimeOptions</code></td>
      <td>
        A EstimatedTimeOptions System object contains:
        <br>
        <code>ETAETD</code>, an enumeration of ETAETDType.
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
              <td><code>Arrival</code></td>
              <td>0</td>
              <td>Indicates the time is an estimated time of arrival.</td>
            </tr>
            <tr>
              <td><code>Depart</code></td>
              <td>1</td>
              <td>Indicates the time is an estimated time of departure.</td>
            </tr>
          </tbody>
        </table>
        <br>
        <code>DateOption</code>, an enumeration of DateOption.
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
              <td><code>Current</code></td>
              <td>0</td>
              <td>Indicates that the current system time should be used.</td>
            </tr>
            <tr>
              <td><code>Specific</code></td>
              <td>1</td>
              <td>Indicates that a specific supplied time should be used.</td>
            </tr>
            <tr>
              <td><code>DayOfWeek</code></td>
              <td>2</td>
              <td>Indicates that a day of the week should be used.</td>
            </tr>
          </tbody>
        </table>
        <br>
        <code>DateAndTime</code>, an Object of <a
          href="/soap-apis/docs/shared-api-members/#DateTime">DateTimeType</a> class.
      </td>
      <td></td>
    </tr>
    <tr>
      <td><code>UseTraffic</code></td>
      <td>
        A Boolean value. Indicate whether or not to use traffic data when calculating transit times, or when using
        fastest routing.
      </td>
      <td></td>
    </tr>
    <tr>
      <td><code>TruckStyle</code></td>
      <td>
        An enumeration of TruckStyle. Indicate the truck style which includes vehicle dimensions and route costs.
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
              <td><code>None</code></td>
              <td>0</td>
              <td>Represents standard style.</td>
            </tr>
            <tr>
              <td><code>TwentyEightDoubleTrailer</code></td>
              <td>1</td>
              <td>Represents 28 Double Trailer style.</td>
            </tr>
            <tr>
              <td><code>FortyStraightTruck</code></td>
              <td>2</td>
              <td>Represents 40 Straight Truck style.</td>
            </tr>
            <tr>
              <td><code>FortyEightSemiTrailer</code></td>
              <td>3</td>
              <td>Represents 48 Semi Trailer style.</td>
            </tr>
            <tr>
              <td><code>FiftyThreeSemiTrailer</code></td>
              <td>4</td>
              <td>Represents 53 Semi Trailer style.</td>
            </tr>
            <tr>
              <td><code>FullSizeVan</code></td>
              <td>5</td>
              <td>Represents Full Size Van style.</td>
            </tr>
          </tbody>
        </table>
      </td>
      <td></td>
    </tr>
  </tbody>
</table>

#### GetPoisAlongRoute Response

PoisAlongRouteResponseBody Members
