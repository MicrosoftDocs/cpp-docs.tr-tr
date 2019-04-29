---
title: realloc
ms.date: 11/04/2016
apiname:
- realloc
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
- _brealloc
- _nrealloc
- realloc
- _frealloc
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
ms.openlocfilehash: 0d61746365a8ded8d68072b1f398a18ba6ce7605
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357674"
---
# <a name="realloc"></a>realloc

Bellek bloklarını yeniden ayırma.

## <a name="syntax"></a>Sözdizimi

```C
void *realloc(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Daha önce ayrılmış bellek bloğuna işaretçi.

*Boyutu*<br/>
Yeni boyutu bayt cinsinden.

## <a name="return-value"></a>Dönüş Değeri

**realloc** döndürür bir **void** yeniden (ve muhtemelen taşınan) bellek bloğuna işaretçi.

Blok için verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, özgün blok sol değiştirilmez, ve **NULL** döndürülür.

Varsa *boyutu* sıfır sonra tarafından işaret edilen blok *memblock* serbest bırakılır; dönüş değeri **NULL**, ve *memblock* işaret sola bir Serbest bırakılan bloğu.

Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun şekilde hizalanması garanti bir depolama alanına işaret eder. Dışında bir türe işaretçi almaya **void**, bir tür ataması dönüş değerini kullanın.

## <a name="remarks"></a>Açıklamalar

**Realloc** işlev ayrılan bellek blok boyutu değiştirir. *Memblock* bağımsız değişken bellek bloğu başlangıcına işaret eder. Varsa *memblock* olduğu **NULL**, **realloc** aynı şekilde davranır **malloc** ve yeni bir bloğu ayırır *boyutu*bayt. Varsa *memblock* değil **NULL**, önceki bir çağrı tarafından döndürülen bir işaretçi olmalıdır **calloc**, **malloc**, veya **realloc** .

*Boyutu* bağımsız değişkeni yeni blok boyutunu bayt cinsinden verir. Yeni bir blok farklı bir konumdan olsa da içeriği bloğunun kadar kısa yeni ve eski boyutlarının değiştirilmez. Yeni bir blok içinde yeni bir bellek konumuna olabileceğinden, işaretçi tarafından döndürülen **realloc** geçtiğini işaretçisi olması garanti edilmez *memblock* bağımsız değişken. **realloc** mu sıfır değil yeni ayrılan bellek arabelleği büyüme söz konusu olduğunda.

**realloc** ayarlar **errno** için **ENOMEM** bellek ayırma başarısız olursa veya bellek miktarını aşıyor istenirse **_HEAP_MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**realloc** çağrıları **malloc** kullanmak için C++ [_set_new_mode](set-new-mode.md) yeni işleyici modu ayarlamak için işlevi. Yeni işleyici modunu gösterir mi, hata durumunda, **malloc** tarafından belirlenen yeni işleyici rutinini çağırmaktır [_set_new_handler](set-new-handler.md). Varsayılan olarak, **malloc** bellek dağıtma hatasında yeni işleyici rutinini çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, **realloc** bellek ayırmak başarısız **malloc** aynı yeni işleyici rutinini çağırır biçimi **yeni** işleci yok aynı nedenden dolayı başarısız olduğunda. Varsayılan geçersiz kılmak için çağırın

```C
_set_new_mode(1);
```

olanları erkenden program veya NEWMODE ile bağlantı. OBJ (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Uygulamayı hata ayıklama sürümü C çalışma zamanı kitaplıkları ile ilişkilendirildiğinde **realloc** çözümler [_realloc_dbg](realloc-dbg.md). Yığının hata ayıklama işlemi sırasında nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığın](/visualstudio/debugger/crt-debug-heap-details).

**realloc** işaretlenmiş `__declspec(noalias)` ve `__declspec(restrict)`, işlevin genel değişkenleri garanti edilir ve döndürülen işaretçiye diğer adı değil. Daha fazla bilgi için [noalias](../../cpp/noalias.md) ve [kısıtlama](../../cpp/restrict.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**realloc**|\<stdlib.h > ve \<malloc.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_realloc.c
// This program allocates a block of memory for
// buffer and then uses _msize to display the size of that
// block. Next, it uses realloc to expand the amount of
// memory used by buffer and then calls _msize again to
// display the new amount of memory allocated to buffer.

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   long *buffer, *oldbuffer;
   size_t size;

   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )
      exit( 1 );

   size = _msize( buffer );
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );

   // Reallocate and show new size:
   oldbuffer = buffer;     // save pointer in case realloc fails
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))
        ==  NULL )
   {
      free( oldbuffer );  // free original block
      exit( 1 );
   }
   size = _msize( buffer );
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",
            size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after malloc of 1000 longs: 4000
Size of block after realloc of 1000 more longs: 8000
```

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
