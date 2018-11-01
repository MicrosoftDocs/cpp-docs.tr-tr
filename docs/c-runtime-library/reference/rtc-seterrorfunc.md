---
title: _RTC_SetErrorFunc
ms.date: 11/04/2016
apiname:
- _RTC_SetErrorFunc
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
helpviewer_keywords:
- RTC_SetErrorFunc function
- _RTC_SetErrorFunc function
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
ms.openlocfilehash: 6b292d685eea8eccb9e9b2a3c3e6cd903d501005
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514744"
---
# <a name="rtcseterrorfunc"></a>_RTC_SetErrorFunc

Çalışma zamanı hata denetimleri (RTCs) raporlaması için işleyici olarak bir işlevi belirtir. Bu işlev kullanım dışı; kullanma **_RTC_SetErrorFuncW** yerine.

## <a name="syntax"></a>Sözdizimi

```C
_RTC_error_fn _RTC_SetErrorFunc(
   _RTC_error_fn function
);
```

### <a name="parameters"></a>Parametreler

*İşlevi*<br/>
Çalışma zamanı hata denetimlerini işleyecek işlevin adresi.

## <a name="return-value"></a>Dönüş Değeri

Önceden tanımlanmış hata işlev. Önceden tanımlanmış bir işlev ise döndürür **NULL**.

## <a name="remarks"></a>Açıklamalar

Bu işlev kullanmayın; Bunun yerine, **_RTC_SetErrorFuncW**. Bu yalnızca geriye dönük uyumluluk için tutulmaktadır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_SetErrorFunc**|\<rtcapi.h >|

Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
