---
title: "<transport> of <wsHttpBinding>"
ms.date: "03/30/2017"
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
---

# \<transport> of \<wsHttpBinding>

Defines authentication settings for the HTTP transport.

\<system.serviceModel>\
\<bindings>\
\<wsHttpBinding>\
\<binding>\
\<security>\
\<transport>

## Syntax

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## Type

<xref:System.ServiceModel.HttpTransportSecurity>

## Attributes and Elements

The following sections describe attributes, child elements, and parent elements.

### Attributes

|Attribute|Description|
|---------------|-----------------|
|`clientCredentialType`|Specifies the credential used to authenticate the client to the service. This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.|
|`proxyCredentialType`|Specifies the credential used to authenticate the client to a domain proxy. This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.|
|`realm`|A string that specifies the authentication realm for digest or basic authentication. The default is an empty string.<br /><br /> An authentication realm specifies at least the name of the host that performs the authentication. It can also specify a collection of users that has access. A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.|
|`policyEnforcement`|This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.<br /><br /> 1.  Never – The policy is never enforced (Extended Protection is disabled).<br />2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.<br />3.  Always – The policy is always enforced. Clients which don’t support Extended Protection will fail to authenticate.|

## clientCredentialType Attribute

|Value|Description|
|-----------|-----------------|
|`None`|Security is disabled.|
|`Basic`|Uses basic authentication.|
|`Digest`|Uses digest authentication.|
|`Ntlm`|Uses NTLM authentication as a fallback with a Windows domain.|
|`Windows`|Uses integrated Windows authentication.|
|`Certificate`|Uses X.509 certificates to authenticate the client.|

## proxyCredentialType Attribute

|Value|Description|
|-----------|-----------------|
|`None`|Security is disabled.|
|`Basic`|Uses basic authentication.|
|`Digest`|Uses digest authentication.|
|`Ntlm`|Uses NTLM as a fallback with a Windows domain.|
|`Windows`|Uses integrated Windows authentication.|
|`Certificate`|Uses X.509 certificates to authenticate the client.|

### Child Elements

None.

### Parent Elements

|Element|Description|
|-------------|-----------------|
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).|

## See also

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Bindings](../../../../../docs/framework/wcf/bindings.md)
- [Configuring System-Provided Bindings](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Using Bindings to Configure Services and Clients](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
