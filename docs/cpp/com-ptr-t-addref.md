---
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 7408b5c174f76673b56caffd56aaa87895bd08d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663365"
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef

**Microsoft'a özgü**

Çağrıları `AddRef` üye işlevinin `IUnknown` kapsüllenmiş arabirim işaretçisini üzerinde.

## <a name="syntax"></a>Sözdizimi

```
void AddRef( );
```

## <a name="remarks"></a>Açıklamalar

Çağrıları `IUnknown::AddRef` kapsüllenmiş arabirim işaretçisini üzerinde oluşturma bir `E_POINTER` NULL işaretçi işaret türündeyse hatası.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)