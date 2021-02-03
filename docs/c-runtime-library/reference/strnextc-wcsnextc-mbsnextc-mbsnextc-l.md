---
description: 'Hakkında daha fazla bilgi edinin: _strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l'
title: _strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l
ms.date: 4/2/2020
api_name:
- _strnextc
- _mbsnextc_l
- _mbsnextc
- _wcsnextc
- _o__mbsnextc
- _o__mbsnextc_l
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
- strnextc
- tcsnextc
- _mbsnextc_l
- _mbsnextc
- mbsnextc_l
- ftcsnextc
- mbsnextc
- _tcsnextc
- _wcsnextc
- _ftcsnextc
- _strnextc
- wcsnextc
helpviewer_keywords:
- _mbsnextc function
- _tcsnextc function
- _wcsnextc function
- tcsnextc function
- strnextc function
- mbsnextc function
- _strnextc function
- _mbsnextc_l function
- mbsnextc_l function
- wcsnextc function
ms.assetid: e3086173-9eb5-4540-a23a-5d866bd05340
ms.openlocfilehash: 7cbe291d19fe09b14cf71989923656f44acff1c7
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522384"
---
# <a name="_strnextc-_wcsnextc-_mbsnextc-_mbsnextc_l"></a>_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l

Dizedeki bir sonraki karakteri bulur.

> [!IMPORTANT]
> **_mbsnextc** ve **_mbsnextc_l** , Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _strnextc(
   const char *str
);
unsigned int _wcsnextc(
   const wchar_t *str
);
unsigned int _mbsnextc(
   const unsigned char *str
);
unsigned int _mbsnextc_l(
   const unsigned char *str,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Kaynak dize.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri *Str* içindeki bir sonraki karakterin tamsayı değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mbsnextc** işlevi, dize işaretçisini ilerletmeksizin *Str* içindeki bir sonraki çok baytlı karakterin tamsayı değerini döndürür. **_mbsnextc** , kullanımda olan [çok baytlı kod sayfasına](../../c-runtime-library/code-pages.md) göre çok baytlı karakter dizilerini tanır.

*Str* **null** ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev 0 döndürür.

**Güvenlik notunun** Bu API, bir arabellek taşması sorunu ile ilgili olası bir tehdit doğurur. Arabellek taşması sorunları, sistem saldırılarına karşı sık kullanılan bir yöntemdir ve bu da garanti edilmemiş ayrıcalık yükselmesine neden olur. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnextc**|**_strnextc**|**_mbsnextc**|**_wcsnextc**|

**_strnextc** ve **_wcsnextc** , **_mbsnextc** tek baytlık karakter dizesidir ve geniş karakterli dize sürümleridir. **_wcsnextc** *Str* içindeki bir sonraki geniş karakterin tamsayı değerini döndürür. **_strnextc** *Str* içindeki bir sonraki tek baytlı karakterin tamsayı değerini döndürür. **_strnextc** ve **_wcsnextc** yalnızca bu eşleme için sağlanır ve aksi halde kullanılmamalıdır. Daha fazla bilgi için bkz. [Generic-Text eşlemelerini](../../c-runtime-library/using-generic-text-mappings.md) ve [Genel metin eşlemelerini](../../c-runtime-library/generic-text-mappings.md)kullanma.

**_mbsnextc_l** , bunun yerine geçirilen yerel ayar parametresini kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnextc**|\<mbstring.h>|
|**_mbsnextc_l**|\<mbstring.h>|
|**_strnextc**|\<tchar.h>|
|**_wcsnextc**|\<tchar.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Multibyte-Character sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_strdec, _wcsdec, _mbsdec, _mbsdec_l](strdec-wcsdec-mbsdec-mbsdec-l.md)<br/>
[_strinc, _wcsinc, _mbsinc, _mbsinc_l](strinc-wcsinc-mbsinc-mbsinc-l.md)<br/>
[_strninc, _wcsninc, _mbsninc, _mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
