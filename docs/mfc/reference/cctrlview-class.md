---
title: CCtrlView sınıfı
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
ms.openlocfilehash: 5cb68ab46e2cac8b2f1dcc13989077e32480a2c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262612"
---
# <a name="cctrlview-class"></a>CCtrlView sınıfı

Belge / görünüm mimarisi için Windows 98 ve Windows NT tarafından 3.51 sürümü ve sonraki sürümlerde desteklenen ortak denetimlere uyum sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CCtrlView : public CView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCtrlView::CCtrlView](#cctrlview)|Oluşturur bir `CCtrlView` nesne.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCtrlView::OnDraw](#ondraw)|Belirtilen bir cihaz bağlamı kullanma çizmek için framework tarafından çağırılır.|
|[CCtrlView::PreCreateWindow](#precreatewindow)|Şuna bağlı Windows penceresi oluşturulmasını önce çağırılır `CCtrlView` nesne.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|Görünüm sınıfı için varsayılan stili içerir.|
|[CCtrlView::m_strClass](#m_strclass)|Görünüm sınıfını Windows sınıf adı içeriyor.|

## <a name="remarks"></a>Açıklamalar

Sınıf `CCtrlView` ve kendi türevleri [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), ve [CRichEditView](../../mfc/reference/cricheditview-class.md), uyum Belge / görünüm mimarisi yeni ortak denetimleri için Windows 95/98 ve Windows NT 3.51 sürümü ve sonraki sürümlerde desteklenir. Belge / görünüm mimarisi hakkında daha fazla bilgi için bkz. [belge/görünüm mimarisi](../../mfc/document-view-architecture.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CCtrlView`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cctrlview"></a>  CCtrlView::CCtrlView

Oluşturur bir `CCtrlView` nesne.

```
CCtrlView(
    LPCTSTR lpszClass,
    DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*lpszClass*<br/>
Windows sınıf adı görünüm sınıfı.

*dwStyle*<br/>
Görünüm sınıfını stili.

### <a name="remarks"></a>Açıklamalar

Framework, yeni bir çerçeve penceresi oluşturulduğunda veya bir pencereyi bölme oluşturucuyu çağırır. Geçersiz kılma [CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) belgeye eklendikten sonra Görünüm başlatılamadı. Çağrı [CWnd::Create](../../mfc/reference/cwnd-class.md#create) veya [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) Windows nesneyi oluşturmak için.

##  <a name="m_strclass"></a>  CCtrlView::m_strClass

Görünüm sınıfını Windows sınıf adı içeriyor.

```
CString m_strClass;
```

##  <a name="m_dwdefaultstyle"></a>  CCtrlView::m_dwDefaultStyle

Görünüm sınıfı için varsayılan stili içerir.

```
DWORD m_dwDefaultStyle;
```

### <a name="remarks"></a>Açıklamalar

Bir pencere oluşturulduğunda bu stil uygulanır.

##  <a name="ondraw"></a>  CCtrlView::OnDraw

İçeriği çizmek için framework tarafından çağırılır `CCtrlView` belirtilen bir cihaz bağlamı kullanma nesne.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Çizim oluştuğu cihaz bağlamı için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`OnDraw` ekran görüntüsü, ekran, tarafından belirtilen bir cihaz bağlamı geçirme için genellikle adlı *pDC*.

##  <a name="precreatewindow"></a>  CCtrlView::PreCreateWindow

Şuna bağlı Windows penceresi oluşturulmasını önce çağırılır `CWnd` nesne.

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Parametreler

*cs*<br/>
A [CREATESTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcreatestructa) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Pencere oluşturma devam etmelidir olursa sıfır dışı; oluşturma hatası göstermek için 0'ı tıklatın.

### <a name="remarks"></a>Açıklamalar

Hiçbir zaman doğrudan bu işlevi çağırın.

Bu işlev varsayılan uygulaması için bir NULL pencere sınıf adı denetler ve uygun bir varsayılan yerini alır. Değiştirmek için bu üye işlevi geçersiz kılma `CREATESTRUCT` pencere oluşturulmadan önce yapılandırın.

Her sınıf için türetilen `CCtrlView` kendi işlevi için geçersiz kılma ekler `PreCreateWindow`. Tasarıma göre bu türetme, `PreCreateWindow` belirtilmeyen. Her bir sınıf ve stilleri birbirine uygun stilleri belirlemek için uygulamanızın temel sınıf için MFC kaynak kodu inceleyebilirsiniz. Geçersiz kılmayı seçerseniz `PreCreateWindow`, uygulamanızın temel sınıfta kullanılan stilleri MFC kaynak kodundan topladığınız bilgileri kullanarak gereksinim duyduğunuz işlevselliğini sağlamak olup olmadığını belirleyebilirsiniz.

Pencere stilleri değiştirme hakkında daha fazla bilgi için bkz. [penceresinde oluşturulan MFC tarafından stillerini değiştirme](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CTreeView Sınıfı](../../mfc/reference/ctreeview-class.md)<br/>
[CListView Sınıfı](../../mfc/reference/clistview-class.md)<br/>
[CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
