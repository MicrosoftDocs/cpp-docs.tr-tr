---
description: 'Daha fazla bilgi edinin: Cmfcönizleme Ctrlimpl sınıfı'
title: Cmfcönizleme Ctrlımpl sınıfı
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
ms.openlocfilehash: 09e4b8e023a55110986aafccfd2646d8e7775c31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334725"
---
# <a name="cmfcpreviewctrlimpl-class"></a>Cmfcönizleme Ctrlımpl sınıfı

Bu sınıf, kabuk tarafından zengin önizleme için sunulan bir konak penceresine yerleştirilmiş bir pencere uygular.

## <a name="syntax"></a>Syntax

```
class CMFCPreviewCtrlImpl : public CWnd;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcönizleme Ctrlımpl:: ~ Cmfcönizleme Ctrlımpl](#dtor)|Bir önizleme denetim nesnesinin yapılarını kaldırır.|
|[Cmfcönizleme Ctrlımpl:: Cmfcönizleme Ctrlımpl](#cmfcpreviewctrlimpl)|Bir önizleme denetim nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcönizleme Ctrlımpl:: Create](#create)|Fazla Yüklendi. Windows penceresini oluşturmak için zengin bir önizleme işleyicisi tarafından çağırılır.|
|[Cmfcönizleme Ctrlımpl::D estroy](#destroy)|Bu denetimi yok etmeniz gerektiğinde zengin bir önizleme işleyicisi tarafından çağırılır.|
|[Cmfcönizleme Ctrlımpl:: Focus](#focus)|Giriş odağını bu denetime ayarlar.|
|[Cmfcönizleme Ctrlımpl:: GetDocument](#getdocument)|Bu önizleme denetimine bağlı bir belge döndürür.|
|[Cmfcönizleme Ctrlımpl:: yeniden Çiz](#redraw)|Bu denetime yeniden çizim söyler.|
|[Cmfcönizleme Ctrlımpl:: SetDocument](#setdocument)|Belge uygulamasıyla önizleme denetimi arasında bir ilişki oluşturmak için Önizleme işleyicisi tarafından çağırılır.|
|[Cmfcönizleme Ctrlımpl:: SetHost](#sethost)|Bu denetim için yeni bir üst ayarlar.|
|[Cmfcönizleme Ctrlımpl:: Setönizleme görselleri](#setpreviewvisuals)|Zengin önizleme içeriği görselleri ayarlaması gerektiğinde zengin bir önizleme işleyicisi tarafından çağırılır.|
|[Cmfcönizleme Ctrlımpl:: SetRect](#setrect)|Bu denetim için yeni bir sınırlayıcı dikdörtgen ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcönizleme Ctrlımpl::D oPaint](#dopaint)|Önizlemeyi işlemek için Framework tarafından çağırılır.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcönizleme Ctrlımpl:: m_clrBackColor](#m_clrbackcolor)|Önizleme penceresinin arka plan rengi.|
|[Cmfcönizleme Ctrlımpl:: m_clrTextColor](#m_clrtextcolor)|Önizleme penceresinin metin rengi.|
|[Cmfcönizleme Ctrlımpl:: m_font](#m_font)|Önizleme penceresinde metin görüntülemek için kullanılan yazı tipi.|
|[Cmfcönizleme Ctrlımpl:: m_pDocument](#m_pdocument)|İçeriği denetimde önizlenen bir belgeye yönelik işaretçi.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="cmfcpreviewctrlimpl"></a> Cmfcönizleme Ctrlımpl:: Cmfcönizleme Ctrlımpl

Bir önizleme denetim nesnesi oluşturur.

### <a name="syntax"></a>Syntax

Cmfcönizleme Ctrlımpl ();

## <a name="cmfcpreviewctrlimplcreate"></a><a name="create"></a> Cmfcönizleme Ctrlımpl:: Create

Fazla Yüklendi. Windows penceresini oluşturmak için zengin bir önizleme işleyicisi tarafından çağırılır.

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
Zengin Önizleme için kabuğun sağladığı konak penceresine yönelik bir tanıtıcı.

*PRC*<br/>
Pencerenin başlangıç boyutunu ve konumunu belirtir.

*pContext*<br/>
Oluşturma bağlamına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Oluşturma başarılı olursa doğru; Aksi halde yanlış.

## <a name="cmfcpreviewctrlimpldestroy"></a><a name="destroy"></a> Cmfcönizleme Ctrlımpl::D estroy

Bu denetimi yok etmeniz gerektiğinde zengin bir önizleme işleyicisi tarafından çağırılır.

### <a name="syntax"></a>Syntax

```
virtual void Destroy();
```

## <a name="cmfcpreviewctrlimpldopaint"></a><a name="dopaint"></a> Cmfcönizleme Ctrlımpl::D oPaint

Önizlemeyi işlemek için Framework tarafından çağırılır.

### <a name="syntax"></a>Sözdizimi

```
virtual void DoPaint(
   CPaintDC* pDC
);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Boyama için bir cihaz bağlamı işaretçisi.

## <a name="cmfcpreviewctrlimplfocus"></a><a name="focus"></a> Cmfcönizleme Ctrlımpl:: Focus

Giriş odağını bu denetime ayarlar.

### <a name="syntax"></a>Syntax

```
virtual void Focus();
```

## <a name="cmfcpreviewctrlimplgetdocument"></a><a name="getdocument"></a> Cmfcönizleme Ctrlımpl:: GetDocument

Bu önizleme denetimine bağlı bir belge döndürür.

### <a name="syntax"></a>Syntax

```
ATL::IDocument* GetDocument();
```

### <a name="return-value"></a>Dönüş Değeri

İçeriği denetimde önizlenen bir belge işaretçisi.

## <a name="cmfcpreviewctrlimplm_clrbackcolor"></a><a name="m_clrbackcolor"></a> Cmfcönizleme Ctrlımpl:: m_clrBackColor

Önizleme penceresinin arka plan rengi.

### <a name="syntax"></a>Syntax

```
COLORREF m_clrBackColor;
```

## <a name="cmfcpreviewctrlimplm_clrtextcolor"></a><a name="m_clrtextcolor"></a> Cmfcönizleme Ctrlımpl:: m_clrTextColor

Önizleme penceresinin metin rengi.

### <a name="syntax"></a>Syntax

```
COLORREF m_clrTextColor;
```

## <a name="cmfcpreviewctrlimplm_font--font-used-to-display-text-in-the-preview-window"></a><a name="m_font"></a> Cmfcpreview Ctrlımpl:: m_font önizleme penceresinde metin görüntülemek için kullanılan yazı tipi.

### <a name="syntax"></a>Syntax

```
CFont m_font;
```

## <a name="cmfcpreviewctrlimplm_pdocument"></a><a name="m_pdocument"></a> Cmfcönizleme Ctrlımpl:: m_pDocument

İçeriği denetimde önizlenen bir belgeye yönelik işaretçi.

### <a name="syntax"></a>Syntax

```
ATL::IDocument* m_pDocument;
```

## <a name="cmfcpreviewctrlimplredraw"></a><a name="redraw"></a> Cmfcönizleme Ctrlımpl:: yeniden Çiz

Bu denetime yeniden çizim söyler.

### <a name="syntax"></a>Syntax

```
virtual void Redraw();
```

## <a name="cmfcpreviewctrlimplsetdocument"></a><a name="setdocument"></a> Cmfcönizleme Ctrlımpl:: SetDocument

Belge uygulamasıyla önizleme denetimi arasında bir ilişki oluşturmak için Önizleme işleyicisi tarafından çağırılır.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetDocument(
   IDocument* pDocument
);
```

### <a name="parameters"></a>Parametreler

*pDocument*<br/>
Belge uygulamasına yönelik bir işaretçi.

## <a name="cmfcpreviewctrlimplsethost"></a><a name="sethost"></a> Cmfcönizleme Ctrlımpl:: SetHost

Bu denetim için yeni bir üst ayarlar.

### <a name="syntax"></a>Sözdizimi

```
virtual void SetHost(
   HWND hWndParent
);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
Yeni ana pencereye yönelik bir tanıtıcı.

## <a name="cmfcpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a> Cmfcönizleme Ctrlımpl:: Setönizleme görselleri

Zengin önizleme içeriği görselleri ayarlaması gerektiğinde zengin bir önizleme işleyicisi tarafından çağırılır.

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
Önizleme penceresinin arka plan rengi.

*clrText*<br/>
Önizleme penceresinin metin rengi.

*PLF*<br/>
Önizleme penceresinde metin görüntülemek için kullanılan yazı tipi.

## <a name="cmfcpreviewctrlimplsetrect"></a><a name="setrect"></a> Cmfcönizleme Ctrlımpl:: SetRect

Bu denetim için yeni bir sınırlayıcı dikdörtgen ayarlar.

### <a name="syntax"></a>Sözdizimi

```
virtual void SetRect(
   const RECT* prc,
   BOOL bRedraw
);
```

### <a name="parameters"></a>Parametreler

*PRC*<br/>
Önizleme denetiminin yeni boyutunu ve konumunu belirtir.

*bRedraw*<br/>
Denetimin yeniden çizilip çizmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

Genellikle, ana bilgisayar denetimi yeniden boyutlandırılırken yeni bir sınırlayıcı dikdörtgen ayarlanır.

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="dtor"></a> Cmfcönizleme Ctrlımpl:: ~ Cmfcönizleme Ctrlımpl

Bir önizleme denetim nesnesinin yapılarını kaldırır.

### <a name="syntax"></a>Syntax

```
virtual ~CMFCPreviewCtrlImpl();
```
