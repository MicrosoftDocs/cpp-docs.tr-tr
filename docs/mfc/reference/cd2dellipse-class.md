---
title: CD2DEllipse sınıfı
ms.date: 08/29/2019
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
ms.openlocfilehash: 21087682d40dac521cc949a39ef4b1aab23e7d71
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177219"
---
# <a name="cd2dellipse-class"></a>CD2DEllipse sınıfı

İçin `D2D1_ELLIPSE`bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DEllipse : public D2D1_ELLIPSE;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|Fazla Yüklendi. Nesnesinden`D2D1_ELLIPSE` bir `CD2DEllipse` nesne oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

##  <a name="cd2dellipse"></a>CD2DEllipse::CD2DEllipse

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
