---
title: CD2DEllipse sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
ms.openlocfilehash: aa280215aaac55e3aaa9542ca1ab2bd9d21655e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642045"
---
# <a name="cd2dellipse-class"></a>CD2DEllipse sınıfı

İçin sarmalayıcı `D2D1_ELLIPSE`.

## <a name="syntax"></a>Sözdizimi

```
class CD2DEllipse : public D2D1_ELLIPSE;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|Fazla Yüklendi. Oluşturur bir `CD2DEllipse` nesnesinden `D2D1_ELLIPSE` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="cd2dellipse"></a>  CD2DEllipse::CD2DEllipse

CD2DRectF nesnesinden CD2DEllipse bir nesne oluşturur.

```
CD2DEllipse(const CD2DRectF& rect);
CD2DEllipse(const D2D1_ELLIPSE& ellipse);
  CD2DEllipse(const D2D1_ELLIPSE* ellipse);

CD2DEllipse(
    const CD2DPointF& ptCenter,
    const CD2DSizeF& sizeRadius);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Kaynak dikdörtgenin

*Elips*<br/>
Kaynak elips

*ptCenter*<br/>
Merkez noktası koordinatlarıyla.

*sizeRadius*<br/>
X-radius ve elipsin Y yarıçapı.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
