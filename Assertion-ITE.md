# Azure Active Directory B2C - RealMe Assertion service - ITE Integration

This wiki explains how to integrate Real Me Assertion service in the RealMe ITE environment:

## Certificates ordering

Purchase two certificates:

1. The first one will be used to sign the SAML requests.
2. The second one will be used to integrate with the RCMS service (client certificate authentication).

## Configuring the AAD B2C tenant

You will need to generate the metadata file before completing the ITE request.

Follow the integration steps as describe for the MTS environment. You will have to adjust these steps:

1. Use your own SAML messaging key pair. Do not reuse the MTS key pair certificate provided by RealMe.

1. Use the correct provided RealMe ITE SAML metadata file rather than the previous MTS SAML metadata file.

1. In the *TrustFrameworkExtensions.xml* file, check that these lines contain the correct SAML attribute to convert into a claim.   Note that previous versions of the MTS used a different SAML attribute names from ITE and Prod. However they should now align.  Therefore it is worthwhile checking the correct attribute names are being used.

    Make sure these line uses the correct `PartnerClaimType`. Note the required presence of `:JSON:` in the value.

    ```xml
    <OutputClaim ClaimTypeReferenceId="safeB64Identity" PartnerClaimType="urn:nzl:govt:ict:stds:authn:safeb64:attribute:igovt:IVS:Assertion:JSON:Identity" />
    ```

    ```xml
    <OutputClaim ClaimTypeReferenceId="safeB64Address" PartnerClaimType="urn:nzl:govt:ict:stds:authn:safeb64:attribute:NZPost:AVS:Assertion:JSON:Address" />
    ```

### Sample SAML Responses

See the following page for a [sample SAML response](./Sample-Saml-Assert-Response.md) from the RealMe assert service.

For developers there is nothing like seeing the actual decrypted traffic to understanding what is being received and how the custom policies should treat the claims.

## ITE Request

1. Create a new ITE request on the [RealMe developers website](https://developers.realme.govt.nz/):
2. In ITE request, specify:

- `RCMS token required` in the **Opaque token** dropdown.
- `Return JSON identity and/or address` in the **Additional setup description** textarea.

## Decoding identity and address claims

As part of the user journey, you can decode the safe base64 identity following this tutorial: [Decoding RealMe Claims](./Decoding-RealMe-Claims.md)
