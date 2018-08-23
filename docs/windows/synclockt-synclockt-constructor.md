---
title: SyncLockT::SyncLockT Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3dfee1d923536f519917a50ed44fd5c115007c27
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601973"
---
# <a name="synclocktsynclockt-constructor"></a>SyncLockT::SyncLockT Oluşturucusu

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);
```

### <a name="parameters"></a>Parametreler

*Diğer*  
Diğer bir rvalue başvurusuna **SyncLockT** nesne.

*Eşitleme*  
Başka bir başvuru `SyncLockWithStatusT` nesne.

## <a name="remarks"></a>Açıklamalar

Yeni bir örneğini başlatır **SyncLockT** sınıfı.

İlk Oluşturucu geçerli başlatır **SyncLockT** başka bir nesne **SyncLockT** parametresi tarafından belirtilen nesne *diğer*ve ardından diğer geçersizkılar **SyncLockT** nesne. İkinci oluşturucu **korumalı**ve geçerli başlatır **SyncLockT** nesnesi için geçersiz bir durumda.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Ayrıca Bkz.

[SyncLockT Sınıfı](../windows/synclockt-class.md)