---
title: CriticalSectionTraits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
dev_langs:
- C++
helpviewer_keywords:
- CriticalSectionTraits structure
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d15f65ecc2253556a6812cfb90ef78f90c7fb29
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594740"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits Yapısı

Uzmanlaşmış bir `CriticalSection` geçersiz bir kritik bölüm veya kritik bir bölüm serbest bırakmak için bir işlevi desteklemek için nesne.

## <a name="syntax"></a>Sözdizimi

```
struct CriticalSectionTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`Type`|A **typedef** , kritik bir bölüm için bir işaretçi tanımlar. `Type` olarak tanımlanan `typedef CRITICAL_SECTION* Type;`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CriticalSectionTraits::GetInvalidValue Metodu](../windows/criticalsectiontraits-getinvalidvalue-method.md)|Uzmanlaşmış bir `CriticalSection` şablon böylece şablonu her zaman geçerli değil.|
|[CriticalSectionTraits::Unlock Metodu](../windows/criticalsectiontraits-unlock-method.md)|Uzmanlaşmış bir `CriticalSection` BT'nin siteminizi belirtilen kritik bölüm nesnenin sahipliğini destekler böylece şablonu.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CriticalSectionTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers::HandleTraits Ad Alanı](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)