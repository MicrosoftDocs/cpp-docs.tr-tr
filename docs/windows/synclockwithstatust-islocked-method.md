---
title: Synclockwithstatust::IsLocked metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d70a2c316f9e7994292f3dc29cef5bce993778ad
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595069"
---
# <a name="synclockwithstatustislocked-method"></a>SyncLockWithStatusT::IsLocked Metodu

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
bool IsLocked() const;
```

## <a name="remarks"></a>Açıklamalar

Belirtir olup olmadığını geçerli **SyncLockWithStatusT** nesnesi bir kaynağa sahiptir; diğer bir deyişle, **SyncLockWithStatusT** nesnedir *kilitli*.

## <a name="return-value"></a>Dönüş Değeri

**doğru** varsa **SyncLockWithStatusT** nesnedir kilitli; Aksi takdirde **false**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Ayrıca Bkz.

[SyncLockWithStatusT Sınıfı](../windows/synclockwithstatust-class.md)