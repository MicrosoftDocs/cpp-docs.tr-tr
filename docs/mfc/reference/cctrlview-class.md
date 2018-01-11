---
title: "CCtrlView sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
dev_langs: C++
helpviewer_keywords:
- CCtrlView [MFC], CCtrlView
- CCtrlView [MFC], OnDraw
- CCtrlView [MFC], PreCreateWindow
- CCtrlView [MFC], m_dwDefaultStyle
- CCtrlView [MFC], m_strClass
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 484abaf5344400e03b53038d2c137497c202345f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cctrlview-class"></a>CCtrlView sınıfı
Windows 98 ve Windows NT tarafından 3.51 ve sonraki sürümlerde desteklenen ortak denetimleri için belge görünüm mimarisi uyum sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CCtrlView : public CView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCtrlView::CCtrlView](#cctrlview)|Oluşturan bir `CCtrlView` nesnesi.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCtrlView::OnDraw](#ondraw)|Belirtilen cihaz bağlamı kullanma çizmek için çerçevesi tarafından çağrılır.|  
|[CCtrlView::PreCreateWindow](#precreatewindow)|Bu bağlı Windows penceresi oluşturulmasını önce adlı `CCtrlView` nesnesi.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|View sınıfı için varsayılan stili içerir.|  
|[CCtrlView::m_strClass](#m_strclass)|View sınıfı Windows sınıf adı içeriyor.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf `CCtrlView` ve türevleri, [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), ve [CRichEditView](../../mfc/reference/cricheditview-class.md), uyarlama Belge görünüm mimarisi yeni ortak denetimleri için Windows 95/98 ve Windows NT 3.51 ve sonraki sürümlerde desteklenir. Belge görünüm mimarisi hakkında daha fazla bilgi için bkz: [belge/görünüm mimarisinin](../../mfc/document-view-architecture.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CCtrlView`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cctrlview"></a>CCtrlView::CCtrlView  
 Oluşturan bir `CCtrlView` nesnesi.  
  
```  
CCtrlView(
    LPCTSTR lpszClass,  
    DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszClass`  
 View sınıfı Windows sınıfı adı.  
  
 `dwStyle`  
 View sınıfı stili.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir çerçeve penceresi oluşturulduğunda veya bir pencereyi bölmek framework Oluşturucusu çağırır. Geçersiz kılma [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) belge eklendikten sonra Görünüm başlatılamadı. Çağrı [CWnd::Create](../../mfc/reference/cwnd-class.md#create) veya [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) Windows nesnesi oluşturulamıyor.  
  
##  <a name="m_strclass"></a>CCtrlView::m_strClass  
 View sınıfı Windows sınıf adı içeriyor.  
  
```  
CString m_strClass;  
```  
  
##  <a name="m_dwdefaultstyle"></a>CCtrlView::m_dwDefaultStyle  
 View sınıfı için varsayılan stili içerir.  
  
```  
DWORD m_dwDefaultStyle;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir pencere oluşturulduğunda bu stili uygulanır.  
  
##  <a name="ondraw"></a>CCtrlView::OnDraw  
 İçeriğini çizmek için çerçevesi tarafından çağrılır `CCtrlView` belirtilen cihaz bağlamı kullanma nesne.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Çizim oluştuğu cihaz bağlamı için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 `OnDraw`ekran görüntüsü, tarafından belirtilen bir ekran cihaz bağlamı geçirme için genellikle adlı `pDC`.  
  
##  <a name="precreatewindow"></a>CCtrlView::PreCreateWindow  
 Bu bağlı Windows penceresi oluşturulmasını önce adlı `CWnd` nesnesi.  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>Parametreler  
 *cs*  
 A [CREATESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632603) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencere oluşturma devam etmesi gerekiyorsa sıfır olmayan; oluşturma hatası göstermek için 0'ı tıklatın.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir zaman doğrudan bu işlevini çağırın.  
  
 Bu işlev varsayılan uygulaması denetler bir **NULL** pencere sınıfı adı ve uygun bir varsayılan değiştirir. Bu üye işlevini değiştirmek için geçersiz kılma `CREATESTRUCT` penceresi oluşturulmadan önce yapılandırın.  
  
 Her sınıf türetilmiş `CCtrlView` , geçersiz kılma için kendi işlevsellik ekler `PreCreateWindow`. Tasarıma göre bu türetme, `PreCreateWindow` belirtilmeyen. Her sınıf ve stilleri birbirine uygun stilleri belirlemek için uygulamanızın taban sınıfı için MFC kaynak kodu inceleyebilirsiniz. Geçersiz kılmayı seçerseniz `PreCreateWindow`, uygulamanızın taban sınıf içinde kullanılan stiller MFC kaynak kodundan topladığınız bilgileri kullanarak gereksinim duyduğunuz işlevselliği sağlamak olup olmadığını belirleyebilirsiniz.  
  
 Pencere stilleri değiştirme hakkında daha fazla bilgi için bkz: [miktar MFC tarafından oluşturulan bir pencere stillerini değiştirme](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CView sınıfı](../../mfc/reference/cview-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CTreeView sınıfı](../../mfc/reference/ctreeview-class.md)   
 [CListView sınıfı](../../mfc/reference/clistview-class.md)   
 [CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
