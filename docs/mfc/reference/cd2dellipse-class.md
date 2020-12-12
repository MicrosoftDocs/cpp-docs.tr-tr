---
description: 'Daha fazla bilgi edinin: CD2DEllipse Class'
title: CD2DEllipse sınıfı
ms.date: 08/29/2019
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
ms.openlocfilehash: 827ba5515cb4b20cb8e5b10012590a001e01c08f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313066"
---
# <a name="cd2dellipse-class"></a>CD2DEllipse sınıfı

İçin bir sarmalayıcı `D2D1_ELLIPSE` .

## <a name="syntax"></a>Syntax

```
class CD2DEllipse : public D2D1_ELLIPSE;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|Fazla Yüklendi. Nesnesinden bir `CD2DEllipse` nesne oluşturur `D2D1_ELLIPSE` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dellipsecd2dellipse"></a><a name="cd2dellipse"></a> CD2DEllipse::CD2DEllipse

CD2DRectF nesnesinden bir CD2DEllipse nesnesi oluşturur.

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
Kaynak dikdörtgeni

*tir*<br/>
Kaynak elips

*ptCenter*<br/>
Elipsin orta noktası.

*Sizsilinebilir orus*<br/>
Elipsin X-radius ve Y-Radius.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
