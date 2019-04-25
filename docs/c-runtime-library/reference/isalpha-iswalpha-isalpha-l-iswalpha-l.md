---
title: isalpha, iswalpha, _isalpha_l, _iswalpha_l
ms.date: 11/04/2016
apiname:
- iswalpha
- _iswalpha_l
- isalpha
- _isalpha_l
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
- _istalpha
- _ismbcalpha_l
- isalpha
- _isalpha_l
- iswalpha
- _istalpha_l
- _iswalpha_l
helpviewer_keywords:
- _iswalpha_l function
- _isalpha_l function
- _ismbcalpha_l function
- _istalpha_l function
- _ismbcalpha function
- isalpha function
- iswalpha function
- istalpha function
- _istalpha function
ms.assetid: ed6cc2be-c4b0-4475-87ac-bc06d8c23064
ms.openlocfilehash: 47b7e43172884524e50e332dcb421e84a99b9806
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158000"
---
# <a name="isalpha-iswalpha-isalphal-iswalphal"></a>isalpha, iswalpha, _isalpha_l, _iswalpha_l

Bir tamsayı alfabetik bir karakteri temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isalpha(
   int c
);
int iswalpha(
   wint_t c
);
int _isalpha_l(
   int c,
   _locale_t locale
);
int _iswalpha_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Test edilecek tamsayı.

*Yerel ayar*<br/>
Geçerli yerel ayarı yerine kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Yordamların her biri bu döndürür sıfır olmayan *c* alfabetik bir karakter belirli bir gösterimidir. **isalpha** sıfır olmayan bir değer döndürür *c* A - Z veya a - z aralıkları içinde. **iswalpha** yalnızca geniş karakterler için sıfır olmayan bir değer döndüren [iswupper](isupper-isupper-l-iswupper-iswupper-l.md) veya **iswlower** sıfır değil; diğer bir deyişle, geniş diğer bir deyişle bir için bir uygulama tanımlı kümesinin karakter hangi hiçbiri **iswcntrl**, **iswdigit**, **iswpunct**, veya **iswspace** sıfır değil. Bu yordamların her biri 0 döndürür *c* test koşulu karşılamayan.

Sahip bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı yerine iletilen yerel ayar parametresini kullanın. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Davranışını **isalpha** ve **_isalpha_l** tanımsızdır *c* EOF değilse veya 0-0xFF aralığındaysa aralığında. Bir hata ayıklama CRT Kitaplığı kullanıldığında ve *c* değil, bu değerleri işlevleri raise onaylama biridir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istalpha**|**isalpha**|**_ismbcalpha**|**iswalpha**|
|**_istalpha_l**|**_isalpha_l**|**_ismbcalpha_l**|**_iswalpha_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isalpha**|\<CType.h >|
|**iswalpha**|\<CType.h > veya \<wchar.h >|
|**_isalpha_l**|\<CType.h >|
|**_iswalpha_l**|\<CType.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
