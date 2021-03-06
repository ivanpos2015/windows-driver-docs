---
title: Native 802.11 IHV Extensions DLL Overview
description: Native 802.11 IHV Extensions DLL Overview
ms.assetid: 6a3d3e62-41b3-4ae2-a379-273431a36bb1
keywords:
- IHV Extensions DLL WDK Native 802.11 , about Native 802.11 IHV Extensions DLL
- Native 802.11 IHV Extensions DLL WDK , about Native 802.11 IHV Extensions DLL
ms.date: 04/20/2017
ms.localizationpriority: medium
---

# Native 802.11 IHV Extensions DLL Overview




 

Through an IHV Extensions DLL, the independent hardware vendor (IHV) can support the following:

-   Proprietary or non-standard authentication algorithms. Through this support, the IHV Extensions DLL sends and receives all security packets related to the authentication algorithm.

    The IHV Extensions DLL can also support standard authentication algorithms for network configurations that are not supported by the operating system. For example, the DLL can support the Wi-Fi Protected Access with preshared keys (WPA-PSK) authentication algorithm over independent basic service set (IBSS) networks, which is a configuration not supported by Windows Vista.

-   Proprietary or non-standard cipher algorithms. Through this support, the IHV Extensions DLL is responsible for deriving the cipher key and downloading the keys to the Native 802.11 miniport driver.

    The IHV Extensions DLL can also support standard cipher algorithms for network configurations that are not supported by the operating system. For example, the DLL can support the Temporal Key Integrity Protocol (TKIP) over IBSS networks, which is a configuration not supported by Windows Vista.

-   Verification of proprietary extensions to a network profile. For example, the IHV Extensions DLL is responsible for the validation of user settings for IHV-defined security options.

-   Configuration of the Native 802.11 miniport driver. For example, prior to starting a connection operation with the miniport driver, the operating system will call the [*Dot11ExtIhvPerformPreAssociate*](https://msdn.microsoft.com/library/windows/hardware/ff547499) function so that the IHV Extensions DLL can configure the driver with proprietary extensions related to the connection to a BSS network.

-   Interface to the IHV UI Extensions DLL. Through this interface, the IHV Extensions DLL can request user input or notification. For more information about the IHV UI Extensions DLL, see [Native 802.11 IHV UI Extensions DLL](native-802-11-ihv-ui-extensions-dll2.md).

The Native 802.11 IHV Extensibility Host process loads the IHV Extensions DLL into its process space upon the first arrival and detection of a wireless LAN (WLAN) adapter for which the DLL was installed. For more information about the Native 802.11 IHV Extensibility Host process and Native 802.11 framework, see [Native 802.11 Software Architecture](native-802-11-software-architecture.md).

The Native 802.11 IHV Extensibility Host process provides an API through its IHV Extensibility functions. Through this API, the IHV Extensions DLL can interface the Native 802.11 miniport driver or IHV UI Extensions DLL. For more information about the IHV Extensibility functions, see [Native 802.11 IHV Extensibility Functions](https://msdn.microsoft.com/library/windows/hardware/ff560609).

Similarly, the IHV Extensions DLL provides an API through its IHV Handler functions. The Native 802.11 IHV Extensibility Host process uses this API for various operations, such as initiating pre- or post-association operations. For more information about the IHV Handler functions, see [Native 802.11 IHV Handler Functions](https://msdn.microsoft.com/library/windows/hardware/ff560627).

 

 





