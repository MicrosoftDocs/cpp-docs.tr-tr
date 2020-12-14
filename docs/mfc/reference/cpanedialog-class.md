---
description: 'Daha fazla bilgi edinin: CPaneDialog Class'
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
ms.openlocfilehash: 6efbbf710f09cf6507853b983a68578a24111a34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345179"
---
# <a name="cpanedialog-class"></a>CPaneDialog sınıfı

`CPaneDialog`Sınıfı, kalıcı olmayan, yerleştirilebilir bir iletişim kutusunu destekler.

## <a name="syntax"></a>Syntax

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
|[CPaneDialog:: Create](#create)|Bir yerleştirilebilir iletişim kutusu oluşturur ve onu bir nesneye ekler `CPaneDialog` .|
|`CPaneDialog::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|`CPaneDialog::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CPaneDialog:: HandleInitDialog](#handleinitdialog)|[WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) iletisini işler. (Tekrar tanımlar `CBasePane::HandleInitDialog` .)|
|`CPaneDialog::OnEraseBkgnd`|[WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd) iletisini işler. ( [CWnd:: Onsilinebilir Sebkplan](../../mfc/reference/cwnd-class.md#onerasebkgnd)' i tanımlar.)|
|`CPaneDialog::OnLButtonDblClk`|[WM_LBUTTONDBLCLK](/windows/win32/inputdev/wm-lbuttondblclk) iletisini işler. ( [CWnd:: OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|
|`CPaneDialog::OnLButtonDown`|[WM_LBUTTONDOWN](/windows/win32/inputdev/wm-lbuttondown) iletisini işler. ( [CWnd:: Onlbuttonkey](../../mfc/reference/cwnd-class.md#onlbuttondown)öğesini tekrar tanımlar.)|
|`CPaneDialog::OnUpdateCmdUI`|İletişim kutusu penceresini güncelleştirmek için Framework tarafından çağırılır. ( [CDockablePane:: OnUpdateCmdUI](cdockablepane-class.md).)|
|`CPaneDialog::OnWindowPosChanging`|[WM_WINDOWPOSCHANGING](/windows/win32/winmsg/wm-windowposchanging) iletisini işler. ( [CWnd:: OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)öğesini tekrar tanımlar.)|
|[CPaneDialog:: Setoccdialogınfo](#setoccdialoginfo)|OLE denetim kapsayıcısı olan bir iletişim kutusunun şablonunu belirtir.|

## <a name="remarks"></a>Açıklamalar

`CPaneDialog`İki adımda bir nesne oluşturun. İlk olarak, kodunuzda nesnesini oluşturun. İkincisi, [CPaneDialog:: Create](#create)öğesini çağırın. Geçerli bir kaynak şablonu adı veya şablon KIMLIĞI belirtmeniz ve ana pencereye bir işaretçi geçirmeniz gerekir. Aksi takdirde, oluşturma işlemi başarısız olur. İletişim kutusunda WS_CHILD ve WS_VISIBLE stili belirtilmelidir. WS_CLIPCHILDREN ve WS_CLIPSIBLINGS stillerini de belirtmenizi öneririz. Daha fazla bilgi için bkz. [pencere stilleri](styles-used-by-mfc.md#window-styles).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CPaneDialog](../../mfc/reference/cpanedialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpanedialog. h

## <a name="cpanedialogcreate"></a><a name="create"></a> CPaneDialog:: Create

Bir yerleştirme iletişim kutusu oluşturur ve onu bir nesneye ekler `CPaneDialog` .

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
'ndaki Takma iletişim kutusunun adı.

*pParentWnd*<br/>
'ndaki Üst pencereyi işaret eder.

*Bhaskavrayıcı*<br/>
'ndaki Bir açıklamalı alt yazı (kavrayıcı) ile takma iletişim kutusu oluşturmak için TRUE; Aksi takdirde, FALSE.

*lpszTemplateName*<br/>
'ndaki Kaynak iletişim kutusu şablonunun adı.

*nStyle*<br/>
'ndaki Windows stili.

*NID*<br/>
'ndaki Denetim KIMLIĞI.

*Nıdtemplate*<br/>
'ndaki İletişim kutusu şablonunun kaynak KIMLIĞI.

*dwTabbedStyle*<br/>
'ndaki Kullanıcı başka bir denetim bölmesini bu denetim bölmesinin başlık üzerine sürüklediğinde oluşan sekmeli pencerenin stili. Varsayılan değer AFX_CBRS_REGULAR_TABS. Daha fazla bilgi için [CBasePane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex) yönteminin açıklamalar bölümüne bakın.

*dwControlBarStyle*<br/>
'ndaki Ek stil öznitelikleri. Varsayılan değer AFX_DEFAULT_DOCKING_PANE_STYLE. Daha fazla bilgi için [CBasePane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex) yönteminin açıklamalar bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında yönteminin nasıl kullanılacağını gösterir `Create` `CPaneDialog` . Bu örnek, [küme bölmesi boyut örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]

## <a name="cpanedialoghandleinitdialog"></a><a name="handleinitdialog"></a> CPaneDialog:: HandleInitDialog

[WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) iletisini işler.

```
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*wParam*<br/>
'ndaki Varsayılan klavye odağını almak için kullanılan denetime işleyin.

*lParam*<br/>
'ndaki Ek başlatma verilerini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE. Ayrıca, TRUE, klavye odağını *wParam* parametresi tarafından belirtilen denetime ayarlar; FALSE, varsayılan klavye odağını ayarlamayı engeller.

### <a name="remarks"></a>Açıklamalar

Framework, denetimleri ve bir iletişim kutusunun görünümünü başlatmak için bu yöntemi kullanır. Framework, iletişim kutusunu görüntülemeden önce bu yöntemi çağırır.

## <a name="cpanedialogsetoccdialoginfo"></a><a name="setoccdialoginfo"></a> CPaneDialog:: Setoccdialogınfo

OLE denetim kapsayıcısı olan bir iletişim kutusunun şablonunu belirtir.

```
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Parametreler

*Poccdialogınfo*<br/>
'ndaki İletişim kutusu nesnesini oluşturmak için kullanılan bir iletişim kutusu şablonuna yönelik işaretçi. Daha sonra bu parametrenin değeri [COccManager:: CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) yöntemine geçirilir.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, OLE denetim siteleri ve ActiveX denetimlerini yöneten [COccManager](../../mfc/reference/coccmanager-class.md) sınıfını destekler. _AFX_OCC_DIALOG_INFO yapısı, afxocc. h üstbilgi dosyasında tanımlanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md)<br/>
[Pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles)
