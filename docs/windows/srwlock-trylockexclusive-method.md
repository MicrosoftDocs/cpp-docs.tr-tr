---
title: SRWLock::TryLockExclusive yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
dev_langs:
- C++
helpviewer_keywords:
- TryLockExclusive method
ms.assetid: 661e8b19-3058-4511-8742-c9fbb90412c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d0deec4790d185a5c6b7a7bdcbd670b056fc6f03
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424111"
---
# <a name="srwlocktrylockexclusive-method"></a>SRWLock::TryLockExclusive Yöntemi

Almaya çalışır bir **SRWLock** nesne için geçerli veya belirtilen özel modda **SRWLock** nesne. Çağrı başarılı olursa, çağıran iş parçacığını kilidi sahipliğini alır.

## <a name="syntax"></a>Sözdizimi

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*lock*<br/>
İşaretçi bir **SRWLock** nesne.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bir **SRWLock** Dışlayıcı ve çağıran iş parçacığını nesne kilidi sahipliğini alır. Aksi takdirde, bir **SRWLock** nesne durumu geçersiz.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[SRWLock Sınıfı](../windows/srwlock-class.md)