---
title: _realloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _realloc_dbg
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
- _realloc_dbg
- realloc_dbg
dev_langs: C++
helpviewer_keywords:
- reallocating memory blocks
- realloc_dbg function
- memory blocks, reallocating
- memory, reallocating
- _realloc_dbg function
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3885bfb44745d815e50012d0447060b6ff2aa985
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="reallocdbg"></a>_realloc_dbg
Belirtilen bir yığınındaki bellek bloğu taşıma ve/veya blok (yalnızca hata ayıklama sürümü) yeniden boyutlandırma yeniden ayırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *_realloc_dbg(  
   void *userData,  
   size_t newSize,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `userData`  
 Önceden ayrılmış bellek bloğu işaretçi.  
  
 `newSize`  
 Boyutu (bayt) reallocated bloğunun istedi.  
  
 `blockType`  
 İstenen reallocated bloğunun türü: `_CLIENT_BLOCK` veya `_NORMAL_BLOCK`.  
  
 `filename`  
 İstenen kaynak dosyasının adını işaretçi `realloc` işlemi ya da NULL.  
  
 `linenumber`  
 Satır numarası kaynak dosyasında nerede `realloc` işlemi istenen veya NULL.  
  
 `filename` Ve `linenumber` parametreleri yalnızca kullanılabilir olduğunda `_realloc_dbg` açıkça çağrılan veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) önişlemci sabiti tanımlandı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarıyla tamamlandığında, bu işlev bir işaretçi ayrılabilecek bellek bloğu kullanıcı bölümünü döndürür, yeni işleyici işlevini çağırır ya da NULL döndürür. Dönüş davranışı tam bir açıklaması için aşağıdaki Açıklamalar bölümüne bakın. Yeni işleyici işlevi nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [realloc](../../c-runtime-library/reference/realloc.md) işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 `_realloc_dbg`bir hata ayıklama sürümü [realloc](../../c-runtime-library/reference/realloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı `_realloc_dbg` yapılan bir çağrı için sınırlı `realloc`. Her ikisi de `realloc` ve `_realloc_dbg` bir bellek bloğu temel yığınındaki yeniden tahsis ancak `_realloc_dbg` birkaç hata ayıklama özelliği düzenler: kullanıcı bölümünün belirli izlemek için bir blok türü parametresi bloğunun sızıntıları için test etmek için her iki tarafında arabellekler ayırma türleri ve `filename` / `linenumber` ayırma isteklerini kökenini belirlemek için bilgi.  
  
 `_realloc_dbg`İstenen biraz daha fazla alan ile belirtilen bellek bloğu yeniden ayırır `newSize`. `newSize`büyük veya ilk olarak ayrılmış bellek bloğu boyutundan küçük olabilir. Ek alanı, hata ayıklama bellek blokları bağlantı ve uygulama ile hata ayıklama üst bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Yeniden ayırma özgün bellek bloğu yığınındaki farklı bir konuma taşıyarak, aynı zamanda bellek bloğu boyutunu değiştirme neden olabilir. Bellek bloğu taşınırsa, özgün bloğun içeriğinin üzerine yazılır.  
  
 `_realloc_dbg`Ayarlar `errno` için `ENOMEM` bir bellek ayırma başarısız olursa veya (daha önce bahsedilen ek yük dahil) gerekli bellek miktarını aşarsa `_HEAP_MAXREQ`. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_realloc_dbg`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="example"></a>Örnek  
 Örnekte bkz [_msize_dbg](../../c-runtime-library/reference/msize-dbg.md) konu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)