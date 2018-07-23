---
title: strstr, wcsstr, _mbsstr, _mbsstr_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsstr
- wcsstr
- _mbsstr_l
- strstr
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _fstrstr
- _ftcsstr
- strstr
- wcsstr
- _mbsstr
- _tcsstr
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ea5ed6c4441ebd98462562ac9405d6f8c115c61
ms.sourcegitcommit: 04d327940787df1297b72d534f388a035d472af0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39181100"
---
# <a name="strstr-wcsstr-mbsstr-mbsstrl"></a>strstr, wcsstr, _mbsstr, _mbsstr_l
Bir arama dizesinin bir dizede ilk geçtiği yere bir işaretçi döndürür.

> [!IMPORTANT]
> `_mbsstr` ve `_mbsstr_l` Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*str*<br/>
Aramak için null ile sonlandırılmış dize.

*strSearch*<br/>
Aramak için null ile sonlandırılmış dize.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

İlk geçtiği bir işaretçi döndürür *strSearch* içinde *str*, veya yoksa NULL *strSearch* görünmez *str*. Varsa *strSearch* işaret sıfır uzunluğunda bir dize için işlev döndürür *str*.

## <a name="remarks"></a>Açıklamalar

`strstr` İşlevi için ilk geçtiği bir işaretçi döndürür *strSearch* içinde *str*. Arama boş karakterlerin sonlandırılmasını içermez. `wcsstr` öğesinin geniş karakterli sürümüdür `strstr` ve `_mbsstr` çok baytlı karakter sürümüdür. Bağımsız değişkenler ve dönüş değeri `wcsstr` geniş karakterli dizelerdir; `_mbsstr` çok baytlı karakter dizeleridir. `_mbsstr` kendi parametrelerini doğrular. Varsa *str* veya *strSearch* NULL ise açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütmenin devam etmesine izin verilirse `_mbsstr` ayarlar `errno` EINVAL ve 0 döndürür. `strstr` ve `wcsstr` kendi parametrelerini doğrulamazlar. Bu üç işlev aynı şekilde davranır.

> [!IMPORTANT]
> Bu işlevler, arabellek taşması sorunu kaynaklanan bir tehdit tabi olabilirsiniz. Arabellek taşması sorunları, bir unwarranted ayrıcalık yükselmesine neden olabilir rastgele kod yürütülmesine izin verebilir çünkü bir sistem saldırmak için kullanılabilir. Daha fazla bilgi için [arabellek taşmalarını](http://msdn.microsoft.com/library/windows/desktop/ms717795).

C'de bu işlevler alır bir **const** ilk bağımsız değişken için bir işaretçi. C++'da, iki aşırı yüklemesi kullanılabilir. Bir işaretçi alan aşırı yüklemesini **const** bir işaretçi döndürür **const**; olmayan bir işaretçiye alan sürüm**const** olmayan bir işaretçi döndürür **const**. Her iki makro _CRT_CONST_CORRECT_OVERLOADS tanımlanan **const** ve olmayan-**const** bu işlevlerin sürümleri mevcuttur. Olmayan gerektiriyorsa**const** davranışı için her iki C++ aşırı _const_return sembolünü.

Çıkış değeri LC_CTYPE yerel ayar kategori ayarından etkilenir; Daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md). Sahip olmayan bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı kullanır bu yerel ayara bağlı davranışı için; sahip sürümler **_l** sonekine yerine kullandıkları dışında geçirilen yerel ayar parametresini. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|
|**yok**|**yok**|`_mbsstr_l`|**yok**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`strstr`|\<String.h >|
|`wcsstr`|\<String.h > veya \<wchar.h >|
|`_mbsstr`, `_mbsstr_l`|\<Mbstring.h >|

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

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[basic_string::Find](../../standard-library/basic-string-class.md#find)<br/>
