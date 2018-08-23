---
title: Synclockt::IsLocked metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: a81fea43-f99a-4708-812a-7fd6af500d3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ca4391539e4f6987431e8b9b036053db02218007
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593061"
---
# <a name="synclocktislocked-method"></a>SyncLockT::IsLocked Metodu

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
bool IsLocked() const;
```

## <a name="return-value"></a>Dönüş Değeri

**doğru** varsa **SyncLockT** nesnedir kilitli; Aksi takdirde **false**.

## <a name="remarks"></a>Açıklamalar

Belirtir olup olmadığını geçerli **SyncLockT** nesnesi bir kaynağa sahiptir; diğer bir deyişle, **SyncLockT** nesnedir *kilitli*.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Ayrıca Bkz.

[SyncLockT Sınıfı](../windows/synclockt-class.md)