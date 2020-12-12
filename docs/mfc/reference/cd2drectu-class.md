---
description: 'Daha fazla bilgi edinin: CD2DRectU Class'
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
ms.openlocfilehash: dadbaf37f1ed11f96f29c7e4cf78eebf8095590d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301626"
---
# <a name="cd2drectu-class"></a>CD2DRectU sınıfı

İçin bir sarmalayıcı `D2D1_RECT_U` .

## <a name="syntax"></a>Syntax

```
class CD2DRectU : public D2D1_RECT_U;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRectU::CD2DRectU](#cd2drectu)|Fazla Yüklendi. Nesnesinden bir `CD2DRectU` nesne oluşturur `D2D1_RECT_U` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRectU:: IsNull](#isnull)|Bir ifadenin geçerli veri içerip içermediğini gösteren bir **Boole** değeri döndürür (null).|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DRectU:: operator ekibi](#operator_crect)|`CD2DRectU`Nesnesine dönüştürür `CRect` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_RECT_U`

`CD2DRectU`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2drectucd2drectu"></a><a name="cd2drectu"></a> CD2DRectU::CD2DRectU

CRect nesnesinden bir CD2DRectU nesnesi oluşturur.

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
Kaynak dikdörtgeni

*Uıleft*<br/>
Kaynak Sol koordinatı

*uTop*<br/>
Kaynak üst koordinat

*uRight dili*<br/>
Kaynak sağ koordinatı

*uBottom*<br/>
kaynak alt koordinat

## <a name="cd2drectuisnull"></a><a name="isnull"></a> CD2DRectU:: IsNull

Bir ifadenin geçerli veri içerip içermediğini gösteren bir Boole değeri döndürür (null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgenin üst, sol, alt ve sağ değerlerinin tümü 0 ' a eşit ise TRUE; Aksi halde yanlış.

## <a name="cd2drectuoperator-crect"></a><a name="operator_crect"></a> CD2DRectU:: operator ekibi

CD2DRectU öğesini CRect nesnesine dönüştürür.

```
operator CRect();
```

### <a name="return-value"></a>Dönüş Değeri

D2D dikdörtgeninin geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
