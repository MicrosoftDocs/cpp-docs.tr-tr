---
title: isblank, iswblank, _isblank_l, _iswblank_l
ms.date: 11/04/2016
apiname:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
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
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
ms.openlocfilehash: eb088c4056e2277e188d7f98a57dd36216d013ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287087"
---
# <a name="isblank-iswblank-isblankl-iswblankl"></a>isblank, iswblank, _isblank_l, _iswblank_l

Tamsayının boşluk karakterini temsil edip etmediğini belirler.

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
Test edilecek tamsayı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Yordamların her biri bu döndürür sıfır olmayan *c* bir boşluk veya yatay sekme karakterinin belirli bir gösterimiyse veya bir yerel ayara özgü bir metin satırı içinde sözcükleri ayırmak için kullanılan karakter kümesini biridir. **ısblank** sıfır olmayan bir değer döndürür *c* bir boşluk karakteri (0x20) veya yatay sekme karakteriyse (0x09). İçin test durumunun sonucu **ısblank** işlevleri bağlıdır **LC_CTYPE** kategori ayar yerel; daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md). Sahip olmayan bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı için herhangi bir yerel ayara bağımlı davranış; sahip sürümler **_l** sonekine kullanmaları dışında Bunun yerine iletilen yerel ayar. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

**iswblank** sıfır olmayan bir değer döndürür *c* standart bir alana karşılık gelen bir geniş karakter veya yatay sekme karakterinin.

Davranışını **ısblank** ve **_isblank_l** tanımsızdır *c* EOF değilse veya 0-0xFF aralığındaysa aralığında. Bir hata ayıklama CRT Kitaplığı kullanıldığında ve *c* değil, bu değerleri işlevleri raise onaylama biridir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istblank**|**isblank**|[_ismbcblank](ismbcgraph-functions.md)|**iswblank**|
|**_istblank_l**|**_isblank_l**|[_ismbcblank_l](ismbcgraph-functions.md)|**_iswblank_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isblank**|\<CType.h >|
|**iswblank**|\<CType.h > veya \<wchar.h >|
|**_isblank_l**|\<CType.h >|
|**_iswblank_l**|\<CType.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
