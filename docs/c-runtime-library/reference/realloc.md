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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 964c465a95d44de9d8a4d399f23ec43f8a3a6692
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332930"
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
Daha önce ayrılmış bellek bloğu için işaretçi.

*Boyutu*<br/>
Baytlarda yeni boyut.

## <a name="return-value"></a>Dönüş Değeri

**realloc,** **yeniden** tahsis edilen (ve büyük olasılıkla taşınan) bellek bloğuna bir boşluk işaretçisi döndürür.

Bloğu verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, özgün blok değişmeden bırakılır ve **NULL** döndürülür.

*Boyut* sıfır ise, *memblock* tarafından işaret edilen blok serbest bırakılır; döndürme değeri **NULL'dur**ve *memblock* serbest bırakılmış bir bloğu işaret ederek bırakılır.

İade değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalanması garanti edilen bir depolama alanına işaret ediyor. **Void**dışında bir tür için bir işaretçi almak için, dönüş değeri bir tür döküm kullanın.

## <a name="remarks"></a>Açıklamalar

**Realloc** işlevi ayrılmış bellek bloğunun boyutunu değiştirir. *Memblock* bağımsız değişkeni bellek bloğunun başlangıcını işaret edersiniz. *memblock* **NULL**ise, **realloc** **malloc** aynı şekilde olur ve *boyutu* bayt yeni bir blok ayırır. *Memblock* **NULL**değilse, bir işaretçi **calloc,** **malloc,** veya **realloc**önceki bir çağrı tarafından döndürülen olmalıdır.

Boyut bağımsız *değişkeni,* baytlar halinde bloğun yeni boyutunu verir. Yeni blok farklı bir konumda olsa da, bloğun içeriği yeni ve eski boyutların daha kısasına kadar değişmez. Yeni blok yeni bir bellek konumunda olabileceğinden, **realloc** tarafından döndürülen işaretçinin *memblock* bağımsız değişkeninden geçen işaretçi olacağı garanti edilmez. **realloc** tampon büyüme durumunda sıfır yeni ayrılmış bellek değildir.

**realloc,** bellek ayırma başarısız olursa veya istenen bellek miktarı **_HEAP_MAXREQ**aşarsa **ENOMeM'e** **errno** ayarlar. Bu ve diğer hata kodları hakkında bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

**realloc,** c++ [_set_new_mode](set-new-mode.md) işlevini kullanarak yeni işleyici modunu ayarlamak için **malloc** çağırır. Yeni işleyici modu, hata, **malloc** [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamı aramak olup olmadığını gösterir. Varsayılan olarak, **malloc** bellek tahsis başarısız yeni işleyici yordamı aramaz. Bu varsayılan davranışı geçersiz kılabilirsiniz, **böylece, realloc** bellek ayırmayı başaramayınca, **malloc** **yeni** işleyici yordamını yeni işlecinin aynı nedenle başarısız olduğu gibi çağırır. Varsayılanı geçersiz kılmak için,

```C
_set_new_mode(1);
```

erken olanlar programı, ya da NEWMODE ile bağlantı. OBJ (bkz. [Bağlantı Seçenekleri](../../c-runtime-library/link-options.md)).

Uygulama C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, **realloc** [_realloc_dbg.](realloc-dbg.md) Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için [CRT Hata Ayıklama Yığını'na](/visualstudio/debugger/crt-debug-heap-details)bakın.

**realloc** `__declspec(noalias)` işaretlenir `__declspec(restrict)`ve , işlevin genel değişkenleri değiştirmemesi için garanti edildiği ve döndürülen işaretçinin diğer adı olmadığı anlamına gelir. Daha fazla bilgi için [noalias'a](../../cpp/noalias.md) bakın ve [kısıtlayın.](../../cpp/restrict.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**realloc**|\<stdlib.h> \<ve malloc.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
[Ücret -siz](free.md)<br/>
[malloc](malloc.md)<br/>
