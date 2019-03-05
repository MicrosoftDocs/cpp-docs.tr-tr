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
ms.openlocfilehash: 8e5c22fe15ce0d930f81dd16673927d5299bf630
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290839"
---
# <a name="cd2drectf-class"></a>CD2DRectF sınıfı

İçin sarmalayıcı `D2D1_RECT_F`.

## <a name="syntax"></a>Sözdizimi

```
class CD2DRectF : public D2D1_RECT_F;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRectF::CD2DRectF](#cd2drectf)|Fazla Yüklendi. Oluşturur bir `CD2DRectF` nesnesinden `D2D1_RECT_F` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRectF::IsNull](#isnull)|Döndürür bir **Boole** bir ifade (NULL) geçerli olmayan veri içerip içermediğini gösteren bir değer.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRectF::operator CRect](#operator_crect)|Dönüştürür `CD2DRectF` için `CRect` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_RECT_F`

`CD2DRectF`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="cd2drectf"></a>  CD2DRectF::CD2DRectF

CRect nesnesinden CD2DRectF bir nesne oluşturur.

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
Kaynak dikdörtgenin

*fLeft*<br/>
Kaynak sol koordinatı

*fTop*<br/>
Kaynak üst koordinat

*fRight*<br/>
Kaynak şu koordinat

*fBottom*<br/>
kaynak alt koordinat

##  <a name="isnull"></a>  CD2DRectF::IsNull

Bir ifade (Null) geçerli olmayan veri içerip içermediğini gösteren bir Boole değeri döndürür.

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgenin üst, sol, alt ve sağ değerlerin tüm 0'a eşit ise TRUE; Aksi durumda FALSE.

##  <a name="operator_crect"></a>  CD2DRectF::operator CRect

CD2DRectF CRect nesnesine dönüştürür.

```
operator CRect();
```

### <a name="return-value"></a>Dönüş Değeri

D2D dikdörtgen geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
