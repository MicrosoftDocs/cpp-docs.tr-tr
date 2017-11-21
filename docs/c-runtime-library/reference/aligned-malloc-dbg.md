---
title: _aligned_malloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_malloc_dbg
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
- _aligned_malloc_dbg
- aligned_malloc_dbg
dev_langs: C++
helpviewer_keywords:
- aligned_malloc_dbg function
- _aligned_malloc_dbg function
ms.assetid: fb0429c3-685d-4826-9075-2515c5bdc5c6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aca23722103b75c6420ed14132d1fdac9cd097f6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="alignedmallocdbg"></a>_aligned_malloc_dbg
Hata ayıklama başlığı için belirtilen hizalama sınırında ek alan ile bellek ayırır ve arabellekler (yalnızca hata ayıklama sürümü) üzerine yazın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void * _aligned_malloc_dbg(  
    size_t size,   
    size_t alignment,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`size`  
 İstenen bellek ayırma boyutu.  
  
 [in]`alignment`  
 Hizalama değeri bir tamsayı güç 2 olmalıdır.  
  
 [in]`filename`  
 İşaretçi ayırma işlemi ya da NULL istenen kaynak dosyanın adı.  
  
 [in]`linenumber`  
 Satır numarası burada ayırma işlemi istendi, ancak kaynak dosyasında veya NULL.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış olan bellek bloğu için bir işaretçi veya `NULL` işlemi başarısız olursa.  
  
## <a name="remarks"></a>Açıklamalar  
 `_aligned_malloc_dbg`bir hata ayıklama sürümü [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı `_aligned_malloc_dbg` yapılan bir çağrı için sınırlı `_aligned_malloc`. Her ikisi de `_aligned_malloc` ve `_aligned_malloc_dbg` bir temel yığınındaki bellek bloğu tahsis ancak `_aligned_malloc_dbg` birkaç hata ayıklama özellikleri sunar: her iki tarafında sızıntıları için test etmek için blok kullanıcı kısmının arabellekleri ve `filename` / `linenumber` ayırma isteklerini kökenini belirlemek için bilgi.  
  
 `_aligned_malloc_dbg`İstenen biraz daha fazla alan ile bellek bloğu ayırır `size`. Ek alanı, hata ayıklama bellek blokları bağlantı ve uygulama ile hata ayıklama üst bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Blok atandığında, blok kullanıcı bölümünü 0xCD değeri ile doldurulur ve 0xFD ile doldurulmuş her üzerine yaz arabellek.  
  
 `_aligned_malloc_dbg`Ayarlar `errno` için `ENOMEM` bir bellek ayırma başarısız olursa veya (daha önce bahsedilen ek yük dahil) gerekli bellek miktarını aşarsa `_HEAP_MAXREQ`. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, `_aligned_malloc_dbg` parametrelerini doğrular. Varsa `alignment` 2'in üssü değil veya `size` sıfır açıklandığı gibi bu işlevi geçersiz parametre işleyicisi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür `NULL` ve ayarlar `errno` için `EINVAL`.  
  
 Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_aligned_malloc_dbg`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)