---
title: CMFCRibbonMiniToolBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07b20d43c53fc0f485d33f71805e73f885c1200a
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041756"
---
# <a name="cmfcribbonminitoolbar-class"></a>CMFCRibbonMiniToolBar sınıfı
Bağlamsal açılan araç uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Varsayılan Oluşturucu.|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|`CMFCRibbonMiniToolBar::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|(Geçersiz kılmaları `CMFCPopupMenu::IsRibbonMiniToolBar`.)|  
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|Araç çubuğunda görüntülenecek komutların listesini ayarlar.|  
|[CMFCRibbonMiniToolBar::Show](#show)|Mini araç belirtilen ekran koordinatlarda görüntüler.|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|Mini araç bir bağlam menüsü ile birlikte görüntüler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir belgedeki nesneyi seçtikten sonra mini araç genellikle görüntülenir. Örneğin, kullanıcı bir sözcük program işleme metin bloğunu seçtikten sonra uygulama metin biçimlendirme komutları içeren mini araç çubuğu görüntüler.  
  
 Fare işaretçisini mini araç sınırların dışında olduğunda mini araç saydam olur.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 `CMFCRibbonPanelMenu`  
  
 [CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxRibbonMiniToolBar.h  
  
##  <a name="setcommands"></a>  CMFCRibbonMiniToolBar::SetCommands  
 Araç çubuğunda görüntülenecek komutların listesini ayarlar.  
  
```  
void SetCommands(
    CMFCRibbonBar* pRibbonBar,  
    const CList<UINT,UINT>& lstCommands);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pRibbonBar*  
 Mini araç çubuğu düğmeleri görüntülemek arar Şerit çubuk.  
  
 [in] *lstCommands*  
 Mini araç çubuğunda görüntülenecek komutları listesi. Tüm Şerit kategorileri ilişkili düğmeleri bulmak için arama yapılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Mini araç çubuğunda görüntülenecek komutların listesini ayarlamak için bu işlevi kullanın.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `SetCommands` yöntemi `CMFCRibbonMiniToolBar` sınıfı. Bu kod parçacığını parçası olan [MS Office 2007 Demo örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]  
  
##  <a name="show"></a>  CMFCRibbonMiniToolBar::Show  
 Mini araç belirtilen ekran koordinatlarda görüntüler.  
  
```  
BOOL Show(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *x*  
 Ekran koordinatları olarak mini araç yatay konumunu belirtir.  
  
 [in] *y*  
 Ekran koordinatları olarak mini araç dikey konumu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` mini araç başarıyla görüntülendiyse; Aksi takdirde `FALSE`.  
  
##  <a name="showwithcontextmenu"></a>  CMFCRibbonMiniToolBar::ShowWithContextMenu  
 Mini araç bir bağlam menüsü ile birlikte görüntüler.  
  
```  
BOOL ShowWithContextMenu(
    int x,  
    int y,  
    UINT uiMenuResID,  
    CWnd* pWndOwner);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *x*  
 Yatay Konum bağlam menüsünün ekran koordinatları olarak belirtir.  
  
 [in] *y*  
 Ekran koordinatları olarak bağlam menüsü dikey konumu belirtir.  
  
 [in] *uiMenuResID*  
 Görüntülenecek bağlam menüsü kaynak Kimliğini belirtir.  
  
 [in] *pWndOwner*  
 Bağlam menüsünden iletileri alan penceresi tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bağlam menüsü başarıyla görüntülendiyse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bağlam menüsü sahip mini bir araç çubuğu görüntülemek için bu işlevi kullanın. Bağlam menüsü konumlandırılmış 15 mini araç çubuğunun altında pikseldir.  
  
##  <a name="iscontextmenumode"></a>  CMFCRibbonMiniToolBar::IsContextMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsContextMenuMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isribbonminitoolbar"></a>  CMFCRibbonMiniToolBar::IsRibbonMiniToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsRibbonMiniToolBar() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
