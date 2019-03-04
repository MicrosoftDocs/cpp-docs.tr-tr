---
title: CBitmapRenderTarget sınıfı
ms.date: 11/04/2016
f1_keywords:
- CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::Attach
- AFXRENDERTARGET/CBitmapRenderTarget::Detach
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmap
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::m_pBitmapRenderTarget
helpviewer_keywords:
- CBitmapRenderTarget [MFC], CBitmapRenderTarget
- CBitmapRenderTarget [MFC], Attach
- CBitmapRenderTarget [MFC], Detach
- CBitmapRenderTarget [MFC], GetBitmap
- CBitmapRenderTarget [MFC], GetBitmapRenderTarget
- CBitmapRenderTarget [MFC], m_pBitmapRenderTarget
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
ms.openlocfilehash: 8c110ec8f7c232180bf054e8e4ba90a18f1902c1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283559"
---
# <a name="cbitmaprendertarget-class"></a>CBitmapRenderTarget sınıfı

ID2D1BitmapRenderTarget için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CBitmapRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|CBitmapRenderTarget bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBitmapRenderTarget::Attach](#attach)|Varolan ekler nesnesine hedef arabirimi oluşturma|
|[CBitmapRenderTarget::Detach](#detach)|İşleme hedefi arabirimi nesnesinden ayırır|
|[CBitmapRenderTarget::GetBitmap](#getbitmap)|Bu işleme hedefi için bit eşlem alır. Döndürülen bir bit eşlem operations çizmek için kullanılabilir.|
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|Döndürür ID2D1BitmapRenderTarget arabirimi|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|Döndürür ID2D1BitmapRenderTarget arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CBitmapRenderTarget::m_pBitmapRenderTarget](#m_pbitmaprendertarget)|ID2D1BitmapRenderTarget nesneye bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

`CBitmapRenderTarget`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="attach"></a>  CBitmapRenderTarget::Attach

Varolan ekler nesnesine hedef arabirimi oluşturma

```
void Attach(ID2D1BitmapRenderTarget* pTarget);
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
Mevcut işleme hedefi arabirimi. NULL olamaz

##  <a name="cbitmaprendertarget"></a>  CBitmapRenderTarget::CBitmapRenderTarget

CBitmapRenderTarget bir nesne oluşturur.

```
CBitmapRenderTarget();
```

##  <a name="detach"></a>  CBitmapRenderTarget::Detach

İşleme hedefi arabirimi nesnesinden ayırır

```
ID2D1BitmapRenderTarget* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçi ayrılmış işleme hedefi arabirimi.

##  <a name="getbitmap"></a>  CBitmapRenderTarget::GetBitmap

Bu işleme hedefi için bit eşlem alır. Döndürülen bir bit eşlem operations çizmek için kullanılabilir.

```
BOOL GetBitmap(CD2DBitmap& bitmap);
```

### <a name="parameters"></a>Parametreler

*Bit eşlem*<br/>
Bu yöntem döndürüldüğünde, bu işleme hedefi için geçerli bir bit eşlem içerir. Bu bit eşlem operations çizmek için kullanılabilir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="getbitmaprendertarget"></a>  CBitmapRenderTarget::GetBitmapRenderTarget

Döndürür ID2D1BitmapRenderTarget arabirimi

```
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1BitmapRenderTarget arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="m_pbitmaprendertarget"></a>  CBitmapRenderTarget::m_pBitmapRenderTarget

ID2D1BitmapRenderTarget nesneye bir işaretçi.

```
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;
```

##  <a name="operator_id2d1bitmaprendertarget_star"></a>  CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *

Döndürür ID2D1BitmapRenderTarget arabirimi

```
operator ID2D1BitmapRenderTarget*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1BitmapRenderTarget arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
