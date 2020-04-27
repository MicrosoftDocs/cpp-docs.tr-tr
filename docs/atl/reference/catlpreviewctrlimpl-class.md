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
ms.openlocfilehash: fd94d0d6fe43d80b45def3f747c7b7d558de31d4
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167883"
---
# <a name="catlpreviewctrlimpl-class"></a>CAtlPreviewCtrlImpl Sınıfı

Bu sınıf, kabuk tarafından zengin önizleme için sunulan bir konak penceresine yerleştirilmiş bir pencerenin ATL uygulamasıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Catlönizleme Ctrlımpl:: ~ Catlönizleme Ctrlımpl](#dtor)|Bir önizleme denetim nesnesinin yapılarını kaldırır.|
|[Catlönizleme Ctrlımpl:: Catlönizleme Ctrlımpl](#catlpreviewctrlimpl)|Bir önizleme denetim nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Catlönizleme Ctrlımpl:: Create](#create)|Windows penceresini oluşturmak için zengin bir önizleme işleyicisi tarafından çağırılır.|
|[Catlönizleme Ctrlımpl::D estroy](#destroy)|Bu denetimi yok etmeniz gerektiğinde zengin bir önizleme işleyicisi tarafından çağırılır.|
|[Catlönizleme Ctrlımpl:: Focus](#focus)|Giriş odağını bu denetime ayarlar.|
|[Catlönizleme Ctrlımpl:: OnPaint](#onpaint)|WM_PAINT iletisini işler.|
|[Catlönizleme Ctrlımpl:: yeniden Çiz](#redraw)|Bu denetime yeniden çizim söyler.|
|[Catlönizleme Ctrlımpl:: SetHost](#sethost)|Bu denetim için yeni bir üst ayarlar.|
|[Catlönizleme Ctrlımpl:: Setönizleme görselleri](#setpreviewvisuals)|Zengin önizleme içeriği görselleri ayarlaması gerektiğinde zengin bir önizleme işleyicisi tarafından çağırılır.|
|[Catlönizleme Ctrlımpl:: SetRect](#setrect)|Bu denetim için yeni bir sınırlayıcı dikdörtgen ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Catlönizleme Ctrlımpl::D oPaint](#dopaint)|Önizlemeyi işlemek için Framework tarafından çağırılır.|

### <a name="protected-constants"></a>Korunan sabitler

|Adı|Açıklama|
|----------|-----------------|
|[Catlönizleme Ctrlımpl:: m_plf](#m_plf)|Önizleme penceresinde metin görüntülemek için kullanılan yazı tipi.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[Catlönizleme Ctrlımpl:: m_clrBack](#m_clrback)|Önizleme penceresinin arka plan rengi.|
|[Catlönizleme Ctrlımpl:: m_clrText](#m_clrtext)|Önizleme penceresinin metin rengi.|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`TBase`

`ATL::CMessageMap`

`ATL::CWindowImplRoot<TBase>`

`ATL::CWindowImplBaseT<TBase,TWinTraits>`

[ATL:: CWindowImpl\<catlönizleme ctrlimpl>](../../atl/reference/cwindowimpl-class.md)

`IPreviewCtrl`

`ATL::CAtlPreviewCtrlImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlönizleme ctrlimpl. h

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="catlpreviewctrlimpl"></a>Catlönizleme Ctrlımpl:: Catlönizleme Ctrlımpl

Bir önizleme denetim nesnesi oluşturur.

```cpp
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="dtor"></a>Catlönizleme Ctrlımpl:: ~ Catlönizleme Ctrlımpl

Bir önizleme denetim nesnesinin yapılarını kaldırır.

```cpp
virtual ~CAtlPreviewCtrlImpl(void);
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplcreate"></a><a name="create"></a>Catlönizleme Ctrlımpl:: Create

Windows penceresini oluşturmak için zengin bir önizleme işleyicisi tarafından çağırılır.

```cpp
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Zengin Önizleme için kabuğun sağladığı konak penceresine yönelik bir tanıtıcı.

*PRC*<br/>
Pencerenin başlangıç boyutunu ve konumunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimpldestroy"></a><a name="destroy"></a>Catlönizleme Ctrlımpl::D estroy

Bu denetimi yok etmeniz gerektiğinde zengin bir önizleme işleyicisi tarafından çağırılır.

```cpp
virtual void Destroy();
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimpldopaint"></a><a name="dopaint"></a>Catlönizleme Ctrlımpl::D oPaint

Önizlemeyi işlemek için Framework tarafından çağırılır.

```cpp
virtual void DoPaint(HDC hdc);
```

### <a name="parameters"></a>Parametreler

*HDC*<br/>
Boyama için bir cihaz bağlamı tutamacı.

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplfocus"></a><a name="focus"></a>Catlönizleme Ctrlımpl:: Focus

Giriş odağını bu denetime ayarlar.

```cpp
virtual void Focus();
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplm_clrback"></a><a name="m_clrback"></a>Catlönizleme Ctrlımpl:: m_clrBack

Önizleme penceresinin arka plan rengi.

```cpp
COLORREF m_clrBack;
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplm_clrtext"></a><a name="m_clrtext"></a>Catlönizleme Ctrlımpl:: m_clrText

Önizleme penceresinin metin rengi.

```cpp
COLORREF m_clrText;
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplm_plf"></a><a name="m_plf"></a>Catlönizleme Ctrlımpl:: m_plf

Önizleme penceresinde metin görüntülemek için kullanılan yazı tipi.

```cpp
const LOGFONTW* m_plf;
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplonpaint"></a><a name="onpaint"></a>Catlönizleme Ctrlımpl:: OnPaint

WM_PAINT iletisini işler.

```cpp
LRESULT OnPaint(
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parametreler

*nMsg*<br/>
WM_PAINT olarak ayarlayın.

*wParam*<br/>
Bu parametre kullanılmaz.

*lParam*<br/>
Bu parametre kullanılmaz.

*Bişlenmiş*<br/>
Bu işlev döndürüldüğünde, TRUE değerini içerir.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplredraw"></a><a name="redraw"></a>Catlönizleme Ctrlımpl:: yeniden Çiz

Bu denetime yeniden çizim söyler.

```cpp
virtual void Redraw();
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplsethost"></a><a name="sethost"></a>Catlönizleme Ctrlımpl:: SetHost

Bu denetim için yeni bir üst ayarlar.

```cpp
virtual void SetHost(HWND hWndParent);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Yeni ana pencereye yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>Catlönizleme Ctrlımpl:: Setönizleme görselleri

Zengin önizleme içeriği görselleri ayarlaması gerektiğinde zengin bir önizleme işleyicisi tarafından çağırılır.

```cpp
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```

### <a name="parameters"></a>Parametreler

*clrBack*<br/>
Önizleme penceresinin arka plan rengi.

*clrText*<br/>
Önizleme penceresinin metin rengi.

*PLF*<br/>
Önizleme penceresinde metin görüntülemek için kullanılan yazı tipi.

### <a name="remarks"></a>Açıklamalar

## <a name="catlpreviewctrlimplsetrect"></a><a name="setrect"></a>Catlönizleme Ctrlımpl:: SetRect

Bu denetim için yeni bir sınırlayıcı dikdörtgen ayarlar.

```cpp
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```

### <a name="parameters"></a>Parametreler

*PRC*<br/>
Önizleme denetiminin yeni boyutunu ve konumunu belirtir.

*bRedraw*<br/>
Denetimin yeniden çizilip çizmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)
