---
title: _RTC_NumErrors
ms.date: 11/04/2016
apiname:
- _RTC_NumErrors
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
- _RTC_NumErrors
- RTC_NumErrors
helpviewer_keywords:
- run-time errors
- _RTC_NumErrors function
- RTC_NumErrors function
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
ms.openlocfilehash: e13f85f2140473d6e971d27abb6012effd36c37c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477200"
---
# <a name="rtcnumerrors"></a>_RTC_NumErrors

Çalışma zamanı hata denetimleri (RTC) tarafından algılanabilir hatalarının toplam sayısını döndürür. Bu sayı denetimi olarak kullanabileceğiniz bir **için** döngü, burada her bir döngü değeri geçirilir [_RTC_GetErrDesc](rtc-geterrdesc.md).

## <a name="syntax"></a>Sözdizimi

```C

int _RTC_NumErrors( void );

```

## <a name="return-value"></a>Dönüş Değeri

Bir tamsayı değeri tarafından Visual C++ çalışma zamanı hata denetimleri algılanabilir hatalarının toplam sayısını temsil eder.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_NumErrors**|\<rtcapi.h >|

Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
