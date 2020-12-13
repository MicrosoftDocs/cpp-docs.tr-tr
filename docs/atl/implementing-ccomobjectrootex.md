---
description: 'Daha fazla bilgi edinin: CComObjectRootEx uygulama'
title: CComObjectRootEx uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
ms.openlocfilehash: 235d10a8c390311230057da5dda11e5a8f093445
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152847"
---
# <a name="implementing-ccomobjectrootex"></a>CComObjectRootEx uygulama

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) gereklidir; tüm ATL nesneleri `CComObjectRootEx` Devralmada bir veya [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) örneğine sahip olmalıdır. `CComObjectRootEx``QueryInterface`com eşleme girişlerine göre varsayılan mekanizmayı sağlar.

İstemci bir arabirimi sorguladığında, COM eşlemesi aracılığıyla bir nesnenin arabirimleri istemciye gösterilir. Sorgu ile gerçekleştirilir `CComObjectRootEx::InternalQueryInterface` . `InternalQueryInterface` yalnızca COM Map tablosundaki arabirimleri işler.

COM harita tablosuna, [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) makrosunu veya bunların çeşitlerinden birini içeren arabirimler girebilirsiniz. Örneğin, aşağıdaki kod, `IDispatch` `IBeeper` ve arabirimlerini `ISupportErrorInfo` com map tablosuna girer:

[!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM nesnelerinin temelleri](../atl/fundamentals-of-atl-com-objects.md)<br/>
[COM eşleme makroları](../atl/reference/com-map-macros.md)
