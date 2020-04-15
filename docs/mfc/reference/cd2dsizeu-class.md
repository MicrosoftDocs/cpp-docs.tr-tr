---
title: CD2DSizeU Sınıfı
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
ms.openlocfilehash: a5b87fe2ddd8fb32ddbbb2884c630952afdb079c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359287"
---
# <a name="cd2dsizeu-class"></a>CD2DSizeU Sınıfı

D2D1_SIZE_U için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DSizeU : public D2D1_SIZE_U;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DSizeU::CD2DSizeu](#cd2dsizeu)|Fazla Yüklendi. Nesneden `D2D1_SIZE_U` `CD2DSizeU` bir nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DSizeU::Isnull](#isnull)|İfadenin geçerli veri içermediğini gösteren bir **boolean** değeri döndürür (NULL).|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DSizeU::operatör CSize](#operator_csize)|`CD2DSizeU` Nesneye `CSize` dönüştürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_SIZE_U`

[CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dsizeucd2dsizeu"></a><a name="cd2dsizeu"></a>CD2DSizeU::CD2DSizeu

CSize nesnesinden bir CD2DSizeU nesnesi oluşturuyor.

```
CD2DSizeU(const CSize& size);
CD2DSizeU(const D2D1_SIZE_U& size);
CD2DSizeU(const D2D1_SIZE_U* size);

CD2DSizeU(
    UINT32 cx = 0,
    UINT32 cy = 0);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
kaynak boyutu

*Cx*<br/>
kaynak genişliği

*Cy*<br/>
kaynak yüksekliği

## <a name="cd2dsizeuisnull"></a><a name="isnull"></a>CD2DSizeU::Isnull

Bir ifadenin geçerli veri içermediğini belirten bir Boolean değeri döndürür (Null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Dönüş Değeri

Genişlik ve yükseklik boşsa DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2dsizeuoperator-csize"></a><a name="operator_csize"></a>CD2DSizeU::operatör CSize

CD2DSizeU'yi CSize nesnesine dönüştürür.

```
operator CSize();
```

### <a name="return-value"></a>Dönüş Değeri

D2D boyutunun geçerli değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
