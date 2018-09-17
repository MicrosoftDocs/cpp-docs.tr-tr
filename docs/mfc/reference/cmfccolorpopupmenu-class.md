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
ms.openlocfilehash: 32dd81b005570761088cdeb874ad0524bc543df2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721870"
---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu sınıfı
Kullanıcıların bir belge veya uygulamadaki renkleri seçmek için açılır menü temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|Oluşturur bir `CMFCColorPopupMenu` nesne.|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|Bir yerleştirilebilir etkinleştiriliyorken renk çubuğu oluşturur. (Geçersiz kılmaları [CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|  
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|Döndürür [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) içinde açılır menüde gömülü. (Geçersiz kılmaları [CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|  
|`CMFCColorPopupMenu::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|  
|[CMFCColorPopupMenu::SetPropList](#setproplist)|Özellik Kılavuzu denetimini nesnesi Embedded ayarlar `CMFCColorBar` nesne.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`m_bEnabledInCustomizeMode`|Renk çubuğu gösterilip gösterilmeyeceğini belirleyen bir Boole değeri.|  
|`m_wndColorBar`|`CMFCColorBar` Renk seçimi sağlayan nesne.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf açılır menü işlevselliğini devralır `CMFCPopupMenu` sınıfı ve yöneten bir `CMFCColorBar` renk seçimi sağlayan nesne. Araç çubuğu framework özelleştirme modunda olduğunda ve `m_bEnabledInCustomizeMode` üye yanlış olarak ayarlandığında, renk çubuğu nesne gösterilmez. Özelleştirme modu hakkında daha fazla bilgi için bkz: [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)  
  
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
 Oluşturur bir `CMFCColorPopupMenu` nesne.  
  
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
*Renkleri*<br/>
[in] Açılır menüde framework görüntüler renkleri dizisi.  
  
*Renk*<br/>
[in] Varsayılan renk seçili.  
  
*lpszAutoColor*<br/>
[in] Metin etiketini *otomatik* rengi düğmesi (varsayılan) ya da NULL.  
  
 Standart etiket otomatik düğmenin **otomatik**.  
  
*lpszOtherColor*<br/>
[in] Metin etiketini *diğer* görüntüleyen daha rengi seçimleri veya NULL düğmesi.  
  
 Diğer düğme için standart etiket **daha fazla renk...** .  
  
*lpszDocColors*<br/>
[in] Belge renkleri düğmesinin metin etiketi. Belge renkler paleti belge şu anda kullandığı tüm renkleri listeler.  
  
*lstDocColors*<br/>
[in] Belge şu anda kullandığı renkler listesi.  
  
*nColumns*<br/>
[in] Renkleri dizi sahip sütun sayısı.  
  
*nHorzDockRows*<br/>
[in] Renk çubuğu yatay yerleştirildiğinde olan satır sayısı.  
  
*nVertDockColumns*<br/>
[in] Renk Çubuğu dikey yerleştirildiğinde olan sütun sayısı.  
  
*colorAutomatic*<br/>
[in] Otomatik düğmeyi tıklattığınızda, framework uygulanan varsayılan rengi.  
  
*uiCommandID*<br/>
[in] Renk çubuğu denetim komut kimliği.  
  
*bStdColorDlg*<br/>
[in] Standart sistem renk iletişim kutusu gösterilip gösterilmeyeceğini belirten bir Boole değeri veya [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusu.  
  
*pParentBtn*<br/>
[in] Bir üst düğme için bir işaretçi.  
  
*nID*<br/>
[in] Komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Her aşırı Oluşturucusu kümeleri `m_bEnabledInCustomizeMode` üye false.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCColorPopupMenu` nesne.  
  
 [!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]  
  
##  <a name="createtearoffbar"></a>  CMFCColorPopupMenu::CreateTearOffBar  
 Bir yerleştirilebilir etkinleştiriliyorken renk çubuğu oluşturur.  
  
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
|*pWndMain*|[in] Bölünmüş çubuğunun üst penceresine yönelik işaretçi.|  
|*uiID*|[in] Bölünmüş çubuk komut kimliği.|  
|*lpszName*|[in] Bölünmüş çubuk pencere metni.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni etiket denetim çubuğu nesnesine bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, oluşturur bir [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md) nesne ve kendisine bıraktığı bir [CPane sınıfı](../../mfc/reference/cpane-class.md) işaretçi. Bu değer çevirebilirsiniz geri bir [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md) açıklanan atama makroları birini kullanarak işaretçi [MFC sınıf nesnelerine, tür atama](../../mfc/reference/type-casting-of-mfc-class-objects.md).  
  
##  <a name="getmenubar"></a>  CMFCColorPopupMenu::GetMenuBar  
 Döndürür [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) içinde açılır menüde gömülü.  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Katıştırılmış bir işaretçiye `CMFCPopupMenuBar`.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk açılır menüsünü katıştırılmış sahip [CMFCPopupMenuBar sınıfı](../../mfc/reference/cmfcpopupmenubar-class.md) nesne. Uygulamanızın kullandığı farklı bir ekli türü türetilen bir sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="setproplist"></a>  CMFCColorPopupMenu::SetPropList  
 Özellik Kılavuzu denetimini nesnesi Embedded ayarlar `CMFCColorBar` nesne.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Parametreler  
*pWndList*<br/>
[in] Bir özellik Kılavuzu denetimini nesnesi işaretçisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
