---
title: _strninc, _wcsninc, _mbsninc, _mbsninc_l
ms.date: 4/2/2020
api_name:
- _mbsninc
- _mbsninc_l
- _wcsninc
- _strninc
- _o__mbsninc
- _o__mbsninc_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strninc
- wcsninc
- mbsninc_l
- _strninc
- _tcsninc
- mbsninc
- _mbsninc_l
- _ftcsninc
- _wcsninc
- _mbsninc
helpviewer_keywords:
- _mbsninc_l function
- mbsninc function
- _strninc function
- tcsninc function
- wcsninc function
- _mbsninc function
- strninc function
- _wcsninc function
- mbsninc_l function
- _tcsninc function
ms.assetid: 6caace64-f9e4-48c0-afa8-ea51824ad723
ms.openlocfilehash: 297d2fdf940ab81a3d636d4726e6e6a345ce5c02
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364473"
---
# <a name="_strninc-_wcsninc-_mbsninc-_mbsninc_l"></a>_strninc, _wcsninc, _mbsninc, _mbsninc_l

Bir dize işaretçisini **n** karakterlere göre ilerletin.

> [!IMPORTANT]
> **_mbsninc** ve **_mbsninc_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
char *_strninc(
   const char *str,
   size_t count
);
wchar_t *_wcsninc(
   const wchar_t *str,
   size_t count
);
unsigned char *_mbsninc(
   const unsigned char *str,
   size_t count
);
unsigned char *_mbsninc(
   const unsigned char *str,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Kaynak dize.

*Sayısı*<br/>
Dize işaretçisini artımlı karakter sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, sağlanan işaretçi **NULL**ise *str sayısı* karakterleri veya **NULL** tarafından artımlı *sonra* *str* için bir işaretçi döndürür. *Sayım* *str'deki*karakter sayısından büyük veya eşitse, sonuç tanımsızdır.

## <a name="remarks"></a>Açıklamalar

**_mbsninc** işlevi, *sayı* çok bayt karakterleri ile *str.* **_mbsninc,** şu anda kullanılmakta olan [çok bayt kod sayfasına](../../c-runtime-library/code-pages.md) göre çok bayt karakter dizilerini tanır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsninc**|**_strninc**|**_mbsninc**|**_wcsninc**|

**_strninc** ve **_wcsninc** **_mbsninc**tek bayt karakterli dize ve geniş karakterli dize sürümleridir. **_wcsninc** ve **_strninc** yalnızca bu eşleme için sağlanır ve başka türlü kullanılmamalıdır. Daha fazla bilgi için [genel metin eşlemelerini](../../c-runtime-library/using-generic-text-mappings.md) ve Genel [Metin Eşlemelerini](../../c-runtime-library/generic-text-mappings.md)Kullanma'ya bakın.

**_mbsninc_l,** bunun yerine geçirilen yerel parametreyi kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsninc**|\<mbstring.h>|
|**_mbsninc_l**|\<mbstring.h>|
|**_strninc**|\<tchar.h>|
|**_wcsninc**|\<tchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_strdec, _wcsdec, _mbsdec, _mbsdec_l](strdec-wcsdec-mbsdec-mbsdec-l.md)<br/>
[_strinc, _wcsinc, _mbsinc, _mbsinc_l](strinc-wcsinc-mbsinc-mbsinc-l.md)<br/>
[_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
