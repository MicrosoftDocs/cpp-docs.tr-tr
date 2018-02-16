---
title: _msize_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _msize_dbg
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
- _msize_dbg
- msize_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks
- _msize_dbg function
- msize_dbg function
ms.assetid: a333f4b6-f8a2-4e61-bb69-cb34063b8cef
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c4168f6652e00d91fc1013c7acad04798b0bf03
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="msizedbg"></a>_msize_dbg
(Yalnızca hata ayıklama sürümü) yığın bellek bloğu boyutu hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      size_t _msize_dbg(  
   void *userData,  
   int blockType   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `userData`  
 Bellek Blok boyutu belirlemek üzere işaretçi.  
  
 *blockType*  
 Belirtilen bellek bloğu türü: `_CLIENT_BLOCK` veya **_NORMAL_BLOCK**.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarıyla tamamlandığında, `_msize_dbg` döndürür boyutunu (bayt cinsinden) belirtilen bellek bloğu; Aksi takdirde NULL döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_msize_dbg` _ hata ayıklama sürümü[msize](../../c-runtime-library/reference/msize.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı `_msize_dbg` yapılan bir çağrı için sınırlı `_msize`. Her ikisi de `_msize` ve `_msize_dbg` bir bellek bloğu içinde temel öbek boyutunu hesaplamak ancak `_msize_dbg` iki hata ayıklama özellikleri ekler: döndürülen boyutunda bellek bloğu kullanıcı kısmının her iki tarafında arabellekleri içerir ve boyutuna izin verir hesaplamalar için belirli blok türü.  
  
 Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
 Bu işlev, parametre doğrular. Varsa `memblock` null işaretçi `_msize` açıklandığı gibi bir geçersiz parametre işleyiciyi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Hata işleniyorsa işlevi ayarlar `errno` için `EINVAL` ve -1 döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_msize_dbg`|\<crtdbg.h>|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_msize_dbg.c  
// compile with: /MTd  
/*  
 * This program allocates a block of memory using _malloc_dbg  
 * and then calls _msize_dbg to display the size of that block.  
 * Next, it uses _realloc_dbg to expand the amount of  
 * memory used by the buffer and then calls _msize_dbg again to  
 * display the new amount of memory allocated to the buffer.  
 */  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
        long *buffer, *newbuffer;  
        size_t size;  
  
        /*   
         * Call _malloc_dbg to include the filename and line number  
         * of our allocation request in the header  
         */  
        buffer = (long *)_malloc_dbg( 40 * sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );  
        if( buffer == NULL )  
               exit( 1 );  
  
        /*   
         * Get the size of the buffer by calling _msize_dbg  
         */  
        size = _msize_dbg( buffer, _NORMAL_BLOCK );  
        printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );  
  
        /*   
         * Reallocate the buffer using _realloc_dbg and show the new size  
         */  
        newbuffer = _realloc_dbg( buffer, size + (40 * sizeof(long)), _NORMAL_BLOCK, __FILE__, __LINE__ );  
        if( newbuffer == NULL )  
               exit( 1 );  
        buffer = newbuffer;  
        size = _msize_dbg( buffer, _NORMAL_BLOCK );  
        printf( "Size of block after _realloc_dbg of 40 more longs: %u\n", size );  
  
        free( buffer );  
        exit( 0 );  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
Size of block after _malloc_dbg of 40 longs: 160  
Size of block after _realloc_dbg of 40 more longs: 320  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)