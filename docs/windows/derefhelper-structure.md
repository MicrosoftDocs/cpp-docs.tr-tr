---
title: DerefHelper yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
dev_langs:
- C++
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 326974e935608c9b41866e61e72b7a85fc8cb0b2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598537"
---
# <a name="derefhelper-structure"></a>DerefHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename T
>
struct DerefHelper;

template <
   typename T
>
struct DerefHelper<T*>;
```

### <a name="parameters"></a>Parametreler

*T*  
Şablon parametresi.

## <a name="remarks"></a>Açıklamalar

Başvurusu kaldırılmış bir işaretçi temsil `T*` şablon parametresi.

**DerefHelper** bir ifadede gibi kullanılır: `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`DerefType`|Başvurusu kaldırılmış bir şablon parametresi için tanımlayıcı `T*`.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DerefHelper`

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)