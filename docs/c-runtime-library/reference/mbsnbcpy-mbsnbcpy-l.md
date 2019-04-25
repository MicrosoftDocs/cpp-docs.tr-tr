---
title: _mbsnbcpy, _mbsnbcpy_l
ms.date: 11/04/2016
apiname:
- _mbsnbcpy
- _mbsnbcpy_l
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
- mbsnbcpy
- _ftcsncpy
- _mbsnbcpy
- mbsnbcpy_l
- _mbsnbcpy_l
helpviewer_keywords:
- mbsnbcpy function
- _mbsnbcpy_l function
- _mbsnbcpy function
- _tcsncpy function
- tcsncpy_l function
- _tcsncpy_l function
- mbsnbcpy_l function
- tcsncpy function
ms.assetid: 83d17b50-3cbf-4df9-bce8-3b6d52f85d04
ms.openlocfilehash: 1f22e8066b5b32feef642b01ad82955935a450e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285580"
---
# <a name="mbsnbcpy-mbsnbcpyl"></a>_mbsnbcpy, _mbsnbcpy_l

Kopya **n** baytlık dizeyi hedef dizeye. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz [_mbsnbcpy_s, _mbsnbcpy_s_l](mbsnbcpy-s-mbsnbcpy-s-l.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned char * _mbsnbcpy(
   unsigned char * strDest,
   const unsigned char * strSource,
   size_t count
);
unsigned char * _mbsnbcpy_l(
   unsigned char * strDest,
   const unsigned char * strSource,
   size_t count,
   _locale_t locale
);
template <size_t size>
unsigned char * _mbsnbcpy(
   unsigned char (&strDest)[size],
   const unsigned char * strSource,
   size_t count
); // C++ only
template <size_t size>
unsigned char * _mbsnbcpy_l(
   unsigned char (&strDest)[size],
   const unsigned char * strSource,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*strDest*<br/>
Kopyalanacak karakter dizesi için hedef.

*strSource*<br/>
Kopyalanacak karakter dizesi.

*Sayısı*<br/>
Kopyalanacak bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbsnbcpy** karakter hedef dizeye bir işaretçi döndürür. Dönüş değeri bir hatayı göstermek üzere ayrılmıştır.

## <a name="remarks"></a>Açıklamalar

**_Mbsnbcpy** işlev kopyaları *sayısı* bayt *strSource* için *strDest*. Varsa *sayısı* boyutunu aşıyor *strDest* veya üst üste, davranışını kaynak ve hedef dizeleri **_mbsnbcpy** tanımsızdır.

Varsa *strSource* veya *strDest* null bir işaretçiyse, bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, işlev döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri, dışında olmayan, aynıdır **_l** soneki geçerli yerel ayarı ve sahip olmayan sürümleri kullanan **_l** soneki, bunun yerine yerel ayar parametresini kullanın Bu geçirildi. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

> [!IMPORTANT]
> Bu işlevler, arabellek taşma tehditlerine açık olabilir. Arabellek taşmaları, bir unwarranted ayrıcalık yükselmesine neden ve sistemden rastgele bir saldırgan kod yürütmek için kullanılabilir. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

C++'da, bu işlevler, bu işlevlerin daha yeni ve güvenli karşılıklarını çağırma şablon aşırı yüklemeleri vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncpy**|[strncpy](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)|**_mbsnbcpy**|[wcsncpy](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)|
|**_tcsncpy_l**|**_strncpy_l**|**_mbsnbcp_l**|**_wcsncpy_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbcpy**|\<Mbstring.h >|
|**_mbsnbcpy_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
