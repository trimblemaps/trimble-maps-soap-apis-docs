---
title: Process Geocode
weight: 3
---

The ProcessGeocode operation allows you to find the find the closest latitude and longitude for a given street/city/state/ZIP address location supplied in the Request object.

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SOAP-ENV:Header>
    <m:AuthHeader xmlns:m="http://www.alk.com">
      <m:Authorization>String</m:Authorization>
      <m:Date>String</m:Date>
    </m:AuthHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <m:ProcessGeocode xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
        <m:Body>
          <m:Locations>
            <m:GeocodeLocation>
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
              <m:Region>Unknown</m:Region>
              <m:GeoList>true</m:GeoList>
              <m:MaxResults>0</m:MaxResults>
              <m:CitySearchFilter>CitiesWithZips</m:Region>
            </m:GeocodeLocation>
          </m:Locations>
        </m:Body>
      </m:Request>
    </m:ProcessGeocode>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Geocode Request

**Request Body Members**

Represents a request to geocode one or more locations. Request body contains the locations to geocode.

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
      <td><code>Location</code></td>
      <td>
        A list &lt;&gt; of
        <a href="#GeocodeLocation">GeocodeLocation</a> object. Gets or sets the
        collection of locations to geocode.
        <br />
        <br />
        Usage:<br />
        <code>
          GeocodeLocation[] geocodeLocs = new GeocodeLocation[1];<br />
          geocodeLocs[0] = new GeocodeLocation()<br />
          {<br />
          Address = new Address() { Zip = "08540" },<br />
          Region = DataRegion.NA,<br />
          RegionSpecified = true,<br />
          GeoList = true,<br />
          GeoListSpecified = true,<br />
          MaxResults = 5<br />
          };<br />
          geocodeLocs[0].Address.StreetAddress = "Herrontown Rd";<br />
          geoListRequest.Body.Locations = geocodeLocs;</code
        >
      </td>
      <td>Y</td>
    </tr>
  </tbody>
</table>

**GeocodeLocation Members**

Represents a location to geocode.

| Element            | Definition                                                                                                                                                                                                                                   | Required |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `Address`          | An Address object. Gets or sets the address that needs to be geocoded.<br>Usage: Address = new Address() { Zip = "08540" };                                                                                                                  | Y        |
| `GeoList`          | A Boolean value. Gets or sets a value indicating whether to return a single match for the geocoded result or multiple matches (if they exist).<br>Usage: GeoList = true;                                                                      | N        |
| `MaxResults`       | An Integer value. Gets or sets the value indicating the maximum number of results to be returned from a search (by default is null: indicates that all results are wanted).<br>Usage: MaxResults = 5;                                         | N        |
| `DataRegion`       | An enumeration of DataRegion. Gets or sets the Region that the location is in.<br>Usage: Region = DataRegion.NA;                                                                                                                             | Y        |
| `CitySearchFilter` | An enumeration of CitySearchFilter. Gets or sets a value that dictates whether city searches return city centers or cities with all their corresponding zips (default).<br>Usage: CitySearchFilter = GeocodeCitySearchFilter.CitiesWithZips; | N        |

**Calling ProcessGeocode**

```js
GeocodeRequest geoListRequest = new GeocodeRequest();
  geoListRequest.Header = new  RequestHeader() { DataVersion =  DataVersion.ToString(), RequestType = "GeoCode" };
  geoListRequest.Body = new GeocodeRequestBody();
  // Specify the location(s)
  GeocodeLocation[] geocodeLocs = new GeocodeLocation[1];
  geocodeLocs[0] = new GeocodeLocation()
  {
    Address = new Address() { Zip = "08540" },
    Region = DataRegion.NA
    GeoList = true
    MaxResults = 5
  };
  geocodeLocs[0].Address.StreetAddress = "Herrontown Rd";
  geoListRequest.Body.Locations = geocodeLocs;

  // Create the authentication and authorization header
  AuthHeader soapHeader =  GenerateAuthHeader(APIName);

  // Create the service client
  ServiceClient service = new  ServiceClient();

  // Call API
  GeocodeResponse response = service.ProcessGeocode(soapHeader, geoListRequest);
```

### Geocode Response

GeocodeOutputLocation Members

### Request

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">https://pcmiler.alk.com/APIs/v1.0/IService/CreateRouteSyncMessage</Action>
    <h:AuthHeader xmlns="http://www.alk.com" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:h="http://www.alk.com">
      <Authorization>A77097D2D202A743BB1660E15794D7CA </Authorization>
      <Date>Thu, 21 Aug 2014 16:23:26 GMT</Date>
    </h:AuthHeader>
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ProcessGeocode xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <Request>
        <Header>
          <DataVersion>current</DataVersion>
          <RequestType>GeoCode</RequestType>
        </Header>
        <Body>
          <Locations>
            <GeocodeLocation>
              <Address>
                <StreetAddress>Herrontown Rd</StreetAddress>
                <City xsi:nil="true" />
                <State xsi:nil="true" />
                <Zip>08540</Zip>
                <County xsi:nil="true" />
                <Country xsi:nil="true" />
                <SPLC xsi:nil="true" />
              </Address>
              <Region>NA</Region>
              <GeoList>true</GeoList>
             <MaxResults>2</MaxResults>
            </GeocodeLocation>
          </Locations>
        </Body>
      </Request>
    </ProcessGeocode>
  </s:Body>
</s:Envelope>
```

### Response

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <ProcessGeocodeResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <ProcessGeocodeResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>GeoCode</Type>
          <Success>true</Success>
          <DataVersion>28.2.26.3681</DataVersion>
          <Errors i:nil="true" />
        </Header>
        <Body>
          <Locations>
            <GeocodeOutputLocation>
              <Address>
                <StreetAddress>1-64 Herrontown Road</StreetAddress>
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
                <Lat>40.376874</Lat>
                <Lon>-74.624109</Lon>
              </Coords>
              <Region>NA</Region>
              <Label />
              <PlaceName />
              <TimeZone>EST</TimeZone>
              <Errors>
                <Error>
                  <Type>Warning</Type>
                  <Code>GEOCODE_WARN</Code>
                  <LegacyErrorCode>1000</LegacyErrorCode>
                  <Description>No street number input; Multiple matches; Address uncertain</Description>
                </Error>
              </Errors>
              <ConfidenceLevel>Uncertain</ConfidenceLevel>
              <DistanceFromRoad i:nil="true" />
            </GeocodeOutputLocation>
          </Locations>
        </Body>
      </ProcessGeocodeResult>
    </ProcessGeocodeResponse>
  </s:Body>
</s:Envelope>
```
