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
ms.openlocfilehash: 5bfff575861d92eaaef07a1f2f21b79d89cb52b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653641"
---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite sınıfı

`CAutoHideDockSite` Genişletir [CDockSite sınıfı](../../mfc/reference/cdocksite-class.md) otomatik gizleme dock panellerini uygulamak için.

## <a name="syntax"></a>Sözdizimi

```
class CAutoHideDockSite : public CDockSite
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Ad|Açıklama|
|`CAutoHideDockSite::CAutoHideDockSite`|Oluşturur bir `CAutoHideDockSite` nesne.|
|`CAutoHideDockSite::~CAutoHideDockSite`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Belirtir olup olmadığını `CAutoHideDockSite` bölmesi menüsünde görüntülenir.|
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|Temel bölmesi nesnesi dan türetilip türetilmediğini belirler [CMFCAutoHideBar sınıfı](../../mfc/reference/cmfcautohidebar-class.md).|
|[CAutoHideDockSite::DockPane](#dockpane)|Bir bölme için docks `CAuotHideDockSite` nesne.|
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|Ekran koordinatları dock sitesine VHD'nin boyutunu alır.|
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|Üzerinde bölmesinde yeniden çizer `CAutoHideDockSite` genel kenar boşlukları ve düğme aralığı.|
|[CAutoHideDockSite::SetOffsetLeft](#setoffsetleft)|Kenar boşluğu takma çubuğu sol tarafında ayarlar.|
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|Kenar boşluğu yerleştirme çubuğunun sağ tarafında ayarlar.|
|[CAutoHideDockSite::UnSetAutoHideMode](#unsetautohidemode)|Çağrıları [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) nesnelerin `CAutoHideDockSite`.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|Ad|Açıklama|
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|Araç çubukları ve yerleştirme çubuğu kenarı arasındaki boşluk boyutunu tanımlar. Bu alan, sol kenarı veya üst kenarı, dock alanı hizalama bağlı olarak ölçülür.|

## <a name="remarks"></a>Açıklamalar

Çağırdığınızda [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes), çerçeve otomatik olarak oluşturur bir `CAutoHideDockSite` nesne. Çoğu durumda, örneği veya doğrudan bu sınıfı kullanmanız gerekmez.

Yerleştirme bölmesinin sol tarafındaki sol tarafındaki arasındaki aralık yerleştirme çubuğudur [CMFCAutoHideButton sınıfı](../../mfc/reference/cmfcautohidebutton-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl alınacağını gösterir. bir `CAutoHideDockSite` nesnesinden bir `CMFCAutoHideBar` nesne ve yerleştirme çubuğunun sol ve sağ kenar boşluklarını ayarlama.

[!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxautohidedocksite.h

##  <a name="canacceptpane"></a>  CAutoHideDockSite::CanAcceptPane

Temel bölme olup olmadığını belirleyen bir [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesne veya türetilmiş `CMFCAutoHideBar`.

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pBar*|[in] Framework testleri temel bölme.|

### <a name="return-value"></a>Dönüş Değeri

TRUE ise *pBar* türetilir `CMFCAutoHideBar`; FALSE Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Temel bölmesi nesnesi türetilir, `CMFCAutoHideBar`, içerebileceği bir `CAutoHideDockSite`.

##  <a name="dockpane"></a>  CAutoHideDockSite::DockPane

Bir bölme için docks [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) nesne.

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
|*pWnd*|[in] Framework noktaları bölmesi.|
|*dockMethod*|[in] Seçenekler bölmesi için yerleştirme.|
|*lpRect*|[in] Yerleştirilmiş bölmenin sınırlarını belirten bir dikdörtgen.|

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama parametresini kullanmıyor *dockMethod*, gelecekte kullanılmak üzere sağlanır.

Varsa *lpRect* NULL ise framework bölmesinin dock site sunucusundaki varsayılan konumu koyar. Dock sitesiyle yatay ise, varsayılan dock sitesiyle sol ucundaki konumdur. Aksi takdirde, varsayılan konumu dock sitesiyle başında ' dir.

##  <a name="getalignrect"></a>  CAutoHideDockSite::GetAlignRect

Ekran koordinatları dock sitesine VHD'nin boyutunu alır.

```
void GetAlignRect(CRect& rect) const;
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*Rect*|[in] Bir dikdörtgen bir başvuru. Yöntemi, bu dikdörtgenin içindeki dock sitesiyle boyutunu depolar.|

### <a name="remarks"></a>Açıklamalar

Böylece dahil edilmez dikdörtgen uzaklık kenar boşluklarını ayarlanır.

##  <a name="m_nextraspace"></a>  CAutoHideDockSite::m_nExtraSpace

Kenarları arasındaki boşluk boyutunu [CAutoHideDockSite sınıfı](../../mfc/reference/cautohidedocksite-class.md) ve [CMFCAutoHideBar sınıfı](../../mfc/reference/cmfcautohidebar-class.md) nesneleri.

```
static int m_nExtraSpace;
```

### <a name="remarks"></a>Açıklamalar

Olduğunda bir `CMFCAutoHideBar` , yerleşik bir `CAutoHideDockSite`, tüm dock sitesiyle bulunması gereken değil. Bu genel değişkeni sol veya üst kenarlığını arasında ek boşluk denetimleri `CMFCAutoHideBar` ve karşılık gelen `CAutoHideDockSite` edge. Üst veya sol Köşeden kullanılıp kullanılmadığını geçerli hizalamayı bağlıdır.

##  <a name="setoffsetleft"></a>  CAutoHideDockSite::SetOffsetLeft

Kenar boşluğu takma çubuğu sol tarafında ayarlar.

```
void SetOffsetLeft(int nOffset);
```

### <a name="parameters"></a>Parametreler

*nOffset*<br/>
[in] Yeni uzaklığı.

### <a name="remarks"></a>Açıklamalar

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesneler üzerinde statik olarak konumlandırılmıştır `CAutoHideDockSite` nesne. Bu kullanıcı konumunu el ile değiştiremez anlamına gelir `CMFCAutoHideBar` nesneleri. `SetOffsetLeft` Yöntemi en soldaki sol tarafındaki arasındaki boşluğu denetleyen `CMFCAutoHideBar` ve sol tarafındaki `CAutoHideDockSite`.

##  <a name="setoffsetright"></a>  CAutoHideDockSite::SetOffsetRight

Kenar boşluğu yerleştirme çubuğunun sağ tarafında ayarlar.

```
void SetOffsetRight(int nOffset);
```

### <a name="parameters"></a>Parametreler

*nOffset*<br/>
[in] Yeni uzaklığı.

### <a name="remarks"></a>Açıklamalar

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesneler üzerinde statik olarak konumlandırılmıştır `CAutoHideDockSite` nesne. Bu kullanıcı konumunu el ile değiştiremez anlamına gelir `CMFCAutoHideBar` nesneleri. `SetOffsetRight` Yöntemi en sağdaki sağ tarafında arasındaki boşluğu denetleyen `CMFCAutoHideBar` ve sağ tarafında `CAutoHideDockSite`.

##  <a name="repositionpanes"></a>  CAutoHideDockSite::RepositionPanes

Bölmeleri üzerinde yeniden çizer [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md).

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*rectNewClientArea*|[in] Ayrılmış bir değer.|

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama kullanmaz *rectNewClientArea*. Bu, bölmeleri genel araç kenar boşluklarını ve düğme aralığı ile yeniden çizer.

##  <a name="unsetautohidemode"></a>  CAutoHideDockSite::UnSetAutoHideMode

Çağrıları [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) dock site nesneleri için.

```
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pAutoHideToolbar*|[in] Bir işaretçi bir [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesne bölmesinde bulunan `CAutoHideDockSite`.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem içeren satır için arar *pAutoHideToolbar*. Çağrı `CMFCAutoHideBar.UnSetAutoHideMode` tüm `CMFCAutoHideBar` satırının nesneleri. Varsa *pAutoHideToolbar* bulunamadı veya NULL ise, bu yöntemin çağırdığı `CMFCAutoHideBar.UnSetAutoHideMode` tüm `CMFCAutoHideBar` üzerindeki nesneleri `CAutoHideDockSite`.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite Sınıfı](../../mfc/reference/cdocksite-class.md)
