---
title: _calloc_dbg
ms.date: 11/04/2016
api_name:
- _calloc_dbg
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
- _calloc_dbg
- calloc_dbg
helpviewer_keywords:
- _calloc_dbg function
- calloc_dbg function
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
ms.openlocfilehash: eab17348e473a4f642e784defe4569e0e799299e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939315"
---
# <a name="_calloc_dbg"></a>_calloc_dbg

Bir hata ayıklama üst bilgisi ve üzerine yazma arabellekleri (yalnızca hata ayıklama sürümü) için ek alana sahip yığında dizi bellek bloğu ayırır.

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

*sayısından*<br/>
İstenen bellek bloğu sayısı.

*boyutla*<br/>
Her bellek bloğunun istenen boyutu (bayt).

*blockType*<br/>
İstenen bellek bloğu türü: **_Client_block** veya **_NORMAL_BLOCK**.

Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz.[hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

*kısaltın*<br/>
Ayırma işlemi veya **null**için istenen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyasındaki ayırma işleminin istendiği veya **null**olduğu satır numarası.

*Filename* ve *onayın* parametreleri yalnızca **_calloc_dbg** açıkça çağrıldığında veya [_crtdbg_map_ayırma](../../c-runtime-library/crtdbg-map-alloc.md) Önişlemci sabiti tanımlandığında kullanılabilir.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, bu işlev son ayrılan bellek bloğunun Kullanıcı kısmına bir işaretçi döndürür, yeni işleyici işlevini çağırır veya **null**değerini döndürür. Dönüş davranışının ayrıntılı bir açıklaması için, açıklamalar bölümüne bakın. Yeni işleyici işlevinin nasıl kullanıldığı hakkında daha fazla bilgi için, [calloc](calloc.md) işlevine bakın.

## <a name="remarks"></a>Açıklamalar

**_calloc_dbg** , [calloc](calloc.md) işlevinin bir hata ayıklama sürümüdür. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_calloc_dbg** öğesine yapılan her çağrı, **calloc**çağrısına düşürülür. Hem **calloc** hem de **_calloc_dbg** , temel yığında *sayı* bellek blokları ayırır, ancak **_calloc_dbg** çeşitli hata ayıklama özellikleri sunar:

- Sızıntıların test olması için bloğun Kullanıcı bölümünün her iki tarafında da arabellekler.

- Belirli ayırma türlerini izlemek için bir blok türü parametresi.

- /ayırma isteklerinin kaynağını belirleyebilmek için dosya adı*onayın* bilgileri.

**_calloc_dbg** her bir bellek bloğunu istenen *boyuttan*biraz daha fazla alanla ayırır. Hata ayıklama bellek bloklarını bağlamak ve uygulamanın hata ayıklama üstbilgi bilgilerini ve üzerine yazma arabelleğini sağlamak için ek alan, hata ayıklama yığın Yöneticisi tarafından kullanılır. Blok ayrıldığında, bloğun Kullanıcı bölümü, 0xCD değeri ile doldurulur ve üzerine yazma arabelleklerinin her biri 0xFD ile doldurulur.

**_calloc_dbg** bir bellek ayırma başarısız olursa **errno** değerini **ENOMEM** olarak ayarlar; **EINVAL** , gereken bellek miktarı (daha önce bahsedilen ek yük dahil) **_Heap_maxreq**değerini aşarsa döndürülür. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde bir standart yığın işlevi çağırma ile ilgili hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_calloc_dbg**|\<Crtdbg. h >|

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
