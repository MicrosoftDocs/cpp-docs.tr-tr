---
title: CriticalSectionTraits::Unlock yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 003bb9c845ef8124ade1262a25368d3d4cb34fa6
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606437"
---
# <a name="criticalsectiontraitsunlock-method"></a>CriticalSectionTraits::Unlock Yöntemi

Uzmanlaşmış bir `CriticalSection` BT'nin siteminizi belirtilen kritik bölüm nesnenin sahipliğini destekler böylece şablonu.

## <a name="syntax"></a>Sözdizimi

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>Parametreler

*cs*  
Kritik bölüm nesnesine bir işaretçi.

## <a name="remarks"></a>Açıklamalar

`Type` Değiştirici olarak tanımlanmış olan `typedef CRITICAL_SECTION* Type;`.

Daha fazla bilgi için **LeaveCriticalSection işlevi** içinde **eşitleme işlevleri** Windows API belgelerinin bölümü.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Ayrıca Bkz.

[CriticalSectionTraits Yapısı](../windows/criticalsectiontraits-structure.md)