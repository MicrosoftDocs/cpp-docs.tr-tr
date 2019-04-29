---
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
ms.openlocfilehash: bf446cdf1ea064943ff92d66ac89b0e4177e6910
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345792"
---
# <a name="chwndrendertarget-class"></a>CHwndRenderTarget sınıfı

ID2D1HwndRenderTarget için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CHwndRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|Hwnd'inden CHwndRenderTarget bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHwndRenderTarget::Attach](#attach)|Varolan ekler nesnesine hedef arabirimi oluşturma|
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|Bu işleme hedefi ile ilişkili HWND occluded olup olmadığını gösterir.|
|[CHwndRenderTarget::Create](#create)|Pencere ile ilgili bir işleme hedefi oluşturur|
|[CHwndRenderTarget::Detach](#detach)|İşleme hedefi arabirimi nesnesinden ayırır|
|[CHwndRenderTarget::GetHwnd](#gethwnd)|İşleme hedefi ile ilişkili HWND döndürür.|
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|ID2D1HwndRenderTarget arabirimi döndürür.|
|[CHwndRenderTarget::ReCreate](#recreate)|Pencere ile ilgili bir işleme hedefi yeniden oluşturur|
|[CHwndRenderTarget::Resize](#resize)|Belirtilen piksel boyutuna oluşturma hedef boyutunu değiştirir|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|ID2D1HwndRenderTarget arabirimi döndürür.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|ID2D1HwndRenderTarget nesneye bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="attach"></a>  CHwndRenderTarget::Attach

Varolan ekler nesnesine hedef arabirimi oluşturma

```
void Attach(ID2D1HwndRenderTarget* pTarget);
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
Mevcut işleme hedefi arabirimi. NULL olamaz

##  <a name="checkwindowstate"></a>  CHwndRenderTarget::CheckWindowState

Bu işleme hedefi ile ilişkili HWND occluded olup olmadığını gösterir.

```
D2D1_WINDOW_STATE CheckWindowState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şununla ilişkili HWND hedef işlenip işlenmeyeceğini gösteren bir değer occluded.

##  <a name="chwndrendertarget"></a>  CHwndRenderTarget::CHwndRenderTarget

Hwnd'inden CHwndRenderTarget bir nesne oluşturur.

```
CHwndRenderTarget(HWND hwnd = NULL);
```

### <a name="parameters"></a>Parametreler

*HWND*<br/>
Şununla ilişkili HWND hedef işleme

##  <a name="create"></a>  CHwndRenderTarget::Create

Pencere ile ilgili bir işleme hedefi oluşturur

```
BOOL Create(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*hWnd*<br/>
Şununla ilişkili HWND hedef işleme

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür

##  <a name="detach"></a>  CHwndRenderTarget::Detach

İşleme hedefi arabirimi nesnesinden ayırır

```
ID2D1HwndRenderTarget* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçi ayrılmış işleme hedefi arabirimi.

##  <a name="gethwnd"></a>  CHwndRenderTarget::GetHwnd

İşleme hedefi ile ilişkili HWND döndürür.

```
HWND GetHwnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şununla ilişkili HWND hedef işleyin.

##  <a name="gethwndrendertarget"></a>  CHwndRenderTarget::GetHwndRenderTarget

ID2D1HwndRenderTarget arabirimi döndürür.

```
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1HwndRenderTarget arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="m_phwndrendertarget"></a>  CHwndRenderTarget::m_pHwndRenderTarget

ID2D1HwndRenderTarget nesneye bir işaretçi.

```
ID2D1HwndRenderTarget* m_pHwndRenderTarget;
```

##  <a name="operator_id2d1hwndrendertarget_star"></a>  CHwndRenderTarget::operator ID2D1HwndRenderTarget *

ID2D1HwndRenderTarget arabirimi döndürür.

```
operator ID2D1HwndRenderTarget*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1HwndRenderTarget arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="recreate"></a>  CHwndRenderTarget::ReCreate

Pencere ile ilgili bir işleme hedefi yeniden oluşturur

```
BOOL ReCreate(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*hWnd*<br/>
Şununla ilişkili HWND hedef işleme

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="resize"></a>  CHwndRenderTarget::Resize

Belirtilen piksel boyutuna oluşturma hedef boyutunu değiştirir

```
BOOL Resize(const CD2DSizeU& size);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Cihaz piksel cinsinden işleme hedefi yeni boyutu

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
