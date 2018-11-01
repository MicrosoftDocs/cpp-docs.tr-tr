---
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: cf4cea35386d1f781d6d2946c1730ba2e18dacea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624050"
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release

**Microsoft'a özgü**

Çağrıları **yayın** üye işlevinin `IUnknown` kapsüllenmiş arabirim işaretçisini üzerinde.

## <a name="syntax"></a>Sözdizimi

```
void Release( );
```

## <a name="remarks"></a>Açıklamalar

Çağrıları `IUnknown::Release` kapsüllenmiş arabirim işaretçisini üzerinde oluşturma bir `E_POINTER` bu arabirim işaretçisi, NULL ise hata.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)