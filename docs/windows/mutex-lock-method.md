---
title: Mutex::Lock yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 61d95072-b690-441e-a080-0bf94a733141
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8bb04b8be33f81931106574152d0ccb6ba535295
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427842"
---
# <a name="mutexlock-method"></a>Mutex::Lock Yöntemi

Geçerli nesne kadar bekler veya **Mutex** belirtilen tanıtıcısı, mutex veya belirtilen zaman aşımı aralığı geçtikten yayınlar ilişkili nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>Parametreler

*Milisaniye*<br/>
Milisaniye cinsinden zaman aşımı aralığı. Varsayılan değer süresiz olarak bekler sonsuzdur.

*h*<br/>
Tanıtıcısını bir **Mutex** nesne.

## <a name="return-value"></a>Dönüş Değeri

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[Mutex sınıfı](../windows/mutex-class1.md)