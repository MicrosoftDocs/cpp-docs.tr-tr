---
title: IsBaseOfStrict Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
ms.openlocfilehash: 85aeb71ceaa162cc6366836dd286f2f9983d34e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386024"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>Parametreler

*temel*<br/>
Temel türü.

*Türetilmiş*<br/>
Türetilmiş bir tür.

## <a name="remarks"></a>Açıklamalar

Başka bir taban bir türü olup olmadığını sınar.

İlk şablon yield bir temel tür türetilmiş bir tür olup olmadığını test **true** veya **false**. İkinci şablon türetilmiş bir tür kendisinden, her zaman veren olmadığını sınar **false**.

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

`value` olan **true** , türü `Base` bir temel sınıf türünün `Derived`, aksi halde kalır **false**.
