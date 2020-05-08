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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: fe35d3b37d5aadfbeae69de5ff00c349a2263e30
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914201"
---
# <a name="_strninc-_wcsninc-_mbsninc-_mbsninc_l"></a>_strninc, _wcsninc, _mbsninc, _mbsninc_l

Bir dize işaretçisini **n** karakterle ilerletir.

> [!IMPORTANT]
> **_mbsninc** ve **_mbsninc_l** , Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*üstbilgisine*<br/>
Kaynak dize.

*biriktirme*<br/>
Bir dize işaretçisinin artırılacağı karakter sayısı.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, *Str* *sayı* karakterleri ile arttırıldıktan sonra Str veya sağlanan işaretçi **null**ise **null** *olarak bir* işaretçi döndürür. *Count* , *Str*içindeki karakter sayısından büyükse veya eşitse sonuç tanımsızdır.

## <a name="remarks"></a>Açıklamalar

**_Mbsninc** işlevi, çok baytlı karakterleri *sayarak* *Str* 'yi arttırır. **_mbsninc** , kullanımda olan [çok baytlı kod sayfasına](../../c-runtime-library/code-pages.md) göre çok baytlı karakter dizilerini tanır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsninc**|**_strninc**|**_mbsninc**|**_wcsninc**|

**_strninc** ve **_wcsninc** , **_mbsninc**tek baytlık karakter dizesidir ve geniş karakterli dize sürümleridir. **_wcsninc** ve **_strninc** yalnızca bu eşleme için sağlanır ve aksi halde kullanılmamalıdır. Daha fazla bilgi için bkz. [Genel metin eşlemelerini](../../c-runtime-library/using-generic-text-mappings.md) ve [Genel metin eşlemelerini](../../c-runtime-library/generic-text-mappings.md)kullanma.

**_mbsninc_l** , bunun yerine geçirilen yerel ayar parametresini kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsninc**|\<mbstring. h>|
|**_mbsninc_l**|\<mbstring. h>|
|**_strninc**|\<Tchar. h>|
|**_wcsninc**|\<Tchar. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_strdec, _wcsdec, _mbsdec, _mbsdec_l](strdec-wcsdec-mbsdec-mbsdec-l.md)<br/>
[_strinc, _wcsinc, _mbsinc, _mbsinc_l](strinc-wcsinc-mbsinc-mbsinc-l.md)<br/>
[_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
