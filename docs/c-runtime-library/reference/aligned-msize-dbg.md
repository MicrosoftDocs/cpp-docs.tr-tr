---
title: _aligned_msize_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_msize_dbg
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
f1_keywords: _aligned_msize_dbg
dev_langs: C++
helpviewer_keywords: _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c278f9b9860026b3cd097b49cdce691d353e6f50
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="alignedmsizedbg"></a>_aligned_msize_dbg
Yığın (yalnızca hata ayıklama sürümü) ayrılan bellek bloğu boyutu döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t _aligned_msize_dbg(  
   void *memblock,  
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`memblock`  
 Bellek bloğu işaretçi.  
  
 [in]`alignment`  
 Hizalama değeri bir tamsayı güç 2 olmalıdır.  
  
 [in]`offset`  
 Hizalama zorlamak için bellek ayırma içine uzaklığı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Boyutu (bayt) imzalanmamış tamsayı olarak döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `alignment` Ve `offset` değerleri blok ayrılan işleve değerleri aynı olmalıdır.  
  
 `_aligned_msize_dbg`bir hata ayıklama sürümü [_aligned_msize](../../c-runtime-library/reference/aligned-msize.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı `_aligned_msize_dbg` yapılan bir çağrı için sınırlı `_aligned_msize`. Her ikisi de `_aligned_msize` ve `_aligned_msize_dbg` bir bellek bloğu içinde temel öbek boyutunu hesaplamak ancak `_aligned_msize_dbg` hata ayıklama özelliği ekler: döndürülen boyutunda bellek bloğu kullanıcı kısmının her iki tarafında arabellekleri içerir.  
  
 Bu işlev, parametre doğrular. Varsa `memblock` null işaretçi veya `alignment` 2 ' nin güç değil `_msize` açıklandığı gibi bir geçersiz parametre işleyiciyi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Hata işleniyorsa işlevi ayarlar `errno` için `EINVAL` ve -1 döndürür.  
  
 Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_aligned_msize_dbg`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../../c-runtime-library/memory-allocation.md)