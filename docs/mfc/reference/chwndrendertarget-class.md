---
description: 'Daha fazla bilgi edinin: CHwndRenderTarget sınıfı'
title: CHwndRenderTarget sınıfı
ms.date: 11/04/2016
f1_keywords:
- CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::Attach
- AFXRENDERTARGET/CHwndRenderTarget::CheckWindowState
- AFXRENDERTARGET/CHwndRenderTarget::Create
- AFXRENDERTARGET/CHwndRenderTarget::Detach
- AFXRENDERTARGET/CHwndRenderTarget::GetHwnd
- AFXRENDERTARGET/CHwndRenderTarget::GetHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::ReCreate
- AFXRENDERTARGET/CHwndRenderTarget::Resize
- AFXRENDERTARGET/CHwndRenderTarget::m_pHwndRenderTarget
helpviewer_keywords:
- CHwndRenderTarget [MFC], CHwndRenderTarget
- CHwndRenderTarget [MFC], Attach
- CHwndRenderTarget [MFC], CheckWindowState
- CHwndRenderTarget [MFC], Create
- CHwndRenderTarget [MFC], Detach
- CHwndRenderTarget [MFC], GetHwnd
- CHwndRenderTarget [MFC], GetHwndRenderTarget
- CHwndRenderTarget [MFC], ReCreate
- CHwndRenderTarget [MFC], Resize
- CHwndRenderTarget [MFC], m_pHwndRenderTarget
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
ms.openlocfilehash: 3a3058105fff5e5ac304f2cc980cd93f2bac70a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143643"
---
# <a name="chwndrendertarget-class"></a>CHwndRenderTarget sınıfı

ID2D1HwndRenderTarget için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CHwndRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHwndRenderTarget:: CHwndRenderTarget](#chwndrendertarget)|HWND 'den bir CHwndRenderTarget nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHwndRenderTarget:: Attach](#attach)|Mevcut işleme hedefi arabirimini nesneye iliştirir|
|[CHwndRenderTarget:: CheckWindowState](#checkwindowstate)|Bu işleme hedefi ile ilişkilendirilen HWND 'in, occluded olup olmadığını gösterir.|
|[CHwndRenderTarget:: oluştur](#create)|Pencereyle ilişkili bir işleme hedefi oluşturur|
|[CHwndRenderTarget::D etach](#detach)|Nesneden işleme hedefi arabirimini ayırır|
|[CHwndRenderTarget:: GetHwnd](#gethwnd)|Bu işleme hedefi ile ilişkili HWND 'yi döndürür.|
|[CHwndRenderTarget:: GetHwndRenderTarget](#gethwndrendertarget)|ID2D1HwndRenderTarget arabirimini döndürür.|
|[CHwndRenderTarget:: yeniden oluştur](#recreate)|Pencereyle ilişkili bir işleme hedefini yeniden oluşturur|
|[CHwndRenderTarget:: yeniden boyutlandır](#resize)|Oluşturma hedefinin boyutunu belirtilen piksel boyutuna dönüştürür|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CHwndRenderTarget:: operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|ID2D1HwndRenderTarget arabirimini döndürür.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CHwndRenderTarget:: m_pHwndRenderTarget](#m_phwndrendertarget)|ID2D1HwndRenderTarget nesnesine yönelik bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="chwndrendertargetattach"></a><a name="attach"></a> CHwndRenderTarget:: Attach

Mevcut işleme hedefi arabirimini nesneye iliştirir

```cpp
void Attach(ID2D1HwndRenderTarget* pTarget);
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
Mevcut işleme hedefi arabirimi. NULL olamaz

## <a name="chwndrendertargetcheckwindowstate"></a><a name="checkwindowstate"></a> CHwndRenderTarget:: CheckWindowState

Bu işleme hedefi ile ilişkilendirilen HWND 'in, occluded olup olmadığını gösterir.

```
D2D1_WINDOW_STATE CheckWindowState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu işleme hedefi ile ilişkilendirilen HWND 'in, occluded olup olmadığını gösteren bir değer.

## <a name="chwndrendertargetchwndrendertarget"></a><a name="chwndrendertarget"></a> CHwndRenderTarget:: CHwndRenderTarget

HWND 'den bir CHwndRenderTarget nesnesi oluşturur.

```
CHwndRenderTarget(HWND hwnd = NULL);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
Bu işleme hedefi ile ilişkilendirilen HWND

## <a name="chwndrendertargetcreate"></a><a name="create"></a> CHwndRenderTarget:: oluştur

Pencereyle ilişkili bir işleme hedefi oluşturur

```
BOOL Create(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
Bu işleme hedefi ile ilişkilendirilen HWND

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür

## <a name="chwndrendertargetdetach"></a><a name="detach"></a> CHwndRenderTarget::D etach

Nesneden işleme hedefi arabirimini ayırır

```
ID2D1HwndRenderTarget* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış işleme hedefi arabirimine yönelik işaretçi.

## <a name="chwndrendertargetgethwnd"></a><a name="gethwnd"></a> CHwndRenderTarget:: GetHwnd

Bu işleme hedefi ile ilişkili HWND 'yi döndürür.

```
HWND GetHwnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu işleme hedefi ile ilişkilendirilen HWND.

## <a name="chwndrendertargetgethwndrendertarget"></a><a name="gethwndrendertarget"></a> CHwndRenderTarget:: GetHwndRenderTarget

ID2D1HwndRenderTarget arabirimini döndürür.

```
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1HwndRenderTarget arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="chwndrendertargetm_phwndrendertarget"></a><a name="m_phwndrendertarget"></a> CHwndRenderTarget:: m_pHwndRenderTarget

ID2D1HwndRenderTarget nesnesine yönelik bir işaretçi.

```
ID2D1HwndRenderTarget* m_pHwndRenderTarget;
```

## <a name="chwndrendertargetoperator-id2d1hwndrendertarget"></a><a name="operator_id2d1hwndrendertarget_star"></a> CHwndRenderTarget:: operator ID2D1HwndRenderTarget *

ID2D1HwndRenderTarget arabirimini döndürür.

```
operator ID2D1HwndRenderTarget*();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1HwndRenderTarget arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="chwndrendertargetrecreate"></a><a name="recreate"></a> CHwndRenderTarget:: yeniden oluştur

Pencereyle ilişkili bir işleme hedefini yeniden oluşturur

```
BOOL ReCreate(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
Bu işleme hedefi ile ilişkilendirilen HWND

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="chwndrendertargetresize"></a><a name="resize"></a> CHwndRenderTarget:: yeniden boyutlandır

Oluşturma hedefinin boyutunu belirtilen piksel boyutuna dönüştürür

```
BOOL Resize(const CD2DSizeU& size);
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Oluşturma hedefinin cihaz piksellerindeki yeni boyutu

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
