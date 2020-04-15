---
title: CAutoHideDockSite Sınıfı
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
ms.openlocfilehash: 3a4593ac17f0af26517144edb7b01a9ca4203b1a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352975"
---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite Sınıfı

Otomatik `CAutoHideDockSite` gizleme dock bölmeleri uygulamak için [CDockSite Sınıf](../../mfc/reference/cdocksite-class.md) genişletir.

## <a name="syntax"></a>Sözdizimi

```
class CAutoHideDockSite : public CDockSite
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|`CAutoHideDockSite::CAutoHideDockSite`|Bir `CAutoHideDockSite` nesne inşa eder.|
|`CAutoHideDockSite::~CAutoHideDockSite`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Bölme menüsünde gösterip `CAutoHideDockSite` gösterilmediğini gösterir.|
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|[CmFCAutoHideBar Sınıfı'ndan](../../mfc/reference/cmfcautohidebar-class.md)bir temel bölme nesnesinin türetilip türetilmediğini belirler.|
|[CAutoHideDockSite::DockPane](#dockpane)|Bu `CAuotHideDockSite` nesneye bir bölme yapıştırıyor.|
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|Ekran koordinatlarında dock alanının boyutunu alır.|
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|Genel kenar boşlukları ve `CAutoHideDockSite` düğme aralığı yla bölmeyi yeniden çizer.|
|[CautoHideDockSite::SetoffsetLeft](#setoffsetleft)|Yanaşma çubuğunun sol tarafındaki kenar boşluğunu ayarlar.|
|[CautoHideDockSite::SetoffsetRight](#setoffsetright)|Kenar boşluğunu yanaşma çubuğunun sağ tarafında ayarlar.|
|[CautoHideDockSite::unsetautohidemode](#unsetautohidemode)|Aramalar [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) üzerinde nesneler `CAutoHideDockSite`için .|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|Adı|Açıklama|
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|Araç çubukları ile yerleştirme çubuğunun kenarı arasındaki boşluğun boyutunu tanımlar. Bu boşluk, dock alanının hizalanmasına bağlı olarak sol kenardan veya üst kenardan ölçülür.|

## <a name="remarks"></a>Açıklamalar

[CFrameWndEx::EnableAutoHidePanes'i](../../mfc/reference/cframewndex-class.md#enableautohidepanes)aradiğinizde, çerçeve otomatik `CAutoHideDockSite` olarak bir nesne oluşturur. Çoğu durumda, bu sınıfı doğrudan anlık olarak veya kullanmanız gerekmez.

Yerleştirme çubuğu, dock bölmesinin sol tarafı ile [CMFCAutoHideButton Sınıfının](../../mfc/reference/cmfcautohidebutton-class.md)sol tarafı arasındaki boşluktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CAutoHideDockSite` `CMFCAutoHideBar` nesnenin bir nesneden nasıl alındığını ve yerleştirme çubuğunun sol ve sağ kenar boşluklarını nasıl ayarlayabilirsiniz'ı gösterir.

[!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxautohidedocksite.h

## <a name="cautohidedocksitecanacceptpane"></a><a name="canacceptpane"></a>CAutoHideDockSite::CanAcceptPane

Bir temel bölmenin [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesnesi `CMFCAutoHideBar`mi yoksa türetilmiş mi olduğunu belirler.

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pBar*|[içinde] Çerçevenin test ettiği temel bölme.|

### <a name="return-value"></a>Dönüş Değeri

*pBar* türetilmişse `CMFCAutoHideBar`DOĞRU; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bir taban bölme nesnesi `CMFCAutoHideBar`türetilmişse, bir `CAutoHideDockSite`.

## <a name="cautohidedocksitedockpane"></a><a name="dockpane"></a>CAutoHideDockSite::DockPane

Bu [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) nesnesine bir bölme yapıştırıyor.

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*Pwnd*|[içinde] Çerçevenin sabitolduğu bölme.|
|*dockMethod*|[içinde] Bölme için yerleştirme seçenekleri.|
|*Lprect*|[içinde] Kenetlenmiş bölmenin sınırlarını belirten bir dikdörtgen.|

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, ileride kullanılmak üzere sağlanan *dockMethod*parametresini kullanmaz.

*lpRect* NULL ise, çerçeve bölmeyi dock sitesinde varsayılan konuma yerletir. Dock sitesi yataysa, varsayılan konum dock alanının en solundadır. Aksi takdirde, varsayılan konum dock sitenin üst kısmındadır.

## <a name="cautohidedocksitegetalignrect"></a><a name="getalignrect"></a>CAutoHideDockSite::GetAlignRect

Ekran koordinatlarında dock alanının boyutunu alır.

```
void GetAlignRect(CRect& rect) const;
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*Rect*|[içinde] Dikdörtgen için bir başvuru. Yöntem, bu dikdörtgende dock sitenin boyutunu depolar.|

### <a name="remarks"></a>Açıklamalar

Dikdörtgen, eklenmemesi için ofset kenar boşlukları için ayarlanır.

## <a name="cautohidedocksitem_nextraspace"></a><a name="m_nextraspace"></a>CAutoHideDockSite::m_nExtraSpace

[CAutoHideDockSite Sınıfı'nın](../../mfc/reference/cautohidedocksite-class.md) kenarları ile [CMFCAutoHideBar Sınıfı](../../mfc/reference/cmfcautohidebar-class.md) nesneleri arasındaki boşluğun boyutu.

```
static int m_nExtraSpace;
```

### <a name="remarks"></a>Açıklamalar

Bir `CMFCAutoHideBar` deken, `CAutoHideDockSite`tüm dock site işgal etmemelidir. Bu genel değişken, ilgili `CMFCAutoHideBar` `CAutoHideDockSite` kenarın sol veya üst kenarı arasındaki ekstra boşluğu denetler. Üst veya sol kenarın kullanılıp kullanılmadığı geçerli hizalamaya bağlıdır.

## <a name="cautohidedocksitesetoffsetleft"></a><a name="setoffsetleft"></a>CautoHideDockSite::SetoffsetLeft

Yanaşma çubuğunun sol tarafındaki kenar boşluğunu ayarlar.

```
void SetOffsetLeft(int nOffset);
```

### <a name="parameters"></a>Parametreler

*nOffset*<br/>
[içinde] Yeni ofset.

### <a name="remarks"></a>Açıklamalar

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesneleri `CAutoHideDockSite` statik olarak nesne üzerinde konumlandırılır. Bu, kullanıcının `CMFCAutoHideBar` nesnelerin konumunu el ile değiştiremeyeceği anlamına gelir. Yöntem, `SetOffsetLeft` sol-en `CMFCAutoHideBar` sol tarafı ve sol tarafı arasındaki aralığı `CAutoHideDockSite`denetler.

## <a name="cautohidedocksitesetoffsetright"></a><a name="setoffsetright"></a>CautoHideDockSite::SetoffsetRight

Kenar boşluğunu yanaşma çubuğunun sağ tarafında ayarlar.

```
void SetOffsetRight(int nOffset);
```

### <a name="parameters"></a>Parametreler

*nOffset*<br/>
[içinde] Yeni ofset.

### <a name="remarks"></a>Açıklamalar

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesneleri `CAutoHideDockSite` statik olarak nesne üzerinde konumlandırılır. Bu, kullanıcının `CMFCAutoHideBar` nesnelerin konumunu el ile değiştiremeyeceği anlamına gelir. Yöntem, `SetOffsetRight` sağ-en `CMFCAutoHideBar` sağ tarafı ile sağ tarafı arasındaki aralığı `CAutoHideDockSite`denetler.

## <a name="cautohidedocksiterepositionpanes"></a><a name="repositionpanes"></a>CAutoHideDockSite::RepositionPanes

[CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)üzerinde bölmeleri redraws .

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*rectNewClientArea*|[içinde] Ayrılmış bir değer.|

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama *rectNewClientArea*kullanmaz. Bölmeleri genel araç çubuğu kenar boşlukları ve düğme aralığıyla yeniden çizer.

## <a name="cautohidedocksiteunsetautohidemode"></a><a name="unsetautohidemode"></a>CautoHideDockSite::unsetautohidemode

[CMFCAutoHideBar çağırır::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) dock sitesinde nesneler için.

```
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pAutoHideToolbar*|[içinde] Üzerinde bulunan [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesne bölmesine `CAutoHideDockSite`işaretçi.|

### <a name="remarks"></a>Açıklamalar

Bu *yöntem, pAutoHideToolbar*içeren satırı arar. O `CMFCAutoHideBar.UnSetAutoHideMode` satırdaki `CMFCAutoHideBar` tüm nesneleri çağırır. *pAutoHideToolbar* bulunamadı veya NULL ise, bu `CMFCAutoHideBar.UnSetAutoHideMode` yöntem tüm `CMFCAutoHideBar` nesneleri `CAutoHideDockSite`çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite Sınıfı](../../mfc/reference/cdocksite-class.md)
