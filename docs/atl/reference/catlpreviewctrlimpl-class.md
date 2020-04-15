---
title: CAtlPreviewCtrlImpl Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
ms.openlocfilehash: 1ccd01bc4d48dc088538f4799b595cce3fb910ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321364"
---
# <a name="catlpreviewctrlimpl-class"></a>CAtlPreviewCtrlImpl Sınıfı

Bu sınıf, Zengin Önizleme için Shell tarafından sağlanan ana bilgisayar penceresine yerleştirilen bir pencerenin ATL uygulamasıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::~CAtlPreviewCtrlImpl](#dtor)|Bir önizleme denetim nesnesini yok eder.|
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|Bir önizleme denetim nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::Oluştur](#create)|Windows penceresini oluşturmak için Zengin Önizleme işleyicisi tarafından çağrılır.|
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|Bu denetimi yok etmesi gerektiğinde Zengin Önizleme işleyicisi tarafından çağrılır.|
|[CAtlPreviewCtrlImpl::Odak](#focus)|Bu denetime giriş odağı ayarlar.|
|[CAtlPreviewCtrlImpl::OnPaint](#onpaint)|WM_PAINT iletisini işler.|
|[CAtlPreviewCtrlImpl::Yeniden çiz](#redraw)|Bu denetimi yeniden çizmeyi söyler.|
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|Bu denetim için yeni bir ebeveyn ayarlar.|
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Zengin önizleme içeriğinin görsellerini ayarlaması gerektiğinde Zengin Önizleme işleyicisi tarafından çağrılır.|
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|Bu denetim için yeni bir sınırlayıcı dikdörtgen ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|Önizlemeyi işlemek için çerçeve tarafından çağrılır.|

### <a name="protected-constants"></a>Korumalı Sabitler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|Önizleme penceresinde metni görüntülemek için kullanılan yazı tipi.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::m_clrBack](#m_clrback)|Önizleme penceresinin arka plan rengi.|
|[CAtlPreviewCtrlImpl::m_clrText](#m_clrtext)|Önizleme penceresinin metin rengi.|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`TBase`

`ATL::CMessageMap`

`ATL::CWindowImplRoot<TBase>`

`ATL::CWindowImplBaseT<TBase,TWinTraits>`

[ATL::CWindowImpl\<CAtlPreviewCtrlImpl>](../../atl/reference/cwindowimpl-class.md)

`IPreviewCtrl`

`ATL::CAtlPreviewCtrlImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlpreviewctrlimpl.h

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="catlpreviewctrlimpl"></a>CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl

Bir önizleme denetim nesnesi oluşturuyor.

```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="dtor"></a>CAtlPreviewCtrlImpl::~CAtlPreviewCtrlImpl

Bir önizleme denetim nesnesini yok eder.

```
virtual ~CAtlPreviewCtrlImpl(void);
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplcreate"></a><a name="create"></a>CAtlPreviewCtrlImpl::Oluştur

Windows penceresini oluşturmak için Zengin Önizleme işleyicisi tarafından çağrılır.

```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Zengin Önizleme için Shell tarafından sağlanan ana bilgisayar penceresine bir tutamaç.

*Çhc*<br/>
Pencerenin başlangıç boyutunu ve konumunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimpldestroy"></a><a name="destroy"></a>CAtlPreviewCtrlImpl::Destroy

Bu denetimi yok etmesi gerektiğinde Zengin Önizleme işleyicisi tarafından çağrılır.

```
virtual void Destroy();
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimpldopaint"></a><a name="dopaint"></a>CAtlPreviewCtrlImpl::DoPaint

Önizlemeyi işlemek için çerçeve tarafından çağrılır.

```
virtual void DoPaint(HDC hdc);
```

### <a name="parameters"></a>Parametreler

*Hdc*<br/>
Boyama için aygıt bağlamına bir tutamaç.

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplfocus"></a><a name="focus"></a>CAtlPreviewCtrlImpl::Odak

Bu denetime giriş odağı ayarlar.

```
virtual void Focus();
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplm_clrback"></a><a name="m_clrback"></a>CAtlPreviewCtrlImpl::m_clrBack

Önizleme penceresinin arka plan rengi.

```
COLORREF m_clrBack;
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplm_clrtext"></a><a name="m_clrtext"></a>CAtlPreviewCtrlImpl::m_clrText

Önizleme penceresinin metin rengi.

```
COLORREF m_clrText;
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplm_plf"></a><a name="m_plf"></a>CAtlPreviewCtrlImpl::m_plf

Önizleme penceresinde metni görüntülemek için kullanılan yazı tipi.

```
const LOGFONTW* m_plf;
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplonpaint"></a><a name="onpaint"></a>CAtlPreviewCtrlImpl::OnPaint

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
WM_PAINT ayarlayın.

*Wparam*<br/>
Bu parametre kullanılmaz.

*Lparam*<br/>
Bu parametre kullanılmaz.

*bHandled*<br/>
Bu işlev döndüğünde TRUE içerir.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplredraw"></a><a name="redraw"></a>CAtlPreviewCtrlImpl::Yeniden çiz

Bu denetimi yeniden çizmeyi söyler.

```
virtual void Redraw();
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplsethost"></a><a name="sethost"></a>CAtlPreviewCtrlImpl::SetHost

Bu denetim için yeni bir ebeveyn ayarlar.

```
virtual void SetHost(HWND hWndParent);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Yeni üst pencerenin tutamacı.

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>CAtlPreviewCtrlImpl::SetPreviewVisuals

Zengin önizleme içeriğinin görsellerini ayarlaması gerektiğinde Zengin Önizleme işleyicisi tarafından çağrılır.

```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```

### <a name="parameters"></a>Parametreler

*clrGeri*<br/>
Önizleme penceresinin arka plan rengi.

*clrMetin*<br/>
Önizleme penceresinin metin rengi.

*plf*<br/>
Önizleme penceresinde metni görüntülemek için kullanılan yazı tipi.

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplsetrect"></a><a name="setrect"></a>CAtlPreviewCtrlImpl::SetRect

Bu denetim için yeni bir sınırlayıcı dikdörtgen ayarlar.

```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```

### <a name="parameters"></a>Parametreler

*Çhc*<br/>
Önizleme denetiminin yeni boyutunu ve konumunu belirtir.

*bRedraw*<br/>
Denetimin yeniden çizilip çizilmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)
