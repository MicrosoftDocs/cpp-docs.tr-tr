---
title: COccManager Sınıfı
ms.date: 11/04/2016
f1_keywords:
- COccManager
- AFXOCC/COccManager
- AFXOCC/COccManager::CreateContainer
- AFXOCC/COccManager::CreateDlgControls
- AFXOCC/COccManager::CreateSite
- AFXOCC/COccManager::GetDefBtnCode
- AFXOCC/COccManager::IsDialogMessage
- AFXOCC/COccManager::IsLabelControl
- AFXOCC/COccManager::IsMatchingMnemonic
- AFXOCC/COccManager::OnEvent
- AFXOCC/COccManager::PostCreateDialog
- AFXOCC/COccManager::PreCreateDialog
- AFXOCC/COccManager::SetDefaultButton
- AFXOCC/COccManager::SplitDialogTemplate
helpviewer_keywords:
- COccManager [MFC], CreateContainer
- COccManager [MFC], CreateDlgControls
- COccManager [MFC], CreateSite
- COccManager [MFC], GetDefBtnCode
- COccManager [MFC], IsDialogMessage
- COccManager [MFC], IsLabelControl
- COccManager [MFC], IsMatchingMnemonic
- COccManager [MFC], OnEvent
- COccManager [MFC], PostCreateDialog
- COccManager [MFC], PreCreateDialog
- COccManager [MFC], SetDefaultButton
- COccManager [MFC], SplitDialogTemplate
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
ms.openlocfilehash: 5637a4709e90bb14caff3fe4e396487e62e213e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360357"
---
# <a name="coccmanager-class"></a>COccManager Sınıfı

Çeşitli özel kontrol sitelerini yönetir; tarafından `COleControlSite` ve `COleControlContainer` nesneler tarafından uygulanır.

## <a name="syntax"></a>Sözdizimi

```
class COccManager : public CNoTrackObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COccManager::CreateContainer](#createcontainer)|Bir `COleContainer` nesnesi oluşturur.|
|[COccManager::CreateDlgControls](#createdlgcontrols)|İlişkili `COleContainer` nesne tarafından barındırılan ActiveX denetimleri oluşturur.|
|[COccManager::Site Oluştur](#createsite)|Bir `COleClientSite` nesnesi oluşturur.|
|[COccManager::GetDefBtnCode](#getdefbtncode)|Varsayılan düğmenin kodunu alır.|
|[COccManager::IsDialogMessage](#isdialogmessage)|İletişim iletisinin hedefini belirler.|
|[COccManager::IsLabelControl](#islabelcontrol)|Belirtilen denetimin bir etiket denetimi olup olmadığını belirler.|
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|Geçerli mnemonik belirtilen kontrolün mnemonik eşleşir söycama belirler.|
|[COccManager::OnEvent](#onevent)|Belirtilen olayı işlemeye çalışır.|
|[COccManager::PostCreateDialog](#postcreatedialog)|İletişim oluşturma sırasında ayrılan kaynakları boşaltıyor.|
|[COccManager::PreCreateDialog](#precreatedialog)|ActiveX denetimleri için bir iletişim şablonu işler.|
|[COccManager::SetDefaultButton](#setdefaultbutton)|Belirtilen denetimin varsayılan durumunu geçişe erdirin.|
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|Varolan tüm ActiveX denetimlerini belirtilen iletişim şablonundaki ortak denetimlerden ayırır.|

## <a name="remarks"></a>Açıklamalar

Taban sınıf, `CNoTrackObject`belgesiz bir taban sınıftır (AFXTLS'de bulunur. H). MFC çerçevesi tarafından kullanılmak üzere tasarlanan `CNoTrackObject` sınıftan türetilen sınıflar bellek sızıntısı algılamasından muaftır. Doğrudan ' dan `CNoTrackObject`türetmeniz önerilmez.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CNoTrackObject`

`COccManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxocc.h

## <a name="coccmanagercreatecontainer"></a><a name="createcontainer"></a>COccManager::CreateContainer

Bir denetim kapsayıcısı oluşturmak için çerçeve tarafından çağrıldı.

```
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Özel site kapsayıcısıyla ilişkili pencere nesnesi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan kapsayıcı için bir işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Özel siteler oluşturma hakkında daha fazla bilgi için [Bkz. COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite).

## <a name="coccmanagercreatedlgcontrols"></a><a name="createdlgcontrols"></a>COccManager::CreateDlgControls

*pOccDialogInfo* parametresi tarafından belirtilen ActiveX denetimlerini oluşturmak için bu işlevi arayın.

```
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,
    LPCTSTR lpszResourceName,
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);

virtual BOOL CreateDlgControls(
    CWnd* pWndParent,
    void* lpResource,
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
İletişim nesnesinin üst öğesine işaretçi.

*lpszResourceName*<br/>
Oluşturulan kaynağın adı.

*pOccDialogInfo*<br/>
İletişim nesnesini oluşturmak için kullanılan iletişim şablonuna işaretçi.

*lpResource*<br/>
Kaynağa işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Denetim başarıyla oluşturulduysa sıfırsız; aksi takdirde sıfır.

## <a name="coccmanagercreatesite"></a><a name="createsite"></a>COccManager::Site Oluştur

Çerçeve tarafından çağrılan bir kontrol sitesi oluşturmak için, konteyner *tarafından barındırılan pCtrlCont*tarafından işaret.

```
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>Parametreler

*pCtrlCont*<br/>
Yeni denetim sitesini barındıran denetim kapsayıcısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan denetim sitesine işaretçi.

### <a name="remarks"></a>Açıklamalar

[COleControlSite](../../mfc/reference/colecontrolsite-class.md)türetilmiş sınıfınızı kullanarak özel bir denetim sitesi oluşturmak için bu işlevi geçersiz kılın.

Her denetim kapsayıcısı birden çok siteyi barındırabilir. Birden çok arama içeren `CreateSite`ek siteler oluşturun.

## <a name="coccmanagergetdefbtncode"></a><a name="getdefbtncode"></a>COccManager::GetDefBtnCode

Denetimin varsayılan bir basma düğmesi olup olmadığını belirlemek için bu işlevi arayın.

```
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Düğme denetimini içeren pencere nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri:

- DLGC_DEFPUSHBUTTON Denetim iletişim kutusundavarsayılan düğmedir.

- DLGC_UNDEFPUSHBUTTON Denetimi iletişim kutusundavarsayılan düğme değildir.

- **0** Denetim bir düğme değildir.

## <a name="coccmanagerisdialogmessage"></a><a name="isdialogmessage"></a>COccManager::IsDialogMessage

İletinin belirtilen iletişim kutusu için tasarlanıp tasarlanmadığını belirlemek için çerçeve tarafından çağrılır ve değilse, iletiyi işler.

```
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*pWndDlg*<br/>
İletinin amaçlanan hedef iletişim kutusuna işaretçi.

*lpMsg*<br/>
Denetlenecek iletiyi içeren bir `MSG` yapıya işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfırsız; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranış `IsDialogMessage` klavye iletileri için kontrol etmek ve ilgili iletişim kutusu için seçimler içine dönüştürmektir. Örneğin, TAB tuşu basıldığında bir sonraki denetimi veya denetim grubunu seçer.

Belirtilen iletişim kutusuna gönderilen iletiler için özel davranış sağlamak için bu işlevi geçersiz kılın.

## <a name="coccmanagerislabelcontrol"></a><a name="islabelcontrol"></a>COccManager::IsLabelControl

Belirtilen denetimin bir etiket denetimi olup olmadığını belirlemek için bu işlevi arayın.

```
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Denetimi içeren pencereye bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Denetim bir etiketse sıfırsız; aksi takdirde sıfır

### <a name="remarks"></a>Açıklamalar

Etiket denetimi, sıralamada sırada ne olursa olsun denetim için bir etiket gibi davranan bir denetimdir.

## <a name="coccmanagerismatchingmnemonic"></a><a name="ismatchingmnemonic"></a>COccManager::IsMatchingMnemonic

Denetim tarafından temsil edilen geçerli mnemonik eşleşmeleri olup olmadığını belirlemek için bu işlevi arayın.

```
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,
    LPMSG lpMsg);

static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Denetimi içeren pencereye bir işaretçi.

*lpMsg*<br/>
Eşleşmek için mnemonic içeren iletiiçin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Mnemonik kontrol eşleşirse Nonzero; aksi takdirde sıfır

### <a name="remarks"></a>Açıklamalar

## <a name="coccmanageronevent"></a><a name="onevent"></a>COccManager::OnEvent

Belirtilen olayı işlemek için çerçeve tarafından çağrılır.

```
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,
    UINT idCtrl,
    AFX_EVENT* pEvent,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Parametreler

*pCmdHedef*<br/>
Olayı işlemeye `CCmdTarget` çalışan nesneye işaretçi

*idCtrl*<br/>
Denetimin kaynak kimliği.

*pOlay*<br/>
Olay ele alınıyor.

*pHandlerInfo*<br/>
NULL değilse, `OnEvent` komutu `pTarget` göndermek `pmf` yerine `AFX_CMDHANDLERINFO` yapının üyelerini ve üyelerini doldurur. Genellikle, bu parametre NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Olay işlenirse sıfır değil, aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Varsayılan olay işleme işlemini özelleştirmek için bu işlevi geçersiz kılın.

## <a name="coccmanagerprecreatedialog"></a><a name="precreatedialog"></a>COccManager::PreCreateDialog

Gerçek iletişim kutusunu oluşturmadan önce ActiveX denetimleri için bir iletişim şablonu işlemek için çerçeve tarafından çağrılır.

```
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,
    const DLGTEMPLATE* pOrigTemplate);
```

### <a name="parameters"></a>Parametreler

*pOccDialogInfo*<br/>
İletişim `_AFX_OCC_DIALOG_INFO` şablonu ve iletişim kutusu tarafından barındırılan tüm ActiveX denetimleri hakkında bilgi içeren bir yapı.

*pOrigTemplate*<br/>
İletişim kutusunu oluştururken kullanılacak iletişim şablonuna işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunu oluşturmak için kullanılan iletişim şablonu yapısına işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan `SplitDialogTemplate`davranış, activex denetimleri var olup olmadığını belirleyen bir arama yapar ve sonra ortaya çıkan iletişim şablonu döndürür.

ActiveX denetimlerini barındıran bir iletişim kutusu oluşturma işlemini özelleştirmek için bu işlevi geçersiz kılın.

## <a name="coccmanagerpostcreatedialog"></a><a name="postcreatedialog"></a>COccManager::PostCreateDialog

İletişim şablonu için ayrılan boş bellek için çerçeve tarafından çağrılır.

```
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Parametreler

*pOccDialogInfo*<br/>
İletişim `_AFX_OCC_DIALOG_INFO` şablonu ve iletişim kutusu tarafından barındırılan tüm ActiveX denetimleri hakkında bilgi içeren bir yapı.

### <a name="remarks"></a>Açıklamalar

Bu bellek bir çağrı `SplitDialogTemplate`tarafından tahsis edildi ve iletişim kutusunda barındırılan activex denetimleri için kullanıldı.

İletişim kutusu nesnesi tarafından kullanılan kaynakları temizleme işlemini özelleştirmek için bu işlevi geçersiz kılın.

## <a name="coccmanagersetdefaultbutton"></a><a name="setdefaultbutton"></a>COccManager::SetDefaultButton

Denetimi varsayılan düğme olarak ayarlamak için bu işlevi arayın.

```
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,
    BOOL bDefault);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Denetimi içeren pencereye bir işaretçi.

*bVarsayılan*<br/>
Denetim varsayılan düğme olacaksa sıfırolmayan; aksi takdirde sıfır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Denetim, OLEMISC_ACTSLIKEBUTTON durum biti ayarlı olmalıdır. OLEMISC bayrakları hakkında daha fazla bilgi için Windows SDK'daki [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc) konusuna bakın.

## <a name="coccmanagersplitdialogtemplate"></a><a name="splitdialogtemplate"></a>COccManager::SplitDialogTemplate

ActiveX denetimlerini ortak iletişim denetimlerinden bölmek için çerçeve tarafından çağrılır.

```
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,
    DLGITEMTEMPLATE** ppOleDlgItems);
```

### <a name="parameters"></a>Parametreler

*pTemplate*<br/>
İncelenecek iletişim şablonuna işaretçi.

*ppOleDlgItems*<br/>
ActiveX denetimleri olan iletişim kutusu öğeleriiçin işaretçilerin listesi.

### <a name="return-value"></a>Dönüş Değeri

Yalnızca ActiveX olmayan denetimleri içeren bir iletişim şablonu yapısıiçin işaretçi. ActiveX denetimi yoksa NULL döndürülür.

### <a name="remarks"></a>Açıklamalar

Herhangi bir ActiveX denetimi bulunursa, şablon analiz edilir ve yalnızca ActiveX olmayan denetimleri içeren yeni bir şablon oluşturulur. Bu işlem sırasında bulunan tüm ActiveX kontrolleri *ppOleDlgItems*eklenir.

Şablonda ActiveX denetimi yoksa NULL *döndürülür.*

> [!NOTE]
> Yeni şablon için ayrılan bellek `PostCreateDialog` işlevte serbest bırakılır.

Bu işlemi özelleştirmek için bu işlevi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleControlSite Sınıfı](../../mfc/reference/colecontrolsite-class.md)<br/>
[COleControlContainer Sınıfı](../../mfc/reference/colecontrolcontainer-class.md)
