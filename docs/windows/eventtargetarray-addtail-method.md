---
title: EventTargetArray::AddTail yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
dev_langs:
- C++
helpviewer_keywords:
- AddTail method
ms.assetid: d0fafab9-049c-40e0-a40c-d126c9ee63e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ab0219c8893ff7ad35e29f9dd8b18be18caf8eb9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378130"
---
# <a name="eventtargetarrayaddtail-method"></a>EventTargetArray::AddTail Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>Parametreler

*Öğesi*<br/>
Olay işleyicisi eklemek için işaretçi.

## <a name="remarks"></a>Açıklamalar

Belirtilen olay işleyicisi, olay işleyicileri iç dizi sonuna ekler.

**AddTail()** yalnızca tarafından dahili olarak kullanılması amaçlanmıştır `EventSource` sınıfı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[EventTargetArray Sınıfı](../windows/eventtargetarray-class.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)