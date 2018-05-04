---
title: İn uygulamasına uygulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CComObjectRootEx
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44c62e7589b9b300ceaa2886760bf2c3d85550ce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="implementing-ccomobjectrootex"></a>İn uygulamasına uygulama
[İn uygulamasına](../atl/reference/ccomobjectrootex-class.md) tüm ATL nesneleri bir örneği olması gerekir; gereklidir `CComObjectRootEx` veya [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) kendi Devralmada. `CComObjectRootEx` Varsayılan sağlar `QueryInterface` mekanizması tabanlı COM harita girişlerde.  
  
 İstemci için bir arabirimi sorguladığında kendi COM eşlemesi üzerinden bir istemciye bir nesnenin arabirimleri sunulur. Sorgu üzerinden gerçekleştirilir `CComObjectRootEx::InternalQueryInterface`. `InternalQueryInterface` Yalnızca COM eşleme tablosu arabirimlerde işler.  
  
 İle COM harita tabloya arabirimleri girebilirsiniz [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) makrosu veya türevleri biri. Örneğin, aşağıdaki kodu arabirimler girer `IDispatch`, `IBeeper`, ve `ISupportErrorInfo` COM eşleme tablosu:  
  
 [!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM nesneleri temelleri](../atl/fundamentals-of-atl-com-objects.md)   
 [COM Eşleme Makroları](../atl/reference/com-map-macros.md)

