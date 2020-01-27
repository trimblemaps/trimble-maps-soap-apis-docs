---
title: Process States
weight: 9
---

The ProcessStates operation returns a list of states or countries in a specified region. If the region is NA (North America), the state abbreviation and the full state name are filled in, as well as the country abbreviation and the full country name. Outside of NA, only the country abbreviation and the full country name is filled in.

<style>
main td:first-child{width:111px}
</style>

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SOAP-ENV:Header>
    <m:AuthHeader xmlns:m="http://www.alk.com">
      <m:Authorization>String</m:Authorization>
      <m:Date>String</m:Date>
    </m:AuthHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <m:ProcessStates xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
        <m:Body>
          <m:Format>FIPS</m:Format>
          <m:Region>Unknown</m:Region>
          <m:CountryOnly>true</m:CountryOnly>
        </m:Body>
      </m:Request>
    </m:ProcessStates>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### GetStates Request

Represents a request to reverse geocode a set of geographic coordinates into an address location. The GetStates Request will contain the Region, CountryCodeFormat, and a boolean to specify if the search is for states or countries only.

#### Request Body Members

Represents the request body of a GetStates Request allowing the user to specify what region and format and whether or not to retrieve countries only when performing the operation.

| Element       | Definition                                                                                                                                                                                                                                                                            | Required |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `CountryOnly` | A Boolean value. Gets or sets a value indicating whether to retrieve only countries in the region or whether to also retrieve states.<br>Usage: <code>GetStatesRequest request = new GetStatesRequest();<br>request.Body = new GetStatesRequestBody() { CountryOnly = false };</code> | N        |
| `Format`      | An enumeration of [CountryCodeFormat](#CountryCodeFormat). Gets or sets the abbreviation format for the states and countries returned.<br>Usage: <code>request.Body = new GetStatesRequestBody() { Format = countryCodeFormat.FIPS }; </code>                                         | N        |
| `Region`      | An enumeration of [DataRegion](/soap-apis/docs/shared-api-members/) Gets or sets the region in which to perform the retrieval of states and countries.<br>Usage: <code>request.Body = new GetStatesRequestBody() {Region = DataRegion.NA};</code>                                     | Y        |

#### CountryCodeFormat

| Element | Value | Description                                                   |
| ------- | ----- | ------------------------------------------------------------- |
| `FIPS`  | 0     | Geopolitical codes used by US government. See FIPS PUB 10-4   |
| `ISO2`  | 1     | Two-letter code format, based on ISO 3166-1 "Country Codes."  |
| `ISO3`  | 2     | Three-letter code format used by UN Statistics Division.      |
| `GENC2` | 3     | Two-letter code format for Geopolitical Entities and Codes.   |
| `GENC3` | 4     | Three-letter code format for Geopolitical Entities and Codes. |

### Request

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">https://pcmiler.alk.com/APIs/v1.0/IService/ProcessReverseGeocode</Action>
    <h:AuthHeader xmlns="http://www.alk.com" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:h="http://www.alk.com">
      <Authorization>A77097D2D202A743BB1660E15794D7CA</Authorization>
      <Date>Tue, 24 Feb 2015 18:11:28 GMT</Date>
    </h:AuthHeader>
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <ProcessStates xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <Request>
        <Header>
          <DataVersion>current</DataVersion>
          <RequestType>GetStates</RequestType>
        </Header>
        <Body>
          <Format>FIPS</Format>
          <Region>NA</Region>
          <CountryOnly>false</CountryOnly>
        </Body>
      </Request>
    </ProcessStates>
  </s:Body>
</s:Envelope>
```

### Response

Represents the output response to a request to get states/countries within a region.

#### GetStatesResponse Members

Gets or sets the response body which contains the collection of states/countries within the region.

| Element | Definition                                                                                                                   |
| ------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `State` | A list <> of [StateCountry](#statecountry) system object. Gets or sets the collection of states/countries within the region. |

#### StateCountry

| Element       | Definition                             |
| ------------- | -------------------------------------- |
| `CountryAbbr` | Gets or sets the country abbreviation. |
| `CountryName` | Gets or sets the country name.         |
| `StateAbbr`   | Gets or sets the state abbreviation.   |
| `StateName`   | Gets or sets the state name.           |

### Sample Response

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header />
  <s:Body>
    <ProcessStatesResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <ProcessStatesResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>GetStates</Type>
          <Success>true</Success>
          <DataVersion>28.3.26.9224</DataVersion>
          <Errors i:nil="true" />
        </Header>
        <Body>
          <States>
            <StateCountry>
              <StateAbbr>AL</StateAbbr>
              <StateName>Alabama</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>AK</StateAbbr>
              <StateName>Alaska</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>AZ</StateAbbr>
              <StateName>Arizona</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>AR</StateAbbr>
              <StateName>Arkansas</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>CA</StateAbbr>
              <StateName>California</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>CO</StateAbbr>
              <StateName>Colorado</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>CT</StateAbbr>
              <StateName>Connecticut</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>DE</StateAbbr>
              <StateName>Delaware</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>DC</StateAbbr>
              <StateName>District of Columbia</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>FL</StateAbbr>
              <StateName>Florida</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>GA</StateAbbr>
              <StateName>Georgia</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>HI</StateAbbr>
              <StateName>Hawaii</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>ID</StateAbbr>
              <StateName>Idaho</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>IL</StateAbbr>
              <StateName>Illinois</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>IN</StateAbbr>
              <StateName>Indiana</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>IA</StateAbbr>
              <StateName>Iowa</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>KS</StateAbbr>
              <StateName>Kansas</StateName>
              <CountryAbbr>US</CountryAbbr>
              <CountryName>United States</CountryName>
            </StateCountry>
            <StateCountry>
              <StateAbbr>SB</StateAbbr>
              <StateName>Saint Pierre and Miquelon</StateName>
              <CountryAbbr>SB</CountryAbbr>
              <CountryName>Saint Pierre and Mique</CountryName>
            </StateCountry>
          </States>
        </Body>
      </ProcessStatesResult>
    </ProcessStatesResponse>
  </s:Body>
</s:Envelope>
```
