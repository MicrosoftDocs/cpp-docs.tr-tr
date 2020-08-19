---
title: CAutoHideDockSite sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::CanAcceptPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::DockPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::GetAlignRect
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::RepositionPanes
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetLeft
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetRight
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::UnSetAutoHideMode
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::m_nExtraSpace
helpviewer_keywords:
- CAutoHideDockSite [MFC], CanAcceptPane
- CAutoHideDockSite [MFC], DockPane
- CAutoHideDockSite [MFC], GetAlignRect
- CAutoHideDockSite [MFC], RepositionPanes
- CAutoHideDockSite [MFC], SetOffsetLeft
- CAutoHideDockSite [MFC], SetOffsetRight
- CAutoHideDockSite [MFC], UnSetAutoHideMode
- CAutoHideDockSite [MFC], m_nExtraSpace
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
ms.openlocfilehash: 2779e643b15179b0017535fbfbb144f94e1aedbe
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562018"
---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite sınıfı

, `CAutoHideDockSite` [CDockSite sınıfını](../../mfc/reference/cdocksite-class.md) genişleterek otomatik gizleme yerleştirme bölmelerini uygular.

## <a name="syntax"></a>Syntax

```
class CAutoHideDockSite : public CDockSite
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Ad|Açıklama|
|`CAutoHideDockSite::CAutoHideDockSite`|Bir `CAutoHideDockSite` nesnesi oluşturur.|
|`CAutoHideDockSite::~CAutoHideDockSite`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|`CAutoHideDockSite::AllowShowOnPaneMenu`|`CAutoHideDockSite`Bölmesinin bölme menüsünde gösterilip gösterilmeyeceğini gösterir.|
|[Cautohidedocksıte:: CanAcceptPane](#canacceptpane)|Bir taban bölmesi nesnesinin [CMFCAutoHideBar sınıfından](../../mfc/reference/cmfcautohidebar-class.md)türetilip türetilmediğini belirler.|
|[Cautohidedocksıte::D ockPane](#dockpane)|Bu nesneye bir bölme noktası oluşturma `CAuotHideDockSite` .|
|[Cautohidedocksıte:: Gethizalaması Rect](#getalignrect)|Dock sitesinin boyutunu ekran koordinatlarına göre alır.|
|[CAutoHideDockSite:: Depotionbölmeler](#repositionpanes)|İçindeki bölmesini, `CAutoHideDockSite` genel kenar boşlukları ve düğme aralığı ile yeniden çizer.|
|[Cautohidedocksıte:: SetOffsetLeft](#setoffsetleft)|Yerleştirme çubuğunun sol tarafındaki boşluğu ayarlar.|
|[Cautohidedocksıte:: SetOffsetRight](#setoffsetright)|Yerleştirme çubuğunun sağ tarafındaki boşluğu ayarlar.|
|[Cautohidedocksıte:: UnSetAutoHideMode](#unsetautohidemode)|İçindeki nesneler için [CMFCAutoHideBar:: UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) öğesini çağırır `CAutoHideDockSite` .|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|Ad|Açıklama|
|[CAutoHideDockSite:: m_nExtraSpace](#m_nextraspace)|Araç çubukları ve yerleştirme çubuğunun kenarı arasındaki alanın boyutunu tanımlar. Bu boşluk, yerleştirme alanının hizalamasına bağlı olarak, sol kenardan veya üst kenardan ölçülür.|

## <a name="remarks"></a>Açıklamalar

[CFrameWndEx:: Enableotomatik Hidebölmelerini](../../mfc/reference/cframewndex-class.md#enableautohidepanes)çağırdığınızda, çerçeve otomatik olarak bir `CAutoHideDockSite` nesne oluşturur. Çoğu durumda, bu sınıfı doğrudan örneği oluşturmak veya kullanmak zorunda değilsiniz.

Takma çubuğu, Dock bölmesinin sol tarafı ve [CMFCAutoHideButton sınıfının](../../mfc/reference/cmfcautohidebutton-class.md)sol tarafı arasındaki eksikdir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesneden bir nesnenin nasıl alınacağını `CAutoHideDockSite` `CMFCAutoHideBar` ve yerleştirme çubuğunun sol ve sağ kenar boşluklarını nasıl ayarlayabileceğinizi gösterir.

[!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxoto hidedocksite. h

## <a name="cautohidedocksitecanacceptpane"></a><a name="canacceptpane"></a> Cautohidedocksıte:: CanAcceptPane

Bir temel bölmenin [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesnesi olup olmadığını veya öğesinden türetilip türetilmediğini belirler `CMFCAutoHideBar` .

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parametreler

*pBar*\
'ndaki Framework 'ün test olduğu taban bölmesi.

### <a name="return-value"></a>Dönüş Değeri

*PBar* öğesinden TÜRETILDIYSE doğru `CMFCAutoHideBar` ; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bir taban bölmesi nesnesi öğesinden türetildiyse `CMFCAutoHideBar` , bir içerir `CAutoHideDockSite` .

## <a name="cautohidedocksitedockpane"></a><a name="dockpane"></a> Cautohidedocksıte::D ockPane

Bu [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) nesnesine bir bölme noktası oluşturma.

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

*pWnd*\
'ndaki Framework 'ün noktalarını belirten pencere.

*Dockyöntemi*\
'ndaki Bölme için yerleştirme seçenekleri.

*lpRect*\
'ndaki Yerleşik bölme için sınırları belirten bir dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, gelecekte kullanılmak üzere belirtilen *dockMethod*parametresini kullanmaz.

*LpRect* null ise Framework, bölmeyi Dock sitesindeki varsayılan konuma koyar. Dock sitesi yataysa, varsayılan konum dock sitesinin en sol tarafında bulunur. Aksi takdirde, varsayılan konum dock sitesinin en üstünde bulunur.

## <a name="cautohidedocksitegetalignrect"></a><a name="getalignrect"></a> Cautohidedocksıte:: Gethizalaması Rect

Dock sitesinin boyutunu ekran koordinatlarına göre alır.

```cpp
void GetAlignRect(CRect& rect) const;
```

### <a name="parameters"></a>Parametreler

*Rect*\
'ndaki Bir dikdörtgene başvuru. Yöntemi, dock sitesinin boyutunu bu dikdörtgende depolar.

### <a name="remarks"></a>Açıklamalar

Dikdörtgen, kenar boşlukları için, bu değerler dahil kalmayacak şekilde ayarlanır.

## <a name="cautohidedocksitem_nextraspace"></a><a name="m_nextraspace"></a> CAutoHideDockSite:: m_nExtraSpace

[CAutoHideDockSite sınıfının](../../mfc/reference/cautohidedocksite-class.md) kenarları Ile [CMFCAutoHideBar sınıf](../../mfc/reference/cmfcautohidebar-class.md) nesnelerinin kenarları arasındaki alanın boyutu.

```
static int m_nExtraSpace;
```

### <a name="remarks"></a>Açıklamalar

Bir bir öğesine `CMFCAutoHideBar` yerleştirildiğinde `CAutoHideDockSite` , tüm Dock sitesini kaplamamalıdır. Bu genel değişken, ve ilgili kenarın sol veya üst kenarlığı arasındaki ek boşluğu denetler `CMFCAutoHideBar` `CAutoHideDockSite` . Üst veya sol kenar kullanılıp kullanılmayacağını geçerli hizalamaya göre değişir.

## <a name="cautohidedocksitesetoffsetleft"></a><a name="setoffsetleft"></a> Cautohidedocksıte:: SetOffsetLeft

Yerleştirme çubuğunun sol tarafındaki boşluğu ayarlar.

```cpp
void SetOffsetLeft(int nOffset);
```

### <a name="parameters"></a>Parametreler

*nKonum*<br/>
'ndaki Yeni fark.

### <a name="remarks"></a>Açıklamalar

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesneleri, nesne üzerinde statik olarak konumlandırılır `CAutoHideDockSite` . Bu, kullanıcının nesnelerin konumunu el ile değiştiremeyeceği anlamına gelir `CMFCAutoHideBar` . `SetOffsetLeft`Yöntemi, öğesinin sol ve sol tarafının sol tarafı arasındaki boşluğu denetler `CMFCAutoHideBar` `CAutoHideDockSite` .

## <a name="cautohidedocksitesetoffsetright"></a><a name="setoffsetright"></a> Cautohidedocksıte:: SetOffsetRight

Yerleştirme çubuğunun sağ tarafındaki boşluğu ayarlar.

```cpp
void SetOffsetRight(int nOffset);
```

### <a name="parameters"></a>Parametreler

*nKonum*<br/>
'ndaki Yeni fark.

### <a name="remarks"></a>Açıklamalar

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesneleri, nesne üzerinde statik olarak konumlandırılır `CAutoHideDockSite` . Bu, kullanıcının nesnelerin konumunu el ile değiştiremeyeceği anlamına gelir `CMFCAutoHideBar` . `SetOffsetRight`Yöntemi `CMFCAutoHideBar` , öğesinin sağ ve sağ tarafının sağ tarafı arasındaki boşluğu denetler `CAutoHideDockSite` .

## <a name="cautohidedocksiterepositionpanes"></a><a name="repositionpanes"></a> CAutoHideDockSite:: Depotionbölmeler

[Cautohidedocksitesindeki](../../mfc/reference/cautohidedocksite-class.md)bölmeleri yeniden çizer.

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>Parametreler

*rectNewClientArea*\
'ndaki Ayrılmış bir değer.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama *rectNewClientArea*kullanmaz. Bölmeleri genel araç çubuğu kenar boşlukları ve düğme aralığı ile yeniden çizer.

## <a name="cautohidedocksiteunsetautohidemode"></a><a name="unsetautohidemode"></a> Cautohidedocksıte:: UnSetAutoHideMode

Dock sitesindeki nesneler için [CMFCAutoHideBar:: UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) öğesini çağırır.

```cpp
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```

### <a name="parameters"></a>Parametreler

*pAutoHideToolbar*\
'ndaki Üzerinde bulunan [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesne bölmesine yönelik bir işaretçi `CAutoHideDockSite` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem *pAutoHideToolbar*içeren satırı arar. `CMFCAutoHideBar.UnSetAutoHideMode` `CMFCAutoHideBar` Bu satırdaki tüm nesneleri çağırır. *PAutoHideToolbar* BULUNAMAZSA veya null ise, bu yöntem `CMFCAutoHideBar.UnSetAutoHideMode` `CMFCAutoHideBar` üzerindeki tüm nesneleri çağırır `CAutoHideDockSite` .

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite sınıfı](../../mfc/reference/cdocksite-class.md)
