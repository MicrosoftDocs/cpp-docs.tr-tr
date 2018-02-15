---
title: _aligned_offset_malloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _aligned_offset_malloc_dbg
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
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc5ec74619f358dbbad27e0bed47115982d5da4e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="alignedoffsetmallocdbg"></a>_aligned_offset_malloc_dbg
Belirtilen hizalama sınırında (yalnızca hata ayıklama sürümü) bellek ayırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void * _aligned_offset_malloc_dbg(  
   size_t size,   
   size_t alignment,   
   size_t offset,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `size`  
 İstenen bellek ayırma boyutu.  
  
 [in] `alignment`  
 Hizalama değeri bir tamsayı güç 2 olmalıdır.  
  
 [in] `offset`  
 Hizalama zorlamak için bellek ayırma içine uzaklığı.  
  
 [in] `filename`  
 İşaretçi ayırma işlemi ya da NULL istenen kaynak dosyanın adı.  
  
 [in] `linenumber`  
 Satır numarası burada ayırma işlemi istendi, ancak kaynak dosyasında veya NULL.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış olan bellek bloğu için bir işaretçi veya `NULL` işlemi başarısız olursa.  
  
## <a name="remarks"></a>Açıklamalar  
 `_aligned_offset_malloc_dbg` bir hata ayıklama sürümü [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı `_aligned_offset_malloc_dbg` yapılan bir çağrı için sınırlı `_aligned_offset_malloc`. Her ikisi de `_aligned_offset_malloc` ve `_aligned_offset_malloc_dbg` bir temel yığınındaki bellek bloğu tahsis ancak `_aligned_offset_malloc_dbg` birkaç hata ayıklama özellikleri sunar: kullanıcı bölümünün belirli ayırma izlemek için bir blok türü parametresi bloğunun sızıntıları için test etmek için her iki tarafında arabellekler türleri ve `filename` / `linenumber` ayırma isteklerini kökenini belirlemek için bilgi.  
  
 `_aligned_offset_malloc_dbg` İstenen biraz daha fazla alan ile bellek bloğu ayırır `size`. Ek alanı, hata ayıklama bellek blokları bağlantı ve uygulama ile hata ayıklama üst bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Blok atandığında, blok kullanıcı bölümünü 0xCD değeri ile doldurulur ve 0xFD ile doldurulmuş her üzerine yaz arabellek.  
  
 `_aligned_offset_malloc_dbg` Hizalama iç içe geçmiş bir öğede burada gerektiği durumlarda kullanışlıdır. Örneğin, hizalama iç içe bir sınıf üzerinde gerekiyorsa.  
  
 `_aligned_offset_malloc_dbg` dayanır `malloc`; daha fazla bilgi için bkz: [malloc](../../c-runtime-library/reference/malloc.md).  
  
 Bu işlev ayarlar `errno` için `ENOMEM` bellek ayırma başarısız olursa veya istenen boyutu büyük olursa `_HEAP_MAXREQ`. Hakkında daha fazla bilgi için `errno`, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, `_aligned_offset_malloc` parametrelerini doğrular. Varsa `alignment` 2'in üssü değil veya `offset` büyük veya eşit `size` ve sıfır dışında bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür `NULL` ve ayarlar `errno` için `EINVAL`.  
  
 Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).  
  
 Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_aligned_offset_malloc_dbg`|\<crtdbg.h>|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)