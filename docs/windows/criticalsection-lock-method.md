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
ms.openlocfilehash: f13af220107ba8d5bc5c26c65c2034f125a39454
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382459"
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

*cs*<br/>
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