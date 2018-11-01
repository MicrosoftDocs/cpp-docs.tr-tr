---
title: Çalışma Zamanı Hata Denetimi
ms.date: 11/04/2016
f1_keywords:
- c.runtime
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
ms.openlocfilehash: 348698faa1f91e4d98acc762538fc1cbdb798e0b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435653"
---
# <a name="run-time-error-checking"></a>Çalışma Zamanı Hata Denetimi

C çalışma zamanı kitaplığı, çalışma zamanı hata denetimleri (RTC) destekleyen işlevler içerir. Çalışma zamanı hata denetimi, programınızın çalışma zamanı hataları belirli bir türde bildirilen şekilde oluşturmanıza olanak tanır. Hataları nasıl raporlandığını ve hataları hangi türde rapor belirt Daha fazla bilgi için [nasıl yapılır: yerel çalışma zamanı denetimleri kullanın](/visualstudio/debugger/how-to-use-native-run-time-checks).

Programınızın çalışma zamanı hata denetimini olduğu gibi özelleştirmek için aşağıdaki işlevleri kullanın.

## <a name="run-time-error-checking-functions"></a>Çalışma zamanı hata denetimi işlevleri

|İşlev|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------------|---------|
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Bir çalışma zamanı hata denetimi türü kısa bir açıklamasını döndürür.|
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Çalışma zamanı hata denetimleri tarafından algılanabilir hatalarının toplam sayısını döndürür.|
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Çalışma zamanı hata denetimleri raporlama için işleyici olarak bir işlevi belirtir.|
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Çalışma zamanı hata denetimleri ile bir tür tarafından algılanan bir hata ilişkilendirir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[/RTC (Çalışma Zamanı Hata Denetimleri)](../build/reference/rtc-run-time-error-checks.md)<br/>
[runtime_checks](../preprocessor/runtime-checks.md)<br/>
[Hata Ayıklama Yordamları](../c-runtime-library/debug-routines.md)<br/>
