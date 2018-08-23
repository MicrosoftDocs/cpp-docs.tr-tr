---
title: Criticalsectiontraits::getınvalidvalue metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- GetInvalidValue method
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4a23445cc9df0553a40d4f78a7ce3095a343d5d0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599242"
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue Metodu

Uzmanlaşmış bir **CriticalSection** şablon böylece şablonu her zaman geçerli değil.

## <a name="syntax"></a>Sözdizimi

```cpp
inline static Type GetInvalidValue();
```

## <a name="return-value"></a>Dönüş Değeri

Her zaman için geçersiz bir kritik bölüm bir işaretçi döndürür.

## <a name="remarks"></a>Açıklamalar

`Type` Değiştirici olarak tanımlanmış olan `typedef CRITICAL_SECTION* Type;`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Ayrıca Bkz.

[CriticalSectionTraits Yapısı](../windows/criticalsectiontraits-structure.md)