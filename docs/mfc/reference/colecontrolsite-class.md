---
title: "COleControlSite sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80541bc777d2c77209812cbee621045b7d6c6507
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
---
# <a name="colecontrolsite-class"></a>COleControlSite sınıfı
Özel istemci-tarafı denetim arabirimler için destek sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleControlSite : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleControlSite::COleControlSite](#colecontrolsite)|Oluşturan bir `COleControlSite` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleControlSite::BindDefaultProperty](#binddefaultproperty)|Barındırılan denetimin varsayılan özelliği bir veri kaynağına bağlar.|  
|[COleControlSite::BindProperty](#bindproperty)|Barındırılan denetim özelliğini bir veri kaynağına bağlar.|  
|[COleControlSite::CreateControl](#createcontrol)|Barındırılan bir ActiveX denetimi oluşturur.|  
|[COleControlSite::DestroyControl](#destroycontrol)|Barındırılan denetim bozar.|  
|[COleControlSite::DoVerb](#doverb)|Belirli bir fiil barındırılan denetimin yürütür.|  
|[COleControlSite::EnableDSC](#enabledsc)|Kaynak denetimi site için veri sağlar.|  
|[COleControlSite::EnableWindow](#enablewindow)|Denetim site sağlar.|  
|[COleControlSite::FreezeEvents](#freezeevents)|Denetim site olayları kabul ediyor belirtir.|  
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|Barındırılan denetimi varsayılan düğme kodunu alır.|  
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|Denetim tanımlayıcısını alır.|  
|[COleControlSite::GetEventIID](#geteventiid)|Barındırılan bir denetim için bir olay arabirimi Kimliğini alır.|  
|[COleControlSite::GetExStyle](#getexstyle)|Denetim site genişletilmiş stili alır.|  
|[COleControlSite::GetProperty](#getproperty)|Belirli bir özellik barındırılan denetimin alır.|  
|[COleControlSite::GetStyle](#getstyle)|Denetim site stillerini alır.|  
|[COleControlSite::GetWindowText](#getwindowtext)|Barındırılan denetim metni alır.|  
|[COleControlSite::InvokeHelper](#invokehelper)|Barındırılan denetimin belirli bir yöntemi çağırır.|  
|[COleControlSite::InvokeHelperV](#invokehelperv)|Bağımsız değişken listesiyle barındırılan denetimin belirli bir yöntemi çağırır.|  
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|Denetimi varsayılan düğme penceresinde olup olmadığını belirler.|  
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|Denetim site görünür durumunu denetler.|  
|[COleControlSite::ModifyStyle](#modifystyle)|Denetim site stillerini genişletilmiş geçerli değiştirir.|  
|[COleControlSite::ModifyStyleEx](#modifystyleex)|Denetim site geçerli stillerini değiştirir.|  
|[COleControlSite::MoveWindow](#movewindow)|Denetim sitenin konumunu değiştirir.|  
|[COleControlSite::QuickActivate](#quickactivate)|Hızlı denetimden etkinleştirir.|  
|[COleControlSite::SafeSetProperty](#safesetproperty)|Bir özellik veya yöntem bir özel durum atma olasılığını olmadan denetiminin ayarlar.|  
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|Varsayılan düğme penceresinde ayarlar.|  
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|Denetim tanımlayıcısını alır.|  
|[COleControlSite::SetFocus](#setfocus)|Odağı denetimi siteye ayarlar.|  
|[COleControlSite::SetProperty](#setproperty)|Belirli bir özellik barındırılan denetimin ayarlar.|  
|[COleControlSite::SetPropertyV](#setpropertyv)|Belirli bir özellik denetimden bağımsız değişken listesiyle ayarlar.|  
|[COleControlSite::SetWindowPos](#setwindowpos)|Denetim sitenin konumunu ayarlar.|  
|[COleControlSite::SetWindowText](#setwindowtext)|Barındırılan denetim metin ayarlar.|  
|[COleControlSite::ShowWindow](#showwindow)|Gösterir veya gizler denetim site.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleControlSite::GetControlInfo](#getcontrolinfo)|Klavye bilgileri ve anımsatıcıları barındırılan denetimi için alır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|Barındırılan denetimi penceresiz bir denetim olup olmadığını belirler.|  
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|Klavye için denetim işleme hakkında bilgi içerir.|  
|[COleControlSite::m_dwEventSink](#m_dweventsink)|Denetimin bağlantı noktası tanımlama bilgisi.|  
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|Barındırılan denetimi için çeşitli durumları.|  
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|`IPropertyNotifySink` Denetiminin tanımlama bilgisi.|  
|[COleControlSite::m_dwStyle](#m_dwstyle)|Barındırılan denetim stilleri.|  
|[COleControlSite::m_hWnd](#m_hwnd)|Denetim site tanıtıcısı.|  
|[COleControlSite::m_iidEvents](#m_iidevents)|Barındırılan denetimi için olay arabirimi kimliği.|  
|[COleControlSite::m_nID](#m_nid)|Barındırılan denetim kimliği.|  
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|Bir işaretçi `IOleInPlaceActiveObject` barındırılan denetimin nesne.|  
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|Barındırılan denetimi kapsayıcısı.|  
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|Bir işaretçi `IOleInPlaceObject` barındırılan denetimin nesne.|  
|[COleControlSite::m_pObject](#m_pobject)|Bir işaretçi `IOleObjectInterface` denetiminin arabirimi.|  
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|Bir işaretçi `IOleInPlaceObjectWindowless` denetiminin arabirimi.|  
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|Barındırılan denetimi için pencere nesnesi için bir işaretçi.|  
|[COleControlSite::m_rect](#m_rect)|Denetim site boyutları.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu destek olarak katıştırılmış bir ActiveX denetimini konumu ve görüntüleneceği site, takma adı, kullanıcı arabirimi, ortam özelliklerini ve kapsayıcısı tarafından sağlanan diğer kaynakları hakkında bilgi edinir birincil anlamına gelir. `COleControlSite` tam olarak uygulayan [IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502), [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706), [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638),  **IBoundObjectSite**, **INotifyDBEvents**, [IRowsetNotify](../../data/oledb/irowsetnotifyimpl-class.md) arabirimleri. Ayrıca, (ortam özelliklerine ve olay havuzlarını için destek sağlayan) IDispatch arabirimi da uygulanır.  
  
 Bir ActiveX denetimini site kullanarak oluşturmak için `COleControlSite`, öğesinden bir sınıf türetin `COleControlSite`. İçinde `CWnd`-türetilmiş bir sınıf (örneğin, iletişim kutusu) kapsayıcısı için geçersiz kılma **CWnd::CreateControlSite** işlevi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlSite`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxocc.h  
  
##  <a name="binddefaultproperty"></a>  COleControlSite::BindDefaultProperty  
 Veri kaynağı denetimi veri kaynağı, kullanıcı adı, parola ve SQL özellikleri tarafından tanımlanan temel imleç arama nesnenin varsayılan basit ilişkili özelliği, tür kitaplığında işaretli olarak bağlar.  
  
```  
virtual void BindDefaultProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    LPCTSTR szFieldName,  
    CWnd* pDSCWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDispID`  
 Belirtir **DISPID** bir veri kaynağı denetimine bağlı bir veri bağlama denetimi bir özellik.  
  
 `vtProp`  
 Bağlanacak özelliğin türünü belirtir; örneğin, `VT_BSTR`, **VT_VARIANT**ve benzeri.  
  
 `szFieldName`  
 Veri kaynağı denetimi özelliği bağlanacak tarafından sağlanan imleç sütunun adını belirtir.  
  
 `pDSCWnd`  
 Bir işaretçi `CWnd`-olduğu özelliği bağlı veri kaynağı denetimini barındıran türetilen nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `CWnd` Üzerinde bu işlevini çağırmanız nesne bir veri bağlama denetimi olması gerekir.  
  
##  <a name="bindproperty"></a>  COleControlSite::BindProperty  
 Veri kaynağı denetimi veri kaynağı, kullanıcı adı, parola ve SQL özellikleri tarafından tanımlanan imleci temel alınan tür kitaplığında işaretli olarak çağıran nesnenin basit ilişkili özelliği bağlar.  
  
```  
virtual void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwDispId*  
 Belirtir **DISPID** bir veri kaynağı denetimine bağlı bir veri bağlama denetimi bir özellik.  
  
 `pWndDSC`  
 Bir işaretçi `CWnd`-olduğu özelliği bağlı veri kaynağı denetimini barındıran türetilen nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `CWnd` Üzerinde bu işlevini çağırmanız nesne bir veri bağlama denetimi olması gerekir.  
  
##  <a name="colecontrolsite"></a>  COleControlSite::COleControlSite  
 Yeni bir oluşturur `COleControlSite` nesnesi.  
  
```  
explicit COleControlSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCtrlCont`  
 (Bu ActiveX denetimini barındıran pencereyi temsil eder) denetimin kapsayıcı için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev tarafından çağrılır [COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer) işlevi. Kapsayıcıları oluşturulmasını özelleştirme hakkında daha fazla bilgi için bkz: [COccManager::CreateSite](../../mfc/reference/coccmanager-class.md#createsite).  
  
##  <a name="createcontrol"></a>  COleControlSite::CreateControl  
 Tarafından barındırılan bir ActiveX denetimini oluşturur `COleControlSite` nesnesi.  
  
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
 `pWndCtrl`  
 Denetim temsil eden pencere nesnesi için bir işaretçi.  
  
 `clsid`  
 Denetimin benzersiz sınıf kimliği.  
  
 `lpszWindowName`  
 Denetimde görüntülenecek metni için bir işaretçi. Winodw's resim yazısını veya metin özelliğinin değeri (varsa) ayarlar.  
  
 `dwStyle`  
 Windows stilleri. Kullanılabilir stiller altında listelenen **açıklamalar** bölümü.  
  
 `rect`  
 Denetimin boyutunu ve konumunu belirtir. Ya da olabilir bir `CRect` nesnesi veya bir `RECT` yapısı.  
  
 `nID`  
 Denetimin alt pencere kimliğini belirtir.  
  
 `pPersist`  
 Bir işaretçi bir `CFile` denetimi kalıcı durumunu içeren. Varsayılan değer **NULL**, denetimi kendisini herhangi kalıcı depolama biriminden durumuna geri yüklemeden başlatır olduğunu gösteren. Aksi takdirde **NULL**, bir işaretçi olmalıdır bir `CFile`-türetilmiş bir akış veya bir depolama biçiminde denetimin kalıcı veri içeren nesne. Bu veriler istemcinin önceki bir etkinleştirme kaydedilmiş. `CFile` Diğer verileri içerebilir, ancak çağrısı zaman kalıcı verilerin ilk baytı ayarlamak okuma-yazma işaretçisini olmalıdır `CreateControl`.  
  
 `bStorage`  
 Gösterir olup olmadığını verileri `pPersist` olarak yorumlanıp `IStorage` veya `IStream` veri. Varsa verilerde `pPersist` bir depolama `bStorage` olmalıdır **doğru**. Varsa verilerde `pPersist` bir akışı `bStorage` olmalıdır **FALSE**. Varsayılan değer **FALSE**.  
  
 `bstrLicKey`  
 İsteğe bağlı lisans anahtar verileri. Bu veriler, yalnızca bir çalışma zamanı lisans anahtarı gerekli denetimleri oluşturmak için gereklidir. Denetim lisans destekliyorsa, başarılı olması için denetimi oluşturulması için bir lisans anahtarı sağlamanız gerekir. Varsayılan değer **NULL**.  
  
 `ppt`  
 Bir işaretçi bir **noktası** denetimin sol üst köşesinde içeren yapısı. Denetimin boyutunu değeri tarafından belirlenir *psize*. `ppt` Ve *psize* değerler boyutu belirten isteğe bağlı bir yöntem ve opf denetimi getirin.  
  
 *psize*  
 Bir işaretçi bir **BOYUTU** denetimin boyutunu içeren yapısı. Sol üst köşesindeki değeri tarafından belirlenir `ppt`. `ppt` Ve *psize* değerler boyutu belirten isteğe bağlı bir yöntem ve opf denetimi getirin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca bir alt kümesini Windows `dwStyle` bayrakları tarafından desteklenen `CreateControl`:  
  
- **Ws_vısıble** başlangıçta görünür bir pencere oluşturur. Denetim hemen, normal windows gibi görünür olmasını istiyorsanız gereklidir.  
  
- **Ws_dısabled** başlangıçta devre dışı bir pencere oluşturur. Devre dışı bırakılan penceresinde kullanıcıdan giriş alamaz. Denetim etkin özelliğine sahipse ayarlanabilir.  
  
- `WS_BORDER` Bir pencere ince çizgi kenarlık ile oluşturur. Denetim kenarlık stili özelliğine sahipse ayarlanabilir.  
  
- **WS_GROUP** denetimleri grubunun ilk denetim belirtir. Kullanıcı klavye odağını grubundaki bir denetimden sonraki yön tuşlarını kullanarak değiştirebilirsiniz. İle tanımlanmış tüm denetimler **WS_GROUP** ilk denetim ait sonra aynı gruba stili. Sonraki denetimiyle **WS_GROUP** Stil grubu sona erer ve sonraki grubu başlatır.  
  
- **WS_TABSTOP** kullanıcı SEKME tuşuna bastığında klavye odağı alabilecek bir denetim belirtir. Sonraki denetimin değişiklikleri klavye odağını SEKME tuşuna basarak **WS_TABSTOP** stili.  
  
 İkinci varsayılan boyutlu denetimleri oluşturmak için kullanın.  
  
##  <a name="destroycontrol"></a>  COleControlSite::DestroyControl  
 Bozar `COleControlSite` nesnesi.  
  
```  
virtual BOOL DestroyControl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sıfır olmayan Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonra tamamlandı, nesne belleği serbest bırakılmaz ve nesne için tüm işaretçiler artık geçerli değil.  
  
##  <a name="doverb"></a>  COleControlSite::DoVerb  
 Belirtilen fiil çalıştırır.  
  
```  
virtual HRESULT DoVerb(
    LONG nVerb,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `nVerb`  
 Yürütülecek fiili belirtir. Aşağıdakilerden birini içerebilir:  
  
|Değer|Açıklama|Simgesi|  
|-----------|-------------|------------|  
|0|Birincil fiil|`OLEIVERB_PRIMARY`|  
|-1|İkincil fiil|(Hiçbiri)|  
|1.|Nesneyi düzenlemek üzere görüntüler.|`OLEIVERB_SHOW`|  
|-2|Ayrı bir pencerede öğesini düzenler.|`OLEIVERB_OPEN`|  
|-3|Nesne gizler.|`OLEIVERB_HIDE`|  
|-4|Bir denetim yerinde etkinleştirir.|`OLEIVERB_UIACTIVATE`|  
|-5|Bir denetim yerinde, ek kullanıcı arabirimi öğeleri olmadan etkinleştirir.|**OLEIVERB_INPLACEACTIVATE**|  
|-7|Denetimin özelliklerini görüntüleyin.|**OLEIVERB_PROPERTIES**|  
  
 `lpMsg`  
 İşaretçi etkinleştirilmesi için öğeyi neden iletisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev denetim doğrudan çağıran `IOleObject` belirtilen fiil yürütmek için arabirim. Bu işlev çağrısının sonucunda bir özel durum, bir `HRESULT` hata kodu döndürülür.  
  
 Daha fazla bilgi için bkz: [Rpc_e_serverfault](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK'sındaki.  
  
##  <a name="enabledsc"></a>  COleControlSite::EnableDSC  
 Kaynak denetimi site için veri sağlar.  
  
```  
virtual void EnableDSC();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Etkinleştirme ve denetim site için kaynak verilerini başlatmak için çerçevesi tarafından çağrılır. Özelleştirilmiş davranışı sağlamak için bu işlevi geçersiz kılar.  
  
##  <a name="enablewindow"></a>  COleControlSite::EnableWindow  
 Etkinleştirir veya fare ve klavye denetim siteye devre dışı bırakır.  
  
```  
virtual BOOL EnableWindow(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 `bEnable`  
 Etkinleştirmek veya devre dışı penceresi belirtir: **TRUE** penceresi giriş, aksi takdirde etkinleştirilecek ise **FALSE**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencerenin daha önce devre dışı bırakılmışsa, sıfır olmayan Aksi halde 0.  
  
##  <a name="freezeevents"></a>  COleControlSite::FreezeEvents  
 Denetim site işleyebilir veya denetimden tetiklenen olayları yoksay belirtir.  
  
```  
void FreezeEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Parametreler  
 `bFreeze`  
 Denetim site olayları kabul etmeyi istediği olup olmadığını belirtir. Denetim olayları kabul etmiyor, sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bFreeze` olan **doğru**, Denetim site fring olayları durdurmak için Denetim ister. Varsa `bFreeze` olan **yanlış**, Denetim site denetim olaylarını tetikleme devam etmek ister.  
  
> [!NOTE]
>  Denetim olayları denetim site tarafından isteniyorsa tetikleme durdurmak için gerekli değildir. Tetikleme devam edebilirsiniz ancak tüm sonraki olaylarda denetim site tarafından göz ardı edilir.  
  
##  <a name="getcontrolinfo"></a>  COleControlSite::GetControlInfo  
 Bir denetimin klavye anımsatıcıları ve klavye davranışını ilgili bilgileri alır.  
  
```  
void GetControlInfo();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bilgi depolanan [COleControlSite::m_ctlInfo](#m_ctlinfo).  
  
##  <a name="getdefbtncode"></a>  COleControlSite::GetDefBtnCode  
 Denetimi varsayılan düğme olup olmadığını belirler.  
  
```  
DWORD GetDefBtnCode();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden biri olabilir:  
  
- **DLGC_DEFPUSHBUTTON** denetimidir iletişim kutusunda varsayılan düğme.  
  
- **DLGC_UNDEFPUSHBUTTON** denetim iletişim kutusunda varsayılan düğme değil.  
  
- **0** denetim bir düğme değil.  
  
##  <a name="getdlgctrlid"></a>  COleControlSite::GetDlgCtrlID  
 Denetim tanımlayıcısını alır.  
  
```  
virtual int GetDlgCtrlID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimin iletişim öğe tanımlayıcısı.  
  
##  <a name="geteventiid"></a>  COleControlSite::GetEventIID  
 Denetimin varsayılan olay arabirimi için bir işaretçi alır.  
  
```  
BOOL GetEventIID(IID* piid);
```  
  
### <a name="parameters"></a>Parametreler  
 `piid`  
 Bir işaretçi bir arabirim kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sıfır olmayan Aksi halde 0. Başarılı olursa, `piid` denetimin varsayılan olay arabirimi arabirimi Kimliğini içerir.  
  
##  <a name="getexstyle"></a>  COleControlSite::GetExStyle  
 Genişletilmiş pencere stilleri alır.  
  
```  
virtual DWORD GetExStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim pencere stilleri genişletilmiş.  
  
### <a name="remarks"></a>Açıklamalar  
 Normal stilleri almak için arama [COleControlSite::GetStyle](#getstyle).  
  
##  <a name="getproperty"></a>  COleControlSite::GetProperty  
 Tarafından belirtilen denetim özelliğini alır `dwDispID`.  
  
```  
virtual void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDispID`  
 Denetimin varsayılan olarak bulunan özellik gönderme Kimliğini tanımlar `IDispatch` alınması için arabirim.  
  
 `vtProp`  
 Alınacak özelliğin türünü belirtir. Olası değerler için için Açıklamalar bölümüne bakın [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `pvProp`  
 Özellik değeri alacak değişkeni adresidir. Tarafından belirtilen tür eşleşmelidir `vtProp`.  
  
### <a name="remarks"></a>Açıklamalar  
 Aracılığıyla döndürülen değer `pvProp`.  
  
##  <a name="getstyle"></a>  COleControlSite::GetStyle  
 Denetim site stillerini alır.  
  
```  
virtual DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencere stilleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Olası değerler listesi için bkz: [Windows stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles). Denetim site genişletilmiş stillerini almak için arama [COleControlSite::GetExStyle](#getexstyle).  
  
##  <a name="getwindowtext"></a>  COleControlSite::GetWindowText  
 Denetimin geçerli metni alır.  
  
```  
virtual void GetWindowText(CString& str) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 Bir başvuru bir `CString` denetimin geçerli metni içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim resim yazısı stok özellik destekliyorsa, bu değeri döndürülür. Resim yazısı stok özellik desteklenmiyorsa metin özelliğinin değeri döndürülür.  
  
##  <a name="invokehelper"></a>  COleControlSite::InvokeHelper  
 Yöntemi veya özelliği tarafından belirtilen çağırır `dwDispID`, tarafından belirtilen bağlamda `wFlags`.  
  
```  
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDispID`  
 Özellik veya yöntem, denetimin üzerinde bulunan gönderme Kimliğini tanımlar `IDispatch` çağrılacak arabirimi.  
  
 `wFlags`  
 IDispatch::Invoke çağrısı bağlamında açıklayan bayrakları. Olası için `wFlags` değerler, bakın `IDispatch::Invoke` Windows SDK'sındaki.  
  
 `vtRet`  
 Dönüş değeri türünü belirtir. Olası değerler için için Açıklamalar bölümüne bakın [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `pvRet`  
 Özellik değeri alır veya dönüş değeri değişken adresidir. Tarafından belirtilen tür eşleşmelidir `vtRet`.  
  
 `pbParamInfo`  
 Aşağıdaki parametre türlerini belirtme bayt null ile sonlandırılmış dizeye işaretçi `pbParamInfo`. Olası değerler için için Açıklamalar bölümüne bakın [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Belirtilen türlerinin parametrelerin değişken listesi `pbParamInfo`.  
  
### <a name="remarks"></a>Açıklamalar  
 `pbParamInfo` Parametresi, yöntemi veya özelliği için geçirilen parametre türlerini belirtir. Bağımsız değişken listesi... sözdizimi bildiriminde temsil edilir.  
  
 Bu işlev parametreleri dönüştürür **VARIANTARG** değerleri sonra çağırır **IDispatch::Invoke** denetimindeki yöntemi. Varsa çağrısı **IDispatch::Invoke** başarısız olursa, bu işlev throw bir özel durum. Durum kodu tarafından döndürülürse **IDispatch::Invoke** olan `DISP_E_EXCEPTION`, bu işlev oluşturur bir **COleDispatchException** onu oluşturur nesnesi, aksi takdirde bir `COleException`.  
  
##  <a name="invokehelperv"></a>  COleControlSite::InvokeHelperV  
 Yöntemi veya özelliği tarafından belirtilen çağırır `dwDispID`, tarafından belirtilen bağlamda `wFlags`.  
  
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
 `dwDispID`  
 Özellik veya yöntem, denetimin üzerinde bulunan gönderme Kimliğini tanımlar `IDispatch` çağrılacak arabirimi.  
  
 `wFlags`  
 IDispatch::Invoke çağrısı bağlamında açıklayan bayrakları.  
  
 `vtRet`  
 Dönüş değeri türünü belirtir. Olası değerler için için Açıklamalar bölümüne bakın [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `pvRet`  
 Özellik değeri alır veya dönüş değeri değişken adresidir. Tarafından belirtilen tür eşleşmelidir `vtRet`.  
  
 `pbParamInfo`  
 Aşağıdaki parametre türlerini belirtme bayt null ile sonlandırılmış dizeye işaretçi `pbParamInfo`. Olası değerler için için Açıklamalar bölümüne bakın [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `argList`  
 Değişken bağımsız değişken listesi işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 `pbParamInfo` Parametresi, yöntemi veya özelliği için geçirilen parametre türlerini belirtir. Ek parametreler için yöntemi veya özelliği çağrılan kullanılarak geçirilebilir *va_list* parametresi.  
  
 Genellikle, bu işlev tarafından çağrılır `COleControlSite::InvokeHelper`.  
  
##  <a name="isdefaultbutton"></a>  COleControlSite::IsDefaultButton  
 Denetimi varsayılan düğme olup olmadığını belirler.  
  
```  
BOOL IsDefaultButton();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim ise sıfır olmayan pencere varsayılan düğme Aksi halde sıfır.  
  
##  <a name="iswindowenabled"></a>  COleControlSite::IsWindowEnabled  
 Denetim site etkin olup olmadığını belirler.  
  
```  
virtual BOOL IsWindowEnabled() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan denetim etkinse, aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Değer denetim etkin stok özelliğinden alınır.  
  
##  <a name="m_biswindowless"></a>  COleControlSite::m_bIsWindowless  
 Nesne penceresiz bir denetim olup olmadığını belirler.  
  
```  
BOOL m_bIsWindowless;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sıfır olmayan denetimi penceresi yok varsa, aksi takdirde sıfır.  
  
##  <a name="m_ctlinfo"></a>  COleControlSite::m_ctlInfo  
 Klavye girişi denetim tarafından nasıl işleneceğini hakkında bilgi.  
  
```  
CONTROLINFO m_ctlInfo;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bilgileri bir [CONTROLINFO](http://msdn.microsoft.com/library/windows/desktop/ms680734) yapısı.  
  
##  <a name="m_dweventsink"></a>  COleControlSite::m_dwEventSink  
 Bağlantı noktasının tanımlama bilgisinden denetimin olay havuzu içerir.  
  
```  
DWORD m_dwEventSink;  
```  
  
##  <a name="m_dwmiscstatus"></a>  COleControlSite::m_dwMiscStatus  
 Denetimi hakkında çeşitli bilgi içerir.  
  
```  
DWORD m_dwMiscStatus;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497)Windows SDK'sındaki.  
  
##  <a name="m_dwpropnotifysink"></a>  COleControlSite::m_dwPropNotifySink  
 İçeren [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638) tanımlama bilgisi.  
  
```  
DWORD m_dwPropNotifySink;  
```  
  
##  <a name="m_dwstyle"></a>  COleControlSite::m_dwStyle  
 Pencere stilleri denetimi içerir.  
  
```  
DWORD m_dwStyle;  
```  
  
##  <a name="m_hwnd"></a>  COleControlSite::m_hWnd  
 İçeren `HWND` denetiminin veya **NULL** denetim penceresiz ise.  
  
```  
HWND m_hWnd;  
```  
  
##  <a name="m_iidevents"></a>  COleControlSite::m_iidEvents  
 Denetimin varsayılan olay havuz arabirimi arabirimi Kimliğini içerir.  
  
```  
IID m_iidEvents;  
```  
  
##  <a name="m_nid"></a>  COleControlSite::m_nID  
 Denetimin iletişim öğesi kimliğini içerir.  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_pactiveobject"></a>  COleControlSite::m_pActiveObject  
 İçeren [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) denetiminin arabirimi.  
  
```  
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;  
```  
  
##  <a name="m_pctrlcont"></a>  COleControlSite::m_pCtrlCont  
 Denetimin kapsayıcısı (formun temsil eder) içerir.  
  
```  
COleControlContainer* m_pCtrlCont;  
```  
  
##  <a name="m_pinplaceobject"></a>  COleControlSite::m_pInPlaceObject  
 İçeren `IOleInPlaceObject` [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) denetiminin arabirimi.  
  
```  
LPOLEINPLACEOBJECT m_pInPlaceObject;  
```  
  
##  <a name="m_pobject"></a>  COleControlSite::m_pObject  
 İçeren **IOleObjectInterface** denetiminin arabirimi.  
  
```  
LPOLEOBJECT m_pObject;  
```  
  
##  <a name="m_pwindowlessobject"></a>  COleControlSite::m_pWindowlessObject  
 İçeren `IOleInPlaceObjectWindowless` [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) denetiminin arabirimi.  
  
```  
IOleInPlaceObjectWindowless* m_pWindowlessObject;  
```  
  
##  <a name="m_pwndctrl"></a>  COleControlSite::m_pWndCtrl  
 Bir işaretçi içeriyor `CWnd` denetimini temsil eden nesne.  
  
```  
CWnd* m_pWndCtrl;  
```  
  
##  <a name="m_rect"></a>  COleControlSite::m_rect  
 Denetimin kapsayıcısının penceresi göre sınırları içerir.  
  
```  
CRect m_rect;  
```  
  
##  <a name="modifystyle"></a>  COleControlSite::ModifyStyle  
 Denetim stilleri değiştirir.  
  
```  
virtual BOOL ModifyStyle(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwRemove`  
 Geçerli pencere stilleri kaldırılacak stilleri.  
  
 `dwAdd`  
 Geçerli pencere stilleri eklenecek stilleri.  
  
 `nFlags`  
 Bayrakları konumlandırma penceresini açın. Olası değerler listesi için bkz: [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Windows SDK'sındaki işlevi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Stilleri değiştirilirse, aksi takdirde sıfır sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimin hisse senedi etkin özelliğin ayarını eşleşecek şekilde değiştirilecek **ws_dısabled**. Denetimin stok kenarlık stili özellik istenen ayarını eşleşecek şekilde değiştirilecek `WS_BORDER`. Var olan tüm diğer stilleri doğrudan denetimin pencere tanıtıcının için uygulanır.  
  
 Pencere stilleri denetiminin değiştirir. Bit düzeyinde OR kullanarak eklendiğinde veya kaldırıldığında stiller birleştirilebilir ( &#124; ) işleci. Bkz: [CreateWindow'u](http://msdn.microsoft.com/library/windows/desktop/ms632679) kullanılabilir pencere stilleri hakkında bilgi için Windows SDK'sı işlevinde.  
  
 Varsa `nFlags` sıfır olmayan, olan `ModifyStyle` Win32 işlev çağrılarını `SetWindowPos`ve pencere birleştirerek yeniden çizer `nFlags` aşağıdaki dört bayrağı ile:  
  
- `SWP_NOSIZE` Geçerli boyutu korur.  
  
- `SWP_NOMOVE` Geçerli konumu korur.  
  
- `SWP_NOZORDER` Geçerli Z düzenini korur.  
  
- `SWP_NOACTIVATE` Pencerenin etkinleştirmez.  
  
 Stilleri genişletilmiş bir pencere değiştirmek için arama [ModifyStyleEx](#modifystyleex).  
  
##  <a name="modifystyleex"></a>  COleControlSite::ModifyStyleEx  
 Denetimin genişletilmiş stilleri değiştirir.  
  
```  
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwRemove`  
 Geçerli pencere stilleri kaldırılacak genişletilmiş stili.  
  
 `dwAdd`  
 Geçerli pencere stilleri eklenecek genişletilmiş stili.  
  
 `nFlags`  
 Bayrakları konumlandırma penceresini açın. Olası değerler listesi için bkz: [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Windows SDK'sındaki işlevi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Stilleri değiştirilirse, aksi takdirde sıfır sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimin stoğu görünümünü özellik ayarı eşleşecek şekilde değiştirilecek **WS_EX_CLIENTEDGE**. Var olan diğer tüm genişletilmiş pencere stilleri doğrudan denetimin pencere tanıtıcının için uygulanır.  
  
 Denetim site nesnesi stillerini genişletilmiş penceresini değiştirir. Bit düzeyinde OR kullanarak eklendiğinde veya kaldırıldığında stiller birleştirilebilir ( &#124; ) işleci. Bkz: [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) kullanılabilir pencere stilleri hakkında bilgi için Windows SDK'sı işlevinde.  
  
 Varsa `nFlags` sıfır olmayan, olan `ModifyStyleEx` Win32 işlev çağrılarını `SetWindowPos`ve pencere birleştirerek yeniden çizer `nFlags` aşağıdaki dört bayrağı ile:  
  
- `SWP_NOSIZE` Geçerli boyutu korur.  
  
- `SWP_NOMOVE` Geçerli konumu korur.  
  
- `SWP_NOZORDER` Geçerli Z düzenini korur.  
  
- `SWP_NOACTIVATE` Pencerenin etkinleştirmez.  
  
 Stilleri genişletilmiş bir pencere değiştirmek için arama [ModifyStyle](#modifystyle).  
  
##  <a name="movewindow"></a>  COleControlSite::MoveWindow  
 Denetimin konumunu değiştirir.  
  
```  
virtual void MoveWindow(
    int x,  
    int y,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 Pencerenin sol tarafında yeni konumu.  
  
 *y*  
 Pencerenin üst kısmında yeni konumu.  
  
 `nWidth`  
 Pencerenin yeni genişliği  
  
 `nHeight`  
 Pencerenin yeni yüksekliği.  
  
##  <a name="quickactivate"></a>  COleControlSite::QuickActivate  
 Hızlı kapsanan denetimini etkinleştirir.  
  
```  
virtual BOOL QuickActivate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan denetim site etkinleştirilmişse, aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca kullanıcı denetimi oluşturma işlemi geçersiz kılıyorsa çağrılmalıdır.  
  
 `IPersist*::Load` Ve `IPersist*::InitNew` hızlı etkinleştirme gerçekleştikten sonra yöntemleri'nin çağrılabilir. Denetim bağlantılarından kapsayıcının havuzlarını için hızlı etkinleştirme sırasında oluşturmanız gerekir. Ancak, bu bağlantıları kadar dinamik olmayan `IPersist*::Load` veya `IPersist*::InitNew` çağrıldı.  
  
##  <a name="safesetproperty"></a>  COleControlSite::SafeSetProperty  
 Denetim özelliği tarafından belirtilen ayarlar `dwDispID`.  
  
```  
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDispID`  
 Özellik veya yöntem, denetimin üzerinde bulunan gönderme Kimliğini tanımlar `IDispatch` ayarlanacak arabirimi.  
  
 `vtProp`  
 Ayarlanacak özelliği türünü belirtir. Olası değerler için için Açıklamalar bölümüne bakın [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Tek bir parametre tarafından belirtilen türde `vtProp`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Farklı `SetProperty` ve `SetPropertyV`, (varolmayan bir özellik ayarlanmaya çalışılırken gibi) bir hatayla karşılaştı, hiçbir özel durum oluşur.  
  
##  <a name="setdefaultbutton"></a>  COleControlSite::SetDefaultButton  
 Denetimi varsayılan düğme olarak ayarlar.  
  
```  
void SetDefaultButton(BOOL bDefault);
```  
  
### <a name="parameters"></a>Parametreler  
 `bDefault`  
 Denetimi varsayılan düğme duruma gelir, sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Denetimi olmalıdır **OLEMISC_ACTSLIKEBUTTON** durum biti ayarlanmamış.  
  
##  <a name="setdlgctrlid"></a>  COleControlSite::SetDlgCtrlID  
 Denetimin iletişim öğesi tanımlayıcısının değeri ile değiştirir.  
  
```  
virtual int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Yeni tanımlayıcı değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, önceki iletişim penceresi tanıtıcısı öğesi; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setfocus"></a>  COleControlSite::SetFocus  
 Denetim odağı ayarlar.  
  
```  
virtual CWnd* SetFocus();  
virtual CWnd* SetFocus(LPMSG lpmsg);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpmsg*  
 Bir işaretçi bir [MSG yapısı](../../mfc/reference/msg-structure1.md). Bu yapı Windows ileti harekete içerir `SetFocus` geçerli denetim sitede bulunan denetim isteği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce odağa sahip penceresi için bir işaretçi.  
  
##  <a name="setproperty"></a>  COleControlSite::SetProperty  
 Denetim özelliği tarafından belirtilen ayarlar `dwDispID`.  
  
```  
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDispID`  
 Özellik veya yöntem, denetimin üzerinde bulunan gönderme Kimliğini tanımlar `IDispatch` ayarlanacak arabirimi.  
  
 `vtProp`  
 Ayarlanacak özelliği türünü belirtir. Olası değerler için için Açıklamalar bölümüne bakın [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Tek bir parametre tarafından belirtilen türde `vtProp`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `SetProperty` karşılaştığı bir hata, bir özel durum oluşur.  
  
 Özel durum türü özellik veya yöntem ayarlama girişimi dönüş değeri tarafından belirlenir. Dönüş değeri ise `DISP_E_EXCEPTION`, **COleDispatchExcpetion** oluşturulur; Aksi takdirde bir `COleException`.  
  
##  <a name="setpropertyv"></a>  COleControlSite::SetPropertyV  
 Denetim özelliği tarafından belirtilen ayarlar `dwDispID`.  
  
```  
virtual void SetPropertyV(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    va_list argList);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDispID`  
 Özellik veya yöntem, denetimin üzerinde bulunan gönderme Kimliğini tanımlar `IDispatch` ayarlanacak arabirimi.  
  
 `vtProp`  
 Ayarlanacak özelliği türünü belirtir. Olası değerler için için Açıklamalar bölümüne bakın [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 `argList`  
 Bağımsız değişken listesiyle işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Ek parametreler için yöntemi veya özelliği çağrılan passeed olabilir kullanarak *arg_list* parametresi. Varsa `SetProperty` karşılaştığı bir hata, bir özel durum oluşur.  
  
 Özel durum türü özellik veya yöntem ayarlama girişimi dönüş değeri tarafından belirlenir. Dönüş değeri ise `DISP_E_EXCEPTION`, **COleDispatchExcpetion** oluşturulur; Aksi takdirde bir `COleException`.  
  
##  <a name="setwindowpos"></a>  COleControlSite::SetWindowPos  
 Boyut, konum ve denetim site Z düzenini belirler.  
  
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
 `pWndInsertAfter`  
 Penceresi için bir işaretçi.  
  
 *x*  
 Pencerenin sol tarafında yeni konumu.  
  
 *y*  
 Pencerenin üst kısmında yeni konumu.  
  
 `cx`  
 Pencerenin yeni genişliği  
  
 `cy`  
 Pencerenin yeni yüksekliği.  
  
 `nFlags`  
 Boyutlandırma ve bayrakları konumlandırmasını penceresi belirtir. Olası değerler için için Açıklamalar bölümüne bakın [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan başarılı olursa, aksi takdirde sıfır.  
  
##  <a name="setwindowtext"></a>  COleControlSite::SetWindowText  
 Metin denetim site için ayarlar.  
  
```  
virtual void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszString`  
 Yeni başlık veya denetim metin olarak kullanılacak bir null ile sonlandırılmış dize işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, ilk resim yazısı stok özellik ayarlamaya çalışır. Metin özelliği, resim yazısını stok özellik desteklenmiyorsa, bunun yerine ayarlanır.  
  
##  <a name="showwindow"></a>  COleControlSite::ShowWindow  
 Pencerenin Göster durumunu ayarlar.  
  
```  
virtual BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>Parametreler  
 `nCmdShow`  
 Nasıl denetim site gösterilecek belirtir. Aşağıdaki değerlerden biri olmalıdır:  
  
- **SW_HIDE** bu pencereyi gizler ve başka bir pencere için etkinleştirme geçirir.  
  
- **SW_MINIMIZE** pencerenin en aza indirir ve üst düzey pencere sistemin listesinde etkinleştirir.  
  
- **SW_RESTORE** Activates ve penceresi görüntüler. Pencereyi simge durumuna küçültülmüş veya ekranı, Windows, özgün boyutunu ve konumunu geri yükler.  
  
- **SW_SHOW** penceresini etkinleştirir ve onun geçerli boyutunu ve konumunu görüntüler.  
  
- **SW_SHOWMAXIMIZED** penceresini etkinleştirir ve kaplamış görüntüler.  
  
- **SW_SHOWMINIMIZED** penceresini etkinleştirir ve simge olarak görüntüler.  
  
- **SW_SHOWMINNOACTIVE** pencereyi simge olarak görüntüler. Şu anda etkin olan penceresi etkin kalır.  
  
- **SW_SHOWNA** geçerli durumunda pencerede görüntülenir. Şu anda etkin olan penceresi etkin kalır.  
  
- **SW_SHOWNOACTIVATE** penceresi, en son boyutunu ve konumunu görüntüler. Şu anda etkin olan penceresi etkin kalır.  
  
- **SW_SHOWNORMAL** Activates ve penceresi görüntüler. Pencereyi simge durumuna küçültülmüş veya ekranı, Windows, özgün boyutunu ve konumunu geri yükler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencerenin daha önce görülebiliyorsa sıfır olmayan; pencerenin gizlenmiş ise 0.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleControlContainer Sınıfı](../../mfc/reference/colecontrolcontainer-class.md)
