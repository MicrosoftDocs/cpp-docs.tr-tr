---
description: 'Daha fazla bilgi edinin: DontUseNewUseMake sınıfı'
title: DontUseNewUseMake Sınıfı
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
helpviewer_keywords:
- Microsoft::WRL::Details::DontUseNewUseMake class
- Microsoft::WRL::Details::DontUseNewUseMake::operator new operator
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
ms.openlocfilehash: f6b6740e472123e59565e3bad16e4a535a4e17fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272909"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Syntax

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>Açıklamalar

İçindeki işlecinin kullanımını `new` engeller `RuntimeClass` . Sonuç olarak, bunun yerine [Make işlevini](make-function.md) kullanmanız gerekir.

## <a name="members"></a>Üyeler

### <a name="public-operators"></a>Ortak İşleçler

Ad                                             | Açıklama
------------------------------------------------ | ---------------------------------------------------------------------------
[DontUseNewUseMake:: operator New](#operator-new) | Aşırı yüklemeler işleci `new` ve içinde kullanılmasını önler `RuntimeClass` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DontUseNewUseMake`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="dontusenewusemakeoperator-new"></a><a name="operator-new"></a> DontUseNewUseMake:: operator New

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>Parametreler

*__unnamed0*<br/>
Ayrılacak belleğin bayt sayısını belirten adlandırılmamış bir parametre.

*yerleştirilmesine*<br/>
Ayrılacak tür.

### <a name="return-value"></a>Dönüş Değeri

İşleci aşırı yüklüyorsanız ek bağımsız değişkenler geçirmek için bir yol sağlar `new` .

### <a name="remarks"></a>Açıklamalar

Aşırı yüklemeler işleci `new` ve içinde kullanılmasını önler `RuntimeClass` .
