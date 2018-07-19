---
title: CHtmlEditView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0519373a46e1c25feda7a3130b420c565a96eece
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339549"
---
# <a name="chtmleditview-class"></a>CHtmlEditView sınıfı
MFC'nin belge/görünüm mimarisi bağlamında WebBrowser düzenleme platformu işlevlerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|Oluşturur bir `CHtmlEditView` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHtmlEditView::Create](#create)|Yeni bir pencere nesnesi oluşturur.|  
|[CHtmlEditView::GetDHtmlDocument](#getdhtmldocument)|Döndürür `IHTMLDocument2` geçerli belge arabirimi.|  
|[CHtmlEditView::GetStartDocument](#getstartdocument)|Bu görünüm için varsayılan belge adını alır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CHtmlView](../../mfc/reference/chtmlview-class.md)  
  
 `CHtmlEditView`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxhtml.h  
  
##  <a name="chtmleditview"></a>  CHtmlEditView::CHtmlEditView  
 Oluşturur bir `CHtmlEditView` nesne.  
  
```  
CHtmlEditView();
```  
  
##  <a name="create"></a>  CHtmlEditView::Create  
 Yeni bir pencere nesnesi oluşturur.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszClassName*  
 Windows sınıf adları null ile sonlandırılmış dizeye işaret eder. Sınıf adı ile kayıtlı herhangi bir ad olabilir [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) genel işlev veya `RegisterClass` Windows işlevi. NULL ise, önceden tanımlanmış varsayılan kullanan [CFrameWnd](../../mfc/reference/cframewnd-class.md) öznitelikleri.  
  
 *lpszWindowName*  
 Pencere adının temsil eden bir boş sonlandırılmış karakter dizesi işaret eder.  
  
 *dwStyle*  
 Pencere stili özniteliklerini belirtir. Ws_vısıble ve WS_CHILD Windows stilleri varsayılan olarak ayarlanır.  
  
 *Rect*  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı pencerenin konumunu ve boyutunu belirtme. *RectDefault* değer, yeni pencerenin konumunu ve boyutunu belirtmek Windows sağlar.  
  
 *pParentWnd*  
 Denetiminin üst penceresine bir işaretçi.  
  
 *nID*  
 Görünüm kimliği sayısı. Varsayılan olarak, AFX_IDW_PANE_FIRST için ayarlayın.  
  
 *pContext*  
 Bir işaretçi bir [CCreateContext](../../mfc/reference/ccreatecontext-structure.md). Varsayılan olarak null değerini DÖNDÜRÜR.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ayrıca kapsanan WebBrowser's göndereceği `Navigate` varsayılan bir belge yüklemek için gereken yöntemini (bkz [CHtmlEditView::GetStartDocument](#getstartdocument)).  
  
##  <a name="getdhtmldocument"></a>  CHtmlEditView::GetDHtmlDocument  
 Döndürür `IHTMLDocument2` geçerli belge arabirimi.  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *ppDocument*  
 [Ihtmldocument2](https://msdn.microsoft.com/library/aa752574.aspx) arabirimi.  
  
##  <a name="getstartdocument"></a>  CHtmlEditView::GetStartDocument  
 Bu görünüm için varsayılan belge adını alır.  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HTMLEdit örnek](../../visual-cpp-samples.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)


