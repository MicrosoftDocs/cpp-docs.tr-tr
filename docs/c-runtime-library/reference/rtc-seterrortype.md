---
title: _RTC_SetErrorType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _RTC_SetErrorType
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
- RTC_SetErrorType
- _RTC_SetErrorType
dev_langs: C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorType function
- _RTC_SetErrorType function
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c89c5adba9224c11f8d5ec77e13b06a8cea4d0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="rtcseterrortype"></a>_RTC_SetErrorType
Bir türüyle çalışma zamanı hata denetimleri (RTCs) tarafından algılanan hata ilişkilendirir. Hata işleyicinizi hataları belirtilen türe ait çıktı nasıl işler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int _RTC_SetErrorType(  
   _RTC_ErrorNumber errnum,  
   int ErrType   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *errnum*  
 Sıfır ve bir tarafından döndürülen değeri,'den arasında bir sayı [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md).  
  
 *ErrType*  
 Bu atama için bir değer *errnum*. Örneğin, kullanabilirsiniz **_CRT_ERROR**. Kullanıyorsanız `_CrtDbgReport` hata işleyicinizi olarak *ErrType* yalnızca biri tanımlanmış semboller olabilir [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md). Kendi hata işleyicisine varsa ([_RTC_SetErrorFunc](../../c-runtime-library/reference/rtc-seterrorfunc.md)), kadar olabilir *ErrType*orada olarak s *errnum*s.  
  
 Bir *ErrType* _RTC_ERRTYPE_IGNORE özel bir anlamı olan `_CrtSetReportMode`; hatayı göz ardı edilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Hata türü için önceki değeri `type`.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, tüm hataları ayarlamak *ErrType* karşılık gelen 1 = **_CRT_ERROR**. Varsayılan hata hakkında daha fazla bilgi türleri gibi **_CRT_ERROR**, bkz: [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).  
  
 Bu işlev çağrısı önce çalışma zamanı hata denetimi başlatma işlevlerinden birini ilk çağırmalısınız; bkz: [C çalışma zamanı kitaplığı olmadan kullanarak çalışma zamanı denetler](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_RTC_SetErrorType`|\<rtcapi.h >|  
  
 Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_RTC_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)