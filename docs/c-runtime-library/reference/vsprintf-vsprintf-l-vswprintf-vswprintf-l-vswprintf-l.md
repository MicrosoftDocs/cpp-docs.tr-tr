---
title: vsprintf, _vsprintf_l, vswprintf, _vswprintf_l, __vswprintf_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _vswprintf_l
- _vsprintf_l
- vsprintf
- vswprintf
- __vswprintf_l
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
- vstprintf
- vswprintf
- _vstprintf
- vsprintf
- __vswprintf_l
- _vsprintf_l
- _vswprintf_l
- vswprintf_l
dev_langs:
- C++
helpviewer_keywords:
- __vswprintf_l function
- _vstprintf_l function
- formatted text
- vstprintf_l function
- _vswprintf_l function
- vsprintf_l function
- buffers, avoiding overruns
- buffer overruns
- vswprintf_l function
- buffers, buffer overruns
- vstprintf function
- _vsprintf_l function
- vswprintf function
- vsprintf function
- _vstprintf function
ms.assetid: b8ef1c0d-58f9-4a18-841a-f1a989e1c29b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c9e236d7b880b2bcc5a66f8f2494990c6b420193
ms.sourcegitcommit: c770a343def04ae77522708387c3f7c470e49969
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="vsprintf-vsprintfl-vswprintf-vswprintfl-vswprintfl"></a>vsprintf, _vsprintf_l, vswprintf, _vswprintf_l, __vswprintf_l
Bir işaretçi bağımsız değişken listesini kullanarak biçimlendirilmiş çıktı yazma. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int vsprintf(  
   char *buffer,  
   const char *format,  
   va_list argptr   
);   
int _vsprintf_l(  
   char *buffer,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);   
int vswprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vswprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
int __vswprintf_l(  
   wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int vsprintf(  
   char (&buffer)[size],  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsprintf_l(  
   char (&buffer)[size],  
   const char *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int vswprintf(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vswprintf_l(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 `buffer`  
 Çıktı için depolama konumu.  
  
 `count`  
 Buna depolamak için karakter sayısının üst sınırı `UNICODE` bu işlev sürümü.  
  
 `format`  
 Biçim belirtimi.  
  
 `argptr`  
 İşaretçi bağımsız değişken listesi.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `vsprintf` ve `vswprintf` çıkış hata oluşursa sonlandırma null karakter veya negatif bir değer içermeyen yazılan karakterlerin sayısını döndürür. Varsa `buffer` veya `format` null işaretçi açıklandığı gibi bu işlevleri geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve `errno` için `EINVAL`.  
  
 Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri bir bağımsız değişken listesi için bir işaretçi alır ve ardından biçimlendirir ve gösterdiği bellek için belirtilen veri Yazar `buffer`.  
  
 Bu işlevleri sürümlerini `_l` soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.  
  
> [!IMPORTANT]
>  Kullanarak `vsprintf`, var. karakter sayısını sınırlamak için hiçbir şekilde yazılır, bu işlevi kullanarak kod arabellek taşmaları açıktır anlamına gelir. Kullanım [_vsnprintf](../../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) bunun yerine, veya arama [_vscprintf](../../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md) ne kadar büyük bir arabellek gerekli belirlemek için. Ayrıca, emin `format` kullanıcı tanımlı bir dize değil. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 `vswprintf` ISO C ikinci parametre gerektiren standart, uyumlu `count`, türü `size_t`. Eski standart olmayan davranış zorlamak için tanımlamak `_CRT_NON_CONFORMING_SWPRINTFS.` eski davranışı sonraki bir sürümde olabilir, bu kod yeni uyumluluğunu davranışı kullanmak için değiştirilmesi gereken biçimde değil.  
  
 C++'da, bu işlevlerin daha yeni, güvenli ortaklarınıza çağırma şablon aşırı yüklemeleri bu işlevler vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vstprintf`|`vsprintf`|`vsprintf`|`vswprintf`|  
|`_vstprintf_l`|`_vsprintf_l`|`_vsprintf_l`|`_vswprintf_l`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|----------------------|  
|`vsprintf`, `_vsprintf_l`|\<stdio.h > ve \<stdarg.h >|\<varargs.h>*|  
|`vswprintf`, `_vswprintf_l`|\<stdio.h > veya \<wchar.h >, ve \<stdarg.h >|\<varargs.h>*|  
  
 \* UNIX V uyumluluk için gereklidir.  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_vsprintf.c  
// compile with: /W3  
// This program uses vsprintf to write to a buffer.  
// The size of the buffer is determined by _vscprintf.  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <stdarg.h>  
  
void test( char * format, ... )  
{  
    va_list args;  
    int     len;  
    char    *buffer;  
  
    // retrieve the variable arguments  
    va_start( args, format );  
  
    len = _vscprintf( format, args ) // _vscprintf doesn't count  
                                + 1; // terminating '\0'  
  
    buffer = (char*)malloc( len * sizeof(char) );  
  
    vsprintf( buffer, format, args ); // C4996  
    // Note: vsprintf is deprecated; consider using vsprintf_s instead  
    puts( buffer );  
  
    free( buffer ); 
    va_end( args ); 
}  
  
int main( void )  
{  
   test( "%d %c %d", 123, '<', 456 );  
   test( "%s", "This is a string" );  
}  
```  
  
```Output  
123 < 456  
This is a string  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [vprintf işlevleri](../../c-runtime-library/vprintf-functions.md)   
 [Biçim belirtim Sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [Printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)
