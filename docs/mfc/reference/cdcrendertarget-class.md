---
title: CDCRenderTarget Sınıfı
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
ms.openlocfilehash: 790ce0f32c2325fa0ea92ca0bda64ddaa4c86c45
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375702"
---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget Sınıfı

ID2D1DCRenderTarget için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CDCRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDCRenderTarget::CDCRenderTarget](#cdcrendertarget)|BIR CDCRenderTarget nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDCRenderTarget::Ekle](#attach)|Nesneye varolan render hedef arabirimi ataşır|
|[CDCRenderTarget::BindDC](#binddc)|Render hedefini çizim komutları veren aygıt bağlamına bağlar|
|[CDCRenderTarget::Oluştur](#create)|Bir CDCRenderTarget oluşturur.|
|[CDCRenderTarget::Detach](#detach)|Ayırıcılar hedef arabirimi nesneden işleme|
|[CDCRenderTarget::GetDCRenderTarget](#getdcrendertarget)|ID2D1DCRenderTarget arabirimini döndürür|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CDCRenderTarget::operatör ID2D1DCRenderTarget*](#operator_id2d1dcrendertarget_star)|ID2D1DCRenderTarget arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDCRenderTarget::m_pDCRenderTarget](#m_pdcrendertarget)|ID2D1DCRenderTarget nesnesine işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cdcrendertargetattach"></a><a name="attach"></a>CDCRenderTarget::Ekle

Nesneye varolan render hedef arabirimi ataşır

```
void Attach(ID2D1DCRenderTarget* pTarget);
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
Varolan render hedef arabirimi. NULL olamaz

## <a name="cdcrendertargetbinddc"></a><a name="binddc"></a>CDCRenderTarget::BindDC

Render hedefini çizim komutları veren aygıt bağlamına bağlar

```
BOOL BindDC(
    const CDC& dc,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Dc*<br/>
Render hedef çizim komutları sorunları olduğu aygıt bağlamı

*Rect*<br/>
İşlem hedefinin bağlı olduğu bir aygıt bağlamına (HDC) tanıtıcının boyutları

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cdcrendertargetcdcrendertarget"></a><a name="cdcrendertarget"></a>CDCRenderTarget::CDCRenderTarget

BIR CDCRenderTarget nesnesi oluşturuyor.

```
CDCRenderTarget();
```

## <a name="cdcrendertargetcreate"></a><a name="create"></a>CDCRenderTarget::Oluştur

Bir CDCRenderTarget oluşturur.

```
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```

### <a name="parameters"></a>Parametreler

*Sahne*<br/>
İşleme modu, piksel biçimi, remoting seçenekleri, DPI bilgileri ve donanım işleme için gereken minimum DirectX desteği.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür.

## <a name="cdcrendertargetdetach"></a><a name="detach"></a>CDCRenderTarget::Detach

Ayırıcılar hedef arabirimi nesneden işleme

```
ID2D1DCRenderTarget* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Hedef arabirimini ayırılamak için işaretçi.

## <a name="cdcrendertargetgetdcrendertarget"></a><a name="getdcrendertarget"></a>CDCRenderTarget::GetDCRenderTarget

ID2D1DCRenderTarget arabirimini döndürür

```
ID2D1DCRenderTarget* GetDCRenderTarget();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1DCRenderTarget arabirimine veya NULL'a işaretçi.

## <a name="cdcrendertargetm_pdcrendertarget"></a><a name="m_pdcrendertarget"></a>CDCRenderTarget::m_pDCRenderTarget

ID2D1DCRenderTarget nesnesine işaretçi.

```
ID2D1DCRenderTarget* m_pDCRenderTarget;
```

## <a name="cdcrendertargetoperator-id2d1dcrendertarget"></a><a name="operator_id2d1dcrendertarget_star"></a>CDCRenderTarget::operatör ID2D1DCRenderTarget*

ID2D1DCRenderTarget arabirimini döndürür

```
operator ID2D1DCRenderTarget*();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1DCRenderTarget arabirimine veya NULL'a işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
