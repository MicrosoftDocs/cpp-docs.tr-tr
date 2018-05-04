---
title: realloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6452d14e0a8630c68d5e179fd94d531db1b667ab
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
Önceden ayrılmış bellek bloğu işaretçi.

*Boyutu*<br/>
Yeni boyutunu bayt cinsinden.

## <a name="return-value"></a>Dönüş Değeri

**realloc** döndüren bir **void** bırakılan (ve muhtemelen taşınan) bellek bloğu işaretçi.

Blok verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, özgün blok değiştirilmeden olduğundan, ve **NULL** döndürülür.

Varsa *boyutu* sıfır gösterdiği blok olduğundan *memblock* serbest bırakılır; dönüş değeri **NULL**, ve *memblock* gösteren sol bir boşaltılmış bloğu.

Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun hizalanacak garanti bir depolama alanı işaret eder. Bir işaretçi bir türe dışında almak için **void**, dönüş değerini cast türünü kullanın.

## <a name="remarks"></a>Açıklamalar

**Realloc** işlev ayrılmış bellek bloğu boyutu değiştirir. *Memblock* bağımsız değişkeni bellek bloğu başlangıcına işaret eder. Varsa *memblock* olan **NULL**, **realloc** aynı şekilde davranır **malloc** ve yeni bir blok ayırır *boyutu*bayt sayısı. Varsa *memblock* değil **NULL**, önceki bir çağrı tarafından döndürülen bir işaretçi olmalıdır **calloc**, **malloc**, veya **realloc** .

*Boyutu* bağımsız değişkeni yeni blok boyutunu bayt cinsinden verir. Yeni blok farklı bir konumda olabilir ancak blok içeriğini kadar kısa yeni ve eski boyutlarının değiştirilmemiştir. Yeni bir bellek konumda yeni blok olabileceğinden, işaretçi tarafından döndürülen **realloc** geçtiğini işaretçi olması garanti edilmemiştir *memblock* bağımsız değişkeni. **realloc** mu sıfır değil yeni ayrılan bellek arabelleği büyüme durumunda.

**realloc** ayarlar **errno** için **ENOMEM** bellek ayırma başarısız olursa veya bellek miktarını aşıyor istediyseniz **_HEAP_MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**realloc** çağrıları **malloc** C++ kullanmak için [_set_new_mode](set-new-mode.md) yeni işleyici modu ayarlamak için işlevi. Yeni işleyici modunu gösterir, hatasında kullanılıp **malloc** belirlediği yeni işleyici yordamı çağırmaktır [_set_new_handler](set-new-handler.md). Varsayılan olarak, **malloc** yeni işleyici yordamı bellek ayırma hatası çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, **realloc** bellek ayırmak başarısız **malloc** yeni işleyici yordamını aynı çağırıyor biçimi **yeni** işleci mu aynı nedenden dolayı başarısız olduğunda. Varsayılan değer geçersiz kılmak için arama

```C
_set_new_mode(1);
```

olanları erkenden program veya NEWMODE bağlantısıyla. OBJ (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında **realloc** çözümler [_realloc_dbg](realloc-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

**realloc** işaretlenmiş `__declspec(noalias)` ve `__declspec(restrict)`, işlev genel değişkenler değiştirmemeniz garanti ve işaretçi döndürdü diğer adı değil anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md) ve [kısıtlamak](../../cpp/restrict.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**realloc**|\<stdlib.h > ve \<malloc.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
