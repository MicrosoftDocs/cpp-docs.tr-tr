---
title: _RTC_SetErrorFunc
ms.date: 11/04/2016
api_name:
- _RTC_SetErrorFunc
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
- RTC_SetErrorFunc
- _RTC_SetErrorFunc
helpviewer_keywords:
- RTC_SetErrorFunc function
- _RTC_SetErrorFunc function
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
ms.openlocfilehash: 6b173dd9af9fe11146341468c44a0abc10ce90bc
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949022"
---
# <a name="_rtc_seterrorfunc"></a>_RTC_SetErrorFunc

Çalışma zamanı hata denetimleri (RTCs) için işleyici olarak bir işlevi belirtir. Bu işlev kullanım dışıdır; Bunun yerine **_RTC_SetErrorFuncW** kullanın.

## <a name="syntax"></a>Sözdizimi

```C
_RTC_error_fn _RTC_SetErrorFunc(
   _RTC_error_fn function
);
```

### <a name="parameters"></a>Parametreler

*çalışmayacaktır*<br/>
Çalışma zamanı hata denetimlerini işleyecek işlevin adresi.

## <a name="return-value"></a>Dönüş Değeri

Daha önce tanımlanan hata işlevi. Önceden tanımlanmış bir işlev yoksa, **null**değerini döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevi kullanmayın; Bunun yerine, **_RTC_SetErrorFuncW**kullanın. Yalnızca geriye dönük uyumluluk için korunur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_SetErrorFunc**|\<rtcapı. h >|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
