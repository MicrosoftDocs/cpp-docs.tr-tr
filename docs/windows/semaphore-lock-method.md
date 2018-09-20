---
title: Semaphore::Lock yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2083992bcb444a10b495b7007c698499f9cd9628
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419171"
---
# <a name="semaphorelock-method"></a>Semaphore::Lock Yöntemi

Geçerli nesne kadar bekler veya **semafor** nesne ile ilişkili belirtilen işleyici içinde sinyal verilmiş duruma dönmesine ya da belirtilen zaman aşımı aralığı geçti.

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
İçin bir tanıtıcı bir **semafor** nesne.

## <a name="return-value"></a>Dönüş Değeri

A `Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[Semafor Sınıfı](../windows/semaphore-class.md)