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
ms.openlocfilehash: b0edc3a255d3778711b2b8e74bde448dc34c814c
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849102"
---
# <a name="cpanedialog-class"></a>CPaneDialog sınıfı
`CPaneDialog` Sınıfı, engelleyici olmayan, yerleştirilebilir bir iletişim kutusunu destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CPaneDialog::CPaneDialog`|Varsayılan Oluşturucu.|  
|`CPaneDialog::~CPaneDialog`|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaneDialog::Create](#create)|Yerleştirilebilir bir iletişim kutusu oluşturur ve ona bağlanan bir `CPaneDialog` nesne.|  
|`CPaneDialog::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|  
|`CPaneDialog::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|  
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|İşleme [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) ileti. ('ı yeniden tanımladığı `CBasePane::HandleInitDialog`.)|  
|`CPaneDialog::OnEraseBkgnd`|İşleme [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) ileti. ('ı yeniden tanımladığı [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|  
|`CPaneDialog::OnLButtonDblClk`|İşleme [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) ileti. ('ı yeniden tanımladığı [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|  
|`CPaneDialog::OnLButtonDown`|İşleme [WM_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607) ileti. ('ı yeniden tanımladığı [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|  
|`CPaneDialog::OnUpdateCmdUI`|İletişim kutusu penceresini güncelleştirmek için framework tarafından çağırılır. (Geçersiz kılmaları [CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/5dd61606-1c12-40d4-b024-f3839aa5e2e0).)|  
|`CPaneDialog::OnWindowPosChanging`|İşleme [WM_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653) ileti. ('ı yeniden tanımladığı [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|  
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|OLE denetim kapsayıcısı olan bir iletişim kutusu için şablonu belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CPaneDialog` iki adımda nesne. İlk olarak, kodunuzda nesnesi oluşturun. İkinci olarak, çağrı [CPaneDialog::Create](#create). Üst penceresine bir işaretçi geçirin ve geçerli kaynak şablonu adı veya şablon kimliği belirtmelisiniz. Aksi takdirde oluşturma işlemi başarısız olur. İletişim kutusu WS_CHILD ve ws_vısıble stili belirtmeniz gerekir. Ws_clıpchıldren ve ws_clıpsıblıngs stilleri de belirtmenizi öneririz. Daha fazla bilgi için [pencere stilleri](styles-used-by-mfc.md#window-styles).  
  
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
 Yerleştirme bir iletişim kutusu oluşturur ve ona bağlanan bir `CPaneDialog` nesne.  
  
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
 [in] *lpszWindowName*  
 Yerleştirme iletişim kutusunun adı.  
  
 [in] *pParentWnd*  
 Üst pencere işaret eder.  
  
 [in] *bHasGripper*  
 Bir resim yazısı (kavrayıcı); yerleştirme iletişim kutusu oluşturmak için TRUE Aksi takdirde FALSE.  
  
 [in] *lpszTemplateName*  
 Kaynak iletişim şablonunun adı.  
  
 [in] *nStyle*  
 Windows stili.  
  
 [in] *nID*  
 Denetim kimliği.  
  
 [in] *nIDTemplate*  
 İletişim şablonu kaynak kimliği.  
  
 [in] *dwTabbedStyle*  
 Kullanıcı bu denetimi bölme açıklamalı alt yazı başka bir Denetim Masası sürüklediğinde sonuçları sekmeli pencere stili. AFX_CBRS_REGULAR_TABS varsayılan değerdir. Daha fazla bilgi için Açıklamalar bölümüne bakın. [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) yöntemi.  
  
 [in] *dwControlBarStyle*  
 Ek stil öznitelikleri. AFX_DEFAULT_DOCKING_PANE_STYLE varsayılan değerdir. Daha fazla bilgi için Açıklamalar bölümüne bakın. [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `Create` yönteminde `CPaneDialog` sınıfı. Bu örneğin parçasıdır [bölme boyutunu ayarlayın örnek](../../visual-cpp-samples.md).  
  
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
 [in] *wParam*  
 Varsayılan klavye odağının alınacağı denetimi için işler.  
  
 [in] *lParam*  
 Ek başlatma verilerini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE. Ayrıca, doğru klavye odağı tarafından belirtilen denetim ayarlar *wParam* parametre; Varsayılan klavye odağı ayarını FALSE engeller.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve, denetimleri ve bir iletişim kutusu görünümünü başlatmak için bu yöntemi kullanır. İletişim kutusu görüntülenmeden önce framework bu yöntemi çağırır.  
  
##  <a name="setoccdialoginfo"></a>  CPaneDialog::SetOccDialogInfo  
 OLE denetim kapsayıcısı olan bir iletişim kutusu için şablonu belirtir.  
  
```  
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pOccDialogInfo*  
 İletişim kutusu nesnesi oluşturmak için kullanılan bir iletişim kutusunda şablon için işaretçi. Bu parametrenin değerini daha sonra içine geçirilen [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem destekler [COccManager](../../mfc/reference/coccmanager-class.md) OLE denetim siteleri ve ActiveX denetimleri yöneten sınıfı. _AFX_OCC_DIALOG_INFO yapısı afxocc.h üstbilgi dosyasında tanımlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md)   
 [Pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles)



