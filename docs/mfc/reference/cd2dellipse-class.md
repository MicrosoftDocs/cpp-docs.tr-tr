---
title: CD2DEllipse Sınıfı
ms.date: 08/29/2019
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
ms.openlocfilehash: 82ad2fbfb8558486134f85d7ec9bcaa6eb4e7507
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369269"
---
# <a name="cd2dellipse-class"></a>CD2DEllipse Sınıfı

Bir sarmalayıcı. `D2D1_ELLIPSE`

## <a name="syntax"></a>Sözdizimi

```
class CD2DEllipse : public D2D1_ELLIPSE;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|Fazla Yüklendi. Nesneden `D2D1_ELLIPSE` `CD2DEllipse` bir nesne inşa eder.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dellipsecd2dellipse"></a><a name="cd2dellipse"></a>CD2DEllipse::CD2DEllipse

CD2DRectF nesnesinden bir CD2DEllipse nesnesi oluşturuyor.

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
kaynak dikdörtgen

*ellipse*<br/>
kaynak elips

*ptCenter*<br/>
Elipsin merkez noktası.

*boyutYarıçapı*<br/>
Elipsin X yarıçapı ve Y yarıçapı.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
