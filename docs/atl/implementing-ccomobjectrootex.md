---
title: CComObjectRootEx uygulama | Microsoft Docs
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
ms.openlocfilehash: fefc7c3ed9177fb756e6298b54121a638ac8e253
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767484"
---
# <a name="implementing-ccomobjectrootex"></a>CComObjectRootEx uygulama

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) tüm ATL nesneleri bir örneği olması gerekir; önemlidir `CComObjectRootEx` veya [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) kendi Devralmada. `CComObjectRootEx` Varsayılan sağlar `QueryInterface` mekanizması tabanlı COM eşleme girişleri üzerinde.

İçin bir arabirimi istemciye sorgu oluştururken, COM eşlemesi üzerinden bir istemciye bir nesnenin arabirimlerinin sunulur. Sorgu üzerinden gerçekleştirilen `CComObjectRootEx::InternalQueryInterface`. `InternalQueryInterface` yalnızca COM eşleme tablosunda arabirimleri işler.

COM eşleme tablosu ile arabirimleri girebilirsiniz [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) makrosu veya türevleri biri. Örneğin, aşağıdaki kod arabirimleri girer `IDispatch`, `IBeeper`, ve `ISupportErrorInfo` COM eşlemesi tabloya:

[!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]

## <a name="see-also"></a>Ayrıca Bkz.

[ATL COM nesnelerinin temelleri](../atl/fundamentals-of-atl-com-objects.md)   
[COM Eşleme Makroları](../atl/reference/com-map-macros.md)

