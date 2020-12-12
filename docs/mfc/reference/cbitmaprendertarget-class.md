---
description: 'Daha fazla bilgi edinin: CBitmapRenderTarget Class'
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
ms.openlocfilehash: a7987651c988dcf7fcd4c4decf4a2bd474ab8619
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122687"
---
# <a name="cbitmaprendertarget-class"></a>CBitmapRenderTarget sınıfı

ID2D1BitmapRenderTarget için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CBitmapRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|Bir CBitmapRenderTarget nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBitmapRenderTarget:: Attach](#attach)|Mevcut işleme hedefi arabirimini nesneye iliştirir|
|[CBitmapRenderTarget::D etach](#detach)|Nesneden işleme hedefi arabirimini ayırır|
|[CBitmapRenderTarget:: GetBitmap](#getbitmap)|Bu işleme hedefi için bit eşlemi alır. Döndürülen bit eşlem, çizim işlemleri için kullanılabilir.|
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|ID2D1BitmapRenderTarget arabirimini döndürür|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CBitmapRenderTarget:: operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|ID2D1BitmapRenderTarget arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CBitmapRenderTarget:: m_pBitmapRenderTarget](#m_pbitmaprendertarget)|ID2D1BitmapRenderTarget nesnesine yönelik bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

`CBitmapRenderTarget`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cbitmaprendertargetattach"></a><a name="attach"></a> CBitmapRenderTarget:: Attach

Mevcut işleme hedefi arabirimini nesneye iliştirir

```cpp
void Attach(ID2D1BitmapRenderTarget* pTarget);
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
Mevcut işleme hedefi arabirimi. NULL olamaz

## <a name="cbitmaprendertargetcbitmaprendertarget"></a><a name="cbitmaprendertarget"></a> CBitmapRenderTarget::CBitmapRenderTarget

Bir CBitmapRenderTarget nesnesi oluşturur.

```
CBitmapRenderTarget();
```

## <a name="cbitmaprendertargetdetach"></a><a name="detach"></a> CBitmapRenderTarget::D etach

Nesneden işleme hedefi arabirimini ayırır

```
ID2D1BitmapRenderTarget* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış işleme hedefi arabirimine yönelik işaretçi.

## <a name="cbitmaprendertargetgetbitmap"></a><a name="getbitmap"></a> CBitmapRenderTarget:: GetBitmap

Bu işleme hedefi için bit eşlemi alır. Döndürülen bit eşlem, çizim işlemleri için kullanılabilir.

```
BOOL GetBitmap(CD2DBitmap& bitmap);
```

### <a name="parameters"></a>Parametreler

*biteş*<br/>
Bu yöntem döndüğünde, bu işleme hedefi için geçerli bit eşlemi içerir. Bu bit eşlem, çizim işlemleri için kullanılabilir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cbitmaprendertargetgetbitmaprendertarget"></a><a name="getbitmaprendertarget"></a> CBitmapRenderTarget::GetBitmapRenderTarget

ID2D1BitmapRenderTarget arabirimini döndürür

```
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1BitmapRenderTarget arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cbitmaprendertargetm_pbitmaprendertarget"></a><a name="m_pbitmaprendertarget"></a> CBitmapRenderTarget:: m_pBitmapRenderTarget

ID2D1BitmapRenderTarget nesnesine yönelik bir işaretçi.

```
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;
```

## <a name="cbitmaprendertargetoperator-id2d1bitmaprendertarget"></a><a name="operator_id2d1bitmaprendertarget_star"></a> CBitmapRenderTarget:: operator ID2D1BitmapRenderTarget *

ID2D1BitmapRenderTarget arabirimini döndürür

```
operator ID2D1BitmapRenderTarget*();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1BitmapRenderTarget arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
