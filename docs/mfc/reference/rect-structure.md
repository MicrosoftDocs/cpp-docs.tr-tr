---
title: RECT Yapısı
ms.date: 11/04/2016
f1_keywords:
- LPRECT
- RECT
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
ms.openlocfilehash: 1cb997fc0f1ec89eabf5e4d2c2c5ccb15e3bafec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549024"
---
# <a name="rect-structure"></a>RECT Yapısı

`RECT` Yapısını tanımlayan bir dikdörtgenin sol ve sağ alt köşe koordinatları.

## <a name="syntax"></a>Sözdizimi

```
typedef struct tagRECT {
    LONG left;
    LONG top;
    LONG right;
    LONG bottom;
} RECT;
```

## <a name="members"></a>Üyeler

`left`<br/>
Bir dikdörtgenin sol üst köşesinin x koordinatını belirtir.

`top`<br/>
Dikdörtgenin sol üst köşesinin y koordinatını belirtir.

`right`<br/>
Bir dikdörtgenin sağ alt köşesinin x koordinatını belirtir.

`bottom`<br/>
Bir dikdörtgenin sağ alt köşesinin y koordinatını belirtir.

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** windef.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRect Sınıfı](../../atl-mfc-shared/reference/crect-class.md)
