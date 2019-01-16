---
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
ms.openlocfilehash: 02420f2657c7d7d6a7a0294f0321717a3bb2b5d7
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335230"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>Açıklamalar

İşleç engel `new` içinde `RuntimeClass`. Sonuç olarak, kullanmanız gereken [olun işlevi](make-function.md) yerine.

## <a name="members"></a>Üyeler

### <a name="public-operators"></a>Ortak İşleçler

Ad                                             | Açıklama
------------------------------------------------ | ---------------------------------------------------------------------------
[DontUseNewUseMake::operator yeni](#operator-new) | İşleç aşırı `new` ve içinde kullanılmasını engeller `RuntimeClass`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DontUseNewUseMake`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="operator-new"></a>DontUseNewUseMake::operator yeni

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>Parametreler

*__unnamed0*<br/>
Bir adlandırılmamış parametresi ayrılacak bellek bayt sayısını belirtir.

*yerleştirme*<br/>
Ayrılacak türü.

### <a name="return-value"></a>Dönüş Değeri

İşleç işlecini aşırı yüklediyseniz ek bağımsız değişkenleri geçirmek için bir yol sağlar `new`.

### <a name="remarks"></a>Açıklamalar

İşleç aşırı `new` ve içinde kullanılmasını engeller `RuntimeClass`.
