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
ms.openlocfilehash: fbba6d96106cc95910ccd9d0029cb3e9c254d7d3
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335352"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>Parametreler

*TDelegateInterface*<br/>
Bir temsilci arabirimi.

## <a name="remarks"></a>Açıklamalar

Yardımcı olur, temsilci bağımsız değişkenleri genel özelliklerini tanımlayın.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad         | Açıklama
------------ | ------------------------------------------------------
`methodType` | İçin bir eşanlamlı `decltype(&TDelegateInterface::Invoke)`.
`Traits`     | İçin bir eşanlamlı `ArgTraits<methodType>`.

### <a name="public-constants"></a>Genel sabitler

Ad                           | Açıklama
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[ArgTraitsHelper::args](#args) | Yardımcı [ArgTraits::args](#args) parametreleri sayısını takip edin `Invoke` yöntemi temsilci arabirimi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ArgTraitsHelper`

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::wrl:: details

## <a name="args"></a>ArgTraitsHelper::args

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>Açıklamalar

Yardımcı `ArgTraitsHelper::args` parametreleri sayısını takip edin `Invoke` yöntemi temsilci arabirimi.
