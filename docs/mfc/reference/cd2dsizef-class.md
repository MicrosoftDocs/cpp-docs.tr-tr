---
title: CD2DSizeF sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DSizeF [MFC], CD2DSizeF
- CD2DSizeF [MFC], IsNull
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3610f5c8fa11aabcc3de81ddf0cb23060b9e77a1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390935"
---
# <a name="cd2dsizef-class"></a>CD2DSizeF sınıfı

D2D1_SIZE_F için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DSizeF : public D2D1_SIZE_F;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSizeF::CD2DSizeF](#cd2dsizef)|Fazla Yüklendi. Oluşturur bir `CD2DSizeF` nesnesinden `D2D1_SIZE_F` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSizeF::IsNull](#isnull)|Döndürür bir **Boole** bir ifade (NULL) geçerli olmayan veri içerip içermediğini gösteren bir değer.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSizeF::operator CSize](#operator_csize)|Dönüştürür `CD2DSizeF` için `CSize` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_SIZE_F`

[CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="cd2dsizef"></a>  CD2DSizeF::CD2DSizeF

CSize nesnesinden CD2DSizeF bir nesne oluşturur.

```
CD2DSizeF(const CSize& size);
CD2DSizeF(const D2D1_SIZE_F& size);
  CD2DSizeF(const D2D1_SIZE_F* size);


CD2DSizeF(
    FLOAT cx = 0.,
    FLOAT cy = 0.);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Kaynak boyutu

*CX*<br/>
Kaynak genişliği

*CY*<br/>
Kaynak yükseklik

##  <a name="isnull"></a>  CD2DSizeF::IsNull

Bir ifade (Null) geçerli olmayan veri içerip içermediğini gösteren bir Boole değeri döndürür.

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Dönüş Değeri

Genişlik ve yükseklik boş ise TRUE; Aksi durumda FALSE.

##  <a name="operator_csize"></a>  CD2DSizeF::operator CSize

CD2DSizeF CSize nesnesine dönüştürür.

```
operator CSize();
```

### <a name="return-value"></a>Dönüş Değeri

D2D boyutu geçerli değeri.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
