---
description: 'Daha fazla bilgi edinin: CD2DPointF Class'
title: CD2DPointF sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
ms.openlocfilehash: 0f63aa35acb33504c96316b67ecc4f885f4f0247
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193363"
---
# <a name="cd2dpointf-class"></a>CD2DPointF sınıfı

İçin bir sarmalayıcı `D2D1_POINT_2F` .

## <a name="syntax"></a>Syntax

```
class CD2DPointF : public D2D1_POINT_2F;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPointF::CD2DPointF](#cd2dpointf)|Fazla Yüklendi. Nesnesinden bir `CD2DPointF` nesne oluşturur `D2D1_POINT_2F` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPointF:: operator CPoint](#operator_cpoint)|`CD2DPointF`Nesnesine dönüştürür `CPoint` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_POINT_2F`

`CD2DPointF`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dpointfcd2dpointf"></a><a name="cd2dpointf"></a> CD2DPointF::CD2DPointF

CPoint nesnesinden bir CD2DPointF nesnesi oluşturur.

```
CD2DPointF(const CPoint& pt);
CD2DPointF(const D2D1_POINT_2F& pt);
CD2DPointF(const D2D1_POINT_2F* pt);
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
kaynak noktası

*Döviz*<br/>
Kaynak X

*La*<br/>
Kaynak Y

## <a name="cd2dpointfoperator-cpoint"></a><a name="operator_cpoint"></a> CD2DPointF:: operator CPoint

CD2DPointF öğesini CPoint nesnesine dönüştürür.

```
operator CPoint();
```

### <a name="return-value"></a>Dönüş Değeri

D2D Point 'in geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
