---
title: _RTC_GetErrDesc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _RTC_GetErrDesc
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
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a176aa258f805a516bf36c982ba63e531a74478
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="rtcgeterrdesc"></a>_RTC_GetErrDesc

Bir çalışma zamanı hata denetimi (RTC) türü kısa bir açıklamasını döndürür.

## <a name="syntax"></a>Sözdizimi

```C
const char * _RTC_GetErrDesc(
   _RTC_ErrorNumber errnum
);
```

### <a name="parameters"></a>Parametreler

*errnum*<br/>
Sıfır ve bir tarafından döndürülen değeri,'den arasında bir sayı **_RTC_NumErrors**.

## <a name="return-value"></a>Dönüş Değeri

Çalışma zamanı hata denetimi sistem tarafından algılanan hata türlerinden birini kısa bir açıklamasını içeren bir karakter dizesi. Hata sıfır veya daha büyük veya eşittir tarafından döndürülen değer düşükse [_RTC_NumErrors](rtc-numerrors.md), **_RTC_GetErrDesc** NULL döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_GetErrDesc**|\<rtcapi.h >|

Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[_RTC_NumErrors](rtc-numerrors.md)<br/>
[Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
