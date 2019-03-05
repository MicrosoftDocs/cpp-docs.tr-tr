---
title: CD2DRectU sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
helpviewer_keywords:
- CD2DRectU [MFC], CD2DRectU
- CD2DRectU [MFC], IsNull
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
ms.openlocfilehash: feb8af3992b9f56164ded0e3b6a4529a46fe2a1d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294388"
---
# <a name="cd2drectu-class"></a>CD2DRectU sınıfı

İçin sarmalayıcı `D2D1_RECT_U`.

## <a name="syntax"></a>Sözdizimi

```
class CD2DRectU : public D2D1_RECT_U;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRectU::CD2DRectU](#cd2drectu)|Fazla Yüklendi. Oluşturur bir `CD2DRectU` nesnesinden `D2D1_RECT_U` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRectU::IsNull](#isnull)|Döndürür bir **Boole** bir ifade (NULL) geçerli olmayan veri içerip içermediğini gösteren bir değer.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRectU::operator CRect](#operator_crect)|Dönüştürür `CD2DRectU` için `CRect` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_RECT_U`

`CD2DRectU`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="cd2drectu"></a>  CD2DRectU::CD2DRectU

CRect nesnesinden CD2DRectU bir nesne oluşturur.

```
CD2DRectU(const CRect& rect);
CD2DRectU(const D2D1_RECT_U& rect);
  CD2DRectU(const D2D1_RECT_U* rect);

CD2DRectU(
    UINT32 uLeft = 0,
    UINT32 uTop = 0,
    UINT32 uRight = 0,
    UINT32 uBottom = 0);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Kaynak dikdörtgenin

*uLeft*<br/>
Kaynak sol koordinatı

*uTop*<br/>
Kaynak üst koordinat

*uRight*<br/>
Kaynak şu koordinat

*uBottom*<br/>
kaynak alt koordinat

##  <a name="isnull"></a>  CD2DRectU::IsNull

Bir ifade (Null) geçerli olmayan veri içerip içermediğini gösteren bir Boole değeri döndürür.

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgenin üst, sol, alt ve sağ değerlerin tüm 0'a eşit ise TRUE; Aksi durumda FALSE.

##  <a name="operator_crect"></a>  CD2DRectU::operator CRect

CD2DRectU CRect nesnesine dönüştürür.

```
operator CRect();
```

### <a name="return-value"></a>Dönüş Değeri

D2D dikdörtgen geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
