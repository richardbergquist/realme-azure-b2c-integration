# Azure Active Directory B2C - RealMe Login service - ITE Integration

This wiki explains how to integrate Real Me Login in the RealMe ITE environment:

1. Purchase a certificate: it will be used to sign the SAML requests.

2. Download the [ITE login service IdP metadata zip file](https://developers.realme.govt.nz/how-to-integrate/core-steps-for-technical-integration). It contains the ITE SAML Metadata

3. Follow the integration steps as describe for the MTS environment:

- Use your own SAML messaging key pair. Do not reuse the MTS key pair certificate provided by RealMe.
- Use the correct provided RealMe ITE SAML metadata file rather than the previous MTS SAML metadata file.

4. Create an ITE Integration Request on the [RealMe developers website](https://developers.realme.govt.nz/)
