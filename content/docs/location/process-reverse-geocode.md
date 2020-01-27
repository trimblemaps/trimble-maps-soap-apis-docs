---
title: Process Reverse Geocode
weight: 4
---

The ProcessReverseGeocode operation returns a readable address based on the latitude and longitude in the Request.

### Schema

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SOAP-ENV:Header>
    <m:AuthHeader xmlns:m="http://www.alk.com">
      <m:Authorization>String</m:Authorization>
      <m:Date>String</m:Date>
    </m:AuthHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <m:ProcessReverseGeocode xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
        <m:Body>
          <m:Coords>
            <m:ReverseGeoCoord>
              <m:Lat>String</m:Lat>
              <m:Lon>String</m:Lon>
              <m:Region>Unknown</m:Region>
              <m:Timestamp>String</m:Timestamp>
            </m:ReverseGeoCoord>
          </m:Coords>
          <m:MatchNamedRoadsOnly>false</m:MatchNamedRoadsOnly>
          <m:MaxCleanupMiles>3.14159265358979E0</m:MaxCleanupMiles>
          <m:IncludePostedSpeedLimit>Boolean</m:IncludePostedSpeedLimit>
          <m:CountryAbbrevType>Integer</m:CountryAbbrevType>
        </m:Body>
      </m:Request>
    </m:ProcessReverseGeocode>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### ReverseGeocode Request

**Request Body Members**

Represents a request to reverse geocode a set of geographic coordinates into an address location. Gets or sets the request body which contains the collection of coordinates to reverse geocode. [See ReverseGeocodeRequestBody](/web-services/api/class_a_l_k_1_1_p_c_m_1_1_model_1_1_service_models_1_1_reverse_geocode_request_body.html).

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
                        <td><code>Coords</code></td>
                        <td>A list &lt;&gt; of ReverseGeocode system object(inherited from Coordinates). Gets or sets the list of coordinates to reverse geocode.
                            <br>
                            Usage:<br>
                            <span>List&lt;ReverseGeoCoord&gt; coordsList = new List&lt;ReverseGeoCoord&gt;();</span>
                            <br>
                            <span>ReverseGeoCoord coords = new ReverseGeoCoord() { Lat = "40.388250", Lon = "-74.654726", Region = DataRegion.NA };  // ALK - decimal formatted coords</span>
                            <br>
                            <span>coordsList.Add(coords);</span>
                            <br>
                            <span>coords = new ReverseGeoCoord() { Lat = "40863263", Lon = "-74425648", Region = DataRegion.NA }; // Parsipanny - int formatted coords</span>
                            <br>
                            <span>coordsList.Add(coords);</span>
                        </td>
                        <td>Y</td>
                    </tr>
                    <tr>
                        <td><code>MatchNamedRoadsOnly</code></td>
                        <td>A boolean value.  Get or sets when looking up coordinates, force reverse geocoding to match named roads only.
                            <br>
                            Usage:<span>body.MatchNamedRoadsOnly = true;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>MaxCleanupMiles</code></td>
                        <td>A double value. Get or sets when looking up coordinates, this sets maximum radius in which to find the closest matching road.
                            <br>
                            Usage:<span>body.MaxCleanupMiles = 20;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>IncludePostedSpeedLimit</code></td>
                        <td>
                            A boolean value. For users licensed with speed limit, setting to true will include posted speed limit in the response.
                            <br>
                            Usage:<span>body.IncludePostedSpeedLimit = true;</span>
                        </td>
                        <td>N</td>
                    </tr>
                  <tr>
                      <td><code>CountryAbbrevType</code></td>
                      <td>
                          A string value. Abbreviated country code to be returned. Valid values are "FIPS" (default), "ISO2", "ISO3", "GENC2", "GENC3".
                          <br>
                          Usage:<span>body.CountryAbbrevType = "FIPS";</span>
                      </td>
                      <td>N</td>
                  </tr>
                <tr>
                    <td><code>Timestamp</code></td>
                    <td>
                        A string value. The date/time at the location which will be used to determine whether daylight savings will be applied to the output time zone.
                        <br>
                        Usage:<span>body.Timestamp = "2017-1-12 17:40";</span>
                    </td>
                    <td>N</td>
                </tr>
                </tbody>
</table>

**Calling ProcessReverseGeocode**

```js
List<ReverseGeoCoord> coordsList = new List<ReverseGeoCoord>();

       ReverseGeoCoord coords = new ReverseGeoCoord() { Lat = "40.388250", Lon = "-74.654726", Region = DataRegion.NA };  // ALK - decimal formatted coords
       coordsList.Add(coords);

       coords = new ReverseGeoCoord() { Lat = "40863263", Lon = "-74425648", Region = DataRegion.NA }; // Parsipanny - int formatted coords
       coordsList.Add(coords);

       // Create request
       ReverseGeocodeRequestBody body = new ReverseGeocodeRequestBody() { Coords = coordsList.ToArray() };
       body.MatchNamedRoadsOnly = true;
       body.MatchNamedRoadsOnlySpecified = true;
       body.MaxCleanupMiles = 20;
       body.MaxCleanupMilesSpecified = true;

       ReverseGeocodeRequest request = new ReverseGeocodeRequest()
       {
            Header = new RequestHeader() { DataVersion =  DataVersion.ToString(), RequestType = "ReverseGeocode" },
            Body = body
       };

       // Create the authentication and authorization header
       AuthHeader soapHeader =  GenerateAuthHeader(APIName);

       // Create the service client
       ServiceClient service = new ServiceClient();

       // Call API
       GeocodeResponse response = service.ProcessReverseGeocode(soapHeader, request);
```

### Request

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <h:AuthHeader xmlns="http://www.alk.com" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:h="http://www.alk.com">
      <Authorization>Your Key here</Authorization>
      <Date>Tue, 24 Feb 2015 18:11:28 GMT</Date>
    </h:AuthHeader>
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ProcessReverseGeocode xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <Request>
        <Header>
          <DataVersion>current</DataVersion>
          <RequestType>ReverseGeocode</RequestType>
        </Header>
        <Body>
          <Coords>
            <ReverseGeoCoord>
              <Lat>40.388250</Lat>
              <Lon>-74.654726</Lon>
              <Timestamp>2017-1-21 5:40PM</Timestamp>
            </ReverseGeoCoord>
            <ReverseGeoCoord>
              <Lat>40863263</Lat>
              <Lon>-74425648</Lon>
              <Timestamp>2017-6-21 5:40PM</Timestamp>
            </ReverseGeoCoord>
          </Coords>
          <IncludePostedSpeedLimit>true</IncludePostedSpeedLimit>
          <MatchNamedRoadsOnly>true</MatchNamedRoadsOnly>
          <MaxCleanupMiles>20</MaxCleanupMiles>
          <CountryAbbrevType>FIPS</CountryAbbrevType>
        </Body>
      </Request>
    </ProcessReverseGeocode>
  </s:Body>
</s:Envelope>
```

### Response

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header />
  <s:Body>
    <ProcessReverseGeocodeResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <ProcessReverseGeocodeResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>ReverseGeocode</Type>
          <Success>true</Success>
          <DataVersion>28.3.26.9224</DataVersion>
          <Errors i:nil="true" />
        </Header>
        <Body>
          <Locations>
            <GeocodeOutputLocation>
              <Address>
                <StreetAddress>1000 Herrontown Road</StreetAddress>
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
                <Lat>40.38825</Lat>
                <Lon>-74.654726</Lon>
              </Coords>
              <Region>NA</Region>
              <Label />
```
