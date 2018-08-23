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
ms.openlocfilehash: 382dbdd2d0816d6ab0846acd0f8c164cd542114f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42575847"
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

*cs*  
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