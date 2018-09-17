---
title: Cmdıtabınfo sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo::Serialize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bAutoColor
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bDocumentMenu
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bEnableTabSwap
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bFlatFrame
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCloseButton
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCustomTooltips
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabIcons
- AFXMDICLIENTAREAWND/CMDITabInfo::m_nTabBorderSize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_style
- AFXMDICLIENTAREAWND/CMDITabInfo::m_tabLocation
dev_langs:
- C++
helpviewer_keywords:
- CMDITabInfo [MFC], Serialize
- CMDITabInfo [MFC], m_bAutoColor
- CMDITabInfo [MFC], m_bDocumentMenu
- CMDITabInfo [MFC], m_bEnableTabSwap
- CMDITabInfo [MFC], m_bFlatFrame
- CMDITabInfo [MFC], m_bTabCloseButton
- CMDITabInfo [MFC], m_bTabCustomTooltips
- CMDITabInfo [MFC], m_bTabIcons
- CMDITabInfo [MFC], m_nTabBorderSize
- CMDITabInfo [MFC], m_style
- CMDITabInfo [MFC], m_tabLocation
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7cd0355c4d0ce203617729142e03860e9960190a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726615"
---
# <a name="cmditabinfo-class"></a>Cmdıtabınfo sınıfı
`CMDITabInfo` Sınıfı için parametreleri geçirmek için kullanılan [CMDIFrameWndEx::EnableMDITabbedGroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) yöntemi. Sekmeli grupları MDI davranışını denetlemek için bu sınıfın üyelerini ayarlayın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMDITabInfo   
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMDITabInfo::CMDITabInfo`|Varsayılan Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMDITabInfo::Serialize](#serialize)|Okur veya ya da bir arşivden bu nesneyi yazar.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMDITabInfo::m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|Belirtir olup olmadığını bir **Kapat** düğmesi etkin sekmenin etiketi gösterilir.|  
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|MDI sekmeleri rengi belirtir.|  
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|Sekme grubu, açılmış belgelerin listesini gösteren veya kaydırma düğmelerine görüntüler bir açılan menü görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|Kullanıcının sekme sürükleyerek Değiştir olup olmadığını belirtir.|  
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|Sekmeleri düz bir çerçeve sahip olup olmadığını belirtir.|  
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|Her sekme etiketi görüntülenip görüntülenmeyeceğini belirten bir **Kapat** düğmesi.|  
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|Özel araç ipuçları etkin olup olmadığını belirtir.|  
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|MDI sekmeleri üzerinde simgeler görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|Her sekme penceresinde kenarlık boyutunu belirtir.|  
|[CMDITabInfo::m_style](#m_style)|Sekme etiketleri stilini belirtir.|  
|[CMDITabInfo::m_tabLocation](#m_tablocation)|Sekmeleri etiketleri üstünde veya sayfanın altında bulunan olup olmadığını belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, framework oluşturur MDI sekme grupları parametrelerini belirtir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli üye değişkenlerinde değerlerini ayarlamak gösterilmiştir `CMDITabInfo` sınıfı.  
  
 [!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Cmdıtabınfo](../../mfc/reference/cmditabinfo-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmdiclientareawnd.h  
  
##  <a name="m_bactivetabclosebutton_"></a>  CMDITabInfo::m_bActiveTabCloseButton;  
 Belirtir olup olmadığını bir **Kapat** düğmesi etkin sekmenin etiketi gösterilir.  
  
```  
BOOL m_bActiveTabCloseButton;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 TRUE ise active sekmenin etiketini görüntüler bir **Kapat** düğmesi. **Kapat** düğmesini sekme alanının sağ üst köşeden kaldırılacak. Aksi takdirde, etkin sekmede etiketi görüntülenmez bir **Kapat** düğmesi. **Kapat** düğmesini sekme alanının sağ üst köşesinde görünür.  
  
##  <a name="m_bautocolor"></a>  CMDITabInfo::m_bAutoColor  
 Her MDI sekme kendi rengi olup olmadığını belirtir.  
  
```  
BOOL m_bAutoColor;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 TRUE ise, her sekme, kendi rengine sahip olur. Renkler kümesi MFC Kitaplığı tarafından yönetilir. Aksi takdirde, sekmeler beyaz görüntülenir. Varsayılan değer FALSE olur.  
  
##  <a name="m_bdocumentmenu"></a>  CMDITabInfo::m_bDocumentMenu  
 Her sekme bir sekme alanının sağ kenarında açılmış belgelerin listesini gösteren bir açılan menü görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
BOOL m_bDocumentMenu;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 TRUE ise, her sekme windows sekme alanının sağ kenarında açılmış belgelerin listesini gösteren bir açılan menü görüntüler. Aksi takdirde, sekme penceresinde sekme alanının sağ kenardaki kaydırma düğmelerine görüntüler. Varsayılan değer FALSE olur.  
  
##  <a name="m_benabletabswap"></a>  CMDITabInfo::m_bEnableTabSwap  
 Kullanıcının sekme sürükleyerek Değiştir olup olmadığını belirtir.  
  
```  
BOOL m_bEnableTabSwap;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 TRUE ise kullanıcı sekmeler konumları sekmeleri sürükleyerek değiştirebilirsiniz. Aksi takdirde, kullanıcı sekmeler konumlar değiştiremezsiniz. Varsayılan değer True'dur.  
  
##  <a name="m_bflatframe"></a>  CMDITabInfo::m_bFlatFrame  
 Her sekme penceresinde düz bir çerçeve olup olmadığını belirtir.  
  
```  
BOOL m_bFlatFrame;  
```  
  
##  <a name="m_btabclosebutton"></a>  CMDITabInfo::m_bTabCloseButton  
 Her sekme penceresinde mı gösterileceğini belirten bir **Kapat** düğmesi.  
  
```  
BOOL m_bTabCloseButton;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 TRUE ise, her sekme penceresinde görüntüler **Kapat** sekmenin sağ kenarda düğmesi. Aksi takdirde, **Kapat** düğmesi görüntülenmez. Varsayılan değer True'dur.  
  
##  <a name="m_btabcustomtooltips"></a>  CMDITabInfo::m_bTabCustomTooltips  
 Sekmeleri araç ipuçlarını görüntüleme olup olmadığını belirtir.  
  
```  
BOOL m_bTabCustomTooltips;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 TRUE ise, uygulama ana kareye AFX_WM_ON_GET_TAB_TOOLTIP iletisi gönderir. On_regıstered_message makrosu kullanarak bu ileti işleyebilir.  
  
##  <a name="m_btabicons"></a>  CMDITabInfo::m_bTabIcons  
 MDI sekmeleri üzerinde simgeler görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
BOOL m_bTabIcons;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 TRUE ise simgeler her MDI sekmesinde görüntülenir. Aksi takdirde, sekmelerde simgeler görüntülenmez. Varsayılan değer FALSE olur.  
  
##  <a name="m_ntabbordersize"></a>  CMDITabInfo::m_nTabBorderSize  
 Kenarlık boyutu her sekmesi penceresi piksel cinsinden belirtir.  
  
```  
int m_nTabBorderSize;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 [CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) varsayılan değerini döndürür.  
  
##  <a name="m_style"></a>  CMDITabInfo::m_style  
 Sekme etiketleri stilini belirtir.  
  
```  
CMFCTabCtrl::Style m_style  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki stilleri için sekmesinde etiketleri birini belirtin:  
  
 STYLE_3D  
 3B stili.  
  
 STYLE_3D_ONENOTE  
 Microsoft OneNote stili.  
  
 STYLE_3D_VS2005  
 Microsoft Visual Studio 2005 stili.  
  
 STYLE_3D_SCROLLED  
 Dikdörtgen sekme etiketleri ile 3B stili.  
  
 STYLE_FLAT_SHARED_HORZ_SCROLL  
 Paylaşılan yatay kaydırma çubuklu düz stili.  
  
 STYLE_3D_ROUNDED_SCROLL  
 Yuvarlak sekme etiketleri ile 3B stili.  
  
##  <a name="m_tablocation"></a>  CMDITabInfo::m_tabLocation  
 Sekmeleri etiketleri üstünde veya sayfanın altında bulunan olup olmadığını belirtir.  
  
```  
CMFCTabCtrl::Location m_tabLocation;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki konum bayrakları sekmeleri biri için geçerlidir:  
  
-   LOCATION_BOTTOM: sekmeler etiketleri sayfanın alt kısmında bulunur.  
  
-   LOCATION_TOP: sekmeler etiketleri sayfanın en üstünde bulunur  
  
##  <a name="serialize"></a>  CMDITabInfo::Serialize  
 Okur ya da bu nesne bir arşiv ya da bir arşivden yazar.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
*ar*<br/>
[in] A [CArchive sınıfı](../../mfc/reference/carchive-class.md) nesneyi serileştirmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cmdıframewndex sınıfı](../../mfc/reference/cmdiframewndex-class.md)   
 [MDI sekmeli grupları](../../mfc/mdi-tabbed-groups.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
