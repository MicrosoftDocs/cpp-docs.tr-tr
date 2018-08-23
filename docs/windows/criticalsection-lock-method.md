---
title: CriticalSection::Lock yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4fedde29441c9c14b68dec5cff998be57d216e29
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607666"
---
# <a name="criticalsectionlock-method"></a>CriticalSection::Lock Yöntemi

Belirtilen kritik bölüm Nesne sahipliği için bekler. Çağıran iş parçacığını sahipliği verildiğinde işlevi döndürür.

## <a name="syntax"></a>Sözdizimi

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Parametreler

*cs*  
Bir kullanıcı tarafından belirtilen kritik bölüm nesnesi.

## <a name="return-value"></a>Dönüş Değeri

Geçerli kritik bölümün kilidini açmak için kullanılan nesnesi kilitlenemedi.

## <a name="remarks"></a>Açıklamalar

İlk **kilit** işlevi, geçerli kritik bölüm nesnesini etkiler. İkinci **kilit** işlevi kullanıcı tanımlı bir kritik bölüm etkiler.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[CriticalSection Sınıfı](../windows/criticalsection-class.md)