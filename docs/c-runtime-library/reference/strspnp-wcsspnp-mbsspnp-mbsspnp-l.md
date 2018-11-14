---
title: _strspnp, _wcsspnp, _mbsspnp, _mbsspnp_l
ms.date: 11/04/2016
apiname:
- _mbsspnp
- _wcsspnp
- _mbsspnp_l
- _strspnp
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
- _tcsspnp
- _mbsspnp
- strspnp
- _ftcsspnp
- _mbsspnp_l
- wcsspnp
- mbsspnp_l
- _wcsspnp
- _strspnp
- mbsspnp
helpviewer_keywords:
- _strspnp function
- _wcsspnp function
- _mbsspnp_l function
- strspnp function
- mbsspnp function
- wcsspnp function
- _mbsspnp function
- mbsspnp_l function
- _tcsspnp function
- tcsspnp function
ms.assetid: 1ce18100-2edd-4c3b-af8b-53f204d80233
ms.openlocfilehash: 9a4a0d2f9b9940e181625b129e5ded8bb9644c39
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521238"
---
# <a name="strspnp-wcsspnp-mbsspnp-mbsspnpl"></a>_strspnp, _wcsspnp, _mbsspnp, _mbsspnp_l

İçinde başka dizesi verilmiş belirli bir dizedeki ilk karaktere bir işaretçi döndürür.

> [!IMPORTANT]
> **_mbsspnp** ve **_mbsspnp_l** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char *_strspnp(
   const char *str,
   const char *charset
);
wchar_t *_wcsspnp(
   const unsigned wchar_t *str,
   const unsigned wchar_t *charset
);
unsigned char *_mbsspnp(
   const unsigned char *str,
   const unsigned char *charset
);
unsigned char *_mbsspnp_l(
   const unsigned char *str,
   const unsigned char *charset,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Aramak için null ile sonlandırılmış dize.

*karakter kümesi*<br/>
Null ile sonlandırılmış karakter kümesi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_strspnp**, **_wcsspnp**, ve **_mbsspnp** ilk karakter, bir işaretçi döndürür *str* ait olmayan karakterkümesini*charset*. Bu işlevlerin her biri döndürür **NULL** varsa *str* tamamen karakterlerinden oluşuyorsa *charset*. Bu yordamların her biri için dönüş değeri bir hatayı göstermek için ayrılmıştır.

## <a name="remarks"></a>Açıklamalar

**_Mbsspnp** işlevi ilk karakteri olan çok baytlı karaktere bir işaretçi döndürür *str* ait olmayan karakter kümesini *charset*. **_mbsspnp** çok baytlı karakter sıralarına göre tanır [çok baytlı kod sayfası](../../c-runtime-library/code-pages.md) şu anda kullanımda. Arama boş karakterlerin sonlandırılmasını içermez.

Ya da *str* veya *charset* null bir işaretçiyse, bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, işlev döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsspnp**|**_strspnp**|**_mbsspnp**|**_wcsspnp**|

**_strspnp** ve **_wcsspnp** tek baytlık karakter ve geniş karakter sürümleri **_mbsspnp**. **_strspnp** ve **_wcsspnp** öğesine aynı şekilde davranır **_mbsspnp** Aksi takdirde; bunlar yalnızca bu eşleşmeye ilişkin sağlanırlar ve başka bir nedenle kullanılmamalıdır. Daha fazla bilgi için [genel metin eşlemelerini kullanma](../../c-runtime-library/using-generic-text-mappings.md) ve [genel metin eşlemeleri](../../c-runtime-library/generic-text-mappings.md).

**_mbsspnp_l** bunun yerine iletilmiş yerel ayar parametresini kullanması hariç, aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsspnp**|\<Mbstring.h >|
|**_strspnp**|\<Tchar.h >|
|**_wcsspnp**|\<Tchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_mbsspnp.c
#include <mbstring.h>
#include <stdio.h>

int main( void ) {
   const unsigned char string1[] = "cabbage";
   const unsigned char string2[] = "c";
   unsigned char *ptr = 0;
   ptr = _mbsspnp( string1, string2 );
   printf( "%s\n", ptr);
}
```

### <a name="output"></a>Çıkış

```Output
abbage
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
