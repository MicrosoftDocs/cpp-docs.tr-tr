---
title: CriticalSection::TryLock yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs:
- C++
helpviewer_keywords:
- TryLock method
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 44b4e251898ef6386d0642582af2c00881f7a181
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408589"
---
# <a name="criticalsectiontrylock-method"></a>CriticalSection::TryLock Yöntemi

Engelleme olmadan kritik bir bölüm girin dener. Çağrı başarılı olursa, çağıran iş parçacığı, kritik bölüm sahipliğini alır.

## <a name="syntax"></a>Sözdizimi

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Parametreler

*cs*<br/>
Bir kullanıcı tarafından belirtilen kritik bölüm nesnesi.

## <a name="return-value"></a>Dönüş Değeri

Kritik bölüm başarıyla girdiyseniz sıfır olmayan bir değer veya geçerli iş parçacığı, kritik bölüm zaten sahip. Başka bir iş parçacığı kritik bölüm sahipse sıfır.

## <a name="remarks"></a>Açıklamalar

İlk **TryLock** işlevi, geçerli kritik bölüm nesnesini etkiler. İkinci **TryLock** işlevi kullanıcı tanımlı bir kritik bölüm etkiler.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[CriticalSection Sınıfı](../windows/criticalsection-class.md)