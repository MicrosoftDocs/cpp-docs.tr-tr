---
title: Çalışma zamanı hata denetimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2468cd05efdf732fbf955b8532a61d24fa6c0ff4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409130"
---
# <a name="run-time-error-checking"></a>Çalışma Zamanı Hata Denetimi

C çalışma zamanı kitaplığı çalışma zamanı hata denetimleri (RTC) desteği işlevler içerir. Çalışma zamanı hata denetimi, belirli türde bir çalışma zamanı hataları bildirilen şekilde, program oluşturmanıza olanak verir. Hataları nasıl raporlandığını ve hangi tür hatalara bildirilen belirtin. Daha fazla bilgi için bkz: [nasıl yapılır: çalışma zamanı kullanmak yerel denetler](/visualstudio/debugger/how-to-use-native-run-time-checks).

 Çalışma zamanı hata denetimi programınızı mu biçimini özelleştirmek için aşağıdaki işlevleri kullanın.

## <a name="run-time-error-checking-functions"></a>Çalışma zamanı hata denetimini işlevleri

|İşlev|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------------|---------|
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Bir çalışma zamanı hata denetimi türü kısa bir açıklamasını döndürür.|
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Çalışma zamanı hata denetimleri tarafından algılanan hatalarının toplam sayısını döndürür.|
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Çalışma zamanı hata denetimleri raporlama için işleyici olarak bir işlev belirler.|
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Çalışma zamanı hata denetimleri türüne sahip tarafından algılanır hatayla ilişkilendirir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
 [/RTC (Çalışma Zamanı Hata Denetimleri)](../build/reference/rtc-run-time-error-checks.md)<br/>
 [runtime_checks](../preprocessor/runtime-checks.md)<br/>
 [Hata Ayıklama Yordamları](../c-runtime-library/debug-routines.md)<br/>
