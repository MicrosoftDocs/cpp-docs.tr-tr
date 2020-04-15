---
title: ArgTraitsHelper Yapısı
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraitsHelper structure
- Microsoft::WRL::Details::ArgTraitsHelper::args constant
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
ms.openlocfilehash: 4acbd9fa660f29bbaf209282ff0e90f43621574d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360777"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>Parametreler

*TDelegateArayüzü*<br/>
Temsilci arabirimi.

## <a name="remarks"></a>Açıklamalar

Temsilci bağımsız değişkenlerinin ortak özelliklerini tanımlamaya yardımcı olur.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı         | Açıklama
------------ | ------------------------------------------------------
`methodType` | Bir eşanlamlı `decltype(&TDelegateInterface::Invoke)`.
`Traits`     | Bir eşanlamlı `ArgTraits<methodType>`.

### <a name="public-constants"></a>Genel Sabitler

Adı                           | Açıklama
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[ArgTraitsHelper::args](#args) | [ArgTraits yardımcı olur::args](#args) bir temsilci arabirimi `Invoke` yöntemi üzerinde parametre sayısını tutmak.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ArgTraitsHelper`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** event.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="argtraitshelperargs"></a><a name="args"></a>ArgTraitsHelper::args

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>Açıklamalar

Temsilci `ArgTraitsHelper::args` arabirimi yöntemindeki parametre `Invoke` sayısının saytutulmasına yardımcı olur.
