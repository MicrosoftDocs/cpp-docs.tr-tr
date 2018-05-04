---
title: memchr'e, wmemchr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wmemchr
- memchr
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
apitype: DLLExport
f1_keywords:
- memchr
- wmemchr
dev_langs:
- C++
helpviewer_keywords:
- memchr function
- wmemchr function
ms.assetid: 5a348581-28f1-4256-8434-687245f7fc9f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c2ba300275f0154e84f7d2ced21b0893bbe3d85
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="memchr-wmemchr"></a>memchr, wmemchr

Karakter arabellekte bulun.

## <a name="syntax"></a>Sözdizimi

```C
void *memchr(
   const void *buffer,
   int c,
   size_t count
); // C only
void *memchr(
   void *buffer,
   int c,
   size_t count
); // C++ only
const void *memchr(
   const void *buffer,
   int c,
   size_t count
); // C++ only
wchar_t *wmemchr(
   const wchar_t * buffer,
   wchar_t c,
   size_t count
); // C only
wchar_t *wmemchr(
   wchar_t * buffer,
   wchar_t c,
   size_t count
); // C++ only
const wchar_t *wmemchr(
   const wchar_t * buffer,
   wchar_t c,
   size_t count
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Arabellek işaretçi.

*c*<br/>
Aranacak karakter.

*Sayısı*<br/>
Denetlenecek karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bir işaretçi ilk konumunu döndürür *c* içinde *arabellek*. Aksi takdirde döndürür **NULL**.

## <a name="remarks"></a>Açıklamalar

**memchr'e** ve **wmemchr** ilk geçtiği için Ara *c* ilk *sayısı* bayt *arabellek*. Bunu bulduğunda durdurur *c* veya ne zaman kullanıma ilk *sayısı* bayt sayısı.

C, bu işlevler ele bir ** const ** ilk bağımsız değişken için bir işaretçi. C++'da, iki aşırı kullanılabilir. Bir işaretçi alma aşırı ** const ** gösteren bir işaretçi döndürür **const **; bir işaretçi olmayan alır sürüm**const ** gösteren bir işaretçi olmayan döndürür**const **. Her iki makrosu _CRT_CONST_CORRECT_OVERLOADS tanımlanan **const ** ve olmayan-** const ** bu işlevler sürümlerinde kullanılabilir. Olmayan gerektiriyorsa**const ** hem C++, C++ overloadsin davranışını simgesi _CONST_RETURN tanımlayın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memchr'e**|\<Memory.h > veya \<string.h >|
|**wmemchr**|\<wchar.h >|

Uyumluluğu hakkında daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_memchr.c

#include <memory.h>
#include <stdio.h>

int  ch = 'r';
char str[] =    "lazy";
char string[] = "The quick brown dog jumps over the lazy fox";
char fmt1[] =   "         1         2         3         4         5";
char fmt2[] =   "12345678901234567890123456789012345678901234567890";

int main( void )
{
   char *pdest;
   int result;
   printf( "String to be searched:\n             %s\n", string );
   printf( "             %s\n             %s\n\n", fmt1, fmt2 );

   printf( "Search char: %c\n", ch );
   pdest = memchr( string, ch, sizeof( string ) );
   result = (int)(pdest - string + 1);
   if ( pdest != NULL )
      printf( "Result:      %c found at position %d\n", ch, result );
   else
      printf( "Result:      %c not found\n" );
}
```

### <a name="output"></a>Çıkış

```Output
String to be searched:
             The quick brown dog jumps over the lazy fox
                      1         2         3         4         5
             12345678901234567890123456789012345678901234567890

Search char: r
Result:      r found at position 12
```

## <a name="see-also"></a>Ayrıca bkz.

[Ara Bellek Düzenlemesi](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
