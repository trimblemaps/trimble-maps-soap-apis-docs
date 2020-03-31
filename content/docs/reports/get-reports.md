---
title: Get Reports
weight: 2
---

The GetReports operation allows the user to run routes based on location and options, and retrieve routing data and certain types of reports. The types of reports are driven by parameters passed into the API.

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
    <m:GetReports xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
        <m:Body>
          <m:ReportRoutes>
            <m:ReportRoute>
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
                <m:useSites>false</m:useSites>
                <m:HubRouting>true</m:HubRouting>
                <m:OverrideRestrict>true</m:OverrideRestrict>
                <m:RouteOptimization>None</m:RouteOptimization>
                <m:RoutingType>Practical</m:RoutingType>
                <m:TollDiscourage>true</m:TollDiscourage>
                <m:TrailerCfg>
                  <m:TypeOfTrailer>Trailer</m:TypeOfTrailer>
                  <m:Count>1</m:Count>
                  <m:MaxHeight>String</m:MaxHeight>
                  <m:MaxWeight>88180</m:MaxWeight>
                  <m:MaxAxles>2</m:MaxAxles>
                  <m:Engine>
                    <m:Hybrid>false</m:Hybrid>
                    <m:EmissionType>EuroV</m:EmissionType>
                    <m:MinPollutionVeh>false</m:MinPollutionVeh>
                  </m:Engine>
                </m:TrailerCfg>
                <m:TruckCfg>
                  <m:Axles>0</m:Axles>
                  <m:Height>String</m:Height>
                  <m:LCV>true</m:LCV>
                  <m:Length>String</m:Length>
                  <m:Units>English</m:Units>
                  <m:Weight>String</m:Weight>
                  <m:Width>String</m:Width>
                </m:TruckCfg>
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
              <m:ReportingOptions>
                <m:EstimatedTimeOptions>
                  <m:ETAETD>Arrival</m:ETAETD>
                  <m:DateOption>Current</m:DateOption>
                  <m:DateAndTime>
                    <m:CalendarDate>String</m:CalendarDate>
                    <m:DayOfWeek>Sunday</m:DayOfWeek>
                    <m:TimeOfDay>String</m:TimeOfDay>
                    <m:TimeZone>Local</m:TimeZone>
                  </m:DateAndTime>
                </m:EstimatedTimeOptions>
                <m:ExchangeRate>3.14159265358979E0</m:ExchangeRate>
                <m:FuelUnits>Gallons</m:FuelUnits>
                <m:IncludeFerryDistance>true</m:IncludeFerryDistance>
                <m:Language>ENUS</m:Language>
                <m:RouteCosts>
                  <m:CostTimeEmpty>3.14159265358979E0</m:CostTimeEmpty>
                  <m:CostTimeLoaded>3.14159265358979E0</m:CostTimeLoaded>
                  <m:FuelEconomyEmpty>3.14159265358979E0</m:FuelEconomyEmpty>
                  <m:FuelEconomyLoaded>3.14159265358979E0</m:FuelEconomyLoaded>
                  <m:GreenHouseGas>3.14159265358979E0</m:GreenHouseGas>
                  <m:OtherCostPerDistUnitLoaded>3.14159265358979E0</m:OtherCostPerDistUnitLoaded>
                  <m:OtherCostPerDistanceUnitEmpty>3.14159265358979E0</m:OtherCostPerDistanceUnitEmpty>
                  <m:PricePerFuelUnit>3.14159265358979E0</m:PricePerFuelUnit>
                  <m:TruckStyle>None</m:TruckStyle>
                </m:RouteCosts>
                <m:TimeCosts>
                  <m:BreakInterval>3.14159E0</m:BreakInterval>
                  <m:BreakLength>3.14159E0</m:BreakLength>
                  <m:BorderWait>3.14159E0</m:BorderWait>
                  <m:DepartTime>
                    <m:Hour>0</m:Hour>
                    <m:Minute>0</m:Minute>
                    <m:AmPm>Military</m:AmPm>
                  </m:DepartTime>
                  <m:RemainingHoursOfService>3.14159E0</m:RemainingHoursOfService>
                </m:TimeCosts>
                <m:TollCurrency>US</m:TollCurrency>
                <m:TollDiscount>String</m:TollDiscount>
                <m:UseCustomRoadSpeeds>true</m:UseCustomRoadSpeeds>
                <m:UseTollData>true</m:UseTollData>
                <m:UseTraffic>true</m:UseTraffic>
              </m:ReportingOptions>
              <m:ReportTypes>
                <m:ReportType/>
              </m:ReportTypes>
            </m:ReportRoute>
          </m:ReportRoutes>
        </m:Body>
      </m:Request>
    </m:GetReports>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Report Request

#### Request Body Elements

Represents a ReportRequest structure containing the request header and report specific data. The request body contains a collection of routes and routing options.

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
      <td><code>ReportRoutes</code></td>
      <td>
        A list &lt;&gt; of ReportRoute object. Gets or sets the list of
        ReportRoute objects to create routing information.<br><br>
        Usage:<br>
        <span
          >List&lt;ReportRoute&gt; listr = new List &lt;ReportRoute&gt;();</span>
        <br>
        <span
          >ReportRoute rr = new ReportRoute { Stops = new StopLocation[3]
          };</span>
        <br>
        <span>listr.Add(rr);</span>
        <br>
        <span>Body.ReportRouters = listr.ToArray();</span>
      </td>
      <td>Y</td>
    </tr>
  </tbody>
</table>

#### ReportRoute Members

Represents a route and all its associate information from the standpoint of a request for reporting.

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
                        <td><code>Options</code></td>
                        <td>
                            A <a href="/soap-apis/docs/shared-api-members#routeoptions">RouteOptions</a> object. Gets or sets the routing options for the route calculations.
                            <br>
                            <br>
                            Usage:<span>RouteOptions tripOption = new RouteOptions()</span>
                            <span>{</span>
                            <span>HighwayOnly = true,</span>
                            <span>HighwayOnlySpecified = true,</span>
                            <span>VehicleType = VehicleType.Truck,</span>
                            <span>VehicleTypeSpecified = true,</span>
                            <span>ClassOverrides = ClassOverridesType.FiftyThreeFoot,</span>
                            <span>ClassOverridesSpecified = True,</span>
                            <span>};</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>ReportingOptions</code></td>
                        <td>
                            A ReportOptions object. Gets or sets the reporting options used in creating the output data.
                            <br>
                            <br>
                            Usage:<span>ReportOptions repOption = new ReportOptions()</span>
                            <p style="text-indent: 4em;" class="mb-0"><span>{</span></p>
                            <p style="text-indent: 5em;" class="mb-0"><span>EstimatedTimeOptions = timeOpts,</span></p>
                            <p style="text-indent: 5em;" class="mb-0"><span>ExchangeRate = 1.5,</span></p>
                            <p style="text-indent: 5em;" class="mb-0"><span>ExchangeRateSpecified = true,</span></p>
                            <p style="text-indent: 4em;" class="mb-0"><span>};</span></p>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>ReportTypes</code></td>
                        <td>
                            A list of ReportType object. Gets or sets a collection of different report types that the user would like to have generated.
                            <br>
                            This collection should contain instances of:<br>
                            MileageReportType, DetailReportType, CalculateMilesReportType, DirectionsReportType, GeoTunnelReportType, HoursOfServiceReportType, LeastCostReportType, RoadReportType, WeatherAlertsReportType, StateReportType, TollDetailReportType.
                            <br>
                            <br>
                            Usage:<br>
                            <span>ReportTypes = new ReportType[2];</span>
                            <br>
                            <span>ReportTypes[0] = (new DirectionsMilesReportType() {</span>
                            <br>
                            <span>CondenseDirections = true, CondenseDirectionsSpecified = true });</span>
                            <br>
                            <span>ReportTypes[1] = new MileageReportType();</span>
                        </td>
                        <td>Y</td>
                    </tr>
                    <tr>
                        <td><code>RouteId</code></td>
                        <td>
                            A string value. Sets the unique route identifier. This may be used to identify routes when reports are created.
                            <br>
                            <br>
                            Usage:<span>routeID = "PhillytoAC";</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Stops</code></td>
                        <td>
                            A list of the StopLocation object. Sets the collection of stops that make up the route.
                            <br>
                            <br>
                            Usage:<span>ServiceRef.StopLocation [] stops = new ServiceRef.StopLocation[3];</span>
                        </td>
                        <td>Y</td>
                    </tr>
                </tbody>
</table>

#### Report Class

Represents a general report. This class is abstract and cannot be instantiated. All reports are subclassed from this.

#### Inheritance Hierarchy

System.Object

- ALK.PCM.Model.BusinessModels.Report
  - ALK.PCM.Model.BusinessModels.CalculateMilesReport
  - ALK.PCM.Model.BusinessModels.DetailedReport
  - ALK.PCM.Model.BusinessModels.DirectionsReport
  - ALK.PCM.Model.BusinessModels.GeoTunnelReport
  - ALK.PCM.Model.BusinessModels.HoursOfServiceReportType
  - ALK.PCM.Model.BusinessModels.LeastCostReport
  - ALK.PCM.Model.BusinessModels.MileageReport
  - ALK.PCM.Model.BusinessModels.RoadReport
  - ALK.PCM.Model.BusinessModels.StateReport
  - ALK.PCM.Model.BusinessModels.TollDetailReportType

#### CalculateMiles Report Type

The CalculateMilesReportType represents a request for a Calculate Miles Report which is simply a request for total miles for a trip. This type does not have any additional request members.

**Detailed Report Type**

#### The DetailedReportType

represents a request for a detailed report as part of a ReportRequestBody

**DetailedReportType Members**

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
      <td><code>SeparateHeadingFromRoute</code></td>
      <td>
        A boolean value. When set to true, the DetailedReportLine.Direction(North, South, etc) property will contain the heading, otherwise it will be prepended onto the DetailedReportLine.Route property.
        <br />For Example: <br />
        When true, the response element Direction and Route will be populated: <br /><br />
        &lt;Direction&gt;North&lt;/Direction&gt;<br />
        &lt;Route&gt;Local&lt;/Route&gt; <br /><br />
        When False, the Direction will be Nil and the Route will have the direction valued precede the route value: <br /><br />
        &lt;Direction i:nil="true"/&gt; <br />
        &lt;Route&gt;North Local&lt;/Route&gt; <br/><br />
        Usage: <br />
        <span>ReportTypes = new ReportType[1];</span><br/>
        <span>ReportTypes[0] = (new DetailedReportType() { SeparateHeadingFromRoute = true, separateHeadingFromRouteFieldSpecified = true });</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>SegmentEndpoints</code></td>
      <td>
        Indicate whether or not to report segment endpoint coordinates. Default is false. <br />
        When set to true, the DetailReportLine.StartCoordinate and EndCoordinate properties will contain the segment endpoint coordinates.
        <br /><br />Usage: <br /><span>ReportTypes = new ReportType[1];</span> <br />
        <span>ReportTypes[0] = (new DetailedReportType() { SeparateHeadingRoute = true});</span>
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

### Directions Report Type

The DirectionsReportType represents a request for a Directions Report within a ReportRequestBody

**DirectionsReportType Members**

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
      <td><code>CondenseDirections</code></td>
      <td>
        A boolean value. Gets or sets a value indicating whether or not to
        condense the driving directions within the report.
        <br /><br />Usage: <br /><span>ReportTypes = new ReportType[1];</span>
        <br /><span
          >ReportTypes[0] = (new DirectionsReportType() { CondenseDirections =
          true, CondenseDirectionsSpecified = true });</span>
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

#### Directions Report Type

The DirectionsReportType represents a request for a Directions Report within a ReportRequestBody

**DirectionsReportType Members**

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
      <td><code>CondenseDirections</code></td>
      <td>
        A boolean value. Gets or sets a value indicating whether or not to
        condense the driving directions within the report.
        <br /><br />Usage: <br /><span
          >ReportTypes = new ReportType[1];</span>
        <br /><span>ReportTypes[0] = (new DirectionsReportType() { CondenseDirections =
          true, CondenseDirectionsSpecified = true });</span>
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

#### Geotunnel Report Type

The GeotunnelReportType represents a request for a geotunnel report which is a series of points along a route.

**GeotunnelReportType Members**

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
      <td><code>CiteInterval</code></td>
      <td>
        A double value. Gets or sets the desired distance in miles between each
        point.
        <br /><br />
        Usage: <br />
        <span>ReportTypes = new ReportType[1];</span>
        <br /><span>ReportTypes[0] = (new GeotunnelReportType() { CiteInterval = 25 });</span>
      </td>
      <td>Y</td>
    </tr>
  </tbody>
</table>

#### Hours of Service Report Type

HoursOfServiceReportType is a report type that calculates estimated departure and arrival times for all stops. If hours of service options are given rest stops will be inserted to maintain hours of service compliance. Remaining hours of service at the end of the trip will also be provided.

#### LeastCost Report Type

The LeastCostReportType represents a request for a least cost report within a ReportRequestBody. This does not have any additional request members.

#### Mileage Report Type

MileageReportType represents a request for a mileage report which contains mileage information for each stop as well as mileage information for the entire trip. This type does not have any additional request members.

#### Road Report Type

RoadReportType represents a request for a road report which is a report that breaks up miles by road type. This type does not have any additional request members.

#### State Report Type

StateReportType is a report type to display the summary of mileage by state and country travelled.

**StateReportType Members**

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
      <td><code>SortByRoute</code></td>
      <td>
        A boolean value. Gets or sets whether the state in the report should be
        sorted by route order(true) or alphabetically in State order(false -
        default).
        <br /><br />Usage: <br /><span
          >ReportTypes = new ReportType[1];</span
        >
        <br /><span
          >ReportTypes[0] = (new StateReportType() { SortByRoute = true,
          SortByRouteSpecified = true });</span
        >
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

### Toll Detail Report Type

TollDetailType represents a request for a detailed toll report in the European streets dataset which contains detailed toll information for each segment as well as a summary of toll costs by country and toll. This type does not have any additional request members, however the `TrailerCfg` object should be filled in within the `RouteOptions` and `ReportType` list should contain a `TollDetailReportType`. Please note that report is only available within the PCM_EU dataset and is currently in beta.

### Calling GetReports

```js
List<ReportRoute> rptRoutes = new List<ReportRoute>();
     ReportRoute rr = new ReportRoute();
    ReportRoute rptRoute = new ReportRoute();
    rptRoute.Stops = new StopLocation[2];
    rptRoute.Stops[0] = new StopLocation()
    {

        Address = new Address()
        {
            City = "Princeton",
            State = "NJ",
            Zip = "08540"
        },
        Label = "Princeton, NJ",
        Region = DataRegion.NA,
        RegionSpecified = true
    };
    rptRoute.Stops[1] = new StopLocation()
    {
        Address = new Address()
        {
            City = "Beverly Hills",
            State = "CA",
            Zip = "90210"
        },
        Label = "Beverly Hills, CA",
        Region = DataRegion.NA,
        RegionSpecified = true
    };
    // Request a directions report and mileage report
    rptRoute.ReportTypes = new  ReportType[2];

    rptRoute.ReportTypes[0] = (new DirectionsReportType() { CondenseDirections = true, CondenseDirectionsSpecified = true });
    rptRoute.ReportTypes[1] = (new MileageReportType());
    // Set route options
    rptRoute.RouteId = "Test Route";
    rptRoute.Options = new RouteOptions();
    rptRoute.Options.HubRouting = false;
    rptRoute.Options.HubRoutingSpecified = true;
    rptRoute.Options.HighwayOnly = true;
    rptRoute.Options.HighwayOnlySpecified = true;
    rptRoute.Options.DistanceUnits = DistanceUnits.Miles;
    rptRoute.Options.DistanceUnitsSpecified = true;
    rptRoute.Options.VehicleType = VehicleType.Truck;
    rptRoute.Options.VehicleTypeSpecified = true;

    rptRoute.Options.TruckCfg = new TruckConfig()
    {
        Axles = 2,
        Height = "13'6",
        Length = "53'0",
        Units = VehicleDimUnits.English,
        UnitsSpecified = true,
        Weight = "132000",
        AxlesSpecified = true,
        Width = "102\""
    };
    rptRoute.ReportingOptions = new ReportOptions() { TollDiscount = "ALL", UseTollData = true, UseTollDataSpecified = true  };
    rptRoutes.Add(rptRoute);
    ReportRequest request = new ReportRequest()
    {
        Header = new RequestHeader() { DataVersion =  DataVersion.ToString(), RequestType = "GetReports" },
        Body = new ReportRequestBody()
    };
    request.Body.ReportRoutes = rptRoutes.ToArray();
    // Create the authentication and authorization header
    AuthHeader soapHeader = this.Caller.GenerateAuthHeader(this.Caller.APIName);
    // Create the service client
    ServiceClient service = new ServiceClient();
    // Call,  API
    ReportResponse response = service.GetReports(soapHeader, request);
```

### Request

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">https://pcmiler.alk.com/APIs/v1.0/IService/GetReports</Action>
    <h:AuthHeader xmlns="http://www.alk.com" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:h="http://www.alk.com">
      <Authorization>A77097D2D202A743BB1660E15794D7CA</Authorization>
      <Date>Wed, 24 Sep 2014 16:54:53 GMT</Date>
    </h:AuthHeader>
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <GetReports xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <Request>
        <Header>
          <DataVersion>current</DataVersion>
          <RequestType>GetReports</RequestType>
        </Header>
        <Body>
          <ReportRoutes>
            <ReportRoute>
              <RouteId>Test Route</RouteId>
              <Stops>
                <StopLocation>
                  <Address>
                    <StreetAddress xsi:nil="true" />
                    <City>Princeton</City>
                    <State>NJ</State>
                    <Zip>08540</Zip>
                    <County xsi:nil="true" />
                    <Country xsi:nil="true" />
                    <SPLC xsi:nil="true" />
                  </Address>
                  <Coords xsi:nil="true" />
                  <Region>NA</Region>
                  <Label>Princeton, NJ</Label>
                  <PlaceName xsi:nil="true" />
                  <Costs xsi:nil="true" />
                </StopLocation>
                <StopLocation>
                  <Address>
                    <StreetAddress xsi:nil="true" />
                    <City>Beverly Hills</City>
                    <State>CA</State>
                    <Zip>90210</Zip>
                    <County xsi:nil="true" />
                    <Country xsi:nil="true" />
                    <SPLC xsi:nil="true" />
                  </Address>
                  <Coords xsi:nil="true" />
                  <Region>NA</Region>
                  <Label>Beverly Hills, CA</Label>
                  <PlaceName xsi:nil="true" />
                  <Costs xsi:nil="true" />
                </StopLocation>
              </Stops>
              <Options>
                <DistanceUnits>Miles</DistanceUnits>
                <HighwayOnly>true</HighwayOnly>
                <HubRouting>false</HubRouting>
                <TruckCfg>
                  <Axles>2</Axles>
                  <Height>13'6</Height>
                  <Length>53'0</Length>
                  <Units>English</Units>
                  <Weight>132000</Weight>
                  <Width>102"</Width>
                </TruckCfg>
                <VehicleType>Truck</VehicleType>
              </Options>
              <FuelOptions xsi:nil="true" />
              <AFOptions xsi:nil="true" />
              <ReportingOptions>
                <EstimatedTimeOptions xsi:nil="true" />
                <RouteCosts xsi:nil="true" />
                <TimeCosts xsi:nil="true" />
                <TollDiscount>ALL</TollDiscount>
                <UseTollData>true</UseTollData>
              </ReportingOptions>
              <ReportTypes>
                <ReportType xsi:type="DirectionsReportType">
                  <CondenseDirections>true</CondenseDirections>
                </ReportType>
                <ReportType xsi:type="DetailReportType">
                  <SeparateHeadingFromRoute>true</SeparateHeadingFromRoute>
                </ReportType>
                <ReportType xsi:type="MileageReportType" />
                <ReportType xsi:type="StateReportType">
                  <SortByRoute>true</SortByRoute>
                </ReportType>
              </ReportTypes>
            </ReportRoute>
          </ReportRoutes>
        </Body>
      </Request>
    </GetReports>
  </s:Body>
</s:Envelope>
```

### Response

Represents ReportResponse structure containing the response header and report response body.

**ReportResponseBody Members**

Gets or sets the report response body. Represents the ReportResponseBody structure which contains a collection of Report objects.

**CalculateMilesReport Response Members**

Represents a Calculate Miles Report which simply contains the total miles for a trip.

| Element   | Definition                                                                                                            |
| --------- | --------------------------------------------------------------------------------------------------------------------- |
| `RouteID` | A string value. Gets or sets the unique route identifier that was supplied during the request. Inherited from Report. |
| `TMiles`  | A double value. Gets or sets the total miles for the trip.                                                            |

**DetailReport Response Members**

Represents a detailed report which contains detailed information for a trip including mileage, costs, directions, etc.

| Element           | Definition                                                                                                                                             |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `Destination`     | A GeocodeOutputLocation object. Gets or sets the trip's destination.                                                                                   |
| `Origin`          | A GeocodeOutputLocation object. Gets or sets the trip's origin.                                                                                        |
| `ReportLegs`      | A list of `<DetailReportLeg>` objects. Gets or sets the list of the detail report's legs. There should be one leg per trip stop including destination. |
| `RouteID`         | Gets or sets the unique route identifier that was supplied during the request. Inherited from Report.                                                  |
| `TrafficDataUsed` | A boolean value. Gets or sets the value indicating whether or not traffic data is used in this report.                                                 |

**GeocodeOutputLocation Members**

Represents the result of geocoding or reverse geocoding location.

<table class="table table-sm">
  <thead>
    <tr>
      <th>Element</th>
      <th>Definition</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>Address</code></td>
      <td>Gets or sets the address information for the location.</td>
    </tr>
    <tr>
      <td><code>Coords</code></td>
      <td>Gets or sets the geographic coordinates for the location.</td>
    </tr>
    <tr>
      <td><code>Errors</code></td>
      <td>Gets or sets any errors or warnings associated with the geocode result.</td>
    </tr>
    <tr>
      <td><code>Label</code></td>
      <td>A string. Gets or sets a string which represents a label to be displayed on maps and in reports in association with a stop.</td>
    </tr>
    <tr>
      <td><code>PlaceName</code></td>
      <td>A string. Gets or sets the place name which responds to a custom place; this would supersede standard address entries for geocoding or identify a custom place to be associated with the address.</td>
    </tr>
    <tr>
      <td><code>Region</code></td>
      <td>An enumeration of DataRegion. Gets or sets the Region that the location is in.</td>
    </tr>
    <tr id="timeZone">
      <td><code>TimeZone</code></td>
      <td>
        An enumeration of TimeZone. Gets or sets the time zone for the time. Note the time zone for traffic will always be the system's time zone regardless of the value set here.
        <br />
        <table class="table table-sm">
          <thead>
            <tr>
              <th>Member Name</th>
              <th>Value</th>
              <th>Description</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><code>Local</code></td>
              <td>0</td>
              <td>Indicates that the timezone should be the local time at each stop.</td>
            </tr>
            <tr>
              <td><code>System</code></td>
              <td>1</td>
              <td>Indicates that the timezone to be that of the server.</td>
            </tr>
            <tr>
              <td><code>Hawaii</code></td>
              <td>2</td>
              <td>Indicates the timezone for Hawaii.</td>
            </tr>
            <tr>
              <td><code>Alaska</code></td>
              <td>3</td>
              <td>Indicates the timezone for Alaska.</td>
            </tr>
            <tr>
              <td><code>Pacific</code></td>
              <td>4</td>
              <td>Indicates the Pacific timezone.</td>
            </tr>
            <tr>
              <td><code>Arizona</code></td>
              <td>5</td>
              <td>Indicates the timezone for the state of Arizona.</td>
            </tr>
            <tr>
              <td><code>Mountain</code></td>
              <td>6</td>
              <td>Indicates the Mountain timezone.</td>
            </tr>
            <tr>
              <td><code>Central</code></td>
              <td>7</td>
              <td>Indicates the Central timezone.</td>
            </tr>
            <tr>
              <td><code>Eastern</code></td>
              <td>8</td>
              <td>Indicates the Eastern timezone.</td>
            </tr>
            <tr>
              <td><code>Atlantic</code></td>
              <td>9</td>
              <td>Indicates the Atlantic timezone.</td>
            </tr>
            <tr>
              <td><code>Newfoundland</code></td>
              <td>7</td>
              <td>Indicates the timezone for Newfoundland.</td>
            </tr>
          </tbody>
        </table>
        <br />
        Usage: <span>TimeZone = TimeZone.Eastern;</span>
      </td>
    </tr>
    <tr>
      <td><code>ConfidenceLevel</code></td>
      <td>The confidence level of the match. See detailed definition in <a href="/restful-apis/developer-guide/appendix/glossary/">Glossary</a>.</td>
    </tr>
    <tr>
      <td><code>DistanceFromRoad</code></td>
      <td>The distance from coordinate to nearest road.</td>
    </tr>
  </tbody>
</table>

**DetailedReportLeg Members**

Represents one of the legs of a detailed report.

<table class="table table-sm">
  <thead>
    <tr>
      <th>Element</th>
      <th>Definition</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>Dest</code></td>
      <td>A <a href="#GeocodeOutputLocation">GeocodeOutputLocation</a> object. Gets or sets the destination of the journey.</td>
    </tr>
    <tr>
      <td><code>Origin</code></td>
      <td>A <a href="#GeocodeOutputLocation">GeocodeOutputLocation</a> object. Gets or sets the origin of the journey.</td>
    </tr>
    <tr>
      <td><code>ReportLines</code></td>
      <td>A List of &lt;<a href="#DetailReportLine">DetailReportLine</a>&gt; object. Gets or sets the list of report lines associated with this report leg.</td>
    </tr>
  </tbody>
</table>

#### DetailReportLine Members

Gets or sets the list of report lines associated with this report leg. Represents a single line on a detailed report.

| Element         | Definition                                                                                               |
| --------------- | -------------------------------------------------------------------------------------------------------- |
| `ArState`       | A string value. Gets or sets the arrival state information such as arrive loaded.                        |
| `Direction`     | A string value. Gets or sets the direction or heading to drive on the route.                             |
| `EtaEtd`        | A string value. Gets or sets the estimated time of arrival or departure for this particular report line. |
| `Info`          | A string value. Gets or sets driver break and border wait information.                                   |
| `InterCh`       | A string value. Gets or sets interchange information associated with this report line.                   |
| `LMiles`        | A string value. Gets or sets the miles accumulated on the report leg.                                    |
| `LTime`         | A string value. Gets or sets the time elapsed on the report leg.                                         |
| `LToll`         | A string value. Gets or sets the toll costs for the report leg.                                          |
| `Miles`         | A string value. Gets or sets the miles to travel on the Route.                                           |
| `Restriction`   | A string value. Gets or sets hazmat restriction information.                                             |
| `Route`         | A string value. Gets or sets driving instruction along with the associated route or road.                |
| `State`         | A string value. Gets or sets the state for this report line and associated information takes place in.   |
| `Stop`          | A string value. Gets or sets the stop information.                                                       |
| `Time`          | A string value. Gets or sets the time to travel on the Route.                                            |
| `TMiles`        | A string value. Gets or sets the total miles accumulated for the trip thus far.                          |
| `TollPlazaAbbr` | A string value. Gets or sets the toll plaza abbreviation.                                                |
| `TollPlazaName` | A string value. Gets or sets toll plaza name.                                                            |
| `TTime`         | A string value. Gets or sets the total time elapsed for the trip thus far.                               |
| `TToll`         | A string value. Gets or sets the total toll costs for the trip thus far.                                 |
| `Warn`          | A string value. Gets or sets the warning associated with this report line.                               |

#### DirectionsReport Response Members

Represents a driving directions report.

| Element       | Definition                                                                                                                                                    |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Destination` | A GeocodeOutputLocation object. Gets or sets the trip's destination.                                                                                          |
| `Origin`      | A GeocodeOutputLocation object. Gets or sets the trip's origin.                                                                                               |
| `ReportLegs`  | A list of `<DirectionsReportLeg>` objects. Gets or sets the list of the direction report's legs. There should be one leg per trip stop including destination. |
| `RouteID`     | Gets or sets the unique route identifier that was supplied during the request. Inherited from Report.                                                         |

#### DirectionReportLeg Members

Represents a leg of a direction report.

| Element       | Definition                                                                                                        |
| ------------- | ----------------------------------------------------------------------------------------------------------------- |
| `Dest`        | A GeocodeOutputLocation object. Gets or sets the destination of the journey.                                      |
| `Origin`      | A GeocodeOutputLocation object. Gets or sets the origin of the journey.                                           |
| `ReportLines` | A List of `<DirectionsReportLine>` object. Gets or sets the list of report lines associated with this report leg. |

#### DirectionReportLine Members

Represent the directions report line

| Element     | Definition                                                                                                     |
| ----------- | -------------------------------------------------------------------------------------------------------------- |
| `Delay`     | A string value. Gets or sets any delay associated with this report line.                                       |
| `Direction` | A string value. Gets or sets the direction or heading to drive on the route.                                   |
| `Dist`      | A string value. Gets or sets the distance to travel for the associated driving directions in this report line. |
| `InterCh`   | A string value. Gets or sets interchange information associated with this report line.                         |
| `Time`      | A string value. Gets or sets the time it will take to travel the distance for the report line.                 |
| `Warn`      | A string value. Gets or sets the warning associated with this report line.                                     |

#### GeotunnelReport Response Members

Represents a geotunnel report which is a series of coordinates along the route at a given interval.

| Element           | Definition                                                                                                            |
| ----------------- | --------------------------------------------------------------------------------------------------------------------- |
| `GeoTunnelPoints` | A List of `<Coordinates>` object. A string value. Gets or sets the coordinates along the route.                       |
| `RouteID`         | A string value. Gets or sets the unique route identifier that was supplied during the request. Inherited from Report. |

#### LeastCostReport Response Members

Represents a least cost report which contains information of alternative routes with distance, time and cost estimates.

| Element       | Definition                                                                                                                                                                           |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `Destination` | A GeocodeOutputLocation object. Gets or sets the trip's destination.                                                                                                                 |
| `Origin`      | A GeocodeOutputLocation object. Gets or sets the trip's origin.                                                                                                                      |
| `ReportLines` | A list of `<ComparisonReportLine>` object. Gets or sets the comparison report lines each of which contains the distance, time and cost estimates for its respective alternate route. |
| `RouteID`     | Gets or sets the unique route identifier that was supplied during the request. Inherited from Report.                                                                                |

#### ComparisonReportLine Response Members

Gets or sets the comparison report lines each of which contains the distance, time and cost estimates for its respective alternate route.

| Element                | Definition                                                                                                                            |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `Cost`                 | A string value. Gets or sets the trip's total cost for this particular least cost configuration.                                      |
| `Estghg`               | A string value. Gets or sets the trip's estimated greenhouse gas emissions for this particular least cost configuration.              |
| `Fuel`                 | A string value. Gets or sets the fuel costs for this particular least cost configuration.                                             |
| `Hours`                | A string value. Gets or sets the trip's total hours for this particular least cost configuration.                                     |
| `Labor`                | A string value. Gets or sets the trip's total cost for labor for this particular least cost configuration.                            |
| `LeastCostTripOptions` | A string value. Gets or sets the trip's least cost configuration which is the routing type followed by whether or not tolls are used. |
| `Miles`                | A string value. Gets or sets the trip's total mileage for this particular least cost configuration.                                   |
| `Other`                | A string value. Gets or sets the trip's total cost for maintenance for this particular least cost configuration.                      |
| `Route`                | A string value. Gets or sets the route identifier, which will be Route followed by the route number.                                  |
| `Tolls`                | A string value. Gets or sets the trip's total cost for tolls for this particular least cost configuration.                            |

#### MileageReport Response Members

Represents a mileage report for a trip

| Element           | Definition                                                                                                         |
| ----------------- | ------------------------------------------------------------------------------------------------------------------ |
| `ReportLines`     | A list of `<StopReportLine>` objects. Gets or sets the collection of report lines that make up the mileage report. |
| `RouteID`         | Gets or sets the unique route identifier that was supplied during the request. Inherited from Report.              |
| `TrafficDataUsed` | A boolean value. Gets or sets the value indicating whether or not traffic data is used in this report.             |

#### StopReportLine Response Members

Gets or sets the collection of report lines that make up the mileage report. The StopReportLine structure is used to return the line information associated with each stop of the State/Country Distance report, as well as the Mileage report.

| Element     | Definition                                                                                               |
| ----------- | -------------------------------------------------------------------------------------------------------- |
| `EtaEtd`    | A string value. Gets or sets the estimated time of arrival or departure for this particular report line. |
| `LCostMile` | A string value. Gets or sets the leg cost/mile data.                                                     |
| `LEstghg`   | A string value. Gets or sets the leg ESTGHG data.                                                        |
| `LHours`    | A string value. Gets or sets the leg hours data.                                                         |
| `LMiles`    | A string value. Gets or sets the leg mileage data.                                                       |
| `LToll`     | A string value. Gets or sets the leg toll data.                                                          |
| `Stop`      | A string value. Gets or sets the address information at the stop.                                        |
| `TCostMile` | A string value. Gets or sets the total cost/mile data.                                                   |
| `TEstghg`   | A string value. Gets or sets the total ESTGHG data..                                                     |
| `THours`    | A string value. Gets or sets the total hours data.                                                       |
| `TMiles`    | A string value. Gets or sets total mileage data.                                                         |
| `TToll`     | A string value. Gets or sets the total toll data.                                                        |

#### RoadReport Response Members

Represents a road report which contains mile information broken down by road.

| Element       | Definition                                                                                                          |
| ------------- | ------------------------------------------------------------------------------------------------------------------- |
| `Disclaimer`  | A list of `<string>` objects. Gets or sets a collection of strings that make up the disclaimer for the road report. |
| `ReportLines` | A list of `<RoadReportLine>` objects. Gets or sets the collection of report lines that make up the mileage report.  |
| `RouteID`     | Gets or sets the unique route identifier that was supplied during the request. Inherited from Report.               |

#### RoadReportLine Response Members

Gets or sets the road report lines that make up the road report. Represents a single line of information within a road report.

| Element         | Definition                                                                                         |
| --------------- | -------------------------------------------------------------------------------------------------- |
| `Divide`        | A string value. Gets or sets the number of divided highway miles.                                  |
| `Energy`        | A string value. Gets or sets the number of miles on energy roads.                                  |
| `Ferry`         | A string value. Gets or sets the number of ferry miles.                                            |
| `InterSt`       | A string value. Gets or sets the number of interstate miles.                                       |
| `InterstNoRamp` | A string value. Gets or sets the number of interstate no ramp miles.                               |
| `LMiles`        | A string value. Gets or sets the number of leg miles.                                              |
| `Local`         | A string value. Gets or sets the number of miles on a local road.                                  |
| `Prime`         | A string value. Gets or sets the number of primary road miles.                                     |
| `Ramp`          | A string value. Gets or sets the number of ramp miles.                                             |
| `Second`        | A string value. Gets or sets the number of secondary road miles.                                   |
| `Stop`          | A `<GeocodeOutputLocation>` object. Gets or sets the stop location associate with the report line. |
| `Toll`          | A string value. Gets or sets the number of miles on toll roads.                                    |

#### StateReport Response Members

The State Report Structure contains a summary of mileage by state and country travelled.

| Element              | Definition                                                                                             |
| -------------------- | ------------------------------------------------------------------------------------------------------ |
| `MileageReportLines` | A list of `<StopReportLine>` objects. Gets or sets a collection of StopReportLine objects.             |
| `RouteID`            | Gets or sets the unique route identifier that was supplied during the request. Inherited from Report.  |
| `StateReportLines`   | A list of `<StateCostReportLine>` objects. Gets or sets the collection of StateCostReportLine objects. |

#### StateCostReport

Gets or sets a collection of StateCostReportLine objects. the StateCostReportLine structure contains the state/country line information in the State Report.

| Element   | Definition                                                                              |
| --------- | --------------------------------------------------------------------------------------- |
| `Empty`   | A string value. Gets or sets the empty miles travelled in the state/country.            |
| `Energy`  | A string value. Gets or sets the miles travelled on energy roads for the state/country. |
| `Ferry`   | A string value. Gets or sets the ferry miles travelled in the state/country.            |
| `Free`    | A string value. Gets or sets the non-toll road miles travelled in the state/country.    |
| `Loaded`  | A string value. Gets or sets the loaded miles travelled in the state/country.           |
| `StCntry` | A string value. Gets or sets the state/country information.                             |
| `Toll`    | A string value. Gets or sets the toll road miles travelled in the state/country.        |
| `Tolls`   | A string value. Gets or sets the toll cost for the state (in North America).            |
| `Total`   | A string value. Gets or sets the total miles travelled in the state/country.            |

#### TollDetailReport Response Members

The Toll Detail Report Structure contains detailed toll information per segment as well as toll summary information.

| Element        | Definition                                                                                                             |
| -------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `RouteID`      | Gets or sets the unique route identifier that was supplied during the request. Inherited from [Report](#report-class). |
| `SegmentLines` | A list of [TollDetailReportSegmentLine](#tolldetailreportsegmentline) objects.                                         |
| `SummaryLines` | A list of [TollDetailReportSummaryLine](#tolldetailReportsummaryline) objects.                                         |
| `TollCurrency` | The toll currency used for the `<TollDetailReportSummaryLine>`                                                         |

#### TollDetailReportSegmentLine

Gets or sets a collection of [TollDetailReportSegmentLine](#tolldetailreportsegmentline) objects. the TollDetailReportSegmentLine structure contains the country, toll, road and cost information per toll segment.

| Element         | Definition                                                              |
| --------------- | ----------------------------------------------------------------------- |
| `Country`       | A string value. Gets or sets the country abbreviation.                  |
| `Road`          | A string value. Gets or sets the road name.                             |
| `TollName`      | A string value. Gets or sets the toll name.                             |
| `DistanceBased` | A string value. Gets or sets the distance based toll cost.              |
| `Pass`          | A string value. Gets or sets the toll cost if the toll requires a pass. |
| `Flat`          | A string value. Gets or sets the toll cost if the toll has a flat rate. |

#### TollDetailReportSummaryLine

Gets or sets a collection of TollDetailReportSummaryLine objects. the TollDetailReportSummaryLine structure contains summary information for the country, toll, toll cost and payment option.

| Element         | Definition                                                                                                  |
| --------------- | ----------------------------------------------------------------------------------------------------------- |
| `Country`       | A string value. Gets or sets the country name.                                                              |
| `TollType`      | A string value. Gets or sets the type of toll.                                                              |
| `TollName`      | A string value. Gets or sets the toll name.                                                                 |
| `TollDistance`  | A string value. Gets or sets the distance used in toll calculation if the toll type is distance based.      |
| `TollsLocal`    | A string value. Gets or sets the toll cost in local currency.                                               |
| `Tolls`         | A string value. Gets or sets the toll cost in the desired currency specified by ReportOptions.TollCurrency. |
| `PaymentOption` | A string value. Gets or sets the toll payment option - whether it is cash, bank card, etc.                  |

### Sample GetReport Response

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header />
  <s:Body>
    <GetReportsResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <GetReportsResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>GetReports</Type>
          <Success>true</Success>
          <DataVersion>28.0.25.2830</DataVersion>
          <Errors />
        </Header>
        <Body>
          <Reports>
            <Report i:type="DirectionsReport">
              <RouteID>Test Route</RouteID>
              <Origin>
                <Address>
                  <StreetAddress />
                  <City>Princeton</City>
                  <State>NJ</State>
                  <Zip>08540</Zip>
                  <County>Mercer</County>
                  <Country>United States</Country>
                  <SPLC i:nil="true" />
                  <CountryPostalFilter>US</CountryPostalFilter>
                  <AbbreviationFormat>FIPS</AbbreviationFormat>
                  <CountryAbbreviation>US</CountryAbbreviation>
                </Address>
                <Coords>
                  <Lat>40.348727</Lat>
                  <Lon>-74.659049</Lon>
                </Coords>
                <Region>NA</Region>
                <Label>Princeton, NJ</Label>
                <PlaceName>Princeton, NJ</PlaceName>
                <TimeZone>EDT</TimeZone>
                <Errors />
              </Origin>
              <Destination>
                <Address>
                  <StreetAddress />
                  <City>Beverly Hills</City>
                  <State>CA</State>
                  <Zip>90210</Zip>
                  <County>Los Angeles</County>
                  <Country>United States</Country>
                  <SPLC i:nil="true" />
                  <CountryPostalFilter>US</CountryPostalFilter>
                  <AbbreviationFormat>FIPS</AbbreviationFormat>
                  <CountryAbbreviation>US</CountryAbbreviation>
                </Address>
                <Coords>
                  <Lat>34.079799</Lat>
                  <Lon>-118.412935</Lon>
                </Coords>
                <Region>NA</Region>
                <Label>Beverly Hills, CA</Label>
                <PlaceName>Beverly Hills, CA</PlaceName>
                <TimeZone>PDT</TimeZone>
                <Errors />
              </Destination>
              <ReportLegs>
                <DirectionsReportLeg>
                  <Origin>
                    <Address>
                      <StreetAddress />
                      <City>Princeton</City>
                      <State>NJ</State>
                      <Zip>08540</Zip>
                      <County>Mercer</County>
                      <Country>United States</Country>
                      <SPLC i:nil="true" />
                      <CountryPostalFilter>US</CountryPostalFilter>
                      <AbbreviationFormat>FIPS</AbbreviationFormat>
                      <CountryAbbreviation>US</CountryAbbreviation>
                    </Address>
                    <Coords>
                      <Lat>40.348727</Lat>
                      <Lon>-74.659049</Lon>
                    </Coords>
                    <Region>NA</Region>
                    <Label>Princeton, NJ</Label>
                    <PlaceName>Princeton, NJ</PlaceName>
                    <TimeZone>EDT</TimeZone>
                    <Errors />
                  </Origin>
                  <ReportLines>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>N Local</Direction>
                      <Dist>0.1</Dist>
                      <Time>0:00</Time>
                      <InterCh>+ Local NJ-27</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>S NJ-27</Direction>
                      <Dist>0.2</Dist>
                      <Time>0:00</Time>
                      <InterCh>+ NJ-27 Route 583</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>S Route 583</Direction>
                      <Dist>4.9</Dist>
                      <Time>0:07</Time>
                      <InterCh>+ Route 583 Ramp</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>S I-95</Direction>
                      <Dist>13.3</Dist>
                      <Time>0:12</Time>
                      <InterCh>+ I-95 X 46B</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BR X 46B</Direction>
                      <Dist>0.6</Dist>
                      <Time>0:02</Time>
                      <InterCh>+ X 46B US-1</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>S US-1</Direction>
                      <Dist>6.0</Dist>
                      <Time>0:05</Time>
                      <InterCh>+ US-1 Ramp</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-276</Direction>
                      <Dist>24.8</Dist>
                      <Time>0:23</Time>
                      <InterCh>+ I-276 I-76</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-76</Direction>
                      <Dist>251.5</Dist>
                      <Time>3:52</Time>
                      <InterCh>+ I-76 X 75</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BR X 75</Direction>
                      <Dist>0.6</Dist>
                      <Time>0:02</Time>
                      <InterCh>+ X 75 I-70</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-70</Direction>
                      <Dist>39.5</Dist>
                      <Time>0:37</Time>
                      <InterCh>+ I-70 </InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-70</Direction>
                      <Dist>27.0</Dist>
                      <Time>0:25</Time>
                      <InterCh>+ I-70 X 5A</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BL X 5A</Direction>
                      <Dist>0.0</Dist>
                      <Time>0:00</Time>
                      <InterCh>+ X 5A I-470</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-470</Direction>
                      <Dist>10.5</Dist>
                      <Time>0:10</Time>
                      <InterCh>+ I-470 Ramp</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-70</Direction>
                      <Dist>32.4</Dist>
                      <Time>0:30</Time>
                      <InterCh>+ I-70 </InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-70</Direction>
                      <Dist>145.1</Dist>
                      <Time>2:15</Time>
                      <InterCh>+ I-70 US-40</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-70</Direction>
                      <Dist>17.1</Dist>
                      <Time>0:16</Time>
                      <InterCh>+ I-70 OH-4</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-70</Direction>
                      <Dist>31.4</Dist>
                      <Time>0:29</Time>
                      <InterCh>+ I-70 OH-49</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-70</Direction>
                      <Dist>58.9</Dist>
                      <Time>0:54</Time>
                      <InterCh>+ I-70 X 90</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BR X 90</Direction>
                      <Dist>0.3</Dist>
                      <Time>0:01</Time>
                      <InterCh>+ X 90 Ramp</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>S I-465</Direction>
                      <Dist>17.6</Dist>
                      <Time>0:16</Time>
                      <InterCh>+ I-465 X 9</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BR X 9</Direction>
                      <Dist>1.0</Dist>
                      <Time>0:03</Time>
                      <InterCh>+ X 9 I-70</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-70</Direction>
                      <Dist>74.0</Dist>
                      <Time>1:08</Time>
                      <InterCh>+ I-70 </InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-70</Direction>
                      <Dist>61.7</Dist>
                      <Time>0:57</Time>
                      <InterCh>+ I-70 I-70</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-70</Direction>
                      <Dist>76.7</Dist>
                      <Time>1:11</Time>
                      <InterCh>+ I-70 Ramp</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>S I-55</Direction>
                      <Dist>8.1</Dist>
                      <Time>0:07</Time>
                      <InterCh>+ I-55 X 10</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BR X 10</Direction>
                      <Dist>1.4</Dist>
                      <Time>0:04</Time>
                      <InterCh>+ X 10 I-255</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>S I-255</Direction>
                      <Dist>17.5</Dist>
                      <Time>0:16</Time>
                      <InterCh>+ I-255 </InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>S I-255</Direction>
                      <Dist>5.4</Dist>
                      <Time>0:05</Time>
                      <InterCh>+ I-255 IL-3</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-255</Direction>
                      <Dist>1.2</Dist>
                      <Time>0:01</Time>
                      <InterCh>+ I-255 I-270</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>N I-270</Direction>
                      <Dist>5.8</Dist>
                      <Time>0:05</Time>
                      <InterCh>+ I-270 X 5B</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BR X 5B</Direction>
                      <Dist>0.7</Dist>
                      <Time>0:02</Time>
                      <InterCh>+ X 5B I-44</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-44</Direction>
                      <Dist>28.6</Dist>
                      <Time>0:25</Time>
                      <InterCh>+ I-44 </InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-44</Direction>
                      <Dist>234.5</Dist>
                      <Time>3:27</Time>
                      <InterCh>+ I-44 US-50</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-44</Direction>
                      <Dist>8.2</Dist>
                      <Time>0:07</Time>
                      <InterCh>+ I-44 I-49</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-44</Direction>
                      <Dist>91.7</Dist>
                      <Time>1:21</Time>
                      <InterCh>+ I-44 X 34</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BR X 34</Direction>
                      <Dist>0.6</Dist>
                      <Time>0:02</Time>
                      <InterCh>+ X 34 I-44</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-44</Direction>
                      <Dist>4.6</Dist>
                      <Time>0:04</Time>
                      <InterCh>+ I-44 </InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-44</Direction>
                      <Dist>15.3</Dist>
                      <Time>0:13</Time>
                      <InterCh>+ I-44 US-412</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-44</Direction>
                      <Dist>86.2</Dist>
                      <Time>1:16</Time>
                      <InterCh>+ I-44 Ramp</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>S I-35</Direction>
                      <Dist>4.1</Dist>
                      <Time>0:04</Time>
                      <InterCh>+ I-35 X 133</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BR X 133</Direction>
                      <Dist>0.1</Dist>
                      <Time>0:00</Time>
                      <InterCh>+ X 133 I-44</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-44</Direction>
                      <Dist>7.7</Dist>
                      <Time>0:07</Time>
                      <InterCh>+ I-44 Ramp</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-44</Direction>
                      <Dist>2.9</Dist>
                      <Time>0:03</Time>
                      <InterCh>+ I-44 X 120A</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BR X 120A</Direction>
                      <Dist>0.2</Dist>
                      <Time>0:01</Time>
                      <InterCh>+ X 120A I-40</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>31.0</Dist>
                      <Time>0:27</Time>
                      <InterCh>+ I-40 </InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>82.2</Dist>
                      <Time>1:13</Time>
                      <InterCh>+ I-40 US-270</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>88.6</Dist>
                      <Time>1:18</Time>
                      <InterCh>+ I-40 OK-34</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>23.2</Dist>
                      <Time>0:20</Time>
                      <InterCh>+ I-40 TX-70</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>12.5</Dist>
                      <Time>0:11</Time>
                      <InterCh>+ I-40 Old US-66</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>14.9</Dist>
                      <Time>0:13</Time>
                      <InterCh>+ I-40 Old US-66</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>79.7</Dist>
                      <Time>1:10</Time>
                      <InterCh>+ I-40 I-40</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>86.9</Dist>
                      <Time>1:17</Time>
                      <InterCh>+ I-40 </InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>20.4</Dist>
                      <Time>0:18</Time>
                      <InterCh>+ I-40 US-54</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>328.2</Dist>
                      <Time>4:50</Time>
                      <InterCh>+ I-40 US-84</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>41.5</Dist>
                      <Time>0:37</Time>
                      <InterCh>+ I-40 AZ-77</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>44.2</Dist>
                      <Time>0:39</Time>
                      <InterCh>+ I-40 AZ-99</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>152.2</Dist>
                      <Time>2:14</Time>
                      <InterCh>+ I-40 US-180</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>53.8</Dist>
                      <Time>0:49</Time>
                      <InterCh>+ I-40 Ramp</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>Str Needles Inspection Station</Direction>
                      <Dist>0.0</Dist>
                      <Time>0:00</Time>
                      <InterCh>+ Needles Inspection Station </InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BL Local roads</Direction>
                      <Dist>0.2</Dist>
                      <Time>0:00</Time>
                      <InterCh>+  Ramp</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>16.5</Dist>
                      <Time>0:18</Time>
                      <InterCh>+ I-40 </InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W I-40</Direction>
                      <Dist>132.3</Dist>
                      <Time>2:24</Time>
                      <InterCh>+ I-40 I-15</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>S I-15</Direction>
                      <Dist>58.6</Dist>
                      <Time>1:04</Time>
                      <InterCh>+ I-15 I-15</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>S I-15</Direction>
                      <Dist>7.8</Dist>
                      <Time>0:09</Time>
                      <InterCh>+ I-15 X 115A</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BR X 115A</Direction>
                      <Dist>1.1</Dist>
                      <Time>0:03</Time>
                      <InterCh>+ X 115A CA-210</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W CA-210</Direction>
                      <Dist>37.6</Dist>
                      <Time>0:41</Time>
                      <InterCh>+ CA-210 CA-134</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W CA-134</Direction>
                      <Dist>4.6</Dist>
                      <Time>0:05</Time>
                      <InterCh>+ CA-134 Ramp</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>S CA-2</Direction>
                      <Dist>5.5</Dist>
                      <Time>0:07</Time>
                      <InterCh>+ CA-2 Ramp</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>N US-101</Direction>
                      <Dist>2.4</Dist>
                      <Time>0:03</Time>
                      <InterCh>+ US-101 X 7</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>BR X 7</Direction>
                      <Dist>0.2</Dist>
                      <Time>0:00</Time>
                      <InterCh>+ X 7 CA-2</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>W CA-2</Direction>
                      <Dist>6.0</Dist>
                      <Time>0:09</Time>
                      <InterCh>+ CA-2 N Beverly Dr</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>R N Beverly Dr</Direction>
                      <Dist>0.7</Dist>
                      <Time>0:01</Time>
                      <InterCh>+ N Beverly Dr Local</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                    <DirectionsReportLine>
                      <Warn i:nil="true" />
                      <Direction>L Local</Direction>
                      <Dist>0.1</Dist>
                      <Time>0:00</Time>
                      <InterCh>Beverly Hills, CA, Beverly Hills, CA 90210</InterCh>
                      <Delay i:nil="true" />
                    </DirectionsReportLine>
                  </ReportLines>
                  <Dest>
                    <Address>
                      <StreetAddress />
                      <City>Beverly Hills</City>
                      <State>CA</State>
                      <Zip>90210</Zip>
                      <County>Los Angeles</County>
                      <Country>United States</Country>
                      <SPLC i:nil="true" />
                      <CountryPostalFilter>US</CountryPostalFilter>
                      <AbbreviationFormat>FIPS</AbbreviationFormat>
                    </Address>
                    <Coords>
                      <Lat>34.079799</Lat>
                      <Lon>-118.412935</Lon>
                    </Coords>
                    <Region>NA</Region>
                    <Label>Beverly Hills, CA</Label>
                    <PlaceName>Beverly Hills, CA</PlaceName>
                    <TimeZone>PDT</TimeZone>
                    <Errors />
                  </Dest>
                </DirectionsReportLeg>
              </ReportLegs>
            </Report>
            <Report i:type="MileageReport">
              <RouteID>Test Route</RouteID>
              <ReportLines>
                <StopReportLine>
                  <Stop>
                    <Address>
                      <StreetAddress />
                      <City>Princeton</City>
                      <State>NJ</State>
                      <Zip>08540</Zip>
                      <County>Mercer</County>
                      <Country>United States</Country>
                      <SPLC i:nil="true" />
                      <CountryPostalFilter>US</CountryPostalFilter>
                      <AbbreviationFormat>FIPS</AbbreviationFormat>
                    </Address>
                    <Coords>
                      <Lat>40.348727</Lat>
                      <Lon>-74.659049</Lon>
                    </Coords>
                    <Region>NA</Region>
                    <Label>Princeton, NJ</Label>
                    <PlaceName>Princeton, NJ</PlaceName>
                    <TimeZone>EDT</TimeZone>
                    <Errors />
                  </Stop>
                  <LMiles>0.0</LMiles>
                  <TMiles>0.0</TMiles>
                  <LCostMile>0.00</LCostMile>
                  <TCostMile>0.00</TCostMile>
                  <LHours>0:00</LHours>
                  <THours>0:00</THours>
                  <LTolls>0.00</LTolls>
                  <TTolls>0.00</TTolls>
                  <LEstghg>0.0</LEstghg>
                  <TEstghg>0.0</TEstghg>
                  <EtaEtd i:nil="true" />
                </StopReportLine>
                <StopReportLine>
                  <Stop>
                    <Address>
                      <StreetAddress />
                      <City>Beverly Hills</City>
                      <State>CA</State>
                      <Zip>90210</Zip>
                      <County>Los Angeles</County>
                      <Country>United States</Country>
                      <SPLC i:nil="true" />
                      <CountryPostalFilter>US</CountryPostalFilter>
                      <AbbreviationFormat>FIPS</AbbreviationFormat>
                      <CountryAbbreviation>US</CountryAbbreviation>
                    </Address>
                    <Coords>
                      <Lat>34.079799</Lat>
                      <Lon>-118.412935</Lon>
                    </Coords>
                    <Region>NA</Region>
                    <Label>Beverly Hills, CA</Label>
                    <PlaceName>Beverly Hills, CA</PlaceName>
                    <TimeZone>PDT</TimeZone>
                    <Errors />
                  </Stop>
                  <LMiles>2758.5</LMiles>
                  <TMiles>2758.5</TMiles>
                  <LCostMile>3558.74</LCostMile>
                  <TCostMile>3558.74</TCostMile>
                  <LHours>42:43</LHours>
                  <THours>42:43</THours>
                  <LTolls>30.22</LTolls>
                  <TTolls>30.22</TTolls>
                  <LEstghg>9450.5</LEstghg>
                  <TEstghg>9450.5</TEstghg>
                  <EtaEtd i:nil="true" />
                </StopReportLine>
              </ReportLines>
              <TrafficDataUsed>false</TrafficDataUsed>
            </Report>
          </Reports>
        </Body>
      </GetReportsResult>
    </GetReportsResponse>
  </s:Body>
</s:Envelope>
```
