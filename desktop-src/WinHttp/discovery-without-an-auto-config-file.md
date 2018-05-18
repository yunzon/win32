---
Description: 'If a proxy auto-configuration file has not been deployed on the local network, WinHttpGetProxyForUrl cannot find a proxy server.'
ms.assetid: 'a170e63a-8586-47df-af5e-4ee3621795b2'
title: 'Discovery Without an Auto-Config File'
---

# Discovery Without an Auto-Config File

If a proxy auto-configuration file has not been deployed on the local network, [**WinHttpGetProxyForUrl**](winhttpgetproxyforurl.md) cannot find a proxy server. If **WinHttpGetProxyForUrl** fails, there are several possible fall-back strategies for obtaining a viable proxy configuration, depending on its runtime environment. These include prompting for the proxy setting through a user interface, requiring someone to store the proxy configuration in the registry using the WinHTTP "ProxyCfg.exe" utility, or using [**WinHttpGetIEProxyConfigForCurrentUser**](winhttpgetieproxyconfigforcurrentuser.md) to check whether a proxy server is listed in Internet Explorer's settings.

It is possible that there is no proxy auto-configuration file because the client has a direct Internet connection, such as through an ISP, and does not need a proxy server.

A proxy server may be required, on the other hand, but the local network may not support WPAD. In this case, the proxy configuration must be obtained from the user or found somewhere on the client machine.

A WinHTTP-based application running in a middle-tier server environment, such as a COM+ or ASP application, should rely on a server administrator setting a default proxy configuration in the registry using the "ProxyCfg.exe" utility. This default configuration information can then be retrieved either by using the [**WinHttpGetDefaultProxyConfiguration**](winhttpgetdefaultproxyconfiguration.md) function, or simply by specifying the **WINHTTP\_ACCESS\_TYPE\_PRECONFIG** flag in the [**WinHttpOpen**](winhttpopen.md) call.

On the other hand, a WinHTTP application running on a client desktop machine can attempt to examine Internet Explorer's proxy settings. [**WinHttpGetIEProxyConfigForCurrentUser**](winhttpgetieproxyconfigforcurrentuser.md) fills in a caller-supplied [**WINHTTP\_CURRENT\_USER\_IE\_PROXY\_CONFIG**](winhttp-current-user-ie-proxy-config.md) structure with the current user's Internet Explorer proxy settings for the current active connection (dial-up, VPN or LAN). This configuration may indicate that auto-detection is used, or it may specify a URL for a proxy auto-configuration file, or it may specify an actual proxy server to use, or it may specify a combination of the three. If this information includes a PAC URL or a proxy server, the WinHTTP application can try using those.

A sample that uses the [**WinHttpGetProxyForUrl**](winhttpgetproxyforurl.md) and [**WinHttpGetIEProxyConfigForCurrentUser**](winhttpgetieproxyconfigforcurrentuser.md) functions can be found in the Platform Software Development Kit (SDK) WinHTTP samples.

 

 


