---
description: 'Daha fazla bilgi edinin: CD2DSizeU Class'
title: CD2DSizeU sınıfı
ms.date: 08/29/2019
f1_keywords:
- CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::IsNull
helpviewer_keywords:
- CD2DSizeU [MFC], CD2DSizeU
- CD2DSizeU [MFC], IsNull
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
ms.openlocfilehash: 0bb2d7cc632012fe8d8c0e3ada09025c2b025e64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154714"
---
# <a name="cd2dsizeu-class"></a>CD2DSizeU sınıfı

D2D1_SIZE_U için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DSizeU : public D2D1_SIZE_U;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSizeU::CD2DSizeU](#cd2dsizeu)|Fazla Yüklendi. Nesnesinden bir `CD2DSizeU` nesne oluşturur `D2D1_SIZE_U` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSizeU:: IsNull](#isnull)|Bir ifadenin geçerli veri içerip içermediğini gösteren bir **Boole** değeri döndürür (null).|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSizeU:: operator CSize](#operator_csize)|`CD2DSizeU`Nesnesine dönüştürür `CSize` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_SIZE_U`

[CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dsizeucd2dsizeu"></a><a name="cd2dsizeu"></a> CD2DSizeU::CD2DSizeU

CSize nesnesinden bir CD2DSizeU nesnesi oluşturur.

```
CD2DSizeU(const CSize& size);
CD2DSizeU(const D2D1_SIZE_U& size);
CD2DSizeU(const D2D1_SIZE_U* size);

CD2DSizeU(
    UINT32 cx = 0,
    UINT32 cy = 0);
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Kaynak boyutu

*yazmaç*<br/>
Kaynak genişliği

*lı*<br/>
Kaynak yüksekliği

## <a name="cd2dsizeuisnull"></a><a name="isnull"></a> CD2DSizeU:: IsNull

Bir ifadenin geçerli veri içerip içermediğini gösteren bir Boole değeri döndürür (null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Dönüş Değeri

Genişlik ve yükseklik boşsa, doğru; Aksi halde yanlış.

## <a name="cd2dsizeuoperator-csize"></a><a name="operator_csize"></a> CD2DSizeU:: operator CSize

CD2DSizeU öğesini CSize nesnesine dönüştürür.

```
operator CSize();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli D2D boyutu değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
