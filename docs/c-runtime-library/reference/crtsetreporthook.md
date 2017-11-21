---
title: _CrtSetReportHook | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetReportHook
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
- _CrtSetReportHook
- CrtSetReportHook
dev_langs: C++
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7742b9f26c2eaffada242b7a0322fd0d2a426c0a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="crtsetreporthook"></a>_CrtSetReportHook
C çalışma zamanı hata ayıklama raporlama işlemine (yalnızca hata ayıklama sürümü) takma tarafından istemci tanımlı raporlama işlevi yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_CRT_REPORT_HOOK _CrtSetReportHook(   
   _CRT_REPORT_HOOK reportHook   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `reportHook`  
 C çalışma zamanı kanca için yeni istemci tanımlı Raporlama işlevini raporlama işlemi hata ayıklama.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Önceki istemci tanımlı raporlama işlevi döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_CrtSetReportHook`işlem raporlama C çalışma zamanı hata ayıklama kitaplığa Raporlama işlevini kullanmak bir uygulama sağlar. Sonuç olarak, her [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) çağrılır hata ayıklama rapor oluşturmak için uygulama işlevi ilk kez çağrıldığında raporlama kullanıcının. Bir uygulamanın odaklanmak belirli ayırma türlerinde veya kullanarak hedeflere kullanılamaz bir raporu göndermek için hata ayıklama raporları filtreleme gibi işlemler gerçekleştirmek için bu işlevi etkinleştirir `_CrtDbgReport`. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar `_CrtSetReportHook` ön işleme sırasında kaldırılır.  
  
 Daha güçlü bir sürümü için `_CrtSetReportHook`, bkz: [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md).  
  
 `_CrtSetReportHook` İşlevi yükler yeni istemci tanımlı raporlama belirtilen işlevi `reportHook` ve önceki istemci tanımlı kanca döndürür. Aşağıdaki örnek, bir istemci tarafından tanımlanan rapor kancası nasıl örneklenmiş olmalıdır gösterir:  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 Burada `reportType` hata ayıklama rapor türü (`_CRT_WARN`, `_CRT_ERROR`, veya `_CRT_ASSERT`), `message` rapora dahil edilmek üzere tam olarak birleştirilmiş hata ayıklama kullanıcı iletisi ve `returnValue` istemci tanımlı tarafından belirtilen değeri Raporlama tarafından döndürülmelidir işlevi `_CrtDbgReport`. Kullanılabilir rapor türleri tam bir açıklaması için bkz: [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) işlevi.  
  
 Başka bir raporlama yok gerekli olacak şekilde, istemci tarafından tanımlanan raporlama işlevi tamamen hata ayıklama iletisi işliyorsa, ardından işlevi döndürmelidir `TRUE`. İşlevi döndüğünde `FALSE`, `_CrtDbgReport` rapor türü, modu ve dosya için geçerli ayarları kullanarak hata ayıklama raporu oluşturmak için çağrılır. Belirterek ek olarak, `_CrtDbgReport` dönüş değeri `returnValue`, uygulamanın, ayrıca bir hata ayıklama kesme oluşup oluşmadığını denetleyebilir. Hata ayıklama raporun nasıl yapılandırılan ve oluşturulan tam bir açıklaması için bkz: `_CrtSetReportMode`, [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md), ve `_CrtDbgReport`.  
  
 Kanca özellikli diğer çalışma zamanı işlevleri ve kendi istemci tarafından tanımlanan yazma hakkında daha fazla bilgi için kanca işlevleri, bkz: [hata ayıklama kanca işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).  
  
> [!NOTE]
>  Uygulamanız ile derlenmiş ise `/clr` ve uygulama çıkıldıktan sonra Raporlama işlevi ana çağrılır, Raporlama işlevini herhangi CRT işlevleri çağırırsa CLR bir özel durum oluşturur.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_CrtSetReportHook`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)   
 [_CrtGetReportHook](../../c-runtime-library/reference/crtgetreporthook.md)