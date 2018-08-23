---
title: SRWLock::LockShared yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
dev_langs:
- C++
helpviewer_keywords:
- LockShared method
ms.assetid: 9d826a5c-b6a2-4430-ac85-d5753cbca889
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0f6b3135171e61e928984c0eeb91aff0717a4727
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599255"
---
# <a name="srwlocklockshared-method"></a>SRWLock::LockShared Yöntemi

Alması bir **SRWLock** paylaşılan modda nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametreler

*lock*  
İşaretçi bir **SRWLock** nesne.

## <a name="return-value"></a>Dönüş Değeri

Bir **SRWLock** paylaşılan modda nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[SRWLock Sınıfı](../windows/srwlock-class.md)