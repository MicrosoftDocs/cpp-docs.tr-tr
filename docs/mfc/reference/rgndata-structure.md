---
title: RGNDATA Yapısı
ms.date: 11/04/2016
f1_keywords:
- RGNDATA
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
ms.openlocfilehash: d6ee25b490aa5c7055b4e8ccf63939fbdd8dd4ac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638145"
---
# <a name="rgndata-structure"></a>RGNDATA Yapısı

`RGNDATA` Yapısı üstbilgi ve bölge oluşturma dikdörtgenler dizisi içerir. Bu dikdörtgenler, soldan sağa doğru sıralanmış yukarıdan çakışmaz.

## <a name="syntax"></a>Sözdizimi

```
typedef struct _RGNDATA { /* rgnd */
    RGNDATAHEADER rdh;
    char Buffer[1];
} RGNDATA;
```

#### <a name="parameters"></a>Parametreler

*rdh*<br/>
Belirtir bir [RGNDATAHEADER](/windows/desktop/api/wingdi/ns-wingdi-_rgndataheader) yapısı. (Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.) Bu yapının üyeleri (dikdörtgen veya trapezoidal olup), bölge dikdörtgen yapıları içeren arabellek boyutu bölgeyi oluşturan dikdörtgenler sayısını türünü belirtin ve benzeri.

*Arabellek*<br/>
İçeren bir rastgele boyutlu bir arabellek belirtir [RECT](../../mfc/reference/rect-structure1.md) bölgeyi oluşturan yapılar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** wingdi.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)<br/>
[CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

