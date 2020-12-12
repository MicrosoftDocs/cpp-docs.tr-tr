---
description: Daha fazla bilgi için bkz. yapı başına argtraitshel
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
ms.openlocfilehash: a749c48c72c837eb0898d32ddd08410b87918871
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175865"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>Parametreler

*Tdelegateınterface*<br/>
Temsilci arabirimi.

## <a name="remarks"></a>Açıklamalar

Temsilci bağımsız değişkenlerinin ortak özelliklerini tanımlamaya yardımcı olur.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad         | Açıklama
------------ | ------------------------------------------------------
`methodType` | İçin bir eş anlamlı `decltype(&TDelegateInterface::Invoke)` .
`Traits`     | İçin bir eş anlamlı `ArgTraits<methodType>` .

### <a name="public-constants"></a>Genel sabitler

Ad                           | Açıklama
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[ArgTraitsHelper:: args](#args) | [Argnitelikler:: args](#args) , `Invoke` bir temsilci arabiriminin yöntemindeki parametre sayısının sayısını tutar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ArgTraitsHelper`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Event. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="argtraitshelperargs"></a><a name="args"></a> ArgTraitsHelper:: args

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>Açıklamalar

`ArgTraitsHelper::args`Bir temsilci arabiriminin yöntemindeki parametre sayısını tutmaya yardımcı olur `Invoke` .
