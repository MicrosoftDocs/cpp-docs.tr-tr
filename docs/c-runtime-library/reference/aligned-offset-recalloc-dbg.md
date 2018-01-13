---
title: _aligned_offset_recalloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_offset_recalloc_dbg
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
- aligned_offset_recalloc_dbg
- _aligned_offset_recalloc_dbg
dev_langs: C++
helpviewer_keywords:
- aligned_offset_recalloc_dbg function
- _aligned_offset_recalloc_dbg function
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8701f2e2a52603f08727220e2638f06cc40b7aec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="alignedoffsetrecallocdbg"></a>_aligned_offset_recalloc_dbg
İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) ve bellek 0 (yalnızca hata ayıklama sürümü) başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void * _aligned_offset_recalloc_dbg(  
   void *memblock,   
   size_t num,   
   size_t size,   
   size_t alignment,  
   size_t offset,  
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
 Her öğenin bayt cinsinden uzunluğu.  
  
 [in]`alignment`  
 Hizalama değeri bir tamsayı güç 2 olmalıdır.  
  
 [in]`offset`  
 Hizalama zorlamak için bellek ayırma içine uzaklığı.  
  
 [in]`filename`  
 İstenen kaynak dosyasının adını işaretçi `realloc` işlemi ya da NULL.  
  
 [in]`linenumber`  
 Satır numarası kaynak dosyasında nerede `realloc` işlemi istenen veya NULL.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_aligned_offset_recalloc_dbg`void işaretçi ayrılabilecek (ve muhtemelen taşınan) bellek bloğuna döndürür. Dönüş değeri `NULL` boyutu sıfır ise ve arabellek bağımsız değişken değil `NULL`, veya blok verilen boyuta genişletmek için yeterli kullanılabilir bellek değilse. İlk durumda, özgün blok serbest bırakılır. İkinci durumda, özgün blok değiştirilmez. Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun hizalanacak garanti bir depolama alanı işaret eder. Dönüş değerini cast türü void, kullanım dışında bir tür için bir işaretçi almak için.  
  
## <a name="remarks"></a>Açıklamalar  
 `_aligned_offset_realloc_dbg`bir hata ayıklama sürümü [_aligned_offset_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı `_aligned_offset_recalloc_dbg` yapılan bir çağrı için sınırlı `_aligned_offset_recalloc`. Her ikisi de `_aligned_offset_recalloc` ve `_aligned_offset_recalloc_dbg` bir bellek bloğu temel yığınındaki yeniden tahsis ancak `_aligned_offset_recalloc_dbg` birkaç hata ayıklama özelliği düzenler: kullanıcı bölümünün belirli izlemek için bir blok türü parametresi bloğunun sızıntıları için test etmek için her iki tarafında arabellekler ayırma türleri ve `filename` / `linenumber` ayırma isteklerini kökenini belirlemek için bilgi.  
  
 `_aligned_offset_realloc_dbg`İstenen biraz daha fazla alan ile belirtilen bellek bloğu yeniden ayırır `newSize`. `newSize`büyük veya ilk olarak ayrılmış bellek bloğu boyutundan küçük olabilir. Ek alanı, hata ayıklama bellek blokları bağlantı ve uygulama ile hata ayıklama üst bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Yeniden ayırma özgün bellek bloğu yığınındaki farklı bir konuma taşıyarak, aynı zamanda bellek bloğu boyutunu değiştirme neden olabilir. Bellek bloğu taşınırsa, özgün bloğun içeriğinin üzerine yazılır.  
  
 Bu işlev ayarlar `errno` için `ENOMEM` bellek ayırma başarısız olursa veya istenen boyuta (`num` * `size`) daha büyük olan `_HEAP_MAXREQ`. Hakkında daha fazla bilgi için `errno`, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, `_aligned_offset_recalloc_dbg` parametrelerini doğrular. Varsa `alignment` 2'in üssü değil veya `offset` daha büyük veya eşit istenen boyuta ve sıfır olmayan, bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür `NULL` ve ayarlar `errno` için `EINVAL`.  
  
 Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_aligned_offset_recalloc_dbg`|\<malloc.h >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri Hizalama](../../c-runtime-library/data-alignment.md)