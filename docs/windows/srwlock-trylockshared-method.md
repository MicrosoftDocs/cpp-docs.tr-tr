---
title: SRWLock::TryLockShared yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
dev_langs:
- C++
helpviewer_keywords:
- TryLockShared method
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 985629f224f199d1b1f095847e64cc67fa5a97f9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388477"
---
# <a name="srwlocktrylockshared-method"></a>SRWLock::TryLockShared Yöntemi

Almaya çalışır bir **SRWLock** nesne için geçerli veya belirtilen paylaşılan modda **SRWLock** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
İşaretçi bir **SRWLock** nesne.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bir **SRWLock** paylaşılan modda ve çağıran iş parçacığını nesne kilidi sahipliğini alır. Aksi takdirde, bir **SRWLock** nesne durumu geçersiz.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[SRWLock Sınıfı](../windows/srwlock-class.md)