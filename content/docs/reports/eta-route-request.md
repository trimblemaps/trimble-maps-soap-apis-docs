---
title: Get ETA OOR
weight: 3
---

The GetETAOutOfRouteReport operation returns the out of route(Oor) mileage and estimated time of arrival(ETA) given a collection of out of route locations, for a defined route.

**Schema**

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SOAP-ENV:Header>
    <m:AuthHeader xmlns:m="http://www.alk.com">
      <m:Authorization>String</m:Authorization>
      <m:Date>String</m:Date>
    </m:AuthHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <m:GetETAOutOfRouteReport xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
        <m:Body>
          <m:RouteID>String</m:RouteID>
          <m:Origin>
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
          </m:Origin>
          <m:Destination>
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
          </m:Destination>
          <m:CurrentLocations>
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
          </m:CurrentLocations>
          <m:RoutingOptions>
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
          </m:RoutingOptions>
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
        </m:Body>
      </m:Request>
    </m:GetETAOutOfRouteReport>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### ETAOutOfRoute Request

#### Request Body Elements

Represents a request to perform out of route mileage and estimated time of arrival from supplied current locations for a defined route. Request body gets or sets the body of the request which contains information needed to perform the operation.

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
      <td><code>CurrentLocations</code></td>
      <td>
        A list &lt;&gt; of StopLocation object. Gets or sets a collection of StopLocation objects each of which represent the truck's current location.
        <br />
        <br />
        Usage:<span>List&lt;StopLocation&gt; oorStops = new List&lt;StopLocation&gt;();</span>
        <p style="text-indent: 4em;" class="mb-0"><span>StopLocation loc = new StopLocation()</span></p>
        <p style="text-indent: 4em;" class="mb-0"><span>{ Coord = new Coordinates { Lat ="40353828", Lon="-74610884" } };</span></p>
        <p style="text-indent: 4em;" class="mb-0"><span>oorStops.Add(loc);</span></p>
        <p style="text-indent: 4em;" class="mb-0"><span>CurrentLocation = oorStops.ToArrat();</span></p>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>Destination</code></td>
      <td>
        A StopLocation object. Gets or sets the trip's destination.
        <br />
        <br />
        Usage:<span>StopLocation tripDest = new StopLocation() { Address = new Address() };</span>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>Origin</code></td>
      <td>
        A StopLocation object. Gets or sets the trip's origin.
        <br />
        <br />
        Usage:<span>StopLocation tripOrigin = new StopLocation() { Address = new Address() };</span>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>ReportingOptions</code></td>
      <td>
        A ReportOptions object. Gets or sets the reporting options used in creating the output data.
        <br />
        <br />
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
      <td><code>RouteID</code></td>
      <td>
        A string value. Gets or sets a unique identifier for the route which will be visible in the output report generated. Inherited from Route.
        <br />
        <br />
        Usage:<span>RouteID = "ETA Out of Route Report Test";</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>RoutingOptions</code></td>
      <td>
        A RouteOptions object. Gets or sets the routing options for the route calculations.
        <br />
        <br />
        Usage:<span>RouteOptions tripOption = new RouteOptions()</span>
        <p style="text-indent: 4em;" class="mb-0"><span>{</span></p>
        <p style="text-indent: 5em;" class="mb-0"><span>HighwayOnly = true,</span></p>
        <p style="text-indent: 5em;" class="mb-0"><span>HighwayOnlySpecified = true,</span></p>
        <p style="text-indent: 5em;" class="mb-0"><span>VehicleType = VehicleType.LightTruck,</span></p>
        <p style="text-indent: 5em;" class="mb-0"><span>VehicleTypeSpecified = true,</span></p>
        <p style="text-indent: 5em;" class="mb-0"><span>ClassOverrides = ClassOverridesType.FiftyThreeFoot,</span></p>
        <p style="text-indent: 5em;" class="mb-0"><span>ClassOverridesSpecified = True,</span></p>
        <p style="text-indent: 4em;" class="mb-0"><span>};</span></p>
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

#### Calling ETA OOR Report

```js
StopLocation tripOrigin = new StopLocation() { Address = new Address() };
      StopLocation tripDest = new StopLocation() { Address = new Address() };
      tripOrigin.Address.City = "Princeton";
      tripOrigin.Address.Zip = "08540";
      tripOrigin.Region = DataRegion.NA;
      tripOrigin.RegionSpecified = true;

      tripDest.Address.City = "Monmouth Junction";
      tripDest.Address.Zip = "08852";
      tripDest.Region = DataRegion.NA;
      tripDest.RegionSpecified = true;

      Coordinates coords = new Coordinates()
      {
          Lat = "40353828",
          Lon = "-74610884"
      };
      StopLocation[] loc = new StopLocation[2] ;
      loc[0] = new StopLocation() { Coords = new Coordinates() { Lat = "40353828", Lon = "74610884" } };
      loc[1] = new StopLocation() {Address = new Address() {Zip = "19123"}, Region = DataRegion.NA, RegionSpecified = true};

      // Set route options
      RouteOptions tripOption = new RouteOptions();
      tripOption.HighwayOnly = true;
      tripOption.HighwayOnlySpecified = true;
      tripOption.VehicleType = VehicleType.LightTruck;
      tripOption.VehicleTypeSpecified = true;
      tripOption.ClassOverrides = ClassOverrideType.FiftyThreeFoot;

      ReportOptions repOption = new ReportOptions()
      {
          EstimatedTimeOptions = timeOpts,
          ExchangeRate = 1.5,
          ExchangeRateSpecified = true,
          FuelUnits = VolumeUnits.Gallons,
          FuelUnitsSpecified = true,
          IncludeFerryDistance = true,
          IncludeFerryDistanceSpecified = true,
          Language = LanguageType.DE,
          LanguageSpecified = true,
          RouteCosts =routeCosts,
          TimeCosts = timeCosts,
          TollCurrency = Currency.US,
          TollCurrencySpecified = true,
          TollDiscount = "All",
          UseCustomRoadSpeeds = false,
          UseCustomRoadSpeedsSpecified =true,
          UseTollData = true,
          UseTollDataSpecified = true,
      };

      // Create the request
      ETAOutOfRouteRequestBody body = new ETAOutOfRouteRequestBody();
      body.RouteID = "ETA Out of Route Report Test";
      body.Origin = tripOrigin;
      body.Destination = tripDest;
      body.CurrentLocations = loc;
      body.ReportingOptions = repOption;
      body.RoutingOptions = tripOption;

      ETAOutOfRouteRequest request = new ETAOutOfRouteRequest()
      {
          Header = new RequestHeader() { DataVersion =  DataVersion.ToString(), RequestType = "GetETAOutOfRouteReport" },
          Body = body
      };
      // Create the authentication and authorization header
      AuthHeader soapHeader =  GenerateAuthHeader(APIName);
      // Create the service client
      ServiceClient service = new  ServiceClient();

      // Call API
      ReportResponse response = service.GetETAOutOfRouteReport(soapHeader, request);
```

### Request

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
   <h:AuthHeader xmlns="http://www.alk.com" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:h="http://www.alk.com">
      <Authorization>A77097D2D202A743BB1660E15794D7CA</Authorization>
      <Date>Wed, 10 Sep 2014 19:35:41 GMT</Date>
    </h:AuthHeader>
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <GetETAOutOfRouteReport xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <Request>
        <Header>
          <DataVersion>current</DataVersion>
          <RequestType>GetETAOutOfRouteReport</RequestType>
        </Header>
        <Body>
          <RouteID>ETA Out of Route Report Test</RouteID>
          <Origin>
            <Address>
              <City>Princeton</City>
              <Zip>08540</Zip>
            </Address>
            <Region>NA</Region>
          </Origin>
          <Destination>
            <Address>
              <City>Monmouth Junction</City>
              <Zip>08852</Zip>
             </Address>
             <Region>NA</Region>
            <Costs>
              <CostOfStop>5</CostOfStop>
              <HoursPerStop>1</HoursPerStop>
              <Loaded>true</Loaded>
              <OnDuty>true</OnDuty>
              <UseOrigin>false</UseOrigin>
            </Costs>
          </Destination>
          <CurrentLocations>
            <StopLocation>
              <Coords>
                <Lat>40353828</Lat>
                <Lon>-74610884</Lon>
              </Coords>
            </StopLocation>
            <StopLocation>
              <Address>
                <Zip>19123</Zip>
              </Address>
              <Region>NA</Region>
            </StopLocation>
          </CurrentLocations>
          <RoutingOptions>
            <ClassOverrides>FiftyThreeFoot</ClassOverrides>
            <HighwayOnly>true</HighwayOnly>
            <TruckCfg xsi:nil="true" />
            <VehicleType>LightTruck</VehicleType>
          </RoutingOptions>
          <ReportingOptions>
            <EstimatedTimeOptions>
              <ETAETD>Arrival</ETAETD>
              <DateOption>Specific</DateOption>
              <DateAndTime>
                <CalendarDate>10/10/2014</CalendarDate>
                <DayOfWeek>Friday</DayOfWeek>
                <TimeOfDay>12:00</TimeOfDay>
                <TimeZone>Eastern</TimeZone>
              </DateAndTime>
            </EstimatedTimeOptions>
            <ExchangeRate>1.5</ExchangeRate>
            <FuelUnits>Gallons</FuelUnits>
            <IncludeFerryDistance>true</IncludeFerryDistance>
            <Language>DE</Language>
            <RouteCosts>
              <CostTimeEmpty>5</CostTimeEmpty>
              <CostTimeLoaded>15</CostTimeLoaded>
              <FuelEconomyEmpty>1</FuelEconomyEmpty>
              <FuelEconomyLoaded>16</FuelEconomyLoaded>
              <GreenHouseGas>1</GreenHouseGas>
              <OtherCostPerDistUnitLoaded>2</OtherCostPerDistUnitLoaded>
              <OtherCostPerDistanceUnitEmpty>5</OtherCostPerDistanceUnitEmpty>
              <PricePerFuelUnit>3.95</PricePerFuelUnit>
              <TruckStyle>FiftyThreeSemiTrailer</TruckStyle>
            </RouteCosts>
            <TollCurrency>US</TollCurrency>
            <TollDiscount>All</TollDiscount>
            <UseCustomRoadSpeeds>false</UseCustomRoadSpeeds>
            <UseTollData>true</UseTollData>
            <UseTraffic>true</UseTraffic>
          </ReportingOptions>
        </Body>
      </Request>
    </GetETAOutOfRouteReport>
  </s:Body>
</s:Envelope>
```

### Response

Represents an ETA Out of Route report which presents information related to out of route stops.

#### ETAOutOfRouteReport Response Body Members

| Element       | Definition                                                                                            |
| ------------- | ----------------------------------------------------------------------------------------------------- |
| `Destination` | A GeocodeOutputLocation object. Gets or sets the trip's destination.                                  |
| `Origin`      | A GeocodeOutputLocation object. Gets or sets the trip's origin.                                       |
| `ReportLines` | A list of <OutOfRouteReportLine> objects. Gets or sets the report lines for the report.               |
| `Destination` | Gets or sets the unique route identifier that was supplied during the request.(Inherited from Report) |

#### OutOfRouteReportLine Members

| Element           | Definition                                                                                                                                      |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| `CurrentLocation` | A GeocodeOutputLocation object. Gets or sets the geocoded output location containing the address information of the vehicle's current position. |
| `LCostMile`       | A string value. Gets or sets the leg cost per mile.                                                                                             |
| `LHours`          | A string value. Gets or sets the leg hours.                                                                                                     |
| `LMiles`          | A string value. Gets or sets the leg miles.                                                                                                     |
| `LTolls`          | A string value. Gets or sets the leg tolls.                                                                                                     |
| `OORMILE`         | A string value. Gets or sets the estimated out-of-route miles.                                                                                  |
| `TCostMile`       | A string value. Gets or sets the total cost per mile.                                                                                           |
| `THours`          | A string value. Gets or sets the total hours.                                                                                                   |
| `TMiles`          | A string value. Gets or sets the total miles.                                                                                                   |
| `TTolls`          | A string value. Gets or sets the total tolls.                                                                                                   |

#### Sample Response

````xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header />
  <s:Body>
    <GetETAOutOfRouteReportResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <GetETAOutOfRouteReportResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>GetETAOutOfRouteReport</Type>
          <Success>true</Success>
          <DataVersion>28.0.24.5492</DataVersion>
          <Errors />
        </Header>
        <Body>
          <Reports>
            <Report i:type="ETAOutOfRouteReport">
              <RouteID>ETA Out of Route Report Test</RouteID>
              <Origin>
                <Address>
                  <StreetAddress />
                  <City>Princeton</City>
                  <State>NJ</State>
                  <Zip>08540</Zip>
                  <County>Mercer</County>
                  <Country i:nil="true" />
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
                <Label />
                <PlaceName />
                ```
````
