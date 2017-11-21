---
title: _recalloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _recalloc_dbg
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
- recalloc_dbg
- _recalloc_dbg
dev_langs: C++
helpviewer_keywords:
- _recalloc_dbg function
- recalloc_dbg function
ms.assetid: 43c3e9b2-be6d-4508-9b0f-3220c8a47ca3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 02ac41e22a5080576339b00e54f339bb878a794d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="recallocdbg"></a>_recalloc_dbg
Bir dizi yeniden ayırır ve öğeleri 0 (yalnızca hata ayıklama sürümü) başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *_recalloc_dbg(   
   void *userData,  
   size_t num,  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `userData`  
 Önceden ayrılmış bellek bloğu işaretçi.  
  
 `num`  
 Bellek blokları istenen sayısı.  
  
 `size`  
 İstenen boyut her bellek bloğu (bayt).  
  
 `blockType`  
 İstenen bellek bloğu türü: `_CLIENT_BLOCK` veya `_NORMAL_BLOCK`.  
  
 Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details).  
  
 `filename`  
 İstenen ayırma işlemi kaynak dosyasının adını işaretçi veya `NULL`.  
  
 `linenumber`  
 Satır numarası ayırma işlemi istenen burada kaynak dosyasında veya `NULL`.  
  
 `filename` Ve `linenumber` parametreleri yalnızca kullanılabilir olduğunda `_recalloc_dbg` açıkça çağrılan veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) önişlemci sabiti tanımlandı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarıyla tamamlandığında, bu işlev bir işaretçi ayrılabilecek bellek bloğu kullanıcı bölümünü döndürür, yeni işleyici işlevini çağırır ya da NULL döndürür. Dönüş davranışı tam bir açıklaması için aşağıdaki Açıklamalar bölümüne bakın. Yeni işleyici işlevi nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [_recalloc](../../c-runtime-library/reference/recalloc.md) işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 `_recalloc_dbg`bir hata ayıklama sürümü [_recalloc](../../c-runtime-library/reference/recalloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı `_recalloc_dbg` yapılan bir çağrı için sınırlı `_recalloc`. Her ikisi de `_recalloc` ve `_recalloc_dbg` bir bellek bloğu temel yığınındaki yeniden tahsis ancak `_recalloc_dbg` birkaç hata ayıklama özelliği düzenler: kullanıcı bölümünün belirli izlemek için bir blok türü parametresi bloğunun sızıntıları için test etmek için her iki tarafında arabellekler ayırma türleri ve `filename` / `linenumber` ayırma isteklerini kökenini belirlemek için bilgi.  
  
 `_recalloc_dbg`İstenen boyuttan biraz daha fazla alan ile belirtilen bellek bloğu yeniden ayırır (`num` * `size`) hangi olabilir veya büyük başlangıçta ayrılmış bellek bloğu boyutu küçüktür. Ek alanı, hata ayıklama bellek blokları bağlantı ve uygulama ile hata ayıklama üst bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Yeniden ayırma özgün bellek bloğu yığınındaki farklı bir konuma taşıyarak, aynı zamanda bellek bloğu boyutunu değiştirme neden olabilir. Blok kullanıcı bölümünü 0xCD değeri ile doldurulur ve 0xFD ile doldurulmuş her üzerine yaz arabellek.  
  
 `_recalloc_dbg`Ayarlar `errno` için `ENOMEM` bir bellek ayırma başarısız olursa; `EINVAL` (daha önce bahsedilen ek yük dahil) gerekli bellek miktarını aşıyorsa döndürülen `_HEAP_MAXREQ`. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_recalloc_dbg`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)