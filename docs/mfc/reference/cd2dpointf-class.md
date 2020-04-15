---
title: CD2DPointF Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
ms.openlocfilehash: 5d66c31289f9e17df99df4681cff1d5cf6a0ec86
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369154"
---
# <a name="cd2dpointf-class"></a>CD2DPointF Sınıfı

Bir sarmalayıcı. `D2D1_POINT_2F`

## <a name="syntax"></a>Sözdizimi

```
class CD2DPointF : public D2D1_POINT_2F;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DPointF::CD2DPointF](#cd2dpointf)|Fazla Yüklendi. Nesneden `D2D1_POINT_2F` `CD2DPointF` bir nesne inşa eder.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DPointF::operatör CPoint](#operator_cpoint)|`CD2DPointF` Nesneye `CPoint` dönüştürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_POINT_2F`

`CD2DPointF`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dpointfcd2dpointf"></a><a name="cd2dpointf"></a>CD2DPointF::CD2DPointF

CPoint nesnesinden bir CD2DPointF nesnesi oluşturuyor.

```
CD2DPointF(const CPoint& pt);
CD2DPointF(const D2D1_POINT_2F& pt);
CD2DPointF(const D2D1_POINT_2F* pt);
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
kaynak noktası

*Fx*<br/>
kaynak X

*Fy*<br/>
kaynak Y

## <a name="cd2dpointfoperator-cpoint"></a><a name="operator_cpoint"></a>CD2DPointF::operatör CPoint

CD2DPointF'yi CPoint nesnesine dönüştürür.

```
operator CPoint();
```

### <a name="return-value"></a>Dönüş Değeri

D2D noktasının geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
