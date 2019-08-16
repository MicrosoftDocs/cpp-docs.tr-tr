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
ms.openlocfilehash: 334f139b81afeb06d57cbd128abe9e413b1fd0e7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507157"
---
# <a name="cctrlview-class"></a>CCtrlView sınıfı

Belge görünümü mimarisini Windows 98 ve Windows NT sürüm 3,51 ve üzeri tarafından desteklenen ortak denetimlerle uyum sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CCtrlView : public CView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCtrlView::CCtrlView](#cctrlview)|Bir `CCtrlView` nesnesi oluşturur.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCtrlView:: OnDraw](#ondraw)|Çerçeve tarafından belirtilen cihaz bağlamı kullanılarak çizilecek şekilde çağırılır.|
|[CCtrlView::P reCreateWindow](#precreatewindow)|Bu `CCtrlView` nesneye eklenmiş Windows penceresini oluşturmadan önce çağırılır.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|Görünüm sınıfının varsayılan stilini içerir.|
|[CCtrlView::m_strClass](#m_strclass)|Görünüm sınıfının Windows sınıf adını içerir.|

## <a name="remarks"></a>Açıklamalar

Sınıf `CCtrlView` ve türevleri, [CEditView](../../mfc/reference/ceditview-class.md), [clienstview](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), ve [CRichEditView](../../mfc/reference/cricheditview-class.md), belge görünümü mimarisini Windows 95/98 ve Windows NT sürümleri 3,51 tarafından desteklenen yeni ortak denetimlere uyarlar. ve üzeri. Belge-görünüm mimarisi hakkında daha fazla bilgi için bkz. [belge/görünüm mimarisi](../../mfc/document-view-architecture.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CCtrlView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="cctrlview"></a>CCtrlView::CCtrlView

Bir `CCtrlView` nesnesi oluşturur.

```
CCtrlView(
    LPCTSTR lpszClass,
    DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*lpszClass*<br/>
Görünüm sınıfının Windows sınıf adı.

*dwStyle*<br/>
Görünüm sınıfının stili.

### <a name="remarks"></a>Açıklamalar

Çerçeve, yeni bir çerçeve penceresi oluşturulduğunda veya pencere bölündüğünde oluşturucuyu çağırır. Görünümü belge eklendikten sonra başlatmak için [CView:: OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) 'i geçersiz kılın. Windows nesnesini oluşturmak için [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) veya [CWnd:: CreateEx](../../mfc/reference/cwnd-class.md#createex) öğesini çağırın.

##  <a name="m_strclass"></a>CCtrlView::m_strClass

Görünüm sınıfının Windows sınıf adını içerir.

```
CString m_strClass;
```

##  <a name="m_dwdefaultstyle"></a>CCtrlView::m_dwDefaultStyle

Görünüm sınıfının varsayılan stilini içerir.

```
DWORD m_dwDefaultStyle;
```

### <a name="remarks"></a>Açıklamalar

Bu stil bir pencere oluşturulduğunda uygulanır.

##  <a name="ondraw"></a>CCtrlView:: OnDraw

Belirtilen cihaz bağlamı kullanılarak `CCtrlView` nesnenin içeriğini çizmek için Framework tarafından çağırılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Çizimin gerçekleştiği cihaz bağlamına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`OnDraw`genellikle ekran görüntüleme için çağrılır, *PDC*tarafından belirtilen bir ekran cihaz bağlamı geçer.

##  <a name="precreatewindow"></a>CCtrlView::P reCreateWindow

Bu `CWnd` nesneye eklenmiş Windows penceresini oluşturmadan önce çağırılır.

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
[CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Pencere oluşturma işleminin devam etmesi gerekiyorsa sıfır dışı; oluşturma hatasını göstermek için 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi hiçbir şekilde doğrudan çağırmayın.

Bu işlevin varsayılan uygulanması NULL pencere sınıfı adını denetler ve uygun bir varsayılan değer koyar. Pencere oluşturulmadan önce `CREATESTRUCT` yapıyı değiştirmek için bu üye işlevini geçersiz kılın.

Öğesinden `CCtrlView` türetilen her bir `PreCreateWindow`sınıf kendi işlevselliğini geçersiz kılma öğesine ekler. Tasarım yaparak, bu türetmeler `PreCreateWindow` açıklanmamıştır. Her sınıfa uygun stilleri ve stiller arasındaki bağımlılıkları öğrenmek için, uygulamanızın temel sınıfı için MFC kaynak kodunu inceleyebilirsiniz. Geçersiz kılmayı `PreCreateWindow`seçerseniz, uygulamanızın temel sınıfında kullanılan stillerin, MFC kaynak kodundan toplanan bilgileri kullanarak ihtiyacınız olan işlevleri sağlayıp sağlamadığını belirleyebilirsiniz.

Pencere stillerini değiştirme hakkında daha fazla bilgi için bkz. [MFC tarafından oluşturulan pencerenin stillerini değiştirme](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CTreeView Sınıfı](../../mfc/reference/ctreeview-class.md)<br/>
[CListView Sınıfı](../../mfc/reference/clistview-class.md)<br/>
[CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
