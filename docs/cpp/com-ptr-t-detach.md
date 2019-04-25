---
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: affaefd8af4802836733587af62977171ba01410
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154974"
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach

**Microsoft'a özgü**

Kapsüllenmiş arabirim işaretçisini ayıklar ve döndürür.

## <a name="syntax"></a>Sözdizimi

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>Açıklamalar

Ayıklar kapsüllenmiş arabirim işaretçisini döndürür ve ardından kapsüllenmiş işaretçi depolamasını null temizler. Bu, arabirim işaretçisini kapsüllemeden kaldırır. Size kalmıştır çağrılacak olan `Release` döndürülen arabirim işaretçisinde üzerinde.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)