---
title: _aligned_recalloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_recalloc_dbg
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
- _aligned_recalloc_dbg
- aligned_recalloc_dbg
dev_langs: C++
helpviewer_keywords:
- aligned_recalloc_dbg function
- _aligned_recalloc_dbg function
ms.assetid: 55c3c27e-561c-4d6b-9bf9-1e34cc556e4b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f434c09e22933859b227f2517e124e9ca668e2cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="alignedrecallocdbg"></a>_aligned_recalloc_dbg
İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) ve bellek 0 (yalnızca hata ayıklama sürümü) başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void * _aligned_recalloc_dbg(  
   void * memblock,   
   size_t num,  
   size_t size,   
   size_t alignment,  
   const char *filename,  
   int linenumber  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`memblock`  
 Geçerli bellek bloğu işaretçisi.  
  
 [in]`num`  
 Öğe sayısı.  
  
 [in]`size`  
 Her öğenin bayt cinsinden boyutu.  
  
 [in]`alignment`  
 Hizalama değeri bir tamsayı güç 2 olmalıdır.  
  
 [in]`filename`  
 İstenen ayırma işlemi kaynak dosyasının adını işaretçi veya `NULL`.  
  
 [in]`linenumber`  
 Satır numarası ayırma işlemi istenen burada kaynak dosyasında veya `NULL`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_aligned_recalloc_dbg`void işaretçi ayrılabilecek (ve muhtemelen taşınan) bellek bloğuna döndürür. Dönüş değeri `NULL` boyutu sıfır ise ve arabellek bağımsız değişken değil `NULL`, veya blok verilen boyuta genişletmek için yeterli kullanılabilir bellek değilse. İlk durumda, özgün blok serbest bırakılır. İkinci durumda, özgün blok değiştirilmez. Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun hizalanacak garanti bir depolama alanı işaret eder. Dönüş değerini cast türü void, kullanım dışında bir tür için bir işaretçi almak için.  
  
 Belleği yeniden tahsis ve bir blok hizalamasını değiştirmek için bir hata var.  
  
## <a name="remarks"></a>Açıklamalar  
 `_aligned_recalloc_dbg`bir hata ayıklama sürümü [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı `_aligned_recalloc_dbg` yapılan bir çağrı için sınırlı `_aligned_recalloc`. Her ikisi de `_aligned_recalloc` ve `_aligned_recalloc_dbg` bir bellek bloğu temel yığınındaki yeniden tahsis ancak `_aligned_recalloc_dbg` birkaç hata ayıklama özelliği düzenler: kullanıcı bölümünün belirli izlemek için bir blok türü parametresi bloğunun sızıntıları için test etmek için her iki tarafında arabellekler ayırma türleri ve `filename` / `linenumber` ayırma isteklerini kökenini belirlemek için bilgi.  
  
 `_aligned_recalloc_dbg`İstenen boyuttan biraz daha fazla alan ile belirtilen bellek bloğu yeniden ayırır (`num` * `size`) hangi olabilir veya büyük başlangıçta ayrılmış bellek bloğu boyutu küçüktür. Ek alanı, hata ayıklama bellek blokları bağlantı ve uygulama ile hata ayıklama üst bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Yeniden ayırma özgün bellek bloğu yığınındaki farklı bir konuma taşıyarak, aynı zamanda bellek bloğu boyutunu değiştirme neden olabilir. Blok kullanıcı bölümünü 0xCD değeri ile doldurulur ve üzerine yazma arabelleği 0xFD ile doldurulur.  
  
 `_aligned_recalloc_dbg`Ayarlar `errno` için `ENOMEM` bir bellek ayırma başarısız olursa; `EINVAL` (daha önce bahsedilen ek yük dahil) gerekli bellek miktarını aşıyorsa döndürülen `_HEAP_MAXREQ`. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Ayrıca, `_aligned_recalloc_dbg` parametrelerini doğrular. Varsa `alignment` güç değil açıklandığı gibi bu işlev 2, geçersiz parametre işleyicisi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür `NULL` ve ayarlar `errno` için `EINVAL`.  
  
 Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_aligned_recalloc_dbg`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)