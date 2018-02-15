---
title: _CrtMemDifference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtMemDifference
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
- _CrtMemDifference
- CrtMemDifference
dev_langs:
- C++
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 68d0aa43167e9c4641851927bd56819e384fed4d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="crtmemdifference"></a>_CrtMemDifference
Karşılaştırır iki bellek durumları ve farklılıkları (yalnızca hata ayıklama sürümü) döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _CrtMemDifference(   
   _CrtMemState *stateDiff,  
   const _CrtMemState *oldState,  
   const _CrtMemState *newState   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stateDiff`  
 İşaretçi bir `_CrtMemState` (döndürülen) iki bellek durumları arasındaki farklar depolamak için kullanılan yapısı.  
  
 `oldState`  
 Önceki bir bellek durumu işaretçisine (`_CrtMemState` yapısı).  
  
 `newState`  
 Bir sonraki bellek durumu işaretçisine (`_CrtMemState` yapısı).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bellek önemli ölçüde farklı belirtiliyorsa `_CrtMemDifference` TRUE değerini döndürür. Aksi takdirde işlevi FALSE değerini döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_CrtMemDifference` İşlev karşılaştırır `oldState` ve `newState` ve bunların farklılıkları depolar `stateDiff`, hangi sonra uygulama tarafından bellek sızıntıları ve diğer bellek sorunlarını algılamak için kullanılabilir. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar `_CrtMemDifference` ön işleme sırasında kaldırılır.  
  
 `newState` ve `oldState` her için geçerli bir işaretçi olmalıdır bir `_CrtMemState` tarafından doldurulmuştur Crtdbg.h, tanımlanan yapısı [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) çağırmadan önce `_CrtMemDifference`. `stateDiff` önceden ayrılmış bir örneğini gösteren bir işaretçi olmalıdır `_CrtMemState` yapısı. Varsa `stateDiff`, `newState`, veya `oldState` olan `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ayarlanır `EINVAL` işlevi FALSE değerini döndürür.  
  
 `_CrtMemDifference` karşılaştırır `_CrtMemState` alan bloklarında değerlerini `oldState` de için `newState` ve sonuçta depolar `stateDiff`. Blok türleri sayısı, ayrılan veya her tür için ayrılan bloğu toplam sayısı iki bellek durumlar arasında farklılık gösterir, durumları önemli ölçüde farklı olduğu söylenir. İki durumlu de depolanmış şimdiye kadar aynı anda iki durumlu ve toplam ayırmaları arasındaki fark için ayrılan en büyük miktar arasındaki farkı `stateDiff`.  
  
 Varsayılan olarak, iç C çalışma zamanı blokları (`_CRT_BLOCK`) bellek durumu işlemlerinde dahil edilmez. [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) işlevi,'nı açmak için kullanılabilir `_CRTDBG_CHECK_CRT_DF` , bit `_crtDbgFlag` bu blokları sızıntısı algılama ve diğer bellek durumu işlemleri dahil edilecek. Bellek blokları serbest (`_FREE_BLOCK`) neden olmaz `_CrtMemDifference` TRUE döndürmek için.  
  
 Yığın durumu İşlevler hakkında daha fazla bilgi ve `_CrtMemState` yapısı için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_CrtMemDifference`|\<crtdbg.h>|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
 **Kitaplıklar:** hata ayıklama sürümleri [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)