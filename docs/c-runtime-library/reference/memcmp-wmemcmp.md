---
title: memcmp, wmemcmp
ms.date: 11/04/2016
api_name:
- memcmp
- wmemcmp
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- memcmp
- wmemcmp
helpviewer_keywords:
- wmemcmp function
- memcmp function
ms.assetid: 0c21c3e3-8ee4-40e5-add1-eb26d225fd8d
ms.openlocfilehash: b18479e50d5b35c8de3dfd11eb34d0d21d45f223
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232462"
---
# <a name="memcmp-wmemcmp"></a>memcmp, wmemcmp

İki arabelleki karakterleri karşılaştırır.

## <a name="syntax"></a>Söz dizimi

```C
int memcmp(
   const void *buffer1,
   const void *buffer2,
   size_t count
);
int wmemcmp(
   const wchar_t * buffer1,
   const wchar_t * buffer2,
   size_t count
);
```

### <a name="parameters"></a>Parametreler

*buffer1*<br/>
İlk arabellek.

*buffer2*<br/>
İkinci arabellek.

*biriktirme*<br/>
Karşılaştırılacak karakter sayısı. ( **Memcmp**için baytları ve **wmemcmp**için geniş karakterleri karşılaştırır).

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri, arabellekler arasındaki ilişkiyi gösterir.

|Döndürülen değer|Buf1 ve buf2 'in ilk *sayı* karakterlerinin ilişkisi|
|------------------|---------------------------------------------------------------|
|< 0|*buffer1* küçüktür *buffer2*|
|0|*buffer1* özdeş *buffer2*|
|> 0|*buffer1* daha büyük *buffer2*|

## <a name="remarks"></a>Açıklamalar

*Buffer1* ve *buffer2* öğesinin ilk *sayı* karakterlerini karşılaştırır ve ilişkilerini gösteren bir değer döndürür. Sıfır olmayan bir dönüş değeri işareti, arabelleklerindeki ilk farklı değer çifti arasındaki farkın işaret değeridir. Değerler **`unsigned char`** **memcmp**için olarak yorumlanır ve **`wchar_t`** **wmemcmp**için.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memcmp**|\<memory.h> veya \<string.h>|
|**wmemcmp**|\<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplığının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_memcmp.c
/* This program uses memcmp to compare
* the strings named first and second. If the first
* 19 bytes of the strings are equal, the program
* considers the strings to be equal.
*/

#include <string.h>
#include <stdio.h>

int main( void )
{
   char first[]  = "12345678901234567890";
   char second[] = "12345678901234567891";
   int int_arr1[] = {1,2,3,4};
   int int_arr2[] = {1,2,3,4};
   int result;

   printf( "Compare '%.19s' to '%.19s':\n", first, second );
   result = memcmp( first, second, 19 );
   if( result < 0 )
      printf( "First is less than second.\n" );
   else if( result == 0 )
      printf( "First is equal to second.\n" );
   else
      printf( "First is greater than second.\n" );

   printf( "Compare '%d,%d' to '%d,%d':\n", int_arr1[0], int_arr1[1], int_arr2[0], int_arr2[1]);
   result = memcmp( int_arr1, int_arr2, sizeof(int) * 2 );
   if( result < 0 )
      printf( "int_arr1 is less than int_arr2.\n" );
   else if( result == 0 )
      printf( "int_arr1 is equal to int_arr2.\n" );
   else
      printf( "int_arr1 is greater than int_arr2.\n" );
}
```

```Output
Compare '1234567890123456789' to '1234567890123456789':
First is equal to second.
Compare '1,2' to '1,2':
int_arr1 is equal to int_arr2.
```

## <a name="see-also"></a>Ayrıca bkz.

[Arabellek Işleme](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
