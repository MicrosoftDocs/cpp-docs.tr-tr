---
title: CD2DPointU sınıfı
ms.date: 08/29/2019
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
ms.openlocfilehash: 6289d33aa0672d1ee423d91b11527dccfc868da7
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177171"
---
# <a name="cd2dpointu-class"></a>CD2DPointU sınıfı

İçin `D2D1_POINT_2U`bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DPointU : public D2D1_POINT_2U;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPointU::CD2DPointU](#cd2dpointu)|Fazla Yüklendi. `CD2DPointU` Nesnesinden`D2D1_POINT_2U` bir nesnesi oluşturur.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPointU:: operator CPoint](#operator_cpoint)|Nesnesine dönüştürür `CD2DPointU`. `CPoint`|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

##  <a name="cd2dpointu"></a>CD2DPointU::CD2DPointU

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

##  <a name="operator_cpoint"></a>CD2DPointU:: operator CPoint

CD2DPointU öğesini CPoint nesnesine dönüştürür.

```
operator CPoint();
```

### <a name="return-value"></a>Dönüş Değeri

D2D Point 'in geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
