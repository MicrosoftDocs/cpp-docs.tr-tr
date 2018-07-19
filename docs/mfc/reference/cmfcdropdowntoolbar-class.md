---
title: CMFCDropDownToolBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::AllowShowOnPaneMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadBitmap
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnLButtonUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnMouseMove
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnSendCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnUpdateCmdUI
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownToolBar [MFC], AllowShowOnPaneMenu
- CMFCDropDownToolBar [MFC], LoadBitmap
- CMFCDropDownToolBar [MFC], LoadToolBar
- CMFCDropDownToolBar [MFC], OnLButtonUp
- CMFCDropDownToolBar [MFC], OnMouseMove
- CMFCDropDownToolBar [MFC], OnSendCommand
- CMFCDropDownToolBar [MFC], OnUpdateCmdUI
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e12799f10fe86ef5dd556eac4e344aa972e2503
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027316"
---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolBar sınıfı
Kullanıcı bir üst düzey araç çubuğu düğmesini basılı tuttuğunda görünen bir araç çubuğu.  
  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCDropDownToolBar : public CMFCToolBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Geçersiz kılmaları `CPane::AllowShowOnPaneMenu`.)|  
|[CMFCDropDownToolBar::LoadBitmap](#loadbitmap)|(Geçersiz kılmaları [CMFCToolBar::LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap).)|  
|[CMFCDropDownToolBar::LoadToolBar](#loadtoolbar)|(Geçersiz kılmaları [CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar).)|  
|[CMFCDropDownToolBar::OnLButtonUp](#onlbuttonup)||  
|[CMFCDropDownToolBar::OnMouseMove](#onmousemove)||  
|[CMFCDropDownToolBar::OnSendCommand](#onsendcommand)|(Geçersiz kılmaları `CMFCToolBar::OnSendCommand`.)|  
|[CMFCDropDownToolBar::OnUpdateCmdUI](#onupdatecmdui)|(Geçersiz kılmaları [CMFCToolBar::OnUpdateCmdUI](http://msdn.microsoft.com/571a38ab-2a56-4968-9796-273516126f80).)|  
  
### <a name="remarks"></a>Açıklamalar  
 A `CMFCDropDownToolBar` nesne ile bir açılan menü davranışını bir araç çubuğu görsel görünümünü birleştirir. Ne zaman bir kullanıcının bastığında ve bir açılır araç çubuğu düğmesini (bkz [CMFCDropDownToolbarButton sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)), aşağı açılan araç çubuğu görünür ve kullanıcı bir düğme açılan araç çubuğundan için kaydırma ve fare düğmesini bırakmadan seçebilirsiniz düğmesi. Kullanıcının açılan araç çubuğunda bir düğmeyi seçtiğinde sonra bu düğme olarak geçerli bir üst düzey araç çubuğunda görüntülenir.  
  
 Bir açılır araç çubuğunu özelleştirilmiş veya yerleştirilmiş olamaz ve etkinleştiriliyorken durumu yok.  
  
 Aşağıdaki çizimde gösterildiği bir `CMFCDropDownToolBar` nesnesi:  
  
 ![CMFCDropDownToolbar örneği](../../mfc/reference/media/cmfcdropdown.png "cmfcdropdown")  
  
 Oluşturduğunuz bir `CMFCDropDownToolBar` sıradan bir araç çubuğu oluşturma aynı şekilde nesnesi (bkz [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)).  
  
 Üst araç çubuğuna açılan araç çubuğu eklemek için:  
  
 1. Üst araç çubuğunda kaynağında düğme için bir işlevsiz kaynak kimliği saklı tutarız.  
  
 2. Oluşturma bir `CMFCDropDownToolBarButton` açılan araç çubuğu içeren nesne (daha fazla bilgi için [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)).  
  
 3. İşlevsiz bir düğmeyle değiştirin `CMFCDropDownToolBarButton` kullanarak nesne [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Araç çubuğu düğmeleri hakkında daha fazla bilgi için bkz: [izlenecek yol: temel denetimler koyma araç'çubukları](../../mfc/walkthrough-putting-controls-on-toolbars.md). Örnek Proje VisualStudioDemo bir açılır araç çubuğunu örneği için bkz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `Create` yönteminde `CMFCDropDownToolBar` sınıfı. Bu kod parçacığı parçasıdır [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdropdowntoolbar.h  
  
##  <a name="allowshowonpanemenu"></a>  CMFCDropDownToolBar::AllowShowOnPaneMenu  

  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="loadbitmap"></a>  CMFCDropDownToolBar::LoadBitmap  
 Araç çubuğu görüntülerini uygulama kaynaklarından yükler.  
  
```  
virtual BOOL LoadBitmap(
    UINT uiResID,  
    UINT uiColdResID=0,  
    UINT uiMenuResID=0,  
    BOOL bLocked=FALSE,  
    UINT uiDisabledResID=0,  
    UINT uiMenuDisabledResID=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiResID*  
 Etkin araç çubuğu görüntülerini başvuran bir bit eşlem kaynak kimliği.  
  
 [in] *uiColdResID*  
 Soğuk araç görüntülere başvuruyor bit eşlemi kaynak kimliği.  
  
 [in] *uiMenuResID*  
 Normal menü görüntülere başvuruyor bit eşlemi kaynak kimliği.  
  
 [in] *engellendi*  
 Araç kilitlemek için TRUE; Aksi durumda FALSE.  
  
 [in] *uiDisabledResID*  
 Devre dışı araç görüntülere başvuruyor bit eşlemi kaynak kimliği.  
  
 [in] *uiMenuDisabledResID*  
 Devre dışı bırakılmış menü görüntülere başvuruyor bit eşlemi kaynak kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) yöntemi araç ile ilişkili görüntü yüklemek için bu yöntemi çağırır. Özel resim kaynakları yüklemesini gerçekleştirmek için bu yöntemi yok sayın.  
  
 Çağrı `LoadBitmapEx` araç oluşturduktan sonra ek resimleri yüklemek için yöntemi.  
  
##  <a name="loadtoolbar"></a>  CMFCDropDownToolBar::LoadToolBar  

  
```  
virtual BOOL LoadToolBar(
    UINT uiResID,  
    UINT uiColdResID = 0,  
    UINT uiMenuResID = 0,
    BOOL = FALSE,  
    UINT uiDisabledResID = 0,  
    UINT uiMenuDisabledResID = 0,  
    UINT uiHotResID = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiResID*  
 [in] *uiColdResID*  
 [in] *uiMenuResID*  
 [in] *BOOL*  
 [in] *uiDisabledResID*  
 [in] *uiMenuDisabledResID*  
 [in] *uiHotResID*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onlbuttonup"></a>  CMFCDropDownToolBar::OnLButtonUp  

  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nFlags*  
 [in] *noktası*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onmousemove"></a>  CMFCDropDownToolBar::OnMouseMove  

  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nFlags*  
 [in] *noktası*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsendcommand"></a>  CMFCDropDownToolBar::OnSendCommand  

  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pButton*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onupdatecmdui"></a>  CMFCDropDownToolBar::OnUpdateCmdUI  

  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pTarget*  
 [in] *bDisableIfNoHndler*  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::Create](../../mfc/reference/cmfctoolbar-class.md#create)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [CMFCDropDownToolbarButton sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)   
 [İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)



