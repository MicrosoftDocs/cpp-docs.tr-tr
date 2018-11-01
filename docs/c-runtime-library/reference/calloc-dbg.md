---
title: _calloc_dbg
ms.date: 11/04/2016
apiname:
- _calloc_dbg
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
- _calloc_dbg
- calloc_dbg
helpviewer_keywords:
- _calloc_dbg function
- calloc_dbg function
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
ms.openlocfilehash: c525aa2f19b39ba3cb8304c59c96196707ad859c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454398"
---
# <a name="callocdbg"></a>_calloc_dbg

Hata ayıklama üst bilgisi için bir sayı ile ek alana yığın bellek bloğu ayırır ve arabellek (yalnızca hata ayıklama sürümü) üzerine yazılır.

## <a name="syntax"></a>Sözdizimi

```C
void *_calloc_dbg(
   size_t num,
   size_t size,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*Sayı*<br/>
İstenen bellek bloğu sayısı.

*Boyutu*<br/>
İstenen boyut (bayt) her bellek bloğu.

*blockType*<br/>
İstenen bellek bloğu türü: **_clıent_block** veya **_NORMAL_BLOCK**.

Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz.[hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details).

*Dosya adı*<br/>
Ayırma işlemi istenen kaynak dosyasının adı işaretçi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada ayırma işlemi burada istendi veya **NULL**.

*Filename* ve *linenumber* parametreleri yalnızca kullanılabilir olduğunda **_calloc_dbg** açıkça çağrılan veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)ön işlemci sabiti tanımlanmış.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, bu işlev bir işaretçi en son ayrılmış bellek bloğu kullanıcı bölümünü döndürür, yeni işleyici işlevi çağırır veya döndürür **NULL**. Dönüş davranışı eksiksiz bir açıklaması için Açıklamalar bölümüne bakın. Yeni işleyici işlevi nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [calloc](calloc.md) işlevi.

## <a name="remarks"></a>Açıklamalar

**_calloc_dbg** bir hata ayıklama sürümü [calloc](calloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_calloc_dbg** çağrısı azaltılır **calloc**. Her ikisi de **calloc** ve **_calloc_dbg** tahsis *numarası* temel yığında bellek engeller ancak **_calloc_dbg** birkaç hata ayıklama sunar Özellikler:

- Her iki tarafında sızıntıları için test edilecek blok kullanıcı kısmı, arabellek.

- Belirli bir ayırma türleri izlemek için bir blok türü parametresi.

- *filename*/*linenumber* ayırma isteklerini kökenini belirlemek için bilgi.

**_calloc_dbg** istenen biraz daha fazla alan ile her bellek bloğu ayırır *boyutu*. Ek alan, hata ayıklama bellek bloklarını bağlantı ve uygulama ile hata ayıklama üstbilgi bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Blok atandığında, blok kullanıcı bölümünü 0xCD değeri ile doldurulur ve 0xFD ile doldurulmuş her üzerine yaz arabellek.

**_calloc_dbg** ayarlar **errno** için **ENOMEM** bir bellek ayırma başarısız olursa; **EINVAL** (daha önce bahsedilen ek yük dahil) ihtiyaç duyulan bellek miktarı aşması durumunda döndürülen **_HEAP_MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama derlemesinde hata ayıklama sürümü yerine standart yığın işlev çağırma arasındaki farklar hakkında daha fazla bilgi için bkz. [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_calloc_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_callocd.c
// This program uses _calloc_dbg to allocate space for
// 40 long integers. It initializes each element to zero.

#include <stdio.h>
#include <malloc.h>
#include <crtdbg.h>

int main( void )
{
    long *bufferN, *bufferC;

    // Call _calloc_dbg to include the filename and line number
    // of our allocation request in the header and also so we can
    // allocate CLIENT type blocks specifically
    bufferN = (long *)_calloc_dbg( 40, sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );
    bufferC = (long *)_calloc_dbg( 40, sizeof(long), _CLIENT_BLOCK, __FILE__, __LINE__ );
    if( bufferN != NULL && bufferC != NULL )
        printf( "Allocated memory successfully\n" );
    else
        printf( "Problem allocating memory\n" );

    / _free_dbg must be called to free CLIENT type blocks
    free( bufferN );
    _free_dbg( bufferC, _CLIENT_BLOCK );
}
```

```Output
Allocated memory successfully
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[calloc](calloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
