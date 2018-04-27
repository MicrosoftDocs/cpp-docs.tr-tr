---
title: _RTC_NumErrors | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- _RTC_NumErrors function
- RTC_NumErrors function
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7c6c2fd9f804bdbb949e4e2909cd4b9627e0f24
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="rtcnumerrors"></a>_RTC_NumErrors

Çalışma zamanı hata denetimleri (RTC) tarafından algılanan hatalarının toplam sayısını döndürür. Bu sayı, denetimi olarak kullanabileceğiniz bir **için** döngü, burada her değer döngüsünde iletilir [_RTC_GetErrDesc](rtc-geterrdesc.md).

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

Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Çalışma Zamanı Hata Denetimi](../../c-runtime-library/run-time-error-checking.md)<br/>
