---
title: _CrtMemDumpStatistics | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtMemDumpStatistics
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
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
dev_langs: C++
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0d1c5192d3770a520a26bd7d9fd532f412a3e153
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics
Kullanıcı tarafından okunabilir bir biçimde (yalnızca hata ayıklama sürümü) belirtilen yığın durumu için hata ayıklama üstbilgiyi dökümünü yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _CrtMemDumpStatistics(   
   const _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `state`  
 Yığın Dökümü durumuna yönelik işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 `_CrtMemDumpStatistics` İşlevi öbeğe kullanıcı okunabilir bir form, belirtilen bir durum için hata ayıklama üst bilgileri dökümünü yapar. Döküm istatistikleri ayırmaları izlemek ve bellek sorunları algılamak için uygulama tarafından kullanılabilir. Bellek durumu belirli yığın durumu veya iki durumlu arasındaki farkı içerebilir. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar `_CrtMemDumpStatistics` ön işleme sırasında kaldırılır.  
  
 `state` Parametresi için bir işaretçi olmalıdır bir `_CrtMemState` tarafından doldurulmuştur yapısı [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) veya tarafından döndürülen [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) önce `_CrtMemDumpStatistics` olarak adlandırılır. Varsa `state` olan `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve hiçbir işlem yapılmadı. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Yığın durumu İşlevler hakkında daha fazla bilgi ve `_CrtMemState` yapısı için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|----------------------|  
|`_CrtMemDumpStatistics`|\<crtdbg.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
 **Kitaplıklar:** hata ayıklama sürümleri [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)