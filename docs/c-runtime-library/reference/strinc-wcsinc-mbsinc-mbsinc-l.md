---
title: _strinc, _wcsinc, _mbsinc, _mbsinc_l
ms.date: 11/04/2016
apiname:
- _mbsinc
- _wcsinc
- _mbsinc_l
- _strinc
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
- mbsinc_l
- _strinc
- strinc
- _mbsinc
- _wcsinc
- wcsinc
- mbsinc
- _mbsinc_l
helpviewer_keywords:
- _mbsinc function
- wcsinc function
- mbsinc_l function
- _strinc function
- strinc function
- _mbsinc_l function
- mbsinc function
- _wcsinc function
- _tcsinc function
- tcsinc function
ms.assetid: 54685943-8e2c-45e9-a559-2d94930dc6b4
ms.openlocfilehash: dae14fc7b66b9be4e1016c5409a93cd172691fed
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51520402"
---
# <a name="strinc-wcsinc-mbsinc-mbsincl"></a>_strinc, _wcsinc, _mbsinc, _mbsinc_l

Dize işaretçisine bir karakter yoluyla ilerler.

> [!IMPORTANT]
> **_mbsinc** ve **_mbsinc_l** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char *_strinc(
   const char *current,
   _locale_t locale
);
wchar_t *_wcsinc(
   const wchar_t *current,
   _locale_t locale
);
unsigned char *_mbsinc(
   const unsigned char *current
);
unsigned char *_mbsinc_l(
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Geçerli*<br/>
Karakter işaretçisi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri hemen izleyen karaktere bir işaretçi döndürür *geçerli*.

## <a name="remarks"></a>Açıklamalar

**_Mbsinc** işlevi hemen izleyen çok baytlı karakterin ilk baytına bir işaretçi döndürür *geçerli*. **_mbsinc** çok baytlı karakter sıralarına göre tanır [çok baytlı kod sayfasına](../../c-runtime-library/code-pages.md) , şu anda kullanımda; **_mbsinc_l** bunun yerine iletilen yerel ayar parametresini kullanması hariç, aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Genel metin işlevi **_tcsinc**eşlenir Tchar.h'de tanımlanan **_mbsinc** varsa **_MBCS** tanımlanmış, veya **_wcsinc** varsa **_UNICODE** tanımlanmış. Aksi takdirde, **_tcsinc** eşlendiği **_strinc**. **_strinc** ve **_wcsinc** tek baytlık karakter ve geniş karakterli sürümleridir **_mbsinc**. **_strinc** ve **_wcsinc** yalnızca bu eşleşmeye ilişkin sağlanırlar ve aksi takdirde kullanılmamalıdır. Daha fazla bilgi için [genel metin eşlemelerini kullanma](../../c-runtime-library/using-generic-text-mappings.md) ve [genel metin eşlemeleri](../../c-runtime-library/generic-text-mappings.md).

Varsa *geçerli* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevi döndürür **EINVAL** ve ayarlar **errno** için **EINVAL**.

> [!IMPORTANT]
> Bu işlevler, arabellek taşma tehditlerine açık olabilir. Arabellek taşmaları, bir unwarranted ayrıcalık yükselmesine neden olabileceği için sistem saldırıları için kullanılabilir. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsinc**|\<Mbstring.h >|
|**_mbsinc_l**|\<Mbstring.h >|
|**_strinc**|\<Tchar.h >|
|**_wcsinc**|\<Tchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdec, _wcsdec, _mbsdec, _mbsdec_l](strdec-wcsdec-mbsdec-mbsdec-l.md)<br/>
[_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
[_strninc, _wcsninc, _mbsninc, _mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
