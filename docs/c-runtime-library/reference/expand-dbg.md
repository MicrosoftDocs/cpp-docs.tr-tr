---
description: 'Hakkında daha fazla bilgi edinin: _expand_dbg'
title: _expand_dbg
ms.date: 11/04/2016
api_name:
- _expand_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- expand_dbg
- _expand_dbg
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
ms.openlocfilehash: 6ebdce3a22c4e5b4b63b8301570effed888fe66f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235976"
---
# <a name="_expand_dbg"></a>_expand_dbg

Bloğu genişleterek veya geçirerek (yalnızca hata ayıklama sürümü) yığında belirtilen bellek bloğunu yeniden boyutlandırır.

## <a name="syntax"></a>Sözdizimi

```C
void *_expand_dbg(
   void *userData,
   size_t newSize,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*userData*<br/>
Önceden ayrılmış bellek bloğuna yönelik işaretçi.

*newSize*<br/>
Blok için yeni boyut istedi (bayt cinsinden).

*Blok türü*<br/>
Yeniden boyutlandırılan blok için istenen tür: **_CLIENT_BLOCK** veya **_NORMAL_BLOCK**.

*filename*<br/>
Genişletme işlemi veya **null değeri** istenen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Genişletme işleminin istendiği veya **null** olduğu kaynak dosyadaki satır numarası.

*Filename* ve *onayın* parametreleri yalnızca **_expand_dbg** açıkça çağrıldığında veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) Önişlemci sabiti tanımlandığında kullanılabilir.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, **_expand_dbg** yeniden boyutlandırılmış bellek bloğuna bir işaretçi döndürür. Bellek taşınmadığından, adres userData ile aynı olur. Bir hata oluştuysa veya blok istenen boyuta genişlememişse, **null** döndürür. Bir hata oluşursa, **errno** işletim sisteminden hatanın doğası hakkında bilgi ile birlikte olur. **Errno** hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Expand_dbg** işlevi, _ [Expand](expand.md) işlevinin bir hata ayıklama sürümüdür. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, her **_expand_dbg** çağrısı **_expand** çağrısına düşürülür. Hem **_expand** hem de **_expand_dbg** temel yığında bir bellek bloğunu yeniden boyutlandırır, ancak **_expand_dbg** , bazı hata ayıklama özelliklerini (örneğin, belirli ayırma türlerini izlemek için blok tür parametresi) ve ayırma isteklerinin kaynağını belirlemede *dosya adı* / *onayın* bilgisini karşılar.

**_expand_dbg** belirtilen bellek bloğunu Istenen *newSize* göre biraz daha fazla alanla yeniden boyutlandırır. *newSize* , başlangıçta ayrılan bellek bloğunun boyutundan daha büyük veya daha küçük olabilir. Hata ayıklama bellek bloklarını bağlamak ve uygulamanın hata ayıklama üstbilgi bilgilerini ve üzerine yazma arabelleğini sağlamak için ek alan, hata ayıklama yığın Yöneticisi tarafından kullanılır. Yeniden boyutlandırma, özgün bellek bloğunun genişletilmesinin veya bir şekilde genişletilmesi ile gerçekleştirilir. **_expand_dbg** , [_realloc_dbg](realloc-dbg.md) işlevi gibi bellek bloğunu taşımaz.

*NewSize* , orijinal blok boyutundan daha büyükse, bellek bloğu genişletilir. Genişleme sırasında, bellek bloğu istenen boyuta uyacak şekilde genişletilemez, **null** döndürülür. *NewSize* , orijinal blok boyutundan küçük olduğunda, bellek bloğu yeni boyut alınana kadar alınır.

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

Bu işlev, parametrelerini doğrular. *Memblock* null bir işaretçiyse veya boyut **_HEAP_MAXREQ** büyükse, bu işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **null** değerini döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_expand_dbg**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

```C
// crt_expand_dbg.c
//
// This program allocates a block of memory using _malloc_dbg
// and then calls _msize_dbg to display the size of that block.
// Next, it uses _expand_dbg to expand the amount of
// memory used by the buffer and then calls _msize_dbg again to
// display the new amount of memory allocated to the buffer.
//

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
#include <crtdbg.h>

int main( void )
{
   long *buffer;
   size_t size;

   // Call _malloc_dbg to include the filename and line number
   // of our allocation request in the header
   buffer = (long *)_malloc_dbg( 40 * sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );
   if( buffer == NULL )
      exit( 1 );

   // Get the size of the buffer by calling _msize_dbg
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );

   // Expand the buffer using _expand_dbg and show the new size
   buffer = (long *)_expand_dbg( buffer, size + sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );

   if( buffer == NULL )
      exit( 1 );
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _expand_dbg of 1 more long: %u\n",
           size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after _malloc_dbg of 40 longs: 160
Size of block after _expand_dbg of 1 more long: 164
```

## <a name="comment"></a>Yorum

Bu programın çıktısı bilgisayarınızın tüm bölümleri genişletme özelliğine bağlıdır. Tüm bölümler genişletilmişse çıkış, çıkış bölümüne yansıtılır.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
