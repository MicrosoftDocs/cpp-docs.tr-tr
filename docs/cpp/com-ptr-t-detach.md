---
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: 8ba42f19e3474cc4a3199771f761b021221f430e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190020"
---
# <a name="_com_ptr_tdetach"></a>_com_ptr_t::Detach

**Microsoft 'a özgü**

Kapsüllenmiş arabirim işaretçisini ayıklar ve döndürür.

## <a name="syntax"></a>Sözdizimi

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>Açıklamalar

Kapsüllenmiş arabirim işaretçisini ayıklar ve döndürür, ardından kapsüllenmiş işaretçi depolamasını NULL olarak temizler. Bu, arabirim işaretçisini kapsüllemeden kaldırır. Döndürülen arabirim İşaretçisinde `Release` çağrın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)
