---
title: Road Speeds
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
            <td><code>Jurisdiction</code></td>
            <td>
              A string value. The jurisdiction (state within NA and country outside NA) abbreviation for retrieval of road speed data.
              <br>
              <br>
              Usage: <span>Jurisdiction = "NJ"</span>
            </td>
            <td>Y</td>
          </tr>
          <tr>
            <td><code>AbbreviationFormat</code></td>
            <td>
              An enumeration value. The country abbreviation format for use outside NA.  Default is FIPS.
              <br>
              <br>
              Usage: <span>AbbreviationFormat = CountryAbbreviationType.ISO2</span>
            </td>
            <td>N</td>
          </tr>
          <tr>
            <td><code>Vehicle</code></td>
            <td>
              An enumeration value. The Vehicle type, either Auto or Truck for which to retrieve road speeds.  Default is Truck.
              <br>
              <br>
              Usage: <span>Vehicle = VehicleType.Auto</span>
            </td>
            <td>N</td>
          </tr>
          <tr>
            <td><code>Region</code></td>
            <td>
              An enumeration value. The Region which is only required when sending country abbreviations against the WorldWide Data.  Default is the default region of the data.
              <br>
              <br>
              Usage: <span>Region = DataRegion.EU</span>
            </td>
            <td>N</td>
          </tr>
</tbody>
</table>

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
