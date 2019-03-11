---
title: 'Tarih ve saat: SYSTEMTIME desteği'
ms.date: 11/04/2016
f1_keywords:
- SYSTEMTIME
helpviewer_keywords:
- system time
- FILETIME structure, with CTime class
- time [C++], formatting
- SYSTEMTIME structure
- dates [C++], MFC
- formatting [C++], time
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
ms.openlocfilehash: be8462858585a5530f360dae97e155b4967239b0
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750356"
---
# <a name="date-and-time-systemtime-support"></a>Tarih ve saat: SYSTEMTIME desteği

[CTime](../atl-mfc-shared/reference/ctime-class.md) sınıfı Win32 sistem ve dosya sürelerinden kabul oluşturucular sahiptir. Kullanırsanız `CTime` nesneler bu amaçlar için başlatma bu makalede açıklandığı gibi uygun şekilde değiştirmeniz gerekir.

SYSTEMTIME yapısı hakkında daha fazla bilgi için bkz: [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime). FILETIME yapısı hakkında daha fazla bilgi için bkz: [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime).

MFC hala sağlar `CTime` MS-DOS stilde zamanı bağımsız değişkenleri, ancak sürüm 3.0 MFC'de başlangıç alan oluşturucular `CTime` sınıfı ayrıca bir Win32 alan bir oluşturucu destekler `SYSTEMTIME` yapısı ve başka bir Win32 alan `FILETIME` yapısı.

Yeni `CTime` oluşturucular şunlardır:

- CTime (const SYSTEMTIME & `sysTime`);

- CTime (const FILETIME & `fileTime`);

*Fıletıme* parametresi, bir Win32 başvuru `FILETIME` yapısı, iç depolama alanı için daha uygun bir biçim 64-bit bir değer olarak saati temsil eden bir `SYSTEMTIME` yapısı ve Win32'tarafından kullanılan biçimi dosyanın oluşturulma zamanı temsil eder.

Kodunuzu içeriyorsa bir `CTime` sistem saatiyle başlatılan nesne kullanmalısınız `SYSTEMTIME` Win32'de Oluşturucusu.

Büyük olasılıkla kullanmaz `CTime` `FILETIME` doğrudan başlatma. Kullanıyorsanız bir `CFile` bir dosya işlemek için nesne [CFile::GetStatus](../mfc/reference/cfile-class.md#getstatus) , dosya zaman damgası alır bir `CTime` nesne başlatıldı ile bir `FILETIME` yapısı.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Genel tarih ve saat programlama MFC](../atl-mfc-shared/date-and-time.md)

- [Tarih ve saat programlama Otomasyon desteği](../atl-mfc-shared/date-and-time-automation-support.md)

## <a name="see-also"></a>Ayrıca bkz.

[Tarih ve Saat](../atl-mfc-shared/date-and-time.md)
