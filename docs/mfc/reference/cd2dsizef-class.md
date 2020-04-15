---
title: CD2DSizeF Sınıfı
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
ms.openlocfilehash: be050f98855e5af794166e1f86962111a23bfa2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369072"
---
# <a name="cd2dsizef-class"></a>CD2DSizeF Sınıfı

D2D1_SIZE_F için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DSizeF : public D2D1_SIZE_F;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DSizeF::CD2DSizeF](#cd2dsizef)|Fazla Yüklendi. Nesneden `D2D1_SIZE_F` `CD2DSizeF` bir nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DSizeF::Isnull](#isnull)|İfadenin geçerli veri içermediğini gösteren bir **boolean** değeri döndürür (NULL).|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DSizeF::operatör CSize](#operator_csize)|`CD2DSizeF` Nesneye `CSize` dönüştürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_SIZE_F`

[CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dsizefcd2dsizef"></a><a name="cd2dsizef"></a>CD2DSizeF::CD2DSizeF

CSize nesnesinden bir CD2DSizeF nesnesi oluşturuyor.

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
kaynak boyutu

*Cx*<br/>
kaynak genişliği

*Cy*<br/>
kaynak yüksekliği

## <a name="cd2dsizefisnull"></a><a name="isnull"></a>CD2DSizeF::Isnull

Bir ifadenin geçerli veri içermediğini belirten bir Boolean değeri döndürür (Null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Dönüş Değeri

Genişlik ve yükseklik boşsa DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2dsizefoperator-csize"></a><a name="operator_csize"></a>CD2DSizeF::operatör CSize

CD2DSizeF'yi CSize nesnesine dönüştürür.

```
operator CSize();
```

### <a name="return-value"></a>Dönüş Değeri

D2D boyutunun geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
