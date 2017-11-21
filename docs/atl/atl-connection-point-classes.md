---
title: "ATL bağlantı noktası sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CFirePropNotifyEvent class, connection point classes
- connection points [C++], ATL classes
- ATL, connection points
- CComDynamicUnkArray class, connection point classes
- CFirePropNotifyEvent class
- CComUnkArray class, connection point classes
ms.assetid: 9582ba71-7ace-4df4-9c9b-1b0636953efc
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ec0a17c47b3a2b30f1f2a2a73a0633ffa321b2a1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="atl-connection-point-classes"></a>ATL bağlantı noktası sınıfları
ATL bağlantı noktaları desteklemek için aşağıdaki sınıflar kullanır:  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) bir bağlantı noktası uygular. Temsil ettiği giden arabirimi IID şablon parametre olarak geçirilir.  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) bağlantı noktası kapsayıcısına uygular ve listesini yönetir `IConnectionPointImpl` nesneleri.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) bir bağlantı noktası temsil eden uygulayan [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638) arabirimi.  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) rastgele bir bağlantı noktası ve onun havuzlarını arasındaki bağlantıları sayısı yönetir.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) bağlantıları şablon parametresi tarafından belirtilen sayıda yönetir.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) bir nesnenin özellik değiştirildi veya değiştirilmek bir istemcinin havuz bildirir.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) ATL COM nesne için bağlantı noktaları için destek sağlar. Bu bağlantı noktaları, COM nesnesi tarafından sağlanan bir olay havuz eşlemesi ile eşlenir.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) sınıfınıza uygun işleyiciyi işlevi için rota olayları olay havuz eşlemesinde ile birlikte çalışır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantı noktası](../atl/atl-connection-points.md)

