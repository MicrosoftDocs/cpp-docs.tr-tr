---
title: Isbaseofstrict yapısı | Microsoft Docs
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 137f572f01d4aa72b9141c3ca172426fdb575b48
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169530"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename Base,
   typename Derived
>

struct IsBaseOfStrict;
template <
   typename Base
>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>Parametreler

*temel*<br/>
Temel türü.

*Türetilmiş*<br/>
Türetilmiş bir tür.

## <a name="remarks"></a>Açıklamalar

Başka bir taban bir türü olup olmadığını sınar.

İlk şablon yield bir temel tür türetilmiş bir tür olup olmadığını test `true` veya `false`. İkinci şablon türetilmiş bir tür kendisinden, her zaman veren olmadığını sınar `false`.

## <a name="members"></a>Üyeler

### <a name="public-constants"></a>Genel sabitler

Ad                            | Açıklama
------------------------------- | --------------------------------------------------
[Isbaseofstrict::Value](#value) | Başka bir taban bir türü olup olmadığını gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IsBaseOfStrict`

## <a name="requirements"></a>Gereksinimler

**Başlık:** internal.h

**Namespace:** Microsoft::wrl:: details

## <a name="value"></a>Isbaseofstrict::Value

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>Açıklamalar

Başka bir taban bir türü olup olmadığını gösterir.

`value` olan `true` , türü `Base` bir temel sınıf türünün `Derived`, aksi halde kalır `false`.
