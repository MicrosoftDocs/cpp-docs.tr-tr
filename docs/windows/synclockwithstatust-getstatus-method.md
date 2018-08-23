---
title: SyncLockWithStatusT::GetStatus metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
dev_langs:
- C++
helpviewer_keywords:
- GetStatus method
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2cef491aac3350c1692c2f87236f3cbf01dd9b0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612084"
---
# <a name="synclockwithstatustgetstatus-method"></a>SyncLockWithStatusT::GetStatus Metodu

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
DWORD GetStatus() const;
```

## <a name="return-value"></a>Dönüş Değeri

Temel alan bir nesne üzerinde bir bekleme işlemini sonucunu **SyncLockWithStatusT** gibi sınıfı bir [Mutex](../windows/mutex-class1.md) veya [semafor](../windows/semaphore-class.md). Sinyal verilmiş duruma dönmesine bekleme işlemi döndürülen sıfır (0) gösterir. geçen zaman aşımı değeri gibi Aksi takdirde, başka bir durum, oluştu.

## <a name="remarks"></a>Açıklamalar

Geçerli bekleme durumunu alır **SyncLockWithStatusT** nesne.

GetStatus() işlevi, temel alınan değeri alır. [status_](../windows/synclockwithstatust-status-data-member.md) veri üyesi. Bir nesne, temel alarak **SyncLockWithStatusT** sınıfı bir kilit işlemi gerçekleştirir, nesne ilk nesne kullanılabilir olana kadar bekler. Bu bekleme işleminin sonucu depolanan `status_` veri üyesi. Olası değerleri `status_` veri üyesi olan dönüş değerlerini bekleme işlemi. Daha fazla bilgi için bkz: dönüş değerlerini `WaitForSingleObjectEx()` MSDN Kitaplığı'nda işlevi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Ayrıca Bkz.

[SyncLockWithStatusT Sınıfı](../windows/synclockwithstatust-class.md)