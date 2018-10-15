---
title: SYSTEMTIME yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6882a4e169b7efa67bef02ab5abee1276384e52f
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2018
ms.locfileid: "49334460"
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

