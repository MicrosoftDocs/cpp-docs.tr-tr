---
description: 'Daha fazla bilgi edinin: CD2DPointU Class'
title: CD2DPointU sınıfı
ms.date: 08/29/2019
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
ms.openlocfilehash: 04c1c366f3026e4a621892fc1c7617707c33d23d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251004"
---
# <a name="cd2dpointu-class"></a>CD2DPointU sınıfı

İçin bir sarmalayıcı `D2D1_POINT_2U` .

## <a name="syntax"></a>Syntax

```
class CD2DPointU : public D2D1_POINT_2U;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPointU::CD2DPointU](#cd2dpointu)|Fazla Yüklendi. Nesnesinden bir nesnesi oluşturur `CD2DPointU` `D2D1_POINT_2U` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPointU:: operator CPoint](#operator_cpoint)|`CD2DPointU`Nesnesine dönüştürür `CPoint` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dpointucd2dpointu"></a><a name="cd2dpointu"></a> CD2DPointU::CD2DPointU

CPoint nesnesinden bir CD2DPointU nesnesi oluşturur.

```
CD2DPointU(const CPoint& pt);
CD2DPointU(const D2D1_POINT_2U& pt);
CD2DPointU(const D2D1_POINT_2U* pt);
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
kaynak noktası

*uX*<br/>
Kaynak X

*uY*<br/>
Kaynak Y

## <a name="cd2dpointuoperator-cpoint"></a><a name="operator_cpoint"></a> CD2DPointU:: operator CPoint

CD2DPointU öğesini CPoint nesnesine dönüştürür.

```
operator CPoint();
```

### <a name="return-value"></a>Dönüş Değeri

D2D Point 'in geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
