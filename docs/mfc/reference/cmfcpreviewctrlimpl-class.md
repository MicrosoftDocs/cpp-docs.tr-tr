---
title: Cmfcpreviewctrlımpl sınıfı
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
ms.openlocfilehash: 3ec1acd1872bc0e51117602ef723116170458afd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636741"
---
# <a name="cmfcpreviewctrlimpl-class"></a>Cmfcpreviewctrlımpl sınıfı

Bu sınıf, kabuk tarafından sağlanan Zengin Önizleme için barındırıcı penceresine yerleştirilen bir pencere uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPreviewCtrlImpl : public CWnd;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcpreviewctrlımpl:: ~ Cmfcpreviewctrlımpl](#dtor)|Önizleme denetim nesnesi destructs.|
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|Önizleme denetim nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::Create](#create)|Fazla Yüklendi. Windows penceresi oluşturmak için Zengin Önizleme işleyici tarafından çağrılır.|
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|Bu denetim yok etmek gereken Zengin Önizleme işleyici tarafından çağrılır.|
|[CMFCPreviewCtrlImpl::Focus](#focus)|Ayarlar, bu denetim odağı girin.|
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|Bu önizleme denetimine bağlı bir belgeyi döndürür.|
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|Bu denetimi yeniden düzenlenen söyler.|
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|Belge uygulaması ve önizleme denetimi arasında bir ilişki oluşturmak için Önizleme işleyici tarafından çağrılır.|
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|Bu denetim için yeni bir üst ayarlar.|
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Görsellerin Zengin Önizleme ihtiyaç duyduğu içerik Zengin Önizleme işleyici tarafından çağrılır.|
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|Bu denetim için yeni sınırlayıcı bir dikdörtgen ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|Önizleme işlemek için framework tarafından çağırılır.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|Önizleme penceresini arka plan rengi.|
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|Önizleme penceresini metin rengi.|
|[CMFCPreviewCtrlImpl::m_font](#m_font)|Önizleme metni görüntülemede kullanılacak yazı tipi.|
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|Denetime içeriğe sahip önizlemesini görebilirsiniz belgeye yönelik işaretçi.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[Cmfcpreviewctrlımpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimpl"></a> CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl

Önizleme denetim nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

CMFCPreviewCtrlImpl();

## <a name="create"></a> CMFCPreviewCtrlImpl::Create

Fazla Yüklendi. Windows penceresi oluşturmak için Zengin Önizleme işleyici tarafından çağrılır.

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
Kabuk tarafından sağlanan Zengin Önizleme için ana penceresi için bir tanıtıcı.

*ÇHC*<br/>
Başlangıç boyutu ve pencerenin konumunu belirtir.

*pContext*<br/>
Bir oluşturma bağlamına bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Oluşturma başarılı olursa TRUE; Aksi durumda FALSE.

## <a name="destroy"></a> CMFCPreviewCtrlImpl::Destroy

Bu denetim yok etmek gereken Zengin Önizleme işleyici tarafından çağrılır.

### <a name="syntax"></a>Sözdizimi

```
virtual void Destroy();
```

## <a name="dopaint"></a> CMFCPreviewCtrlImpl::DoPaint

Önizleme işlemek için framework tarafından çağırılır.

### <a name="syntax"></a>Sözdizimi

```
virtual void DoPaint(
   CPaintDC* pDC
);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Boyama için cihaz bağlamı için bir işaretçi.

## <a name="focus"></a> CMFCPreviewCtrlImpl::Focus

Ayarlar, bu denetim odağı girin.

### <a name="syntax"></a>Sözdizimi

```
virtual void Focus();
```

## <a name="getdocument"></a> CMFCPreviewCtrlImpl::GetDocument

Bu önizleme denetimine bağlı bir belgeyi döndürür.

### <a name="syntax"></a>Sözdizimi

```
ATL::IDocument* GetDocument();
```

### <a name="return-value"></a>Dönüş Değeri

Denetime içeriğe sahip önizlemesini görebilirsiniz belgeye yönelik işaretçi.

## <a name="m_clrbackcolor"></a> CMFCPreviewCtrlImpl::m_clrBackColor

Önizleme penceresini arka plan rengi.

### <a name="syntax"></a>Sözdizimi

```
COLORREF m_clrBackColor;
```

## <a name="m_clrtextcolor"></a> CMFCPreviewCtrlImpl::m_clrTextColor

Önizleme penceresini metin rengi.

### <a name="syntax"></a>Sözdizimi

```
COLORREF m_clrTextColor;
```

## <a name="m_font"></a> CMFCPreviewCtrlImpl::m_font Önizleme metni görüntülemede kullanılacak yazı tipi.

### <a name="syntax"></a>Sözdizimi

```
CFont m_font;
```

## <a name="m_pdocument"></a> CMFCPreviewCtrlImpl::m_pDocument

Denetime içeriğe sahip önizlemesini görebilirsiniz belgeye yönelik işaretçi.

### <a name="syntax"></a>Sözdizimi

```
ATL::IDocument* m_pDocument;
```

## <a name="redraw"></a> CMFCPreviewCtrlImpl::Redraw

Bu denetimi yeniden düzenlenen söyler.

### <a name="syntax"></a>Sözdizimi

```
virtual void Redraw();
```

## <a name="setdocument"></a> CMFCPreviewCtrlImpl::SetDocument

Belge uygulaması ve önizleme denetimi arasında bir ilişki oluşturmak için Önizleme işleyici tarafından çağrılır.

### <a name="syntax"></a>Sözdizimi

```
void SetDocument(
   IDocument* pDocument
);
```

### <a name="parameters"></a>Parametreler

*pDocument*<br/>
Belge uygulaması için bir işaretçi.

## <a name="sethost"></a> CMFCPreviewCtrlImpl::SetHost

Bu denetim için yeni bir üst ayarlar.

### <a name="syntax"></a>Sözdizimi

```
virtual void SetHost(
   HWND hWndParent
);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Yeni bir ana penceresi için bir tanıtıcı.

## <a name="setpreviewvisuals"></a> CMFCPreviewCtrlImpl::SetPreviewVisuals

Görsellerin Zengin Önizleme ihtiyaç duyduğu içerik Zengin Önizleme işleyici tarafından çağrılır.

### <a name="syntax"></a>Sözdizimi

```
virtual void SetPreviewVisuals(
   COLORREF clrBack,
   COLORREF clrText,
   const LOGFONTW *plf
);
```

### <a name="parameters"></a>Parametreler

*clrBack*<br/>
Önizleme penceresini arka plan rengi.

*clrText*<br/>
Önizleme penceresini metin rengi.

*plf*<br/>
Önizleme metni görüntülemede kullanılacak yazı tipi.

##  <a name="setrect"></a> CMFCPreviewCtrlImpl::SetRect

Bu denetim için yeni sınırlayıcı bir dikdörtgen ayarlar.

### <a name="syntax"></a>Sözdizimi

```
virtual void SetRect(
   const RECT* prc,
   BOOL bRedraw
);
```

### <a name="parameters"></a>Parametreler

*ÇHC*<br/>
Yeni boyutunu ve önizleme denetimin konumunu belirtir.

*bRedraw*<br/>
Denetim yeniden olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Konak denetimi yeniden boyutlandırdığınızda, genellikle yeni sınırlayıcı bir dikdörtgen ayarlanır.

## <a name="dtor"></a> Cmfcpreviewctrlımpl:: ~ Cmfcpreviewctrlımpl

Önizleme denetim nesnesi destructs.

### <a name="syntax"></a>Sözdizimi

```
virtual ~CMFCPreviewCtrlImpl();
```

