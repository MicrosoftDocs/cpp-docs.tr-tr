---
title: _aligned_free_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_free_dbg
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
- _aligned_free_dbg
- aligned_free_dbg
dev_langs: C++
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ea0dd62e2b76bef5e55fb152eecfc4c12d01fdf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="alignedfreedbg"></a>_aligned_free_dbg
İle ayrılmış bellek bloğu boşaltır [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) (yalnızca hata ayıklama).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _aligned_free_dbg(  
   void *memblock  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `memblock`  
 İçin döndürülen bellek bloğu için bir işaretçi `_aligned_malloc` veya `_aligned_offset_malloc` işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 `_aligned_free_dbg` İşlevidir bir hata ayıklama sürümü [_aligned_free](../../c-runtime-library/reference/aligned-free.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı `_aligned_free_dbg` yapılan bir çağrı için sınırlı `_aligned_free`. Her ikisi de `_aligned_free` ve `_aligned_free_dbg` bir bellek bloğu temel yığınındaki serbest ancak `_aligned_free_dbg` hata ayıklama özelliği düzenler: yetersiz bellek koşulları benzetimini yapmak için yığın 's bağlantılı listesinde boşaltılmış tutmak yeteneğini engeller.  
  
 `_aligned_free_dbg`Ücretsiz işlemi gerçekleştirmeden önce tüm belirtilen dosyaları ve blok konumları üzerinde bir geçerlilik denetimi gerçekleştirir. Uygulama bu bilgileri sağlamak için beklenmiyor. Bir bellek bloğu boşaltıldığında, hata ayıklama yığını Yöneticisi otomatik olarak kullanıcı bölümünün her iki tarafında arabellekleri bütünlüğünü denetler ve üzerine oluştu, hata raporu verir. Varsa `_CRTDBG_DELAY_FREE_MEM_DF` bit alanı [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağı ayarlanmış, boşaltılmış blok atanan değer ile 0xDD, girilir `_FREE_BLOCK` engelleme türü ve Öbek 's bağlı bellek blokları listesinde tutulur.  
  
 Bellek boşaltma içinde bir hata meydana gelirse `errno` bilgilerle hata işletim sisteminden yapısı üzerinde ayarlanır. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_aligned_free_dbg`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)