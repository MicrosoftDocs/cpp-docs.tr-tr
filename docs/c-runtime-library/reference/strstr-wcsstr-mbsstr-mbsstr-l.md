---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 06fb79ac050f4e1c357a76a782730cd72cbdadec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316937"
---
# <a name="strstr-wcsstr-_mbsstr-_mbsstr_l"></a>strstr, wcsstr, _mbsstr, _mbsstr_l

Bir dizedeki bir arama dizesinin ilk oluşumuna işaretçiyi döndürür.

> [!IMPORTANT]
> `_mbsstr`ve `_mbsstr_l` Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*Str*<br/>
Aramak için null-terminated string.

*strArama*<br/>
Aramak için null-terminated string.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

*strSearch str'de*görünmüyorsa *strSearch'ün* *strSearch* ilk oluşumuna işaretçi verir veya NULL' da *.* *strSearch* sıfır uzunlukta bir dize işaret ederse, işlev *str*döndürür.

## <a name="remarks"></a>Açıklamalar

İşlev `strstr` *str*arama ilk oluşumu *strSearch* için bir işaretçi döndürür. Arama, null karakterleri sonlandırmayı içermez. `wcsstr`geniş karakterli versiyonudur `strstr` `_mbsstr` ve çok bayt karakterli sürümüdür. Bağımsız `wcsstr` değişkenler ve geri dönüş değeri geniş karakterli dizeleri; olanlar `_mbsstr` çok bayt karakterli dizeleri vardır. `_mbsstr`parametrelerini doğrular. *str* veya *strSearch* NULL ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmenin devam etmesine `_mbsstr` izin `errno` verilirse, EINVAL'e ayarlar ve 0 döndürür. `strstr`ve `wcsstr` parametrelerini doğrulamayın. Bu üç işlev aynı şekilde çalışır.

> [!IMPORTANT]
> Bu işlevler, arabellek taşma sorunu bir tehdit tabi olabilir. Arabellek taşma sorunları, gereksiz bir ayrıcalık yükselmesine neden olabilecek rasgele kodun yürütülmesine izin verebileceğinden bir sisteme saldırmak için kullanılabilir. Daha fazla bilgi için [bkz.](/windows/win32/SecBP/avoiding-buffer-overruns)

C'de, bu işlevler ilk bağımsız değişken için bir **const** işaretçisi alır. C++'da iki aşırı yükleme kullanılabilir. **Const** için bir işaretçi alır aşırı yükleme **const**bir işaretçi döndürür; olmayan**const** bir işaretçi alır sürümü**non-const**bir işaretçi döndürür. Makro _CRT_CONST_CORRECT_OVERLOADS, bu işlevlerin **hem const** hem de**const** olmayan sürümleri varsa tanımlanır. Her iki C++ aşırı yüklemesi için**const** olmayan davranışı istiyorsanız, _CONST_RETURN simgesini tanımlayın.

Çıktı değeri, LC_CTYPE yerel kategori ayarından etkilenir; daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md)bakın. **_l** soneki olmayan bu işlevlerin sürümleri, bu yerel eki bağımlı davranış için geçerli yerel **_l** soneki olan sürümler, bunun yerine geçirilen yerel parametreyi kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|
|**Yok**|**Yok**|`_mbsstr_l`|**Yok**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`strstr`|\<string.h>|
|`wcsstr`|\<string.h> \<veya wchar.h>|
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h>|

Uyumluluk hakkında daha fazla bilgi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[basic_string::bul](../../standard-library/basic-string-class.md#find)<br/>
