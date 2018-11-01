---
title: POINT Yapısı
ms.date: 10/12/2018
f1_keywords:
- POINT
- LPPOINT
helpviewer_keywords:
- LPPOINT structure [MFC]
- POINT structure [MFC]
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
ms.openlocfilehash: c53f250b714c66e74a12432b879cbc4bcc1fd88d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646907"
---
# <a name="point-structure"></a>POINT Yapısı

`POINT` Yapısını tanımlayan x*-* ve bir noktanın y koordinatları.

## <a name="syntax"></a>Sözdizimi

```
typedef struct tagPOINT {
    LONG x;
    LONG y;
} POINT;
```

#### <a name="parameters"></a>Parametreler

*x*<br/>
Bir noktasının x koordinatını belirtir.

*Y*<br/>
Bir noktanın y koordinatını belirtir.

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#37](../../mfc/codesnippet/cpp/point-structure1_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** windef.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CPoint Sınıfı](../../atl-mfc-shared/reference/cpoint-class.md)
