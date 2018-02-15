---
title: _free_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _free_dbg
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
- _free_dbg
- free_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa3df169a968313d2a29fbf9c08643748d3196d8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="freedbg"></a>_free_dbg
Bellek (yalnızca hata ayıklama sürümü) yığınındaki bloğunu boşaltır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _free_dbg(   
   void *userData,  
   int blockType   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `userData`  
 İşaretçi boşaltılması için ayrılmış bellek bloğuna.  
  
 `blockType`  
 Boşaltılması için ayrılmış bellek bloğu türü: `_CLIENT_BLOCK`, `_NORMAL_BLOCK`, veya `_IGNORE_BLOCK`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_free_dbg` İşlevidir bir hata ayıklama sürümü [ücretsiz](../../c-runtime-library/reference/free.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı `_free_dbg` yapılan bir çağrı için sınırlı `free`. Her ikisi de `free` ve `_free_dbg` bir bellek bloğu temel yığınındaki serbest ancak `_free_dbg` iki hata ayıklama özelliği düzenler: yetersiz bellek koşulları ve boşaltmak için bir blok türü parametresi benzetimini yapmak için yığın 's bağlantılı listesinde boşaltılmış tutmak yeteneğini engeller belirli ayırma türleri.  
  
 `_free_dbg` Ücretsiz işlemi gerçekleştirmeden önce tüm belirtilen dosyaları ve blok konumları üzerinde bir geçerlilik denetimi gerçekleştirir. Uygulama bu bilgileri sağlamak için beklenmiyor. Bir bellek bloğu boşaltıldığında, hata ayıklama yığını Yöneticisi otomatik olarak kullanıcı bölümünün her iki tarafında arabellekleri bütünlüğünü denetler ve üzerine oluştu, hata raporu verir. Varsa `_CRTDBG_DELAY_FREE_MEM_DF` bit alanı [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağı ayarlanmış, boşaltılmış blok atanan değer ile 0xDD, girilir `_FREE_BLOCK` engelleme türü ve Öbek 's bağlı bellek blokları listesinde tutulur.  
  
 Bellek boşaltma içinde bir hata meydana gelirse `errno` bilgilerle hata işletim sisteminden yapısı üzerinde ayarlanır. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_free_dbg`|\<crtdbg.h>|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Nasıl kullanılacağına ilişkin bir örnek için `_free_dbg`, bkz: [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)