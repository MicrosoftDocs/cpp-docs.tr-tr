---
description: 'Daha fazla bilgi edinin: CDCRenderTarget sınıfı'
title: CDCRenderTarget sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
helpviewer_keywords:
- CDCRenderTarget [MFC], CDCRenderTarget
- CDCRenderTarget [MFC], Attach
- CDCRenderTarget [MFC], BindDC
- CDCRenderTarget [MFC], Create
- CDCRenderTarget [MFC], Detach
- CDCRenderTarget [MFC], GetDCRenderTarget
- CDCRenderTarget [MFC], m_pDCRenderTarget
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
ms.openlocfilehash: 3959321bbd6274c821b1f02be5962b23ec9dbc95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185329"
---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget sınıfı

ID2D1DCRenderTarget için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CDCRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDCRenderTarget:: CDCRenderTarget](#cdcrendertarget)|CDCRenderTarget nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDCRenderTarget:: Attach](#attach)|Mevcut işleme hedefi arabirimini nesneye iliştirir|
|[CDCRenderTarget:: BindDC](#binddc)|İşleme hedefini, çizim komutlarını verdiği cihaz bağlamına bağlar|
|[CDCRenderTarget:: Create](#create)|CDCRenderTarget oluşturur.|
|[CDCRenderTarget::D etach](#detach)|Nesneden işleme hedefi arabirimini ayırır|
|[CDCRenderTarget:: GetDCRenderTarget](#getdcrendertarget)|ID2D1DCRenderTarget arabirimini döndürür|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CDCRenderTarget:: operator ID2D1DCRenderTarget *](#operator_id2d1dcrendertarget_star)|ID2D1DCRenderTarget arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDCRenderTarget:: m_pDCRenderTarget](#m_pdcrendertarget)|ID2D1DCRenderTarget nesnesine yönelik bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cdcrendertargetattach"></a><a name="attach"></a> CDCRenderTarget:: Attach

Mevcut işleme hedefi arabirimini nesneye iliştirir

```cpp
void Attach(ID2D1DCRenderTarget* pTarget);
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
Mevcut işleme hedefi arabirimi. NULL olamaz

## <a name="cdcrendertargetbinddc"></a><a name="binddc"></a> CDCRenderTarget:: BindDC

İşleme hedefini, çizim komutlarını verdiği cihaz bağlamına bağlar

```
BOOL BindDC(
    const CDC& dc,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
İşleme hedefinin çizim komutlarını verdiği cihaz bağlamı

*Rect*<br/>
Tanıtıcının, işleme hedefinin bağlandığı bir cihaz bağlamına (HDC) yönelik boyutları

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cdcrendertargetcdcrendertarget"></a><a name="cdcrendertarget"></a> CDCRenderTarget:: CDCRenderTarget

CDCRenderTarget nesnesi oluşturur.

```
CDCRenderTarget();
```

## <a name="cdcrendertargetcreate"></a><a name="create"></a> CDCRenderTarget:: Create

CDCRenderTarget oluşturur.

```
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```

### <a name="parameters"></a>Parametreler

*props*<br/>
İşleme modu, piksel biçimi, uzaktan iletişim seçenekleri, DPı bilgileri ve donanım işleme için gereken en düşük DirectX desteği.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cdcrendertargetdetach"></a><a name="detach"></a> CDCRenderTarget::D etach

Nesneden işleme hedefi arabirimini ayırır

```
ID2D1DCRenderTarget* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış işleme hedefi arabirimine yönelik işaretçi.

## <a name="cdcrendertargetgetdcrendertarget"></a><a name="getdcrendertarget"></a> CDCRenderTarget:: GetDCRenderTarget

ID2D1DCRenderTarget arabirimini döndürür

```
ID2D1DCRenderTarget* GetDCRenderTarget();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1DCRenderTarget arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cdcrendertargetm_pdcrendertarget"></a><a name="m_pdcrendertarget"></a> CDCRenderTarget:: m_pDCRenderTarget

ID2D1DCRenderTarget nesnesine yönelik bir işaretçi.

```
ID2D1DCRenderTarget* m_pDCRenderTarget;
```

## <a name="cdcrendertargetoperator-id2d1dcrendertarget"></a><a name="operator_id2d1dcrendertarget_star"></a> CDCRenderTarget:: operator ID2D1DCRenderTarget *

ID2D1DCRenderTarget arabirimini döndürür

```
operator ID2D1DCRenderTarget*();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1DCRenderTarget arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
