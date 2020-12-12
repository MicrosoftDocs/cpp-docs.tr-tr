---
description: 'Hakkında daha fazla bilgi edinin: strstr, wcsstr, _mbsstr _mbsstr_l'
title: strstr, wcsstr, _mbsstr, _mbsstr_l
ms.date: 4/2/2020
api_name:
- _mbsstr
- wcsstr
- _mbsstr_l
- strstr
- _o__mbsstr
- _o__mbsstr_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fstrstr
- _ftcsstr
- strstr
- wcsstr
- _mbsstr
- _tcsstr
helpviewer_keywords:
- strings [C++], searching
- mbsstr function
- _ftcsstr function
- ftcsstr function
- fstrstr function
- _tcsstr function
- substrings, finding
- mbsstr_l function
- tcsstr function
- _mbsstr function
- wcsstr function
- _fstrstr function
- _mbsstr_l function
- strstr function
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
ms.openlocfilehash: 05f7cd3b03a56cb5e0e9343bd8cdee98af124988
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181689"
---
# <a name="strstr-wcsstr-_mbsstr-_mbsstr_l"></a>strstr, wcsstr, _mbsstr, _mbsstr_l

Dizedeki arama dizesinin ilk oluşumuna yönelik bir işaretçi döndürür.

> [!IMPORTANT]
> `_mbsstr` ve `_mbsstr_l` Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char *strstr(
   const char *str,
   const char *strSearch
); // C only
char *strstr(
   char *str,
   const char *strSearch
); // C++ only
const char *strstr(
   const char *str,
   const char *strSearch
); // C++ only
wchar_t *wcsstr(
   const wchar_t *str,
   const wchar_t *strSearch
); // C only
wchar_t *wcsstr(
   wchar_t *str,
   const wchar_t *strSearch
); // C++ only
const wchar_t *wcsstr(
   const wchar_t *str,
   const wchar_t *strSearch
); // C++ only
unsigned char *_mbsstr(
   const unsigned char *str,
   const unsigned char *strSearch
); // C only
unsigned char *_mbsstr(
   unsigned char *str,
   const unsigned char *strSearch
); // C++ only
const unsigned char *_mbsstr(
   const unsigned char *str,
   const unsigned char *strSearch
); // C++ only
unsigned char *_mbsstr_l(
   const unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C only
unsigned char *_mbsstr_l(
   unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C++ only
const unsigned char *_mbsstr_l(
   const unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Aranacak null ile sonlandırılmış dize.

*strSearch*<br/>
Aranacak null ile sonlandırılmış dize.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

*Str* Içinde *strSearch* 'ün ilk oluşumuna yönelik bir işaretçi veya *STRSEARCH* , *Str* içinde görünmezse null değerini döndürür. *StrSearch* , sıfır uzunluklu bir dizeye işaret ediyorsa, işlev *Str* döndürür.

## <a name="remarks"></a>Açıklamalar

`strstr`İşlev, *Str* içinde *strSearch* 'ün ilk oluşumuna yönelik bir işaretçi döndürür. Arama, null karakter sonlandırılmasını içermez. `wcsstr` , öğesinin geniş karakterli sürümüdür `strstr` ve `_mbsstr` çok baytlı karakter sürümüdür. Bağımsız değişkenleri ve dönüş değeri `wcsstr` geniş karakterli dizelerdir; bunlar `_mbsstr` çok baytlı karakter dizeleridir. `_mbsstr` parametrelerini doğrular. *Str* veya *strSearch* null ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md) bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, `_mbsstr` `errno` EINVAL olarak ayarlar ve 0 döndürür. `strstr` ve `wcsstr` parametrelerini doğrulamaz. Bu üç işlev, aynı şekilde davranır.

> [!IMPORTANT]
> Bu işlevler, arabellek taşması sorunundan bir tehdit oluşturabilir. Arabellek taşması sorunları, bir sisteme saldırmak için kullanılabilir ve bu, izin verilmeyen ayrıcalık yükselmesine neden olabilir. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

C 'de, bu işlevler **`const`** ilk bağımsız değişken için bir işaretçi alır. C++ ' da, iki aşırı yükleme mevcuttur. ' A bir işaretçi getiren aşırı yükleme, ' a bir işaretçi döndürür. olmayan bir işaretçi **`const`** **`const`** alan sürüm olmayan **`const`** bir işaretçi döndürür **`const`** . Makro _CRT_CONST_CORRECT_OVERLOADS, bu işlevlerin hem hem de **`const`** **`const`** sürümleri kullanılabilir olduğunda tanımlanmıştır. **`const`** Her Iki C++ aşırı yüklemesi için davranışa gerek duyuyorsanız, _CONST_RETURN sembolünü tanımlayın.

Çıkış değeri, LC_CTYPE yerel ayar kategorisi ayarından etkilenir; daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md). **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip sürümler, bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|
|**yok**|**yok**|`_mbsstr_l`|**yok**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`strstr`|\<string.h>|
|`wcsstr`|\<string.h> veya \<wchar.h>|
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h>|

Uyumluluk hakkında daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strstr.c

#include <string.h>
#include <stdio.h>

char str[] =    "lazy";
char string[] = "The quick brown dog jumps over the lazy fox";
char fmt1[] =   "         1         2         3         4         5";
char fmt2[] =   "12345678901234567890123456789012345678901234567890";

int main( void )
{
   char *pdest;
   int  result;
   printf( "String to be searched:\n   %s\n", string );
   printf( "   %s\n   %s\n\n", fmt1, fmt2 );
   pdest = strstr( string, str );
   result = (int)(pdest - string + 1);
   if ( pdest != NULL )
      printf( "%s found at position %d\n", str, result );
   else
      printf( "%s not found\n", str );
}
```

```Output
String to be searched:
   The quick brown dog jumps over the lazy fox
            1         2         3         4         5
   12345678901234567890123456789012345678901234567890

lazy found at position 36
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Multibyte-Character sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[basic_string:: Find](../../standard-library/basic-string-class.md#find)<br/>
