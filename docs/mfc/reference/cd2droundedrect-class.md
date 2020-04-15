---
title: CD2DRoundedRect Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect::CD2DRoundedRect
helpviewer_keywords:
- CD2DRoundedRect [MFC], CD2DRoundedRect
ms.assetid: 06207fb5-e92b-41c0-bceb-b45d8f466531
ms.openlocfilehash: 5189f3d824c008845570eac6eead4a35be1e483d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369080"
---
# <a name="cd2droundedrect-class"></a>CD2DRoundedRect Sınıfı

Bir sarmalayıcı. `D2D1_ROUNDED_RECT`

## <a name="syntax"></a>Sözdizimi

```
class CD2DRoundedRect : public D2D1_ROUNDED_RECT;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DRoundedRect::CD2DRoundedRect](#cd2droundedrect)|Fazla Yüklendi. Nesneden `D2D1_ROUNDED_RECT` `CD2DRoundedRect` bir nesne inşa eder.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_ROUNDED_RECT`

[CD2DRoundedRect](../../mfc/reference/cd2droundedrect-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2droundedrectcd2droundedrect"></a><a name="cd2droundedrect"></a>CD2DRoundedRect::CD2DRoundedRect

CD2DRectF nesnesinden bir CD2DRoundedRect nesnesi oluşturuyor.

```
CD2DRoundedRect(
    const CD2DRectF& rectIn,
    const CD2DSizeF& sizeRadius);

CD2DRoundedRect(const D2D1_ROUNDED_RECT& rectIn);
CD2DRoundedRect(const D2D1_ROUNDED_RECT* rectIn);
```

### <a name="parameters"></a>Parametreler

*rektIn*<br/>
kaynak dikdörtgen

*boyutYarıçapı*<br/>
yarıçap boyutu

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
