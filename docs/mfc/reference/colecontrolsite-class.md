---
title: Cotacontrolsite sınıfı
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
ms.openlocfilehash: 9b9b68a001acdf4b08d9cfc01cc67c43217d9a57
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504310"
---
# <a name="colecontrolsite-class"></a>Cotacontrolsite sınıfı

Özel istemci tarafı denetim arabirimleri için destek sağlar.

## <a name="syntax"></a>Sözdizimi

```
class COleControlSite : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleControlSite::COleControlSite](#colecontrolsite)|Bir `COleControlSite` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Coincontrolsıte:: BindDefaultProperty](#binddefaultproperty)|Barındırılan denetimin varsayılan özelliğini bir veri kaynağına bağlar.|
|[Coincontrolsıte:: BindProperty](#bindproperty)|Barındırılan denetimin bir özelliğini bir veri kaynağına bağlar.|
|[COleControlSite::CreateControl](#createcontrol)|Barındırılan bir ActiveX denetimi oluşturur.|
|[COleControlSite::DestroyControl](#destroycontrol)|Barındırılan denetimi yok eder.|
|[COleControlSite::DoVerb](#doverb)|Barındırılan denetimin belirli bir fiilini yürütür.|
|[Copacontrolsıte:: EnableDSC](#enabledsc)|Bir denetim sitesi için veri kaynağını belirleme imkanı sunar.|
|[Copacontrolsıte:: EnableWindow](#enablewindow)|Denetim sitesini etkinleştirilir.|
|[Copacontrolsıte:: FreezeEvents](#freezeevents)|Denetim sitesinin olayları kabul ettiğini belirtir.|
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|Barındırılan denetim için varsayılan düğme kodunu alır.|
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|Denetimin tanımlayıcısını alır.|
|[COleControlSite::GetEventIID](#geteventiid)|Barındırılan denetim için bir olay arabiriminin KIMLIĞINI alır.|
|[COleControlSite::GetExStyle](#getexstyle)|Denetim sitesinin genişletilmiş stillerini alır.|
|[COleControlSite::GetProperty](#getproperty)|Barındırılan denetimin belirli bir özelliğini alır.|
|[COleControlSite::GetStyle](#getstyle)|Denetim sitesinin stillerini alır.|
|[COleControlSite::GetWindowText](#getwindowtext)|Barındırılan denetimin metnini alır.|
|[Copacontrolsıte:: InvokeHelper](#invokehelper)|Barındırılan denetimin belirli bir yöntemini çağırın.|
|[Copercontrolsite:: InvokeHelperV](#invokehelperv)|Barındırılan denetimin belirli bir yöntemini bir bağımsız değişken listesi ile çağırma.|
|[Coincontrolsıte:: IsDefaultButton](#isdefaultbutton)|Denetimin pencerede varsayılan düğme olup olmadığını belirler.|
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|Denetim sitesinin görünür durumunu denetler.|
|[COleControlSite::ModifyStyle](#modifystyle)|Denetim sitesinin geçerli genişletilmiş stillerini değiştirir.|
|[COleControlSite::ModifyStyleEx](#modifystyleex)|Denetim sitesinin geçerli stillerini değiştirir.|
|[Copacontrolsıte:: MoveWindow](#movewindow)|Denetim sitesinin konumunu değiştirir.|
|[COleControlSite::QuickActivate](#quickactivate)|Barındırılan denetimi hızlı etkinleştirir.|
|[COleControlSite::SafeSetProperty](#safesetproperty)|Özel durum oluşturma şansı olmadan denetimin bir özelliğini veya yöntemini ayarlar.|
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|Penceredeki varsayılan düğmeyi ayarlar.|
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|Denetimin tanımlayıcısını alır.|
|[Coincontrolsıte:: SetFocus](#setfocus)|Odağı denetim sitesine ayarlar.|
|[Copacontrolsıte:: SetProperty](#setproperty)|Barındırılan denetimin belirli bir özelliğini ayarlar.|
|[COleControlSite::SetPropertyV](#setpropertyv)|Barındırılan denetimin belirli bir özelliğini bir bağımsız değişken listesi ile ayarlar.|
|[COleControlSite::SetWindowPos](#setwindowpos)|Denetim sitesinin konumunu ayarlar.|
|[COleControlSite::SetWindowText](#setwindowtext)|Barındırılan denetimin metnini ayarlar.|
|[Copacontrolsıte:: ShowWindow](#showwindow)|Denetim sitesini gösterir veya gizler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleControlSite::GetControlInfo](#getcontrolinfo)|Barındırılan denetim için klavye bilgilerini ve anımsatıcıları alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|Barındırılan denetimin penceresiz bir denetim olup olmadığını belirler.|
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|Denetim için klavye işleme hakkında bilgi içerir.|
|[COleControlSite::m_dwEventSink](#m_dweventsink)|Denetimin bağlantı noktasının tanımlama bilgisi.|
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|Barındırılan denetimin çeşitli durumları.|
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|Denetimin `IPropertyNotifySink` tanımlama bilgisi.|
|[COleControlSite::m_dwStyle](#m_dwstyle)|Barındırılan denetimin stilleri.|
|[COleControlSite::m_hWnd](#m_hwnd)|Denetim sitesinin tanıtıcısı.|
|[COleControlSite::m_iidEvents](#m_iidevents)|Barındırılan denetim için olay arabiriminin KIMLIĞI.|
|[COleControlSite::m_nID](#m_nid)|Barındırılan denetimin KIMLIĞI.|
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|Barındırılan denetimin `IOleInPlaceActiveObject` nesnesine yönelik bir işaretçi.|
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|Barındırılan denetimin kapsayıcısı.|
|[Coincontrolsite:: m_pInPlaceObject](#m_pinplaceobject)|Barındırılan denetimin `IOleInPlaceObject` nesnesine yönelik bir işaretçi.|
|[COleControlSite::m_pObject](#m_pobject)|Denetimin `IOleObjectInterface` arabirimine yönelik bir işaretçi.|
|[Coincontrolsite:: m_pWindowlessObject](#m_pwindowlessobject)|Denetimin `IOleInPlaceObjectWindowless` arabirimine yönelik bir işaretçi.|
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|Barındırılan denetim için pencere nesnesine yönelik bir işaretçi.|
|[COleControlSite::m_rect](#m_rect)|Denetim sitesinin boyutları.|

## <a name="remarks"></a>Açıklamalar

Bu destek, katıştırılmış bir ActiveX denetiminin konum ve kapsamı hakkında bilgileri, bilinen adı, Kullanıcı arabirimi, ortam özellikleri ve kapsayıcısı tarafından belirtilen diğer kaynakları hakkında bilgi elde eden başlıca bir araçtır. `COleControlSite`[IOleControlSite](/windows/win32/api/ocidl/nn-ocidl-iolecontrolsite), [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [IOleClientSite](/windows/win32/api/oleidl/nn-oleidl-ioleclientsite), [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink), `IBoundObjectSite`, `INotifyDBEvents`, [IRowsetNotify](../../data/oledb/irowsetnotifyimpl-class.md) arabirimlerini tamamen uygular. Ayrıca, IDispatch arabirimi (çevresel özellikler ve olay havuzları için destek sağlama) de uygulanır.

Kullanarak `COleControlSite`bir ActiveX Denetim sitesi oluşturmak için, öğesinden `COleControlSite`bir sınıf türetebilirsiniz. Kapsayıcının türetilmiş `CWnd`sınıfınızda (örneğin, iletişim kutusu) `CWnd::CreateControlSite` işlevi geçersiz kılar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlSite`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxocc. h

##  <a name="binddefaultproperty"></a>Coincontrolsıte:: BindDefaultProperty

Nesne kaynağı denetiminin veri kaynağı, Kullanıcı adı, parola ve SQL özellikleri tarafından tanımlanan temel imlecin tür kitaplığı 'nda gösterildiği gibi, çağıran nesnenin varsayılan basit bağlama özelliğini bağlar.

```
virtual void BindDefaultProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    LPCTSTR szFieldName,
    CWnd* pDSCWnd);
```

### <a name="parameters"></a>Parametreler

*Dwdıspıd*<br/>
Bir veri kaynağı denetimine bağlanacak veriye bağlı denetimdeki bir özelliğin DISPID 'sini belirtir.

*vtProp*<br/>
Bağlanacak özelliğin türünü belirtir (örneğin, VT_BSTR, VT_VARIANT vb.).

*szFieldName*<br/>
Özelliğin bağlanacağı veri kaynağı denetimi tarafından belirtilen imlecin bulunduğu sütunun adını belirtir.

*pDSCWnd*<br/>
Özelliğin bağlanacağı veri kaynağı `CWnd`denetimini barındıran, türetilmiş nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu `CWnd` işlevi çağırdığınız nesne, veri bağlantılı bir denetim olmalıdır.

##  <a name="bindproperty"></a>Coincontrolsıte:: BindProperty

Nesne kaynağı denetiminin veri kaynağı, Kullanıcı adı, parola ve SQL özellikleri tarafından tanımlanan temel imlecin tür kitaplığı 'nda işaretlenmiş olarak, çağıran nesnenin basit bağlı özelliğini bağlar.

```
virtual void BindProperty(
    DISPID dwDispId,
    CWnd* pWndDSC);
```

### <a name="parameters"></a>Parametreler

*dwDispId*<br/>
Bir veri kaynağı denetimine bağlanacak veriye bağlı denetimdeki bir özelliğin DISPID 'sini belirtir.

*pWndDSC*<br/>
Özelliğin bağlanacağı veri kaynağı `CWnd`denetimini barındıran, türetilmiş nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu `CWnd` işlevi çağırdığınız nesne, veri bağlantılı bir denetim olmalıdır.

##  <a name="colecontrolsite"></a>  COleControlSite::COleControlSite

Yeni `COleControlSite` bir nesne oluşturur.

```
explicit COleControlSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>Parametreler

*pCtrlCont*<br/>
Denetimin kapsayıcısına (AtiveX denetimini barındıran pencereyi temsil eden) yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev [COccManager:: CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer) işlevi tarafından çağırılır. Kapsayıcıların oluşturulmasını özelleştirme hakkında daha fazla bilgi için bkz. [COccManager:: CreateSite](../../mfc/reference/coccmanager-class.md#createsite).

##  <a name="createcontrol"></a>Copacontrolsıte:: CreateControl

`COleControlSite` Nesnesi tarafından barındırılan bir ActiveX denetimi oluşturur.

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
Denetimi temsil eden pencere nesnesine yönelik bir işaretçi.

*in*<br/>
Denetimin benzersiz sınıf KIMLIĞI.

*lpszWindowName*<br/>
Denetimde gösterilecek metne yönelik bir işaretçi. Winodw 'ın başlık veya metin özelliğinin değerini (varsa) ayarlar.

*dwStyle*<br/>
Windows stilleri. Kullanılabilir stiller, **açıklamalar** bölümü altında listelenmiştir.

*Rect*<br/>
Denetimin boyutunu ve konumunu belirtir. Bir `CRect` nesne`RECT` ya da yapı olabilir.

*NID*<br/>
Denetimin alt pencere KIMLIĞINI belirtir.

*pPersist*<br/>
Denetimin kalıcı durumunu içeren `CFile` bir işaretçisi. Varsayılan değer NULL ' dir ve bu, denetimin kendisini kalıcı depolamadan geri yüklemeden önce başlatıldığını belirtir. NULL değilse, denetimin kalıcı verilerini içeren, bir akış veya `CFile`depolama biçiminde bir türetilmiş nesnenin işaretçisi olması gerekir. Bu veriler, istemcinin önceki bir etkinleştirmesine kaydedilmiş olabilir. Diğer verileri içerebilir, ancak `CreateControl`arama sırasında okuma-yazma işaretçisinin kalıcı verilerin ilk baytına ayarlanmış olması gerekir. `CFile`

*bStorage*<br/>
*PPersist* 'teki verilerin veya `IStorage` `IStream` veri olarak yorumlanıp yorumlanmayacağını gösterir. *PPersist* 'teki veriler bir depolama Ise, *bStorage* doğru olmalıdır. *PPersist* 'teki veriler bir Stream Ise *bStorage* yanlış olmalıdır. Varsayılan değer FALSE 'dur.

*bstrLicKey*<br/>
İsteğe bağlı lisans anahtarı verileri. Bu veriler yalnızca bir çalışma zamanı lisans anahtarı gerektiren denetimler oluşturmak için gereklidir. Denetim lisanslamayı destekliyorsa, denetimin başarılı olması için bir lisans anahtarı sağlamanız gerekir. Varsayılan değer NULL.

*PPT*<br/>
Denetimin sol üst köşesini `POINT` içeren bir yapıya yönelik işaretçi. Denetimin boyutu *psize*değerine göre belirlenir. *PPT* ve *pboyut* değerleri, denetimin boyutunu ve konumunu belirten isteğe bağlı bir yöntemdir.

*psıze*<br/>
Denetimin boyutunu içeren bir `SIZE` yapıya yönelik işaretçi. Sol üst köşe, *PPT*'nin değerine göre belirlenir. *PPT* ve *pboyut* değerleri, denetimin boyutunu ve konumunu belirten isteğe bağlı bir yöntemdir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Yalnızca Windows *dwStyle* bayraklarının bir alt kümesi tarafından `CreateControl`desteklenir:

- WS_VISIBLE Başlangıçta görünür olan bir pencere oluşturur. Denetimin normal pencereler gibi hemen görünür olmasını istiyorsanız gereklidir.

- WS_DISABLED başlangıçta devre dışı bırakılmış bir pencere oluşturur. Devre dışı bırakılan bir pencere kullanıcıdan giriş alamaz. Denetimin etkin bir özelliği varsa, ayarlanabilir.

- WS_BORDER ince çizgili kenarlığı olan bir pencere oluşturur. Denetimin bir BorderStyle özelliği varsa, ayarlanabilir.

- WS_GROUP bir denetim grubunun ilk denetimini belirtir. Kullanıcı, yön tuşlarını kullanarak, klavye odağını gruptaki bir denetimden bir sonrakine değiştirebilir. İlk denetimden sonra WS_GROUP stiliyle tanımlanan tüm denetimler aynı gruba aittir. WS_GROUP stilinde bir sonraki denetim, grubu sonlandırır ve sonraki grubu başlatır.

- WS_TABSTOP, Kullanıcı TAB tuşuna bastığında klavye odağını alabilen bir denetim belirtir. Sekme tuşuna basıldığında klavye odağı WS_TABSTOP stilinin bir sonraki denetimine değişir.

Varsayılan boyutlu denetimleri oluşturmak için ikinci aşırı yüklemeyi kullanın.

##  <a name="destroycontrol"></a>  COleControlSite::DestroyControl

`COleControlSite` Nesneyi yok eder.

```
virtual BOOL DestroyControl();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Tamamlandıktan sonra nesne bellekten serbest bırakılır ve nesne işaretçileri artık geçerli değildir.

##  <a name="doverb"></a>  COleControlSite::DoVerb

Belirtilen fiil yürütülür.

```
virtual HRESULT DoVerb(
    LONG nVerb,
    LPMSG lpMsg = NULL);
```

### <a name="parameters"></a>Parametreler

*Nfiil*<br/>
Yürütülecek fiili belirtir. Aşağıdakilerden birini içerebilir:

|Değer|Açıklama|Sembol|
|-----------|-------------|------------|
|0|Birincil fiil|OLEIVERB_PRIMARY|
|-1|İkincil fiil|Seçim|
|1\.|Düzenlenecek nesneyi görüntüler.|OLEIVERB_SHOW|
|-2|Öğeyi ayrı bir pencerede düzenler.|OLEIVERB_OPEN|
|-3|Nesneyi gizler.|OLEIVERB_HIDE|
|-4|Bir denetimi yerinde etkinleştirir.|OLEIVERB_UIACTIVATE|
|-5|Ek kullanıcı arabirimi öğeleri olmadan bir denetimi yerinde etkinleştirir.|OLEIVERB_INPLACEACTIVATE|
|-7|Denetimin özelliklerini görüntüleyin.|OLEIVERB_PROPERTIES|

*lpMsg*<br/>
Öğenin etkinleştirilmesini neden olan iletinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, belirtilen fiili yürütmek için denetimin `IOleObject` arabiriminden doğrudan çağırır. Bu işlev çağrısının bir sonucu olarak bir özel durum oluşturulursa, HRESULT hata kodu döndürülür.

Daha fazla bilgi için bkz. [IOleObject::D oVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK.

##  <a name="enabledsc"></a>Copacontrolsıte:: EnableDSC

Denetim sitesi için veri kaynağını belirleme imkanı sunar.

```
virtual void EnableDSC();
```

### <a name="remarks"></a>Açıklamalar

Denetim sitesi için veri kaynağını etkinleştirmek ve başlatmak üzere Framework tarafından çağırılır. Özelleştirilmiş davranış sağlamak için bu işlevi geçersiz kılın.

##  <a name="enablewindow"></a>Copacontrolsıte:: EnableWindow

Denetim sitesine fare ve klavye girişini sağlar veya devre dışı bırakır.

```
virtual BOOL EnableWindow(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
Pencerenin etkinleştirilip etkinleştirilmeyeceğini veya devre dışı bırakılacağını belirtir: Pencere girişinin etkinleştirilmesi durumunda TRUE, aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Pencere önceden devre dışı bırakılmışsa sıfır dışında 0.

##  <a name="freezeevents"></a>Copacontrolsıte:: FreezeEvents

Denetim sitesinin bir denetimden tetiklenen olayları işlemesini veya yoksaymasını belirtir.

```
void FreezeEvents(BOOL bFreeze);
```

### <a name="parameters"></a>Parametreler

*bFreeze*<br/>
Denetim sitesinin olayları kabul etmeyi durdurmasını isteyip istemediğinizi belirtir. Denetim olayları kabul etmediğinden sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

*BFreeze* değeri true ise, Denetim sitesi, Fring olaylarını durdurmak için denetimi ister. *BFreeze* yanlış ise, Denetim sitesi olayları tetiketmeye devam etmek için denetimi ister.

> [!NOTE]
>  Denetim sitesi tarafından istenirse, denetimin olayları tetikdurdurulması için denetim gerekli değildir. Çalışmaya devam edebilir, ancak sonraki tüm olaylar Denetim sitesi tarafından yok sayılır.

##  <a name="getcontrolinfo"></a>Coincontrolsite:: Getcontrolinınfo

Bir denetimin klavye anımsatıcıları ve klavye davranışı hakkında bilgi alır.

```
void GetControlInfo();
```

### <a name="remarks"></a>Açıklamalar

Bilgiler [Copacontrolsite:: m_ctlInfo](#m_ctlinfo)içinde depolanır.

##  <a name="getdefbtncode"></a>Coincontrolsıte:: GetDefBtnCode

Denetimin varsayılan bir gönderme düğmesi olup olmadığını belirler.

```
DWORD GetDefBtnCode();
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri olabilir:

- DLGC_DEFPUSHBUTTON denetimi, iletişim kutusunda varsayılan düğmedir.

- DLGC_UNDEFPUSHBUTTON denetimi, iletişim kutusunda varsayılan düğme değildir.

- **0** denetimi bir düğme değildir.

##  <a name="getdlgctrlid"></a>Coincontrolsıte:: Getdlctrlıd

Denetimin tanımlayıcısını alır.

```
virtual int GetDlgCtrlID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin iletişim kutusu öğesi tanımlayıcısı.

##  <a name="geteventiid"></a>  COleControlSite::GetEventIID

Denetimin varsayılan olay arabirimine bir işaretçi alır.

```
BOOL GetEventIID(IID* piid);
```

### <a name="parameters"></a>Parametreler

*piıd*<br/>
Arabirim KIMLIĞINE yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı, aksi durumda 0. Başarılı olursa, *pIID* denetimin varsayılan olay arabirimi IÇIN arabirim kimliğini içerir.

##  <a name="getexstyle"></a>Copacontrolsıte:: GetExStyle

Pencerenin genişletilmiş stillerini alır.

```
virtual DWORD GetExStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim penceresinin Genişletilmiş stilleri.

### <a name="remarks"></a>Açıklamalar

Normal stilleri almak için [Cotacontrolsıte:: GetStyle](#getstyle)öğesini çağırın.

##  <a name="getproperty"></a>Coincontrolsıte:: GetProperty

*Dwdıspıd*tarafından belirtilen denetim özelliğini alır.

```
virtual void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>Parametreler

*Dwdıspıd*<br/>
Denetimin varsayılan `IDispatch` arabiriminde alınacak olan özelliğin dağıtım kimliğini tanımlar.

*vtProp*<br/>
Alınacak özelliğin türünü belirtir. Olası değerler için [Cotadispatchdriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)için açıklamalar bölümüne bakın.

*pvProp*<br/>
Özellik değerini alacak değişkenin adresi. Bu, *vtProp*tarafından belirtilen türle eşleşmelidir.

### <a name="remarks"></a>Açıklamalar

Değer, *pvProp*ile döndürülür.

##  <a name="getstyle"></a>  COleControlSite::GetStyle

Denetim sitesinin stillerini alır.

```
virtual DWORD GetStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pencerenin stilleri.

### <a name="remarks"></a>Açıklamalar

Olası değerler listesi için bkz. [Windows stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles). Denetim sitesinin genişletilmiş stillerini almak için [Cotacontrolsıte:: GetExStyle](#getexstyle)öğesini çağırın.

##  <a name="getwindowtext"></a>Coincontrolsıte:: GetWindowText

Denetimin geçerli metnini alır.

```
virtual void GetWindowText(CString& str) const;
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Denetimin geçerli metnini içeren `CString` bir nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Denetim, başlık stoğu özelliğini destekliyorsa bu değer döndürülür. Caption Stock özelliği desteklenmiyorsa, Text özelliğinin değeri döndürülür.

##  <a name="invokehelper"></a>Copacontrolsıte:: InvokeHelper

*WFlags*tarafından belirtilen bağlamda *dwdıspıd*tarafından belirtilen yöntemi veya özelliği çağırır.

```
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>Parametreler

*Dwdıspıd*<br/>
Çağrılacak olan özelliğin veya yöntemin dağıtım kimliğini belirtir, denetimin `IDispatch` arabiriminde çağrılır.

*wFlags*<br/>
IDispatch:: Invoke çağrısının bağlamını açıklayan bayraklar. Olası *wFlags* değerleri için Windows SDK bakın `IDispatch::Invoke` .

*Sanal tret*<br/>
Dönüş değerinin türünü belirtir. Olası değerler için [Cotadispatchdriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)için açıklamalar bölümüne bakın.

*pvRet*<br/>
Özellik değeri veya dönüş değeri alacak değişkenin adresi. *VtRet*tarafından belirtilen türle eşleşmesi gerekir.

*Pbparaınfo*<br/>
*Pbparaınfo*'dan sonraki parametrelerin türlerini belirten, null ile sonlandırılmış bir bayt dizesi işaretçisi. Olası değerler için [Cotadispatchdriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)için açıklamalar bölümüne bakın.

*...*<br/>
*Pbparaınfo*içinde belirtilen türlerin değişken listesi.

### <a name="remarks"></a>Açıklamalar

*Pbparaınfo* parametresi, yönteme veya özelliğe geçirilen parametrelerin türlerini belirtir. Bağımsız değişkenlerin değişken listesi tarafından temsil edilir... sözdizimi bildiriminde.

Bu işlev, parametreleri VARIANTARG değerlerine dönüştürür ve sonra denetimde `IDispatch::Invoke` yöntemi çağırır. Çağrısı `IDispatch::Invoke` başarısız olursa, bu işlev bir özel durum oluşturur. Tarafından `IDispatch::Invoke` `COleDispatchException` `COleException`döndürülen durum kodu ise, bu işlev bir nesnesi atar, aksi takdirde bir oluşturur. `DISP_E_EXCEPTION`

##  <a name="invokehelperv"></a>Copercontrolsite:: InvokeHelperV

*WFlags*tarafından belirtilen bağlamda *dwdıspıd*tarafından belirtilen yöntemi veya özelliği çağırır.

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

*Dwdıspıd*<br/>
Çağrılacak olan özelliğin veya yöntemin dağıtım kimliğini belirtir, denetimin `IDispatch` arabiriminde çağrılır.

*wFlags*<br/>
IDispatch:: Invoke çağrısının bağlamını açıklayan bayraklar.

*Sanal tret*<br/>
Dönüş değerinin türünü belirtir. Olası değerler için [Cotadispatchdriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)için açıklamalar bölümüne bakın.

*pvRet*<br/>
Özellik değeri veya dönüş değeri alacak değişkenin adresi. *VtRet*tarafından belirtilen türle eşleşmesi gerekir.

*Pbparaınfo*<br/>
*Pbparaınfo*'dan sonraki parametrelerin türlerini belirten, null ile sonlandırılmış bir bayt dizesi işaretçisi. Olası değerler için [Cotadispatchdriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)için açıklamalar bölümüne bakın.

*argList*<br/>
Değişken bağımsız değişken listesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

*Pbparaınfo* parametresi, yönteme veya özelliğe geçirilen parametrelerin türlerini belirtir. Çağrılan yöntem veya özellik için ek parametreler *va_list* parametresi kullanılarak geçirilebilir.

Genellikle, bu işlev tarafından `COleControlSite::InvokeHelper`çağırılır.

##  <a name="isdefaultbutton"></a>Coincontrolsıte:: IsDefaultButton

Denetimin varsayılan düğme olup olmadığını belirler.

```
BOOL IsDefaultButton();
```

### <a name="return-value"></a>Dönüş Değeri

Denetim pencerede varsayılan düğme ise sıfır dışında bir değer.

##  <a name="iswindowenabled"></a>Copacontrolsıte:: IsWindowEnabled

Denetim sitesinin etkinleştirilip etkinleştirilmediğini belirler.

```
virtual BOOL IsWindowEnabled() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim etkinse sıfır sıfır, değilse sıfır.

### <a name="remarks"></a>Açıklamalar

Değer, denetimin etkin stok özelliğinden alınır.

##  <a name="m_biswindowless"></a>  COleControlSite::m_bIsWindowless

Nesnenin penceresiz bir denetim olup olmadığını belirler.

```
BOOL m_bIsWindowless;
```

### <a name="remarks"></a>Açıklamalar

Denetimde pencere yoksa sıfır dışında bir, değilse sıfır.

##  <a name="m_ctlinfo"></a>Coincontrolsite:: m_ctlInfo

Klavye girişinin denetim tarafından nasıl işlendiği hakkında bilgi.

```
CONTROLINFO m_ctlInfo;
```

### <a name="remarks"></a>Açıklamalar

Bu bilgiler bir [Controlinınfo](/windows/win32/api/ocidl/ns-ocidl-controlinfo) yapısında saklanır.

##  <a name="m_dweventsink"></a>  COleControlSite::m_dwEventSink

Denetimin olay havuzundan bağlantı noktasının tanımlama bilgisini içerir.

```
DWORD m_dwEventSink;
```

##  <a name="m_dwmiscstatus"></a>Coincontrolsite:: m_dwMiscStatus

Denetimle ilgili çeşitli bilgileri içerir.

```
DWORD m_dwMiscStatus;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [Olemisc](/windows/win32/api/oleidl/ne-oleidl-olemisc)bölümüne bakın.

##  <a name="m_dwpropnotifysink"></a>  COleControlSite::m_dwPropNotifySink

[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) tanımlama bilgisini içerir.

```
DWORD m_dwPropNotifySink;
```

##  <a name="m_dwstyle"></a>Coincontrolsite:: m_dwStyle

Denetimin pencere stillerini içerir.

```
DWORD m_dwStyle;
```

##  <a name="m_hwnd"></a>Coincontrolsite:: m_hWnd

Denetimin HWND 'sini veya denetim penceresiz ise NULL değerini içerir.

```
HWND m_hWnd;
```

##  <a name="m_iidevents"></a>Coincontrolsite:: m_iidEvents

Denetimin varsayılan olay havuzu arabiriminin arabirim KIMLIĞINI içerir.

```
IID m_iidEvents;
```

##  <a name="m_nid"></a>  COleControlSite::m_nID

Denetimin iletişim kutusu öğe KIMLIĞINI içerir.

```
UINT m_nID;
```

##  <a name="m_pactiveobject"></a>Coincontrolsite:: m_pActiveObject

Denetimin [IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject) arabirimini içerir.

```
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;
```

##  <a name="m_pctrlcont"></a>  COleControlSite::m_pCtrlCont

Denetimin kapsayıcısını (formunu temsil eder) içerir.

```
COleControlContainer* m_pCtrlCont;
```

##  <a name="m_pinplaceobject"></a>Coincontrolsite:: m_pInPlaceObject

Denetimin IOleInPlaceObject arabirimini içerir. [](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject) `IOleInPlaceObject`

```
LPOLEINPLACEOBJECT m_pInPlaceObject;
```

##  <a name="m_pobject"></a>  COleControlSite::m_pObject

`IOleObjectInterface` Denetimin arabirimini içerir.

```
LPOLEOBJECT m_pObject;
```

##  <a name="m_pwindowlessobject"></a>Coincontrolsite:: m_pWindowlessObject

Denetimin ıoleınplaceobjectpenceresiz arabirimini içerir. [](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) `IOleInPlaceObjectWindowless`

```
IOleInPlaceObjectWindowless* m_pWindowlessObject;
```

##  <a name="m_pwndctrl"></a>Coincontrolsite:: m_pWndCtrl

Denetimin kendisini temsil eden `CWnd` nesneye yönelik bir işaretçi içerir.

```
CWnd* m_pWndCtrl;
```

##  <a name="m_rect"></a>Coincontrolsite:: m_rect

Kapsayıcının penceresine göre denetimin sınırlarını içerir.

```
CRect m_rect;
```

##  <a name="modifystyle"></a>  COleControlSite::ModifyStyle

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

*dwAdd*<br/>
Geçerli pencere stillerinden eklenecek stiller.

*nFlags*<br/>
Pencere konumlandırma bayrakları. Olası değerler listesi için Windows SDK [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) işlevine bakın.

### <a name="return-value"></a>Dönüş Değeri

Stiller değiştirilirse sıfır dışında sıfır.

### <a name="remarks"></a>Açıklamalar

Denetimin stok etkin özelliği, WS_DISABLED ayarıyla eşleşecek şekilde değiştirilecek. Denetimin hisse senedi kenarlık stili özelliği, WS_BORDER için istenen ayarla eşleşecek şekilde değiştirilecek. Diğer tüm stiller, varsa, denetimin pencere tanıtıcısına doğrudan uygulanır.

Denetimin pencere stillerini değiştirir. Eklenecek veya kaldırılacak stiller bit düzeyinde OR ( &#124; ) işleci kullanılarak birleştirilebilir. Kullanılabilir pencere stilleri hakkında daha fazla bilgi için Windows SDK [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) işlevine bakın.

*NFlags* sıfırdan farklı ise, `ModifyStyle` Win32 işlevini `SetWindowPos`çağırır ve *nFlags* 'i aşağıdaki dört bayraklı birleştirerek pencereyi yeniden çizer:

- SWP_NOSIZE geçerli boyutu korur.

- SWP_NOMOVE geçerli konumu korur.

- SWP_NOZORDER geçerli Z düzenini korur.

- SWP_NOACTIVATE, pencereyi etkinleştirmez.

Pencerenin genişletilmiş stillerini değiştirmek için, [ModifyStyleEx](#modifystyleex)' ı çağırın.

##  <a name="modifystyleex"></a>  COleControlSite::ModifyStyleEx

Denetimin genişletilmiş stillerini değiştirir.

```
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>Parametreler

*dwRemove*<br/>
Geçerli pencere stillerinden kaldırılacak genişletilmiş stiller.

*dwAdd*<br/>
Geçerli pencere stillerinden eklenecek genişletilmiş stiller.

*nFlags*<br/>
Pencere konumlandırma bayrakları. Olası değerler listesi için Windows SDK [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) işlevine bakın.

### <a name="return-value"></a>Dönüş Değeri

Stiller değiştirilirse sıfır dışında sıfır.

### <a name="remarks"></a>Açıklamalar

Denetimin hisse senedi görünümü özelliği, WS_EX_CLIENTEDGE ayarıyla eşleşecek şekilde değiştirilecek. Diğer tüm genişletilmiş pencere stilleri, varsa, denetimin pencere tanıtıcısına doğrudan uygulanır.

Denetim sitesi nesnesinin genişletilmiş stillerini değiştirir. Eklenecek veya kaldırılacak stiller bit düzeyinde OR ( &#124; ) işleci kullanılarak birleştirilebilir. Kullanılabilir pencere stilleri hakkında bilgi edinmek için Windows SDK [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) işlevine bakın.

*NFlags* sıfırdan farklı ise, `ModifyStyleEx` Win32 işlevini `SetWindowPos`çağırır ve *nFlags* 'i aşağıdaki dört bayraklı birleştirerek pencereyi yeniden çizer:

- SWP_NOSIZE geçerli boyutu korur.

- SWP_NOMOVE geçerli konumu korur.

- SWP_NOZORDER geçerli Z düzenini korur.

- SWP_NOACTIVATE, pencereyi etkinleştirmez.

Pencerenin genişletilmiş stillerini değiştirmek için, [ModifyStyle](#modifystyle)' ı çağırın.

##  <a name="movewindow"></a>Copacontrolsıte:: MoveWindow

Denetimin konumunu değiştirir.

```
virtual void MoveWindow(
    int x,
    int y,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Pencerenin sol tarafındaki yeni konum.

*Iz*<br/>
Pencerenin üst öğesinin yeni konumu.

*nWidth*<br/>
Pencerenin yeni genişliği

*nHeight*<br/>
Pencerenin yeni yüksekliği.

##  <a name="quickactivate"></a>Copacontrolsite:: QuickActivate

İçerilen denetimi hızlı etkinleştirir.

```
virtual BOOL QuickActivate();
```

### <a name="return-value"></a>Dönüş Değeri

Denetim sitesi etkinleştirildiyse sıfır dışında sıfır.

### <a name="remarks"></a>Açıklamalar

Bu işlev, yalnızca Kullanıcı denetimin oluşturma işlemini geçersiz kılıyorsa çağrılmalıdır.

`IPersist*::Load` Ve`IPersist*::InitNew` yöntemleri hızlı etkinleştirme oluştuktan sonra çağrılmalıdır. Denetim, hızlı etkinleştirme sırasında kapsayıcının havuzları için bağlantı kurması gerekir. Ancak, bu bağlantılar, veya `IPersist*::Load` `IPersist*::InitNew` çağrılana kadar canlı değildir.

##  <a name="safesetproperty"></a>Copacontrolsite:: SafeSetProperty

*Dwdıspıd*tarafından belirtilen denetim özelliğini ayarlar.

```
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parametreler

*Dwdıspıd*<br/>
Denetimin `IDispatch` arabirimindeki, ayarlanacak özelliğin veya metodun dağıtım kimliğini belirler.

*vtProp*<br/>
Ayarlanacak özelliğin türünü belirtir. Olası değerler için [Cotadispatchdriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)için açıklamalar bölümüne bakın.

*...*<br/>
*VtProp*tarafından belirtilen türde tek bir parametre.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  `SetProperty` Ve`SetPropertyV`' den farklı olarak, bir hatayla karşılaşılırsa (varolmayan bir özelliği ayarlamaya çalışmak gibi), hiçbir özel durum oluşturulmaz.

##  <a name="setdefaultbutton"></a>Coincontrolsıte:: SetDefaultButton

Denetimi varsayılan düğme olarak ayarlar.

```
void SetDefaultButton(BOOL bDefault);
```

### <a name="parameters"></a>Parametreler

*bDefault*<br/>
Denetimin varsayılan düğme olması halinde sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Denetimin OLEMISC_ACTSLIKEBUTTON durum biti ayarlanmış olması gerekir.

##  <a name="setdlgctrlid"></a>Copacontrolsıte:: Setıdctrlıd

Denetimin iletişim kutusu öğesi tanımlayıcısının değerini değiştirir.

```
virtual int SetDlgCtrlID(int nID);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Yeni tanımlayıcı değeri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, pencerenin önceki iletişim kutusu öğe tanımlayıcısı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="setfocus"></a>Coincontrolsıte:: SetFocus

Odağı denetime ayarlar.

```
virtual CWnd* SetFocus();
virtual CWnd* SetFocus(LPMSG lpmsg);
```

### <a name="parameters"></a>Parametreler

*lpMsg*<br/>
Bir [msg yapısına](/windows/win32/api/winuser/ns-winuser-msg)yönelik işaretçi. Bu yapı, geçerli denetim sitesinde bulunan denetim `SetFocus` için isteği tetikleyen Windows iletisini içerir.

### <a name="return-value"></a>Dönüş Değeri

Daha önce odaklanmış pencerenin işaretçisi.

##  <a name="setproperty"></a>Copacontrolsıte:: SetProperty

*Dwdıspıd*tarafından belirtilen denetim özelliğini ayarlar.

```
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Parametreler

*Dwdıspıd*<br/>
Denetimin `IDispatch` arabirimindeki, ayarlanacak özelliğin veya metodun dağıtım kimliğini belirler.

*vtProp*<br/>
Ayarlanacak özelliğin türünü belirtir. Olası değerler için [Cotadispatchdriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)için açıklamalar bölümüne bakın.

*...*<br/>
*VtProp*tarafından belirtilen türde tek bir parametre.

### <a name="remarks"></a>Açıklamalar

Bir `SetProperty` hatayla karşılaşırsa, bir özel durum oluşturulur.

Özel durum türü, özelliği veya yöntemi ayarlama girişiminin dönüş değeri tarafından belirlenir. Dönüş değeri ise `DISP_E_EXCEPTION`, bir `COleDispatchExcpetion` oluşturulur; Aksi halde bir `COleException`.

##  <a name="setpropertyv"></a>COleControlSite:: SetPropertyV

*Dwdıspıd*tarafından belirtilen denetim özelliğini ayarlar.

```
virtual void SetPropertyV(
    DISPID dwDispID,
    VARTYPE vtProp,
    va_list argList);
```

### <a name="parameters"></a>Parametreler

*Dwdıspıd*<br/>
Denetimin `IDispatch` arabirimindeki, ayarlanacak özelliğin veya metodun dağıtım kimliğini belirler.

*vtProp*<br/>
Ayarlanacak özelliğin türünü belirtir. Olası değerler için [Cotadispatchdriver:: InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)için açıklamalar bölümüne bakın.

*argList*<br/>
Bağımsız değişken listesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Çağrılan yöntem veya özellik için ek parametreler *arg_list* parametresi kullanılarak passeed olabilir. Bir `SetProperty` hatayla karşılaşırsa, bir özel durum oluşturulur.

Özel durum türü, özelliği veya yöntemi ayarlama girişiminin dönüş değeri tarafından belirlenir. Dönüş değeri ise `DISP_E_EXCEPTION`, bir `COleDispatchExcpetion` oluşturulur; Aksi halde bir `COleException`.

##  <a name="setwindowpos"></a>  COleControlSite::SetWindowPos

Denetim sitesinin boyutunu, konumunu ve Z sırasını ayarlar.

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
Pencereye yönelik bir işaretçi.

*x*<br/>
Pencerenin sol tarafındaki yeni konum.

*Iz*<br/>
Pencerenin üst öğesinin yeni konumu.

*yazmaç*<br/>
Pencerenin yeni genişliği

*lı*<br/>
Pencerenin yeni yüksekliği.

*nFlags*<br/>
Pencere boyutlandırma ve konumlandırma bayraklarını belirtir. Olası değerler için, Windows SDK [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) için açıklamalar bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır olmayan sıfır.

##  <a name="setwindowtext"></a>Coincontrolsıte:: SetWindowText

Denetim sitesinin metnini ayarlar.

```
virtual void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*lpszString*<br/>
Yeni başlık veya denetim metni olarak kullanılacak, null ile sonlandırılmış bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu işlev ilk olarak başlık stoğu özelliğini ayarlamaya çalışır. Caption Stock özelliği desteklenmiyorsa, bunun yerine Text özelliği ayarlanır.

##  <a name="showwindow"></a>Copacontrolsıte:: ShowWindow

Pencerenin göster durumunu ayarlar.

```
virtual BOOL ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>Parametreler

*nCmdShow*<br/>
Denetim sitesinin nasıl gösterileceğini belirtir. Aşağıdaki değerlerden biri olmalıdır:

- SW_HIDE bu pencereyi gizler ve etkinleştirmeyi başka bir pencereye geçirir.

- SW_MINIMIZE pencereyi simge durumuna küçültür ve sistem listesinde en üst düzey pencereyi etkinleştirir.

- SW_RESTORE, pencereyi etkinleştirir ve görüntüler. Pencere simge durumuna küçültülmüş veya ekranı kapladıysanız, Windows bu dosyayı özgün boyutuna ve konumuna geri yükler.

- SW_SHOW, pencereyi etkinleştirir ve geçerli boyutunda ve konumunda görüntüler.

- SW_SHOWMAXIMIZED, pencereyi etkinleştirir ve ekranı kaplayan bir pencere olarak görüntüler.

- SW_SHOWMINIMIZED, pencereyi etkinleştirir ve bir simge olarak görüntüler.

- SW_SHOWMINNOACTIVE, pencereyi bir simge olarak görüntüler. Şu anda etkin olan pencere etkin kalır.

- SW_SHOWNA, pencereyi geçerli durumunda görüntüler. Şu anda etkin olan pencere etkin kalır.

- SW_SHOWNOACTIVATE, pencereyi en son boyutunda ve konumunda görüntüler. Şu anda etkin olan pencere etkin kalır.

- SW_SHOWNORMAL, pencereyi etkinleştirir ve görüntüler. Pencere simge durumuna küçültülmüş veya ekranı kapladıysanız, Windows bu dosyayı özgün boyutuna ve konumuna geri yükler.

### <a name="return-value"></a>Dönüş Değeri

Pencere daha önce görünür durumdaysa sıfır dışı; pencere daha önce gizliyse 0.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleControlContainer Sınıfı](../../mfc/reference/colecontrolcontainer-class.md)
