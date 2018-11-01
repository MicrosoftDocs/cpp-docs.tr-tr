---
title: CD2DRoundedRect sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect::CD2DRoundedRect
helpviewer_keywords:
- CD2DRoundedRect [MFC], CD2DRoundedRect
ms.assetid: 06207fb5-e92b-41c0-bceb-b45d8f466531
ms.openlocfilehash: 6c1aa2bb9593cdf12aadc39ef8a85cc8ad14078a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677480"
---
# <a name="cd2droundedrect-class"></a>CD2DRoundedRect sınıfı

İçin sarmalayıcı `D2D1_ROUNDED_RECT`.

## <a name="syntax"></a>Sözdizimi

```
class CD2DRoundedRect : public D2D1_ROUNDED_RECT;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRoundedRect::CD2DRoundedRect](#cd2droundedrect)|Fazla Yüklendi. Oluşturur bir `CD2DRoundedRect` nesnesinden `D2D1_ROUNDED_RECT` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_ROUNDED_RECT`

[CD2DRoundedRect](../../mfc/reference/cd2droundedrect-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="cd2droundedrect"></a>  CD2DRoundedRect::CD2DRoundedRect

CD2DRectF nesnesinden CD2DRoundedRect bir nesne oluşturur.

```
CD2DRoundedRect(
    const CD2DRectF& rectIn,
    const CD2DSizeF& sizeRadius);

CD2DRoundedRect(const D2D1_ROUNDED_RECT& rectIn);
CD2DRoundedRect(const D2D1_ROUNDED_RECT* rectIn);
```

### <a name="parameters"></a>Parametreler

*rectIn*<br/>
Kaynak dikdörtgenin

*sizeRadius*<br/>
RADIUS boyutu

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
