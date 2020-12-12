---
description: 'Hakkında daha fazla bilgi edinin: _RTC_NumErrors'
title: _RTC_NumErrors
ms.date: 11/04/2016
api_name:
- _RTC_NumErrors
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
- _RTC_NumErrors
- RTC_NumErrors
helpviewer_keywords:
- run-time errors
- _RTC_NumErrors function
- RTC_NumErrors function
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
ms.openlocfilehash: df103f5aada8c896669b82abc1b65621597acf1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168715"
---
# <a name="_rtc_numerrors"></a>_RTC_NumErrors

Çalışma zamanı hata denetimleri (RTC) tarafından tespit edilebilir toplam hata sayısını döndürür. Bu numarayı döngüde **`for`** her bir değerin [_RTC_GetErrDesc](rtc-geterrdesc.md)geçirildiği bir döngüdeki denetim olarak kullanabilirsiniz.

## <a name="syntax"></a>Syntax

```C

int _RTC_NumErrors( void );
```

## <a name="return-value"></a>Dönüş Değeri

Değeri, Visual C++ çalışma zamanı hata denetimleri tarafından tespit edilebilir toplam hata sayısını temsil eden bir tamsayı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_RTC_NumErrors**|\<rtcapi.h>|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Çalışma zamanı hata denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
