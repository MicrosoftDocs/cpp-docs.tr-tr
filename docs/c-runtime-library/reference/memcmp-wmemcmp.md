---
title: memcmp, wmemcmp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- wmemcmp function
- memcmp function
ms.assetid: 0c21c3e3-8ee4-40e5-add1-eb26d225fd8d
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 05869e1497ab173bc0f847482225ff215f3690af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="memcmp-wmemcmp"></a>memcmp, wmemcmp
İki arabelleğini karakter karşılaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int memcmp(  
   const void *buf1,  
   const void *buf2,  
   size_t count  
);  
int wmemcmp(  
   const wchar_t * buf1,  
   const wchar_t * buf2,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `buf1`  
 İlk arabelleği.  
  
 `buf2`  
 İkinci bir arabellek.  
  
 `count`  
 Karşılaştırılacak karakter sayısı. (İçin bayt karşılaştırır `memcmp`, geniş karakter için `wmemcmp`).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri arabellek arasındaki ilişkiyi gösterir.  
  
|Dönüş değeri|İlk ilişkisini `count` buf1 ve buf2 karakterleri|  
|------------------|---------------------------------------------------------------|  
|< 0|`buf1`küçüktür`buf2`|  
|0|`buf1`aynı`buf2`|  
|> 0|`buf1`büyüktür`buf2`|  
  
## <a name="remarks"></a>Açıklamalar  
 İlk karşılaştırır `count` karakterlerinden `buf1` ve `buf2` ve ilişkilerini gösteren bir değer döndürür. Sıfır olmayan oturum değeri arabellek değerlerinin ilk farklı çifti arasındaki farkı işaretidir döndür. Değerleri olarak yorumlanır `unsigned char` için `memcmp`ve `wchar_t` için `wmemcmp`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`memcmp`|\<Memory.h > veya \<string.h >|  
|`wmemcmp`|\<wchar.h >|  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ara bellek düzenlemesi](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr'e, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)