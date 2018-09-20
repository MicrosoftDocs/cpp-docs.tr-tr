---
title: CD2DPointU sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58eddd2a4c8be2520baf305f5212bd055412c821
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439230"
---
# <a name="cd2dpointu-class"></a>CD2DPointU sınıfı

İçin sarmalayıcı `D2D1_POINT_2U`.

## <a name="syntax"></a>Sözdizimi

```
class CD2DPointU : public D2D1_POINT_2U;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPointU::CD2DPointU](#cd2dpointu)|Fazla Yüklendi. Oluşturur bir `CD2DPointU` nesnesinden `D2D1_POINT_2U` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DPointU::operator CPoint](#operator_cpoint)|Dönüştürür `CD2DPointU` için `CPoint` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="cd2dpointu"></a>  CD2DPointU::CD2DPointU

CPoint nesnesinden CD2DPointU bir nesne oluşturur.

```
CD2DPointU(const CPoint& pt);
CD2DPointU(const D2D1_POINT_2U& pt);
  CD2DPointU(const D2D1_POINT_2U* pt);
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
Kaynak noktası

*uX*<br/>
Kaynak X

*uY*<br/>
Kaynak Y

##  <a name="operator_cpoint"></a>  CD2DPointU::operator CPoint

CD2DPointU CPoint nesnesine dönüştürür.

```
operator CPoint();
```

### <a name="return-value"></a>Dönüş Değeri

D2D noktası geçerli değeri.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
