---
title: _RTC_SetErrorFunc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _RTC_SetErrorFunc
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
- RTC_SetErrorFunc
- _RTC_SetErrorFunc
dev_langs: C++
helpviewer_keywords:
- RTC_SetErrorFunc function
- _RTC_SetErrorFunc function
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: de71b832af9e6ed2f734f193e49a7c240193edce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="rtcseterrorfunc"></a>_RTC_SetErrorFunc
Çalışma zamanı hata denetimleri (RTCs) raporlama için işleyici olarak bir işlev belirler. Bu işlev kullanım dışıdır; kullanmak `_RTC_SetErrorFuncW` yerine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      _RTC_error_fn _RTC_SetErrorFunc(  
   _RTC_error_fn function   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *işlevi*  
 Çalışma zamanı hata denetimleri işleyecek işlevi adresi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Önceden tanımlanmış hata işlev. Önceden tanımlanmış bir işlev ise NULL döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev kullanmayın; Bunun yerine, kullanın `_RTC_SetErrorFuncW`. Yalnızca geriye dönük uyumluluk için tutulmaktadır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_RTC_SetErrorFunc`|\<rtcapi.h >|  
  
 Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)