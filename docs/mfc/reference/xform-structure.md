---
title: XFORM yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- XFORM
dev_langs:
- C++
helpviewer_keywords:
- XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab1a2fe23f364dc35a2368d325db5e4274fc8e64
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411644"
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

