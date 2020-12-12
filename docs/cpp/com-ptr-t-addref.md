---
description: 'Hakkında daha fazla bilgi edinin: _com_ptr_t:: AddRef'
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 0979245662a94596307b1a63af918d0ce67c7b6f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295698"
---
# <a name="_com_ptr_taddref"></a>_com_ptr_t::AddRef

**Microsoft'a Özgü**

`AddRef` `IUnknown` Kapsüllenmiş arabirim İşaretçisinde öğesinin üye işlevini çağırır.

## <a name="syntax"></a>Syntax

```cpp
void AddRef( );
```

## <a name="remarks"></a>Açıklamalar

`IUnknown::AddRef`IŞARETÇI null ise, kapsüllenmiş arabirim İşaretçisinde bir `E_POINTER` hata ortaya koyar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)
