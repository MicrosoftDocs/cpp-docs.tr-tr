---
title: "İn uygulamasına uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CComObjectRootEx
dev_langs: C++
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 960f7989d3891be4cf23ef75b0982a2577f5e95e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="implementing-ccomobjectrootex"></a>İn uygulamasına uygulama
[İn uygulamasına](../atl/reference/ccomobjectrootex-class.md) tüm ATL nesneleri bir örneği olması gerekir; gereklidir `CComObjectRootEx` veya [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) kendi Devralmada. `CComObjectRootEx`Varsayılan sağlar `QueryInterface` mekanizması tabanlı COM harita girişlerde.  
  
 İstemci için bir arabirimi sorguladığında kendi COM eşlemesi üzerinden bir istemciye bir nesnenin arabirimleri sunulur. Sorgu üzerinden gerçekleştirilir `CComObjectRootEx::InternalQueryInterface`. `InternalQueryInterface`yalnızca COM eşleme tablosu arabirimlerde işler.  
  
 İle COM harita tabloya arabirimleri girebilirsiniz [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) makrosu veya türevleri biri. Örneğin, aşağıdaki kodu arabirimler girer `IDispatch`, `IBeeper`, ve `ISupportErrorInfo` COM eşleme tablosu:  
  
 [!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM nesneleri temelleri](../atl/fundamentals-of-atl-com-objects.md)   
 [COM eşleme makroları](../atl/reference/com-map-macros.md)

