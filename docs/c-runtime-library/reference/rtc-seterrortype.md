---
description: 'Hakkında daha fazla bilgi edinin: _RTC_SetErrorType'
title: _RTC_SetErrorType
ms.date: 11/04/2016
api_name:
- _RTC_SetErrorType
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
- RTC_SetErrorType
- _RTC_SetErrorType
helpviewer_keywords:
- run-time errors
- RTC_SetErrorType function
- _RTC_SetErrorType function
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
ms.openlocfilehash: 8b0b28eaf97a27dbfcf4dcb414c9a17f03df7f9e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168702"
---
# <a name="_rtc_seterrortype"></a>_RTC_SetErrorType

Çalışma zamanı hata denetimleri (RTCs) tarafından algılanan bir hatayı bir tür ile ilişkilendirir. Hata işleyiciniz, belirtilen türdeki hataların nasıl çıkış yapılacağını işler.

## <a name="syntax"></a>Sözdizimi

```C
int _RTC_SetErrorType(
   _RTC_ErrorNumber errnum,
   int ErrType
);
```

### <a name="parameters"></a>Parametreler

*errnum*<br/>
Sıfır ve [_RTC_NumErrors](rtc-numerrors.md)tarafından döndürülen değerden küçük bir sayı.

*ErrType*<br/>
Bu *errnum* öğesine atanacak değer. Örneğin, **_CRT_ERROR** kullanabilirsiniz. Hata işleyiciniz olarak **_CrtDbgReport** kullanıyorsanız *errtype* , [_CrtSetReportMode](crtsetreportmode.md)tanımlı simgelerden yalnızca biri olabilir. Kendi hata işleyiciniz ([_RTC_SetErrorFunc](rtc-seterrorfunc.md)) varsa, *errnum*'lar olduğu Için çok sayıda *ErrType* olabilir.

*ErrType* _RTC_ERRTYPE_IGNORE **_CrtSetReportMode** için özel anlamı vardır; Hata yoksayıldı.

## <a name="return-value"></a>Dönüş Değeri

Hata türü *türü* için önceki değer.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tüm hatalar **_CRT_ERROR** karşılık gelen *ErrType* = 1 olarak ayarlanır. **_CRT_ERROR** gibi varsayılan hata türleri hakkında daha fazla bilgi için bkz. [_CrtDbgReport](crtdbgreport-crtdbgreportw.md).

Bu işlevi çağırabilmeniz için önce çalışma zamanı hata denetimi başlatma işlevlerinden birini çağırmanız gerekir; bkz [. C Run-Time kitaplığı olmadan Run-Time denetimleri kullanma](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_SetErrorType**|\<rtcapi.h>|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Çalışma zamanı hata denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
