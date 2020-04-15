---
title: CCtrlView Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
helpviewer_keywords:
- CCtrlView [MFC], CCtrlView
- CCtrlView [MFC], OnDraw
- CCtrlView [MFC], PreCreateWindow
- CCtrlView [MFC], m_dwDefaultStyle
- CCtrlView [MFC], m_strClass
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
ms.openlocfilehash: f77f1c265920bd160da790647ef754c55e6dbda3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369350"
---
# <a name="cctrlview-class"></a>CCtrlView Sınıfı

Belge görünümü mimarisini Windows 98 ve Windows NT sürümleri 3.51 ve sonraki sürümler tarafından desteklenen ortak denetimlere uyarlar.

## <a name="syntax"></a>Sözdizimi

```
class CCtrlView : public CView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CCtrlView::CCtrlView](#cctrlview)|Bir `CCtrlView` nesne inşa eder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CCtrlView::OnDraw](#ondraw)|Belirtilen aygıt bağlamını kullanarak çizmek için çerçeve tarafından çağrılır.|
|[CCtrlView::Pyeniden CreateWindow](#precreatewindow)|Bu `CCtrlView` nesneye bağlı Windows penceresi nin oluşturulmasından önce çağrılır.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|Görünüm sınıfı için varsayılan stili içerir.|
|[CCtrlView::m_strClass](#m_strclass)|Görünüm sınıfının Windows sınıf adını içerir.|

## <a name="remarks"></a>Açıklamalar

Sınıf `CCtrlView` ve türevleri, [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), ve [CRichEditView](../../mfc/reference/cricheditview-class.md), Windows 95/98 ve Windows NT sürümleri 3.51 ve daha sonra tarafından desteklenen yeni ortak denetimler belge görünümü mimarisini uyarlar. Belge görünümü mimarisi hakkında daha fazla bilgi için Bkz. [Belge/Görünüm Mimarisi.](../../mfc/document-view-architecture.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cview](../../mfc/reference/cview-class.md)

`CCtrlView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cctrlviewcctrlview"></a><a name="cctrlview"></a>CCtrlView::CCtrlView

Bir `CCtrlView` nesne inşa eder.

```
CCtrlView(
    LPCTSTR lpszClass,
    DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*lpszClass*<br/>
Görünüm sınıfının Windows sınıf adı.

*Dwstyle*<br/>
Görünüm sınıfının stili.

### <a name="remarks"></a>Açıklamalar

Yeni bir çerçeve penceresi oluşturulduğunda veya bir pencere bölündüğünde çerçeve oluşturucuyu çağırır. Belge eklendikten sonra görünümü başlatmak için [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) geçersiz kılın. [CWnd'yi arayın::Windows](../../mfc/reference/cwnd-class.md#create) nesnesini oluşturmak için Oluştur veya [CWnd::CreateEx.](../../mfc/reference/cwnd-class.md#createex)

## <a name="cctrlviewm_strclass"></a><a name="m_strclass"></a>CCtrlView::m_strClass

Görünüm sınıfının Windows sınıf adını içerir.

```
CString m_strClass;
```

## <a name="cctrlviewm_dwdefaultstyle"></a><a name="m_dwdefaultstyle"></a>CCtrlView::m_dwDefaultStyle

Görünüm sınıfı için varsayılan stili içerir.

```
DWORD m_dwDefaultStyle;
```

### <a name="remarks"></a>Açıklamalar

Bu stil, bir pencere oluşturulduğunda uygulanır.

## <a name="cctrlviewondraw"></a><a name="ondraw"></a>CCtrlView::OnDraw

Belirtilen aygıt bağlamını kullanarak nesnenin `CCtrlView` içeriğini çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Çizimin gerçekleştiği aygıt bağlamına işaretçi.

### <a name="remarks"></a>Açıklamalar

`OnDraw`genellikle ekran ekranı için çağrılır, *pDC*tarafından belirtilen bir ekran aygıtı bağlamı geçirerek.

## <a name="cctrlviewprecreatewindow"></a><a name="precreatewindow"></a>CCtrlView::Pyeniden CreateWindow

Bu `CWnd` nesneye bağlı Windows penceresi nin oluşturulmasından önce çağrılır.

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Parametreler

*Cs*<br/>
[CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Pencere oluşturma devam ederse sıfır olmayan; Oluşturma hatası göstermek için 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi asla doğrudan aramayın.

Bu işlevin varsayılan uygulaması NULL pencere sınıf adını denetler ve uygun bir varsayılan ın yerine geçer. Pencere oluşturulmadan önce yapıyı `CREATESTRUCT` değiştirmek için bu üye işlevi geçersiz kılın.

Türetilen `CCtrlView` her sınıf, `PreCreateWindow`geçersiz kılmaya kendi işlevini ekler. Tasarım gereği, bu türevleri `PreCreateWindow` belgelenmez. Her sınıfa uygun stilleri ve stiller arasındaki bağımlılıkları belirlemek için, uygulamanızın taban sınıfı için MFC kaynak kodunu inceleyebilirsiniz. Geçersiz kılmayı `PreCreateWindow`seçerseniz, uygulamanızın taban sınıfında kullanılan stillerin MFC kaynak kodundan toplanan bilgileri kullanarak gereksinim duyduğunuz işlevselliği sağlayıp sağlamadığını belirleyebilirsiniz.

Pencere stillerini değiştirme hakkında daha fazla bilgi için, [MFC tarafından oluşturulan pencerenin stillerini değiştirme](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md)bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CTreeView Sınıfı](../../mfc/reference/ctreeview-class.md)<br/>
[CListView Sınıfı](../../mfc/reference/clistview-class.md)<br/>
[CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
