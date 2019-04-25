---
title: ispunct, iswpunct, _ispunct_l, _iswpunct_l
ms.date: 11/04/2016
apiname:
- ispunct
- _iswpunct_l
- iswpunct
- _ispunct_l
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 209f94bb8f9d3338f62b719d4d4b94b152ed5ab7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286541"
---
# <a name="ispunct-iswpunct-ispunctl-iswpunctl"></a>ispunct, iswpunct, _ispunct_l, _iswpunct_l

Bir tamsayı Noktalama karakterini temsil edip etmediğini belirler.

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
Test edilecek tamsayı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Yordamların her biri bu döndürür sıfır olmayan *c* bir noktalama karakteri belirli bir gösterimidir. **ispunct** bir boşluk karakteri veya bir karakter değil herhangi bir yazdırılabilir karakter için sıfır olmayan bir değer döndürür **isalnum** sıfır değil. **iswpunct** ne boşluk geniş karakteri, ne de geniş bir karakter yazdırılabilir geniş karakter için sıfır olmayan bir değer döndürür **iswalnum** sıfır değil. Bu yordamların her biri 0 döndürür *c* test koşulu karşılamayan.

İçin test durumunun sonucu **ispunct** işlevi bağlıdır **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Sahip olmayan bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı için herhangi bir yerel ayara bağımlı davranış; sahip sürümler **_l** sonekine kullanmaları dışında Bunun yerine iletilen yerel ayar. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Davranışını **ispunct** ve **_ispunct_l** tanımsızdır *c* EOF değilse veya 0-0xFF aralığındaysa aralığında. Bir hata ayıklama CRT Kitaplığı kullanıldığında ve *c* değil, bu değerleri işlevleri raise onaylama biridir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istpunct**|**ispunct**|[_ismbcpunct](ismbcgraph-functions.md)|**iswpunct**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ispunct**|\<CType.h >|
|**iswpunct**|\<CType.h > veya \<wchar.h >|
|**_ispunct_l**|\<CType.h >|
|**_iswpunct_l**|\<CType.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
