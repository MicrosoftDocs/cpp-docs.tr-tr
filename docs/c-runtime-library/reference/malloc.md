---
title: malloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f600deb7bfa9b65ed9bdf784f2a16bd037729a51
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405529"
---
# <a name="malloc"></a>malloc

Bellek blokları ayırır.

## <a name="syntax"></a>Sözdizimi

```C
void *malloc(
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Ayrılacak bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**malloc** ayrılan alanı için geçersiz bir işaretçi döndürür veya **NULL** kullanılabilir bellek yetersiz ise. Bir işaretçi bir türe dışında dönmek için **void**, dönüş değerini cast türünü kullanın. Dönüş değeri tarafından işaret depolama alanı nesnesinin bir hizalama koşuluna daha az veya bu değere eşit, temel hizalama sahip herhangi bir türde depolama için uygun hizalanacak garanti edilmez. (Visual C++'da, temel hizalama için gerekli hizalama olan bir **çift**, veya 8 bayt. 64 bit platformları hedefler kodda, 16 bayt'tır.) Kullanım [_aligned_malloc](aligned-malloc.md) daha büyük bir hizalama gereksinim nesneleri için depolama alanı ayırmak için — örneğin, SSE türleri [__m128](../../cpp/m128.md) ve **__m256**ve türleri kullanarak bildirilen `__declspec(align( n ))` nerede **n** 8 büyüktür. Varsa *boyutu* 0 ' dır **malloc** öbek sıfır uzunluklu öğesinde ayırır ve geçerli bir işaretçi için bu öğeyi döndürür. Her zaman dönüş kontrol **malloc**, istenen bellek miktarını küçük olsa bile.

## <a name="remarks"></a>Açıklamalar

**Malloc** işlevi ayırır bir bellek bloğu en az *boyutu* bayt sayısı. Blok büyük *boyutu* hizalama ve Bakım bilgileri için gerekli alanı nedeniyle bayt.

**malloc** ayarlar **errno** için **ENOMEM** bir bellek ayırma başarısız olursa veya bellek miktarını aşıyor istediyseniz **_HEAP_MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Başlangıç kodu kullanan **malloc** için depolama alanı ayırmaya **_environ**, *envp*, ve *argv* değişkenleri. Aşağıdaki işlevleri ve joker karakter dekiler çağırıp **malloc**.

|||||
|-|-|-|-|
|[calloc](calloc.md)|[fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](getw.md)|[setvbuf](setvbuf.md)|
|[_exec işlevleri](../../c-runtime-library/exec-wexec-functions.md)|[fseek](fseek-fseeki64.md)|[_popen](popen-wpopen.md)|[_spawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)|
|[fgetc](fgetc-fgetwc.md)|[fsetpos](fsetpos.md)|[Printf](printf-printf-l-wprintf-wprintf-l.md)|[_strdup](strdup-wcsdup-mbsdup.md)|
|[_fgetchar](fgetc-fgetwc.md)|[_fullpath](fullpath-wfullpath.md)|[putc](putc-putwc.md)|[Sistem](system-wsystem.md)|
|[fgets](fgets-fgetws.md)|[fwrite](fwrite.md)|[putchar](putc-putwc.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](getc-getwc.md)|[_putenv](putenv-wputenv.md)|[ungetc](ungetc-ungetwc.md)|
|[fputc](fputc-fputwc.md)|[getchar](getc-getwc.md)|[yerleştirir](puts-putws.md)|[vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_fputchar](fputc-fputwc.md)|[_getcwd](getcwd-wgetcwd.md)|[_putw](putw.md)|[vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)|
|[fputs](fputs-fputws.md)|[_getdcwd](getcwd-wgetcwd.md)|[scanf](scanf-scanf-l-wscanf-wscanf-l.md)||
|[fread](fread.md)|[Alır](../../c-runtime-library/gets-getws.md)|[_searchenv](searchenv-wsearchenv.md)||

C++ [_set_new_mode](set-new-mode.md) işlevi ayarlar için yeni işleyici modu **malloc**. Yeni işleyici modunu gösterir, hatasında kullanılıp **malloc** belirlediği yeni işleyici yordamı çağırmaktır [_set_new_handler](set-new-handler.md). Varsayılan olarak, **malloc** yeni işleyici yordamı bellek ayırma hatası çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, **malloc** bellek ayırmak başarısız **malloc** yeni işleyici yordamını aynı çağırıyor biçimi **yeni** işleci mu aynı nedenden dolayı başarısız olduğunda. Varsayılan değer geçersiz kılmak için arama `_set_new_mode(1)` program veya NEWMODE bağlantısıyla erken. OBJ (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında **malloc** çözümler [_malloc_dbg](malloc-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

**malloc** işaretlenmiş `__declspec(noalias)` ve `__declspec(restrict)`; yani işlevi genel değişkenler değiştirmemeniz garanti ve işaretçi döndürdü diğer adı değil. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md) ve [kısıtlamak](../../cpp/restrict.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**malloc**|\<stdlib.h > ve \<malloc.h >|

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

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
