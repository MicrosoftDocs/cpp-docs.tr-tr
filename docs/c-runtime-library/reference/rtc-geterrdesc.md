---
description: 'Hakkında daha fazla bilgi edinin: _RTC_GetErrDesc'
title: _RTC_GetErrDesc
ms.date: 11/04/2016
api_name:
- _RTC_GetErrDesc
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- RTC_GetErrDesc
- _RTC_GetErrDesc
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
ms.openlocfilehash: 5e9beccec5e13d6c2c00e3edaefec695a8e16737
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168728"
---
# <a name="_rtc_geterrdesc"></a>_RTC_GetErrDesc

Çalışma zamanı hata denetimi (RTC) türünün kısa bir açıklamasını döndürür.

## <a name="syntax"></a>Sözdizimi

```C
const char * _RTC_GetErrDesc(
   _RTC_ErrorNumber errnum
);
```

### <a name="parameters"></a>Parametreler

*errnum*<br/>
Sıfır ve **_RTC_NumErrors** tarafından döndürülen değerden küçük bir sayı.

## <a name="return-value"></a>Dönüş Değeri

Çalışma zamanı hata denetimi sistemi tarafından algılanan hata türlerinden birinin kısa bir açıklamasını içeren bir karakter dizesi. Hata sıfırdan küçükse veya [_RTC_NumErrors](rtc-numerrors.md)tarafından döndürülen değerden büyük veya ona eşitse, **_RTC_GetErrDesc** **null** döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_GetErrDesc**|\<rtcapi.h>|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[_RTC_NumErrors](rtc-numerrors.md)<br/>
[Çalışma zamanı hata denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
