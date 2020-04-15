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
ms.openlocfilehash: ae67373b4f2f2d4a199b939b06e6f526f1365446
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371548"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>Açıklamalar

'de `RuntimeClass`operatör `new` kullanılmasını önler. Sonuç olarak, bunun yerine [Yap işlevini](make-function.md) kullanmanız gerekir.

## <a name="members"></a>Üyeler

### <a name="public-operators"></a>Ortak İşleçler

Adı                                             | Açıklama
------------------------------------------------ | ---------------------------------------------------------------------------
[DontUseNewUseOlun::operatör yeni](#operator-new) | İşleticiaşırı `new` yükler ve 'de `RuntimeClass`kullanılmasını önler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DontUseNewUseMake`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="dontusenewusemakeoperator-new"></a><a name="operator-new"></a>DontUseNewUseOlun::operatör yeni

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>Parametreler

*__unnamed0*<br/>
Ayrılacak bellek baytlarının sayısını belirten adsız bir parametre.

*Yerleşim*<br/>
Tahsis edilecek tür.

### <a name="return-value"></a>Dönüş Değeri

İşleç `new`aşırı yüklerseniz ek bağımsız değişkenleri geçirmek için bir yol sağlar.

### <a name="remarks"></a>Açıklamalar

İşleticiaşırı `new` yükler ve 'de `RuntimeClass`kullanılmasını önler.
