---
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
ms.openlocfilehash: 70169d2b89d9ea657898f7a96dea27556023d4e2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268284"
---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget sınıfı

ID2D1DCRenderTarget için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CDCRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDCRenderTarget::CDCRenderTarget](#cdcrendertarget)|CDCRenderTarget bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDCRenderTarget::Attach](#attach)|Varolan ekler nesnesine hedef arabirimi oluşturma|
|[CDCRenderTarget::BindDC](#binddc)|İşleme hedefi çizim komutları ermesinin cihaz bağlamına bağlar.|
|[CDCRenderTarget::Create](#create)|Bir CDCRenderTarget oluşturur.|
|[CDCRenderTarget::Detach](#detach)|İşleme hedefi arabirimi nesnesinden ayırır|
|[CDCRenderTarget::GetDCRenderTarget](#getdcrendertarget)|Döndürür ID2D1DCRenderTarget arabirimi|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CDCRenderTarget::operator ID2D1DCRenderTarget *](#operator_id2d1dcrendertarget_star)|Döndürür ID2D1DCRenderTarget arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDCRenderTarget::m_pDCRenderTarget](#m_pdcrendertarget)|ID2D1DCRenderTarget nesneye bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="attach"></a>  CDCRenderTarget::Attach

Varolan ekler nesnesine hedef arabirimi oluşturma

```
void Attach(ID2D1DCRenderTarget* pTarget);
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
Mevcut işleme hedefi arabirimi. NULL olamaz

##  <a name="binddc"></a>  CDCRenderTarget::BindDC

İşleme hedefi çizim komutları ermesinin cihaz bağlamına bağlar.

```
BOOL BindDC(
    const CDC& dc,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*DC*<br/>
İşleme hedefi çizim komutları sorunların cihaz bağlamı

*Rect*<br/>
İşleme hedefi bağlandığı bir cihaz bağlamı (HDC) tanıtıcısını boyutları

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="cdcrendertarget"></a>  CDCRenderTarget::CDCRenderTarget

CDCRenderTarget bir nesne oluşturur.

```
CDCRenderTarget();
```

##  <a name="create"></a>  CDCRenderTarget::Create

Bir CDCRenderTarget oluşturur.

```
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```

### <a name="parameters"></a>Parametreler

*Özellikler*<br/>
İşleme modu, piksel biçimi, uzaktan iletişim seçenekleri, DPI bilgi ve donanım işleme için gereken en düşük DirectX desteği.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür.

##  <a name="detach"></a>  CDCRenderTarget::Detach

İşleme hedefi arabirimi nesnesinden ayırır

```
ID2D1DCRenderTarget* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçi ayrılmış işleme hedefi arabirimi.

##  <a name="getdcrendertarget"></a>  CDCRenderTarget::GetDCRenderTarget

Döndürür ID2D1DCRenderTarget arabirimi

```
ID2D1DCRenderTarget* GetDCRenderTarget();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1DCRenderTarget arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="m_pdcrendertarget"></a>  CDCRenderTarget::m_pDCRenderTarget

ID2D1DCRenderTarget nesneye bir işaretçi.

```
ID2D1DCRenderTarget* m_pDCRenderTarget;
```

##  <a name="operator_id2d1dcrendertarget_star"></a>  CDCRenderTarget::operator ID2D1DCRenderTarget *

Döndürür ID2D1DCRenderTarget arabirimi

```
operator ID2D1DCRenderTarget*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1DCRenderTarget arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
