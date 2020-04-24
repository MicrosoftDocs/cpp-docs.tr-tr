---
title: CMFCPreviewCtrlImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::Create
- AFXWIN/CMFCPreviewCtrlImpl::Destroy
- AFXWIN/CMFCPreviewCtrlImpl::Focus
- AFXWIN/CMFCPreviewCtrlImpl::GetDocument
- AFXWIN/CMFCPreviewCtrlImpl::Redraw
- AFXWIN/CMFCPreviewCtrlImpl::SetDocument
- AFXWIN/CMFCPreviewCtrlImpl::SetHost
- AFXWIN/CMFCPreviewCtrlImpl::SetPreviewVisuals
- AFXWIN/CMFCPreviewCtrlImpl::SetRect
- AFXWIN/CMFCPreviewCtrlImpl::DoPaint
- AFXWIN/CMFCPreviewCtrlImpl::m_clrBackColor
- AFXWIN/CMFCPreviewCtrlImpl::m_clrTextColor
- AFXWIN/CMFCPreviewCtrlImpl::m_font
- AFXWIN/CMFCPreviewCtrlImpl::m_pDocument
helpviewer_keywords:
- CMFCPreviewCtrlImpl [MFC], CMFCPreviewCtrlImpl
- CMFCPreviewCtrlImpl [MFC], Create
- CMFCPreviewCtrlImpl [MFC], Destroy
- CMFCPreviewCtrlImpl [MFC], Focus
- CMFCPreviewCtrlImpl [MFC], GetDocument
- CMFCPreviewCtrlImpl [MFC], Redraw
- CMFCPreviewCtrlImpl [MFC], SetDocument
- CMFCPreviewCtrlImpl [MFC], SetHost
- CMFCPreviewCtrlImpl [MFC], SetPreviewVisuals
- CMFCPreviewCtrlImpl [MFC], SetRect
- CMFCPreviewCtrlImpl [MFC], DoPaint
- CMFCPreviewCtrlImpl [MFC], m_clrBackColor
- CMFCPreviewCtrlImpl [MFC], m_clrTextColor
- CMFCPreviewCtrlImpl [MFC], m_font
- CMFCPreviewCtrlImpl [MFC], m_pDocument
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
ms.openlocfilehash: 0c0a594a84b45ce7bf6f2c2fa5d1a547fa10eaa6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751840"
---
# <a name="cmfcpreviewctrlimpl-class"></a>CMFCPreviewCtrlImpl Sınıfı

Bu sınıf, Zengin Önizleme için Shell tarafından sağlanan ana bilgisayar penceresine yerleştirilen bir pencere uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPreviewCtrlImpl : public CWnd;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::~CMFCPreviewCtrlImpl](#dtor)|Bir önizleme denetim nesnesini yok eder.|
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|Bir önizleme denetim nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::Oluştur](#create)|Fazla Yüklendi. Windows penceresini oluşturmak için Zengin Önizleme işleyicisi tarafından çağrılır.|
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|Bu denetimi yok etmesi gerektiğinde Zengin Önizleme işleyicisi tarafından çağrılır.|
|[CMFCPreviewCtrlImpl::Odak](#focus)|Bu denetime giriş odağı ayarlar.|
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|Bu önizleme denetimine bağlı bir belge döndürür.|
|[CMFCPreviewCtrlImpl::Yeniden Çiz](#redraw)|Bu denetimi yeniden çizmeyi söyler.|
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|Belge uygulaması ve önizleme denetimi arasında bir ilişki oluşturmak için önizleme işleyicisi tarafından çağrılır.|
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|Bu denetim için yeni bir ebeveyn ayarlar.|
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Zengin önizleme içeriğinin görsellerini ayarlaması gerektiğinde Zengin Önizleme işleyicisi tarafından çağrılır.|
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|Bu denetim için yeni bir sınırlayıcı dikdörtgen ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|Önizlemeyi işlemek için çerçeve tarafından çağrılır.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|Önizleme penceresinin arka plan rengi.|
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|Önizleme penceresinin metin rengi.|
|[CMFCPreviewCtrlImpl::m_font](#m_font)|Önizleme penceresinde metni görüntülemek için kullanılan yazı tipi.|
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|Denetiminde içeriği önizlemesi yapılan bir belgenin işaretçisi.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="cmfcpreviewctrlimpl"></a>CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl

Bir önizleme denetim nesnesi oluşturuyor.

### <a name="syntax"></a>Sözdizimi

CMFCPreviewCtrlImpl();

## <a name="cmfcpreviewctrlimplcreate"></a><a name="create"></a>CMFCPreviewCtrlImpl::Oluştur

Fazla Yüklendi. Windows penceresini oluşturmak için Zengin Önizleme işleyicisi tarafından çağrılır.

### <a name="syntax"></a>Sözdizimi

```
virtual BOOL Create(
   HWND hWndParent,
   const RECT* prc
);
virtual BOOL Create(
   HWND hWndParent,
   const RECT* prc,
   CCreateContext* pContext
);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Zengin Önizleme için Shell tarafından sağlanan ana bilgisayar penceresine bir tutamaç.

*Çhc*<br/>
Pencerenin başlangıç boyutunu ve konumunu belirtir.

*Pcontext*<br/>
Oluşturma bağlamına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yaratılış başarılı olduysa DOĞRU; aksi takdirde YANLIŞ.

## <a name="cmfcpreviewctrlimpldestroy"></a><a name="destroy"></a>CMFCPreviewCtrlImpl::Destroy

Bu denetimi yok etmesi gerektiğinde Zengin Önizleme işleyicisi tarafından çağrılır.

### <a name="syntax"></a>Sözdizimi

```
virtual void Destroy();
```

## <a name="cmfcpreviewctrlimpldopaint"></a><a name="dopaint"></a>CMFCPreviewCtrlImpl::DoPaint

Önizlemeyi işlemek için çerçeve tarafından çağrılır.

### <a name="syntax"></a>Sözdizimi

```
virtual void DoPaint(
   CPaintDC* pDC
);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Boyama için aygıt bağlamına işaretçi.

## <a name="cmfcpreviewctrlimplfocus"></a><a name="focus"></a>CMFCPreviewCtrlImpl::Odak

Bu denetime giriş odağı ayarlar.

### <a name="syntax"></a>Sözdizimi

```
virtual void Focus();
```

## <a name="cmfcpreviewctrlimplgetdocument"></a><a name="getdocument"></a>CMFCPreviewCtrlImpl::GetDocument

Bu önizleme denetimine bağlı bir belge döndürür.

### <a name="syntax"></a>Sözdizimi

```
ATL::IDocument* GetDocument();
```

### <a name="return-value"></a>Dönüş Değeri

İçeriği denetimde önizlemesi olan bir belgenin işaretçisi.

## <a name="cmfcpreviewctrlimplm_clrbackcolor"></a><a name="m_clrbackcolor"></a>CMFCPreviewCtrlImpl::m_clrBackColor

Önizleme penceresinin arka plan rengi.

### <a name="syntax"></a>Sözdizimi

```
COLORREF m_clrBackColor;
```

## <a name="cmfcpreviewctrlimplm_clrtextcolor"></a><a name="m_clrtextcolor"></a>CMFCPreviewCtrlImpl::m_clrTextColor

Önizleme penceresinin metin rengi.

### <a name="syntax"></a>Sözdizimi

```
COLORREF m_clrTextColor;
```

## <a name="cmfcpreviewctrlimplm_font--font-used-to-display-text-in-the-preview-window"></a><a name="m_font"></a>CMFCPreviewCtrlImpl::m_font Font önizleme penceresinde metin görüntülemek için kullanılır.

### <a name="syntax"></a>Sözdizimi

```
CFont m_font;
```

## <a name="cmfcpreviewctrlimplm_pdocument"></a><a name="m_pdocument"></a>CMFCPreviewCtrlImpl::m_pDocument

Denetiminde içeriği önizlemesi yapılan bir belgenin işaretçisi.

### <a name="syntax"></a>Sözdizimi

```
ATL::IDocument* m_pDocument;
```

## <a name="cmfcpreviewctrlimplredraw"></a><a name="redraw"></a>CMFCPreviewCtrlImpl::Yeniden Çiz

Bu denetimi yeniden çizmeyi söyler.

### <a name="syntax"></a>Sözdizimi

```
virtual void Redraw();
```

## <a name="cmfcpreviewctrlimplsetdocument"></a><a name="setdocument"></a>CMFCPreviewCtrlImpl::SetDocument

Belge uygulaması ve önizleme denetimi arasında bir ilişki oluşturmak için önizleme işleyicisi tarafından çağrılır.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetDocument(
   IDocument* pDocument
);
```

### <a name="parameters"></a>Parametreler

*pBelge*<br/>
Belge uygulaması için bir işaretçi.

## <a name="cmfcpreviewctrlimplsethost"></a><a name="sethost"></a>CMFCPreviewCtrlImpl::SetHost

Bu denetim için yeni bir ebeveyn ayarlar.

### <a name="syntax"></a>Sözdizimi

```
virtual void SetHost(
   HWND hWndParent
);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Yeni üst pencerenin tutamacı.

## <a name="cmfcpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>CMFCPreviewCtrlImpl::SetPreviewVisuals

Zengin önizleme içeriğinin görsellerini ayarlaması gerektiğinde Zengin Önizleme işleyicisi tarafından çağrılır.

### <a name="syntax"></a>Sözdizimi

```
virtual void SetPreviewVisuals(
   COLORREF clrBack,
   COLORREF clrText,
   const LOGFONTW *plf
);
```

### <a name="parameters"></a>Parametreler

*clrGeri*<br/>
Önizleme penceresinin arka plan rengi.

*clrMetin*<br/>
Önizleme penceresinin metin rengi.

*plf*<br/>
Önizleme penceresinde metni görüntülemek için kullanılan yazı tipi.

## <a name="cmfcpreviewctrlimplsetrect"></a><a name="setrect"></a>CMFCPreviewCtrlImpl::SetRect

Bu denetim için yeni bir sınırlayıcı dikdörtgen ayarlar.

### <a name="syntax"></a>Sözdizimi

```
virtual void SetRect(
   const RECT* prc,
   BOOL bRedraw
);
```

### <a name="parameters"></a>Parametreler

*Çhc*<br/>
Önizleme denetiminin yeni boyutunu ve konumunu belirtir.

*bRedraw*<br/>
Denetimin yeniden çizilip çizilmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

Genellikle ana bilgisayar denetimi yeniden boyutlandırıldığında yeni bir sınırlayıcı dikdörtgen ayarlanır.

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="dtor"></a>CMFCPreviewCtrlImpl::~CMFCPreviewCtrlImpl

Bir önizleme denetim nesnesini yok eder.

### <a name="syntax"></a>Sözdizimi

```
virtual ~CMFCPreviewCtrlImpl();
```
