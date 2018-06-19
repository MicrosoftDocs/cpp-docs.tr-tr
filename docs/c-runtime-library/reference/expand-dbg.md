---
title: _expand_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _expand_dbg
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
apitype: DLLExport
f1_keywords:
- expand_dbg
- _expand_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 023bda761454a6a1e18ce68c8e7576af2759abbf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403641"
---
# <a name="expanddbg"></a>_expand_dbg

Belirtilen bir yığınındaki bellek bloğu genişletmeden veya (yalnızca hata ayıklama sürümü) blok daraltılırken göre yeniden boyutlandırır.

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

*UserData*<br/>
Önceden ayrılmış bellek bloğu işaretçi.

*newSize*<br/>
Yeni boyutu (bayt cinsinden) blok istedi.

*blockType*<br/>
Yeniden boyutlandırılan blok türü istendi: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
İstenen kaynak dosyasının adını işaretçisine işlemi genişletin veya **NULL**.

*LineNumber*<br/>
Satır numarası genişletme işlemi istenen burada kaynak dosyasında veya **NULL**.

*Filename* ve *linenumber* parametreleri yalnızca kullanılabilir olduğunda **_expand_dbg** açıkça çağrılan veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)önişlemci sabiti tanımlandı.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, **_expand_dbg** yeniden boyutlandırılan bellek bloğu için bir işaretçi döndürür. Bellek taşınmaz olduğundan, adres userData aynıdır. Bir hata oluştu veya blok istenen boyuta genişletilemedi, döndürür **NULL**. Bir hata oluşursa **errno** hata ile işletim sisteminden doğası hakkındaki bilgilerdir. Hakkında daha fazla bilgi için **errno**, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Expand_dbg** işlevidir _ hata ayıklama sürümü[genişletin](expand.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_expand_dbg** yapılan bir çağrı için sınırlı **siteyi g_enişlet**. Her ikisi de **siteyi g_enişlet** ve **_expand_dbg** bir bellek bloğu temel yığınındaki yeniden boyutlandırma ancak **_expand_dbg** birkaç hata ayıklama özelliği düzenler: kullanıcı her iki tarafında arabellekler belirli ayırma türleri izlemek için bir blok türü parametresi sızıntıları için test etmek için blok bölümünü ve *filename*/*linenumber* kökenini belirlemek için bilgi ayırma istek sayısı.

**_expand_dbg** istenen biraz daha fazla alan ile belirtilen bellek bloğu yeniden boyutlandırır *newSize*. *newSize* büyük ya da özgün olarak ayrılmış bellek bloğu boyutu küçüktür olabilir. Ek alanı, hata ayıklama bellek blokları bağlantı ve uygulama ile hata ayıklama üst bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Yeniden boyutlandırma, genişletme veya özgün bellek bloğu daraltılırken gerçekleştirilir. **_expand_dbg** yaptığı gibi bellek bloğu taşımaz [_realloc_dbg](realloc-dbg.md) işlevi.

Zaman *newSize* özgün blok boyutu, bellek bloğu genişletilmiş sayısından daha büyük. Bellek bloğu istenen boyutuna genişletilemiyor varsa bir genişletme sırasında **NULL** döndürülür. Zaman *newSize* yeni boyutu alınana kadar özgün blok boyutu, bellek bloğu sözleşme yapılan daha küçük.

Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

Bu işlev parametrelerini doğrular. Varsa *memblock* null işaretçinin veya boyutu büyükse **_HEAP_MAXREQ**, açıklandığı gibi bir geçersiz parametre işleyicisi bu işlevi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi döndürür **NULL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_expand_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

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

Bu programın çıkışı tüm bölümleri genişletmek için bilgisayarınızın özelliği bağlıdır. Tüm bölümler genişletildiğinde, çıktı çıktı bölümünde yansıtılır.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
