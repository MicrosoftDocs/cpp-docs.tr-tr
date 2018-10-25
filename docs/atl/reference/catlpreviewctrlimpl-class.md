---
title: Catlpreviewctrlımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Create
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Destroy
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Focus
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::OnPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Redraw
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetHost
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetPreviewVisuals
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetRect
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::DoPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_plf
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrBack
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrText
dev_langs:
- C++
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 575af8c372e0d935e1ca7c262a70466a97885648
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053961"
---
# <a name="catlpreviewctrlimpl-class"></a>Catlpreviewctrlımpl sınıfı

Bu sınıf bir kabuk tarafından sağlanan Zengin Önizleme için barındırıcı penceresine yerleştirilen bir pencere ATL uygulamasıdır.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Catlpreviewctrlımpl:: ~ Catlpreviewctrlımpl](#dtor)|Önizleme denetim nesnesi destructs.|
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|Önizleme denetim nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::Create](#create)|Windows penceresi oluşturmak için Zengin Önizleme işleyici tarafından çağrılır.|
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|Bu denetim yok etmek gereken Zengin Önizleme işleyici tarafından çağrılır.|
|[CAtlPreviewCtrlImpl::Focus](#focus)|Ayarlar, bu denetim odağı girin.|
|[CAtlPreviewCtrlImpl::OnPaint](#onpaint)|WM_PAINT iletisini işler.|
|[CAtlPreviewCtrlImpl::Redraw](#redraw)|Bu denetimi yeniden düzenlenen söyler.|
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|Bu denetim için yeni bir üst ayarlar.|
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Görsellerin Zengin Önizleme ihtiyaç duyduğu içerik Zengin Önizleme işleyici tarafından çağrılır.|
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|Bu denetim için yeni sınırlayıcı bir dikdörtgen ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|Önizleme işlemek için framework tarafından çağırılır.|

### <a name="protected-constants"></a>Korumalı sabitleri

|Ad|Açıklama|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|Önizleme metni görüntülemede kullanılacak yazı tipi.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::m_clrBack](#m_clrback)|Önizleme penceresini arka plan rengi.|
|[CAtlPreviewCtrlImpl::m_clrText](#m_clrtext)|Önizleme penceresini metin rengi.|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`TBase`

`ATL::CMessageMap`

`ATL::CWindowImplRoot<TBase>`

`ATL::CWindowImplBaseT<TBase,TWinTraits>`

[ATL::CWindowImpl\<Catlpreviewctrlımpl >](../../atl/reference/cwindowimpl-class.md)

`IPreviewCtrl`

`ATL::CAtlPreviewCtrlImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlpreviewctrlimpl.h

##  <a name="catlpreviewctrlimpl"></a>  CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl

Önizleme denetim nesnesi oluşturur.

```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```

### <a name="remarks"></a>Açıklamalar

##  <a name="dtor"></a>  Catlpreviewctrlımpl:: ~ Catlpreviewctrlımpl

Önizleme denetim nesnesi destructs.

```
virtual ~CAtlPreviewCtrlImpl(void);
```

### <a name="remarks"></a>Açıklamalar

##  <a name="create"></a>  CAtlPreviewCtrlImpl::Create

Windows penceresi oluşturmak için Zengin Önizleme işleyici tarafından çağrılır.

```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Kabuk tarafından sağlanan Zengin Önizleme için ana penceresi için bir tanıtıcı.

*ÇHC*<br/>
Başlangıç boyutu ve pencerenin konumunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="destroy"></a>  CAtlPreviewCtrlImpl::Destroy

Bu denetim yok etmek gereken Zengin Önizleme işleyici tarafından çağrılır.

```
virtual void Destroy();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="dopaint"></a>  CAtlPreviewCtrlImpl::DoPaint

Önizleme işlemek için framework tarafından çağırılır.

```
virtual void DoPaint(HDC hdc);
```

### <a name="parameters"></a>Parametreler

*hdc*<br/>
Boyama için cihaz bağlamı için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

##  <a name="focus"></a>  CAtlPreviewCtrlImpl::Focus

Ayarlar, bu denetim odağı girin.

```
virtual void Focus();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_clrback"></a>  CAtlPreviewCtrlImpl::m_clrBack

Önizleme penceresini arka plan rengi.

```
COLORREF m_clrBack;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_clrtext"></a>  CAtlPreviewCtrlImpl::m_clrText

Önizleme penceresini metin rengi.

```
COLORREF m_clrText;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_plf"></a>  CAtlPreviewCtrlImpl::m_plf

Önizleme metni görüntülemede kullanılacak yazı tipi.

```
const LOGFONTW* m_plf;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onpaint"></a>  CAtlPreviewCtrlImpl::OnPaint

WM_PAINT iletisini işler.

```
LRESULT OnPaint(
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parametreler

*nMsg*<br/>
WM_PAINT için ayarlayın.

*wParam*<br/>
Bu parametre kullanılmaz.

*lParam*<br/>
Bu parametre kullanılmaz.

*bHandled*<br/>
Bu işlev döndürüldüğünde TRUE içerir.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="redraw"></a>  CAtlPreviewCtrlImpl::Redraw

Bu denetimi yeniden düzenlenen söyler.

```
virtual void Redraw();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="sethost"></a>  CAtlPreviewCtrlImpl::SetHost

Bu denetim için yeni bir üst ayarlar.

```
virtual void SetHost(HWND hWndParent);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Yeni bir ana penceresi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

##  <a name="setpreviewvisuals"></a>  CAtlPreviewCtrlImpl::SetPreviewVisuals

Görsellerin Zengin Önizleme ihtiyaç duyduğu içerik Zengin Önizleme işleyici tarafından çağrılır.

```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```

### <a name="parameters"></a>Parametreler

*clrBack*<br/>
Önizleme penceresini arka plan rengi.

*clrText*<br/>
Önizleme penceresini metin rengi.

*plf*<br/>
Önizleme metni görüntülemede kullanılacak yazı tipi.

### <a name="remarks"></a>Açıklamalar

##  <a name="setrect"></a>  CAtlPreviewCtrlImpl::SetRect

Bu denetim için yeni sınırlayıcı bir dikdörtgen ayarlar.

```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```

### <a name="parameters"></a>Parametreler

*ÇHC*<br/>
Yeni boyutunu ve önizleme denetimin konumunu belirtir.

*bRedraw*<br/>
Denetim yeniden olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca Bkz.

[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)
