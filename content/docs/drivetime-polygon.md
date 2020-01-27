---
title: DriveTime Polygon
weight: 11
---

Generate a polygon of possible travel location within a given time.

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SOAP-ENV:Header>
    <m:AuthHeader xmlns:m="http://www.alk.com">
      <m:Authorization>String</m:Authorization>
      <m:Date>String</m:Date>
    </m:AuthHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <m:GenerateDriveTimePolygon xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
        <m:Body>
          <m:Center>
            <m:Lat>String</m:Lat>
            <m:Lon>String</m:Lon>
          </m:Center>
          <m:Minutes>0</m:Minutes>
          <m:RouteOptions>
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
          </m:RouteOptions>
          <m:Region>Unknown</m:Region>
        </m:Body>
      </m:Request>
    </m:GenerateDriveTimePolygon>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### DriveTimePolygon Request

Represents a request to get drive times.

#### Request Body Members

Gets or sets the request body which contains specific information associated with creating a DriveTimePolygonRequestBody. Represents the request body of a DriveTimePolygonRequest allowing the user to control various settings relevant to creating a map.

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
      <td>A coordinates system object. Gets or sets the Center.
        <br>
          Usage:<br>
          <code>Center = new Coordinates()<br>
          {<br>
            Lat = "42149700", // NYC<br>
            Lon = "-74938400"<br>
          }</code>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>Minutes</code></td>
      <td>An integer value. Gets or sets the minutes.
        <br>
          Usage: <code>Minutes = 10;</code>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>Region</code></td>
      <td>An enumeration of DataRegion. Gets or sets the region in which the Center resides.
             <br>
             Usage: <code>Region = DataRegion.NA;</code>
         </td>
         <td>Y</td>
    </tr>
    <tr>
      <td><code>RouteOptions</code></td>
      <td>A RouteOptions object.  Gets or sets the route options.
             <br>
             Usage:<br>
             <code>RouteOptions = new RouteOptions()<br>
             {<br>
              BordersOpen = true,<br>
              TollDiscourage = true,<br>
              TollDiscourageSpecified = true,<br>
              HighwayOnly = true,<br>
             }</code>
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

#### Calling GenerateDriveTimePolygon

```js
DriveTimePolygonRequest request = new DriveTimePolygonRequest();
request.Header = new RequestHeader()
{
    DataVersion =  DataVersion.ToString(),
    RequestType = "DriveTimePolygonRequest"
};
GenerateDriveTimePolygonRequest driveTimePoly = new GenerateDriveTimePolygonRequest()
{
    Request = request
};
request.Body = new DriveTimePolygonRequestBody()
{
    Center = new Coordinates()
    {
        Lat = "42149700", // NYC
        Lon = "-74938400"
    },

    Minutes = 10,
    MinutesSpecified = true,
    Region = DataRegion.NA,
    RegionSpecified = true,
    RouteOptions = new RouteOptions()
    {
        BordersOpen = true,
        TollDiscourage = true,
        TollDiscourageSpecified = true,
        HighwayOnly = true,
        HighwayOnlySpecified = true
    }
};
// Create the authentication and authorization header
AuthHeader soapHeader = this.Caller.GenerateAuthHeader(APIName);

// Create the service client
ServiceClient service = new ServiceClient();

// Call API
DriveTimePolygonResponse response = service.GenerateDriveTimePolygon(soapHeader, request);
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
  <GenerateDriveTimePolygon xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <Request>
        <Header>
          <DataVersion>current</DataVersion>
          <RequestType>DriveTimePolygonRequest</RequestType>
        </Header>
        <Body>
          <Center>
            <Lat>42149700</Lat>
            <Lon>-74938400</Lon>
          </Center>
          <Minutes>10</Minutes>
          <RouteOptions>
            <HighwayOnly>true</HighwayOnly>
            <TollDiscourage>true</TollDiscourage>
            <TruckCfg xsi:nil="true" />
          </RouteOptions>
          <Region>NA</Region>
        </Body>
      </Request>
    </GenerateDriveTimePolygon></s:Body>
</s:Envelope>
```

### Response

Represents the output response to a request for generating DriveTimes.

#### RoadSpeedsResponseBody Members

Gets or sets the custom place response body which contains the custom places that were requested.

| Element         | Definition                                                                  |
| --------------- | --------------------------------------------------------------------------- |
| `PolygonPoints` | A list <> of coordinates system object. Gets or sets the Coordinates array. |

#### Sample Response

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header />
  <s:Body>
    <GenerateDriveTimePolygonResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <GenerateDriveTimePolygonResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>DriveTimePolygonRequest</Type>
          <Success>true</Success>
          <DataVersion>28.3.26.9224</DataVersion>
          <Errors />
        </Header>
        <Body>
          <PolygonPoints>
            <Coordinates>
              <Lat>42.167703</Lat>
              <Lon>-75.128571</Lon>
            </Coordinates>
            <Coordinates>
              <Lat>42.167703</Lat>
              <Lon>-75.128571</Lon>
            </Coordinates>
            <Coordinates>
              <Lat>42.167703</Lat>
              <Lon>-75.128571</Lon>
            </Coordinates>
            <Coordinates>
              <Lat>42.167703</Lat>
              <Lon>-75.128571</Lon>
            </Coordinates>
          </PolygonPoints>
        </Body>
      </GenerateDriveTimePolygonResult>
    </GenerateDriveTimePolygonResponse>
  </s:Body>
</s:Envelope>
```
