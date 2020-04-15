---
title: _strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l
ms.date: 4/2/2020
api_name:
- _strlwr_l
- _strlwr
- _wcslwr_l
- _mbslwr_l
- _wcslwr
- _mbslwr
- _o__mbslwr
- _o__mbslwr_l
- _o__strlwr
- _o__strlwr_l
- _o__wcslwr
- _o__wcslwr_l
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _strlwr
- wcslwr_l
- _ftcslwr
- mbslwr_l
- _mbslwr
- _wcslwr
- strlwr_l
- _tcslwr
- mbslwr
helpviewer_keywords:
- tcslwr function
- _strlwr function
- converting case
- string conversion [C++], case
- mbslwr function
- _strlwr_l function
- strlwr_l function
- _wcslwr function
- ftcslwr function
- strings [C++], case
- _tcslwr_l function
- _wcslwr_l function
- wcslwr_l function
- mbslwr_l function
- tcslwr_l function
- _tcslwr function
- converting case, CRT functions
- _ftcslwr function
- _mbslwr function
- case, converting
- strings [C++], converting case
- _mbslwr_l function
ms.assetid: d279181d-2e7d-401f-ab44-6e7c2786a046
ms.openlocfilehash: 40bf64af8284d84c6e58bcb3e8591a1ef6fc9f48
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363812"
---
# <a name="_strlwr-_wcslwr-_mbslwr-_strlwr_l-_wcslwr_l-_mbslwr_l"></a>_strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l

Bir dizeyi küçük harfe dönüştürür. Bu işlevlerin daha güvenli sürümleri mevcuttur; [_strlwr_s, _strlwr_s_l, _mbslwr_s, _mbslwr_s_l, _wcslwr_s, _wcslwr_s_l](strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)bakın.

> [!IMPORTANT]
> **_mbslwr** ve **_mbslwr_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
char *_strlwr(
   char * str
);
wchar_t *_wcslwr(
   wchar_t * str
);
unsigned char *_mbslwr(
   unsigned char * str
);
char *_strlwr_l(
   char * str,
   _locale_t locale
);
wchar_t *_wcslwr_l(
   wchar_t * str,
   _locale_t locale
);
unsigned char *_mbslwr_l(
   unsigned char * str,
   _locale_t locale
);
template <size_t size>
char *_strlwr(
   char (&str)[size]
); // C++ only
template <size_t size>
wchar_t *_wcslwr(
   wchar_t (&str)[size]
); // C++ only
template <size_t size>
unsigned char *_mbslwr(
   unsigned char (&str)[size]
); // C++ only
template <size_t size>
char *_strlwr_l(
   char (&str)[size],
   _locale_t locale
); // C++ only
template <size_t size>
wchar_t *_wcslwr_l(
   wchar_t (&str)[size],
   _locale_t locale
); // C++ only
template <size_t size>
unsigned char *_mbslwr_l(
   unsigned char (&str)[size],
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Küçük harfe dönüştürmek için null-sonlandırılan dize.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri dönüştürülen dize için bir işaretçi döndürür. Değişiklik yerinde yapıldığından, döndürülen işaretçi giriş bağımsız değişkeni olarak geçen işaretçiyle aynıdır. Bir hatayı belirtmek için hiçbir iade değeri ayrılmıştır.

## <a name="remarks"></a>Açıklamalar

**_strlwr** işlevi, *str'deki* büyük harfleri, yerel LC_CTYPE **kategori** ayarına göre belirlendiği gibi küçük harfe dönüştürür. Diğer karakterler etkilenmez. **LC_CTYPE**hakkında daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md)bakın. Bu işlevlerin **_l** soneki olmayan sürümleri, yerel e-çözüme bağlı davranışları için geçerli yerel durumu kullanır; **_l** soneki olan sürümler, bunun yerine geçirilen yerelliği kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

**_wcslwr** ve **_mbslwr** işlevleri **_strlwr**geniş karakterli ve çok bayt karakterli versiyonlarıdır. _wcslwr bağımsız değişkeni **_wcslwr** ve geri dönüş değeri geniş karakterli dizeleridir; **_mbslwr** çok bayt karakterli dizeleri vardır. Bu üç işlev aynı şekilde çalışır.

*Str* bir **NULL** işaretçisiise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler özgün dize döndürün ve **EINVAL** **için errno** ayarlayın.

C++'da, bu işlevlerin daha yeni ve güvenli karşıtlarını çağıran şablon aşırı yüklemeleri vardır. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcslwr**|**_strlwr**|**_mbslwr**|**_wcslwr**|
|**_tcslwr_l**|**_strlwr_l**|**_mbslwr_l**|**_wcslwr_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strlwr**, **_strlwr_l**|\<string.h>|
|**_wcslwr**, **_wcslwr_l**|\<string.h> \<veya wchar.h>|
|**_mbslwr**, **_mbslwr_l**|\<mbstring.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_strlwr.c
// compile with: /W3
// This program uses _strlwr and _strupr to create
// uppercase and lowercase copies of a mixed-case string.
#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[100] = "The String to End All Strings!";
   char * copy1 = _strdup( string ); // make two copies
   char * copy2 = _strdup( string );

   _strlwr( copy1 ); // C4996
   // Note: _strlwr is deprecated; consider using _strlwr_s instead
   _strupr( copy2 ); // C4996
   // Note: _strupr is deprecated; consider using _strupr_s instead

   printf( "Mixed: %s\n", string );
   printf( "Lower: %s\n", copy1 );
   printf( "Upper: %s\n", copy2 );

   free( copy1 );
   free( copy2 );
}
```

```Output
Mixed: The String to End All Strings!
Lower: the string to end all strings!
Upper: THE STRING TO END ALL STRINGS!
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[_strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr](strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md)<br/>
