---
title: RGNDATA yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d40cd86cff4c3e58e88f9d17a551dc789bd1db4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398221"
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

