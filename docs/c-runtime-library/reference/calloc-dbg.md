---
description: 'Hakkında daha fazla bilgi edinin: _calloc_dbg'
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
ms.openlocfilehash: af7b9a5004a35f91710421774fc580bf91d9ab97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198863"
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

*Blok türü*<br/>
İstenen bellek bloğu türü: **_CLIENT_BLOCK** veya **_NORMAL_BLOCK**.

Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz.[hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

*filename*<br/>
Ayırma işlemi veya **null** için istenen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyasındaki ayırma işleminin istendiği veya **null** olduğu satır numarası.

*Filename* ve *onayın* parametreleri yalnızca **_calloc_dbg** açıkça çağrıldığında veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) Önişlemci sabiti tanımlandığında kullanılabilir.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, bu işlev son ayrılan bellek bloğunun Kullanıcı kısmına bir işaretçi döndürür, yeni işleyici işlevini çağırır veya **null** değerini döndürür. Dönüş davranışının ayrıntılı bir açıklaması için, açıklamalar bölümüne bakın. Yeni işleyici işlevinin nasıl kullanıldığı hakkında daha fazla bilgi için, [calloc](calloc.md) işlevine bakın.

## <a name="remarks"></a>Açıklamalar

**_calloc_dbg** , [calloc](calloc.md) işlevinin bir hata ayıklama sürümüdür. [_DEBUG](../../c-runtime-library/debug.md) tanımlanmadığı zaman, **_calloc_dbg** her bir çağrı **calloc** çağrısına düşürülür. Hem **calloc** hem de **_calloc_dbg** , temel yığında *sayı* bellek blokları ayırır, ancak **_calloc_dbg** çeşitli hata ayıklama özellikleri sunar:

- Sızıntıların test olması için bloğun Kullanıcı bölümünün her iki tarafında da arabellekler.

- Belirli ayırma türlerini izlemek için bir blok türü parametresi.

- *dosya adı* / ayırma isteklerinin kaynağını tespit etmek için *onayın* bilgileri.

**_calloc_dbg** , her bellek bloğunu istenen *boyuttan* biraz daha fazla alanla ayırır. Hata ayıklama bellek bloklarını bağlamak ve uygulamanın hata ayıklama üstbilgi bilgilerini ve üzerine yazma arabelleğini sağlamak için ek alan, hata ayıklama yığın Yöneticisi tarafından kullanılır. Blok ayrıldığında, bloğun Kullanıcı bölümü, 0xCD değeri ile doldurulur ve üzerine yazma arabelleklerinin her biri 0xFD ile doldurulur.

bellek ayırma başarısız olursa, **_calloc_dbg** **errno** , **ENOMEM** olarak ayarlanır; **EINVAL** , gereken bellek miktarı (daha önce bahsedilen ek yük dahil) **_HEAP_MAXREQ** aşarsa döndürülür. Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde bir standart yığın işlevi çağırma ile ilgili hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_calloc_dbg**|\<crtdbg.h>|

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

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[calloc](calloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
