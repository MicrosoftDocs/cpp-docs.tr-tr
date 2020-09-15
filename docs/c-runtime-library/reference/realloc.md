---
title: realloc
description: Realloc için API başvurusu (); bellek bloklarını yeniden konumlandırır.
ms.date: 9/11/2020
api_name:
- realloc
- _o_realloc
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
ms.openlocfilehash: c68909b2f5d73959465d63af522ceeb00c8ce23e
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90075822"
---
# <a name="realloc"></a>realloc

Bellek bloklarını yeniden tahsis edin.

## <a name="syntax"></a>Söz dizimi

```C
void *realloc(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*`memblock`*\
Önceden ayrılmış bellek bloğuna yönelik işaretçi.

*`size`*\
Bayt cinsinden yeni boyut.

## <a name="return-value"></a>Dönüş Değeri

**`realloc`****`void`** yeniden ayrılan (ve muhtemelen taşınan) bellek bloğuna yönelik bir işaretçi döndürür.

Bloğu verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, özgün blok değiştirilmeden bırakılır ve **`NULL`** döndürülür.

*`size`* Sıfırsa, tarafından işaret edilen blok *`memblock`* serbest bırakılır; dönüş değeri olur **`NULL`** ve *`memblock`* serbest bırakılan bloğa işaret eder.

Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı bir depolama alanına işaret eder. Dışında bir türe işaretçi almak için **`void`** , dönüş değerinde bir tür dönüştürme kullanın.

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> **`realloc`** Yeni davranış Windows işletim sistemiyle uyumlu olmadığından, C17 davranışını uygulamak için güncelleştirilmedi.

**`realloc`** İşlevi, ayrılmış bir bellek bloğunun boyutunu değiştirir. *`memblock`* Bağımsız değişkeni bellek bloğunun başlangıcına işaret eder. *`memblock`* İse **`NULL`** , **`realloc`** ile aynı şekilde davranır **`malloc`** ve yeni bir bayt bloğunu ayırır *`size`* . Değilse,, *`memblock`* **`NULL`** veya için önceki bir çağrı tarafından döndürülen bir işaretçi olmalıdır **`calloc`** **`malloc`** **`realloc`** .

*`size`* Bağımsız değişkeni, blok için bayt cinsinden yeni boyutunu verir. Yeni blok farklı bir konumda olabilse de bloğunun içeriği yeni ve eski boyutların daha kısa bir yere kadar değişmez. Yeni blok yeni bir bellek konumunda olabileceğinden, tarafından döndürülen işaretçinin **`realloc`** bağımsız değişkenden geçen işaretçi olması garanti edilmez *`memblock`* . **`realloc`** arabellek büyümesi durumunda, yeni ayrılan belleği sıfırlamaz.

**`realloc`****`errno`** **`ENOMEM`** bellek ayırma başarısız olursa veya istenen bellek miktarı aşarsa olarak ayarlanır **`_HEAP_MAXREQ`** . Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**`realloc`****`malloc`** yeni işleyici modunu ayarlamak Için C++ [_set_new_mode](set-new-mode.md) işlevini kullanmak üzere çağrılar. Yeni işleyici modu, hata durumunda, **`malloc`** [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamını çağırıp çağırmayacağını gösterir. Varsayılan olarak, **`malloc`** bellek ayırma hatası üzerine yeni işleyici yordamını çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz, böylece **`realloc`** bellek ayıramadığında, **`malloc`** yeni işleyici yordamını **`new`** aynı nedenden dolayı başarısız olduğunda işlecin yaptığı şekilde çağırır. Varsayılanı geçersiz kılmak için şunu çağırın

```C
_set_new_mode(1);
```

daha erken bir programda veya NEWMODE ile bağlantılandırın. OBJ (bkz. [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Uygulama, C çalışma zamanı kitaplıklarının bir hata ayıklama sürümü ile bağlantılı olduğunda **`realloc`** [_realloc_dbg](realloc-dbg.md)olarak çözümlenir. Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

**`realloc`**`__declspec(noalias)` `__declspec(restrict)` , ve işlevinin genel değişkenleri değiştirmeyeceği garantisi olduğunu ve döndürülen işaretçinin diğer ad olmadığından emin olduğunu belirtir ve olarak işaretlenir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md) ve [Restrict](../../cpp/restrict.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**`realloc`**|\<stdlib.h> ve \<malloc.h>|

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

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)\
[calloc](calloc.md)\
[Süz](free.md)\
[malloc](malloc.md)
