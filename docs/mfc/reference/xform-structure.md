---
title: XFORM Yapısı
ms.date: 11/04/2016
f1_keywords:
- XFORM
helpviewer_keywords:
- XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
ms.openlocfilehash: 621a01accf3c323f8098da68667f06f48b9d169b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457260"
---
# <a name="xform-structure"></a>XFORM Yapısı

`XFORM` Yapısı aşağıdaki biçime sahiptir:

## <a name="syntax"></a>Sözdizimi

```
typedef struct  tagXFORM {  /* xfrm */
    FLOAT eM11;
    FLOAT eM12;
    FLOAT eM21;
    FLOAT eM22;
    FLOAT eDx;
    FLOAT eDy;
} XFORM;
```

## <a name="remarks"></a>Açıklamalar

`XFORM` Yapısı, dünya alanındaki sayfası-space transformation için belirtir. `eDx` Ve `eDy` üyeleri yatay ve dikey çeviri bileşenleri sırasıyla belirtin. Aşağıdaki tablo, diğer üyeleri, bağlı olarak işlem kullanılma gösterir:

|Çalışma|eM11|eM12|eM21|eM22|
|---------------|----------|----------|----------|----------|
|`Rotation`|Döndürme açısının kosinüsünü|Döndürme açısının sinüsünü|Negatif döndürme açısının sinüsünü|Döndürme açısının kosinüsünü|
|`Scaling`|Yatay ölçeklendirme bileşeni|Nothing|Nothing|Dikey ölçeklendirme bileşeni|
|`Shear`|Nothing|Yatay orantı sabiti|Dikey orantı sabiti|Nothing|
|`Reflection`|Yatay yansıma bileşeni|Nothing|Nothing|Dikey yansıma bileşeni|

## <a name="requirements"></a>Gereksinimler

**Başlık:** wingdi.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)

