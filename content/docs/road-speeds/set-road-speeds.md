---
title: Set Road Speeds
weight: 4
---

Represents a RoadSpeedsRequest structure containing the request header and the road speed request body.

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
    <m:SetRoadSpeeds xmlns:m="https://pcmiler.alk.com/APIs/v1.0">
      <m:Request>
        <m:Header>
          <m:DataVersion>String</m:DataVersion>
          <m:RequestType>String</m:RequestType>
        </m:Header>
        <m:Body>
          <m:RoadSpeeds>
            <m:RoadSpeed>
              <m:RoadCategory>String</m:RoadCategory>
              <m:Speed>Integer</m:Speed>
              <m:Jurisdiction>String</m:Jurisdiction>
            </m:RoadSpeed>
          </m:RoadSpeeds>
          <m:AbbreviationFormat>String</m:AbbreviationFormat>
          <m:Vehicle>String</m:Vehicle>
          <m:Region>String</m:Region>
        </m:Body>
      </m:Request>
    </m:SetRoadSpeeds>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### RoadSpeedsRequest Request

Represents a RoadSpeedsRequest structure containing the request header and the road speed request body.

**Request Body Members**

Represents a road speed for a type of road and state.

| Element              | Definition                                                                                                                                                                                         | Required |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `RoadCategory`       | An enumeration of RoadType. Gets or sets the type of road.<br>Usage:<br>rs.RoadCategory = RoadType.InterStateRural;                                                                                | Y        |
| `Speed`              | An integer value. Gets or sets the speed of the road in miles per hour.<br>Usage:<br>rs.Speed = 65;                                                                                                | Y        |
| `Jurisdiction`       | A string value. Gets or sets the jurisdiction abbreviation (state within NA and country outside NA) for the road speed.<br>Usage:<br>rs.Jurisdiction = “NJ”;                                       | Y        |
| `AbbreviationFormat` | An enumeration value. The country abbreviation format for use outside NA. Default is FIPS.<br>Usage: AbbreviationFormat = CountryAbbreviationType.ISO2                                             | N        |
| `Vehicle`            | An enumeration value. The Vehicle type, either Auto or Truck for which to set road speeds. Default is Truck.<br>Usage: Vehicle = VehicleType.Auto                                                  | N        |
| `Region`             | An enumeration value. The Region which is only required when sending country abbreviations against the WorldWide Data. Default is the default region of the data.<br>Usage: Region = DataRegion.EU | N        |

**Calling SetRoadSpeeds**

```js
 List<RoadSpeed> roadSpeeds = new List<RoadSpeed>();
    RoadSpeed rs = new RoadSpeed();

    String[] states = new string[] { "AL", "AR", "DE" };
    int [] speeds = new int[] {45,45,35,75,65,65,55,55,65,65,65};  //11 to match 11 items in RoadType Enum

    int cntr;
    roadSpeeds.Clear();
    for (int i = 0; i < states.Length; i++ )
    {
        for (  cntr = 0; cntr < speeds.Length; cntr++)
        {
            rs = new RoadSpeed();
            rs.RoadCategory = (RoadType)cntr;
            rs.RoadCategorySpecified = true;
            rs.Speed = speeds[cntr];
            rs.SpeedSpecified = true;
            s.Jurisdiction = states[i];

            roadSpeeds.Add(rs);
        }
    }
    SetRoadSpeedsRequest request = new SetRoadSpeedsRequest();
    request.Header = new RequestHeader() { DataVersion = DataVersion.ToString(), RequestType = "SetRoadSpeeds" };
    request.Body = new SetRoadSpeedsRequestBody();
    request.Body.RoadSpeeds = roadSpeeds.ToArray();
    request.Body.AbbreviationFormat = CountryAbbreviationType.FIPS;
    request.Body.Vehicle = VehicleType.Auto;
    request.Body.Region = DataRegion.NA;

    // Create the authentication and authorization header
    AuthHeader soapHeader = this.Caller.GenerateAuthHeader(APIName);

    // Create the service client
    ServiceClient service = new ServiceClient();

    // Call API
    Response response = service.SetRoadSpeeds(soapHeader, request);
```

### Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:alk="http://www.alk.com" xmlns:pcm="https://pcmiler.alk.com/APIs/v1.0">
  <soapenv:Header>
    <alk:AuthHeader>
      <alk:Authorization>YOUR API KEY HERE</alk:Authorization>
    </alk:AuthHeader>
  </soapenv:Header>
  <soapenv:Body>
    <pcm:SetRoadSpeeds>
      <pcm:Request>
        <pcm:Header>
          <pcm:DataVersion/>
          <pcm:RequestType>SetRoadSpeeds</pcm:RequestType>
        </pcm:Header>
        <pcm:Body xmlns="https://pcmiler.alk.com/APIs/v1.0">
          <pcm:RoadSpeeds>
            <pcm:RoadSpeed>
              <RoadCategory>InterStateRural</RoadCategory>
              <Speed>65</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </pcm:RoadSpeed>
            <pcm:RoadSpeed>
              <RoadCategory>InterStateUrban</RoadCategory>
              <Speed>55</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </pcm:RoadSpeed>
            <pcm:RoadSpeed>
              <RoadCategory>LocalUrban</RoadCategory>
              <Speed>12</Speed>
              <Jurisdiction>NJ</Jurisdiction>
            </pcm:RoadSpeed>
          </pcm:RoadSpeeds>
          <pcm:AbbreviationFormat>FIPS</pcm:AbbreviationFormat>
          <pcm:Vehicle>Auto</pcm:Vehicle>
          <pcm:Region>NA</pcm:Region>
        </pcm:Body>
      </pcm:Request>
    </pcm:SetRoadSpeeds>
  </soapenv:Body>
</soapenv:Envelope>
```

### Response

Represents a RoadSpeedResponse structure containing the response header and the road speeds response body.

**RoadSpeedsResponseBody Members.**

Gets or sets the custom place response body which contains the custom places that were requested.

| Element    | Definition                                                                                                                                                |
| ---------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Response` | A responseHeader system object. Represents a general response from the web service which contains no additional output information aside from the header. |

**Sample Response**

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <SetRoadSpeedsResponse xmlns="https://pcmiler.alk.com/APIs/v1.0">
      <SetRoadSpeedsResult xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Header>
          <Type>SetRoadSpeeds</Type>
          <Success>true</Success>
          <DataVersion>31.4.43.5012</DataVersion>
          <Errors i:nil="true" />
        </Header>
      </SetRoadSpeedsResult>
    </SetRoadSpeedsResponse>
  </s:Body>
</s:Envelope>
```
