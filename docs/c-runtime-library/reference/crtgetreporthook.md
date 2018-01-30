---
title: _CrtGetReportHook | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtGetReportHook
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
- CrtGetReportHook
- _CrtGetReportHook
dev_langs:
- C++
helpviewer_keywords:
- CrtGetReportHook function
- _CrtGetReportHook function
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94b92ee2bc6f30df99db23cb1417f1e490d24fa5
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="crtgetreporthook"></a>_CrtGetReportHook
Çalışma zamanı hata ayıklama işlemi (yalnızca hata ayıklama sürümü) raporlaması için C içine takma için istemci tanımlı raporlama işlevi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_CRT_REPORT_HOOK _CrtGetReportHook( void );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli istemci tanımlı raporlama işlevi döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_CrtGetReportHook`Geçerli raporlama işlevi işlem raporlama C çalışma zamanı hata ayıklama kitaplığı için alınacak bir uygulama sağlar.  
  
 Kanca özellikli diğer çalışma zamanı işlevleri ve kendi istemci tarafından tanımlanan yazma hakkında daha fazla bilgi için kanca işlevleri, bkz: [hata ayıklama kanca işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_CrtGetReportHook`|\<crtdbg.h>|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="example"></a>Örnek  
 Nasıl kullanılacağına ilişkin bir örnek için `_CrtSetReportHook`, bkz: [rapor](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/report).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md)