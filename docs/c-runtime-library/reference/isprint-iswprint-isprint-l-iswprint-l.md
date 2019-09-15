---
title: isprint, iswprint, _isprint_l, _iswprint_l
ms.date: 11/04/2016
api_name:
- iswprint
- isprint
- _isprint_l
- _iswprint_l
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- iswprint
- _istprint
- isprint
helpviewer_keywords:
- _istprint function
- iswprint function
- _iswprint_l function
- isprint_l function
- istprint function
- isprint function
- iswprint_l function
- _isprint_l function
ms.assetid: a8bbcdb0-e8d0-4d8c-ae4e-56d3bdee6ca3
ms.openlocfilehash: 282b72fcec84f8096ce0d54cd114e756aeafbc85
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953754"
---
# <a name="isprint-iswprint-_isprint_l-_iswprint_l"></a>isprint, iswprint, _isprint_l, _iswprint_l

Bir tamsayının yazdırılabilir bir karakteri temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isprint(
   int c
);
int iswprint(
   wint_t c
);
int _isprint_l(
   int c,
   _locale_t locale
);
int _iswprint_l(
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

Bu yordamların her biri, *c* , yazdırılabilir bir karakterin belirli bir gösterimiyse sıfır olmayan bir değer döndürür. *c* , yazdırılabilir bir karakter ise, **ısprint** sıfır dışında bir değer döndürür. buna boşluk karakteri (0x20-0x7E) dahildir. *c* , yazdırılabilir geniş bir karakterse **ıswprint** sıfır dışında bir değer döndürür; bu da boşluk geniş karakteri içerir. Bu yordamların her biri, *c* , test koşulunu karşılamadığı takdirde 0 döndürür.

Bu işlevlerin test koşulunun sonucu, yerel ayarın **LC_CTYPE** kategori ayarına bağlıdır; daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md) . **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip olan sürümler, bunun yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*C* , EOF veya 0 ile 0xFF (dahil) aralığında değilse, **ısprint** ve **_isprint_l** davranışı tanımsızdır. Bir hata ayıklama CRT kitaplığı kullanıldığında ve *c* bu değerlerden biri değilse, işlevler bir onaylama işlemi yükseltir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_unicode tanımlı|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istprint**|**isprint**|[_ismbcprint](ismbcgraph-functions.md)|**iswprınt**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isprint**|\<CType. h >|
|**iswprınt**|\<CType. h > veya \<wchar. h >|
|**_isprint_l**|\<CType. h >|
|**_iswprint_l**|\<CType. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
