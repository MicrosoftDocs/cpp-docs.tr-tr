---
title: _RTC_SetErrorFuncW | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _RTC_SetErrorFuncW
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
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
dev_langs: C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b3285e266091a902373f0bfd7b70b9c1123c19f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="rtcseterrorfuncw"></a>_RTC_SetErrorFuncW
Çalışma zamanı hata denetimleri (RTCs) raporlaması için işleyici olarak bir işlev belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      _RTC_error_fnW _RTC_SetErrorFuncW(  
   _RTC_error_fnW function   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `function`  
 Çalışma zamanı hata denetimleri işleyecek işlevi adresi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Önceden tanımlanmış hata işlevi; veya `NULL` önceden tanımlanmış bir işlev ise.  
  
## <a name="remarks"></a>Açıklamalar  
 Yeni kod içinde yalnızca kullanmak `_RTC_SetErrorFuncW`. `_RTC_SetErrorFunc`yalnızca geriye dönük uyumluluk için kitaplığında dahil edilir.  
  
 `_RTC_SetErrorFuncW` Geri çağırma uygular, bağlı bileşenine ancak genel olarak değil.  
  
 Emin olmak için geçirdiğiniz adresi `_RTC_SetErrorFuncW` geçerli hata işlevi işleme olan.  
  
 Hata -1 türünü kullanarak atanmış olan varsa [_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md), hata işlevi işleme çağrılmaz.  
  
 Bu işlev aramadan önce ilk çalışma zamanı hata denetimi başlatma işlevlerinden birini çağırmanız gerekir. Daha fazla bilgi için bkz: [kullanarak çalışma zamanı denetler olmadan C çalışma zamanı kitaplığı](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).  
  
 **_RTC_error_fnW** şu şekilde tanımlanır:  
  
 **TypeDef int (__cdecl \*_RTC_error_fnW) (int** `errorType` **, const wchar_t \***  *filename* **, int** *linenumber* **, const wchar_t \***  `moduleName` **, const wchar_t \***  *biçimi* **, ...);**   
  
 burada:  
  
 `errorType`  
 Tarafından belirtilen hata türü [_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md).  
  
 *Dosya adı*  
 Hatanın oluştuğu kaynak dosyası ya da hiç hata ayıklama bilgileri kullanılabiliyorsa, null.  
  
 *LineNumber*  
 Satırda *filename* hatanın oluştuğu ya da 0 hata ayıklama bilgisi yok.  
  
 `moduleName`  
 DLL veya hatanın oluştuğu yürütülebilir dosya adı.  
  
 *biçimi*  
 printf stili kalan parametrelerini kullanarak bir hata iletisi görüntülenecek dize. VA_ARGLIST ilk bağımsız değişkeni oluşan RTC hata sayısıdır.  
  
 Nasıl kullanılacağını gösteren bir örnek için **_RTC_error_fnW**, bkz: [yerel çalışma zamanı denetler özelleştirme](/visualstudio/debugger/native-run-time-checks-customization).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_RTC_SetErrorFuncW`|\<rtcapi.h >|  
  
 Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Çalışma zamanı hata denetimi](../../c-runtime-library/run-time-error-checking.md)