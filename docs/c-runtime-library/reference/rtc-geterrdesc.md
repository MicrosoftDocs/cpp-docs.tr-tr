---
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
ms.openlocfilehash: 7174e9242b77a904df817886df4f8c763e3e0b2c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949051"
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
Sıfır ve **_RTC_NumErrors**tarafından döndürülen değerden küçük bir sayı.

## <a name="return-value"></a>Dönüş Değeri

Çalışma zamanı hata denetimi sistemi tarafından algılanan hata türlerinden birinin kısa bir açıklamasını içeren bir karakter dizesi. Hata sıfırdan küçükse veya [_RTC_NumErrors](rtc-numerrors.md)tarafından döndürülen değerden büyükse veya eşitse, **_RTC_GetErrDesc** **null**döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_GetErrDesc**|\<rtcapı. h >|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[_RTC_NumErrors](rtc-numerrors.md)<br/>
[Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
