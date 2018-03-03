---
title: "CHtmlEditView sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 98964a48be8b8c36a3d6d5bd708a51b9963ae105
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="chtmleditview-class"></a>CHtmlEditView sınıfı
MFC'nin belge/görünüm mimarisinin bağlamında WebBrowser düzenleme platform işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|Oluşturan bir `CHtmlEditView` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHtmlEditView::Create](#create)|Yeni bir pencere nesnesi oluşturur.|  
|[CHtmlEditView::GetDHtmlDocument](#getdhtmldocument)|Döndürür **Ihtmldocument2** geçerli belge arabirimi.|  
|[CHtmlEditView::GetStartDocument](#getstartdocument)|Bu görünüm için varsayılan belge adını alır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [Cformview'yu](../../mfc/reference/cformview-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CHtmlView](../../mfc/reference/chtmlview-class.md)  
  
 `CHtmlEditView`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxhtml.h  
  
##  <a name="chtmleditview"></a>CHtmlEditView::CHtmlEditView  
 Oluşturan bir `CHtmlEditView` nesnesi.  
  
```  
CHtmlEditView();
```  
  
##  <a name="create"></a>CHtmlEditView::Create  
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
 `lpszClassName`  
 Windows sınıfı adları null olarak sonlandırılan bir karakter dizesine noktaları. Sınıf adı kayıtlı herhangi bir ad olabilir [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) genel işlevi veya **RegisterClass** Windows işlevi. Varsa **NULL**, önceden tanımlanmış varsayılan kullanır [CFrameWnd](../../mfc/reference/cframewnd-class.md) öznitelikleri.  
  
 `lpszWindowName`  
 Pencere adı temsil eden bir null olarak sonlandırılan bir karakter dizesi noktalarına.  
  
 `dwStyle`  
 Pencere stili özniteliklerini belirtir. Varsayılan olarak, **ws_vısıble** ve **WS_CHILD** Windows stilleri ayarlanır.  
  
 `rect`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) boyutunu ve pencere konumunu belirtme yapısı. `rectDefault` Değeri boyutunu ve yeni pencere konumunu belirtmek Windows sağlar.  
  
 `pParentWnd`  
 Denetimin üst pencere için bir işaretçi.  
  
 `nID`  
 Görünüm kimliği sayısı. Varsayılan olarak, kümesine **AFX_IDW_PANE_FIRST**.  
  
 `pContext`  
 Bir işaretçi bir [CCreateContext](../../mfc/reference/ccreatecontext-structure.md). **NULL** varsayılan olarak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem de kapsanan WebBrowser's çağıracaktır **Bul** varsayılan bir belge yüklemek için yöntemi (bkz [CHtmlEditView::GetStartDocument](#getstartdocument)).  
  
##  <a name="getdhtmldocument"></a>CHtmlEditView::GetDHtmlDocument  
 Döndürür **Ihtmldocument2** geçerli belge arabirimi.  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `ppDocument`  
 [Ihtmldocument2](https://msdn.microsoft.com/library/aa752574.aspx) arabirimi.  
  
##  <a name="getstartdocument"></a>CHtmlEditView::GetStartDocument  
 Bu görünüm için varsayılan belge adını alır.  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HTMLEdit örnek](../../visual-cpp-samples.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)


