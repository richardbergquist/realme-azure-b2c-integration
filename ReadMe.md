# Azure Active Directory B2C - RealMe Integration

## About
This wiki explains how to configure and integrate Azure AD B2C as a SAML service provider into the New Zealand government RealMe service, operated by the Department of Internal Affairs (DIA). 

It provides 
- Sample Azure AD B2C custom policies.
- Step by step guides with links to Microsoft documentation.
- References into RealMe developer guides.
- Information on the exact type of attributes returned from RealMe and how to convert them into claims. 
- Sample Azure Functions to extend the integration for the parsing of identity information in the response.


## Attribution
This wiki is forked from the [original repo](https://github.com/realme-govt-nz/azure-b2c-integration). 

The purpose for forking it is to allow for updates and corrections as the original repo has grown out of maintenance and has some updates required to reflect the current state configuration of the RealMe services.


## RealMe Services and Environments
There are the following RealMe services and environments.

1. RealMe Login:
- [MTS: Configure RealMe Login as an external SAML IdP](./Login-MTS.md)
- [ITE integration](./Login-ITE.md)

2. RealMe Assertion:
- [MTS: Configure RealMe Assertion as an external SAML IdP](./Assertion-MTS.md)
- [ITE integration](./Assertion-ITE.md)

## Supporting Guides
- [Sample SAML response](./SAML-Samples/sample-saml-assert-response.md) from the RealMe Assertion Service
- [D365 portal integration](./D365.md)

## Useful links

### Azure Active Directory B2C Links
- [Azure Active Directory B2C Overview](https://azure.microsoft.com/en-us/services/active-directory-b2c/)
- [Custom policies in Azure Active Directory B2C](https://docs.microsoft.com/en-us/azure/active-directory-b2c/active-directory-b2c-overview-custom)
- [Define a SAML technical profile in an Azure Active Directory B2C custom policy](https://docs.microsoft.com/en-us/azure/active-directory-b2c/saml-technical-profile)
- [Azure Active Directory B2C: Collecting Logs](https://docs.microsoft.com/en-us/azure/active-directory-b2c/active-directory-b2c-troubleshoot-custom)

### RealMe Links
- [RealMe for developers](https://developers.realme.govt.nz/)
- [RealMe login service MTS](https://mts.realme.govt.nz/logon-mts/home)
- [RealMe assertion service MTS](https://mts.realme.govt.nz/realme-mts/home/information.xhtml)
