---
title: About
description: "The AboutService operation returns the version of PC*MILER Web Services"
weight: 2
---

The AboutService operation returns the version of PC\*MILER Web Services.

#### Schema

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SOAP-ENV:Header>
    <m:AuthHeader xmlns:m="http://www.alk.com">
      <m:Authorization>String</<m:Authorization>
      <m:Date>String</m:Date>
    </m:AuthHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <m:AboutService xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
      </m:Request>
    </m:AboutService>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Request Elements

<style>
main td:first-child {min-width:99px}
</style>

| Element       | Definition                                                                                                                                                                                                                                    | Required |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `DataVersion` | String value. The data version can be any version number ranging from 25 through 32. Use "LastQuarter" for last quarter data, "current" for current quarter data and baseline for release quarter data.<br><br>Usage: dataVersion = "current" | N        |
| `RequestType` | String value.<br>Options include:<br>RequestType = "Geocode" for the geocode version. RequestType = "Map" for the map data version. RequestType = "RouteType" for the routing version. If an incorrect value or no value is entered, RouteType will be used.                                                                                                                                                                  | Y        |

#### Calling AboutService

```js
Request req = new Request();
req.Header = new RequestHeader();
req.Header.DataVersion = DataVersion.ToString();
req.Header.RequestType = "Map";

// Create the authentication and authorization header
AuthHeader soapHeader = GenerateAuthHeader(APIName);

// Create the service client
ServiceClient service = newServiceClient();

// Perform the call
Response response = service.AboutService(soapHeader, req);
```

#### Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:alk="http://www.alk.com" xmlns:v1="https://pcmiler.alk.com/APIs/v1.0">
  <soapenv:Header>
    <alk:AuthHeader>
      <alk:Authorization>A77097D2D202A743BB1660E15794D7CA</alk:Authorization>
      <alk:Date>Tue, 12 Aug 2014 18:11:39 GMT</alk:Date>
    </alk:AuthHeader>
  </soapenv:Header>
  <soapenv:Body>
    <v1:AboutService>
      <v1:Request>
        <v1:Header>
          <v1:DataVersion>current</v1:DataVersion>
          <v1:RequestType>Map</v1:RequestType>
        </v1:Header>
      </v1:Request>
    </v1:AboutService>
  </soapenv:Body>
</soapenv:Envelope>
```

#### Response

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header />
  <s:Body>
    <AboutServiceResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <AboutServiceResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>Map</Type>
          <Success>true</Success>
          <DataVersion>28.0.24.5492</DataVersion>
          <Errors i:nil="true" />
        </Header>
      </AboutServiceResult>
    </AboutServiceResponse>
  </s:Body>
</s:Envelope>
```
