---
title: CPaneDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
dev_langs:
- C++
helpviewer_keywords:
- CPaneDialog [MFC], Create
- CPaneDialog [MFC], HandleInitDialog
- CPaneDialog [MFC], SetOccDialogInfo
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36f620f0a29e7d1715e7cb5bfb83c0685f97f643
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374946"
---
# <a name="cpanedialog-class"></a>CPaneDialog sınıfı
`CPaneDialog` Sınıfı, bir dockable kalıcı olmayan iletişim kutusu destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CPaneDialog::CPaneDialog`|Varsayılan Oluşturucu.|  
|`CPaneDialog::~CPaneDialog`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaneDialog::Create](#create)|Bir dockable iletişim kutusu oluşturur ve ona ekler bir `CPaneDialog` nesnesi.|  
|`CPaneDialog::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|`CPaneDialog::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|İşleme [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) ileti. (Yeniden tanımlamaktadır `CBasePane::HandleInitDialog`.)|  
|`CPaneDialog::OnEraseBkgnd`|İşleme [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) ileti. (Yeniden tanımlamaktadır [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|  
|`CPaneDialog::OnLButtonDblClk`|İşleme [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) ileti. (Yeniden tanımlamaktadır [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|  
|`CPaneDialog::OnLButtonDown`|İşleme [WM_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607) ileti. (Yeniden tanımlamaktadır [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|  
|`CPaneDialog::OnUpdateCmdUI`|İletişim kutusu Windows Update'i çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/5dd61606-1c12-40d4-b024-f3839aa5e2e0).)|  
|`CPaneDialog::OnWindowPosChanging`|İşleme [WM_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653) ileti. (Yeniden tanımlamaktadır [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|  
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|OLE denetim kapsayıcı bir iletişim kutusu için kullanılacak şablonu belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CPaneDialog` iki adımda nesne. İlk olarak, kodunuzda nesnesi oluşturun. İkinci olarak, arama [CPaneDialog::Create](#create). Geçerli kaynak şablonu adı ya da şablon kimliği belirtin ve bir işaretçi üst penceresine geçmesi gerekir. Aksi takdirde oluşturma işlemi başarısız olur. İletişim kutusu WS_CHILD ve ws_vısıble stili belirtmeniz gerekir. Ws_clıpchıldren ve ws_clıpsıblıngs stilleri de belirtmeniz önerilir. Daha fazla bilgi için bkz: [pencere stilleri](styles-used-by-mfc.md#window-styles).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CPaneDialog](../../mfc/reference/cpanedialog-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpanedialog.h  
  
##  <a name="create"></a>  CPaneDialog::Create  
 Yerleşik bir iletişim kutusu oluşturur ve ona ekler bir `CPaneDialog` nesnesi.  
  
```  
BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    BOOL bHasGripper,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID,  
    DWORD dwTabbedStyle= AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle=AFX_DEFAULT_DOCKING_PANE_STYLE);

 
BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    BOOL bHasGripper,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);

 
BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszWindowName`  
 Yerleştirme iletişim kutusu adı.  
  
 [in] `pParentWnd`  
 Üst pencere noktalarına.  
  
 [in] `bHasGripper`  
 `TRUE` bir resim yazısı (kavrayıcının); yerleştirme iletişim kutusu oluşturmak için Aksi takdirde `FALSE`.  
  
 [in] `lpszTemplateName`  
 Kaynak iletişim şablonunun adı.  
  
 [in] `nStyle`  
 Windows stili.  
  
 [in] `nID`  
 Denetim kimliği.  
  
 [in] `nIDTemplate`  
 İletişim şablonu kaynak kimliği.  
  
 [in] `dwTabbedStyle`  
 Kullanıcı başka bir denetim bölmesinde bu denetim bölmesinde resim yazısı sürüklendiğinde sonuçları sekmeli pencere stili. Varsayılan değer `AFX_CBRS_REGULAR_TABS` şeklindedir. Daha fazla bilgi için Açıklamalar bölümüne bakın [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) yöntemi.  
  
 [in] `dwControlBarStyle`  
 Ek stil öznitelikleri. Varsayılan değer `AFX_DEFAULT_DOCKING_PANE_STYLE` şeklindedir. Daha fazla bilgi için Açıklamalar bölümüne bakın [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Bu yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `Create` yönteminde `CPaneDialog` sınıfı. Bu örneğin parçasıdır [bölmesinin boyutunu Ayarla örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]  
  
##  <a name="handleinitdialog"></a>  CPaneDialog::HandleInitDialog  
 İşleme [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) ileti.  
  
```  
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `wParam`  
 Varsayılan klavye odağını alacak denetimi işleyin.  
  
 [in] `lParam`  
 Ek başlatma verilerini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Bu yöntem başarılı olursa; Aksi takdirde `FALSE`. Ayrıca, `TRUE` tarafından belirtilen denetime klavye odağını ayarlar `wParam` parametresi; `FALSE` varsayılan klavye odağını ayarlamak engeller.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve denetimleri ve bir iletişim kutusu görünümünü başlatmak için bu yöntemi kullanır. Framework'te iletişim kutusu görüntülenmeden önce bu yöntemi çağırır.  
  
##  <a name="setoccdialoginfo"></a>  CPaneDialog::SetOccDialogInfo  
 OLE denetim kapsayıcı bir iletişim kutusu için kullanılacak şablonu belirtir.  
  
```  
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pOccDialogInfo`  
 İletişim kutusu nesnesi oluşturmak için kullanılan bir iletişim kutusu şablon işaretçi. Bu parametrenin değerini daha sonra içine geçirilen [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem destekler [COccManager](../../mfc/reference/coccmanager-class.md) OLE denetim siteleri ve ActiveX denetimlerini yöneten sınıf. _AFX_OCC_DIALOG_INFO yapısı afxocc.h üstbilgi dosyasında tanımlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md)   
 [Pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles)



