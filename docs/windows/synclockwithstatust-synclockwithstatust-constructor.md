---
title: SyncLockWithStatusT::SyncLockWithStatusT Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT, constructor
ms.assetid: 5d2fb820-ae1b-495f-8084-ebb4fecc3104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 85d0adfd03b6822b949523643aa97f7a7d8b088b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607636"
---
# <a name="synclockwithstatustsynclockwithstatust-constructor"></a>SyncLockWithStatusT::SyncLockWithStatusT Oluşturucusu

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
SyncLockWithStatusT(
   _Inout_ SyncLockWithStatusT&& other
);

explicit SyncLockWithStatusT(
   typename SyncTraits::Type sync,
   DWORD status
);
```

### <a name="parameters"></a>Parametreler

*Diğer*  
Diğer bir rvalue başvurusuna **SyncLockWithStatusT** nesne.

*Eşitleme*  
Başka bir başvuru **SyncLockWithStatusT** nesne.

*Durumu*  
Değerini [status_](../windows/synclockwithstatust-status-data-member.md) veri üyesi *diğer* parametresi veya *eşitleme* parametresi.

## <a name="remarks"></a>Açıklamalar

Yeni bir örneğini başlatır **SyncLockWithStatusT** sınıfı.

İlk Oluşturucu geçerli başlatır **SyncLockWithStatusT** başka bir nesne **SyncLockWithStatusT** parametresi tarafından belirtilen *diğer*ve ardından diğer geçersiz kılar **SyncLockWithStatusT** nesne. İkinci oluşturucu **korumalı**ve geçerli başlatır **SyncLockWithStatusT** nesnesi için geçersiz bir durumda.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Ayrıca Bkz.

[SyncLockWithStatusT Sınıfı](../windows/synclockwithstatust-class.md)  
[SyncLockWithStatusT::GetStatus Metodu](../windows/synclockwithstatust-getstatus-method.md)