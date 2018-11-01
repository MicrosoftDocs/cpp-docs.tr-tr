---
title: _strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l
ms.date: 11/04/2016
apiname:
- _strnextc
- _mbsnextc_l
- _mbsnextc
- _wcsnextc
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: fe65378908542293433084dcfd37ad6a77663de2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607122"
---
# <a name="strnextc-wcsnextc-mbsnextc-mbsnextcl"></a>_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l

Bir dize sonraki karakteri bulur.

> [!IMPORTANT]
> **_mbsnextc** ve **_mbsnextc_l** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _strnextc(
   const char *str
);
unsigned int _wscnextc(
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

*str*<br/>
Kaynak dizesi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri öğesindeki sonraki karakterin tamsayı değerini döndürür *str*.

## <a name="remarks"></a>Açıklamalar

**_Mbsnextc** işlevi içinde sonraki çok baytlı karakterin tamsayı değerini döndürür *str*, dize işaretçisini ilerletmeden olmadan. **_mbsnextc** çok baytlı karakter sıralarına göre tanır [çok baytlı kod sayfası](../../c-runtime-library/code-pages.md) şu anda kullanımda.

Varsa *str* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev 0 döndürür.

**Güvenlik Notu** bu API, bir arabellek taşması sorunu duruma olası bir tehdit artmasına neden olur. Arabellek taşması sorunları, sistem saldırı, bir unwarranted ayrıcalık yükseltilmesi ile sonuçlanan sık kullanılan bir yöntemdir. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnextc**|**_strnextc**|**_mbsnextc**|**_wcsnextc**|

**_strnextc** ve **_wcsnextc** tek baytlık karakterlerdir dize ve geniş karakter dizesi sürümleri **_mbsnextc**. **_wcsnextc** bulunan sonraki geniş karakterin tamsayı değerini döndürür *str*; **_strnextc** sonraki tek baytlık karakterin tamsayı değerini döndürür *str*. **_strnextc** ve **_wcsnextc** yalnızca bu eşleşmeye ilişkin sağlanırlar ve aksi takdirde kullanılmamalıdır. Daha fazla bilgi için [genel metin eşlemelerini kullanma](../../c-runtime-library/using-generic-text-mappings.md) ve [genel metin eşlemeleri](../../c-runtime-library/generic-text-mappings.md).

**_mbsnextc_l** bunun yerine iletilmiş yerel ayar parametresini kullanması hariç, aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnextc**|\<Mbstring.h >|
|**_mbsnextc_l**|\<Mbstring.h >|
|**_strnextc**|\<Tchar.h >|
|**_wcsnextc**|\<Tchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_strdec, _wcsdec, _mbsdec, _mbsdec_l](strdec-wcsdec-mbsdec-mbsdec-l.md)<br/>
[_strinc, _wcsinc, _mbsinc, _mbsinc_l](strinc-wcsinc-mbsinc-mbsinc-l.md)<br/>
[_strninc, _wcsninc, _mbsninc, _mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
