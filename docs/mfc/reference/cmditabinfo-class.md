---
title: "CMDITabInfo sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "37"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4254f2b5c4b3c2000e0e466dd29d0ad9492acf6b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmditabinfo-class"></a>CMDITabInfo sınıfı
`CMDITabInfo` Sınıfı parametrelerini iletmek için kullanılan [CMDIFrameWndEx::EnableMDITabbedGroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) yöntemi. MDI davranışını denetlemek için küme üyeleri bu sınıf sekmeli grupları.  
  
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
|[CMDITabInfo::Serialize](#serialize)|Okur veya bir arşiv değiştirilmesine veya bu nesneyi yazar.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMDITabInfo::m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|Belirtir olup bir **Kapat** düğmesi etkin sekme etiketi görüntülenir.|  
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|MDI sekme rengi belirtir.|  
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|Sekme grubu açılan belgelerin bir listesi gösterilir veya kaydırma düğmelerini görüntüler bir menü görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|Sürükleyerek kullanıcı sekmeler konumlarını değiştirebilirsiniz olup olmadığını belirtir.|  
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|Sekmeleri düz bir çerçeve sahip olup olmadığını belirtir.|  
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|Her sekme etiketi mı gösterileceğini belirten bir **Kapat** düğmesi.|  
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|Özel araç ipuçları etkinleştirilip etkinleştirilmeyeceğini belirtir.|  
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|MDI sekmelerinde simgeler görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|Her sekme penceresinde kenarlık boyutunu belirtir.|  
|[CMDITabInfo::m_style](#m_style)|Sekme etiketleri stilini belirtir.|  
|[CMDITabInfo::m_tabLocation](#m_tablocation)|Sekmeleri etiketleri üstüne veya altına sayfasının bulunduğu olup olmadığını belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf çerçevesini oluşturur MDI sekme grupları parametreleri belirtir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli üye değişkenlerin değerleri ayarlamak gösterilmiştir `CMDITabInfo` sınıfı.  
  
 [!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmdiclientareawnd.h  
  
##  <a name="m_bactivetabclosebutton_"></a>CMDITabInfo::m_bActiveTabCloseButton;  
 Belirtir olup bir **Kapat** düğmesi etkin sekme etiketi görüntülenir.  
  
```  
BOOL m_bActiveTabCloseButton;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `TRUE`, etkin sekme etiketini görüntüler bir **Kapat** düğmesi. **Kapat** düğmesini sekme alanı sağ üst köşesinden kaldırılır. Aksi durumda, etkin sekme etiketini görüntülenmez bir **Kapat** düğmesi. **Kapat** düğmesini sekme alanı sağ üst köşesinde görüntülenir.  
  
##  <a name="m_bautocolor"></a>CMDITabInfo::m_bAutoColor  
 Her MDI sekme kendi renk olup olmadığını belirtir.  
  
```  
BOOL m_bAutoColor;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `TRUE`, her sekme kendi renk sahip olur. Renk kümesi MFC Kitaplığı tarafından yönetilir. Aksi takdirde, sekmeler beyaz görüntülenir. Varsayılan değer `FALSE` şeklindedir.  
  
##  <a name="m_bdocumentmenu"></a>CMDITabInfo::m_bDocumentMenu  
 Her sekme sekme alanı sağ ucundaki açılan belgelerin listesini gösteren bir menü görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
BOOL m_bDocumentMenu;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `TRUE`, her sekme windows sekme alanı; sağ ucundaki açılan belgelerin listesini gösteren bir menü görüntüler Aksi takdirde sekmesi penceresi kaydırma düğmeleri sekme alanı sağ sınırında görüntüler. Varsayılan değer `FALSE` şeklindedir.  
  
##  <a name="m_benabletabswap"></a>CMDITabInfo::m_bEnableTabSwap  
 Sürükleyerek kullanıcı sekmeler konumlarını değiştirebilirsiniz olup olmadığını belirtir.  
  
```  
BOOL m_bEnableTabSwap;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `TRUE`, kullanıcı sekmeler sürükleyerek sekmeleri konumlarını değiştirebilirsiniz. Aksi takdirde kullanıcı sekmeler konumlar değiştiremezsiniz. Varsayılan değer `TRUE` şeklindedir.  
  
##  <a name="m_bflatframe"></a>CMDITabInfo::m_bFlatFrame  
 Her sekme penceresinde düz bir çerçeve sahip olup olmadığını belirtir.  
  
```  
BOOL m_bFlatFrame;  
```  
  
##  <a name="m_btabclosebutton"></a>CMDITabInfo::m_bTabCloseButton  
 Her sekme penceresinde mı gösterileceğini belirten bir **Kapat** düğmesi.  
  
```  
BOOL m_bTabCloseButton;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `TRUE`, her sekme penceresinde görüntüler **Kapat** sekmesini sağ köşesine düğmesinde. Aksi takdirde, **Kapat** düğmesi görüntülenmez. Varsayılan değer `TRUE` şeklindedir.  
  
##  <a name="m_btabcustomtooltips"></a>CMDITabInfo::m_bTabCustomTooltips  
 Sekmeleri araç ipuçlarının görüntüleyin olup olmadığını belirtir.  
  
```  
BOOL m_bTabCustomTooltips;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `TRUE`, uygulamanın gönderdiği bir `AFX_WM_ON_GET_TAB_TOOLTIP` ana çerçeve ileti. Bu iletiyi kullanarak işleyebilir `ON_REGISTERED_MESSAGE` makrosu.  
  
##  <a name="m_btabicons"></a>CMDITabInfo::m_bTabIcons  
 MDI sekmelerinde simgeler görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
BOOL m_bTabIcons;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `TRUE`, simgeler her MDI sekmesinde görüntülenir. Aksi takdirde, simgeler sekmelerinde görüntülenmez. Varsayılan değer `FALSE` şeklindedir.  
  
##  <a name="m_ntabbordersize"></a>CMDITabInfo::m_nTabBorderSize  
 Kenarlık boyutu her sekmesi penceresi piksel cinsinden belirtir.  
  
```  
int m_nTabBorderSize;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 [CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) varsayılan değerini döndürür.  
  
##  <a name="m_style"></a>CMDITabInfo::m_style  
 Sekme etiketleri stilini belirtir.  
  
```  
CMFCTabCtrl::Style m_style  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sekme etiketleri için aşağıdaki stiller birini belirtin:  
  
 `STYLE_3D`  
 3B stili.  
  
 `STYLE_3D_ONENOTE`  
 Microsoft OneNote stili.  
  
 `STYLE_3D_VS2005`  
 Microsoft Visual Studio 2005 stili.  
  
 `STYLE_3D_SCROLLED`  
 Dikdörtgen sekmesini etiketlerle 3B stili.  
  
 `STYLE_FLAT_SHARED_HORZ_SCROLL`  
 Paylaşılan yatay kaydırma çubuğu düz stili.  
  
 `STYLE_3D_ROUNDED_SCROLL`  
 Yuvarlak sekmesini etiketlerle 3B stili.  
  
##  <a name="m_tablocation"></a>CMDITabInfo::m_tabLocation  
 Sekmeleri etiketleri üstüne veya altına sayfasının bulunduğu olup olmadığını belirtir.  
  
```  
CMFCTabCtrl::Location m_tabLocation;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki konum bayrakları sekmeleri biri için geçerlidir:  
  
-   LOCATION_BOTTOM: sekmeleri etiketleri sayfasının en altında yer alır.  
  
-   LOCATION_TOP: sekmeleri etiketleri sayfanın en üstünde bulunan  
  
##  <a name="serialize"></a>CMDITabInfo::Serialize  
 Okur veya bu nesne bir arşiv veya bir arşiv yazar.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`ar`  
 A [CArchive sınıfı](../../mfc/reference/carchive-class.md) nesne seri hale getirilemedi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CMDIFrameWndEx sınıfı](../../mfc/reference/cmdiframewndex-class.md)   
 [MDI sekmeli grupları](../../mfc/mdi-tabbed-groups.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)
