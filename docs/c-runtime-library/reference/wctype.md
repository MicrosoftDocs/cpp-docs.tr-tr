---
description: 'Daha fazla bilgi edinin: wctype'
title: wctype
ms.date: 11/04/2016
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctype
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
ms.openlocfilehash: 0791d4f048dfa5d6804db14d577b1370ffbf8754
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254202"
---
# <a name="wctype"></a>wctype

Geniş karakterli kodlar için bir sınıflandırma kuralı belirler.

## <a name="syntax"></a>Sözdizimi

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>Parametreler

*özelliði*<br/>
Özellik dizesi.

## <a name="return-value"></a>Dönüş Değeri

Geçerli yerel ayarın **LC_CTYPE** kategorisi, adı özellik dizesi *özelliği* ile eşleşen bir sınıflandırma kuralı tanımlamıyorsa, işlev sıfır döndürür. Aksi halde, sonraki [towctrans](towctrans.md)çağrısının ikinci bağımsız değişkeni olarak kullanılmak üzere uygun olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

İşlevi, geniş karakter kodları için bir sınıflandırma kuralı belirler. Aşağıdaki çağrı çiftleri tüm yerel ayarlarda aynı davranışa sahiptir (ancak, bir uygulama "C" yerel ayarında bile ek sınıflandırma kuralları tanımlayabilir):

|İşlev|Aynı|
|--------------|-------------|
|iswalnum (c)|ıwctype (c, wctype ("alnum"))|
|iswalpha (c)|ıwctype (c, wctype ("Alpha"))|
|iswcnp (c)|ıwctype (c, wctype ("CNP"))|
|iswdigit (c)|ıwctype (c, wctype ("digit"))|
|iswgraf (c)|ıwctype (c, wctype ("Graph"))|
|iswlower (c)|ıwctype (c, wctype ("Lower"))|
|iswprınt (c)|ıwctype (c, wctype ("PRINT"))|
|iswpunct (c)|ıwctype (c, wctype ("punct"))|
|iswspace (c)|ıwctype (c, wctype ("Space"))|
|iswupper (c)|ıwctype (c, wctype ("Upper"))|
|iswxdigit (c)|ıwctype (c, wctype ("xdigit"))|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctype**|\<wctype.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
