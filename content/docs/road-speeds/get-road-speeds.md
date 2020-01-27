---
title: Get Road Speeds
weight: 3
---

The GetRoadSpeeds operation allows the user to retrieve stored road speeds. The roadspeeds are for different road classes within a state. The GetRoadSpeeds operation returns a collection of RoadSpeed objects, where each item contains the state name, the road type/class, and the roadspeed value.

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
    <m:GetRoadSpeeds xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
        <m:Body>
          <m:Jurisdiction>String</m:Jurisdiction>
          <m:AbbreviationFormat>String</m:AbbreviationFormat>
          <m:Vehicle>String</m:Vehicle>
          <m:Region>String</m:Region>
        </m:Body>
      </m:Request>
    </m:GetRoadSpeeds>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### RoadSpeeds Request

**Request Body Members**

Represents a RoadSpeedsRequest structure containing the request header and the road speed request body.

| Element              | Definition                                                                                                                                                                                         | Required |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `Jurisdiction`       | A string value. The jurisdiction (state within NA and country outside NA) abbreviation for retrieval of road speed data.<br>Usage: Jurisdiction = "NJ"                                             | Y        |
| `AbbreviationFormat` | An enumeration value. The country abbreviation format for use outside NA. Default is FIPS.<br>Usage: AbbreviationFormat = CountryAbbreviationType.ISO2                                             | N        |
| `Vehicle`            | An enumeration value. The Vehicle type, either Auto or Truck for which to retrieve road speeds. Default is Truck.<br>Usage: Vehicle = VehicleType.Auto                                             | N        |
| `Region`             | An enumeration value. The Region which is only required when sending country abbreviations against the WorldWide Data. Default is the default region of the data.<br>Usage: Region = DataRegion.EU | N        |

**Calling Get RoadSpeeds**

```js
RoadSpeedsRequest request = new RoadSpeedsRequest();
  request.Header = new  RequestHeader() { DataVersion =  DataVersion.ToString(), RequestType = "GetRoadSpeeds" };
  // construct body - NJ roads
  request.Body = new RoadSpeedsRequestBody();
  request.Body.Jurisdiction = "NJ";
  request.Body.Vehicle = VehicleType.Auto;

  // Create the authentication and authorization header
  AuthHeader soapHeader =  GenerateAuthHeader( APIName);

  // Create the service client
  ServiceClient service = new ServiceClient();

  // Call API
  RoadSpeedsResponse response = service.GetRoadSpeeds(soapHeader, request);
```

### Request

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
     <h:AuthHeader xmlns="http://www.alk.com" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:h="http://www.alk.com">
      <Authorization>YOUR API KEY HERE</Authorization>
      <Date>Tue, 02 Sep 2014 17:26:01 GMT</Date>
    </h:AuthHeader>
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <GetRoadSpeeds xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <Request>
        <Header>
          <DataVersion>current</DataVersion>
          <RequestType>GetRoadSpeeds</RequestType>
        </Header>
        <Body>
          <Jurisdiction>NJ</Jurisdiction>
          <AbbreviationFormat>FIPS</AbbreviationFormat>
          <Vehicle>Auto</Vehicle>
          <Region>NA</Region>
        </Body>
      </Request>
    </GetRoadSpeeds>
  </s:Body>
</s:Envelope>
```

### Response

Represents a RoadSpeedResponseBody containing a collection of road speed data that was requested by the user. RoadSpeedResponse body represents a request body structure containing the state name for retrieval of road speed data.

**RoadSpeedsResponseBody Members.**

| Element      | Definition                                                                                                |
| ------------ | --------------------------------------------------------------------------------------------------------- |
| `RoadSpeeds` | Gets or sets the collection of RoadSpeed objects containing the road speeds for the different road types. |

**RoadSpeed Response Members**

Represents a road speed for a type of road and state.

| Element        | Definition                                                                                                |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| `RoadCategory` | An enumeration of RoadType. Gets or sets the type of road.                                                |
| `Speed`        | An Integer value. The speed of the road in miles per hour.                                                |
| `Jurisdiction` | A string value. The jurisdiction abbreviation (state within NA and country elsewhere) for the road speed. |

**Sample Response**

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <GetRoadSpeedsResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <GetRoadSpeedsResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>GetRoadSpeeds</Type>
          <Success>true</Success>
          <DataVersion>31.4.43.5012</DataVersion>
          <Errors i:nil="true" />
        </Header>
        <Body>
          <RoadSpeeds>
            <RoadSpeed>
              <RoadCategory>InterStateRural</RoadCategory>
              <Speed>65</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </RoadSpeed>
            <RoadSpeed>
              <RoadCategory>DividedRural</RoadCategory>
              <Speed>45</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </RoadSpeed>
            <RoadSpeed>
              <RoadCategory>PrimaryRural</RoadCategory>
              <Speed>30</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </RoadSpeed>
            <RoadSpeed>
              <RoadCategory>FerriesRural</RoadCategory>
              <Speed>15</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </RoadSpeed>
            <RoadSpeed>
              <RoadCategory>SecondaryRural</RoadCategory>
              <Speed>25</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </RoadSpeed>
            <RoadSpeed>
              <RoadCategory>LocalRural</RoadCategory>
              <Speed>18</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </RoadSpeed>
            <RoadSpeed>
              <RoadCategory>InterStateUrban</RoadCategory>
              <Speed>55</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </RoadSpeed>
            <RoadSpeed>
              <RoadCategory>DividedUrban</RoadCategory>
              <Speed>31</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </RoadSpeed>
            <RoadSpeed>
              <RoadCategory>PrimaryUrban</RoadCategory>
              <Speed>25</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </RoadSpeed>
            <RoadSpeed>
              <RoadCategory>FerriesUrban</RoadCategory>
              <Speed>15</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </RoadSpeed>
            <RoadSpeed>
              <RoadCategory>SecondaryUrban</RoadCategory>
              <Speed>16</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </RoadSpeed>
            <RoadSpeed>
              <RoadCategory>LocalUrban</RoadCategory>
              <Speed>12</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </RoadSpeed>
          </RoadSpeeds>
        </Body>
      </GetRoadSpeedsResult>
    </GetRoadSpeedsResponse>
  </s:Body>
</s:Envelope>
```
