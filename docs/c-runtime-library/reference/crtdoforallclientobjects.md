---
title: _CrtDoForAllClientObjects | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtDoForAllClientObjects
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
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
dev_langs: C++
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a5f48fd19e4170ede161935ea39197741586b66e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects
Bir uygulama tarafından sağlanan işlev için tüm çağrılar `_CLIENT_BLOCK` (yalnızca hata ayıklama sürümü) yığınındaki türler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _CrtDoForAllClientObjects(   
   void ( * pfn )( void *, void * ),  
   void *context  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pfn`  
 Uygulama tarafından sağlanan işlev geri çağırma işlevi işaretçisi. Bu işlevi ilk parametresi verileri işaret eder. İkinci parametre çağrısına iletilen bağlam işaretçidir `_CrtDoForAllClientObjects`.  
  
 `context`  
 Uygulama tarafından sağlanan bağlamı uygulama tarafından sağlanan işleve yönelik işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 `_CrtDoForAllClientObjects` İşlevi arar öbek 's bağlantılı ile bellek blokları istemcinize `_CLIENT_BLOCK` türü ve çağrıları bu tür bir blok olduğunda uygulama tarafından sağlanan işlev bulundu. Bulunan blok ve `context` parametresi için uygulama tarafından sağlanan işlev bağımsız değişkenleri olarak geçirilir. Hata ayıklama sırasında bir uygulama belirli bir grup ayırmalarının açıkça debug belleği ayırmaya yığın işlevleri çağırma ve blokları atanması belirterek izleyebilirsiniz `_CLIENT_BLOCK` engelleme türü. Bu blokları ayrı olarak izlenir ve farklı sızıntısı algılama ve bellek durumu Raporlama sırasında bildirilir.  
  
 Varsa `_CRTDBG_ALLOC_MEM_DF` bit alanı [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağı açık değilse, `_CrtDoForAllClientObjects` hemen döndürür. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar `_CrtDoForAllClientObjects` ön işleme sırasında kaldırılır.  
  
 Hakkında daha fazla bilgi için `_CLIENT_BLOCK` yazın ve diğer hata ayıklama işlevleri tarafından kullanılan bkz [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).  
  
 Varsa `pfn` olan `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ayarlanır `EINVAL` ve işlevi döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_CrtDoForAllClientObjects`|\<crtdbg.h >, \<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
 **Kitaplıklar:** Debug Evrensel C çalışma zamanı kitaplıkları yalnızca sürümleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)   
 [Yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)