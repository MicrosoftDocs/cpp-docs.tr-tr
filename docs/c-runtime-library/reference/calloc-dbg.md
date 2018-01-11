---
title: _calloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _calloc_dbg
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
dev_langs: C++
helpviewer_keywords:
- _calloc_dbg function
- calloc_dbg function
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4295dd84e8066de0906a6fcd7b154c94875f7f5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="callocdbg"></a>_calloc_dbg
Hata ayıklama başlığı için ek alan yığınla bellek blok sayısını ayırır ve arabellekler (yalnızca hata ayıklama sürümü) üzerine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *_calloc_dbg(   
   size_t num,  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `num`  
 Bellek blokları istenen sayısı.  
  
 `size`  
 İstenen boyut her bellek bloğu (bayt).  
  
 `blockType`  
 İstenen bellek bloğu türü: `_CLIENT_BLOCK` veya `_NORMAL_BLOCK`.  
  
 Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz:[hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details).  
  
 `filename`  
 İstenen ayırma işlemi kaynak dosyasının adını işaretçi veya `NULL`.  
  
 `linenumber`  
 Satır numarası ayırma işlemi istenen burada kaynak dosyasında veya `NULL`.  
  
 `filename` Ve `linenumber` parametreleri yalnızca kullanılabilir olduğunda `_calloc_dbg` açıkça çağrılan veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) önişlemci sabiti tanımlandı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarıyla tamamlandığında, bu işlev bir işaretçi son ayrılan bellek bloğu kullanıcı bölümünü döndürür, yeni işleyici işlevini çağırır veya verir `NULL`. Dönüş davranışı tam bir açıklaması için Açıklamalar bölümüne bakın. Yeni işleyici işlevi nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [calloc](../../c-runtime-library/reference/calloc.md) işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 `_calloc_dbg`bir hata ayıklama sürümü [calloc](../../c-runtime-library/reference/calloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı `_calloc_dbg` yapılan bir çağrı için sınırlı `calloc`. Her ikisi de `calloc` ve `_calloc_dbg` tahsis `num` bellek temel yığınında engeller, ancak `_calloc_dbg` birkaç hata ayıklama özellikleri sunar:  
  
-   Her iki tarafında sızıntıları için test etmek için blok kullanıcı bölümünü arabellekler.  
  
-   Belirli ayırma türleri izlemek için bir blok tür parametresi.  
  
-   `filename`/`linenumber`ayırma isteklerini kökenini belirlemek için bilgi.  
  
 `_calloc_dbg`Her bellek bloğu ile istenen biraz daha fazla alan ayırır `size`. Ek alanı, hata ayıklama bellek blokları bağlantı ve uygulama ile hata ayıklama üst bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Blok atandığında, blok kullanıcı bölümünü 0xCD değeri ile doldurulur ve 0xFD ile doldurulmuş her üzerine yaz arabellek.  
  
 `_calloc_dbg`Ayarlar `errno` için `ENOMEM` bir bellek ayırma başarısız olursa; `EINVAL` (daha önce bahsedilen ek yük dahil) gerekli bellek miktarını aşıyorsa döndürülen `_HEAP_MAXREQ`. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Hata ayıklama sürümü karşı standart yığın işlevi bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_calloc_dbg`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_callocd.c  
/*  
 * This program uses _calloc_dbg to allocate space for  
 * 40 long integers. It initializes each element to zero.  
 */  
#include <stdio.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
        long *bufferN, *bufferC;  
  
        /*   
         * Call _calloc_dbg to include the filename and line number  
         * of our allocation request in the header and also so we can  
         * allocate CLIENT type blocks specifically  
         */  
        bufferN = (long *)_calloc_dbg( 40, sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );  
        bufferC = (long *)_calloc_dbg( 40, sizeof(long), _CLIENT_BLOCK, __FILE__, __LINE__ );  
        if( bufferN != NULL && bufferC != NULL )  
              printf( "Allocated memory successfully\n" );  
        else  
              printf( "Problem allocating memory\n" );  
  
        /*   
         * _free_dbg must be called to free CLIENT type blocks  
         */  
        free( bufferN );  
        _free_dbg( bufferC, _CLIENT_BLOCK );  
}  
```  
  
```Output  
Allocated memory successfully  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [_DEBUG](../../c-runtime-library/debug.md)