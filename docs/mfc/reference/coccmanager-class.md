---
title: COccManager sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 10bb10162345453eb9979b985a062dd1e4b595b9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381159"
---
# <a name="coccmanager-class"></a>COccManager sınıfı

Çeşitli özel denetim sitelerini yönetir; tarafından uygulanan `COleControlContainer` ve `COleControlSite` nesneleri.

## <a name="syntax"></a>Sözdizimi

```
class COccManager : public CNoTrackObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COccManager::CreateContainer](#createcontainer)|Oluşturur bir `COleContainer` nesne.|
|[COccManager::CreateDlgControls](#createdlgcontrols)|ActiveX denetimleri, ilişkili tarafından barındırılan oluşturur `COleContainer` nesne.|
|[COccManager::CreateSite](#createsite)|Oluşturur bir `COleClientSite` nesne.|
|[COccManager::GetDefBtnCode](#getdefbtncode)|Varsayılan düğme kodunu alır.|
|[COccManager::IsDialogMessage](#isdialogmessage)|Bir iletişim kutusu iletisinin hedefini belirler.|
|[COccManager::IsLabelControl](#islabelcontrol)|Belirtilen denetiminin etiket denetimi olduğunu belirler.|
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|Geçerli anımsatıcı belirtilen denetiminin anımsatıcı eşleşip eşleşmediğini belirler.|
|[COccManager::OnEvent](#onevent)|Belirtilen olayı işlemek çalışır.|
|[COccManager::PostCreateDialog](#postcreatedialog)|İletişim kutusu oluşturma sırasında ayrılan kaynakları serbest bırakır.|
|[COccManager::PreCreateDialog](#precreatedialog)|ActiveX denetimleri için bir iletişim şablonunu işler.|
|[COccManager::SetDefaultButton](#setdefaultbutton)|Belirtilen denetimi varsayılan duruma geçer.|
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|Varolan bir ActiveX denetimleri belirtilen iletişim şablonunda ortak denetimleri ayırır.|

## <a name="remarks"></a>Açıklamalar

Temel sınıfı, `CNoTrackObject`, (AFXTLS içinde bulunur. belgelenmemiş bir taban sınıfı H). Türetilmiş sınıflar MFC çerçevesi tarafından kullanılmak üzere tasarlanan `CNoTrackObject` bellek sızıntısı algılamadan muaf sınıfı. Doğrudan öğesinden türetilen önerilmez `CNoTrackObject`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CNoTrackObject`

`COccManager`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxocc.h

##  <a name="createcontainer"></a>  COccManager::CreateContainer

Bir denetim kapsayıcısı oluşturmak için framework tarafından çağırılır.

```
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Özel site kapsayıcı ile ilişkili pencere nesnesi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan kapsayıcı için bir işaretçi; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Özel site oluşturma ile ilgili daha fazla bilgi için bkz: [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite).

##  <a name="createdlgcontrols"></a>  COccManager::CreateDlgControls

Tarafından belirtilen ActiveX denetimleri oluşturmak için bu işlevi çağırın *pOccDialogInfo* parametresi.

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
İletişim nesnenin üst öğeye bir işaretçi.

*lpszResourceName*<br/>
Oluşturulan kaynak adı.

*pOccDialogInfo*<br/>
İletişim nesnesi oluşturmak için kullanılan iletişim şablonu için bir işaretçi.

*lpResource*<br/>
Bir kaynağa bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Denetim başarıyla oluşturuldu olursa sıfır dışı; Aksi halde sıfır.

##  <a name="createsite"></a>  COccManager::CreateSite

İşaret ettiği kapsayıcı tarafından barındırılan bir denetim site oluşturmak için framework tarafından çağırılır *pCtrlCont*.

```
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>Parametreler

*pCtrlCont*<br/>
Yeni Denetim site barındırma denetimi kapsayıcısı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan denetime site için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Özel bir denetim oluşturmak için bu işlevi geçersiz kılma kullanarak, site, [COleControlSite](../../mfc/reference/colecontrolsite-class.md)-türetilmiş sınıf.

Her bir denetim kapsayıcısı birden çok site barındırma. Ek siteler birden çok çağrı oluşturmak `CreateSite`.

##  <a name="getdefbtncode"></a>  COccManager::GetDefBtnCode

Denetimi varsayılan düğme olup olmadığını belirlemek için bu işlevi çağırın.

```
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Düğme denetimini içeren pencere nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri:

- İletişim kutusunda varsayılan düğme DLGC_DEFPUSHBUTTON denetimidir.

- DLGC_UNDEFPUSHBUTTON denetim iletişim kutusunda varsayılan düğme değil.

- **0** denetim bir düğme değil.

##  <a name="isdialogmessage"></a>  COccManager::IsDialogMessage

Bir ileti için belirtilen iletişim kutusu kullanılmaya ise, iletiyi işler olup olmadığını ve belirlemek için framework tarafından çağırılır.

```
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*pWndDlg*<br/>
İletinin hedef iletişim için bir işaretçi.

*lpMsg*<br/>
Bir işaretçi bir `MSG` denetlenecek iletiyi içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

İleti işleme olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranışını `IsDialogMessage` klavye iletileri denetleyecek ve karşılık gelen iletişim kutusu için seçimleri dönüştürün. Örneğin, SEKME tuşuna basıldığında, sonraki denetim veya denetimlerin grubu seçer.

Bu işlev belirtilen bir iletişim kutusuna gönderilen iletiler için özel davranış sağlamak için geçersiz kılın.

##  <a name="islabelcontrol"></a>  COccManager::IsLabelControl

Belirtilen denetiminin etiket denetimi olup olmadığını belirlemek için bu işlevi çağırın.

```
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Denetimi içeren penceresine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Denetimin etiket ise sıfır olmayan; Aksi halde sıfır

### <a name="remarks"></a>Açıklamalar

Etiket denetimi için hangi denetim sıralamada sonraki etiket gibi davranan biridir.

##  <a name="ismatchingmnemonic"></a>  COccManager::IsMatchingMnemonic

Geçerli anımsatıcı denetim tarafından temsil edilen eşleşip eşleşmediğini belirlemek için bu işlevi çağırın.

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
Denetimi içeren penceresine bir işaretçi.

*lpMsg*<br/>
Eşleştirilecek anımsatıcı içeren ileti için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Anımsatıcı denetim eşleşen olursa sıfır dışı; Aksi halde sıfır

### <a name="remarks"></a>Açıklamalar

##  <a name="onevent"></a>  COccManager::OnEvent

Belirtilen olayı işlemek için framework tarafından çağırılır.

```
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,
    UINT idCtrl,
    AFX_EVENT* pEvent,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Parametreler

*pCmdTarget*<br/>
Bir işaretçi `CCmdTarget` olayı işlemek çalışırken nesnesi

*idCtrl*<br/>
Denetim kaynak kimliği.

*pEvent*<br/>
İşlenen olayı.

*pHandlerInfo*<br/>
BOŞ değilse `OnEvent` doldurur `pTarget` ve `pmf` üyeleri `AFX_CMDHANDLERINFO` yapısı yerine komut gönderme. Genellikle, bu parametre NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Aksi halde sıfır olay işlenen olursa sıfır dışı.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan olay işleme işlemi özelleştirmek için geçersiz kılın.

##  <a name="precreatedialog"></a>  COccManager::PreCreateDialog

ActiveX denetimleri için bir iletişim şablonunu gerçek iletişim kutusu oluşturmadan önce işlemek için framework tarafından çağırılır.

```
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,
    const DLGTEMPLATE* pOrigTemplate);
```

### <a name="parameters"></a>Parametreler

*pOccDialogInfo*<br/>
Bir `_AFX_OCC_DIALOG_INFO` iletişim şablonunu ve iletişim kutusu tarafından barındırılan herhangi bir ActiveX denetimleri hakkında bilgi içeren yapıya.

*pOrigTemplate*<br/>
İletişim kutusu oluşturulurken kullanılacak iletişim şablonu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu oluşturmak için kullanılan bir iletişim şablonunu yapısı işaretçisi.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranış çağrıda `SplitDialogTemplate`olması durumunda tüm ActiveX denetimlerini mevcut belirleme ve sonra sonuçta elde edilen bir iletişim şablonunu döndürür.

ActiveX denetimlerini barındırma bir iletişim kutusu oluşturma işlemi özelleştirmek için bu işlevi geçersiz kılar.

##  <a name="postcreatedialog"></a>  COccManager::PostCreateDialog

İletişim şablonu için ayrılan belleği boşaltmak için framework tarafından çağırılır.

```
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Parametreler

*pOccDialogInfo*<br/>
Bir `_AFX_OCC_DIALOG_INFO` iletişim şablonunu ve iletişim kutusu tarafından barındırılan herhangi bir ActiveX denetimleri hakkında bilgi içeren yapıya.

### <a name="remarks"></a>Açıklamalar

Bu bellek için bir çağrı tarafından ayrılmış olan `SplitDialogTemplate`ve iletişim kutusunda barındırılan tüm ActiveX denetimleri için kullanıldı.

Bu işlev iletişim kutusu nesnesi tarafından kullanılan tüm kaynakları temizleme işlemi özelleştirmek için geçersiz kılın.

##  <a name="setdefaultbutton"></a>  COccManager::SetDefaultButton

Denetimi varsayılan düğme olarak ayarlamak için bu işlevi çağırın.

```
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,
    BOOL bDefault);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Denetimi içeren penceresine bir işaretçi.

*bVarsayılan*<br/>
Denetimi varsayılan düğme olacağını olursa sıfır dışı; Aksi halde sıfır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Denetim durumu bit kümesi OLEMISC_ACTSLIKEBUTTON olması gerekir. OLEMISC bayrakları hakkında daha fazla bilgi için bkz. [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) konu başlığında Windows SDK'sı.

##  <a name="splitdialogtemplate"></a>  COccManager::SplitDialogTemplate

Ortak iletişim kutusu denetimleri ActiveX denetimlerini bölmek için framework tarafından çağırılır.

```
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,
    DLGITEMTEMPLATE** ppOleDlgItems);
```

### <a name="parameters"></a>Parametreler

*pTemplate*<br/>
İncelenecek iletişim şablonu için bir işaretçi.

*ppOleDlgItems*<br/>
ActiveX denetimleri iletişim kutusu öğeleri için işaretçiler listesi.

### <a name="return-value"></a>Dönüş Değeri

Yalnızca olmayan ActiveX denetimleri içeren bir iletişim şablonunu yapısı işaretçisi. ActiveX denetim mevcut olması durumunda, NULL döndürülür.

### <a name="remarks"></a>Açıklamalar

Herhangi bir ActiveX denetim bulunan varsa, şablonu analiz edilir ve yalnızca olmayan ActiveX denetimlerini içeren yeni bir şablonu oluşturulur. Bu işlem sırasında bulunan herhangi bir ActiveX denetimini eklenen *ppOleDlgItems*.

Şablonda ActiveX denetimler yoksa NULL döndürülür *.*

> [!NOTE]
>  Yeni şablon serbest bırakılır için ayrılan bellek `PostCreateDialog` işlevi.

Bu işlev, bu işlemi özelleştirmek için geçersiz kılın.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleControlSite Sınıfı](../../mfc/reference/colecontrolsite-class.md)<br/>
[COleControlContainer Sınıfı](../../mfc/reference/colecontrolcontainer-class.md)
