---
title: SYSTEMTIME Yapısı
ms.date: 11/04/2016
f1_keywords:
- SYSTEMTIME
helpviewer_keywords:
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
ms.openlocfilehash: b46482a9f4eb0165b72d74cb7d69e96e2a15e953
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559072"
---
# <a name="systemtime-structure"></a>SYSTEMTIME Yapısı

`SYSTEMTIME` Bir tarih ve saat ay, gün, yıl, haftanın günü, saat, dakika, saniye ve milisaniye için tek tek üyeleri kullanarak yapısını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
typedef struct _SYSTEMTIME {
    WORD wYear;
    WORD wMonth;
    WORD wDayOfWeek;
    WORD wDay;
    WORD wHour;
    WORD wMinute;
    WORD wSecond;
    WORD wMilliseconds;
} SYSTEMTIME;
```

#### <a name="parameters"></a>Parametreler

*wYear*<br/>
Geçerli yıl.

*wMonth*<br/>
Geçerli ay; Ocak 1'dir.

*wDayOfWeek*<br/>
Haftanın geçerli günü; Pazar 0, Pazartesi 1 ve benzeri.

*wDay*<br/>
Ayın geçerli günü.

*wHour*<br/>
Geçerli saat.

*wMinute*<br/>
Geçerli dakika.

*wSecond*<br/>
Geçerli saniye.

*wMilliseconds*<br/>
Geçerli milisaniye.

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** winbase.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

