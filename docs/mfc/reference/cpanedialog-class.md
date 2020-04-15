---
title: CPaneDialog Sınıfı
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
ms.openlocfilehash: ad1225034cc5eca8ca53b042ebe3b55db4a2cf09
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364131"
---
# <a name="cpanedialog-class"></a>CPaneDialog Sınıfı

Sınıf, `CPaneDialog` modeless, takılabilir iletişim kutusunu destekler.

## <a name="syntax"></a>Sözdizimi

```
class CPaneDialog : public CDockablePane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CPaneDialog::CPaneDialog`|Varsayılan oluşturucu.|
|`CPaneDialog::~CPaneDialog`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPaneDialog::Oluştur](#create)|Takılabilir bir iletişim kutusu oluşturur ve nesneye `CPaneDialog` bağlar.|
|`CPaneDialog::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|`CPaneDialog::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CPaneDialog::HandleinitDialog](#handleinitdialog)|[WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) iletiyi işler. (Yeniden `CBasePane::HandleInitDialog`tanımlar.)|
|`CPaneDialog::OnEraseBkgnd`|[WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd) iletiyi işler. [(CWnd yeniden tanımlar::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|
|`CPaneDialog::OnLButtonDblClk`|[WM_LBUTTONDBLCLK](/windows/win32/inputdev/wm-lbuttondblclk) iletisini işler. [(CWnd yeniden tanımlar::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|
|`CPaneDialog::OnLButtonDown`|[WM_LBUTTONDOWN](/windows/win32/inputdev/wm-lbuttondown) iletiyi işler. [(CWnd yeniden tanımlar::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|
|`CPaneDialog::OnUpdateCmdUI`|İletişim kutusu penceresini güncelleştirmek için çerçeve tarafından çağrılır. [(Overrides CDockablePane::OnUpdateCmdUI](cdockablepane-class.md).)|
|`CPaneDialog::OnWindowPosChanging`|[WM_WINDOWPOSCHANGING](/windows/win32/winmsg/wm-windowposchanging) iletiyi işler. [(CWnd yeniden tanımlar::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|OLE denetim kapsayıcısı olan bir iletişim kutusu şablonu belirtir.|

## <a name="remarks"></a>Açıklamalar

Bir `CPaneDialog` nesneyi iki adımda oluştur. İlk olarak, kodunuzda nesne oluşturmak. İkinci olarak, [CPaneDialog'u arayın::Oluştur.](#create) Geçerli bir kaynak şablon adı veya şablon kimliği belirtmeniz ve bir işaretçiyi ana pencereye geçirmeniz gerekir. Aksi takdirde, oluşturma işlemi başarısız olur. İletişim kutusu, WS_CHILD ve WS_VISIBLE stilini belirtmelidir. WS_CLIPCHILDREN ve WS_CLIPSIBLINGS stilleri de belirtmenizi öneririz. Daha fazla bilgi için [Bkz. Pencere Stilleri.](styles-used-by-mfc.md#window-styles)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[Cdockablepane](../../mfc/reference/cdockablepane-class.md)

[CPaneDialog](../../mfc/reference/cpanedialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpanedialog.h

## <a name="cpanedialogcreate"></a><a name="create"></a>CPaneDialog::Oluştur

Yerleştirme iletişim kutusu oluşturur ve bir `CPaneDialog` nesneye bağlar.

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
[içinde] Yerleştirme iletişim kutusunun adı.

*pParentWnd*<br/>
[içinde] Üst pencereyi işaret ediyor.

*bHasGripper*<br/>
[içinde] Bir başlık (kavrayıcı) ile yerleştirme iletişim kutusu oluşturmak için TRUE; aksi takdirde, YANLIŞ.

*lpszTemplateName*<br/>
[içinde] Kaynak iletişim şablonunun adı.

*nStyle*<br/>
[içinde] Windows stili.

*Nıd*<br/>
[içinde] Kontrol kimliği.

*nIDTemplate*<br/>
[içinde] İletişim şablonunun kaynak kimliği.

*dwTabbedStyle*<br/>
[içinde] Kullanıcı başka bir denetim bölmesini bu denetim bölmesinin alt yazısına sürüklediğinde oluşan sekmeli pencerenin stili. Varsayılan değer AFX_CBRS_REGULAR_TABS. Daha fazla bilgi için [CBasePane:CreateEx](../../mfc/reference/cbasepane-class.md#createex) yönteminin Açıklamalar bölümüne bakın.

*dwControlBarStyle*<br/>
[içinde] Ek stil öznitelikleri. Varsayılan değer AFX_DEFAULT_DOCKING_PANE_STYLE. Daha fazla bilgi için [CBasePane:CreateEx](../../mfc/reference/cbasepane-class.md#createex) yönteminin Açıklamalar bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemin sınıfta `Create` nasıl `CPaneDialog` kullanılacağını göstermektedir. Bu örnek, [Küme Bölmesi Boyutu örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]

## <a name="cpanedialoghandleinitdialog"></a><a name="handleinitdialog"></a>CPaneDialog::HandleinitDialog

[WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) iletiyi işler.

```
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*Wparam*<br/>
[içinde] Varsayılan klavye odağı almak için denetim için işleme.

*Lparam*<br/>
[içinde] Ek başlatma verilerini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ. Buna ek olarak, TRUE *wParam* parametresi tarafından belirtilen kontrol için klavye odak ayarlar; FALSE varsayılan klavye odağının ayarlanmasını engeller.

### <a name="remarks"></a>Açıklamalar

Çerçeve, denetimleri ve bir iletişim kutusunun görünümünü başlatmayı sağlamak için bu yöntemi kullanır. Çerçeve, iletişim kutusunu görüntülemeden önce bu yöntemi çağırır.

## <a name="cpanedialogsetoccdialoginfo"></a><a name="setoccdialoginfo"></a>CPaneDialog::SetOccDialogInfo

OLE denetim kapsayıcısı olan bir iletişim kutusu şablonu belirtir.

```
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Parametreler

*pOccDialogInfo*<br/>
[içinde] İletişim kutusu nesnesini oluşturmak için kullanılan bir iletişim kutusu şablonuna işaretçi. Bu parametrenin değeri daha sonra [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) yöntemine aktarılır.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, OLE kontrol sitelerini ve ActiveX denetimlerini yöneten [COccManager](../../mfc/reference/coccmanager-class.md) sınıfını destekler. _AFX_OCC_DIALOG_INFO yapısı afxocc.h üstbilgi dosyasında tanımlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)<br/>
[Pencere Stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles)
