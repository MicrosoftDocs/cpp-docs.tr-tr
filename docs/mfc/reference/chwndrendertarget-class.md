---
title: CHwndRenderTarget Sınıfı
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
ms.openlocfilehash: 24cf4127c2f429f66143af3a0f49625f23a4e6ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372460"
---
# <a name="chwndrendertarget-class"></a>CHwndRenderTarget Sınıfı

ID2D1HwndRenderTarget için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CHwndRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CHwndRenderHedef::CHwndRenderHedef](#chwndrendertarget)|HWND bir CHwndRenderTarget nesnesi oluşturmaz.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CHwndRenderTarget::Ekle](#attach)|Nesneye varolan render hedef arabirimi ataşır|
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|Bu işleme hedefiyle ilişkili HWND'nin tıkanıp tıkanmadığını gösterir.|
|[CHwndRenderTarget::Oluştur](#create)|Pencereyle ilişkili bir render hedefi oluşturur|
|[CHwndRenderHedef::Detach](#detach)|Ayırıcılar hedef arabirimi nesneden işleme|
|[CHwndRenderHedef::GetHwnd](#gethwnd)|Bu işleme hedefiyle ilişkili HWND'yi döndürür.|
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|ID2D1HwndRenderTarget arabirimini döndürür.|
|[CHwndRenderTarget::Yeniden Oluşturma](#recreate)|Pencereyle ilişkili bir render hedefini yeniden oluşturur|
|[CHwndRenderTarget::Yeniden boyutlandırma](#resize)|Render hedefinin boyutunu belirtilen piksel boyutuyla değiştirir|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CHwndRenderTarget::operatör ID2D1HwndRenderTarget*](#operator_id2d1hwndrendertarget_star)|ID2D1HwndRenderTarget arabirimini döndürür.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|ID2D1HwndRenderTarget nesnesine işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CHwndRenderHedef](../../mfc/reference/chwndrendertarget-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="chwndrendertargetattach"></a><a name="attach"></a>CHwndRenderTarget::Ekle

Nesneye varolan render hedef arabirimi ataşır

```
void Attach(ID2D1HwndRenderTarget* pTarget);
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
Varolan render hedef arabirimi. NULL olamaz

## <a name="chwndrendertargetcheckwindowstate"></a><a name="checkwindowstate"></a>CHwndRenderTarget::CheckWindowState

Bu işleme hedefiyle ilişkili HWND'nin tıkanıp tıkanmadığını gösterir.

```
D2D1_WINDOW_STATE CheckWindowState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu işleme hedefiyle ilişkili HWND'nin tıkanıp tıkanmadığını gösteren bir değer.

## <a name="chwndrendertargetchwndrendertarget"></a><a name="chwndrendertarget"></a>CHwndRenderHedef::CHwndRenderHedef

HWND bir CHwndRenderTarget nesnesi oluşturmaz.

```
CHwndRenderTarget(HWND hwnd = NULL);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
Bu render hedefi ile ilişkili HWND

## <a name="chwndrendertargetcreate"></a><a name="create"></a>CHwndRenderTarget::Oluştur

Pencereyle ilişkili bir render hedefi oluşturur

```
BOOL Create(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
Bu render hedefi ile ilişkili HWND

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür

## <a name="chwndrendertargetdetach"></a><a name="detach"></a>CHwndRenderHedef::Detach

Ayırıcılar hedef arabirimi nesneden işleme

```
ID2D1HwndRenderTarget* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Hedef arabirimini ayırılamak için işaretçi.

## <a name="chwndrendertargetgethwnd"></a><a name="gethwnd"></a>CHwndRenderHedef::GetHwnd

Bu işleme hedefiyle ilişkili HWND'yi döndürür.

```
HWND GetHwnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

HWND bu render hedefi ile ilişkili.

## <a name="chwndrendertargetgethwndrendertarget"></a><a name="gethwndrendertarget"></a>CHwndRenderTarget::GetHwndRenderTarget

ID2D1HwndRenderTarget arabirimini döndürür.

```
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1HwndRenderTarget arabirimine veya NULL'a işaretçi.

## <a name="chwndrendertargetm_phwndrendertarget"></a><a name="m_phwndrendertarget"></a>CHwndRenderTarget::m_pHwndRenderTarget

ID2D1HwndRenderTarget nesnesine işaretçi.

```
ID2D1HwndRenderTarget* m_pHwndRenderTarget;
```

## <a name="chwndrendertargetoperator-id2d1hwndrendertarget"></a><a name="operator_id2d1hwndrendertarget_star"></a>CHwndRenderTarget::operatör ID2D1HwndRenderTarget*

ID2D1HwndRenderTarget arabirimini döndürür.

```
operator ID2D1HwndRenderTarget*();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1HwndRenderTarget arabirimine veya NULL'a işaretçi.

## <a name="chwndrendertargetrecreate"></a><a name="recreate"></a>CHwndRenderTarget::Yeniden Oluşturma

Pencereyle ilişkili bir render hedefini yeniden oluşturur

```
BOOL ReCreate(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
Bu render hedefi ile ilişkili HWND

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="chwndrendertargetresize"></a><a name="resize"></a>CHwndRenderTarget::Yeniden boyutlandırma

Render hedefinin boyutunu belirtilen piksel boyutuyla değiştirir

```
BOOL Resize(const CD2DSizeU& size);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Aygıt piksellerinde render hedefinin yeni boyutu

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
