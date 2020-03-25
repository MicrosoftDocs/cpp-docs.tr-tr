---
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 51182b461aeac83c12bb18a573a49b2d4347a190
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189940"
---
# <a name="_com_ptr_taddref"></a>_com_ptr_t::AddRef

**Microsoft 'a özgü**

Kapsüllenmiş arabirim İşaretçisinde `IUnknown` `AddRef` üye işlevini çağırır.

## <a name="syntax"></a>Sözdizimi

```
void AddRef( );
```

## <a name="remarks"></a>Açıklamalar

İşaretçi NULL ise, kapsüllenmiş arabirim İşaretçisinde `IUnknown::AddRef` çağırır, `E_POINTER` hatasını ortaya koyar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)
