---
title: CMFCColorPopupMenu sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPopupMenu [MFC], CMFCColorPopupMenu
- CMFCColorPopupMenu [MFC], CreateTearOffBar
- CMFCColorPopupMenu [MFC], GetMenuBar
- CMFCColorPopupMenu [MFC], SetPropList
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54999252af2ec55c67e1afc69c2788f96cfc640e
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037310"
---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu sınıfı
Kullanıcılar bir belge veya uygulama renkleri seçmek için kullanın bir açılır menü temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|Oluşturan bir `CMFCColorPopupMenu` nesnesi.|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|Bir dockable etiketleri renk çubuğu oluşturur. (Geçersiz kılmaları [CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|  
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|Döndürür [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) açılır menü katıştırılmış. (Geçersiz kılmaları [CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|  
|`CMFCColorPopupMenu::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCColorPopupMenu::SetPropList](#setproplist)|Özellik kılavuz denetim nesnesinin katıştırılmış ayarlar `CMFCColorBar` nesnesi.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`m_bEnabledInCustomizeMode`|Renk çubuğu gösterilip gösterilmeyeceğini belirler bir Boole değeri.|  
|`m_wndColorBar`|`CMFCColorBar` Renk seçimi sağlayan nesne.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf açılır menü işlevselliğini devralır `CMFCPopupMenu` sınıfı ve yöneten bir `CMFCColorBar` renk seçimi sağlayan nesne. Araç çubuğu framework özelleştirme modunda olduğunda ve `m_bEnabledInCustomizeMode` üye ayarlanmış `FALSE`, renk çubuğu nesne gösterilmez. Özelleştirme modu hakkında daha fazla bilgi için bkz: [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)  
  
 Hakkında daha fazla bilgi için `CMFCColorBar`, bkz: [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 [CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcolorpopupmenu.h  
  
##  <a name="cmfccolorpopupmenu"></a>  CMFCColorPopupMenu::CMFCColorPopupMenu  
 Oluşturan bir `CMFCColorPopupMenu` nesnesi.  
  
```  
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    int nHorzDockRows,  
    int nVertDockColumns,  
    COLORREF colorAutomatic,  
    UINT uiCommandID,  
    BOOL bStdColorDlg = FALSE);

 
CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic);

 
CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *renkleri*  
 Framework açılır menüsünde görüntüler renkleri dizisi.  
  
 [in] *rengi*  
 Seçili varsayılan rengi.  
  
 [in] *lpszAutoColor*  
 Metin etiketini *otomatik* (varsayılan) renk düğmesi veya `NULL`.  
  
 Otomatik düğmesi için standart etiket **otomatik**.  
  
 [in] *lpszOtherColor*  
 Metin etiketini *diğer* daha fazla rengi seçimleri görüntüleyen düğmesini veya `NULL`.  
  
 Diğer düğmesi için standart etiket **daha renkleri...** .  
  
 [in] *lpszDocColors*  
 Belge renkleri düğmesi metin etiketi. Belge renk paleti belge şu anda kullandığı tüm renkleri listeler.  
  
 [in] *lstDocColors*  
 Belge şu anda kullandığı renk listesi.  
  
 [in] *nColumns*  
 Renkleri dizisi sahip sütun sayısı.  
  
 [in] *nHorzDockRows*  
 Renk çubuğu yatay yerleştirildiğinde olan satırların sayısı.  
  
 [in] *nVertDockColumns*  
 Renk Çubuğu dikey yerleştirildiğinde olan sütun sayısı.  
  
 [in] *colorAutomatic*  
 Otomatik Düğmeye tıkladığınızda, framework uygulanan varsayılan rengi.  
  
 [in] *uiCommandID*  
 Renk çubuğu denetim komut kimliği.  
  
 [in] *bStdColorDlg*  
 Standart sistem renk iletişim kutusu gösterilip gösterilmeyeceğini belirten bir Boole değeri veya [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusu.  
  
 [in] *pParentBtn*  
 Bir üst düğmesini gösteren bir işaretçi.  
  
 [in] *nID*  
 Komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Her aşırı Oluşturucusu kümeleri `m_bEnabledInCustomizeMode` üyesine `FALSE`.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCColorPopupMenu` nesnesi.  
  
 [!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]  
  
##  <a name="createtearoffbar"></a>  CMFCColorPopupMenu::CreateTearOffBar  
 Bir dockable etiketleri renk çubuğu oluşturur.  
  
```  
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,  
    UINT uiID,  
    LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] *pWndMain*|Etiketleri çubuğunun üst pencere işaretçi.|  
|[in] *uiID*|Etiketleri çubuğu komut kimliği.|  
|[in] *lpszName*|Etiketleri çubuğu penceresi metni.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni etiketleri denetim çubuğu nesnesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturur bir [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md) nesne ve ona bıraktığı bir [CPane sınıfı](../../mfc/reference/cpane-class.md) işaretçi. Bu değer çevirebilirsiniz başa bir [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md) açıklanan atama makroları birini kullanarak işaretçi [MFC sınıf nesnelerine, tür atama](../../mfc/reference/type-casting-of-mfc-class-objects.md).  
  
##  <a name="getmenubar"></a>  CMFCColorPopupMenu::GetMenuBar  
 Döndürür [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) açılır menü katıştırılmış.  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Katıştırılmış bir işaretçi `CMFCPopupMenuBar`.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk açılır menüsünü katıştırılmış sahip [CMFCPopupMenuBar sınıfı](../../mfc/reference/cmfcpopupmenubar-class.md) nesnesi. Uygulamanız farklı bir katıştırılmış tür kullanıyorsa bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="setproplist"></a>  CMFCColorPopupMenu::SetPropList  
 Özellik kılavuz denetim nesnesinin katıştırılmış ayarlar `CMFCColorBar` nesnesi.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndList*  
 Bir özellik kılavuz denetim nesnesine işaretçi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
