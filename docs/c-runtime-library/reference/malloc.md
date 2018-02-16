---
title: malloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- malloc
dev_langs:
- C++
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 65b70ba6be4837a36d5987e60b1d7229134ceb99
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="malloc"></a>malloc
Bellek blokları ayırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *malloc(  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `size`  
 Ayrılacak bayt sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `malloc` ayrılan alanı için geçersiz bir işaretçi döndürür veya `NULL` kullanılabilir bellek yetersiz ise. Bir işaretçi bir türe dışında dönmek için `void`, dönüş değerini cast türünü kullanın. Dönüş değeri tarafından işaret depolama alanı nesnesinin bir hizalama koşuluna daha az veya bu değere eşit, temel hizalama sahip herhangi bir türde depolama için uygun hizalanacak garanti edilmez. (Visual C++'da, temel hizalama için gerekli hizalama olan bir `double`, veya 8 bayt. 64 bit platformları hedefler kodda, 16 bayt'tır.) Kullanım [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) daha büyük bir hizalama gereksinim nesneleri için depolama alanı ayırmak için — örneğin, SSE türleri [__m128](../../cpp/m128.md) ve `__m256`ve kullanarakbelirtilentürlerine`__declspec(align( n ))`nerede `n` 8 büyüktür. Varsa `size` 0 ' dır `malloc` öbek sıfır uzunluklu öğesinde ayırır ve geçerli bir işaretçi için bu öğeyi döndürür. Her zaman dönüş kontrol `malloc`, istenen bellek miktarını küçük olsa bile.  
  
## <a name="remarks"></a>Açıklamalar  
 `malloc` İşlevi ayırır bir bellek bloğu en az `size` bayt sayısı. Blok büyük `size` hizalama ve Bakım bilgileri için gerekli alanı nedeniyle bayt.  
  
 `malloc` Ayarlar `errno` için `ENOMEM` bir bellek ayırma başarısız olursa veya bellek miktarını aşıyor istediyseniz `_HEAP_MAXREQ`. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Başlangıç kodu kullanan `malloc` için depolama alanı ayırmaya `_environ`, `envp`, ve `argv` değişkenleri. Aşağıdaki işlevleri ve joker karakter dekiler çağırıp `malloc`.  
  
|||||  
|-|-|-|-|  
|[calloc](../../c-runtime-library/reference/calloc.md)|[fscanf](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](../../c-runtime-library/reference/getw.md)|[setvbuf](../../c-runtime-library/reference/setvbuf.md)|  
|[_exec işlevleri](../../c-runtime-library/exec-wexec-functions.md)|[fseek](../../c-runtime-library/reference/fseek-fseeki64.md)|[_popen](../../c-runtime-library/reference/popen-wpopen.md)|[_spawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)|  
|[fgetc](../../c-runtime-library/reference/fgetc-fgetwc.md)|[fsetpos](../../c-runtime-library/reference/fsetpos.md)|[printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[_strdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)|  
|[_fgetchar](../../c-runtime-library/reference/fgetc-fgetwc.md)|[_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[putc](../../c-runtime-library/reference/putc-putwc.md)|[Sistem](../../c-runtime-library/reference/system-wsystem.md)|  
|[fgets](../../c-runtime-library/reference/fgets-fgetws.md)|[fwrite](../../c-runtime-library/reference/fwrite.md)|[putchar](../../c-runtime-library/reference/putc-putwc.md)|[_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](../../c-runtime-library/reference/getc-getwc.md)|[_putenv](../../c-runtime-library/reference/putenv-wputenv.md)|[ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md)|  
|[fputc](../../c-runtime-library/reference/fputc-fputwc.md)|[getchar](../../c-runtime-library/reference/getc-getwc.md)|[yerleştirir](../../c-runtime-library/reference/puts-putws.md)|[vfprintf](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[_fputchar](../../c-runtime-library/reference/fputc-fputwc.md)|[_getcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[_putw](../../c-runtime-library/reference/putw.md)|[vprintf](../../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|  
|[fputs](../../c-runtime-library/reference/fputs-fputws.md)|[_getdcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)||  
|[fread](../../c-runtime-library/reference/fread.md)|[Alır](../../c-runtime-library/gets-getws.md)|[_searchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)||  
  
 C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) işlevi ayarlar için yeni işleyici modu `malloc`. Yeni işleyici modunu gösterir, hatasında kullanılıp `malloc` belirlediği yeni işleyici yordamı çağırmaktır [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). Varsayılan olarak, `malloc` yeni işleyici yordamı bellek ayırma hatası çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, `malloc` bellek ayırmak başarısız `malloc` yeni işleyici yordamını aynı çağırıyor biçimi `new` işleci mu aynı nedenden dolayı başarısız olduğunda. Varsayılan değer geçersiz kılmak için arama `_set_new_mode(1)` program veya NEWMODE bağlantısıyla erken. OBJ (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).  
  
 Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında `malloc` çözümler [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).  
  
 `malloc` işaretli `__declspec(noalias)` ve `__declspec(restrict)`; yani işlevi genel değişkenler değiştirmemeniz garanti ve işaretçi döndürdü diğer adı değil. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md) ve [kısıtlamak](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`malloc`|\<stdlib.h > ve \<malloc.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_malloc.c  
// This program allocates memory with  
// malloc, then frees the memory with free.  
  
#include <stdlib.h>   // For _MAX_PATH definition  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   char *string;  
  
   // Allocate space for a path name  
   string = malloc( _MAX_PATH );  
  
   // In a C++ file, explicitly cast malloc's return.  For example,   
   // string = (char *)malloc( _MAX_PATH );  
  
   if( string == NULL )  
      printf( "Insufficient memory available\n" );  
   else  
   {  
      printf( "Memory space allocated for path name\n" );  
      free( string );  
      printf( "Memory freed\n" );  
   }  
}  
```  
  
```Output  
Memory space allocated for path name  
Memory freed  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [Boş](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)
