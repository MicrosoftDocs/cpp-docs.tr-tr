---
title: _RTC_GetErrDesc
ms.date: 11/04/2016
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
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
ms.openlocfilehash: d164626ea89bbe10f5b2ffe4224bf6381e40bab0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590313"
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
Sıfır ile bir döndürdüğü değerden daha az arasında bir sayı **_RTC_NumErrors**.

## <a name="return-value"></a>Dönüş Değeri

Çalışma zamanı hata denetimi sisteminiz tarafından algılanan hata türlerinden birini kısa bir açıklamasını içeren bir karakter dizesi. Hata sıfırdan küçük veya büyük veya eşittir tarafından döndürülen değer ise [_RTC_NumErrors](rtc-numerrors.md), **_RTC_GetErrDesc** döndürür **NULL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_GetErrDesc**|\<rtcapi.h >|

Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[_RTC_NumErrors](rtc-numerrors.md)<br/>
[Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
