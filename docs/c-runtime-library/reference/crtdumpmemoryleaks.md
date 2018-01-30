---
title: _CrtDumpMemoryLeaks | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDumpMemoryLeaks
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
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
dev_langs:
- C++
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 859f1918afc69054b13cab161f2d7b4801bcbd78
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks
Bellek sızıntısı (yalnızca hata ayıklama sürümü) oluştuğunda dökümleri tüm bellek hata ayıklama yığınında engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
int _CrtDumpMemoryLeaks( void );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_CrtDumpMemoryLeaks`bellek sızıntısı bulunursa TRUE değerini döndürür. Aksi takdirde işlevi FALSE değerini döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_CrtDumpMemoryLeaks` İşlevi bellek sızıntısı program yürütme başladığından bu yana gerçekleşip gerçekleşmediğini belirler. Yığın içindeki tüm nesneler için hata ayıklama üst bilgileri, bir sızıntısı bulunduğunda, kullanıcı tarafından okunabilir bir biçimde edebilir. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar `_CrtDumpMemoryLeaks` ön işleme sırasında kaldırılır.  
  
 `_CrtDumpMemoryLeaks`sık sık uygulama tarafından ayrılan tüm belleği serbest olduğunu doğrulamak için program yürütme sonunda çağrılır. İşlev otomatik olarak program sonlandırmanın açarak çağrılabilir `_CRTDBG_LEAK_CHECK_DF` bit alanı [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) kullanarak bayrak [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) işlevi.  
  
 `_CrtDumpMemoryLeaks`çağrıları [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) öbek geçerli durumunu almak için değil serbest blokları durumu tarar. Serbest bırakılmamış blok karşılaşıldığında, `_CrtDumpMemoryLeaks` çağrıları [_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) program yürütme başlangıcı yığınından ayrılan tüm nesneleri için döküm bilgi.  
  
 Varsayılan olarak, iç C çalışma zamanı blokları (`_CRT_BLOCK`) bellek dökümü işlemlerinde dahil edilmez. [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) işlevi,'nı açmak için kullanılabilir `_CRTDBG_CHECK_CRT_DF` , bit `_crtDbgFlag` sızıntısı algılama işleminde bu blokları içerecek şekilde.  
  
 Yığın durumu İşlevler hakkında daha fazla bilgi ve `_CrtMemState` yapısı için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_CrtDumpMemoryLeaks`|\<crtdbg.h>|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="example"></a>Örnek  
 Nasıl kullanılacağına ilişkin bir örnek için `_CrtDumpMemoryLeaks`, bkz: [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)