---
title: Process Radius Search
description: The ProcessRadiusSearch operation returns a collection of POIs within a certain radius distance.
weight: 7
---

<style>
main td:first-child{width:155px}
</style>

The ProcessRadiusSearch operation returns a collection of POIs within a certain radius distance.

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SOAP-ENV:Header>
    <m:AuthHeader xmlns:m="http://www.alk.com">
      <m:Authorization>String</m:Authorization>
      <m:Date>String</m:Date>
    </m:AuthHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <m:ProcessRadiusSearch xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
        <m:Body>
          <m:CenterPoint>
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
          </m:CenterPoint>
          <m:Radius>
            <m:Value>3.14159265358979E0</m:Value>
            <m:DistanceUnits>Miles</m:DistanceUnits>
          </m:Radius>
          <m:POICategories>All</m:POICategories>
          <m:NameFilter>String</m:NameFilter>
        </m:Body>
      </m:Request>
    </m:ProcessRadiusSearch>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### ProcessRadiusSearch Request

**Request Body Members**

Represents the request of a RadiusSearchRequest allowing the user to set the center point, radius and categories of POIs to search for.

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
      <td><code>CenterPoint</code></td>
      <td>A Location system object. Gets or sets the center point of the radius search which can be either an address or
        a set of coordinates.
        <br>
        Usage:<br>
        <span>Location searchCenter = new Locations();</span>
        <p style="text-indent: 5em;" class="mb-0">searchCenter.Address = new Address() { Zip = "08540"
            };</p>
        <p style="text-indent: 5em;" class="mb-0">searchCenter.Region = DataRegion.NA;</p>
        <p style="text-indent: 5em;" class="mb-0">searchCenter.RegionSpecified = true;</p>
        <p style="text-indent: 5em;" class="mb-0">req.Body.CenterPoint = searchCenter;</p>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>NameFilter</code></td>
      <td>A string value. Gets or sets the name filter by which to refine results to those that contain the string.
        <br>
        Usage:<span>req.Body.NameFilter = "ALK";</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>POICategory</code></td>
      <td>An enumeration of <a href="#POIType">POIType.</a> Gets or sets one or more POI categories to search for.
        <br>
        Usage:<span>req.Body.POICategories = POIType.City;</span>
      </td>
      <td>Y</td>
    </tr>
    <tr>
      <td><code>Radius</code></td>
      <td>A <a href="#Distance">Distance</a> system object. Gets or sets the distance and distance units for the radius
        search.
        <br>
        Usage:<br>
        <span>req.Body.Radius = new Distance(){ Value = 5, DistanceUnits = DistanceUnits.Miles,
          DistanceUnitsSpecified = true, ValueSpecified = true};</span>
      </td>
      <td>Y</td>
    </tr>
  </tbody>
</table>

**Distance Members**

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
      <td><code>DistanceUnits</code></td>
      <td>A DistanceUnits enumeration. Gets or sets the distance units.
        <br>
        Values:<br>
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
              <td><code>Miles</code></td>
              <td>0</td>
              <td>Indicates miles should be used..</td>
            </tr>
            <tr>
              <td><code>Kilometers</code></td>
              <td>1</td>
              <td>Indicates kilometers should be used.</td>
            </tr>
          </tbody>
        </table>
        Usage:<span>DistanceUnits = DistanceUnits.Miles;</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Value</code></td>
      <td>A double value. Gets or sets the value of the distance.
        <br>
        Usage: <span>value = 10;</span>
      </td>
      <td>Y</td>
    </tr>
  </tbody>
</table>

#### POICategories

| Member name            | Value            | Description                                                                       |
| ---------------------- | ---------------- | --------------------------------------------------------------------------------- |
| `All`                  | 0                | Indicates to include all POITypes as the point of interest.                       |
| `City`                 | 1                | Indicates a city as the point of interest.                                        |
| `Zip`                  | 2                | Indicates a zip as the point of interest.                                         |
| `Place`                | 4                | Indicates a custom place as the point of interest.                                |
| `Airport`              | 8                | Indicates to include airports as the point of interest.                           |
| `Automotive`           | 16               | Indicates to include automotive/vehicle repair facility as the point of interest. |
| `WeightStation`        | 32               | Indicates to include weight stations as the point of interest.                    |
| `Dining`               | 64               | Indicates to include restaurants as the point of interest.                        |
| `Education`            | 128              | Indicates to include schools and universities as the point of interest.           |
| `Emergency`            | 256              | Indicates to include emergency and medical facilities as the point of interest.   |
| `Government`           | 512              | Indicates to include government facilities as the point of interest.              |
| `Gas`                  | 1024             | Indicates to include gas stations as the point of interest.                       |
| `Lodging`              | 2048             | Indicates to include hotels and/or motels as the point of interest.               |
| `Parks`                | 4096             | Indicates to include parks as the point of interest.                              |
| `Retail`               | 8192             | Indicates to include retail facilities as the point of interest.                  |
| `RVServices`           | 16384            | Indicates to include RV Services as the point of interest.                        |
| `SportsRec`            | 32768            | Indicates to include sports and recreation facilities as the point of interest.   |
| `Travel`               | 65536            | Indicates to include travel and transportation as the point of interest.          |
| `TruckServices`        | 131072           | Indicates to include truck services as the point of interest.                     |
| `Attractions`          | 262144           | Indicates to include attractions as the point of interest.                        |
| `OilAndGas`            | 524288           | Indicates to include GeoTrac Oil and Gas as the point of interest.                |
| `AutoDealership`       | 1048576          |
| `Bank`                 | 2097152          |
| `BridgesAndTunnels`    | 4194304          |
| `BusTaxiLimo`          | 8388608          |
| `CATScales`            | 16777216         |
| `CityHall`             | 33554432         |
| `DieselExhaustFluid`   | 67108864         |
| `Entertainment`        | 134217728        |
| `EventFacility`        | 268435456        |
| `FerryTerminal`        | 536870912        |
| `GeographicFeature`    | 1073741824       |
| `GroceryStore`         | 2147483648       |
| `GuestHouse`           | 4294967296       |
| `HighwayExit`          | 8589934592       |
| `IntermodalRampLarge`  | 17179869184      |
| `IntermodalRampMedium` | 34359738368      |
| `IntermodalRampSmall`  | 68719476736      |
| `LCVLot`               | 137438953472     |
| `Marina`               | 274877906944     |
| `Municipal`            | 549755813888     |
| `HighwayIntersection`  | 1099511627776    |
| `Other`                | 2199023255552    |
| `Parking`              | 4398046511104    |
| `PlaceOfWorship`       | 8796093022208    |
| `PoliceStation`        | 17592186044416   |
| `RailwayStation`       | 35184372088832   |
| `RentACar`             | 70368744177664   |
| `RestArea`             | 140737488355328  |
| `ATM`                  | 281474976710656  |
| `DistributionCenter`   | 562949953421312  |
| `IntermodalRamp`       | 1125899906842624 |

**Calling ProcessRadiusSearch**

```js
RadiusSearchRequest req = new RadiusSearchRequest();
  req.Header = new  RequestHeader() { DataVersion = DataVersion.ToString(), RequestType = "RadiusSearch" };
  req.Body = new RadiusSearchRequestBody();

  // Specify the target location
  Location searchCenter = new Location();
  searchCenter.Address = new Address() { Zip = "08540" };
  searchCenter.Region = DataRegion.NA;
  searchCenter.RegionSpecified = true;
  req.Body.CenterPoint = searchCenter;

  // Specify the radius to search within the location
  int radius = 5;
  req.Body.Radius = new Distance(){ Value  = 5, DistanceUnits = DistanceUnits.Miles, DistanceUnitsSpecified = true, ValueSpecified = true};
  req.Body.POICategories = POIType.City;
  req.Body.POICategoriesSpecified = true;

  // Create the authentication and authorization header
  AuthHeader soapHeader =  GenerateAuthHeader( APIName);

  // Create the service client
  ServiceClient service = new  ServiceClient();

  // Call API
  RadiusSearchResponse response = service.ProcessRadiusSearch(soapHeader, req);
```

### Request

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
      <ProcessRadiusSearch xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <Request>
        <Header>
          <DataVersion>current</DataVersion>
          <RequestType>RadiusSearch</RequestType>
        </Header>
        <Body>
          <CenterPoint>
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
          </CenterPoint>
```

### Response

The radius search will return up to 3000 POI's regardless of the miles requested. In some cases you may need to specify a smaller radius to get a complete list of matches. Also, the API uses air miles not road miles.

**RadiusSearchResponseBody Members**

Represents the request body of a RadiusSearchResponse.

| Element            | Definition                                                                                                                                           |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| `POISearchMatches` | A list of RadiusSearchMatch system object. Gets or sets a collection containing the resulting POI search matches that fell within the search radius. |

**RadiusSearchMatch Members**

Represents a single radius search match result.

| Element              | Definition                                                |
| -------------------- | --------------------------------------------------------- |
| `DistanceFromCenter` | Gets or sets the POI's distance from the center point.    |
| `POICategory`        | Gets or sets the category this POI falls into.            |
| `POILocation`        | Gets or sets the location of the POI (point of interest). |

#### Sample Response

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <ProcessRadiusSearchResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <ProcessRadiusSearchResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>RadiusSearch</Type>
          <Success>true</Success>
          <DataVersion>28.3.26.9224</DataVersion>
          <Errors />
        </Header>
        <Body>
          <POISearchMatches>
            <RadiusSearchMatch>
              <DistanceFromCenter>
                <Value>0</Value>
                <DistanceUnits>Miles</DistanceUnits>
              </DistanceFromCenter>
              <POICategory>City</POICategory>
              <POILocation>
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
              </POILocation>
            </RadiusSearchMatch>
            <RadiusSearchMatch>
              <DistanceFromCenter>
                <Value>0.022104250579809828</Value>
                <DistanceUnits>Miles</DistanceUnits>
              </DistanceFromCenter>
              <POICategory>City</POICategory>
              <POILocation>
                <Address>
                  <StreetAddress />
                  <City>Princeton</City>
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
                  <Lat>40.34861</Lat>
                  <Lon>-74.65944</Lon>
                </Coords>
                <Region>NA</Region>
                <Label />
                <PlaceName />
              </POILocation>
            </RadiusSearchMatch>
            <RadiusSearchMatch>
              <DistanceFromCenter>
                <Value>0.27920742407694965</Value>
                <DistanceUnits>Miles</DistanceUnits>
              </DistanceFromCenter>
              <POICategory>City</POICategory>
              <POILocation>
                <Address>
                  <StreetAddress />
                  <City>Princeton Township</City>
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
                  <Lat>40.348202</Lat>
                  <Lon>-74.66431</Lon>
                </Coords>
                <Region>NA</Region>
                <Label />
                <PlaceName />
              </POILocation>
            </RadiusSearchMatch>
            <RadiusSearchMatch>
              <DistanceFromCenter>
                <Value>0.40228780370071504</Value>
                <DistanceUnits>Miles</DistanceUnits>
              </DistanceFromCenter>
              <POICategory>City</POICategory>
              <POILocation>
                <Address>
                  <StreetAddress />
                  <City>Princeton Theo Smnry</City>
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
                  <Lat>40.345558</Lat>
                  <Lon>-74.665464</Lon>
                </Coords>
                <Region>NA</Region>
                <Label />
                <PlaceName />
              </POILocation>
            </RadiusSearchMatch>
          </POISearchMatches>
        </Body>
      </ProcessRadiusSearchResult>
    </ProcessRadiusSearchResponse>
  </s:Body>
</s:Envelope>
```
