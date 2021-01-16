---
description: 'Daha fazla bilgi edinin: wctype'
title: wctype
ms.date: 1/14/2021
api_name:
- wctype
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctype
helpviewer_keywords:
- wctype function
- wide characters
ms.openlocfilehash: d0afd2bd163af967b11d0df58c84b62521ca6c2a
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242936"
---
# `wctype`

Geniş karakterli kodlar için bir sınıflandırma kuralı belirler.

## <a name="syntax"></a>Sözdizimi

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>Parametreler

*`property`*\
Özellik dizesi.

## <a name="return-value"></a>Dönüş Değeri

**`LC_CTYPE`** Geçerli yerel ayarın kategorisi, adı özellik dizesiyle eşleşen bir sınıflandırma kuralı tanımlamıyorsa *`property`* , işlev 0 döndürür. Aksi halde, sonraki bir çağrısının ikinci bağımsız değişkeni olarak kullanılmak üzere uygun olmayan bir değer döndürür [`towctrans`](towctrans.md) .

## <a name="remarks"></a>Açıklamalar

İşlevi, geniş karakter kodları için bir sınıflandırma kuralı belirler. Aşağıdaki çağrı çiftleri tüm yerel ayarlarda aynı davranışa sahiptir (ancak, bir uygulama "C" yerel ayarında bile ek sınıflandırma kuralları tanımlayabilir):

|İşlev|Aynı|
|--------------|-------------|
|`iswalnum(c)`|`iswctype(c, wctype( "alnum" ))`|
|`iswalpha(c)`|`iswctype(c, wctype( "alpha" ))`|
|`iswcntrl(c)`|`iswctype(c, wctype( "cntrl" ))`|
|`iswdigit(c)`|`iswctype(c, wctype( "digit" ))`|
|`iswgraph(c)`|`iswctype(c, wctype( "graph" ))`|
|`iswlower(c)`|`iswctype(c, wctype( "lower" ))`|
|`iswprint(c)`|`iswctype(c, wctype( "print" ))`|
|`iswpunct(c)`|`iswctype(c, wctype( "punct" ))`|
|`iswspace(c)`|`iswctype(c, wctype( "space" ))`|
|`iswupper(c)`|`iswctype(c, wctype( "upper" ))`|
|`iswxdigit(c)`|`iswctype(c, wctype( "xdigit" ))`|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`wctype`|`<wctype.h>`|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)\
[`setlocale`, `_wsetlocale`](setlocale-wsetlocale.md)
