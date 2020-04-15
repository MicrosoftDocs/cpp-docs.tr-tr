---
title: CD2DPointU Sınıfı
ms.date: 08/29/2019
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
ms.openlocfilehash: 8c6db55f1dde1fd054a1f75590f5969c097b2f90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369151"
---
# <a name="cd2dpointu-class"></a>CD2DPointU Sınıfı

Bir sarmalayıcı. `D2D1_POINT_2U`

## <a name="syntax"></a>Sözdizimi

```
class CD2DPointU : public D2D1_POINT_2U;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DPointU::CD2DPointu](#cd2dpointu)|Fazla Yüklendi. Nesne nesnesinden `CD2DPointU` `D2D1_POINT_2U` bir yapı.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DPointU::operatör CPoint](#operator_cpoint)|`CD2DPointU` Nesneye `CPoint` dönüştürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dpointucd2dpointu"></a><a name="cd2dpointu"></a>CD2DPointU::CD2DPointu

CPoint nesnesinden bir CD2DPointU nesnesi oluşturuyor.

```
CD2DPointU(const CPoint& pt);
CD2DPointU(const D2D1_POINT_2U& pt);
CD2DPointU(const D2D1_POINT_2U* pt);
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
kaynak noktası

*Ux*<br/>
kaynak X

*Uslu*<br/>
kaynak Y

## <a name="cd2dpointuoperator-cpoint"></a><a name="operator_cpoint"></a>CD2DPointU::operatör CPoint

CD2DPointU'yi CPoint nesnesine dönüştürür.

```
operator CPoint();
```

### <a name="return-value"></a>Dönüş Değeri

D2D noktasının geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
