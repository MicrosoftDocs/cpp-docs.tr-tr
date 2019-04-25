---
title: _expand_dbg
ms.date: 11/04/2016
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
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
ms.openlocfilehash: cc3aa2b7e39b52eb71ac10a9b5c4a221ba6fb70c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288051"
---
# <a name="expanddbg"></a>_expand_dbg

Belirtilen bir yığında bellek bloğu genişletme veya engelle (yalnızca hata ayıklama sürümü) ihtiyaçlarımıza göre yeniden boyutlandırır.

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
Daha önce ayrılmış bellek bloğuna işaretçi.

*newSize*<br/>
Yeni Boyut (bayt cinsinden) blok için istendi.

*blockType*<br/>
Yeniden boyutlandırılan blok türü istendi: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
İstenen kaynak dosyasının adı işaretçi işlemi genişletin veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada genişletme işlemi burada istendi veya **NULL**.

*Filename* ve *linenumber* parametreleri yalnızca kullanılabilir olduğunda **_expand_dbg** açıkça çağrılan veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)ön işlemci sabiti tanımlanmış.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, **_expand_dbg** yeniden boyutlandırılan bir bellek bloğu için bir işaretçi döndürür. Bellek taşınıp taşınmayacağı çünkü adresi userData aynıdır. Bir hata oluştu veya blok istenen boyuta genişletilemedi, üretebiliyorsa **NULL**. Bir hata oluşursa **errno** hata ile işletim sisteminden yapısı bilgilerdir. Hakkında daha fazla bilgi için **errno**, bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Expand_dbg** işlev _ hata ayıklama sürümü,[genişletin](expand.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_expand_dbg** çağrısı azaltılır **_expand**. Her ikisi de **_expand** ve **_expand_dbg** taban yığının bellek bloğunda yeniden boyutlandırma ancak **_expand_dbg** birkaç hata ayıklama özellikleri kapsar: kullanıcı her iki tarafındaki arabellekler Blok için sızıntılara, belirli bir ayırma türleri izlemek için bir blok türü parametresi test etmek için bir kısmı ve *filename*/*linenumber* kökenini belirlemek için bilgi ayırma isteklerini.

**_expand_dbg** istenen biraz daha fazla alan ile belirtilen bellek bloğu yeniden boyutlandırır *newSize*. *newSize* büyük ya da ilk olarak ayrılan bellek blok boyutundan küçük olabilir. Ek alan, hata ayıklama bellek bloklarını bağlantı ve uygulama ile hata ayıklama üstbilgi bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Yeniden boyutlandırma, genişletme veya orijinal bellek bloğunun ihtiyaçlarımıza gerçekleştirilir. **_expand_dbg** gibi bellek bloğu taşımaz [_realloc_dbg](realloc-dbg.md) işlevi.

Zaman *newSize* özgün blok boyutu, bellek bloğu genişletilir daha büyüktür. Bellek bloğu istenen boyutuna genişletilemiyor, bir genişletme sırasında **NULL** döndürülür. Zaman *newSize* yeni boyut alınana kadar özgün blok boyutu, bellek bloğu sözleşmeleri yapılır daha küçük.

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemesinde çağırma arasındaki farklar hakkında daha fazla bilgi için bkz. [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

Bu işlev, parametrelerini doğrular. Varsa *memblock* null bir işaretçiyse veya boyutu daha büyükse **_HEAP_MAXREQ**, bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **NULL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_expand_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

Bu programın çıkışı tüm bölümleri genişletmek için bilgisayarınızın yeteneklerine bağlı bağlıdır. Tüm bölümleri genişlettiyseniz, çıkışı Çıkış bölümünde yansıtılır.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
