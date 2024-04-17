# Sample SAML Response for Assert

## About

The following is a decrypted SAML response from the RealMe Assert MTS. 
It shows how the FIT and the identity attribute payloads are passed back.

This guide is useful because the SAML messaging specifications for Login and Assert are not published on the [RealMe for developers](https://developers.realme.govt.nz/) site. For Azure AD B2C to pass the claims back it needs to know the actual names of the SAML attributes, which are not explicity stated on the RealMe developers site. The only way is to use developer tools to debug and inspect traffic to find out what an actual decrypted response looks like.

## Sample SAML Response

The SAML response from RealMe is returned with the Assertion XML encrypted, which makes it hard to understand the attributes being passed back. The following is what the response looks after decryption, with the SAML attributes visible.

```xml


<samlp:Response xmlns:saml="urn:oasis:names:tc:SAML:2.0:assertion"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:samlp="urn:oasis:names:tc:SAML:2.0:protocol" ID="_d4eed010-0ba0-4185-bac3-45840e78c346" InResponseTo="_baee5579-0b33-46db-812d-eae91a7debb3" Version="2.0" IssueInstant="2024-02-19T21:25:43.5109598Z" Destination="https://b2cdirnprdcoldir.b2clogin.com/b2cdirnprdcoldir.onmicrosoft.com/B2C_1A_TrustFrameworkBase/samlp/sso/assertionconsumer">
    <saml:Issuer Format="urn:oasis:names:tc:SAML:2.0:nameid-format:entity">https://login.mts.realme.govt.nz/4af8e0e0-497b-4f52-805c-00fa09b50c16/B2C_1A_DIA_RealMe_MTSAssertionService</saml:Issuer>
    <samlp:Status>
        <samlp:StatusCode Value="urn:oasis:names:tc:SAML:2.0:status:Success"/>
    </samlp:Status>
    <saml:Assertion ID="_2ade6791-bddf-4485-b4e6-49817ccaa4da" Version="2.0" IssueInstant="2024-02-19T21:25:43.2389555Z">
        <saml:Issuer Format="urn:oasis:names:tc:SAML:2.0:nameid-format:entity">https://login.mts.realme.govt.nz/4af8e0e0-497b-4f52-805c-00fa09b50c16/B2C_1A_DIA_RealMe_MTSAssertionService</saml:Issuer>
        <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">
            <SignedInfo>
                <CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>
                <SignatureMethod Algorithm="http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"/>
                <Reference URI="#_2ade6791-bddf-4485-b4e6-49817ccaa4da">
                    <Transforms>
                        <Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature"/>
                        <Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#">
                            <InclusiveNamespaces xmlns="http://www.w3.org/2001/10/xml-exc-c14n#" PrefixList="saml samlp xenc xs"/>
                        </Transform>
                    </Transforms>
                    <DigestMethod Algorithm="http://www.w3.org/2001/04/xmlenc#sha256"/>
                    <DigestValue>dX8y97VlMVM92iFM5FsWpZLOxb06TGISKgXssiAEAuI=</DigestValue>
                </Reference>
            </SignedInfo>
            <SignatureValue>--snipped--</SignatureValue>
            <KeyInfo>
                <X509Data>
                    <X509Certificate>--snipped--</X509Certificate>
                </X509Data>
            </KeyInfo>
        </Signature>
        <saml:Subject>
            <saml:NameID NameQualifier="https://login.mts.realme.govt.nz/4af8e0e0-497b-4f52-805c-00fa09b50c16/B2C_1A_DIA_RealMe_MTSAssertionService" SPNameQualifier="https://dia.govt.nz/celebrants/celebrantsonline" Format="urn:oasis:names:tc:SAML:2.0:nameid-format:transient">7f969200-8ed5-4ebe-bdfb-017fd4a7dd0b</saml:NameID>
            <saml:SubjectConfirmation Method="urn:oasis:names:tc:SAML:2.0:cm:bearer">
                <saml:SubjectConfirmationData NotOnOrAfter="2024-02-19T21:30:43.2389555Z" Recipient="https://b2cdirnprdcoldir.b2clogin.com/b2cdirnprdcoldir.onmicrosoft.com/B2C_1A_TrustFrameworkBase/samlp/sso/assertionconsumer" InResponseTo="_baee5579-0b33-46db-812d-eae91a7debb3"/>
            </saml:SubjectConfirmation>
        </saml:Subject>
        <saml:Conditions NotBefore="2024-02-19T21:15:43.2389555Z" NotOnOrAfter="2024-02-19T21:30:43.2389555Z">
            <saml:AudienceRestriction>
                <saml:Audience>https://dia.govt.nz/celebrants/celebrantsonline</saml:Audience>
            </saml:AudienceRestriction>
        </saml:Conditions>
        <saml:AuthnStatement SessionIndex="76cdfd46-3b7f-4004-b6ba-21c561e306b7" AuthnInstant="2024-02-19T21:25:43.2389555Z">
            <saml:AuthnContext>
                <saml:AuthnContextClassRef>urn:nzl:govt:ict:stds:authn:deployment:GLS:SAML:2.0:ac:classes:ModStrength</saml:AuthnContextClassRef>
            </saml:AuthnContext>
        </saml:AuthnStatement>
        <saml:AttributeStatement xmlns:xs="http://www.w3.org/2001/XMLSchema">
            <saml:Attribute Name="urn:nzl:govt:ict:stds:authn:attribute:igovt:IVS:FIT" NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:uri" FriendlyName="FIT">
                <saml:AttributeValue xsi:type="xs:string">AZUE58D73D4582C49DD9D653F468BEC78DE</saml:AttributeValue>
            </saml:Attribute>
            <saml:Attribute Name="urn:nzl:govt:ict:stds:authn:safeb64:attribute:igovt:IVS:Assertion:JSON:Identity" NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:uri">
                <saml:AttributeValue xsi:type="xs:string">eyJuYW1lIjp7ImZpcnN0TmFtZSI6IkVkbXVuZCIsIm1pZGRsZU5hbWUiOiJQZXJjaXZhbCIsImxhc3ROYW1lIjoiSGlsbGFyeSIsIm5hbWVEaXNwdXRlZCI6ZmFsc2V9LCJwbGFjZU9mQmlydGgiOnsibG9jYWxpdHkiOiJBdWNrbGFuZCIsImNvdW50cnkiOiJOZXcgWmVhbGFuZCIsInBsYWNlT2ZCaXJ0aERpc3B1dGVkIjpmYWxzZX0sImdlbmRlciI6eyJnZW5kZXJWYWx1ZSI6Ik0iLCJnZW5kZXJEaXNwdXRlZCI6ZmFsc2V9LCJkYXRlT2ZCaXJ0aCI6eyJkYXRlT2ZCaXJ0aFZhbHVlIjoiMTkxOS0wNy0yMCIsImRhdGVPZkJpcnRoRGlzcHV0ZWQiOmZhbHNlfX0=</saml:AttributeValue>
            </saml:Attribute>
            <saml:Attribute Name="urn:nzl:govt:ict:stds:authn:safeb64:attribute:NZPost:AVS:Assertion:JSON:Address" NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:uri">
                <saml:AttributeValue xsi:type="xs:string">eyJzdHJlZXQiOiIxIE1haW4gU3QiLCJzdWJ1cmIiOiJLZWxidXJuIiwiY2l0eSI6IldlbGxpbmd0b24iLCJwb3N0Y29kZSI6IjExMTEiLCJjb3VudHJ5IjoiTlpMIn0=</saml:AttributeValue>
            </saml:Attribute>
        </saml:AttributeStatement>
    </saml:Assertion>
</samlp:Response>

```

## The Federated Identity Tag (FIT)

The Federated Identity Tag "FIT" is returned back as a SAML attribute called:

`urn:nzl:govt:ict:stds:authn:attribute:igovt:IVS:FIT`

This is a unique identifier of the RealMe identity to the service provider. It has the property that it is persistently returned for the same identity to the same service provider. However the value is not reused across service providers as part of a privacy by design feature to prevent data matching. In identity terms this is known as a pairwise identifier.

## The Identity Payload

Note that the identity payload is returned back as a SAML attribute called:

`urn:nzl:govt:ict:stds:authn:safeb64:attribute:igovt:IVS:Assertion:JSON:Identity`

```xml

<saml:Attribute Name="urn:nzl:govt:ict:stds:authn:safeb64:attribute:igovt:IVS:Assertion:JSON:Identity" NameFormat="urn:oasis:names:tc:SAML:2.0:attrname-format:uri">
                <saml:AttributeValue xsi:type="xs:string">eyJuYW1lIjp7ImZpcnN0TmFtZSI6IkVkbXVuZCIsIm1pZGRsZU5hbWUiOiJQZXJjaXZhbCIsImxhc3ROYW1lIjoiSGlsbGFyeSIsIm5hbWVEaXNwdXRlZCI6ZmFsc2V9LCJwbGFjZU9mQmlydGgiOnsibG9jYWxpdHkiOiJBdWNrbGFuZCIsImNvdW50cnkiOiJOZXcgWmVhbGFuZCIsInBsYWNlT2ZCaXJ0aERpc3B1dGVkIjpmYWxzZX0sImdlbmRlciI6eyJnZW5kZXJWYWx1ZSI6Ik0iLCJnZW5kZXJEaXNwdXRlZCI6ZmFsc2V9LCJkYXRlT2ZCaXJ0aCI6eyJkYXRlT2ZCaXJ0aFZhbHVlIjoiMTkxOS0wNy0yMCIsImRhdGVPZkJpcnRoRGlzcHV0ZWQiOmZhbHNlfX0=</saml:AttributeValue>
            </saml:Attribute>
```

Obtaining the attribute value and using a base64 decodes gives the following json document which is also formatted for clarity.

```json
{
    "name": {
        "firstName":"Edmund",
        "middleName":"Percival",
        "lastName":"Hillary",
        "nameDisputed":false
    },
    "placeOfBirth":{ 
        "locality":"Auckland",
        "country":"New Zealand",
        "placeOfBirthDisputed":false
    },
    "gender": {
        "genderValue":"M",
        "genderDisputed":false
    },
    "dateOfBirth":{ 
        "dateOfBirthValue":"1919-07-20",
        "dateOfBirthDisputed":false
    }
}
```

## The Address Payload

Note that the address payload is returned back as a SAML attribute called:

`urn:nzl:govt:ict:stds:authn:safeb64:attribute:NZPost:AVS:Assertion:JSON:Address`

Obtaining the saml attribute value and base64 decoding it gives

```json
{"street":"1 Main St","suburb":"Kelburn","city":"Wellington","postcode":"1111","country":"NZL"}
```
