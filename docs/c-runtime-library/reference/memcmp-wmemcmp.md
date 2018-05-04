---
title: memcmp, wmemcmp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- memcmp
- wmemcmp
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
apitype: DLLExport
f1_keywords:
- memcmp
- wmemcmp
dev_langs:
- C++
helpviewer_keywords:
- wmemcmp function
- memcmp function
ms.assetid: 0c21c3e3-8ee4-40e5-add1-eb26d225fd8d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e40264c3ee7e48a545c88d7d48891126117ecc8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="memcmp-wmemcmp"></a>memcmp, wmemcmp

İki arabelleğini karakter karşılaştırır.

## <a name="syntax"></a>Sözdizimi

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
İlk arabelleği.

*buffer2*<br/>
İkinci bir arabellek.

*Sayısı*<br/>
Karşılaştırılacak karakter sayısı. (İçin bayt karşılaştırır **memcmp**, geniş karakter için **wmemcmp**).

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri arabellek arasındaki ilişkiyi gösterir.

|Dönüş değeri|İlk ilişkisini *sayısı* buf1 ve buf2 karakterleri|
|------------------|---------------------------------------------------------------|
|< 0|*buffer1* değerinden *buffer2*|
|0|*buffer1* aynı *buffer2*|
|> 0|*buffer1* büyük *buffer2*|

## <a name="remarks"></a>Açıklamalar

İlk karşılaştırır *sayısı* karakterlerinden *buffer1* ve *buffer2* ve ilişkilerini gösteren bir değer döndürür. Sıfır olmayan oturum değeri arabellek değerlerinin ilk farklı çifti arasındaki farkı işaretidir döndür. Değerleri olarak yorumlanır **imzasız** **char** için **memcmp**ve **wchar_t** için **wmemcmp**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memcmp**|\<Memory.h > veya \<string.h >|
|**wmemcmp**|\<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplığı](../../c-runtime-library/crt-library-features.md).

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

[Ara Bellek Düzenlemesi](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
