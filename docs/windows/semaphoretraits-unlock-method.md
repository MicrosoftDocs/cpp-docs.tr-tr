---
title: SemaphoreTraits::Unlock yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c9519fb79bf8229578319fc1f3890f5d2e19442a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448302"
---
# <a name="semaphoretraitsunlock-method"></a>SemaphoreTraits::Unlock Yöntemi

Paylaşılan bir kaynak denetim yayınlar.

## <a name="syntax"></a>Sözdizimi

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
İşlemek için bir **semafor** nesne.

## <a name="remarks"></a>Açıklamalar

Kilit açma işlemi başarısızsa, **Unlock()** hatanın nedenini belirten bir hata gösterir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Ayrıca Bkz.

[SemaphoreTraits Yapısı](../windows/semaphoretraits-structure.md)