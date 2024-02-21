### Azure Active Directory B2C - RealMe Integration


This wiki is forked from the original repo here: https://github.com/realme-govt-nz/azure-b2c-integration

The purpose for forking it is to add updates and corrections as the original repo has grown out of maintenance.

This wiki explains how to configure and integrate Azure AD B2C as a SAML service provider into DIA's RealMe serice. 
It provides Azure AD B2C custom policies (and Azure Functions) to do so.

There are the following RealMe services and environments.

1. RealMe Login:
- [MTS: Configure RealMe Login as an external SAML IdP](./Login-MTS.md)
- [ITE integration](./Login-ITE.md)

2. RealMe Assertion:
- [MTS: Configure RealMe Assertion as an external SAML IdP](./Assertion-MTS.md)
- [ITE integration](./Assertion-ITE.md)

### Miscellaneous
- [D365 portal integration](./D365.md)

### Useful links

Azure Active Directory B2C:
- [Azure Active Directory B2C Overview](https://azure.microsoft.com/en-us/services/active-directory-b2c/)
- [Custom policies in Azure Active Directory B2C](https://docs.microsoft.com/en-us/azure/active-directory-b2c/active-directory-b2c-overview-custom)
- [Define a SAML technical profile in an Azure Active Directory B2C custom policy](https://docs.microsoft.com/en-us/azure/active-directory-b2c/saml-technical-profile)
- [Azure Active Directory B2C: Collecting Logs](https://docs.microsoft.com/en-us/azure/active-directory-b2c/active-directory-b2c-troubleshoot-custom)

Real Me:
- [RealMe for developers](https://developers.realme.govt.nz/)
- [RealMe login service MTS](https://mts.realme.govt.nz/logon-mts/home)
- [RealMe assertion service MTS](https://mts.realme.govt.nz/realme-mts/home/information.xhtml)
