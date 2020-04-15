---
title: CD2DRectU Sınıfı
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
ms.openlocfilehash: 26e647ae01a498a6ad8ca2d7c866f33b01910881
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369106"
---
# <a name="cd2drectu-class"></a>CD2DRectU Sınıfı

Bir sarmalayıcı. `D2D1_RECT_U`

## <a name="syntax"></a>Sözdizimi

```
class CD2DRectU : public D2D1_RECT_U;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DRectU::CD2DRectU](#cd2drectu)|Fazla Yüklendi. Nesneden `D2D1_RECT_U` `CD2DRectU` bir nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DRectU::IsNull](#isnull)|İfadenin geçerli veri içermediğini gösteren bir **boolean** değeri döndürür (NULL).|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DRectU::operatör CRect](#operator_crect)|`CD2DRectU` Nesneye `CRect` dönüştürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_RECT_U`

`CD2DRectU`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2drectucd2drectu"></a><a name="cd2drectu"></a>CD2DRectU::CD2DRectU

CRect nesnesinden bir CD2DRectU nesnesi oluşturuyor.

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
kaynak dikdörtgen

*uLeft*<br/>
kaynak sol koordinat

*uTop*<br/>
kaynak üst koordinat

*uHakkı*<br/>
kaynak sağ koordinat

*uBottom*<br/>
kaynak alt koordinat

## <a name="cd2drectuisnull"></a><a name="isnull"></a>CD2DRectU::IsNull

Bir ifadenin geçerli veri içermediğini belirten bir Boolean değeri döndürür (Null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgenin üst, sol, alt ve sağ değerlerinin tümü 0'a eşitse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2drectuoperator-crect"></a><a name="operator_crect"></a>CD2DRectU::operatör CRect

CD2DRectU'u CRect nesnesine dönüştürür.

```
operator CRect();
```

### <a name="return-value"></a>Dönüş Değeri

D2D dikdörtgeninin geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
