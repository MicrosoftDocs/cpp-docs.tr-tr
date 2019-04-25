---
title: CMFCDropDownFrame sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
helpviewer_keywords:
- CMFCDropDownFrame [MFC], Create
- CMFCDropDownFrame [MFC], GetParentMenuBar
- CMFCDropDownFrame [MFC], GetParentPopupMenu
- CMFCDropDownFrame [MFC], RecalcLayout
- CMFCDropDownFrame [MFC], SetAutoDestroy
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
ms.openlocfilehash: 534dc90443371c8440e0cb317540f2cf80f6eacc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237379"
---
# <a name="cmfcdropdownframe-class"></a>CMFCDropDownFrame sınıfı

Aşağı açılan araç çubukları ve açılır araç çubuğu düğmeleri için açılır çerçeve penceresi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDropDownFrame : public CMiniFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Ad|Açıklama|
|`CMFCDropDownFrame::CMFCDropDownFrame`|Varsayılan Oluşturucu.|
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CMFCDropDownFrame::Create](#create)|Oluşturur bir `CMFCDropDownFrame` nesne.|
|`CMFCDropDownFrame::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|Aşağı açılan çerçevenin üst menü çubuğu alır.|
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|Aşağı açılan çerçevenin üst açılır menü alır.|
|`CMFCDropDownFrame::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|Aşağı açılan çerçeve yeniden konumlandırır.|
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|Alt açılan araç penceresi otomatik olarak edildiğinde olup olmadığını belirler.|

### <a name="remarks"></a>Açıklamalar

Bu sınıf doğrudan sizin kodunuzdan kullanılmak üzere tasarlanmamıştır.

Framework için çerçeve davranışı sağlamak için bu sınıfın kullandığı `CMFCDropDownToolbar` ve `CMFCDropDownToolbarButton` sınıfları. Bu sınıflar hakkında daha fazla bilgi için bkz. [CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md) ve [CMFCDropDownToolbarButton sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir işaretçi almak gösterilmiştir bir `CMFCDropDownFrame` nesnesinden bir `CFrameWnd` sınıfı ve alt otomatik olarak yok edilecek açılan araç penceresi ayarlama.

[!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdropdowntoolbar.h

##  <a name="create"></a>  CMFCDropDownFrame::Create

Oluşturur bir `CMFCDropDownFrame` nesne.

```
virtual BOOL Create(
    CWnd* pWndParent,
    int x,
    int y,
    CMFCDropDownToolBar* pWndOriginToolbar);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pWndParent*|[in] Aşağı açılan çerçevenin üst pencere.|
|*x*|[in] Açılır çerçeve konumunu yatay Ekran koordinatı.|
|*Y*|[in] Açılır çerçeve konumunu dikey Ekran koordinatı.|
|*pWndOriginToolbar*|[in] Yeni açılan çerçeve nesnesi doldurmak için bu yöntemi kullanır açılır düğmeler olan araç çubuğu.|

### <a name="return-value"></a>Dönüş Değeri

Aşağı açılan çerçeve başarıyla oluşturulursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı temel [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) WS_POPUP stili açılan çerçeve penceresi oluşturmak için yöntemi. Belirtilen ekran koordinatlarda açılır çerçeve penceresinde görünür. Bu yöntem, başarısız [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) yöntem FALSE döndürür.

`CMFCDropDownFrame` Sınıf dosyasının bir kopyasını oluşturur `CMFCDropDownToolBar` parametresi. Bu yöntem, düğmeyi görüntüler ve düğme durumları kopyalar `pWndOriginToolbar` parametresi `m_pWndOriginToolbar` veri üyesi.

##  <a name="getparentmenubar"></a>  CMFCDropDownFrame::GetParentMenuBar

Aşağı açılan çerçevenin üst menü çubuğu alır.

```
CMFCMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üst menü çubuğu açılır çerçeve veya çerçeveyi üstü yoksa NULL bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, üst menü çubuğunun üst düğmesinden alır. Aşağı açılan çerçevenin üst düğmesi yok veya üst düğme hiçbir üst menü çubuğu bu yöntem NULL döndürür.

##  <a name="getparentpopupmenu"></a>  CMFCDropDownFrame::GetParentPopupMenu

Aşağı açılan çerçevenin üst açılır menü alır.

```
CMFCDropDownFrame* GetParentPopupMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üst açılan menüsünün çerçevenin üst öğe yoksa null değeri veya açılır çerçeve işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, üst menü üst düğmesinden alır. Aşağı açılan çerçevenin üst düğmesi yok veya üst düğme üst menü yok, bu yöntem NULL döndürür.

##  <a name="recalclayout"></a>  CMFCDropDownFrame::RecalcLayout

Aşağı açılan çerçeve yeniden konumlandırır.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*bNotify*|[in] Kullanılmayan.|

### <a name="remarks"></a>Açıklamalar

Aşağı açılan çerçeve oluşturulduğunda veya üst pencere yeniden boyutlandırıldı, framework bu yöntemi çağırır. Bu yöntem, üst pencere boyutunu ve konumunu kullanarak açılır çerçeve boyutunu ve konumunu hesaplar.

##  <a name="setautodestroy"></a>  CMFCDropDownFrame::SetAutoDestroy

Alt açılan araç penceresi otomatik olarak edildiğinde olup olmadığını belirler.

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*bAutoDestroy*<br/>
[in] Otomatik olarak ilişkili açılan araç penceresini yok etmek için TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Varsa *bAutoDestroy* doğru ise, ardından `CMFCDropDownFrame` yok Edicisi ilişkili açılan araç penceresini yok eder. Varsayılan değer True'dur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDropDownToolBar Sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFCDropDownToolbarButton Sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
