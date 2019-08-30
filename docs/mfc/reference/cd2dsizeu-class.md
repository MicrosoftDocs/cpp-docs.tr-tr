---
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
ms.openlocfilehash: 45625331d0c1be8ca7c663d12c53516dc7bd77c7
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177191"
---
# <a name="cd2dsizeu-class"></a>CD2DSizeU sınıfı

D2D1_SIZE_U için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DSizeU : public D2D1_SIZE_U;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSizeU::CD2DSizeU](#cd2dsizeu)|Fazla Yüklendi. Nesnesinden`D2D1_SIZE_U` bir `CD2DSizeU` nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSizeU:: IsNull](#isnull)|Bir ifadenin geçerli veri içerip içermediğini gösteren bir **Boole** değeri döndürür (null).|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DSizeU:: operator CSize](#operator_csize)|Nesnesine dönüştürür `CD2DSizeU`. `CSize`|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_SIZE_U`

[CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

##  <a name="cd2dsizeu"></a>CD2DSizeU::CD2DSizeU

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

##  <a name="isnull"></a>CD2DSizeU:: IsNull

Bir ifadenin geçerli veri içerip içermediğini gösteren bir Boole değeri döndürür (null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Dönüş Değeri

Genişlik ve yükseklik boşsa, doğru; Aksi halde yanlış.

##  <a name="operator_csize"></a>CD2DSizeU:: operator CSize

CD2DSizeU öğesini CSize nesnesine dönüştürür.

```
operator CSize();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli D2D boyutu değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
