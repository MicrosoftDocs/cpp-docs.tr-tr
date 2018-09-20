---
title: RECT yapısı1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LPRECT
- RECT
dev_langs:
- C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa77af9dd97afc2e9b0cfb94c1fd4c69a50f309b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419600"
---
# <a name="rect-structure1"></a>RECT yapısı1

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
