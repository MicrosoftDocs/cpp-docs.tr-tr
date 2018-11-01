---
title: Tarih ve Saat
ms.date: 11/04/2016
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
ms.openlocfilehash: dcb5ef9f21987e11608cfa29e77b24e96153e6b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459455"
---
# <a name="date-and-time"></a>Tarih ve Saat

MFC, tarihler ve saatler ile çalışma birkaç farklı yolunu destekler. Bu güncelleştirmeler şunlardır:

- Genel amaçlı zaman sınıfları. [CTime](../atl-mfc-shared/reference/ctime-class.md) ve [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md) sınıfları, zaman içinde bildirilen ANSI standardı saati library ile ilişkilendirilmiş işlevselliğinin büyük kısmını kapsüller. H

- Sistem saati için destek. MFC sürüm 3.0 için destek eklendi `CTime` Win32 için `SYSTEMTIME` ve `FILETIME` veri türleri.

- Otomasyon için destek [DATE veri türü](../atl-mfc-shared/date-type.md). Tarih desteklediği tarih, saat ve tarih/saat değerleri. [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) ve [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) sınıfları bu işlevselliğini kapsüller. Birlikte çalıştıkları [COleVariant](../mfc/reference/colevariant-class.md) kullanarak otomasyon desteği.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Tarih ve Saat: SYSTEMTIME Desteği](../atl-mfc-shared/date-and-time-systemtime-support.md)

- [Tarih ve Saat: Otomasyon Desteği](../atl-mfc-shared/date-and-time-automation-support.md)

- [Tarih ve Saat: Veritabanı Desteği](../atl-mfc-shared/date-and-time-database-support.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../mfc/mfc-concepts.md)<br/>
[Genel MFC Konuları](../mfc/general-mfc-topics.md)

