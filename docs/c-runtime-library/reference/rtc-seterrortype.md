---
title: _RTC_SetErrorType
ms.date: 11/04/2016
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
helpviewer_keywords:
- run-time errors
- RTC_SetErrorType function
- _RTC_SetErrorType function
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
ms.openlocfilehash: 022079bd199477c8bca92e853ed66879c96428db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357141"
---
# <a name="rtcseterrortype"></a>_RTC_SetErrorType

Bir tür ile çalışma zamanı hata denetimleri (RTCs) tarafından algılanan bir hata ilişkilendirir. Hata işleyicinizi hata belirtilen türe ait çıktı nasıl işler.

## <a name="syntax"></a>Sözdizimi

```C
int _RTC_SetErrorType(
   _RTC_ErrorNumber errnum,
   int ErrType
);
```

### <a name="parameters"></a>Parametreler

*errnum*<br/>
Sıfır ile bir döndürdüğü değerden daha az arasında bir sayı [_RTC_NumErrors](rtc-numerrors.md).

*ErrType*<br/>
Bu atama için bir değer *errnum*. Örneğin, kullanabileceğinize **_CRT_ERROR**. Kullanıyorsanız **_CrtDbgReport** işleyicinizi hata olarak *ErrType* yalnızca tanımlanmış semboller biri olabilir [_CrtSetReportMode](crtsetreportmode.md). Kendi hata işleyicisi varsa ([_RTC_SetErrorFunc](rtc-seterrorfunc.md)), kadar olabilir *ErrType*orada olarak s *errnum*s.

Bir *ErrType* _RTC_ERRTYPE_IGNORE özel anlamı **_CrtSetReportMode**; hata yoksayıldı.

## <a name="return-value"></a>Dönüş Değeri

Hata türü için önceki değer *türü*.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tüm hataları kümesine *ErrType* = 1, karşılık gelen **_CRT_ERROR**. Varsayılan hata hakkında daha fazla bilgi türleri gibi **_CRT_ERROR**, bkz: [_CrtDbgReport](crtdbgreport-crtdbgreportw.md).

Bu işlev çağrı yapmadan önce ilk çalışma zamanı hata denetimi başlatma işlevlerden birini çağırmanız gerekir; bkz: [kullanarak çalışma zamanı denetimleri olmadan C çalışma zamanı kitaplığı](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_SetErrorType**|\<rtcapi.h >|

Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
