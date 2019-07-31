---
title: CD2DRectF sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
helpviewer_keywords:
- CD2DRectF [MFC], CD2DRectF
- CD2DRectF [MFC], IsNull
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
ms.openlocfilehash: 9b91cfaec3827a61152c4116b56e817a436606be
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682397"
---
# <a name="cd2drectf-class"></a>CD2DRectF sınıfı

İçin `D2D1_RECT_F`bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DRectF : public D2D1_RECT_F;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRectF::CD2DRectF](#cd2drectf)|Fazla Yüklendi. Nesnesinden`D2D1_RECT_F` bir `CD2DRectF` nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRectF:: IsNull](#isnull)|Bir ifadenin geçerli veri içerip içermediğini gösteren bir **Boole** değeri döndürür (null).|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRectF:: operator ekibi](#operator_crect)|Nesnesine dönüştürür `CD2DRectF`. `CRect`|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_RECT_F`

`CD2DRectF`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

##  <a name="cd2drectf"></a>CD2DRectF::CD2DRectF

CRect nesnesinden bir CD2DRectF nesnesi oluşturur.

```
CD2DRectF(const CRect& rect);
CD2DRectF(const D2D1_RECT_F& rect);
CD2DRectF(const D2D1_RECT_F* rect);

CD2DRectF(
    FLOAT fLeft = 0.,
    FLOAT fTop = 0.,
    FLOAT fRight = 0.,
    FLOAT fBottom = 0.);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Kaynak dikdörtgeni

*fLeft*<br/>
Kaynak Sol koordinatı

*fTop*<br/>
Kaynak üst koordinat

*fRight*<br/>
Kaynak sağ koordinatı

*fBottom*<br/>
kaynak alt koordinat

##  <a name="isnull"></a>CD2DRectF:: IsNull

Bir ifadenin geçerli veri içerip içermediğini gösteren bir Boole değeri döndürür (null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgenin üst, sol, alt ve sağ değerlerinin tümü 0 ' a eşit ise TRUE; Aksi halde yanlış.

##  <a name="operator_crect"></a>CD2DRectF:: operator ekibi

CD2DRectF öğesini CRect nesnesine dönüştürür.

```
operator CRect();
```

### <a name="return-value"></a>Dönüş Değeri

D2D dikdörtgeninin geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
