---
description: 'Daha fazla bilgi edinin: COccManager sınıfı'
title: COccManager sınıfı
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
ms.openlocfilehash: 8acd39825f7f842a266a4b1dbf187ba4f7f9b5ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331432"
---
# <a name="coccmanager-class"></a>COccManager sınıfı

Çeşitli özel denetim sitelerini yönetir; `COleControlContainer` ve nesneleri tarafından uygulandı `COleControlSite` .

## <a name="syntax"></a>Syntax

```
class COccManager : public CNoTrackObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COccManager:: CreateContainer](#createcontainer)|Bir `COleContainer` nesnesi oluşturur.|
|[COccManager:: CreateDlgControls](#createdlgcontrols)|İlişkili nesne tarafından barındırılan ActiveX denetimleri oluşturur `COleContainer` .|
|[COccManager:: CreateSite](#createsite)|Bir `COleClientSite` nesnesi oluşturur.|
|[COccManager:: GetDefBtnCode](#getdefbtncode)|Varsayılan düğmenin kodunu alır.|
|[COccManager:: IsDialogMessage](#isdialogmessage)|İletişim kutusu mesajının hedefini belirler.|
|[COccManager:: ıslabelcontrol](#islabelcontrol)|Belirtilen denetimin bir etiket denetimi olup olmadığını belirler.|
|[COccManager:: ısmatchinganımsatıcı](#ismatchingmnemonic)|Geçerli anımsatıcı belirtilen denetimin anımsatıcı ile eşleşip eşleşmediğini belirler.|
|[COccManager:: OnEvent](#onevent)|Belirtilen olayı işlemeye çalışır.|
|[COccManager::P ostCreateDialog](#postcreatedialog)|İletişim kutusu oluşturma sırasında ayrılan kaynakları boşaltır.|
|[COccManager::P reCreateDialog](#precreatedialog)|ActiveX denetimleri için bir iletişim kutusu şablonunu işler.|
|[COccManager:: SetDefaultButton](#setdefaultbutton)|Belirtilen denetimin varsayılan durumunu değiştirir.|
|[COccManager:: SplitDialogTemplate](#splitdialogtemplate)|Varolan tüm ActiveX denetimlerini belirtilen iletişim kutusu şablonundaki ortak denetimlerden ayırır.|

## <a name="remarks"></a>Açıklamalar

Temel sınıf, `CNoTrackObject` bir belgelenmemiş taban sınıftır (AFXTLS ' de bulunur. H). MFC çerçevesi tarafından kullanılmak üzere tasarlanan sınıftan türetilmiş sınıflar `CNoTrackObject` bellek sızıntısı algılamasında muaf tutulur. Doğrudan ' den türetmeniz önerilmez `CNoTrackObject` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CNoTrackObject`

`COccManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxocc. h

## <a name="coccmanagercreatecontainer"></a><a name="createcontainer"></a> COccManager:: CreateContainer

Bir denetim kapsayıcısı oluşturmak için Framework tarafından çağırılır.

```
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Özel site kapsayıcısı ile ilişkili pencere nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan kapsayıcıya yönelik bir işaretçi; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Özel siteler oluşturma hakkında daha fazla bilgi için bkz. [Colicontrolcontainer:: AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite).

## <a name="coccmanagercreatedlgcontrols"></a><a name="createdlgcontrols"></a> COccManager:: CreateDlgControls

*Poccdialogınfo* parametresi tarafından belirtilen ActiveX denetimleri oluşturmak için bu işlevi çağırın.

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
İletişim kutusu nesnesinin üst öğesine yönelik bir işaretçi.

*lpszResourceName*<br/>
Oluşturulmakta olan kaynağın adı.

*Poccdialogınfo*<br/>
İletişim kutusu nesnesini oluşturmak için kullanılan iletişim kutusu şablonuna yönelik bir işaretçi.

*lpResource*<br/>
Kaynak işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Denetim başarıyla oluşturulduysa sıfır dışı; Aksi halde sıfır.

## <a name="coccmanagercreatesite"></a><a name="createsite"></a> COccManager:: CreateSite

*PCtrlCont* tarafından işaret edilen kapsayıcı tarafından barındırılan bir denetim sitesi oluşturmak için Framework tarafından çağırılır.

```
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>Parametreler

*pCtrlCont*<br/>
Yeni denetim sitesini barındıran denetim kapsayıcısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan denetim sitesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

[Coelcontrolsıte](../../mfc/reference/colecontrolsite-class.md)ile türetilmiş sınıfınızı kullanarak özel bir denetim sitesi oluşturmak için bu işlevi geçersiz kılın.

Her denetim kapsayıcısı birden çok siteyi barındırabilirler. Birden çok çağrısı olan ek siteler oluşturun `CreateSite` .

## <a name="coccmanagergetdefbtncode"></a><a name="getdefbtncode"></a> COccManager:: GetDefBtnCode

Denetimin varsayılan bir gönderme düğmesi olup olmadığını öğrenmek için bu işlevi çağırın.

```
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Düğme denetimini içeren pencere nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri:

- DLGC_DEFPUSHBUTTON denetim, iletişim kutusunda varsayılan düğmedir.

- DLGC_UNDEFPUSHBUTTON denetim, iletişim kutusunda varsayılan düğme değil.

- **0** denetimi bir düğme değildir.

## <a name="coccmanagerisdialogmessage"></a><a name="isdialogmessage"></a> COccManager:: IsDialogMessage

Çerçeve tarafından, belirtilen iletişim kutusu için bir iletinin amaçlanıp tasarlanmadığını ve varsa iletiyi işler olduğunu anlamak için çağırılır.

```
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*pWndDlg*<br/>
İletinin amaçlanan hedef iletişim kutusu işaretçisi.

*lpMsg*<br/>
`MSG`Denetlenecek iletiyi içeren bir yapıya yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranışı, `IsDialogMessage` klavye iletilerini denetmek ve ilgili iletişim kutusu için bunları seçimlere dönüştürmelidir. Örneğin TAB tuşu basıldığında, bir sonraki denetimi veya denetim grubunu seçer.

Belirtilen iletişim kutusuna gönderilen iletiler için özel davranış sağlamak üzere bu işlevi geçersiz kılın.

## <a name="coccmanagerislabelcontrol"></a><a name="islabelcontrol"></a> COccManager:: ıslabelcontrol

Belirtilen denetimin bir etiket denetimi olup olmadığını öğrenmek için bu işlevi çağırın.

```
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Denetimi içeren pencereye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Denetim bir etiketse sıfır dışı; Aksi halde sıfır

### <a name="remarks"></a>Açıklamalar

Etiket denetimi, sıralamada herhangi bir denetim için bir etiket gibi davranan bir etikettir.

## <a name="coccmanagerismatchingmnemonic"></a><a name="ismatchingmnemonic"></a> COccManager:: ısmatchinganımsatıcı

Geçerli anımsatıcı denetimin temsil eden ile eşleşip eşleşmediğini öğrenmek için bu işlevi çağırın.

```
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,
    LPMSG lpMsg);

static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Denetimi içeren pencereye yönelik bir işaretçi.

*lpMsg*<br/>
Eşleşecek anımsatıcı içeren iletiye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Anımsatıcı denetimle eşleşiyorsa sıfır dışı; Aksi halde sıfır

### <a name="remarks"></a>Açıklamalar

## <a name="coccmanageronevent"></a><a name="onevent"></a> COccManager:: OnEvent

Belirtilen olayı işlemek için Framework tarafından çağırılır.

```
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,
    UINT idCtrl,
    AFX_EVENT* pEvent,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Parametreler

*pCmdTarget*<br/>
`CCmdTarget`Olayı işlemeye çalışan nesneye yönelik bir işaretçi

*ıdctrl*<br/>
Denetimin kaynak KIMLIĞI.

*pEvent*<br/>
İşlenmekte olan olay.

*pHandlerInfo*<br/>
NULL değilse, `OnEvent` `pTarget` `pmf` `AFX_CMDHANDLERINFO` komutu dağıtma yerine yapının ve üyelerini doldurur. Genellikle, bu parametre NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Olay işlenirse sıfır dışında sıfır.

### <a name="remarks"></a>Açıklamalar

Varsayılan olay işleme işlemini özelleştirmek için bu işlevi geçersiz kılın.

## <a name="coccmanagerprecreatedialog"></a><a name="precreatedialog"></a> COccManager::P reCreateDialog

Asıl iletişim kutusunu oluşturmadan önce ActiveX denetimleri için bir iletişim kutusu şablonunu işlemek üzere Framework tarafından çağırılır.

```
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,
    const DLGTEMPLATE* pOrigTemplate);
```

### <a name="parameters"></a>Parametreler

*Poccdialogınfo*<br/>
İletişim kutusu `_AFX_OCC_DIALOG_INFO` şablonu ve iletişim kutusu tarafından barındırılan tüm ActiveX denetimleri hakkında bilgi içeren bir yapı.

*pOrigTemplate*<br/>
İletişim kutusunu oluştururken kullanılacak iletişim kutusu şablonuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunu oluşturmak için kullanılan iletişim kutusu şablonu yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranış öğesine bir çağrı yapar `SplitDialogTemplate` , varsa ActiveX denetimleri olup olmadığını belirler ve ardından sonuç iletişim kutusu şablonunu döndürür.

ActiveX denetimlerini barındıran bir iletişim kutusu oluşturma işlemini özelleştirmek için bu işlevi geçersiz kılın.

## <a name="coccmanagerpostcreatedialog"></a><a name="postcreatedialog"></a> COccManager::P ostCreateDialog

İletişim kutusu şablonu için ayrılan belleği boşaltmak için Framework tarafından çağırılır.

```
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Parametreler

*Poccdialogınfo*<br/>
İletişim kutusu `_AFX_OCC_DIALOG_INFO` şablonu ve iletişim kutusu tarafından barındırılan tüm ActiveX denetimleri hakkında bilgi içeren bir yapı.

### <a name="remarks"></a>Açıklamalar

Bu bellek, öğesine yapılan bir çağrı tarafından ayrıldı `SplitDialogTemplate` ve iletişim kutusundaki barındırılan tüm ActiveX denetimleri için kullanıldı.

İletişim kutusu nesnesi tarafından kullanılan tüm kaynakları temizleme işlemini özelleştirmek için bu işlevi geçersiz kılın.

## <a name="coccmanagersetdefaultbutton"></a><a name="setdefaultbutton"></a> COccManager:: SetDefaultButton

Denetimi varsayılan düğme olarak ayarlamak için bu işlevi çağırın.

```
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,
    BOOL bDefault);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Denetimi içeren pencereye yönelik bir işaretçi.

*bDefault*<br/>
Denetimin varsayılan düğme olması halinde sıfır dışı; Aksi halde sıfır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Denetimde OLEMISC_ACTSLIKEBUTTON durum biti ayarlanmış olmalıdır. OLEMISC bayrakları hakkında daha fazla bilgi için Windows SDK [Olemisc](/windows/win32/api/oleidl/ne-oleidl-olemisc) konusuna bakın.

## <a name="coccmanagersplitdialogtemplate"></a><a name="splitdialogtemplate"></a> COccManager:: SplitDialogTemplate

Ortak iletişim kutusu denetimlerinden ActiveX denetimlerini ayırmak için Framework tarafından çağırılır.

```
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,
    DLGITEMTEMPLATE** ppOleDlgItems);
```

### <a name="parameters"></a>Parametreler

*pTemplate*<br/>
İncelenen iletişim kutusu şablonuna yönelik bir işaretçi.

*ppOleDlgItems*<br/>
ActiveX denetimleri olan iletişim kutusu öğelerine yönelik işaretçilerin listesi.

### <a name="return-value"></a>Dönüş Değeri

Yalnızca ActiveX olmayan denetimleri içeren bir iletişim kutusu şablonu yapısına yönelik bir işaretçi. Hiçbir ActiveX denetimi yoksa, NULL döndürülür.

### <a name="remarks"></a>Açıklamalar

Herhangi bir ActiveX denetimi bulunursa, şablon çözümlenir ve yalnızca ActiveX olmayan denetimleri içeren yeni bir şablon oluşturulur. Bu işlem sırasında bulunan tüm ActiveX denetimleri *ppOleDlgItems* öğesine eklenir.

Şablonda ActiveX denetimi yoksa, NULL döndürülür *.*

> [!NOTE]
> Yeni şablon için ayrılan bellek, işlevde serbest bırakılır `PostCreateDialog` .

Bu işlemi özelleştirmek için bu işlevi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Cotacontrolsite sınıfı](../../mfc/reference/colecontrolsite-class.md)<br/>
[Cotacontrolcontainer sınıfı](../../mfc/reference/colecontrolcontainer-class.md)
