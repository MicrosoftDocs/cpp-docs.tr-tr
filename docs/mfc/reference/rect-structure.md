---
title: RECT yapısı | Microsoft Docs
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
ms.openlocfilehash: eae2b248f4aa4586bf6453dcc37b521387327d25
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2018
ms.locfileid: "49334457"
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
