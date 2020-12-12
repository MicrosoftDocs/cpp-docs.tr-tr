---
description: 'Hakkında daha fazla bilgi edinin: Run-Time hata denetimi'
title: Çalışma Zamanı Hata Denetimi
ms.date: 11/04/2016
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
ms.openlocfilehash: aff00bc66cd118b891e902328eb6ae85bd6fc14c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273611"
---
# <a name="run-time-error-checking"></a>Çalışma Zamanı Hata Denetimi

C çalışma zamanı kitaplığı, çalışma zamanı hata denetimlerini (RTC) destekleyen işlevleri içerir. Çalışma zamanı hata denetimi, programınızı, belirli çalışma zamanı hatalarının raporlanması için oluşturmanıza olanak sağlar. Hataların nasıl bildirileceğini ve hangi tür hataların raporlanacağı belirtirsiniz. Daha fazla bilgi için bkz. [nasıl yapılır: yerel Run-Time denetimleri kullanma](/visualstudio/debugger/how-to-use-native-run-time-checks).

Programınızın çalışma zamanı hata denetimi şeklini özelleştirmek için aşağıdaki işlevleri kullanın.

## <a name="run-time-error-checking-functions"></a>Run-Time hata denetimi Işlevleri

|İşlev|Kullanın|
|--------------|---------|
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Çalışma zamanı hata denetim türünün kısa bir açıklamasını döndürür.|
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Çalışma zamanı hata denetimleri tarafından tespit edilebilir toplam hata sayısını döndürür.|
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Çalışma zamanı hata denetimleri raporlaması için bir işlevi işleyici olarak belirler.|
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Çalışma zamanı hata denetimleri tarafından algılanan bir hatayı bir tür ile ilişkilendirir.|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[/RTC (çalışma zamanı hata denetimleri)](../build/reference/rtc-run-time-error-checks.md)<br/>
[runtime_checks](../preprocessor/runtime-checks.md)<br/>
[Hata ayıklama yordamları](../c-runtime-library/debug-routines.md)<br/>
