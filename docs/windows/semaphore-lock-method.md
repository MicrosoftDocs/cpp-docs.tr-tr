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
ms.openlocfilehash: 47925bcc647d253775e4dd61f6a7f5d5fb586dde
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599289"
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

*Milisaniye*  
Milisaniye cinsinden zaman aşımı aralığı. Varsayılan değer süresiz olarak bekler sonsuzdur.

*h*  
İçin bir tanıtıcı bir **semafor** nesne.

## <a name="return-value"></a>Dönüş Değeri

A `Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[Semafor Sınıfı](../windows/semaphore-class.md)