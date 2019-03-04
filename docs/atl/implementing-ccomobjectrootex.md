---
title: CComObjectRootEx uygulama
ms.date: 11/04/2016
f1_keywords:
- CComObjectRootEx
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
ms.openlocfilehash: e533f8809238bc94bc95a689197d56f3c616f736
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273835"
---
# <a name="implementing-ccomobjectrootex"></a>CComObjectRootEx uygulama

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) tüm ATL nesneleri bir örneği olması gerekir; önemlidir `CComObjectRootEx` veya [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) kendi Devralmada. `CComObjectRootEx` Varsayılan sağlar `QueryInterface` mekanizması tabanlı COM eşleme girişleri üzerinde.

İçin bir arabirimi istemciye sorgu oluştururken, COM eşlemesi üzerinden bir istemciye bir nesnenin arabirimlerinin sunulur. Sorgu üzerinden gerçekleştirilen `CComObjectRootEx::InternalQueryInterface`. `InternalQueryInterface` yalnızca COM eşleme tablosunda arabirimleri işler.

COM eşleme tablosu ile arabirimleri girebilirsiniz [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) makrosu veya türevleri biri. Örneğin, aşağıdaki kod arabirimleri girer `IDispatch`, `IBeeper`, ve `ISupportErrorInfo` COM eşlemesi tabloya:

[!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)<br/>
[COM Eşleme Makroları](../atl/reference/com-map-macros.md)
