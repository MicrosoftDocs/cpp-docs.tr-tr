---
title: _RTC_SetErrorType | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _RTC_SetErrorType
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
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorType function
- _RTC_SetErrorType function
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9fcca983247f0f5e0c09899e7ebec2774ca92e6
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="rtcseterrortype"></a>_RTC_SetErrorType

Bir türüyle çalışma zamanı hata denetimleri (RTCs) tarafından algılanan hata ilişkilendirir. Hata işleyicinizi hataları belirtilen türe ait çıktı nasıl işler.

## <a name="syntax"></a>Sözdizimi

```C
int _RTC_SetErrorType(
   _RTC_ErrorNumber errnum,
   int ErrType
);
```

### <a name="parameters"></a>Parametreler

*errnum*<br/>
Sıfır ve bir tarafından döndürülen değeri,'den arasında bir sayı [_RTC_NumErrors](rtc-numerrors.md).

*ErrType*<br/>
Bu atama için bir değer *errnum*. Örneğin, kullanabilirsiniz **_CRT_ERROR**. Kullanıyorsanız **_CrtDbgReport** hata işleyicinizi olarak *ErrType* yalnızca biri tanımlanmış semboller olabilir [_CrtSetReportMode](crtsetreportmode.md). Kendi hata işleyicisine varsa ([_RTC_SetErrorFunc](rtc-seterrorfunc.md)), kadar olabilir *ErrType*orada olarak s *errnum*s.

Bir *ErrType* _RTC_ERRTYPE_IGNORE özel bir anlamı olan **_CrtSetReportMode**; hatayı göz ardı edilir.

## <a name="return-value"></a>Dönüş Değeri

Hata türü için önceki değeri *türü*.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tüm hataları ayarlamak *ErrType* karşılık gelen 1 = **_CRT_ERROR**. Varsayılan hata hakkında daha fazla bilgi türleri gibi **_CRT_ERROR**, bkz: [_CrtDbgReport](crtdbgreport-crtdbgreportw.md).

Bu işlev çağrısı önce çalışma zamanı hata denetimi başlatma işlevlerinden birini ilk çağırmalısınız; bkz: [C çalışma zamanı kitaplığı olmadan kullanarak çalışma zamanı denetler](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_SetErrorType**|\<rtcapi.h >|

Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
