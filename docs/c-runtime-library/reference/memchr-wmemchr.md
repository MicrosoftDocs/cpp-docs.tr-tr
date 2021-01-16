---
description: 'Daha fazla bilgi edinin: memchr, wmemchr'
title: memchr, wmemchr
ms.date: 1/14/2021
api_name:
- wmemchr
- memchr
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- memchr
- wmemchr
helpviewer_keywords:
- memchr function
- wmemchr function
ms.assetid: 5a348581-28f1-4256-8434-687245f7fc9f
ms.openlocfilehash: f9643dd9c84244916dfdf151efbec1b0014b42e3
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243170"
---
# <a name="memchr-wmemchr"></a>memchr, wmemchr

Bir arabellekteki karakterleri bulur.

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

*arabelleğin*<br/>
Arabellek işaretçisi.

*,*<br/>
Aranacak karakter.

*biriktirme*<br/>
Denetlenecek karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *arabellekteki* *c* 'nin ilk konumuna bir işaretçi döndürür. Aksi takdirde, NULL döndürür.

## <a name="remarks"></a>Açıklamalar

`memchr`ve `wmemchr` *arabelleğin* ilk *sayı* karakterdeki ilk *c* oluşumunu arayın. *C* bulduğunda veya ilk *sayı* karakterini denetlediyseniz, bu yanıt vermez.

C 'de, bu işlevler **`const`** ilk bağımsız değişken için bir işaretçi alır. C++ ' da, iki aşırı yükleme mevcuttur. ' A bir işaretçi döndüren aşırı yükleme, ' a bir işaretçi döndürür; olmayan bir işaretçiyi **`const`** **`const`** alan sürüm olmayan **`const`** bir işaretçi döndürür **`const`** . Makro \_ CRT \_ const \_ doğru \_ aşırı yüklemeleri, bu işlevlerin hem hem de **`const`** **`const`** sürümleriniz varsa tanımlanmıştır. **`const`** C++ ' da her Iki c++ aşırı yüklemesi için davranışa gerek duyuyorsanız \_ const Return simgesini tanımlayın \_ .

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`memchr`|\<memory.h> veya \<string.h>|
|`wmemchr`|\<wchar.h>|

Uyumluluk hakkında daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

### <a name="output"></a>Çıktı

```Output
String to be searched:
             The quick brown dog jumps over the lazy fox
                      1         2         3         4         5
             12345678901234567890123456789012345678901234567890

Search char: r
Result:      r found at position 12
```

## <a name="see-also"></a>Ayrıca bkz.

[Arabellek Işleme](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
