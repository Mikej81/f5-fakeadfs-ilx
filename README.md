# f5-fakeadfs-ilx

This was created for iRulesLX on BIG-IP, for replacement of AD FS to use as a Trusted Identity Provider for SharePoint.
Modified to support multiple FQDNs and Trusted Identity Providers on a single virtual server.  This is still SP initiated.

## Installation
```
  import tgz to BIG-IP - See included PDF
```

May work better building from scratch in some environments.

https://devcentral.f5.com/articles/big-ip-iruleslx-fakeadfs-ws-federation-saml11-24608

## Example Configuration
* SharePoint https://github.com/Mikej81/f5-fakeadfs-ilx/blob/master/F5%20ADFS%20iRulesLX%20Implementation.pdf
* Exchange https://github.com/Mikej81/f5-fakeadfs-ilx/blob/master/EXCHANGE.md

## Usage
IDP initiated use-case requires a single VS, it does not require any SAML IDP or SP configurations as the initial Client Auth can be anything, the WS-Fed assertion is generated on the Server side, and posted to the Application.

For multiple VS scenarios, see included PDF.

Etensive notes are in the code.

## TODO
Working on adding Ws-Trust support.  FederationMetadata is mostly complete, endpoints currently have to be changed in federationmetadata.template, but this will be dynamic in later code updates.

## Release History
* 0.1.0 Initial release
* 0.2.0 Minor tweaks
* 0.3.0 Multiple FQDN Support added - Jeff larmore
* 0.3.1 STS Federation Metadata Support added; any endpoint ending with FederationMetadata.xml
* 0.4.0 Extensive code changes, cleanup, and other modifications to support 13.x and fix IDP/SP initiated paths.
* 0.5.0 WS-Trust - RST and RSTR generation, not added to an ILX release yet.
