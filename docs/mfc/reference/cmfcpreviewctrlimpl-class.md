---
title: "CMFCPreviewCtrlImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "28"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8def8a8085bebdd09ce58cb6d9abd026fe713fe8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcpreviewctrlimpl-class"></a>CMFCPreviewCtrlImpl sınıfı
Bu sınıf için Zengin Önizleme Kabuk tarafından sağlanan bir konak pencereyi yerleştirildiği bir pencere uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCPreviewCtrlImpl : public CWnd;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl](#dtor)|Önizleme denetim nesnesi destructs.|  
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|Önizleme denetim nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::Create](#create)|Fazla Yüklendi. Windows penceresi oluşturmak için Zengin Önizleme işleyicisi tarafından çağrılır.|  
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|Bu denetim yok etmek gerektiğinde bir Zengin Önizleme işleyicisi tarafından çağrılır.|  
|[CMFCPreviewCtrlImpl::Focus](#focus)|Ayarlar, bu denetim odağı girin.|  
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|Bu önizleme denetimine bağlı bir belgeyi döndürür.|  
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|Bu denetim yeniden boyutlandırmaya söyler.|  
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|Belge uygulama ve önizleme denetimi arasında bir ilişki oluşturmak için Önizleme işleyicisi tarafından çağrılır.|  
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|Bu denetim için yeni bir üst öğe olarak ayarlar.|  
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Zengin Önizleme görselleri ayarlamak gerektiğinde bir Zengin Önizleme işleyicisi tarafından içerik çağrılır.|  
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|Bu denetim için yeni bir sınırlayıcı dikdörtgenini ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|Önizleme işlemek için çerçevesi tarafından çağrılır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|Önizleme penceresi arka plan rengi.|  
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|Önizleme penceresi metin rengi.|  
|[CMFCPreviewCtrlImpl::m_font](#m_font)|Metni Önizleme penceresinde görüntülemek için kullanılan yazıtipi.|  
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|İçerikleri denetiminde önizlemesi bir belge için bir işaretçi.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h    
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimpl"></a>CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
Önizleme denetim nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi
CMFCPreviewCtrlImpl();  

## <a name="create"></a>CMFCPreviewCtrlImpl::Create
Fazla Yüklendi. Windows penceresi oluşturmak için Zengin Önizleme işleyicisi tarafından çağrılır.  
  
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
 `hWndParent`  
 Kabuk tarafından sağlanan Zengin Önizleme için konak penceresi için bir tanıtıcı.  
  
 `prc`  
 Başlangıç boyutu ve pencere konumunu belirtir.  
  
 `pContext`  
 Bağlamı oluşturma için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başarılı bir şekilde oluşturuldu Aksi takdirde `FALSE`.  
  
## <a name="destroy"></a>CMFCPreviewCtrlImpl::Destroy
Bu denetim yok etmek gerektiğinde bir Zengin Önizleme işleyicisi tarafından çağrılır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
virtual void Destroy();  
```  
  
## <a name="dopaint"></a>CMFCPreviewCtrlImpl::DoPaint  
Önizleme işlemek için çerçevesi tarafından çağrılır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
virtual void DoPaint(  
   CPaintDC* pDC  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Boyama için cihaz bağlamı için bir işaretçi.  


## <a name="focus"></a>CMFCPreviewCtrlImpl::Focus  
Ayarlar, bu denetim odağı girin.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
virtual void Focus();  
```  
## <a name="getdocument"></a>CMFCPreviewCtrlImpl::GetDocument
Bu önizleme denetimine bağlı bir belgeyi döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ATL::IDocument* GetDocument();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçerikleri denetiminde önizlemesi, bir belge için bir işaretçi.

## <a name="m_clrbackcolor"></a>CMFCPreviewCtrlImpl::m_clrBackColor  
Önizleme penceresi arka plan rengi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
COLORREF m_clrBackColor;  
```  

## <a name="m_clrtextcolor"></a>CMFCPreviewCtrlImpl::m_clrTextColor
Önizleme penceresi metin rengi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
COLORREF m_clrTextColor;  
```  
## <a name="m_font"></a>CMFCPreviewCtrlImpl::m_font yazı tipi metin önizleme penceresinde görüntülemek için kullanılır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
CFont m_font;  
```  
## <a name="m_pdocument"></a>CMFCPreviewCtrlImpl::m_pDocument  
İçerikleri denetiminde önizlemesi bir belge için bir işaretçi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ATL::IDocument* m_pDocument;  
```  

## <a name="redraw"></a>CMFCPreviewCtrlImpl::Redraw  
Bu denetim yeniden boyutlandırmaya söyler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
virtual void Redraw();  
```  
## <a name="setdocument"></a>CMFCPreviewCtrlImpl::SetDocument 
Belge uygulama ve önizleme denetimi arasında bir ilişki oluşturmak için Önizleme işleyicisi tarafından çağrılır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void SetDocument(  
   IDocument* pDocument  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDocument`  
 Belge uygulaması için bir işaretçi.  

## <a name="sethost"></a>CMFCPreviewCtrlImpl::SetHost  
Bu denetim için yeni bir üst öğe olarak ayarlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
virtual void SetHost(  
   HWND hWndParent  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `hWndParent`  
 Yeni üst pencere için bir tanıtıcı.  

## <a name="setpreviewvisuals"></a>CMFCPreviewCtrlImpl::SetPreviewVisuals  
Zengin Önizleme görselleri ayarlamak gerektiğinde bir Zengin Önizleme işleyicisi tarafından içerik çağrılır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
virtual void SetPreviewVisuals(  
   COLORREF clrBack,  
   COLORREF clrText,  
   const LOGFONTW *plf  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `clrBack`  
 Önizleme penceresi arka plan rengi.  
  
 `clrText`  
 Önizleme penceresi metin rengi.  
  
 `plf`  
 Metni Önizleme penceresinde görüntülemek için kullanılan yazıtipi. 

##  <a name="setrect"></a>CMFCPreviewCtrlImpl::SetRect  
Bu denetim için yeni bir sınırlayıcı dikdörtgenini ayarlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
virtual void SetRect(  
   const RECT* prc,  
   BOOL bRedraw  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `prc`  
 Önizleme denetimin konumunu ve yeni boyutunu belirtir.  
  
 `bRedraw`  
 Denetim yeniden olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Konak kontrolü yeniden boyutlandırıldığında genellikle yeni bir sınırlayıcı dikdörtgenini ayarlanır.  

## <a name="dtor"></a>CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl  
Önizleme denetim nesnesi destructs.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
virtual ~CMFCPreviewCtrlImpl();  
```  
  
