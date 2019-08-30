---
title: CD2DSizeF sınıfı
ms.date: 08/29/2019
f1_keywords:
- CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::IsNull
helpviewer_keywords:
- CD2DSizeF [MFC], CD2DSizeF
- CD2DSizeF [MFC], IsNull
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
ms.openlocfilehash: df895c278003e2c71f37a00af6bf14912756701a
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177205"
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
|[CD2DSizeF::CD2DSizeF](#cd2dsizef)|Fazla Yüklendi. Nesnesinden`D2D1_SIZE_F` bir `CD2DSizeF` nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSizeF:: IsNull](#isnull)|Bir ifadenin geçerli veri içerip içermediğini gösteren bir **Boole** değeri döndürür (null).|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSizeF:: operator CSize](#operator_csize)|Nesnesine dönüştürür `CD2DSizeF`. `CSize`|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_SIZE_F`

[CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

##  <a name="cd2dsizef"></a>CD2DSizeF::CD2DSizeF

CSize nesnesinden bir CD2DSizeF nesnesi oluşturur.

```
CD2DSizeF(const CSize& size);
CD2DSizeF(const D2D1_SIZE_F& size);
CD2DSizeF(const D2D1_SIZE_F* size);

CD2DSizeF(
    FLOAT cx = 0.,
    FLOAT cy = 0.);
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Kaynak boyutu

*yazmaç*<br/>
Kaynak genişliği

*lı*<br/>
Kaynak yüksekliği

##  <a name="isnull"></a>CD2DSizeF:: IsNull

Bir ifadenin geçerli veri içerip içermediğini gösteren bir Boole değeri döndürür (null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Dönüş Değeri

Genişlik ve yükseklik boşsa, doğru; Aksi halde yanlış.

##  <a name="operator_csize"></a>CD2DSizeF:: operator CSize

CD2DSizeF öğesini CSize nesnesine dönüştürür.

```
operator CSize();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli D2D boyutu değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
