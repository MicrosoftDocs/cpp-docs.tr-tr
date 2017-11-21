---
title: _RTC_GetErrDesc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _RTC_GetErrDesc
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
- RTC_GetErrDesc
- _RTC_GetErrDesc
dev_langs: C++
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 792407af9497148bea95333ee18028e0f8c953e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="rtcgeterrdesc"></a>_RTC_GetErrDesc
Bir çalışma zamanı hata denetimi (RTC) türü kısa bir açıklamasını döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      const char * _RTC_GetErrDesc(  
   _RTC_ErrorNumber errnum   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *errnum*  
 Sıfır ve bir tarafından döndürülen değeri,'den arasında bir sayı `_RTC_NumErrors`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Çalışma zamanı hata denetimi sistem tarafından algılanan hata türlerinden birini kısa bir açıklamasını içeren bir karakter dizesi. Hata sıfır veya daha büyük veya eşittir tarafından döndürülen değer düşükse [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md), `_RTC_GetErrDesc` NULL döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_RTC_GetErrDesc`|\<rtcapi.h >|  
  
 Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)   
 [Çalışma zamanı hata denetimi](../../c-runtime-library/run-time-error-checking.md)