---
title: malloc
ms.date: 4/2/2020
api_name:
- malloc
- _o_malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- malloc
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
ms.openlocfilehash: a093dbdbc4849b1c2f3d86e85a5e2b25a7b988e2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836666"
---
# <a name="malloc"></a>malloc

Bellek bloklarını ayırır.

## <a name="syntax"></a>Söz dizimi

```C
void *malloc(
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Ayrılacak bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**malloc** , ayrılan alana bir void işaretçisi döndürür veya yeterli bellek yoksa **null** değer döndürür. Dışında bir türe işaretçi döndürmek için **`void`** , dönüş değerinde bir tür dönüştürme kullanın. Dönüş değeri tarafından işaret edilen depolama alanının, temel hizalamadan daha az veya buna eşit bir hizalama gereksinimine sahip herhangi bir tür nesnenin depolanması için uygun şekilde hizalı olduğu garanti edilir. (Visual C++, temel hizalama **`double`** , veya 8 bayt için gerekli olan hizalamadır. 64 bitlik platformları hedefleyen kodda 16 bayttır.) Daha büyük bir hizalama gereksinimine sahip nesneler için depolama alanı ayırmak üzere [_aligned_malloc](aligned-malloc.md) kullanın — ÖRNEĞIN, SSE türleri [__m128](../../cpp/m128.md) ve **`__m256`** , ve `__declspec(align( n ))` **n** 'nin 8 ' den büyük olduğu ile belirtilen türleri. *Boyut* 0 ise, **malloc** yığında sıfır uzunluklu bir öğe ayırır ve bu öğeye geçerli bir işaretçi döndürür. İstenen bellek miktarı küçük olsa bile, her zaman **malloc**'den dönüşü denetleyin.

## <a name="remarks"></a>Açıklamalar

**Malloc** işlevi en az bayt *boyutundaki* bir bellek bloğunu ayırır. Bir blok, hizalama ve bakım bilgileri için gereken alan nedeniyle *Boyut* baytından daha büyük olabilir.

bellek ayırma **başarısız olursa veya** istenen bellek miktarı **_HEAP_MAXREQ**aşarsa, **malloc** olarak **errno** değeri. Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Başlangıç kodu **_environ**, *envp*ve *argv* değişkenleri için depolama alanı ayırmak üzere **malloc** kullanır. Aşağıdaki işlevler ve geniş karakter karşılıkları de **malloc**öğesini çağırır.

:::row:::
   :::column span="":::
      [calloc](calloc.md)\
      [_exec işlevleri](../../c-runtime-library/exec-wexec-functions.md)\
      [fgetc](fgetc-fgetwc.md)\
      [_fgetchar](fgetc-fgetwc.md)\
      [fal](fgets-fgetws.md)\
      [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)\
      [fputc](fputc-fputwc.md)\
      [_fputchar](fputc-fputwc.md)\
      [fkoyar](fputs-fputws.md)\
      [fread](fread.md)
   :::column-end:::
   :::column span="":::
      [fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)\
      [fseek](fseek-fseeki64.md)\
      [fsetpos](fsetpos.md)\
      [_fullpath](fullpath-wfullpath.md)\
      [fwrite](fwrite.md)\
      [getc](getc-getwc.md)\
      [GetChar](getc-getwc.md)\
      [_getcwd](getcwd-wgetcwd.md)\
      [_getdcwd](getcwd-wgetcwd.md)\
      [iyorsa](../../c-runtime-library/gets-getws.md)
   :::column-end:::
   :::column span="":::
      [_getw](getw.md)\
      [_popen](popen-wpopen.md)\
      [printf](printf-printf-l-wprintf-wprintf-l.md)\
      [putc](putc-putwc.md)\
      [putchar](putc-putwc.md)\
      [_putenv](putenv-wputenv.md)\
      [kontrolünü](puts-putws.md)\
      [_putw](putw.md)\
      [scanf](scanf-scanf-l-wscanf-wscanf-l.md)
   :::column-end:::
   :::column span="":::
      [_searchenv](searchenv-wsearchenv.md)\
      [setvbuf](setvbuf.md)\
      [_spawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)\
      [_strdup](strdup-wcsdup-mbsdup.md)\
      [sistemin](system-wsystem.md)\
      [_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)\
      [ungetc](ungetc-ungetwc.md)\
      [vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)\
      [vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)
   :::column-end:::
:::row-end:::

C++ [_set_new_mode](set-new-mode.md) işlevi, **malloc**için yeni işleyici modunu ayarlar. Yeni işleyici modu, hata durumunda **malloc** 'ın [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamını çağırıp çağırmayacağını gösterir. Varsayılan olarak, **malloc** bellek ayırma hatası üzerine yeni işleyici yordamını çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz, böylece **malloc** bellek ayıramadığında, **malloc** yeni işleyici yordamını **`new`** aynı nedenden dolayı başarısız olduğunda işlecin yaptığı şekilde çağırır. Varsayılan değeri geçersiz kılmak için, `_set_new_mode(1)` programınızda erken çağırın veya NEWMODE ile bağlayın. OBJ (bkz. [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Uygulama, C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, **malloc** [_malloc_dbg](malloc-dbg.md)olarak çözümlenir. Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

**malloc** işaretlenir `__declspec(noalias)` ve `__declspec(restrict)` ; Bu, işlevin genel değişkenleri değiştirmeyeceği ve döndürülen işaretçinin diğer ad olmadığından garanti olduğu anlamına gelir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md) ve [Restrict](../../cpp/restrict.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**malloc**|\<stdlib.h> ve \<malloc.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[Süz](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
