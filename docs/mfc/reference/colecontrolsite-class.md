---
title: COleControlSite Sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleControlSite
- AFXOCC/COleControlSite
- AFXOCC/COleControlSite::COleControlSite
- AFXOCC/COleControlSite::BindDefaultProperty
- AFXOCC/COleControlSite::BindProperty
- AFXOCC/COleControlSite::CreateControl
- AFXOCC/COleControlSite::DestroyControl
- AFXOCC/COleControlSite::DoVerb
- AFXOCC/COleControlSite::EnableDSC
- AFXOCC/COleControlSite::EnableWindow
- AFXOCC/COleControlSite::FreezeEvents
- AFXOCC/COleControlSite::GetDefBtnCode
- AFXOCC/COleControlSite::GetDlgCtrlID
- AFXOCC/COleControlSite::GetEventIID
- AFXOCC/COleControlSite::GetExStyle
- AFXOCC/COleControlSite::GetProperty
- AFXOCC/COleControlSite::GetStyle
- AFXOCC/COleControlSite::GetWindowText
- AFXOCC/COleControlSite::InvokeHelper
- AFXOCC/COleControlSite::InvokeHelperV
- AFXOCC/COleControlSite::IsDefaultButton
- AFXOCC/COleControlSite::IsWindowEnabled
- AFXOCC/COleControlSite::ModifyStyle
- AFXOCC/COleControlSite::ModifyStyleEx
- AFXOCC/COleControlSite::MoveWindow
- AFXOCC/COleControlSite::QuickActivate
- AFXOCC/COleControlSite::SafeSetProperty
- AFXOCC/COleControlSite::SetDefaultButton
- AFXOCC/COleControlSite::SetDlgCtrlID
- AFXOCC/COleControlSite::SetFocus
- AFXOCC/COleControlSite::SetProperty
- AFXOCC/COleControlSite::SetPropertyV
- AFXOCC/COleControlSite::SetWindowPos
- AFXOCC/COleControlSite::SetWindowText
- AFXOCC/COleControlSite::ShowWindow
- AFXOCC/COleControlSite::GetControlInfo
- AFXOCC/COleControlSite::m_bIsWindowless
- AFXOCC/COleControlSite::m_ctlInfo
- AFXOCC/COleControlSite::m_dwEventSink
- AFXOCC/COleControlSite::m_dwMiscStatus
- AFXOCC/COleControlSite::m_dwPropNotifySink
- AFXOCC/COleControlSite::m_dwStyle
- AFXOCC/COleControlSite::m_hWnd
- AFXOCC/COleControlSite::m_iidEvents
- AFXOCC/COleControlSite::m_nID
- AFXOCC/COleControlSite::m_pActiveObject
- AFXOCC/COleControlSite::m_pCtrlCont
- AFXOCC/COleControlSite::m_pInPlaceObject
- AFXOCC/COleControlSite::m_pObject
- AFXOCC/COleControlSite::m_pWindowlessObject
- AFXOCC/COleControlSite::m_pWndCtrl
- AFXOCC/COleControlSite::m_rect
helpviewer_keywords:
- COleControlSite [MFC], COleControlSite
- COleControlSite [MFC], BindDefaultProperty
- COleControlSite [MFC], BindProperty
- COleControlSite [MFC], CreateControl
- COleControlSite [MFC], DestroyControl
- COleControlSite [MFC], DoVerb
- COleControlSite [MFC], EnableDSC
- COleControlSite [MFC], EnableWindow
- COleControlSite [MFC], FreezeEvents
- COleControlSite [MFC], GetDefBtnCode
- COleControlSite [MFC], GetDlgCtrlID
- COleControlSite [MFC], GetEventIID
- COleControlSite [MFC], GetExStyle
- COleControlSite [MFC], GetProperty
- COleControlSite [MFC], GetStyle
- COleControlSite [MFC], GetWindowText
- COleControlSite [MFC], InvokeHelper
- COleControlSite [MFC], InvokeHelperV
- COleControlSite [MFC], IsDefaultButton
- COleControlSite [MFC], IsWindowEnabled
- COleControlSite [MFC], ModifyStyle
- COleControlSite [MFC], ModifyStyleEx
- COleControlSite [MFC], MoveWindow
- COleControlSite [MFC], QuickActivate
- COleControlSite [MFC], SafeSetProperty
- COleControlSite [MFC], SetDefaultButton
- COleControlSite [MFC], SetDlgCtrlID
- COleControlSite [MFC], SetFocus
- COleControlSite [MFC], SetProperty
- COleControlSite [MFC], SetPropertyV
- COleControlSite [MFC], SetWindowPos
- COleControlSite [MFC], SetWindowText
- COleControlSite [MFC], ShowWindow
- COleControlSite [MFC], GetControlInfo
- COleControlSite [MFC], m_bIsWindowless
- COleControlSite [MFC], m_ctlInfo
- COleControlSite [MFC], m_dwEventSink
- COleControlSite [MFC], m_dwMiscStatus
- COleControlSite [MFC], m_dwPropNotifySink
- COleControlSite [MFC], m_dwStyle
- COleControlSite [MFC], m_hWnd
- COleControlSite [MFC], m_iidEvents
- COleControlSite [MFC], m_nID
- COleControlSite [MFC], m_pActiveObject
- COleControlSite [MFC], m_pCtrlCont
- COleControlSite [MFC], m_pInPlaceObject
- COleControlSite [MFC], m_pObject
- COleControlSite [MFC], m_pWindowlessObject
- COleControlSite [MFC], m_pWndCtrl
- COleControlSite [MFC], m_rect
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
ms.openlocfilehash: 90c41a1be1a66cdceebb3f045a98167e56b7cf4c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753950"
---
# <a name="colecontrolsite-class"></a>COleControlSite Sınıfı

Özel istemci tarafı denetim arabirimleri için destek sağlar.

## <a name="syntax"></a>Sözdizimi

```
class COleControlSite : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleControlSite::COleControlSite](#colecontrolsite)|Bir `COleControlSite` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleControlSite::BindDefaultProperty](#binddefaultproperty)|Barındırılan denetimin varsayılan özelliğini bir veri kaynağına bağlar.|
|[COleControlSite::BindProperty](#bindproperty)|Barındırılan denetimin özelliğini bir veri kaynağına bağlar.|
|[COleControlSite::CreateControl](#createcontrol)|Barındırılan activex denetimi oluşturur.|
|[COleControlSite::DestroyControl](#destroycontrol)|Barındırılan denetimi yok eder.|
|[COleControlSite::DoVerb](#doverb)|Barındırılan denetimin belirli bir fiilini yürütür.|
|[COleControlSite::EnableDSC](#enabledsc)|Bir kontrol sitesi için veri kaynağı sağlar.|
|[COleControlSite::EnableWindow](#enablewindow)|Denetim alanını etkinleştirir.|
|[COleControlSite::FreezeEvents](#freezeevents)|Denetim sitesi olayları kabul edip etmediğini belirtir.|
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|Barındırılan denetim için varsayılan düğme kodunu alır.|
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|Denetimin tanımlayıcısını alır.|
|[COleControlSite::GetEventIID](#geteventiid)|Barındırılan denetim için olay arabiriminin kimliğini alır.|
|[COleControlSite::GetExStyle](#getexstyle)|Denetim sitesinin genişletilmiş stillerini alır.|
|[COleControlSite::GetProperty](#getproperty)|Barındırılan denetimin belirli bir özelliğini alır.|
|[COleControlSite::GetStyle](#getstyle)|Denetim alanının stillerini alır.|
|[COleControlSite::GetWindowText](#getwindowtext)|Barındırılan denetimin metnini alır.|
|[COleControlSite::InvokeHelper](#invokehelper)|Barındırılan denetimin belirli bir yöntemini çağırın.|
|[COleControlSite::InvokeHelperV](#invokehelperv)|Bağımsız değişken bir bağımsız değişken listesiyle barındırılan denetimin belirli bir yöntemini çağırın.|
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|Denetimin penceredeki varsayılan düğme olup olmadığını belirler.|
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|Denetim sitesinin görünür durumunu denetler.|
|[COleControlSite::ModifyStyle](#modifystyle)|Denetim sitesinin geçerli genişletilmiş stillerini değiştirir.|
|[COleControlSite::ModifyStyleEx](#modifystyleex)|Denetim sitesinin geçerli stillerini değiştirir.|
|[COleControlSite::MoveWindow](#movewindow)|Denetim alanının konumunu değiştirir.|
|[COleControlSite::QuickActivate](#quickactivate)|Hızlı barındırılan denetimi etkinleştirir.|
|[COleControlSite::SafeSetProperty](#safesetproperty)|Özel durum atma şansı olmadan denetimin bir özelliğini veya yöntemini ayarlar.|
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|Penceredeki varsayılan düğmeyi ayarlar.|
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|Denetimin tanımlayıcısını alır.|
|[COleControlSite::SetFocus](#setfocus)|Odak noktasını kontrol alanına ayarlar.|
|[COleControlSite::SetProperty](#setproperty)|Barındırılan denetimin belirli bir özelliğini ayarlar.|
|[COleControlSite::SetPropertyV](#setpropertyv)|Değişken bir bağımsız değişken listeyle barındırılan denetimin belirli bir özelliğini ayarlar.|
|[COleControlSite::SetWindowPos](#setwindowpos)|Kontrol alanının konumunu ayarlar.|
|[COleControlSite::SetWindowText](#setwindowtext)|Barındırılan denetimin metnini ayarlar.|
|[COleControlSite::ShowWindow](#showwindow)|Denetim sitesini gösterir veya gizler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleControlSite::GetControlInfo](#getcontrolinfo)|Barındırılan denetim için klavye bilgilerini ve mnemonics alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|Barındırılan denetimin penceresiz denetim olup olmadığını belirler.|
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|Denetim için klavye işleme hakkında bilgi içerir.|
|[COleControlSite::m_dwEventSink](#m_dweventsink)|Denetimin bağlantı noktasının çerezi.|
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|Barındırılan kontrol için çeşitli durumlar.|
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|Kontrolün `IPropertyNotifySink` kurabiyesi.|
|[COleControlSite::m_dwStyle](#m_dwstyle)|Barındırılan denetimin stilleri.|
|[COleControlSite::m_hWnd](#m_hwnd)|Kontrol alanının sapı.|
|[COleControlSite::m_iidEvents](#m_iidevents)|Barındırılan denetim için olay arabiriminin kimliği.|
|[COleControlSite::m_nID](#m_nid)|Barındırılan denetimin kimliği.|
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|Barındırılan `IOleInPlaceActiveObject` denetimin nesnesine işaretçi.|
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|Barındırılan denetimin kapsayıcısı.|
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|Barındırılan `IOleInPlaceObject` denetimin nesnesine işaretçi.|
|[COleControlSite::m_pObject](#m_pobject)|Denetimin `IOleObjectInterface` arabirimine bir işaretçi.|
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|Denetimin `IOleInPlaceObjectWindowless` arabirimine bir işaretçi.|
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|Barındırılan denetim için pencere nesnesine işaretçi.|
|[COleControlSite::m_rect](#m_rect)|Kontrol alanının boyutları.|

## <a name="remarks"></a>Açıklamalar

Bu destek, gömülü activex denetiminin görüntü alanının konumu ve kapsamı, takma adı, kullanıcı arabirimi, ortam özellikleri ve kapsayıcıtarafından sağlanan diğer kaynaklar hakkında bilgi edinmesinin birincil yoludur. `COleControlSite`[iOleControlSite](/windows/win32/api/ocidl/nn-ocidl-iolecontrolsite), [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [IOleClientSite](/windows/win32/api/oleidl/nn-oleidl-ioleclientsite), [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink), `IBoundObjectSite`, `INotifyDBEvents` [IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md) arayüzlerini tam olarak uygular. Buna ek olarak, IDispatch arabirimi (ortam özellikleri ve olay lavabolar için destek sağlayan) da uygulanır.

ActiveX denetim sitesi oluşturmak `COleControlSite`için , 'den `COleControlSite`bir sınıf türetmek. Kapsayıcı `CWnd`için türetilmiş sınıfınızda (örneğin, iletişim kutunuz) `CWnd::CreateControlSite` işlevi geçersiz kılar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlSite`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxocc.h

## <a name="colecontrolsitebinddefaultproperty"></a><a name="binddefaultproperty"></a>COleControlSite::BindDefaultProperty

Arama nesnesinin varsayılan basit ciltli özelliğini, tür kitaplığında işaretli olarak, veri kaynağı denetiminin DataSource, User Name, Password ve SQL özellikleri tarafından tanımlanan temel imleçe bağlar.

```
virtual void BindDefaultProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    LPCTSTR szFieldName,
    CWnd* pDSCWnd);
```

### <a name="parameters"></a>Parametreler

*dwDispID*<br/>
Veri kaynağı denetimine bağlanacak bir veri bağlı denetimde bir özelliğin DISPID'ini belirtir.

*vtProp*<br/>
Bağlanacak özelliğin türünü belirtir ( örneğin, VT_BSTR, VT_VARIANT ve benzeri.

*szFieldName*<br/>
Özelliğin bağlı olacağı veri kaynağı denetimi tarafından sağlanan imleçte sütunun adını belirtir.

*pDSCWnd*<br/>
Özelliğin `CWnd`bağlı olacağı veri kaynağı denetimini barındıran türetilmiş nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu `CWnd` işlevde adını aldığınız nesne, veriye bağlı bir denetim olmalıdır.

## <a name="colecontrolsitebindproperty"></a><a name="bindproperty"></a>COleControlSite::BindProperty

Arama nesnesinin basit ciltli özelliğini, tür kitaplığında işaretli olarak, veri kaynağı denetiminin DataSource, UserName, Password ve SQL özellikleri tarafından tanımlanan temel imleçiçin bağlar.

```
virtual void BindProperty(
    DISPID dwDispId,
    CWnd* pWndDSC);
```

### <a name="parameters"></a>Parametreler

*dwDispId*<br/>
Veri kaynağı denetimine bağlanacak bir veri bağlı denetimde bir özelliğin DISPID'ini belirtir.

*pWndDSC*<br/>
Özelliğin `CWnd`bağlı olacağı veri kaynağı denetimini barındıran türetilmiş nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu `CWnd` işlevde adını aldığınız nesne, veriye bağlı bir denetim olmalıdır.

## <a name="colecontrolsitecolecontrolsite"></a><a name="colecontrolsite"></a>COleControlSite::COleControlSite

Yeni `COleControlSite` bir nesne oluşturuyor.

```
explicit COleControlSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>Parametreler

*pCtrlCont*<br/>
Denetimin kapsayıcısına işaretçi (AtiveX denetimini barındıran pencereyi temsil eder).

### <a name="remarks"></a>Açıklamalar

Bu işlev [COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer) işlevi tarafından çağrılır. Kapsayıcıların oluşturulması hakkında daha fazla bilgi için [COccManager::CreateSite'ye](../../mfc/reference/coccmanager-class.md#createsite)bakın.

## <a name="colecontrolsitecreatecontrol"></a><a name="createcontrol"></a>COleControlSite::CreateControl

Nesne tarafından barındırılan `COleControlSite` bir ActiveX denetimi oluşturur.

```
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    UINT nID,
    CFile* pPersist = NULL,
    BOOL bStorage = FALSE,
    BSTR bstrLicKey = NULL);

virtual HRESULT CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const POINT* ppt,
    const SIZE* psize,
    UINT nID,
    CFile* pPersist = NULL,
    BOOL bStorage = FALSE,
    BSTR bstrLicKey = NULL);
```

### <a name="parameters"></a>Parametreler

*pWndCtrl*<br/>
Denetimi temsil eden pencere nesnesi için bir işaretçi.

*Clsıd*<br/>
Denetimin benzersiz sınıf kimliği.

*lpszWindowName*<br/>
Denetimde görüntülenecek metne işaretçi. Winodw'ın Resim Yazısı veya Metin özelliğinin değerini ayarlar (varsa).

*Dwstyle*<br/>
Windows stilleri. Kullanılabilir stiller **Açıklamalar** bölümünde listelenir.

*Rect*<br/>
Denetimin boyutunu ve konumunu belirtir. Bir `CRect` nesne veya yapı `RECT` olabilir.

*Nıd*<br/>
Denetimin alt pencere kimliğini belirtir.

*pPersist*<br/>
Denetim için `CFile` kalıcı durumu içeren bir işaretçi. Varsayılan değer NULL'dur ve denetimin durumunu kalıcı depolamadan geri almadan kendisini başlattıgına işaret eder. NULL değilse, denetimin kalıcı verilerini `CFile`içeren türetilmiş bir nesneye akış veya depolama biçiminde işaretçi olmalıdır. Bu veriler istemcinin önceki etkinleştirme kaydedilmiş olabilir. Diğer `CFile` verileri içerebilir, ancak okuma-yazma işaretçisinin çağrı sırasında ki ilk kalıcı veri baytına `CreateControl`ayarlatılması gerekir.

*bDepolama*<br/>
*pPersist'deki* verilerin veri olarak `IStorage` mı `IStream` yorumlanması gerektiğini gösterir. *pPersist'deki* veriler bir depolama ysa, *bStorage* TRUE olmalıdır. *pPersist'deki* veriler bir akışsa, *bStorage* FALSE olmalıdır. Varsayılan değer FALSE'dur.

*bstrLicKey*<br/>
İsteğe bağlı lisans anahtar verileri. Bu veriler yalnızca çalışma zamanı lisans anahtarı gerektiren denetimler oluşturmak için gereklidir. Denetim lisanslamayı destekliyorsa, denetimin oluşturulmasının başarılı olması için bir lisans anahtarı sağlamanız gerekir. Varsayılan değer NULL'dur.

*Ppt*<br/>
Denetimin sol `POINT` üst köşesini içeren bir yapıya işaretçi. Denetimin boyutu *psize*değerine göre belirlenir. *PPT* ve *psize* değerleri, denetimin boyutunu ve konumunu belirten isteğe bağlı bir yöntemdir.

*psize*<br/>
Denetimin boyutunu `SIZE` içeren bir yapıya işaretçi. Sol üst köşe *ppt*değerine göre belirlenir. *PPT* ve *psize* değerleri, denetimin boyutunu ve konumunu belirten isteğe bağlı bir yöntemdir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Yalnızca Windows *dwStyle* bayraklarının bir alt `CreateControl`kümesi aşağıdakiler tarafından desteklenir:

- WS_VISIBLE Başlangıçta görünür bir pencere oluşturur. Denetimin sıradan pencereler gibi hemen görünür olmasını istiyorsanız gereklidir.

- WS_DISABLED Başlangıçta devre dışı bırakılmış bir pencere oluşturur. Devre dışı bırakılmış bir pencere kullanıcıdan giriş alamaz. Denetimetkin bir özelliği varsa ayarlanabilir.

- WS_BORDER ince çizgi kenarlıklı bir pencere oluşturur. Denetimin BorderStyle özelliği varsa ayarlanabilir.

- WS_GROUP Bir denetim grubunun ilk denetimini belirtir. Kullanıcı yön tuşlarını kullanarak klavye odağı gruptaki bir denetimden diğerine değiştirebilir. İlk denetimden sonra WS_GROUP stili ile tanımlanan tüm denetimler aynı gruba aittir. WS_GROUP stili ile bir sonraki denetim grubu sona erdirer ve bir sonraki grubu başlatır.

- WS_TABSTOP Kullanıcı TAB tuşuna bastığında klavye odağı alabilecek bir denetim belirtir. TAB tuşuna basıldığında klavye odağı WS_TABSTOP stilinin bir sonraki denetimine dönüşür.

Varsayılan boyutlu denetimler oluşturmak için ikinci aşırı yüklemeyi kullanın.

## <a name="colecontrolsitedestroycontrol"></a><a name="destroycontrol"></a>COleControlSite::DestroyControl

Nesneyi `COleControlSite` yok eder.

```
virtual BOOL DestroyControl();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır sız, başarılı ysa, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Tamamlandıktan sonra, nesne bellekten serbest bırakılır ve nesneye işaretçiler artık geçerli değildir.

## <a name="colecontrolsitedoverb"></a><a name="doverb"></a>COleControlSite::DoVerb

Belirtilen fiili yürütür.

```
virtual HRESULT DoVerb(
    LONG nVerb,
    LPMSG lpMsg = NULL);
```

### <a name="parameters"></a>Parametreler

*nVerb*<br/>
Yürütmek için fiil belirtir. Aşağıdakilerden birini içerebilir:

|Değer|Anlamı|Sembol|
|-----------|-------------|------------|
|0|Birincil fiil|OLEIVERB_PRIMARY|
|-1|İkincil fiil|(Yok)|
|1|Düzenleme için nesneyi görüntüler.|OLEIVERB_SHOW|
|-2|Öğeyi ayrı bir pencerede edinimi.|OLEIVERB_OPEN|
|-3|Nesneyi gizler.|OLEIVERB_HIDE|
|-4|Yerinde bir denetim etkinleştirir.|OLEIVERB_UIACTIVATE|
|-5|Ek kullanıcı arabirimi öğeleri olmadan bir denetimi yerinde etkinleştirir.|OLEIVERB_INPLACEACTIVATE|
|-7|Denetimin özelliklerini görüntüleyin.|OLEIVERB_PROPERTIES|

*lpMsg*<br/>
Öğenin etkinleştirilmesine neden olan iletiyi işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, belirtilen fiili `IOleObject` yürütmek için doğrudan denetimin arabirimi üzerinden çağırır. Bu işlev çağrısı nın sonucu olarak bir özel durum atılırsa, bir HRESULT hata kodu döndürülür.

Daha fazla bilgi için Windows SDK'daki [IOleObject::DoVerb'e](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) bakın.

## <a name="colecontrolsiteenabledsc"></a><a name="enabledsc"></a>COleControlSite::EnableDSC

Kontrol sitesi için veri kaynağı sağlar.

```
virtual void EnableDSC();
```

### <a name="remarks"></a>Açıklamalar

Denetim sitesi için veri kaynağı etkinleştirmek ve başlatma çerçevesi tarafından çağrıldı. Özelleştirilmiş davranış sağlamak için bu işlevi geçersiz kılın.

## <a name="colecontrolsiteenablewindow"></a><a name="enablewindow"></a>COleControlSite::EnableWindow

Kontrol sitesine fare ve klavye girişi sağlar veya devre dışı kılabilir.

```
virtual BOOL EnableWindow(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
Pencereyi etkinleştirip etkinleştirmeye veya devre dışı bırakmayacağını belirtir: Pencere girişi etkinolacaksa TRUE, aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Pencere daha önce devre dışı bırakılmışsa sıfır olmayan, aksi takdirde 0.

## <a name="colecontrolsitefreezeevents"></a><a name="freezeevents"></a>COleControlSite::FreezeEvents

Denetim sitesinin denetimden kaynaklanan olayları işleyip işlemeyeceğini veya yok sayılacağını belirtir.

```cpp
void FreezeEvents(BOOL bFreeze);
```

### <a name="parameters"></a>Parametreler

*bFreeze*<br/>
Denetim sitesinin olayları kabul etmeyi durdurmak isteyip istemeyeceğini belirtir. Denetim olayları kabul etmiyorsa sıfırsız; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

*bFreeze* TRUE ise, denetim sitesi saçak olaylarını durdurmak için denetim ister. *bFreeze* FALSE ise, denetim sitesi olayları ateşlemeye devam etmek için denetim ister.

> [!NOTE]
> Denetim sitesi tarafından istenirse olayları ateşlemeyi durdurmak için denetim gerekli değildir. Bu ateş devam edebilirsiniz ama sonraki tüm olaylar kontrol sitesi tarafından göz ardı edilecektir.

## <a name="colecontrolsitegetcontrolinfo"></a><a name="getcontrolinfo"></a>COleControlSite::GetControlInfo

Denetimin klavye mnemonics ve klavye davranışı hakkında bilgi alır.

```cpp
void GetControlInfo();
```

### <a name="remarks"></a>Açıklamalar

Bilgiler [COleControlSite saklanır::m_ctlInfo](#m_ctlinfo).

## <a name="colecontrolsitegetdefbtncode"></a><a name="getdefbtncode"></a>COleControlSite::GetDefBtnCode

Denetimin varsayılan bir basma düğmesi olup olmadığını belirler.

```
DWORD GetDefBtnCode();
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri olabilir:

- DLGC_DEFPUSHBUTTON Denetim iletişim kutusundavarsayılan düğmedir.

- DLGC_UNDEFPUSHBUTTON Denetimi iletişim kutusundavarsayılan düğme değildir.

- **0** Denetim bir düğme değildir.

## <a name="colecontrolsitegetdlgctrlid"></a><a name="getdlgctrlid"></a>COleControlSite::GetDlgCtrlID

Denetimin tanımlayıcısını alır.

```
virtual int GetDlgCtrlID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin iletişim öğesi tanımlayıcısı.

## <a name="colecontrolsitegeteventiid"></a><a name="geteventiid"></a>COleControlSite::GetEventIID

Denetimin varsayılan olay arabirimi için bir işaretçi alır.

```
BOOL GetEventIID(IID* piid);
```

### <a name="parameters"></a>Parametreler

*piid*<br/>
Arabirim kimliği için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfır sız, başarılı ysa, aksi takdirde 0. Başarılı olursa, *piid* denetimin varsayılan olay arabirimi için arabirim kimliği içerir.

## <a name="colecontrolsitegetexstyle"></a><a name="getexstyle"></a>COleControlSite::GetExStyle

Pencerenin genişletilmiş stillerini alır.

```
virtual DWORD GetExStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim penceresi genişletilmiş stilleri.

### <a name="remarks"></a>Açıklamalar

Normal stilleri almak için [COleControlSite'yi arayın::GetStyle.](#getstyle)

## <a name="colecontrolsitegetproperty"></a><a name="getproperty"></a>COleControlSite::GetProperty

*dwDispID*tarafından belirtilen kontrol özelliğini alır.

```
virtual void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>Parametreler

*dwDispID*<br/>
Denetimin varsayılan `IDispatch` arabiriminde bulunan özelliğin sevk kimliğini niçin alınmasını tanımlar.

*vtProp*<br/>
Alınacak özelliğin türünü belirtir. Olası değerler için COleDispatchDriver için Açıklamalar bölümüne [bakın:InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*pvProp*<br/>
Özellik değerini alacak değişkenin adresi. *VtProp*tarafından belirtilen türe uygun olmalıdır.

### <a name="remarks"></a>Açıklamalar

Değer *pvProp*ile döndürülür.

## <a name="colecontrolsitegetstyle"></a><a name="getstyle"></a>COleControlSite::GetStyle

Denetim alanının stillerini alır.

```
virtual DWORD GetStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pencerenin stilleri.

### <a name="remarks"></a>Açıklamalar

Olası değerlerin listesi için [Bkz. Windows Stilleri.](../../mfc/reference/styles-used-by-mfc.md#window-styles) Kontrol sitesinin genişletilmiş stillerini almak için [COleControlSite'yi arayın::GetExStyle.](#getexstyle)

## <a name="colecontrolsitegetwindowtext"></a><a name="getwindowtext"></a>COleControlSite::GetWindowText

Denetimin geçerli metnini alır.

```
virtual void GetWindowText(CString& str) const;
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Denetimin geçerli `CString` metnini içeren bir nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Denetim Resim Yazısı stok özelliğini destekliyorsa, bu değer döndürülür. Resim Yazısı stok özelliği desteklenmezse, Metin özelliğinin değeri döndürülür.

## <a name="colecontrolsiteinvokehelper"></a><a name="invokehelper"></a>COleControlSite::InvokeHelper

*wFlags*tarafından belirtilen *bağlamda, dwDispID*tarafından belirtilen yöntem veya özelliği çağırır.

```
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>Parametreler

*dwDispID*<br/>
Çağrıldırılmak üzere denetimin `IDispatch` arabiriminde bulunan özelliğin veya yöntemin sevk kimliğini tanımlar.

*wFlags*<br/>
IDispatch'e yapılan çağrının bağlamını açıklayan bayraklar::Çağır. Olası *wFlags* değerleri `IDispatch::Invoke` için Windows SDK'ya bakın.

*vtRet*<br/>
İade değerinin türünü belirtir. Olası değerler için COleDispatchDriver için Açıklamalar bölümüne [bakın:InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*pvRet*<br/>
Özellik değerini veya iade değerini alacak değişkenin adresi. *VtRet*tarafından belirtilen türe uygun olmalıdır.

*pbParamInfo*<br/>
*PbParamInfo'yu*izleyen parametrelerin türlerini belirten null-sonlandırılan bayt dizesini işaretçi. Olası değerler için COleDispatchDriver için Açıklamalar bölümüne [bakın:InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
*PbParamInfo'da*belirtilen türparametrelerin değişken listesi.

### <a name="remarks"></a>Açıklamalar

*pbParamInfo* parametresi yönteme veya özelliğe geçirilen parametrelerin türlerini belirtir. Bağımsız değişken ler listesi ile temsil edilir ... sözdizimi bildiriminde.

Bu işlev parametreleri VARIANTARG değerlerine dönüştürür, `IDispatch::Invoke` ardından denetim yöntemini çağırır. Çağrı `IDispatch::Invoke` başarısız olursa, bu işlev bir özel durum atar. Tarafından döndürülen durum `IDispatch::Invoke` `DISP_E_EXCEPTION`kodu ise, bu `COleDispatchException` işlev bir nesne `COleException`atar, aksi takdirde bir .

## <a name="colecontrolsiteinvokehelperv"></a><a name="invokehelperv"></a>COleControlSite::InvokeHelperV

*wFlags*tarafından belirtilen *bağlamda, dwDispID*tarafından belirtilen yöntem veya özelliği çağırır.

```
virtual void InvokeHelperV(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo,
    va_list argList);
```

### <a name="parameters"></a>Parametreler

*dwDispID*<br/>
Çağrıldırılmak üzere denetimin `IDispatch` arabiriminde bulunan özelliğin veya yöntemin sevk kimliğini tanımlar.

*wFlags*<br/>
IDispatch'e yapılan çağrının bağlamını açıklayan bayraklar::Çağır.

*vtRet*<br/>
İade değerinin türünü belirtir. Olası değerler için COleDispatchDriver için Açıklamalar bölümüne [bakın:InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*pvRet*<br/>
Özellik değerini veya iade değerini alacak değişkenin adresi. *VtRet*tarafından belirtilen türe uygun olmalıdır.

*pbParamInfo*<br/>
*PbParamInfo'yu*izleyen parametrelerin türlerini belirten null-sonlandırılan bayt dizesini işaretçi. Olası değerler için COleDispatchDriver için Açıklamalar bölümüne [bakın:InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*Arglist*<br/>
Değişken bağımsız değişken listesine işaretçi.

### <a name="remarks"></a>Açıklamalar

*pbParamInfo* parametresi yönteme veya özelliğe geçirilen parametrelerin türlerini belirtir. Çağrılan yöntem veya özellik için ekstra parametreler *va_list* parametresi kullanılarak geçirilebilir.

Genellikle, bu işlev tarafından `COleControlSite::InvokeHelper`çağrılır.

## <a name="colecontrolsiteisdefaultbutton"></a><a name="isdefaultbutton"></a>COleControlSite::IsDefaultButton

Denetimin varsayılan düğme olup olmadığını belirler.

```
BOOL IsDefaultButton();
```

### <a name="return-value"></a>Dönüş Değeri

Denetim penceredeki varsayılan düğmeise sıfır yok, aksi takdirde sıfır.

## <a name="colecontrolsiteiswindowenabled"></a><a name="iswindowenabled"></a>COleControlSite::IsWindowEnabled

Denetim sitesinin etkin olup olmadığını belirler.

```
virtual BOOL IsWindowEnabled() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim etkinse sıfır değil, aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Değer, denetimin Etkin stok özelliğinden alınır.

## <a name="colecontrolsitem_biswindowless"></a><a name="m_biswindowless"></a>COleControlSite::m_bIsWindowless

Nesnenin penceresiz bir denetim olup olmadığını belirler.

```
BOOL m_bIsWindowless;
```

### <a name="remarks"></a>Açıklamalar

Denetimin penceresi yoksa sıfır yok, aksi takdirde sıfır.

## <a name="colecontrolsitem_ctlinfo"></a><a name="m_ctlinfo"></a>COleControlSite::m_ctlInfo

Klavye girişinin denetim tarafından nasıl işlendiğine ilişkin bilgiler.

```
CONTROLINFO m_ctlInfo;
```

### <a name="remarks"></a>Açıklamalar

Bu bilgiler [CONTROLINFO](/windows/win32/api/ocidl/ns-ocidl-controlinfo) yapısında depolanır.

## <a name="colecontrolsitem_dweventsink"></a><a name="m_dweventsink"></a>COleControlSite::m_dwEventSink

Denetimin olay lavabosundaki bağlantı noktasının çerezini içerir.

```
DWORD m_dwEventSink;
```

## <a name="colecontrolsitem_dwmiscstatus"></a><a name="m_dwmiscstatus"></a>COleControlSite::m_dwMiscStatus

Denetim hakkında çeşitli bilgiler içerir.

```
DWORD m_dwMiscStatus;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [OLEMISC'ye](/windows/win32/api/oleidl/ne-oleidl-olemisc)bakın.

## <a name="colecontrolsitem_dwpropnotifysink"></a><a name="m_dwpropnotifysink"></a>COleControlSite::m_dwPropNotifySink

[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) çerezini içerir.

```
DWORD m_dwPropNotifySink;
```

## <a name="colecontrolsitem_dwstyle"></a><a name="m_dwstyle"></a>COleControlSite::m_dwStyle

Denetimin Pencere stillerini içerir.

```
DWORD m_dwStyle;
```

## <a name="colecontrolsitem_hwnd"></a><a name="m_hwnd"></a>COleControlSite::m_hWnd

Denetimin HWND'sini veya denetim penceresizse NULL'u içerir.

```
HWND m_hWnd;
```

## <a name="colecontrolsitem_iidevents"></a><a name="m_iidevents"></a>COleControlSite::m_iidEvents

Denetimin varsayılan olay lavabo arabiriminin arabirim kimliğini içerir.

```
IID m_iidEvents;
```

## <a name="colecontrolsitem_nid"></a><a name="m_nid"></a>COleControlSite::m_nID

Denetimin iletişim öğesi kimliğini içerir.

```
UINT m_nID;
```

## <a name="colecontrolsitem_pactiveobject"></a><a name="m_pactiveobject"></a>COleControlSite::m_pActiveObject

Denetimin [IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject) arabirimini içerir.

```
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;
```

## <a name="colecontrolsitem_pctrlcont"></a><a name="m_pctrlcont"></a>COleControlSite::m_pCtrlCont

Denetimin kapsayıcısını (formu temsil eder) içerir.

```
COleControlContainer* m_pCtrlCont;
```

## <a name="colecontrolsitem_pinplaceobject"></a><a name="m_pinplaceobject"></a>COleControlSite::m_pInPlaceObject

Denetimin `IOleInPlaceObject` [IOleInPlaceObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject) arabirimini içerir.

```
LPOLEINPLACEOBJECT m_pInPlaceObject;
```

## <a name="colecontrolsitem_pobject"></a><a name="m_pobject"></a>COleControlSite::m_pObject

Denetimin `IOleObjectInterface` arabirimini içerir.

```
LPOLEOBJECT m_pObject;
```

## <a name="colecontrolsitem_pwindowlessobject"></a><a name="m_pwindowlessobject"></a>COleControlSite::m_pWindowlessObject

Denetimin `IOleInPlaceObjectWindowless` [IOleInPlaceObjectWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) arabirimini içerir.

```
IOleInPlaceObjectWindowless* m_pWindowlessObject;
```

## <a name="colecontrolsitem_pwndctrl"></a><a name="m_pwndctrl"></a>COleControlSite::m_pWndCtrl

Denetimin `CWnd` kendisini temsil eden nesneye bir işaretçi içerir.

```
CWnd* m_pWndCtrl;
```

## <a name="colecontrolsitem_rect"></a><a name="m_rect"></a>COleControlSite::m_rect

Kapsayıcının penceresine göre denetimin sınırlarını içerir.

```
CRect m_rect;
```

## <a name="colecontrolsitemodifystyle"></a><a name="modifystyle"></a>COleControlSite::ModifyStyle

Denetimin stillerini değiştirir.

```
virtual BOOL ModifyStyle(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*dwRemove*<br/>
Geçerli pencere stillerinden kaldırılacak stiller.

*dwEkle*<br/>
Geçerli pencere stillerinden eklenecek stiller.

*Nflags*<br/>
Pencere konumlandırma bayrakları. Olası değerlerin listesi için Windows SDK'daki [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) işlevine bakın.

### <a name="return-value"></a>Dönüş Değeri

Stiller değiştirilirse sıfır yok, aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Denetimin stok Etkin özelliği, WS_DISABLED ayarına uyacak şekilde değiştirilir. Denetimin stok Border Style özelliği, WS_BORDER için istenen ayarın eşleşecek şekilde değiştirilir. Varsa, diğer tüm stiller doğrudan denetimin pencere koluna uygulanır.

Denetimin pencere stillerini değiştirir. Eklenecek veya çıkarılacak stiller bitwise OR ( &#124; ) işleci kullanılarak birleştirilebilir. Kullanılabilir pencere stilleri hakkında bilgi için Windows SDK'daki [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) işlevine bakın.

*nFlags* sıfır değilse, `ModifyStyle` Win32 işlevini `SetWindowPos`çağırır ve *nFlags'i* aşağıdaki dört bayrakla birleştirerek pencereyi yeniden çizer:

- SWP_NOSIZE Geçerli boyutu korur.

- SWP_NOMOVE Geçerli konumunu korur.

- SWP_NOZORDER Geçerli Z sırasını korur.

- SWP_NOACTIVATE Pencereyi etkinleştirmez.

Bir pencerenin genişletilmiş stillerini değiştirmek için [ModifyStyleEx'i](#modifystyleex)arayın.

## <a name="colecontrolsitemodifystyleex"></a><a name="modifystyleex"></a>COleControlSite::ModifyStyleEx

Denetimin genişletilmiş stillerini değiştirir.

```
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*dwRemove*<br/>
Genişletilmiş stilleri geçerli pencere stilleri kaldırılacak.

*dwEkle*<br/>
Geçerli pencere stillerinden eklenecek genişletilmiş stiller.

*Nflags*<br/>
Pencere konumlandırma bayrakları. Olası değerlerin listesi için Windows SDK'daki [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) işlevine bakın.

### <a name="return-value"></a>Dönüş Değeri

Stiller değiştirilirse sıfır yok, aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Denetimin stok Görünümü özelliği, WS_EX_CLIENTEDGE ayarına uyacak şekilde değiştirilir. Diğer tüm genişletilmiş pencere stilleri, varsa doğrudan denetimin pencere koluna uygulanır.

Denetim sitesi nesnesinin genişletilmiş stillerini değiştirir. Eklenecek veya çıkarılacak stiller bitwise OR ( &#124; ) işleci kullanılarak birleştirilebilir. Kullanılabilir pencere stilleri hakkında bilgi için Windows SDK'daki [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) işlevine bakın.

*nFlags* sıfır değilse, `ModifyStyleEx` Win32 işlevini `SetWindowPos`çağırır ve *nFlags'i* aşağıdaki dört bayrakla birleştirerek pencereyi yeniden çizer:

- SWP_NOSIZE Geçerli boyutu korur.

- SWP_NOMOVE Geçerli konumunu korur.

- SWP_NOZORDER Geçerli Z sırasını korur.

- SWP_NOACTIVATE Pencereyi etkinleştirmez.

Pencerenin genişletilmiş stillerini değiştirmek için [ModifyStyle'ı](#modifystyle)arayın.

## <a name="colecontrolsitemovewindow"></a><a name="movewindow"></a>COleControlSite::MoveWindow

Denetimin konumunu değiştirir.

```
virtual void MoveWindow(
    int x,
    int y,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Pencerenin sol tarafının yeni konumu.

*Y*<br/>
Pencerenin üst kısmındaki yeni konum.

*Nwidth*<br/>
Pencerenin yeni genişliği

*Nheight*<br/>
Pencerenin yeni yüksekliği.

## <a name="colecontrolsitequickactivate"></a><a name="quickactivate"></a>COleControlSite::QuickActivate

Hızlı, içerdiği denetimi etkinleştirir.

```
virtual BOOL QuickActivate();
```

### <a name="return-value"></a>Dönüş Değeri

Kontrol alanı etkinleştirildiyse sıfır yok, aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu işlev, yalnızca kullanıcı denetimin oluşturma işlemini geçersiz kılıyorsa çağrılmalıdır.

Hızlı `IPersist*::Load` `IPersist*::InitNew` etkinleştirme gerçekleştikten sonra ve yöntemler çağrılmalıdır. Denetim, hızlı etkinleştirme sırasında konteynerin lavabolarına bağlantılarını kurmalıdır. Ancak, bu bağlantılar çağrılana `IPersist*::Load` `IPersist*::InitNew` kadar canlı değildir.

## <a name="colecontrolsitesafesetproperty"></a><a name="safesetproperty"></a>COleControlSite::SafeSetProperty

*dwDispID*tarafından belirtilen denetim özelliğini ayarlar.

```
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parametreler

*dwDispID*<br/>
Denetimin `IDispatch` arabiriminde bulunan özelliğin veya yöntemin sevk kimliğini ayarlar.

*vtProp*<br/>
Ayarlanacak özellik türünü belirtir. Olası değerler için COleDispatchDriver için Açıklamalar bölümüne [bakın:InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
*vtProp*tarafından belirtilen türün tek bir parametresi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Aksine `SetProperty` `SetPropertyV`ve , bir hata (varolmayan bir özellik ayarlamaya çalışırken gibi) karşılaşılan ise, hiçbir özel durum atılır.

## <a name="colecontrolsitesetdefaultbutton"></a><a name="setdefaultbutton"></a>COleControlSite::SetDefaultButton

Denetimi varsayılan düğme olarak ayarlar.

```cpp
void SetDefaultButton(BOOL bDefault);
```

### <a name="parameters"></a>Parametreler

*bVarsayılan*<br/>
Denetim varsayılan düğme olacaksa sıfırolmayan; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Denetim, OLEMISC_ACTSLIKEBUTTON durum biti ayarlı olmalıdır.

## <a name="colecontrolsitesetdlgctrlid"></a><a name="setdlgctrlid"></a>COleControlSite::SetDlgCtrlID

Denetimin iletişim öğesi tanımlayıcısının değerini değiştirir.

```
virtual int SetDlgCtrlID(int nID);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Yeni tanımlayıcı değeri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, pencerenin önceki iletişim öğesi tanımlayıcısı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

## <a name="colecontrolsitesetfocus"></a><a name="setfocus"></a>COleControlSite::SetFocus

Odak denetime odaklanır.

```
virtual CWnd* SetFocus();
virtual CWnd* SetFocus(LPMSG lpmsg);
```

### <a name="parameters"></a>Parametreler

*lpmsg*<br/>
[MSG yapısına](/windows/win32/api/winuser/ns-winuser-msg)işaretçi. Bu yapı, geçerli denetim `SetFocus` sitesinde bulunan denetim isteğini tetikleyen Windows iletisini içerir.

### <a name="return-value"></a>Dönüş Değeri

Daha önce odaklanmış olan pencereiçin bir işaretçi.

## <a name="colecontrolsitesetproperty"></a><a name="setproperty"></a>COleControlSite::SetProperty

*dwDispID*tarafından belirtilen denetim özelliğini ayarlar.

```
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parametreler

*dwDispID*<br/>
Denetimin `IDispatch` arabiriminde bulunan özelliğin veya yöntemin sevk kimliğini ayarlar.

*vtProp*<br/>
Ayarlanacak özellik türünü belirtir. Olası değerler için COleDispatchDriver için Açıklamalar bölümüne [bakın:InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
*vtProp*tarafından belirtilen türün tek bir parametresi.

### <a name="remarks"></a>Açıklamalar

Bir `SetProperty` hatayla karşılaşırsa, bir özel durum atılır.

Özel durum türü, özelliği veya yöntemi ayarlama girişiminin iade değerine göre belirlenir. İade değeri ise `DISP_E_EXCEPTION`, `COleDispatchExcpetion` a atılır; aksi `COleException`takdirde bir .

## <a name="colecontrolsitesetpropertyv"></a><a name="setpropertyv"></a>COleControlSite::SetPropertyV

*dwDispID*tarafından belirtilen denetim özelliğini ayarlar.

```
virtual void SetPropertyV(
    DISPID dwDispID,
    VARTYPE vtProp,
    va_list argList);
```

### <a name="parameters"></a>Parametreler

*dwDispID*<br/>
Denetimin `IDispatch` arabiriminde bulunan özelliğin veya yöntemin sevk kimliğini ayarlar.

*vtProp*<br/>
Ayarlanacak özellik türünü belirtir. Olası değerler için COleDispatchDriver için Açıklamalar bölümüne [bakın:InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*Arglist*<br/>
Bağımsız değişkenler listesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Çağrılan yöntem veya özellik için ekstra parametreler *arg_list* parametresi kullanılarak geçirilebilir. Bir `SetProperty` hatayla karşılaşırsa, bir özel durum atılır.

Özel durum türü, özelliği veya yöntemi ayarlama girişiminin iade değerine göre belirlenir. İade değeri ise `DISP_E_EXCEPTION`, `COleDispatchExcpetion` a atılır; aksi `COleException`takdirde bir .

## <a name="colecontrolsitesetwindowpos"></a><a name="setwindowpos"></a>COleControlSite::SetWindowPos

Denetim alanının boyutunu, konumunu ve Z sırasını ayarlar.

```
virtual BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,
    int x,
    int y,
    int cx,
    int cy,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*pWndInsertAfter*<br/>
Pencereye bir işaretçi.

*X*<br/>
Pencerenin sol tarafının yeni konumu.

*Y*<br/>
Pencerenin üst kısmındaki yeni konum.

*Cx*<br/>
Pencerenin yeni genişliği

*Cy*<br/>
Pencerenin yeni yüksekliği.

*Nflags*<br/>
Pencere boyutlandırma ve konumlandırma bayraklarını belirtir. Olası değerler için Windows SDK'daki [SetWindowPos'un](/windows/win32/api/winuser/nf-winuser-setwindowpos) Açıklamalar bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Sıfır sızı eğer başarılıysa, aksi takdirde sıfır.

## <a name="colecontrolsitesetwindowtext"></a><a name="setwindowtext"></a>COleControlSite::SetWindowText

Denetim sitesi için metni ayarlar.

```
virtual void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*lpszString*<br/>
Yeni başlık veya denetim metni olarak kullanılmak üzere null-sonlandırılan dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu işlev ilk olarak Resim Yazısı stok özelliğini ayarlamaya çalışır. Resim Yazısı stok özelliği desteklenmezse, Metin özelliği bunun yerine ayarlanır.

## <a name="colecontrolsiteshowwindow"></a><a name="showwindow"></a>COleControlSite::ShowWindow

Pencerenin gösteri durumunu ayarlar.

```
virtual BOOL ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>Parametreler

*nCmdShow*<br/>
Denetim alanının nasıl gösterilebildiğini belirtir. Aşağıdaki değerlerden biri olmalıdır:

- SW_HIDE Bu pencereyi gizler ve etkinleştirme yi başka bir pencereye geçirir.

- SW_MINIMIZE Pencereyi en aza indirir ve sistem listesindeki üst düzey pencereyi etkinleştirir.

- SW_RESTORE Pencereyi etkinleştirir ve görüntüler. Pencere en aza indirgendiyse veya en üst düzeye çıkarılırsa, Windows pencereyi özgün boyutuna ve konumuna geri yükler.

- SW_SHOW Pencereyi etkinleştirir ve geçerli boyutu ve konumunda görüntüler.

- SW_SHOWMAXIMIZED Pencereyi etkinleştirir ve en üst düzeybir pencere olarak görüntüler.

- SW_SHOWMINIMIZED Pencereyi etkinleştirir ve simge olarak görüntüler.

- SW_SHOWMINNOACTIVE Pencereyi simge olarak görüntüler. Şu anda etkin olan pencere etkin kalır.

- SW_SHOWNA Pencereyi geçerli durumunda görüntüler. Şu anda etkin olan pencere etkin kalır.

- SW_SHOWNOACTIVATE Pencereyi en son boyutu ve konumunda görüntüler. Şu anda etkin olan pencere etkin kalır.

- SW_SHOWNORMAL Pencereyi etkinleştirir ve görüntüler. Pencere en aza indirgendiyse veya en üst düzeye çıkarılırsa, Windows pencereyi özgün boyutuna ve konumuna geri yükler.

### <a name="return-value"></a>Dönüş Değeri

Pencere daha önce görünürse sıfırolmayan; Pencere daha önce gizlenmişse 0.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleControlContainer Sınıfı](../../mfc/reference/colecontrolcontainer-class.md)
