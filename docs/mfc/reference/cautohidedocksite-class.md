---
title: "CAutoHideDockSite sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8cc4e9158ae9ff2ef6fd4d48483aa5a75dd9617
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite sınıfı
`CAutoHideDockSite` Genişletir [CDockSite sınıfı](../../mfc/reference/cdocksite-class.md) otomatik gizleme uygulamak için bölmeleri sabitleyin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`CAutoHideDockSite::CAutoHideDockSite`|Oluşturan bir `CAutoHideDockSite` nesnesi.|  
|`CAutoHideDockSite::~CAutoHideDockSite`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Gösterir olup olmadığını `CAutoHideDockSite` bölmesi menüsünde gösterilir.|  
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|Temel bölmesi nesnesi türetildiği olup olmadığını belirler [CMFCAutoHideBar sınıfı](../../mfc/reference/cmfcautohidebar-class.md).|  
|[CAutoHideDockSite::DockPane](#dockpane)|Bölme için docks `CAuotHideDockSite` nesnesi.|  
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|Ekran koordinatları yerleştirme sitede boyutunu alır.|  
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|Bölmesinde üzerinde yeniden çizer `CAutoHideDockSite` genel kenar boşluklarını ve düğme aralığı.|  
|[CAutoHideDockSite::SetOffsetLeft](#setoffsetleft)|Kenar yerleştirme çubuğunun sol tarafında ayarlar.|  
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|Kenar yerleştirme çubuğu sağ tarafta ayarlar.|  
|[CAutoHideDockSite::UnSetAutoHideMode](#unsetautohidemode)|Çağrıları [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) nesnelerin `CAutoHideDockSite`.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|Araç çubukları yerleştirme çubuğu kenarı arasındaki boşluk boyutunu tanımlar. Bu alan, sol kenarı veya üst kenarı yerleştirme alanı hizalamasını bağlı olarak ölçülür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çağırdığınızda [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes), framework otomatik olarak oluşturur bir `CAutoHideDockSite` nesnesi. Çoğu durumda, örneği veya doğrudan bu sınıfı kullanmanız gerekmez.  
  
 Yerleştirme çubuğu yerleştirme bölmesi sol tarafındaki ve sol tarafındaki arasındaki boşluk olan [CMFCAutoHideButton sınıfı](../../mfc/reference/cmfcautohidebutton-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl alınacağını gösteren bir `CAutoHideDockSite` nesnesinin bir `CMFCAutoHideBar` nesne ve yerleştirme çubuğunun sağ ve sol kenar boşluklarını ayarlama.  
  
 [!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxautohidedocksite.h  
  
##  <a name="canacceptpane"></a>CAutoHideDockSite::CanAcceptPane  
 Temel bölme olup olmadığını belirleyen bir [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesne veya türetilmiş `CMFCAutoHideBar`.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`pBar`|Framework testleri temel bölme.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa `pBar` türetildiği `CMFCAutoHideBar`; `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel bölmesi nesnesi türetilir varsa `CMFCAutoHideBar`, oluşabilir bir `CAutoHideDockSite`.  
  
##  <a name="dockpane"></a>CAutoHideDockSite::DockPane  
 Bölme için docks [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) nesnesi.  
  
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
|[in]`pWnd`|Framework noktalarını bölme.|  
|[in]`dockMethod`|Bölmesinde seçeneklerini yerleştirme.|  
|[in]`lpRect`|Yerleştirilmiş bölmenin sınırları belirtir dikdörtgen.|  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama parametresi kullanmaz `dockMethod`, gelecekte kullanılmak üzere sağlanır.  
  
 Varsa `lpRect` olan `NULL`, framework bölmesinde yerleştirme sitesinde varsayılan konuma koyan. Yerleştirme yatay siteyse, varsayılan yerleştirme site sol kadar konumdur. Aksi takdirde, varsayılan yerleştirme site üstünde konumdur.  
  
##  <a name="getalignrect"></a>CAutoHideDockSite::GetAlignRect  
 Ekran koordinatları yerleştirme sitede boyutunu alır.  
  
```  
void GetAlignRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`rect`|Dikdörtgene referansı. Yöntemi bu dikdörtgenin içindeki yerleştirme site boyutunu depolar.|  
  
### <a name="remarks"></a>Açıklamalar  
 Böylece dahil edilmez dikdörtgen uzaklık kenar boşlukları için ayarlanır.  
  
##  <a name="m_nextraspace"></a>CAutoHideDockSite::m_nExtraSpace  
 Kenarları arasındaki boşluk boyutunu [CAutoHideDockSite sınıfı](../../mfc/reference/cautohidedocksite-class.md) ve [CMFCAutoHideBar sınıfı](../../mfc/reference/cmfcautohidebar-class.md) nesneleri.  
  
```  
static int m_nExtraSpace;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman bir `CMFCAutoHideBar` adresindeki yerleşik bir `CAutoHideDockSite`, tüm yerleştirme site bulunması gereken değil. Bu genel değişkeni sol veya üst kenarlığı arasında ek boşluk denetimleri `CMFCAutoHideBar` ve karşılık gelen `CAutoHideDockSite` sınır. Üst veya sol Köşeden kullanılıp kullanılmadığını geçerli hizalamayı bağlıdır.  
  
##  <a name="setoffsetleft"></a>CAutoHideDockSite::SetOffsetLeft  
 Kenar yerleştirme çubuğunun sol tarafında ayarlar.  
  
```  
void SetOffsetLeft(int nOffset);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nOffset`  
 Yeni uzaklığı.  
  
### <a name="remarks"></a>Açıklamalar  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesneler üzerinde statik olarak konumlandırıldığı `CAutoHideDockSite` nesnesi. Bu kullanıcı konumunu el ile değiştiremez anlamına gelir `CMFCAutoHideBar` nesneleri. `SetOffsetLeft` Yöntemi denetimleri en solundaki sol tarafındaki arasındaki boşluğu `CMFCAutoHideBar` ve sol tarafındaki `CAutoHideDockSite`.  
  
##  <a name="setoffsetright"></a>CAutoHideDockSite::SetOffsetRight  
 Kenar yerleştirme çubuğu sağ tarafta ayarlar.  
  
```  
void SetOffsetRight(int nOffset);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nOffset`  
 Yeni uzaklığı.  
  
### <a name="remarks"></a>Açıklamalar  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesneler üzerinde statik olarak konumlandırıldığı `CAutoHideDockSite` nesnesi. Bu kullanıcı konumunu el ile değiştiremez anlamına gelir `CMFCAutoHideBar` nesneleri. `SetOffsetRight` Yöntemi denetimleri en sağdaki sağ tarafındaki arasındaki boşluğu `CMFCAutoHideBar` ve sağ tarafındaki `CAutoHideDockSite`.  
  
##  <a name="repositionpanes"></a>CAutoHideDockSite::RepositionPanes  
 Üzerinde bölmeleri yeniden çizer [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md).  
  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`rectNewClientArea`|Ayrılmış bir değer.|  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama kullanmayan `rectNewClientArea`. Bu düğme aralığı ve genel araç kenar boşluklarını bölmeleri yeniden çizer.  
  
##  <a name="unsetautohidemode"></a>CAutoHideDockSite::UnSetAutoHideMode  
 Çağrıları [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) yerleştirme sitesindeki nesneler için.  
  
```  
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`pAutoHideToolbar`|Bir işaretçi bir [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) nesne bölmesinde bulunan `CAutoHideDockSite`.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem arar içeren satırı için `pAutoHideToolbar`. Çağırır `CMFCAutoHideBar.UnSetAutoHideMode` tüm `CMFCAutoHideBar` satır nesnelerde. Varsa `pAutoHideToolbar` bulunamadı veya `NULL`, bu yöntemi çağırır `CMFCAutoHideBar.UnSetAutoHideMode` tüm `CMFCAutoHideBar` üzerinde nesneleri `CAutoHideDockSite`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CDockSite Sınıfı](../../mfc/reference/cdocksite-class.md)
