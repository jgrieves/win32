---
Description: Smart Card Resource Manager
ms.assetid: 96434996-88fa-47d3-bb44-3ebb23610b27
title: Smart Card Resource Manager
ms.topic: article
ms.date: 05/31/2018
---

# Smart Card Resource Manager

The [*smart card*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) [*resource manager*](https://msdn.microsoft.com/en-us/library/ms721604(v=VS.85).aspx) manages access to [*readers*](https://msdn.microsoft.com/en-us/library/ms721604(v=VS.85).aspx) and to *smart cards*. To manage these resources, it performs the following functions.

-   Identifies and tracks resources.
-   Allocates readers and resources across multiple applications.
-   Supports [*transaction*](https://msdn.microsoft.com/en-us/library/ms721627(v=VS.85).aspx) primitives for accessing services available on a given card.
    > [!Note]  
    > This is an important point because current cards are single-threaded devices that often require the execution of multiple commands to complete a single function. [*Transactions*](https://msdn.microsoft.com/en-us/library/ms721627(v=VS.85).aspx) allow multiple commands to be executed without interruption, ensuring that intermediate [*state*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx) information is not corrupted.

     

The resource manager can be accessed directly by way of the resource manager API or indirectly through any smart card [*service provider*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx).

The resource manager API is a set of Windows functions that provide direct access to the resource manager's services. For an overview of the Windows functions provided by the API, see [Smart Card Resource Manager API](smart-card-resource-manager-api.md). In comparison, smart card service providers use COM interfaces.

Many of the Windows functions in the resource manager API have equivalents in the properties and methods of the smart card service providers' COM interfaces. And although most application developers will find COM easier to work with, some applications will still need to use the Windows functions to perform certain tasks. For example, applications that need to manipulate the list of readers or reader groups in the [*smart card database*](https://msdn.microsoft.com/en-us/library/ms721625(v=VS.85).aspx), and those that need direct control of a reader, must use the resource manager API. The services that provide these capabilities are available only in the Windows functions, not in the COM provided by the service providers.

For information about how the [*resource manager*](https://msdn.microsoft.com/en-us/library/ms721604(v=VS.85).aspx) is implemented in Windows, see [Resource Manager Implementation](resource-manager-implementation.md).

 

 



