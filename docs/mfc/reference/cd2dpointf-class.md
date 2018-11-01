---
title: CD2DPointF sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
ms.openlocfilehash: 7b9f6634e4b5980d8318557a8822549d226910b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559113"
---
# <a name="cd2dpointf-class"></a>CD2DPointF sınıfı

İçin sarmalayıcı `D2D1_POINT_2F`.

## <a name="syntax"></a>Sözdizimi

```
class CD2DPointF : public D2D1_POINT_2F;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPointF::CD2DPointF](#cd2dpointf)|Fazla Yüklendi. Oluşturur bir `CD2DPointF` nesnesinden `D2D1_POINT_2F` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPointF::operator CPoint](#operator_cpoint)|Dönüştürür `CD2DPointF` için `CPoint` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_POINT_2F`

`CD2DPointF`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="cd2dpointf"></a>  CD2DPointF::CD2DPointF

CPoint nesnesinden CD2DPointF bir nesne oluşturur.

```
CD2DPointF(const CPoint& pt);
CD2DPointF(const D2D1_POINT_2F& pt);
CD2DPointF(const D2D1_POINT_2F* pt);
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
Kaynak noktası

*fX*<br/>
Kaynak X

*My*<br/>
Kaynak Y

##  <a name="operator_cpoint"></a>  CD2DPointF::operator CPoint

CD2DPointF CPoint nesnesine dönüştürür.

```
operator CPoint();
```

### <a name="return-value"></a>Dönüş Değeri

D2D noktası geçerli değeri.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
