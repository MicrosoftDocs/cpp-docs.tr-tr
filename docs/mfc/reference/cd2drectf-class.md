---
title: CD2DRectF Sınıfı
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
ms.openlocfilehash: 33d3c5f9e795ad6c91b689436e8a3b1b56966dce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369118"
---
# <a name="cd2drectf-class"></a>CD2DRectF Sınıfı

Bir sarmalayıcı. `D2D1_RECT_F`

## <a name="syntax"></a>Sözdizimi

```
class CD2DRectF : public D2D1_RECT_F;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DRectF::CD2DRectF](#cd2drectf)|Fazla Yüklendi. Nesneden `D2D1_RECT_F` `CD2DRectF` bir nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DRectF::IsNull](#isnull)|İfadenin geçerli veri içermediğini gösteren bir **boolean** değeri döndürür (NULL).|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DRectF::operatör CRect](#operator_crect)|`CD2DRectF` Nesneye `CRect` dönüştürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_RECT_F`

`CD2DRectF`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2drectfcd2drectf"></a><a name="cd2drectf"></a>CD2DRectF::CD2DRectF

CRect nesnesinden bir CD2DRectF nesnesi oluşturuyor.

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
kaynak dikdörtgen

*fLeft*<br/>
kaynak sol koordinat

*fTop*<br/>
kaynak üst koordinat

*Korku*<br/>
kaynak sağ koordinat

*fBottom*<br/>
kaynak alt koordinat

## <a name="cd2drectfisnull"></a><a name="isnull"></a>CD2DRectF::IsNull

Bir ifadenin geçerli veri içermediğini belirten bir Boolean değeri döndürür (Null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dikdörtgenin üst, sol, alt ve sağ değerlerinin tümü 0'a eşitse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2drectfoperator-crect"></a><a name="operator_crect"></a>CD2DRectF::operatör CRect

CD2DRectF'yi CRect nesnesine dönüştürür.

```
operator CRect();
```

### <a name="return-value"></a>Dönüş Değeri

D2D dikdörtgeninin geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
