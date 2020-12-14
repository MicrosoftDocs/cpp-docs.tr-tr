---
description: 'Daha fazla bilgi edinin: CCtrlView Class'
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
ms.openlocfilehash: b9cb3d9e32772e0d54d23acfc7606dbc45071446
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227773"
---
# <a name="cctrlview-class"></a>CCtrlView sınıfı

Belge görünümü mimarisini Windows 98 ve Windows NT sürüm 3,51 ve üzeri tarafından desteklenen ortak denetimlerle uyum sağlar.

## <a name="syntax"></a>Syntax

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
|[CCtrlView::P reCreateWindow](#precreatewindow)|Bu nesneye eklenmiş Windows penceresini oluşturmadan önce çağırılır `CCtrlView` .|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCtrlView:: m_dwDefaultStyle](#m_dwdefaultstyle)|Görünüm sınıfının varsayılan stilini içerir.|
|[CCtrlView:: m_strClass](#m_strclass)|Görünüm sınıfının Windows sınıf adını içerir.|

## <a name="remarks"></a>Açıklamalar

Sınıf `CCtrlView` ve türevleri, [CEditView](../../mfc/reference/ceditview-class.md), [clienstview](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), ve [CRichEditView](../../mfc/reference/cricheditview-class.md), belge görünümü mimarisini Windows 95/98 ve Windows NT sürümleri 3,51 ve üzeri tarafından desteklenen yeni ortak denetimlere uyarlar. Belge-görünüm mimarisi hakkında daha fazla bilgi için bkz. [belge/görünüm mimarisi](../../mfc/document-view-architecture.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CCtrlView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cctrlviewcctrlview"></a><a name="cctrlview"></a> CCtrlView::CCtrlView

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

## <a name="cctrlviewm_strclass"></a><a name="m_strclass"></a> CCtrlView:: m_strClass

Görünüm sınıfının Windows sınıf adını içerir.

```
CString m_strClass;
```

## <a name="cctrlviewm_dwdefaultstyle"></a><a name="m_dwdefaultstyle"></a> CCtrlView:: m_dwDefaultStyle

Görünüm sınıfının varsayılan stilini içerir.

```
DWORD m_dwDefaultStyle;
```

### <a name="remarks"></a>Açıklamalar

Bu stil bir pencere oluşturulduğunda uygulanır.

## <a name="cctrlviewondraw"></a><a name="ondraw"></a> CCtrlView:: OnDraw

Belirtilen cihaz bağlamı kullanılarak nesnenin içeriğini çizmek için Framework tarafından çağırılır `CCtrlView` .

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Çizimin gerçekleştiği cihaz bağlamına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`OnDraw` genellikle ekran görüntüleme için çağrılır, *PDC* tarafından belirtilen bir ekran cihaz bağlamı geçer.

## <a name="cctrlviewprecreatewindow"></a><a name="precreatewindow"></a> CCtrlView::P reCreateWindow

Bu nesneye eklenmiş Windows penceresini oluşturmadan önce çağırılır `CWnd` .

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

Bu işlevin varsayılan uygulanması NULL pencere sınıfı adını denetler ve uygun bir varsayılan değer koyar. Pencere oluşturulmadan önce yapıyı değiştirmek için bu üye işlevini geçersiz kılın `CREATESTRUCT` .

Öğesinden türetilen her `CCtrlView` bir sınıf kendi işlevselliğini geçersiz kılma öğesine ekler `PreCreateWindow` . Tasarım yaparak, bu türetmeler `PreCreateWindow` açıklanmamıştır. Her sınıfa uygun stilleri ve stiller arasındaki bağımlılıkları öğrenmek için, uygulamanızın temel sınıfı için MFC kaynak kodunu inceleyebilirsiniz. Geçersiz kılmayı seçerseniz `PreCreateWindow` , uygulamanızın temel sınıfında kullanılan stillerin, MFC kaynak kodundan toplanan bilgileri kullanarak ihtiyacınız olan işlevleri sağlayıp sağlamadığını belirleyebilirsiniz.

Pencere stillerini değiştirme hakkında daha fazla bilgi için bkz. [MFC tarafından oluşturulan pencerenin stillerini değiştirme](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[CView sınıfı](../../mfc/reference/cview-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CTreeView sınıfı](../../mfc/reference/ctreeview-class.md)<br/>
[CListView sınıfı](../../mfc/reference/clistview-class.md)<br/>
[CRichEditView sınıfı](../../mfc/reference/cricheditview-class.md)
