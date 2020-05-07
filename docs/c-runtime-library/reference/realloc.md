---
title: realloc
ms.date: 4/2/2020
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
ms.openlocfilehash: 15c818ee6f70d02fb9b63f12deef6b1bf3698322
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917937"
---
# <a name="realloc"></a>realloc

Bellek bloklarını yeniden tahsis edin.

## <a name="syntax"></a>Sözdizimi

```C
void *realloc(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Önceden ayrılmış bellek bloğuna yönelik işaretçi.

*boyutla*<br/>
Bayt cinsinden yeni boyut.

## <a name="return-value"></a>Dönüş Değeri

**realloc** , yeniden ayrılan (ve muhtemelen taşınan) bellek bloğuna **void** bir işaretçi döndürür.

Bloğu verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, özgün blok değiştirilmeden bırakılır ve **null** döndürülür.

*Boyut* sıfırsa, *memblock* tarafından işaret edilen blok serbest bırakılır; dönüş değeri **null**ve *memblock* serbest bırakılmış bir blok üzerine gelindiğinde bırakılır.

Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garantili bir depolama alanına işaret eder. **Void**dışında bir türe işaretçi almak için, dönüş değerinde bir tür dönüştürme kullanın.

## <a name="remarks"></a>Açıklamalar

**Realloc** işlevi, ayrılmış bir bellek bloğunun boyutunu değiştirir. *Memblock* bağımsız değişkeni bellek bloğunun başlangıcına işaret eder. *Memblock* **null**ise **realloc** , **malloc** ile aynı şekilde davranır ve yeni bir *Boyut* bayt bloğu ayırır. *Memblock* **null**değilse, bir önceki **calloc**, **malloc**veya **realloc**çağrısıyla döndürülen bir işaretçi olmalıdır.

*Boyut* bağımsız değişkeni, blok için bayt cinsinden yeni boyut verir. Yeni blok farklı bir konumda olabilse de bloğunun içeriği yeni ve eski boyutların daha kısa bir yere kadar değişmez. Yeni blok yeni bir bellek konumunda olabileceğinden, **realloc** tarafından döndürülen işaretçinin *memblock* bağımsız değişkeniyle geçen işaretçi olması garanti edilmez. **realloc** , arabellek büyümesi durumunda yeni ayrılan belleği sıfırlamaz.

bellek ayırma başarısız olursa veya istenen bellek miktarı **_HEAP_MAXREQ**aşarsa, **realloc** **errno** değerini **ENOMEM** olarak ayarlar. Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**realloc** , yeni işleyici modunu ayarlamak için C++ [_set_new_mode](set-new-mode.md) işlevini kullanmak üzere **malloc** çağırır. Yeni işleyici modu, hata durumunda **malloc** 'ın [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamını çağırıp çağırmayacağını gösterir. Varsayılan olarak, **malloc** bellek ayırma hatası üzerine yeni işleyici yordamını çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz, böylelikle **realloc** bellek ayıramadığında, **malloc** yeni işleyici yordamını aynı nedenden dolayı başarısız olduğunda **Yeni** işlecin yaptığı şekilde çağırır. Varsayılanı geçersiz kılmak için şunu çağırın

```C
_set_new_mode(1);
```

daha erken bir programda veya NEWMODE ile bağlantılandırın. OBJ (bkz. [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Uygulama, C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, **realloc** [_realloc_dbg](realloc-dbg.md)olarak çözümlenir. Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

**realloc** , ve `__declspec(noalias)` işlevinin `__declspec(restrict)`genel değişkenleri değiştirmeyeceği garantisi olduğunu ve döndürülen işaretçinin diğer ad olmadığından emin olduğunu belirtir ve olarak işaretlenir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md) ve [Restrict](../../cpp/restrict.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**realloc**|\<Stdlib. h> ve \<malloc. h>|

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
[Süz](free.md)<br/>
[malloc](malloc.md)<br/>
