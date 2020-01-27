---
title: Create Route Sync
weight: 5
---

Creates a RouteSync message body given a route.

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
    <m:CreateRouteSyncMessage> xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
        <m:Body>
          <m:OutOfRouteDistance>3.14159265358979E0</m:OutOfRouteDistance>
          <m:Compliance>Strict</m:Compliance>
          <m:IsFirstLegManaged>true</m:IsFirstLegManaged>
          <m:ManagedRoute>
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
          </m:ManagedRoute>
        </m:Body>
      </m:Request>
    </m:CreateRouteSyncMessage>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Request Body Elements

Gets or sets the request body which contains specific information associated with creating a RouteSync message body. Represents the request body of a MapRouteRequest allowing the user to control various settings relevant to creating a map.

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
      <td><code>Compliance</code></td>
      <td>An enumeration of OutOfRouteCompliance.
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
              <td><code>Strict</code></td>
              <td>0</td>
              <td>Strict RouteSync of route compliance</td>
            </tr>
            <tr>
              <td><code>Moderate</code></td>
              <td>1</td>
              <td>Moderate RouteSync of route compliance</td>
            </tr>
            <tr>
              <td><code>None</code></td>
              <td>2</td>
              <td>No RouteSync out of route compliance</td>
            </tr>
          </tbody>
        </table>
        <br>
        Usage: <span>Compliance = OutOfRouteCompliance.Moderate</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>IsFirstLegManaged</code></td>
      <td>A boolean value indicating whether or not the first leg of the route is managed. The default is true.
        <br>
        <br>
        Usage: <span>IsFirstLegManaged = "true"</span>
      </td>
      <td>N(default will be sent if not specified)</td>
    </tr>
    <tr>
      <td><code>OutOfRouteDistance</code></td>
      <td>A decimal value. The maximum allowable out of route distance. The default is 0.2 miles.
        <br>
        <br>
        Usage: <span>OutOfRouteDistance = 5</span>
      </td>
      <td>N(default will be sent if not specified)</td>
    </tr>
    <tr>
      <td><code>ManagedRoute</code></td>
      <td>A Route object. Sets the route to create the RouteSync message from an array of routes.
        <br>
        <br>
        Usage: <span>ManagedRoute = route</span>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>Route</code></td>
      <td>A system object. Represents a route and all its associated information from the standpoint of a request either
        mapping or report.
        <br>
        <br>
        Usage: <span>Route route = new Route(){</span>
        <p style="text-indent: 5em;">
          <span>RouteId = "123",</span>
        </p>
        <p style="text-indent: 5em;" class="mb-0"><span>Stops = stops</span></p>
        <p style="text-indent: 4em;" class="mb-0"><span>};</span></p>
      </td>
      <td>Y</td>
    </tr>
  </tbody>
</table>

**Calling CreateRoutesyncMessage**

```js
var stops = new StopLocation[2];
    stops[0] = new StopLocation()
    {
       Address = new Address
       {
         Zip = "19123"
       },
       Region = DataRegion.NA,
       RegionSpecified = true
    };
    stops[1] = new StopLocation()
    {
      Address = new Address
      {
        Zip = "08540"
      },
      Region = DataRegion.NA,
      RegionSpecified = true
    };

    Route route = new  Route()
    {
      RouteId = "123",
      Stops = stops,
      Options = new RouteOptions()
      {
        HighwayOnly = true,
        HighwayOnlySpecified = true,
        BordersOpen = true,
        BordersOpenSpecified = true,
        TollDiscourage = true
      }

    };
    CreateRouteSyncMsgRequestBody routeBody = new CreateRouteSyncMsgRequestBody()
    {
      Compliance = OutOfRouteCompliance.Moderate,
      ComplianceSpecified = true,
      IsFirstLegManaged = true,
      IsFirstLegManagedSpecified = true,
      OutOfRouteDistance = 5,
      OutOfRouteDistanceSpecified = true,
      ManagedRoute = route
    };
    CreateRouteSyncMsgRequest req = new CreateRouteSyncMsgRequest()
    {
      Body = routeBody,
      Header = new RequestHeader()
      {
        DataVersion = DataVersion.ToString(),
        RequestType = "CreateRouteSyncMessage"
      }
    };

    // Create the authentication and authorization header
    AuthHeader soapHeader = GenerateAuthHeader(APIName);

    // Create the service client
    ServiceClient service = new ServiceClient();


    CreateRouteSyncMsgResponse response = service.CreateRouteSyncMessage(soapHeader, req);
```

### Request

Represents a request to draw a map, optionally with routes on it.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">https://pcmiler.alk.com/APIs/v1.0/IService/CreateRouteSyncMessage</Action>
    <h:AuthHeader xmlns="http://www.alk.com" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:h="http://www.alk.com">
      <Authorization>A77097D2D202A743BB1660E15794D7CA</Authorization>
      <Date>Thu, 21 Aug 2014 16:23:26 GMT</Date>
    </h:AuthHeader>
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <CreateRouteSyncMessage xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <Request>
        <Header>
          <DataVersion>current</DataVersion>
          <RequestType>CreateRouteSyncMessage</RequestType>
        </Header>
        <Body>
          <Compliance>Moderate</Compliance>
          <IsFirstLegManaged>true</IsFirstLegManaged>
          <ManagedRoute>
            <RouteId>routeSync</RouteId>
            <Stops>
              <StopLocation>
                <Address>
                  <StreetAddress xsi:nil="true" />
                  <City xsi:nil="true" />
                  <State xsi:nil="true" />
                  <Zip>19123</Zip>
                  <County xsi:nil="true" />
                  <Country xsi:nil="true" />
                  <SPLC xsi:nil="true" />
                </Address>
                <Coords xsi:nil="true" />
                <Region>NA</Region>
                <Label xsi:nil="true" />
                <PlaceName xsi:nil="true" />
                <Costs xsi:nil="true" />
              </StopLocation>
              <StopLocation>
                <Address>
                  <StreetAddress xsi:nil="true" />
                  <City xsi:nil="true" />
                  <State xsi:nil="true" />
                  <Zip>08540</Zip>
                  <County xsi:nil="true" />
                  <Country xsi:nil="true" />
                  <SPLC xsi:nil="true" />
                </Address>
                <Coords xsi:nil="true" />
                <Region>NA</Region>
                <Label xsi:nil="true" />
                <PlaceName xsi:nil="true" />
                <Costs xsi:nil="true" />
              </StopLocation>
            </Stops>
            <Options>
              <BordersOpen>true</BordersOpen>
              <HighwayOnly>true</HighwayOnly>
              <TruckCfg xsi:nil="true" />
            </Options>
            <FuelOptions xsi:nil="true" />
            <AFOptions xsi:nil="true" />
          </ManagedRoute>
        </Body>
      </Request>
    </CreateRouteSyncMessage>
  </s:Body>
</s:Envelope>
```

### Response

Represents the output response for generating a Routesync message. The CreateRouteSyncMsgResponse Body gets or sets the response body which contains the RouteSync message bytes. Represents the request body of the CreateRouteSyncMsgResponse encapsulating the RouteSync message bytes.

**CreateRouteSyncResponseBody Members**

| Element        | Definition                                                |
| -------------- | --------------------------------------------------------- |
| `MessageBytes` | A byte[] value. Gets or sets the RouteSync message bytes. |

**Sample response**

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header />
  <s:Body>
    <CreateRouteSyncMessageResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <CreateRouteSyncMessageResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>CreateRouteSyncMessage</Type>
          <Success>true</Success>
          <DataVersion>28.0.24.5492</DataVersion>
          <Errors />
        </Header>
        <Body>
          <MessageBytes>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</MessageBytes>
        </Body>
      </CreateRouteSyncMessageResult>
    </CreateRouteSyncMessageResponse>
  </s:Body>
</s:Envelope>
```
