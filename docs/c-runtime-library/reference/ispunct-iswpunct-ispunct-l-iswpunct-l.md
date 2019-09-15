---
title: ispunct, iswpunct, _ispunct_l, _iswpunct_l
ms.date: 11/04/2016
api_name:
- ispunct
- _iswpunct_l
- iswpunct
- _ispunct_l
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
- iswpunct
- _istpunct
- ispunct
helpviewer_keywords:
- _istpunct function
- _ispunct_l function
- iswpunct function
- ispunct function
- istpunct function
- ispunct_l function
- _iswpunct_l function
- iswpunct_l function
ms.assetid: 94403240-85c8-40a4-9c2b-e3e95c729c76
ms.openlocfilehash: 54c51c612cf3b491b49d7e141df34ed5b4415520
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953696"
---
# <a name="ispunct-iswpunct-_ispunct_l-_iswpunct_l"></a>ispunct, iswpunct, _ispunct_l, _iswpunct_l

Bir tamsayının bir noktalama karakterini temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int ispunct(
   int c
);
int iswpunct(
   wint_t c
);
int _ispunct_l(
   int c,
   _locale_t locale
);
int _iswpunct_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Sınanacak tamsayı.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, *c* bir noktalama karakterinin belirli bir gösterimiyse sıfır olmayan bir değer döndürür. **ispunct** , boşluk karakteri olmayan yazdırılabilir bir karakter veya **ısalnum** 'ın sıfır dışında olduğu bir karakter için sıfır dışında bir değer döndürür. **ıwpunct** , boşluk geniş karakteri veya **ıswalnum** 'ın sıfır dışında olduğu geniş bir karakter olmayan herhangi bir yazdırılabilir geniş karakter için sıfır dışında bir değer döndürür. Bu yordamların her biri, *c* , test koşulunu karşılamadığı takdirde 0 döndürür.

**İspunct** işlevinin test koşulunun sonucu, yerel ayarın **LC_CTYPE** kategori ayarına bağlıdır; daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md) . **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip olan sürümler, bunun yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

**Ipunct** ve **_ispunct_l** 'nin DAVRANıŞı, *c* 'nin EOF veya 0 ile 0xFF (dahil) aralığında sıfır olmaması durumunda tanımsızdır. Bir hata ayıklama CRT kitaplığı kullanıldığında ve *c* bu değerlerden biri değilse, işlevler bir onaylama işlemi yükseltir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istpunct**|**ispunct**|[_ismbcpunct](ismbcgraph-functions.md)|**iswpunct**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ispunct**|\<CType. h >|
|**iswpunct**|\<CType. h > veya \<wchar. h >|
|**_ispunct_l**|\<CType. h >|
|**_iswpunct_l**|\<CType. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
