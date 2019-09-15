---
title: isblank, iswblank, _isblank_l, _iswblank_l
ms.date: 11/04/2016
api_name:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
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
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
ms.openlocfilehash: 022eba0335facc597f0608d63cfb58e0146e0f23
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954512"
---
# <a name="isblank-iswblank-_isblank_l-_iswblank_l"></a>isblank, iswblank, _isblank_l, _iswblank_l

Bir tamsayının boş bir karakteri temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isblank(
   int c
);
int iswblank(
   wint_t c
);
int _isblank_l(
   int c,
   _locale_t locale
);
int _iswblank_l(
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

Bu yordamların her biri, *c* 'nin belirli bir boşluk veya yatay sekme karakteri gösterimi olması veya bir metin satırı içinde sözcükleri ayırmak için kullanılan yerel ayara özgü bir karakter kümesinden biridir. *c* bir boşluk karakteri (0x20) veya yatay sekme karakteriyse (0x09), **ISBLANK** sıfır dışında bir değer döndürür. **ISBLANK** işlevlerinin test koşulunun sonucu, yerel ayarın **LC_CTYPE** kategori ayarına bağlıdır; daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md). **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip olan sürümler, bunun yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*c* , standart bir boşluk veya yatay sekme karakterine karşılık gelen geniş bir karakter ise, **ıswblank** sıfır dışında bir değer döndürür.

*C* , EOF veya 0 ile 0xFF (dahil) aralığında değilse, **ıblank** ve **_isblank_l** davranışı tanımsızdır. Bir hata ayıklama CRT kitaplığı kullanıldığında ve *c* bu değerlerden biri değilse, işlevler bir onaylama işlemi yükseltir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istblank**|**ISBLANK**|[_ismbcblank](ismbcgraph-functions.md)|**ıswblank**|
|**_istblank_l**|**_isblank_l**|[_ismbcblank_l](ismbcgraph-functions.md)|**_iswblank_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ISBLANK**|\<CType. h >|
|**ıswblank**|\<CType. h > veya \<wchar. h >|
|**_isblank_l**|\<CType. h >|
|**_iswblank_l**|\<CType. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
