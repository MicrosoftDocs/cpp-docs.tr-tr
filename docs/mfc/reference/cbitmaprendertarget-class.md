---
title: CBitmapRenderTarget Sınıfı
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
ms.openlocfilehash: 6249c121f7bcca0675a8138baef0e2cdc9e632d8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352597"
---
# <a name="cbitmaprendertarget-class"></a>CBitmapRenderTarget Sınıfı

ID2D1BitmapRenderTarget için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CBitmapRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|Bir CBitmapRenderTarget nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CBitmapRenderTarget::Ekle](#attach)|Nesneye varolan render hedef arabirimi ataşır|
|[CBitmapRenderHedef::Detach](#detach)|Ayırıcılar hedef arabirimi nesneden işleme|
|[CBitmapRenderTarget::GetBitmap](#getbitmap)|Bu oluşturma hedefiiçin bit eşlemi alır. Döndürülen bit eşlemi çizim işlemleri için kullanılabilir.|
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|ID2D1BitmapRenderTarget arabirimini döndürür|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CBitmapRenderTarget::operatör ID2D1BitmapRenderTarget*](#operator_id2d1bitmaprendertarget_star)|ID2D1BitmapRenderTarget arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CBitmapRenderHedef::m_pBitmapRenderTarget](#m_pbitmaprendertarget)|BIR ID2D1BitmapRenderTarget nesnesi için bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

`CBitmapRenderTarget`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cbitmaprendertargetattach"></a><a name="attach"></a>CBitmapRenderTarget::Ekle

Nesneye varolan render hedef arabirimi ataşır

```
void Attach(ID2D1BitmapRenderTarget* pTarget);
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
Varolan render hedef arabirimi. NULL olamaz

## <a name="cbitmaprendertargetcbitmaprendertarget"></a><a name="cbitmaprendertarget"></a>CBitmapRenderTarget::CBitmapRenderTarget

Bir CBitmapRenderTarget nesnesi oluşturur.

```
CBitmapRenderTarget();
```

## <a name="cbitmaprendertargetdetach"></a><a name="detach"></a>CBitmapRenderHedef::Detach

Ayırıcılar hedef arabirimi nesneden işleme

```
ID2D1BitmapRenderTarget* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Hedef arabirimini ayırılamak için işaretçi.

## <a name="cbitmaprendertargetgetbitmap"></a><a name="getbitmap"></a>CBitmapRenderTarget::GetBitmap

Bu oluşturma hedefiiçin bit eşlemi alır. Döndürülen bit eşlemi çizim işlemleri için kullanılabilir.

```
BOOL GetBitmap(CD2DBitmap& bitmap);
```

### <a name="parameters"></a>Parametreler

*Bitmap*<br/>
Bu yöntem döndüğünde, bu işleme hedefi için geçerli bit eşlemi içerir. Bu bit eşlemi çizim işlemleri için kullanılabilir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cbitmaprendertargetgetbitmaprendertarget"></a><a name="getbitmaprendertarget"></a>CBitmapRenderTarget::GetBitmapRenderTarget

ID2D1BitmapRenderTarget arabirimini döndürür

```
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1BitmapRenderTarget arabirimine veya NULL'a işaretçi.

## <a name="cbitmaprendertargetm_pbitmaprendertarget"></a><a name="m_pbitmaprendertarget"></a>CBitmapRenderHedef::m_pBitmapRenderTarget

BIR ID2D1BitmapRenderTarget nesnesi için bir işaretçi.

```
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;
```

## <a name="cbitmaprendertargetoperator-id2d1bitmaprendertarget"></a><a name="operator_id2d1bitmaprendertarget_star"></a>CBitmapRenderTarget::operatör ID2D1BitmapRenderTarget*

ID2D1BitmapRenderTarget arabirimini döndürür

```
operator ID2D1BitmapRenderTarget*();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1BitmapRenderTarget arabirimine veya NULL'a işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
