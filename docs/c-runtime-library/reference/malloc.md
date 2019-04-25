---
title: malloc
ms.date: 11/04/2016
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
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
ms.openlocfilehash: e6a007fb6f089ebf1c9f5fc9ce59cbcbf0b13888
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157184"
---
# <a name="malloc"></a>malloc

Bellek bloklarını ayırır.

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

**malloc** ayrılan alana void bir işaretçi döndürür veya **NULL** kullanılabilir bellek yetersiz ise. Bir işaretçiyi dışında bir türe döndürmek için **void**, bir tür ataması dönüş değerini kullanın. Dönüş değeri tarafından işaret edilen depolama alanı hizalama gereksinimleri veya bu değere eşit olan temel hizalamadan için olan nesnenin herhangi bir türde depolama için uygun şekilde hizalanması garanti edilir. (Visual C++'da temel hizalama için gerekli olan hizalamadır bir **çift**, veya 8 bayt. 64-bit platformları hedefleyen kodda, 16 bayttır.) Kullanım [_aligned_malloc](aligned-malloc.md) daha büyük bir hizalama gereksinimi olan nesneleri için ayrılacak — örneğin SSE türleri [__m128](../../cpp/m128.md) ve **__m256**ve türleri kullanılarak bildirilen `__declspec(align( n ))` burada **n** 8'den büyüktür. Varsa *boyutu* 0 ' dır **malloc** bir sıfır uzunluklu öğeyi yığınına ayırır ve bu öğeye geçerli bir işaretçi döndürür. Öğesinden dönüşü her zaman denetleyin **malloc**, istenen bellek miktarı azsa.

## <a name="remarks"></a>Açıklamalar

**Malloc** işlevi bir bellek bloğunu en az ayırır *boyutu* bayt. Blok büyük *boyutu* bayt hizalama ve Bakım bilgileri için gerekli alanı.

**malloc** ayarlar **errno** için **ENOMEM** bir bellek ayırma başarısız olursa veya bellek miktarını aşıyor istenirse **_HEAP_MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Başlangıç kodu kullanan **malloc** için ayrılacak **_environ**, *envp*, ve *argv* değişkenleri. Aşağıdaki işlevler ve geniş karakter karşılıkları çağırıp **malloc**.

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

C++ [_Set_new_mode](set-new-mode.md) işlevi için yeni işleyici modunu ayarlar **malloc**. Yeni işleyici modunu gösterir mi, hata durumunda, **malloc** tarafından belirlenen yeni işleyici rutinini çağırmaktır [_set_new_handler](set-new-handler.md). Varsayılan olarak, **malloc** bellek dağıtma hatasında yeni işleyici rutinini çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, **malloc** bellek ayırmak başarısız **malloc** aynı yeni işleyici rutinini çağırır biçimi **yeni** işleci yok aynı nedenden dolayı başarısız olduğunda. Varsayılan geçersiz kılmak için çağrı `_set_new_mode(1)` program veya NEWMODE bağlantıyla erken. OBJ (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Uygulamayı hata ayıklama sürümü C çalışma zamanı kitaplıkları ile ilişkilendirildiğinde **malloc** çözümler [_malloc_dbg](malloc-dbg.md). Yığının hata ayıklama işlemi sırasında nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

**malloc** işaretlenmiş `__declspec(noalias)` ve `__declspec(restrict)`; yani işlevin genel değişkenleri garanti edilir ve döndürülen işaretçiye diğer adı değil. Daha fazla bilgi için [noalias](../../cpp/noalias.md) ve [kısıtlama](../../cpp/restrict.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**malloc**|\<stdlib.h > ve \<malloc.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
