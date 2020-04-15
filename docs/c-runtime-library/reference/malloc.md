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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: afe9264351110bc062d6168ef803fa6fb796538a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341569"
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
Tahsis etmek için bayt.

## <a name="return-value"></a>Dönüş Değeri

**malloc** ayrılan alana bir boşluk işaretçisi döndürür veya boş bellek varsa **NULL.** Bir işaretçiyi **boşluk**dışında bir türe döndürmek için, iade değerinde bir tür döküm kullanın. İade değerine işaret edilen depolama alanının, temel hizalamadan daha az veya eşit bir hizalama gereksinimi olan herhangi bir nesne türünün depolanması için uygun şekilde hizalanması garanti edilir. (Visual C++'da temel hizalama, **çift**veya 8 bayt için gereken hizalamadır. 64 bit platformları hedefleyen kodda, 16 bayt.) Daha büyük bir hizalama gereksinimi olan nesneler için depolama alanı ayırmak için [_aligned_malloc](aligned-malloc.md) kullanın (örneğin, SSE türleri [__m128](../../cpp/m128.md) ve **__m256**, ve `__declspec(align( n ))` **n** 8'den büyük olduğu durumlarda beyan edilen türleri. *Boyut* 0 ise, **malloc** yığında sıfır uzunlukta bir öğe ayırır ve bu öğeye geçerli bir işaretçi döndürür. İstenen bellek miktarı küçük olsa bile, **malloc'tan**dönüşü her zaman kontrol edin.

## <a name="remarks"></a>Açıklamalar

**Malloc** işlevi en az *boyutta* bayt bir bellek bloğu ayırır. Hizalama ve bakım bilgileri için gerekli olan alan nedeniyle blok *boyut* baytlarından daha büyük olabilir.

**malloc,** bellek ayırmabaşarısız olursa veya istenen bellek miktarı **_HEAP_MAXREQ**aşarsa **ENOMEM'e** **errno** ayarlar. Bu ve diğer hata kodları hakkında bilgi için [_sys_nerr _sys_errlist _doserrno bkz.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

Başlangıç **kodu, _environ,** *envp*ve *argv* değişkenleri için depolama ayırmak için **malloc** kullanır. Aşağıdaki fonksiyonlar ve onların geniş karakterli meslektaşları da **malloc**diyoruz.

|||||
|-|-|-|-|
|[calloc](calloc.md)|[fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](getw.md)|[setvbuf](setvbuf.md)|
|[_exec fonksiyonları](../../c-runtime-library/exec-wexec-functions.md)|[Fseek](fseek-fseeki64.md)|[_popen](popen-wpopen.md)|[_spawn fonksiyonları](../../c-runtime-library/spawn-wspawn-functions.md)|
|[fgetc](fgetc-fgetwc.md)|[fsetpos](fsetpos.md)|[Printf](printf-printf-l-wprintf-wprintf-l.md)|[_strdup](strdup-wcsdup-mbsdup.md)|
|[_fgetchar](fgetc-fgetwc.md)|[_fullpath](fullpath-wfullpath.md)|[putc](putc-putwc.md)|[sistem](system-wsystem.md)|
|[fgets](fgets-fgetws.md)|[fwrite](fwrite.md)|[Putchar](putc-putwc.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[Fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](getc-getwc.md)|[_putenv](putenv-wputenv.md)|[Ungetc](ungetc-ungetwc.md)|
|[Fputc](fputc-fputwc.md)|[Getchar](getc-getwc.md)|[Koyar](puts-putws.md)|[vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_fputchar](fputc-fputwc.md)|[_getcwd](getcwd-wgetcwd.md)|[_putw](putw.md)|[vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)|
|[fputs](fputs-fputws.md)|[_getdcwd](getcwd-wgetcwd.md)|[Scanf](scanf-scanf-l-wscanf-wscanf-l.md)||
|[fread](fread.md)|[gets](../../c-runtime-library/gets-getws.md)|[_searchenv](searchenv-wsearchenv.md)||

C++ [_set_new_mode](set-new-mode.md) işlevi **malloc**için yeni işleyici modunu ayarlar. Yeni işleyici modu, hata, **malloc** [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamı aramak olup olmadığını gösterir. Varsayılan olarak, **malloc** bellek tahsis başarısız yeni işleyici yordamı aramaz. Bu varsayılan davranışı geçersiz kılabilirsiniz, böylece **malloc** bellek ayırmayı başaramayınca, **malloc** **yeni** işleyici yordamını yeni işlecinin aynı nedenle başarısız olduğu gibi çağırır. Varsayılanı geçersiz kılmak `_set_new_mode(1)` için programınızın erken denebilir veya NEWMODE ile bağlantı kurun. OBJ (bkz. [Bağlantı Seçenekleri](../../c-runtime-library/link-options.md)).

Uygulama C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, **malloc** [_malloc_dbg.](malloc-dbg.md) Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için [CRT Hata Ayıklama Yığın Ayrıntıları'na](/visualstudio/debugger/crt-debug-heap-details)bakın.

**malloc** `__declspec(noalias)` işaretlenir `__declspec(restrict)`ve; bu, işlevin genel değişkenleri değiştirmeme garantisi olduğu ve döndürülen işaretçinin diğer adı olmadığı anlamına gelir. Daha fazla bilgi için [noalias'a](../../cpp/noalias.md) bakın ve [kısıtlayın.](../../cpp/restrict.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**malloc**|\<stdlib.h> \<ve malloc.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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
[Ücret -siz](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
