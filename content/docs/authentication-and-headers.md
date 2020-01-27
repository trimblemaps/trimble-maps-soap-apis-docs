---
title: Authentication and Headers
weight: 1
---

The base URI to access SOAP requests is:
`https://pcmiler.alk.com/apis/soap/v1.0/service.svc`

### The SOAPHeader Element

The SOAP header element contains application-specific information (like authentication) about the SOAP message. If the header element is present, it must be the first element in the envelope element.<br>

**Note**: All immediate child elements of the header element must be namespace-qualified.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">https://pcmiler.alk.com/APIs/v1.0/IService/GetReports</Action>
      <h:AuthHeader xmlns="http://www.alk.com" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:h="http://www.alk.com">
        <Authorization>APIKeyHere</Authorization>
        <Date>Tue, 12 Aug 2014 14:18:50 GMT</Date>
      </h:AuthHeader>
    </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
<GetReports xmlns="https://pcmiler.alk.com/APIs/v1.0">
```

#### The mustUnderstand Attribute

The SOAP mustUnderstand attribute can be used to indicate whether a header entry is mandatory or optional for the recipient to process. It is mandatory to send a SOAPHeader to the WCF service.
If you add mustUnderstand="1" to a child element of the header element, it indicates that the receiver processing the header must recognize the element. If the receiver does not recognize the element, it will fail when processing the header.

#### Syntax

```js
soap: mustUnderstand = "0|1";
```

#### AuthHeader

The AuthHeader is required to authenticate the login to the WCF web server. It is contained in the SoapHeader element for every request.

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns="http://www.alk.com" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" elementFormDefault="qualified" targetNamespace="http://www.alk.com">
  <xs:element name="AuthHeader">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="Authorization" type="xs:string"/>
        <xs:element name="Date" type="xs:string"/>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

<style>
main th:first-of-type {min-width:139px; max-width:139px; width:139px;}
</style>

#### AuthHeader Elements

| Element       | Definition | Required |
| ------------- | ---------- | -------- |
| Authorization |            | Y        |
| Date          |            | Y        |

Creating AuthHeader

```js
public AuthHeader AuthHeader
{
  get
  {
  AuthHeader header = null;
  if (!string.IsNullOrEmpty(APIKey))
  {
    header = new AuthHeader();
    header.Date = DateTime.UtcNow.ToString(HEADER_TIMESTAMP_FORMAT); header.Authorization = APIKey;
  }
  else
  {
    throw new PCMilerException("Could not generate AuthHeader. Not all values have been defined.");
  }
  return header;
  }
}
```

### The Request Elements

#### RequestHeader

Represents header information that is part of every web service request.

**Schema**

```xml
<xs:complexType name="RequestHeader">
  <xs:sequence>
    <xs:element minOccurs="0" name="DataVersion" nillable="true" type="xs:string"/>
    <xs:element minOccurs="0" name="RequestType" nillable="true" type="xs:string"/>
  </xs:sequence>
</xs:complexType>
<xs:element name="RequestHeader" nillable="true" type="tns:RequestHeader"/>
```

**RequestHeader Elements**

| Element       | Definition                                                                                                                                                                         | Required |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `DataVersion` | String value. The data version can be any version number, starting with PCM18, for users with access to multiple versions of PC\*MILER. Set to "Current" for current quarter data. | N        |
| `RequestType` | String value. The AboutService API requires this to be "AboutMapService". All other APIs do not validate this and can be any string.                                               | N        |

### ResponseHeader

**ResponseHeader Elements**

| Element       | Definition                                                                                                          |
| ------------- | ------------------------------------------------------------------------------------------------------------------- |
| `DataVersion` | A string. Gets or sets the data version used in the request operation.                                              |
| `Errors`      | A list of Errors object<>. Gets or sets a collection of errors that may have occurred during the request operation. |
| `Success`     | A boolean value. Gets or sets the response type which is the same value that the user passed in for the request.    |
| `Type`        | A string. Gets or sets the response type which is the same value that the user passed in for the request type.      |

**Error Members**

| Element           | Definition                                                                                                                                                                                                             |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Code`            | An enumeration of PcmwsExceptionCode. Gets or sets the data version used in the request operation.<br>Usage: `var errCode = new ServiceReference.PcmwsExceptionCode();<br>errorCode = response.Header.Errors[0].Code;` |
| `Description`     | A string. Gets or sets the detailed error description.<br>Usage: `var description = response.Header.Errors[0].Description;`                                                                                            |
| `LegacyErrorCode` | An Integer. Gets or sets the legacy error code which is an integer valued code that would have been returned in PC\*MILER Web Services V25 and earlier.<br>Usage: `int Xresponse.Header.Errors[0].legacyErrorCode;`    |
| `Type`            | Gets or sets whether the error is an exception or a warning.<br>Usage: `string type = response.Header.Errors[0].type;`                                                                                                 |
