---
title: Reduce Trip
weight: 10
---

The ReduceTrip operation will return a trip based upon a series of latitude/longitudes pings. The Reduce trip operation will return either Mileage or detailed report for the route.

Schema

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SOAP-ENV:Header>
    <m:AuthHeader xmlns:m="http://www.alk.com">
      <m:Authorization>String</m:Authorization>
      <m:Date>String</m:Date>
    </m:AuthHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <m:ReduceTrip xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
        <m:Body>
          <m:HighwayOnly>true</m:HighwayOnly>
          <m:OffRouteMiles>3.14159265358979E0</m:OffRouteMiles>
          <m:Region>Unknown</m:Region>
          <m:ReportType/>
          <m:RoutePings>
            <m:Coordinates>
              <m:Lat>String</m:Lat>
              <m:Lon>String</m:Lon>
            </m:Coordinates>
          </m:RoutePings>
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
        </m:Body>
      </m:Request>
    </m:ReduceTrip>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### ReduceTrip Request

Represents a ReduceTripRequest structure which contains the request header and reduce trip request body.

**Request Body Members**

Gets or sets the reduce trip request body.

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
      <td><code>HighwayOnly</code></td>
      <td>
        A Boolean value. Gets or sets a value indicating whether to use highway only routing. This value will be ignored if RoutingOptions are supplied.
        <br />
        Usage:<span>HighwayOnly = true;</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>OffRouteMiles</code></td>
      <td>
        A double value. Gets or sets the value indicating the off route miles for the route.
        <br />
        Usage:<span>OffRouteMiles = 0;</span>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>Region</code></td>
      <td>
        An enumeration of DataRegion. Gets or sets the region of the pings.
        <br />
        Usage:<span>region = DataRegion.NA; </span>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>ReportType</code></td>
      <td>
        A <a href="/soap-apis/docs/reports/get-reports/#mileage-report-type">MileageReportType</a> or <a href="/soap-apis/docs/reports/get-reports/#the-detailedreporttype">DetailedReportType</a> object. Gets or sets the request report type.
        <br />
        Usage:<span>ReportType = new DetailReportType();</span>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>RoutePings</code></td>
      <td>
        A list&lt;&gt; of Coordinates system object. Gets or sets the collection of coordinates used to specify the pings along the route.
        <br />
        Usage: <span>Coordinates[] coords = new Coordinates[2];</span>
        <p style="text-indent: 4em;" class="mb-0">coord[0] = new Coordinates()</p>
        <p style="text-indent: 4em;" class="mb-0">{</p>
        <p style="text-indent: 5em;" class="mb-0">Lat = "42149700", // NYC</p>
        <p style="text-indent: 5em;" class="mb-0">Lon = "-74938400"</p>
        <p style="text-indent: 4em;" class="mb-0">};</p>
        <p style="text-indent: 4em;" class="mb-0">coord[1] = new Coordinates()</p>
        <p style="text-indent: 4em;" class="mb-0">{</p>
        <p style="text-indent: 5em;" class="mb-0">Lat = "40348727", // Princeton</p>
        <p style="text-indent: 5em;" class="mb-0">Lon = "-74659049"</p>
        <p style="text-indent: 4em;" class="mb-0">};</p>
        <p style="text-indent: 4em;" class="mb-0">RoutePings=coords</p>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>RoutingOptions</code></td>
      <td>
        A RoutingOptions system object. Gets or sets the route options. If this is supplied the HighwayOnly property will be ignored.
        <br />
        Usage: <span>RoutingOptions = new RouteOptions()</span>
        <p style="text-indent: 4em;" class="mb-0">{</p>
        <p style="text-indent: 5em;" class="mb-0">BordersOpen = false,</p>
        <p style="text-indent: 5em;" class="mb-0">ClassOverrides = ClassOverrideType .FiftyThreeFoot ,</p>
        <p style="text-indent: 5em;" class="mb-0">RouteOptimization = RouteOptimizeType.DestinationFixed</p>
        <p style="text-indent: 4em;" class="mb-0">}</p>
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

#### Calling ReduceTrip

```js
// Create coordinates
Coordinates[] coords = new Coordinates[2];
coords[0] = new Coordinates()
{
    Lat = "42149700", // NYC
    Lon = "-74938400"
};

coords[1] = new Coordinates()
{
    Lat = "40348727", // Princeton
    Lon = "-74659049"
};

// Create the request
ReduceTripRequest request = new ReduceTripRequest()
{
    Body = new ReduceTripRequestBody()
    {
        //Coordinates = (new List<Coordinates>() { b1, b2 }).ToArray(),
        RoutePings = coords,
        ReportType = new DetailReportType(),
        HighwayOnly = true,
        OffRouteMiles = 0,
        Region = DataRegion.NA,
        RoutingOptions = new RouteOptions()
        {
            BordersOpen = false,
            BordersOpenSpecified = true,
            ClassOverrides = ClassOverrideType .FiftyThreeFoot ,
            ClassOverridesSpecified = true,
            RouteOptimization = RouteOptimizeType.DestinationFixed,
            RouteOptimizationSpecified = true
        }
    },
    Header = new RequestHeader() { DataVersion =  DataVersion.ToString(), RequestType = "Reduce Trip" }
};

// Create the authentication and authorization header
AuthHeader soapHeader =  GenerateAuthHeader( APIName);

// Create the service client
ServiceClient service = new ServiceClient();

// Call API
ReportResponse response = service.ReduceTrip(soapHeader, request);
```

### Request

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">https://pcmiler.alk.com/APIs/v1.0/IService/ReduceTrip</Action>
    <h:AuthHeader xmlns="http://www.alk.com" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:h="http://www.alk.com">
      <Authorization>A77097D2D202A743BB1660E15794D7CA</Authorization>
      <Date>Tue, 24 Feb 2015 21:34:46 GMT</Date>
    </h:AuthHeader>
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ReduceTrip xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <Request>
        <Header>
          <DataVersion>current</DataVersion>
          <RequestType>Reduce Trip</RequestType>
        </Header>
        <Body>
          <ReportType xsi:type="DetailReportType" />
          <RoutePings>
            <Coordinates>
              <Lat>42149700</Lat>
              <Lon>-74938400</Lon>
            </Coordinates>
            <Coordinates>
              <Lat>40348727</Lat>
              <Lon>-74659049</Lon>
            </Coordinates>
          </RoutePings>
          <RoutingOptions>
            <BordersOpen>false</BordersOpen>
            <ClassOverrides>FiftyThreeFoot</ClassOverrides>
            <RouteOptimization>DestinationFixed</RouteOptimization>
            <TruckCfg xsi:nil="true" />
          </RoutingOptions>
        </Body>
      </Request>
    </ReduceTrip>
  </s:Body>
</s:Envelope>
```

### Response

Represents a ReportResponse structure containing the response header and report response body.

#### ReportResponseBody Members

Gets or sets the report response body.

| Element      | Definition                                                                                     |
| ------------ | ---------------------------------------------------------------------------------------------- |
| `ReportType` | A MileageReportType or DetailedReportType object. Gets or sets a collection of Report objects. |

#### Sample Response

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <ReduceTripResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <ReduceTripResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>Reduce Trip</Type>
          <Success>true</Success>
          <DataVersion>28.3.26.9224</DataVersion>
          <Errors />
        </Header>
        <Body>
          <Reports>
            <Report i:type="MileageReport">
              <RouteID i:nil="true" />
              <ReportLines>
                <StopReportLine>
                  <Stop>
                    <Address>
                      <StreetAddress />
                      <City>Walton</City>
                      <State>NY</State>
                      <Zip />
                      <County>Delaware</County>
                      <Country i:nil="true" />
                      <SPLC i:nil="true" />
                      <CountryPostalFilter>US</CountryPostalFilter>
                      <AbbreviationFormat>FIPS</AbbreviationFormat>
                      <CountryAbbreviation>US</CountryAbbreviation>
                    </Address>
                    <Coords>
                      <Lat>42.1497</Lat>
                      <Lon>-74.9384</Lon>
                    </Coords>
                    <Region>NA</Region>
                    <Label />
                    <PlaceName />
                    <TimeZone i:nil="true" />
                    <Errors i:nil="true" />
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
                      <City>Westminster Choir Clg</City>
                      <State>NJ</State>
                      <Zip />
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
                    <TimeZone i:nil="true" />
                    <Errors i:nil="true" />
                  </Stop>
                  <LMiles>173.1</LMiles>
                  <TMiles>173.1</TMiles>
                  <LCostMile>238.92</LCostMile>
                  <TCostMile>238.92</TCostMile>
                  <LHours>3:07</LHours>
                  <THours>3:07</THours>
                  <LTolls>3.50</LTolls>
                  <TTolls>3.50</TTolls>
                  <LEstghg>592.9</LEstghg>
                  <TEstghg>592.9</TEstghg>
                  <EtaEtd i:nil="true" />
                </StopReportLine>
              </ReportLines>
              <TrafficDataUsed>false</TrafficDataUsed>
            </Report>
          </Reports>
        </Body>
      </ReduceTripResult>
    </ReduceTripResponse>
  </s:Body>
</s:Envelope>
```
