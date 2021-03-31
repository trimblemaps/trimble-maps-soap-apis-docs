---
title: Shared API Members
weight: 12
---

Shared API members are those that are used in several API calls such as the StopLocation. This structure that is shared is the same for each API input and response.

### StopLocation

The StopLocation structure is used to pass all data associated with the geographic point. It can contain either address or latitude/longitude information. Either the address element is sent or the cords element is specified. Only one is required and specifying both will result in an error. The StopLocation extends the Location Elements.

### Location

Represents a real world location made up of an address and/or latitude/longitude coordinates.

Inheritance Hierarchy

[System.Object](https://docs.microsoft.com/en-us/dotnet/api/system.object?redirectedfrom=MSDN&view=netframework-4.8)

- ALK.PCM.Model.BusinessModels.Location
- ALK.PCM.Model.BusinessModels.CustomPlace
- ALK.PCM.Model.BusinessModels.GeocodeOutputLocation
- ALK.PCM.Model.BusinessModels.NewCustomPlace
- ALK.PCM.Model.BusinessModels.StopLocation

### StopLocation and Location Schema

**StopLocation**

The ComplexType Locations extends stopLocation to include Location elements as shown below this schema.

```xml
<xs:complexType name="StopLocation">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Location">
      <xs:sequence>
        <xs:element minOccurs="0" name="Costs" nillable="true" type="tns:StopCosts"/>
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
<xs:element name="StopLocation" nillable="true" type="tns:StopLocation"/>
```

**Location**

```xml
<xs:complexType name="Location">
  <xs:sequence>
    <xs:element minOccurs="0" name="Address" nillable="true" type="tns:Address"/>
    <xs:element minOccurs="0" name="Coords" nillable="true" type="tns:Coordinates"/>
    <xs:element minOccurs="0" name="Region" type="tns:DataRegion"/>
    <xs:element minOccurs="0" name="Label" nillable="true" type="xs:string"/>
    <xs:element minOccurs="0" name="PlaceName" nillable="true" type="xs:string"/>
  </xs:sequence>
</xs:complexType>
<xs:element name="Location" nillable="true" type="tns:Location"/>
```

StopLocation Members

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
                        <td><code>Address</code></td>
                        <td>A system object of the <a href="#Address">Address.</a> Gets or sets the address information for the location.
                            <br>
                            Usage:<span>Address = new Address</span>
                            <p style="text-indent: 4em;" class="mb-0"><span class="kwd mb-0">{</p>
                            <p style="text-indent: 5em;" class="mb-0">Zip = "19123"</p>
                            <p style="text-indent: 4em;" class="mb-0">}</p>
                        </td>
                        <td>Y(if not sending coords)</td>
                    </tr>
                    <tr>
                        <td><code>Coords</code></td>
                        <td>A system object of type <a href="#Coordinates">Coordinates.</a> Gets or sets the geographic coordinates for the location.
                            <br>
                            Usage:<span>Coordinates = new Coordinates</span>
                            <p style="text-indent: 4em;" class="mb-0">{</p>
                            <p style="text-indent: 5em;" class="mb-0">Lat = "40353828",</p>
                            <p style="text-indent: 5em;" class="mb-0">Lon = "-74610884"</p>
                            <p style="text-indent: 4em;" class="mb-0">}</p>
                        </td>
                        <td>Y(if not sending Address)</td>
                    </tr>
                    <tr>
                        <td><code>Cost</code></td>
                        <td>A system object of type <a href="#StopCost">StopCost.</a> Gets or sets the cost associated with this stop.
                            <br>
                            Usage:<span>StopCosts stopCosts = new StopCosts</span>
                            <p style="text-indent: 4em;" class="mb-0">{</p>
                            <p style="text-indent: 5em;" class="mb-0">CostOfStop = 5,</p>
                            <p style="text-indent: 5em;" class="mb-0">CostOfStopSpecified = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">HoursPerStop = 1,</p>
                            <p style="text-indent: 5em;" class="mb-0">HoursPerStopSpecified = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">Loaded = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">LoadedSpecified = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">OnDuty = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">OnDutySpecified = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">UseOrigin = false,</p>
                            <p style="text-indent: 5em;" class="mb-0">UseOriginSpecified = true</p>
                            <p style="text-indent: 4em;" class="mb-0">};</p>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Label</code></td>
                        <td>A string value. Gets or sets a string which represents a label to be displayed on maps and in reports in association with a stop.
                            <br>
                            Usage:<span>label = “stop 1”;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>PlaceName</code></td>
                        <td>A string value. Gets or sets the place name which corresponds to a custom place; this would supersede standard address entries for geocoding or identify a custom place to be associated with the address.  Available for premium account types only.
                            <br>
                            Usage:<span>PlaceName = “ALK”;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Region</code></td>
                        <td>An enumeration of <a href="#DataRegion">DataRegion.</a> Gets or sets the Region that the location is in.
                            <br>
                            Usage:<span>Region = DataRegion.NA</span>
                        </td>
                        <td>Y</td>
                    </tr>
                </tbody>
</table>

Location Members

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
                        <td><code>Address</code></td>
                        <td>A system object of the <a href="#Address">Address.</a> Gets or sets the address information for the location.
                            <br>
                            Usage:<span>Address = new Address</span>
                            <p style="text-indent: 4em;" class="mb-0">{</p>
                            <p style="text-indent: 5em;" class="mb-0">Zip = "19123"</p>
                            <p style="text-indent: 4em;" class="mb-0">}</p>
                        </td>
                        <td>Y(if not sending coords)</td>
                    </tr>
                    <tr>
                        <td><code>Coords</code></td>
                        <td>A system object of type <a href="#Coordinates">Coordinates.</a> Gets or sets the geographic coordinates for the location.
                            <br>
                            Usage:<span>Coordinates = new Coordinates</span>
                            <p style="text-indent: 4em;" class="mb-0">{</p>
                            <p style="text-indent: 5em;" class="mb-0">Lat = "40353828",</p>
                            <p style="text-indent: 5em;" class="mb-0">Lon = "-74610884"</p>
                            <p style="text-indent: 4em;" class="mb-0">}</p>
                        </td>
                        <td>Y(if not sending Address)</td>
                    </tr>
                    <tr>
                        <td><code>Label</code></td>
                        <td>A string value. Gets or sets a string which represents a label to be displayed on maps and in reports in association with a stop.
                            <br>
                            Usage:<span>label = “stop 1”;</span>
                        </td>
                        <td>Y</td>
                    </tr>
                    <tr>
                        <td><code>PlaceName</code></td>
                        <td>A string value. Gets or sets the place name which responds to a custom place; this would supersede standard address entries for geocoding or identify a custom place to be associated with the address.  Available for premium account types only.
                            <br>
                            Usage:<span>PlaceName = “ALK”;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Region</code></td>
                        <td>An enumeration of <a href="#DataRegion">DataRegion.</a> Gets or sets the Region that the location is in.
                            <br>
                            Usage:<span>Region = DataRegion.NA</span>
                        </td>
                        <td>Y</td>
                    </tr>
                </tbody>
            </table>

## Address

Represents a street address with support for SPLC as well as place name for custom places.

**Address Schema**

```xml
<xs:complexType name="Address"> <xs:sequence> <xs:element minOccurs="0" name="StreetAddress" nillable="true" type="xs:string"/>
<xs:element minOccurs="0" name="City" nillable="true" type="xs:string"/>
<xs:element minOccurs="0" name="State" nillable="true" type="xs:string"/>
<xs:element minOccurs="0" name="Zip" nillable="true" type="xs:string"/>
<xs:element minOccurs="0" name="County" nillable="true" type="xs:string"/>
<xs:element minOccurs="0" name="Country" nillable="true" type="xs:string"/>
<xs:element minOccurs="0" name="SPLC" nillable="true" type="xs:string"/>
<xs:element minOccurs="0" name="CountryPostalFilter" type="tns:PostCodeType"/>
<xs:element minOccurs="0" name="AbbreviationFormat" type="tns:CountryAbbreviationType"/>
</xs:sequence>
</xs:complexType>
<xs:element name="Address" nillable="true" type="tns:Address"/>
```

**Address Members**

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
                        <td><code>AbbreviationFormat</code></td>
                        <td>An enumeration of CountryAbbreviationType. Gets or sets the AbbreviationFormat. The default setting is FIPS.
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>FIPS</td>
                                        <td>0</td>
                                        <td>Indicates the country abbreviation type to FIPS</td>
                                    </tr>
                                    <tr>
                                        <td>ISO2</td>
                                        <td>1</td>
                                        <td>Indicates the country abbreviation type to ISO2</td>
                                    </tr>
                                    <tr>
                                        <td>ISO3</td>
                                        <td>2</td>
                                        <td>Indicates the country abbreviation type to ISO3</td>
                                    </tr>
                                    <tr>
                                        <td>GENC2</td>
                                        <td>3</td>
                                        <td>Two-letter code format for Geopolitical Entities and Codes</td>
                                    </tr>
                                    <tr>
                                        <td>GENC3</td>
                                        <td>4</td>
                                        <td>Three-letter code format for Geopolitical Entities and Codes</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>AbbreviationFormat = CountryAbbreviationType.FIPS</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>City</code></td>
                        <td>A string value. Gets or sets the city
                            <br>
                            Usage:<span>City = “Philadelphia”</span>
                        </td>
                        <td>Y(when sending state)</td>
                    </tr>
                    <tr>
                        <td><code>Country</code></td>
                        <td>A string value. Gets or sets the country.
                            <br>
                            Usage:<span>Country = “US”</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>CountryPostalFilter</code></td>
                        <td>An enumeration of PosCodeType. Gets or sets the postal code country filter. This can be used to filter the postal code by country within North America.
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>US</td>
                                        <td>0</td>
                                        <td>Indicates the country code filter to be the United States</td>
                                    </tr>
                                    <tr>
                                        <td>Mexico</td>
                                        <td>1</td>
                                        <td>Indicates the country code filter to be Mexico</td>
                                    </tr>
                                    <tr>
                                        <td>Both</td>
                                        <td>2</td>
                                        <td>Indicates the country code filter to be both United States and Mexico.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>CountryPostalFilter =PostCodeType.US</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>County</code></td>
                        <td>A string value. Gets or sets the county or jurisdiction. Used in conjunction with City/State
                            <br>
                            Usage:<span>County = “Bucks”;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>SPLC</code></td>
                        <td>A string value. Gets or sets the Standard Point Location Code.
                            <br>
                            Usage:<span>SPLC = “1234”</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>State</code></td>
                        <td>A string value. Gets or sets the state or country name if the Region is outside of the North America.
                            <br>
                            Usage:<span>State = "PA"</span>
                        </td>
                        <td>Y(When city specified)</td>
                    </tr>
                    <tr>
                        <td><code>StreetAddress</code></td>
                        <td>A string value. Gets or sets the house number and/or street name. Premium accounts only have street-level routing.
                            <br>
                            Usage:<span>StreetAddress = “1030 N. 2nd St.”</span>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

#### Region

| Member Name | Value | Description                        |
| ----------- | ----- | ---------------------------------- |
| AF          | 1     | Indicates Africa.                  |
| AS          | 2     | Indicates Asia.                    |
| EU          | 3     | Indicates Europe.                  |
| NA          | 4     | Indicates North America            |
| OC          | 5     | Indicates the Australian continent |
| SA          | 6     | Indicates South America            |

#### Coordinates

Represents geographic coordinates, i.e. latitude and longitude.

**Coordinates Schema**

```xml
<xs:complexType name="Coordinates">
  <xs:sequence>
    <xs:element minOccurs="0" name="Lat" nillable="true" type="xs:string"/>
    <xs:element minOccurs="0" name="Lon" nillable="true" type="xs:string"/>
  </xs:sequence>
</xs:complexType>
<xs:element name="Coordinates" nillable="true" type="tns:Coordinates"/>
```

| Element | Definition                                                                                                        | Required               |
| ------- | ----------------------------------------------------------------------------------------------------------------- | ---------------------- |
| `Lat`   | Gets or sets the latitude in decimal degrees or decimal degrees \*1E6 as a string.<br>Usage:Lat = “34.079799”;    | Y(When sending coords) |
| `Lon`   | Gets or sets the longitude in decimal degrees or decimal degrees \* 1E6 as a string<br>Usage:Lon = “-118.412935”; | Y(When sending coords) |

#### StopCosts

The StopCosts structure is used to pass all data associated with any additional costs incurred by stopping at a specific location. This structure is references as part of the StopLocation structure.

**StopCosts Schema**

```xml
<xs:complexType name="StopCosts">
  <xs:sequence>
    <xs:element minOccurs="0" name="CostOfStop" type="xs:double"/>
    <xs:element minOccurs="0" name="HoursPerStop" type="xs:double"/>
    <xs:element minOccurs="0" name="Loaded" type="xs:boolean"/>
    <xs:element minOccurs="0" name="OnDuty" type="xs:boolean"/>
    <xs:element minOccurs="0" name="UseOrigin" type="xs:boolean"/>
  </xs:sequence>
</xs:complexType>
<xs:element name="StopCosts" nillable="true" type="tns:StopCosts"/>
```

**StopCost Members**

| Element        | Definition                                                                                                                                                 | Required |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `CostOfStop`   | A double value. Gets or sets the cost of the stop(in dollars)<br>Usage:CostOfStop = 10.5;                                                                  | N        |
| `HoursPerStop` | A double value. Gets or sets a length of time allocated for this stop. The format is in decimal hours.<br>Usage:HoursPerStop = 2.5;                        | N        |
| `Loaded`       | A boolean value. Gets or sets a value indicating whether the truck is loaded.<br>Usage:Loaded = true;                                                      | N        |
| `OnDuty`       | A boolean value. Gets or sets a value indicating whether the truck is on duty.<br>Usage:onDuty = true;                                                     | N        |
| `UseOrigin`    | A boolean value. Gets or sets a value indicating whether to default all the settings to those associated with the route origin.<br>Usage:UseOrigin = true; | N        |

### ReportOptions Members

Represents options specific to creation of reports.

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
                        <td><code>EstimatedTimeOptions</code></td>
                        <td>A system object of type EstimatedTimeOptions. Gets or sets the estimated time options.
                            <br>
                            Usage:<span>EstimatedTimeOptions timeOpts = new EstimatedTimeOptions()</span>
                            <p style="text-indent: 4em;" class="mb-0">{</p>
                            <p style="text-indent: 5em;" class="mb-0">DateAndTime = dateAndTime,</p>
                            <p style="text-indent: 5em;" class="mb-0">DateOption = DateOption.Specific,</p>
                            <p style="text-indent: 5em;" class="mb-0">DateOptionSpecified = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">ETAETD = ETAETDType.Arrival,</p>
                            <p style="text-indent: 5em;" class="mb-0">ETAETDSpecified = true</p>
                            <p style="text-indent: 4em;" class="mb-0">};</p>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>ExchangeRate</code></td>
                        <td>A double value. Gets or sets the change rate to convert US dollars to Canadian dollars.
                            <br>
                            Usage:<span>ExchangeRate = 1.5;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>FuelUnits</code></td>
                        <td>An enumeration of VolumeUnits. Gets or sets the fuel units to gallons(default) or liters.
                            Values:
                            <br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>Gallons</td>
                                        <td>0</td>
                                        <td>Indicates U.S. gallons should be used.</td>
                                    </tr>
                                    <tr>
                                        <td>Liters</td>
                                        <td>1</td>
                                        <td>Indicates liters should be used.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>FuelUnits = VolumeUnits.Gallons;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>IncludeFerryDistance</code></td>
                        <td>A boolean value. Gets or sets a value indicating whether or not miles travelled on ferries are included in mileage calculation. The default is true.
                            <br>
                            Usage:<span>IncludeFerryDistance=false</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Language</code></td>
                        <td>An enumeration of Language Type. Gets or sets the language in which the information is to be displayed. The default is ENUS for English United States.
                            Values:
                            <br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>ENUS</td>
                                        <td>0</td>
                                        <td>Indicates English - United States.</td>
                                    </tr>
                                    <tr>
                                        <td>ENGB</td>
                                        <td>1</td>
                                        <td>Indicates English - Great Britain.</td>
                                    </tr>
                                    <tr>
                                        <td>DE</td>
                                        <td>2</td>
                                        <td>Indicates German.</td>
                                    </tr>
                                    <tr>
                                        <td>FR</td>
                                        <td>3</td>
                                        <td>Indicates French.</td>
                                    </tr>
                                    <tr>
                                        <td>ES</td>
                                        <td>4</td>
                                        <td>Indicates Spanish.</td>
                                    </tr>
                                    <tr>
                                        <td>IT</td>
                                        <td>5</td>
                                        <td>Indicates Italian.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>Language = LanguageType.DE;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>RouteCosts</code></td>
                        <td>A system object of type <a href="#RouteCost">RouteCosts.</a> Gets or sets the route costs.
                            <br>
                            Usage:<span>RouteCosts routeCosts = new RouteCosts</span>
                            <p style="text-indent: 4em;" class="mb-0">{</p>
                            <p style="text-indent: 5em;" class="mb-0">CostTimeLoaded = 15,</p>
                            <p style="text-indent: 5em;" class="mb-0">CostTimeLoadedSpecified = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">FuelEconomyEmpty = 1,</p>
                            <p style="text-indent: 5em;" class="mb-0">FuelEconomyEmptySpecified = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">FuelEconomyLoaded = 16,</p>
                            <p style="text-indent: 5em;" class="mb-0">FuelEconomyLoadedSpecified = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">PricePerFuelUnit = 3.95,</p>
                            <p style="text-indent: 5em;" class="mb-0">PricePerFuelUnitSpecified = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">TruckStyle = TruckStyle.FiftyThreeSemiTrailer,</p>
                            <p style="text-indent: 5em;" class="mb-0">TruckStyleSpecified = true</p>
                            <p style="text-indent: 4em;" class="mb-0">};</p>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>TimeCosts</code></td>
                        <td>An object <a href="#TimeCost">timeCosts.</a> Gets or sets the time costs.
                            <br>
                            Usage:<span>TimeCosts timeCosts = new TimeCosts()</span>
                            <p style="text-indent: 4em;" class="mb-0">{</p>
                            <p style="text-indent: 5em;" class="mb-0">BorderWait = 5,</p>
                            <p style="text-indent: 5em;" class="mb-0">BorderWaitSpecified = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">BreakInterval = 4,</p>
                            <p style="text-indent: 5em;" class="mb-0">BreakIntervalSpecified = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">BreakLength = 2,</p>
                            <p style="text-indent: 5em;" class="mb-0">BreakLengthSpecified = true</p>
                            <p style="text-indent: 4em;" class="mb-0">};</p>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>TollCurrency</code></td>
                        <td>An enumeration of TollCurrency. Gets or sets the toll currency, currently US or CDN
                            Values:
                            <br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>US</td>
                                        <td>0</td>
                                        <td>Indicates that the currency should be United States dollars.</td>
                                    </tr>
                                    <tr>
                                        <td>CDN</td>
                                        <td>1</td>
                                        <td>Indicates that the currency should be Canadian dollars.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>TollCurrency = Currency.US;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>TollDiscount</code></td>
                        <td>A string value. Gets or sets a string containing the applicable toll discount program.  This field is only valid if the user has quarterly toll data privileges and the UseTollData is set to true.  Available programs are: 407ETR Transponder, A25 Transponder, BreezeBy,C-Pass, Cruise Card, E-Pass, E-Pass Canada, EXpress Toll, EZ Tag, EZPass, EZPass-NJ, EZPass-WV, FAST LANE, FasTrak, GeauxPass, GO-PASS, Good to Go, I-PASS, I-Zoom, K-TAG, Laredo Trade Tag, Leeway, MACPASS, NC Quick Pass, NEXPRESS TOLL, Palmetto Pass, Peach Pass, PikePass, Quickpass, Smart Tag, StraitPASS, SunPass, TollTag, TxTag, and WabashPass or All.
                            <br>
                            Usage:<span>TollDiscount = “All”;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>UseCustomRoadSpeeds</code></td>
                        <td>A boolean value. Gets or sets a value indicating whether or not to use custom road speeds and avoids and favors.
                            <br>
                            Usage:<span>Use CustomRoadSpeeds = false;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>UseTollData</code></td>
                        <td>A boolean value. Gets or sets a value indicating whether or not toll data should be used.
                            <br>
                            Usage:<span>UseTollData=false;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>UseTraffic</code></td>
                        <td>A boolean value. Gets or sets a value indicating whether or not to use traffic data when calculating transit times.
                            <br>
                            Usage:<span>UseTraffic=true;</span>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

### EstimatedTimeOption Members

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
                        <td><code>DateAndTime</code></td>
                        <td>A system object of type <a href="#DateTime">DateTimeType</a>. Gets or sets the date, time, time of day and time zone information.
                            <br>
                            Usage:<span>DateTimeType dateAndTime = new DateTimeType()</span>
                            <p style="text-indent: 4em;" class="mb-0">{</p>
                            <p style="text-indent: 5em;" class="mb-0">CalendarDate = "10/10/2014",</p>
                            <p style="text-indent: 5em;" class="mb-0">DayOfWeek =DayOfWeek.Friday,</p>
                            <p style="text-indent: 5em;" class="mb-0">DayOfWeekSpecified = true,</p>
                            <p style="text-indent: 5em;" class="mb-0">TimeOfDay = "12:00",</p>
                            <p style="text-indent: 5em;" class="mb-0">TimeZone = TimeZone.Eastern,</p>
                            <p style="text-indent: 5em;" class="mb-0">TimeZoneSpecified = true</p>
                            <p style="text-indent: 4em;" class="mb-0">};</p>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>DateOption</code></td>
                        <td>An enumeration of DateOption.
                            <br>
                            Values:
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>Current</td>
                                        <td>0</td>
                                        <td>Indicates that the current system time should be used.</td>
                                    </tr>
                                    <tr>
                                        <td>Specific</td>
                                        <td>1</td>
                                        <td>Indicates that a specific supplied time should be used.</td>
                                    </tr>
                                    <tr>
                                        <td>DayOfWeek</td>
                                        <td>2</td>
                                        <td>Indicates that a day of the week should be used.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>FuelUnits = VolumeUnits.Gallons;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>ETAETD</code></td>
                        <td>An enumeration of ETAETD type.
                            <br>
                            Values:
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>Arrival</td>
                                        <td>0</td>
                                        <td>Indicates the time is an estimated time of arrival.</td>
                                    </tr>
                                    <tr>
                                        <td>Depart</td>
                                        <td>1</td>
                                        <td>Indicates the time is an estimated time of departure.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>ETAETD = ETAETD.Arrival;</span>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

### TimeCosts Members

The Timecosts structure is used to pass all data associated with additional delays associated with the trip. This structure is part of the RouteOptions structure and is valid for the GetReport functionality.

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
      <td><code>BorderWait</code></td>
      <td>
        A float value. Gets or sets the additional amount of time at the border to the overall trip.
        <br />
        Usage:<span>BorderWait=5;</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>BreakInterval</code></td>
      <td>
        A float value. Gets or sets the elapsed time of the trip before a break will be taken. The format is in decimal hours.
        <br />
        Usage:<span>BreakInterval = 4;</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>BreakLength</code></td>
      <td>
        A float value. Gets or sets the amount of time a break will last. The format is in decimal hours.
        <br />
        Usage:<span>BreakLength = 2;</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>DepartTime</code></td>
      <td>
        A <a href="#TimeOfDay">TimeOfDayObject</a>. Gets or sets the start time of the trip. The format is HH:MM A[P]M. This field is conditional, and valid if the RoutingType is Fastest.
        <br />
        Usage: DepartTime = new TimeOfDay()
        <p style="text-indent: 4em;" class="mb-0">{</p>
        <p style="text-indent: 5em;" class="mb-0">AmPm = AmPmType.AM,</p>
        <p style="text-indent: 5em;" class="mb-0">AmPmSpecified = true,</p>
        <p style="text-indent: 5em;" class="mb-0">Hour = 10,</p>
        <p style="text-indent: 5em;" class="mb-0">HourSpecified = true,</p>
        <p style="text-indent: 5em;" class="mb-0">Minute = 15,</p>
        <p style="text-indent: 5em;" class="mb-0">MinuteSpecified = true</p>
        <p style="text-indent: 4em;" class="mb-0">}</p>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>RemainingHoursOfService</code></td>
      <td>
        A float value. Gets or sets the remaining hours of service at the start of the trip before the driver needs to take a break. The format is in decimal hours.
        <br />
        Usage:<span>RemainingHoursOfService = 2;</span>
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

### TimeOfDay

The TimeOfDay structure contains the hour, minute, and AM/PM.

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
                        <td><code>AmPm</code></td>
                        <td>An enumeration of AmPmType. Gets or sets the value indicating military, am, or pm.
                            <br>
                            Values:
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>Military</td>
                                        <td>0</td>
                                        <td>Indicates the time is in 24-hour clock, also known as military format.</td>
                                    </tr>
                                    <tr>
                                        <td>AM</td>
                                        <td>1</td>
                                        <td>Indicates the time in the AM period of the 12-hour clock.</td>
                                    </tr>
                                    <tr>
                                        <td>PM</td>
                                        <td>2</td>
                                        <td>Indicates the time in the PM period of the 12-hour clock.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>AmPm = AmPmType.AM;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Hour</code></td>
                        <td>An integer value. Gets or sets the hour value.
                            <br>
                            Usage:<span>Hour = 10;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>Min</code></td>
                        <td>An Integer value. Gets or sets the minute value.
                            <br>
                            Usage:<span>Minute = 30;</span>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

### RouteCosts Members

Represents route cost information associated with a Route and subclasses such as MapRoute and ReportRoute

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
                        <td><code>CostTimeEmpty</code></td>
                        <td>A double value. Gets or sets the estimated labor or other cost per hour when empty.
                            <br>
                            Usage:<span>CostTimeEmpty = 5.5;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>CostTimeLoaded</code></td>
                        <td>A double value. Gets or sets the estimated labor or other cost per hour when loaded.
                            <br>
                            Usage:<span>CostTimeEmpty = 15;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>FuelEconomyEmpty</code></td>
                        <td>A double value. Gets or sets the fuel efficiency(distance units per volume units) when empty.
                            <br>
                            Usage:<span>FuelEconomyEmpty = 1;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>FuelEconomyLoaded</code></td>
                        <td>A double value. Gets or sets the fuel efficiency(distance units per volume units) when loaded.
                            <br>
                            Usage:<span>FuelEconomyLoaded = 16;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>GreenHouseGas</code></td>
                        <td>A double value. Gets or sets the greenhouse gas cost in lbs per fuel unit.
                            <br>
                            Usage:<span>GreenHouseGas = 1;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>OtherCostPerDistanceUnitEmpty</code></td>
                        <td>A double value. Gets or sets the maintenance cost per mile when empty.
                            <br>
                            Usage:<span>OtherCostPerDistanceUnitEmpty = 5;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>OtherCostPerDistUnitLoaded</code></td>
                        <td>A double value. Gets or sets the maintenance cost per distance unit when loaded.
                            <br>
                            Usage:<span>OtherCostPerDistUnitLoaded = 2;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>PricePerFuelUnit</code></td>
                        <td>A double value. Gets or sets the price per gallon of fuel.
                            <br>
                            Usage:<span>PricePerFuelUnit = 3.95;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>TruckStyle</code></td>
                        <td>An enumeration of TruckStyle. Gets or sets the truck style which includes vehicle dimensions and route costs.
                            <br>
                            Values:
                            <table>
                                <thead>
                                    <tr>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>None</td>
                                        <td>Indicates that no particular truck style is chosen.</td>
                                    </tr>
                                    <tr>
                                        <td>TwentyEightDoubleTrailer</td>
                                        <td>Indicates that a 28' double trailer should be used.</td>
                                    </tr>
                                    <tr>
                                        <td>FortyStraightTruck</td>
                                        <td>Indicates that a 40' straight truck trailer should be used.</td>
                                    </tr>
                                    <tr>
                                        <td>FortyEightSemiTrailer</td>
                                        <td>Indicates that a 48' semitrailer should be used.</td>
                                    </tr>
                                    <tr>
                                        <td>FiftyThreeSemiTrailer</td>
                                        <td>Indicates that a 53' semitrailer should be used.</td>
                                    </tr>
                                    <tr>
                                        <td>FullSizeVan</td>
                                        <td>Indicates a full-size van should be used.</td>
                                    </tr>
                                    <tr>
                                        <td>TwentySixStraightTruck</td>
                                        <td>Indicates a 26' straight truck should be used.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>TruckStyle = TruckStyle.FiftyThreeSemiTrailer;</span>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

### Route

Represents a route and all its associated information from the standpoint of a request for either mapping or reporting.

**Route Schema**

```xml
<xs:complexType name="Route">
<xs:sequence>
<xs:element minOccurs="0" name="RouteId" nillable="true" type="xs:string"/>
<xs:element minOccurs="0" name="Stops" nillable="true" type="tns:ArrayOfStopLocation"/>
<xs:element minOccurs="0" name="Options" nillable="true" type="tns:RouteOptions"/>
<xs:element minOccurs="0" name="FuelOptions" nillable="true" type="tns:FuelOptions"/>
<xs:element minOccurs="0" name="AFOptions" nillable="true" type="tns:AvoidFavorSetOption"/>
</xs:sequence>
</xs:complexType>
<xs:element name="Route" nillable="true" type="tns:Route"/>
```

**Route Members**

| Element   | Definition                                                                                                                                        | Required |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `Options` | A system object. Sets the routing options with the RouteOption class. See RouteOption Members.<br>Usage:RouteOptions opts = new RouteOptions(){}; | N        |
| `RouteId` | A string value. Sets the unique route identifier. This may be used to identify routes when reports are created.<br>Usage:routeID = "PhillytoAC";  | N        |
| `Stops`   | A list of the StopLocation object. Sets the collection of stops that make up the route.<br>Usage:StopLocation [] stops = new StopLocation[3];     | Y        |

### RouteOptions

Represents options specific to the kind of route to be run.

**RouteOptions Schema**

```xml
<xs:complexType name="RouteOptions">
<xs:sequence>
<xs:element minOccurs="0" name="BordersOpen" nillable="true" type="xs:boolean"/>
<xs:element minOccurs="0" name="ClassOverrides" type="tns:ClassOverrideType"/>
<xs:element minOccurs="0" name="CustomRoadSpeeds" nillable="true" type="tns:ArrayOfRoadSpeedBase"/>
<xs:element minOccurs="0" name="DistanceUnits" type="tns:DistanceUnits"/>
<xs:element minOccurs="0" name="ElevLimit" nillable="true" type="xs:unsignedInt" />
<xs:element minOccurs="0" name="FerryDiscourage" type="xs:boolean" />
<xs:element minOccurs="0" name="FuelRoute" type="xs:boolean" />
<xs:element minOccurs="0" name="GovernorSpeedLimit" nillable="true" type="xs:int" />
<xs:element minOccurs="0" name="HazMatType" type="tns:HazMatType"/>
<xs:element minOccurs="0" name="HighwayOnly" nillable="true" type="xs:boolean"/>
<xs:element minOccurs="0" name="HoSOptions" nillable="true" type="tns:HoursOfServiceOptions" />
<xs:element minOccurs="0" name="HubRouting" type="xs:boolean"/>
<xs:element minOccurs="0" name="OverrideRestrict" type="xs:boolean"/>
<xs:element minOccurs="0" name="RouteOptimization" type="tns:RouteOptimizeType"/>
<xs:element minOccurs="0" name="RoutingType" type="tns:RoutingType"/>
<xs:element minOccurs="0" name="SideOfStreetAdherence" type="tns:SideOfStreetAdherenceLevel" />
<xs:element minOccurs="0" name="TollDiscourage" type="xs:boolean"/>
<xs:element minOccurs="0" name="TrailerCfg" nillable="true" type="tns:TrailerConfig" />
<xs:element minOccurs="0" name="TruckCfg" nillable="true" type="tns:TruckConfig"/>
<xs:element minOccurs="0" name="UseAvoidsAndFavors" type="xs:boolean"/>
<xs:element minOccurs="0" name="VehicleType" type="tns:VehicleType"/>
</xs:sequence>
</xs:complexType>
<xs:element name="RouteOptions" nillable="true" type="tns:RouteOptions"/>
```

RouteOptions Members

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
                        <td><code>BordersOpen</code></td>
                        <td>A boolean value. Gets or sets a value indicating whether borders are open for travel. The default is true.
                            <br>
                            Usage:<span>bordersOpen = true;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>ClassOverrides</code></td>
                        <td>An enumeration of ClassOverrideType. Gets or sets the enumeration of class overrides. This is an optional field and the default is None.
                            <br>
                            Values:
                            <table>
                                <thead>
                                    <tr>
                                        <th>Member Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>None</td>
                                        <td>0</td>
                                        <td>Indicates that no class overrides are present. This is the default value.</td>
                                    </tr>
                                    <tr>
                                        <td>FiftyThreeFoot</td>
                                        <td>1</td>
                                        <td>Indicates a 53' class override.</td>
                                    </tr>
                                    <tr>
                                        <td>NationalNetwork</td>
                                        <td>2</td>
                                        <td>Indicates a National Network class override.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>ClassOverrides = ServiceRef.ClassOverrideType.FiftyThreeFoot;</span>
                        </td>
                        <td>N</td>
                    </tr>
          <tr>
            <td><code>CustomRoadSpeeds</code></td>
            <td>
              An array of <code>RoadSpeedBase</code> objects containing custom road speeds per road category in mph. This is an optional field and the default is an empty list.
              <br>
              <code>RoadSpeedBase</code>:
              <table>
                    <thead>
                    <tr>
                    <th>Member Name</th>
                    <th>Value</th>
                    <th>Description</th>
                    </tr>
          </thead>
                    <tbody>
                    <tr>
                    <td>RoadCategory</td>
                    <td>InterStateRural</td>
                    <td>Indicates the road class which is of type <code>RoadType</code>.</td>
                    </tr>
                    <tr>
                    <td>Speed</td>
                    <td>35</td>
                    <td>Indicates the speed of the road <b>in mph</b>.</td>
                    </tr>
                    </tbody>
              </table>
              <br>
              <code>RoadType</code>:
              <table>
                    <thead>
                    <tr>
                    <th>Member Name</th>
                    <th>Value</th>
                    </tr>
                    </thead>
                    <tbody>
                    <tr>
                    <td>InterStateRural</td>
                    <td>1</td>
                    </tr>
                    <tr>
                    <td>DividedRural</td>
                    <td>3</td>
                    </tr>
                    <tr>
                    <td>PrimaryRural</td>
                    <td>4</td>
                    </tr>
                    <tr>
                    <td>FerriesRural</td>
                    <td>5</td>
                    </tr>
                    <tr>
                    <td>SecondaryRural</td>
                    <td>6</td>
                    </tr>
                    <tr>
                    <td>RampRural</td>
                    <td>7</td>
                    </tr>
                    <tr>
                    <td>LocalRural</td>
                    <td>6</td>
                    </tr>
                    <tr>
                    <td>InterStateUrban</td>
                    <td>10</td>
                    </tr>
                    <tr>
                    <td>DividedUrban</td>
                    <td>12</td>
                    </tr>
                    <tr>
                    <td>PrimaryUrban</td>
                    <td>13</td>
                    </tr>
                    <tr>
                    <td>FerriesUrban</td>
                    <td>14</td>
                    </tr>
                    <tr>
                    <td>SecondaryUrban</td>
                    <td>15</td>
                    </tr>
                    <tr>
                    <td>RampUrban</td>
                    <td>16</td>
                    </tr>
                    <tr>
                    <td>LocalUrban</td>
                    <td>17</td>
                    </tr>
                    </tbody>
              </table>
            </td>
            <td>N</td>
          </tr>
                    <tr>
                        <td><code>DistanceUnits</code></td>
                        <td>An enumeration of DistanceUnits. Gets or sets the distance units to miles(default) or kilometers. The unit of measure to calculate route, and when drawing a map, the scale bar legend will use these distance units.
                            <br>
                            Values:
                            <table>
                                <thead>
                                    <tr>
                                        <th>Members Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>Miles</td>
                                        <td>0</td>
                                        <td>Indicates miles should be used.</td>
                                    </tr>
                                    <tr>
                                        <td>Kilometers</td>
                                        <td>1</td>
                                        <td>Indicates kilometers should be used.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>DistanceUnits = ServiceRef.DistanceUnits.Miles;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>HazMatType</code></td>
                        <td>An enumeration of HazMatType. Gets or sets the hazardous material type. The default is none
                            <br>
                            Values:
                            <table>
                                <thead>
                                    <tr>
                                        <th>Members Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>None</td>
                                        <td>0</td>
                                        <td>Indicates that there is no hazardous material.</td>
                                    </tr>
                                    <tr>
                                        <td>General</td>
                                        <td>1</td>
                                        <td>Indicates general hazardous materials.</td>
                                    </tr>
                                    <tr>
                                        <td>Caustic</td>
                                        <td>2</td>
                                        <td>Indicates caustic hazardous materials.</td>
                                    </tr>
                                    <tr>
                                        <td>Explosives</td>
                                        <td>3</td>
                                        <td>Indicates explosive hazardous materials.</td>
                                    </tr>
                                    <tr>
                                        <td>Flammable</td>
                                        <td>4</td>
                                        <td>Indicates flammable hazardous materials.</td>
                                    </tr>
                                    <tr>
                                        <td>Inhalants</td>
                                        <td>5</td>
                                        <td>Indicates that the hazardous materials are inhalants.</td>
                                    </tr>
                                    <tr>
                                        <td>Radioactive</td>
                                        <td>6</td>
                                        <td>Indicates radioactive hazardous materials.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>HazMatType = ServiceRef.HazMatType.Caustic;</span>
                            <br>
                            See details in <a href="/restful-apis/developer-guide/appendix/glossary/#hazmat">Glossary</a>.
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>HighwayOnly</code></td>
                        <td>A boolean value. Gets or sets a value indicating whether to use highways only. Street-level routing is available for premium account only.
                            <br>
                            Usage:<span>HighwayOnly = true;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>HubRouting</code></td>
                        <td>A boolean value. Gets or sets a value indicating whether or not to enable hub routing. The default is false to disable hub routing.
                            <br>
                            Usage:<span>HubRouting = true;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>OverrideRestrict</code></td>
                        <td>A boolean value. Gets or sets a value indicating whether or not to override truck restrictions. The default is false to keep the restrictions.
                            <br>
                            Usage:<span>OverrideRestrict = true;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>RouteOptimization</code></td>
                        <td>An enumeration of RouteOptimizeType. Gets or sets the method by which to optimize the route stops. Default is None
                            <br>
                            Values:
                            <table>
                                <thead>
                                    <tr>
                                        <th>Members Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>None</td>
                                        <td>0</td>
                                        <td>Indicates to not use any stop optimization.</td>
                                    </tr>
                                    <tr>
                                        <td>ThruAll</td>
                                        <td>1</td>
                                        <td>Indicates that all of the input stops should be resequenced for the most optimal sequence.</td>
                                    </tr>
                                    <tr>
                                        <td>DestinationFixed</td>
                                        <td>2</td>
                                        <td>Indicates that the destination remain fixed, but all other input stops should be resequenced for the most optimal sequence.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>RouteOptimization=RouteOptimizeType.DestinationFixed;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>RoutingType</code></td>
                        <td>An enumeration of RoutingType. Gets or sets the type of routing desired. Versions prior to 27 do not support fastest routing, practical will be used if fastest is supplied.
                            <br>
                            Values:
                            <table>
                                <thead>
                                    <tr>
                                        <th>Members Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>Practical</td>
                                        <td>0</td>
                                        <td>Indicates that routing should be optimized to minimize time and cost.</td>
                                    </tr>
                                    <tr>
                                        <td>Shortest</td>
                                        <td>1</td>
                                        <td>Indicates that routing should be optimized for shortest distance.</td>
                                    </tr>
                                    <tr>
                                        <td>Fastest</td>
                                        <td>2</td>
                                        <td>Indicates that routing should be optimized to minimize time based on supplied estimated time options in conjunction with Inrix traffic data.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>RoutingType=RoutingType.Practical;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>TollDiscourage</code></td>
                        <td>A boolean value. Gets or sets a value indicating whether or not tolls should be discouraged on the route. The default is false.
                            <br>
                            Usage:<span>TollDiscourage=true;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>TruckCfg</code></td>
                        <td>A system object. Gets or sets the truck configuration.
                            <br>
                            Usage:<span>ServiceRef.TruckConfigCfg=new Serv.TruckConfig(){};</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>UseAvoidsAndFavors</code></td>
                        <td>A boolean value. Gets or sets a value indicating whether or not to use avoids and favors. Available for premium account types only.
                            <br>
                            Usage:<span>UseAvoidFavors=false;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>VehicleType</code></td>
                        <td>An enumeration of vehicleType. Gets or sets the type of the vehicle.
                            <br>
                            Values:
                            <table>
                                <thead>
                                    <tr>
                                        <th>Members Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>Truck</td>
                                        <td>0</td>
                                        <td>Indicates a truck.</td>
                                    </tr>
                                    <tr>
                                        <td>LightTruck</td>
                                        <td>1</td>
                                        <td>Indicates a light truck.</td>
                                    </tr>
                                    <tr>
                                        <td>Auto</td>
                                        <td>2</td>
                                        <td>Indicates an automobile.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <br>
                            Usage:<span>VehicleType = ServiceRef.VehicleType.Truck;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>ElevLimit</code></td>
                        <td>
                            A boolean value. Gets or sets a value indicating elevation limit when generating a route.
                            <br>
                            Elevation units can be either meters or feet determined by <code>DistanceUnits</code>.
                            <br>
                            Limit will be ignored if routing is deemed impractical with the limit, or a stop is located at an elevation higher than the limit.
                            <br>
                            Usage:<span>elevLimit = true;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>FerryDiscourage</code></td>
                        <td>
                            A boolean value. Gets or sets a value indicating Whether or not to avoid ferries while routing. The default is false to disable avoiding ferries.
                            <br>
                            Usage:<span>FerryDiscourage = true;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>SideOfStreetAdherence</code></td>
                        <td>
                            An enumeration value. How strict to be in order to avoid the destination being on the opposite side of the street.
                            <br>
                            <table>
                                <thead>
                                    <tr>
                                        <th>Members Name</th>
                                        <th>Value</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>Off</td>
                                        <td>0</td>
                                        <td></td>
                                    </tr>
                                    <tr>
                                        <td>Minimal</td>
                                        <td>1</td>
                                        <td></td>
                                    </tr>
                                    <tr>
                                        <td>Moderate</td>
                                        <td>2</td>
                                        <td></td>
                                    </tr>
                                    <tr>
                                        <td>Average</td>
                                        <td>3</td>
                                        <td></td>
                                    </tr>
                                    <tr>
                                        <td>Strict</td>
                                        <td>4</td>
                                        <td></td>
                                    </tr>
                                    <tr>
                                        <td>Adhere</td>
                                        <td>5</td>
                                        <td></td>
                                    </tr>
                                    <tr>
                                        <td>StronglyAdhere</td>
                                        <td>6</td>
                                        <td></td>
                                    </tr>
                                </tbody>
                            </table>
                            Usage:<span>SideOfStreetAdherence = SideOfStreetAdherence.Minimal;</span>
                        </td>
                        <td>N</td>
                    </tr>
                    <tr>
                        <td><code>GovernorSpeedLimit</code></td>
                        <td>
                            An Integer value. Maximum average road speed to use in route calculations that overrides all other road speeds when they are above this value.
                            <br>
                            Valid value is between 1 and 100 mph, or 1 and 161kph determined by <code>DistanceUnits</code>.
                            <br>
                            Usage:<span>GovernorSpeedLimit = 50;</span>
                        </td>
                        <td>N</td>
                    </tr>
                </tbody>
            </table>

### TruckCfg

The TruckConfig structure is used to pass all data associated with the truck configuration(vehicle dimension, weight and number of axles) for routing and tolls.

```xml
<xs:complexType name="TruckConfig">
<xs:sequence>
<xs:element minOccurs="0" name="Axles" type="xs:int"/>
<xs:element minOccurs="0" name="Height" nillable="true" type="xs:string"/>
<xs:element minOccurs="0" name="LCV" type="xs:boolean"/>
<xs:element minOccurs="0" name="Length" nillable="true" type="xs:string"/>
<xs:element minOccurs="0" name="Units" type="tns:VehicleDimUnits"/>
<xs:element minOccurs="0" name="Weight" nillable="true" type="xs:string"/>
<xs:element minOccurs="0" name="Width" nillable="true" type="xs:string"/>
</xs:sequence>
</xs:complexType>
<xs:element name="TruckConfig" nillable="true" type="tns:TruckConfig"/>
```

### TruckCfg Members

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
      <td><code>Axles</code></td>
      <td>
        An integer value. Gets or sets the number of axles on the truck. If TrailerConfig.MaxAxles is also set, then the two values must add up to the total axle count of the vehicle. Acceptable values are 2 through 14. The default value is 5.
        <br />
        Usage:<span>Axles = 2;</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Height</code></td>
      <td>
        A string value. Gets or sets the height of the truck in feet and inches, or meters depending upon the units. If TrailerConfig.MaxHeight is also set, then the greater of the two will be used.
        <br />
        Valid range is between 5' and 15' for English Unit, or between 1.524 and 5 meters for Metric Unit.
        <br />
        The default is 13'6" in all regions except Europe, which is 12'6".
        <br />
        Usage:<span>Height = "13'6"</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>LCV</code></td>
      <td>
        A boolean value. Gets or sets a value indicating whether the truck is a multi-trailer or longer combination vehicle. This is used for calculation of toll costs, and only for North region.
        <br />
        Usage:<span>LCV = true;</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Length</code></td>
      <td>
        A string value. Gets or sets the length of the truck in feet or meters, depending upon the units.
        <br />
        Valid range is between 8' and 70' for English Unit, or between 2.4384 and 28 meters for Metric Unit.
        <br />
        Default is 48 feet in all regions except Europe, which is 54'1".
        <br />
        Usage:<span>Length = "53'0";</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Units</code></td>
      <td>
        An enumeration of VehicleDimUnits. Gets or sets the units of measure to be used for the vehicle dimensions.
        <br />
        Values:
        <table>
          <thead>
            <tr>
              <th>Member Name</th>
              <th>Value</th>
              <th>Description</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>English</td>
              <td>0</td>
              <td>Indicates that vehicle dimension units should be English.</td>
            </tr>
            <tr>
              <td>Metric</td>
              <td>1</td>
              <td>Indicates that vehicle dimension units should be metric.</td>
            </tr>
          </tbody>
        </table>
        <br />
        Usage:<span>Units = VehicleDimUnits.English;</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Weight</code></td>
      <td>
        A string value. Gets or sets the weight of the truck in pounds or kilos, depending upon units. If TrailerConfig.MaxWeight is also set, then the two values will be added up to determine the total vehicle weight.
        <br />
        Valid range is between 1500 and 156470 lbs for English Unit, or between 680.39 and 60000 kgs for Metric Unit.
        <br />
        The default value is 80,000 pounds for all regions.
        <br />
        Usage:<span>Weight = "132000";</span>
      </td>
      <td>N</td>
    </tr>
    <tr>
      <td><code>Width</code></td>
      <td>
        A string value. Gets or sets the width of the truck in inches or meters, depending upon units.
        <br />
        Valid range is between 60" and 102" for English Unit, or between 1.524 and 3 meters for Metric Unit.
        <br />
        The default value is 96" for all regions.
        <br />
        Usage:<span>Width = "102\"";</span>
      </td>
      <td>N</td>
    </tr>
  </tbody>
</table>

### ActionType

Gets or sets the operation to perform; either save the custom place or delete it.

**ActionType Enumeration(Used for AvoidFavor & SetCustomPlace)**

| Member Name | Value | Description       |
| ----------- | ----- | ----------------- |
| Save        | 0     | Perform a save.   |
| Delete      | 1     | Perform a delete. |
