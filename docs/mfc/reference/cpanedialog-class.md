---
title: CPaneDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
helpviewer_keywords:
- CPaneDialog [MFC], Create
- CPaneDialog [MFC], HandleInitDialog
- CPaneDialog [MFC], SetOccDialogInfo
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
ms.openlocfilehash: c78b8f2cd19e87fa559c3f9bbd24d07543d887c5
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769751"
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
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|İşleme [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) ileti. ('ı yeniden tanımladığı `CBasePane::HandleInitDialog`.)|
|`CPaneDialog::OnEraseBkgnd`|İşleme [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd) ileti. ('ı yeniden tanımladığı [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|
|`CPaneDialog::OnLButtonDblClk`|İşleme [WM_LBUTTONDBLCLK](/windows/desktop/inputdev/wm-lbuttondblclk) ileti. ('ı yeniden tanımladığı [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|
|`CPaneDialog::OnLButtonDown`|İşleme [WM_LBUTTONDOWN](/windows/desktop/inputdev/wm-lbuttondown) ileti. ('ı yeniden tanımladığı [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|
|`CPaneDialog::OnUpdateCmdUI`|İletişim kutusu penceresini güncelleştirmek için framework tarafından çağırılır. (Geçersiz kılmaları [CDockablePane::OnUpdateCmdUI](cdockablepane-class.md).)|
|`CPaneDialog::OnWindowPosChanging`|İşleme [WM_WINDOWPOSCHANGING](/windows/desktop/winmsg/wm-windowposchanging) ileti. ('ı yeniden tanımladığı [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|
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

*lpszWindowName*<br/>
[in] Yerleştirme iletişim kutusunun adı.

*pParentWnd*<br/>
[in] Üst pencere işaret eder.

*bHasGripper*<br/>
[in] Bir resim yazısı (kavrayıcı); yerleştirme iletişim kutusu oluşturmak için TRUE Aksi takdirde FALSE.

*lpszTemplateName*<br/>
[in] Kaynak iletişim şablonunun adı.

*nStyle*<br/>
[in] Windows stili.

*nID*<br/>
[in] Denetim kimliği.

*nIDTemplate*<br/>
[in] İletişim şablonu kaynak kimliği.

*dwTabbedStyle*<br/>
[in] Kullanıcı bu denetimi bölme açıklamalı alt yazı başka bir Denetim Masası sürüklediğinde sonuçları sekmeli pencere stili. AFX_CBRS_REGULAR_TABS varsayılan değerdir. Daha fazla bilgi için Açıklamalar bölümüne bakın. [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) yöntemi.

*dwControlBarStyle*<br/>
[in] Ek stil öznitelikleri. AFX_DEFAULT_DOCKING_PANE_STYLE varsayılan değerdir. Daha fazla bilgi için Açıklamalar bölümüne bakın. [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `Create` yönteminde `CPaneDialog` sınıfı. Bu örneğin parçasıdır [bölme boyutunu ayarlayın örnek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]

##  <a name="handleinitdialog"></a>  CPaneDialog::HandleInitDialog

İşleme [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) ileti.

```
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*wParam*<br/>
[in] Varsayılan klavye odağının alınacağı denetimi için işler.

*lParam*<br/>
[in] Ek başlatma verilerini belirtir.

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

*pOccDialogInfo*<br/>
[in] İletişim kutusu nesnesi oluşturmak için kullanılan bir iletişim kutusunda şablon için işaretçi. Bu parametrenin değerini daha sonra içine geçirilen [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem destekler [COccManager](../../mfc/reference/coccmanager-class.md) OLE denetim siteleri ve ActiveX denetimleri yöneten sınıfı. _AFX_OCC_DIALOG_INFO yapısı afxocc.h üstbilgi dosyasında tanımlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)<br/>
[Pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles)
