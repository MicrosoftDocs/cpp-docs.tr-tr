---
title: COlePropertyPage sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COlePropertyPage
- AFXCTL/COlePropertyPage
- AFXCTL/COlePropertyPage::COlePropertyPage
- AFXCTL/COlePropertyPage::GetControlStatus
- AFXCTL/COlePropertyPage::GetObjectArray
- AFXCTL/COlePropertyPage::GetPageSite
- AFXCTL/COlePropertyPage::OVERWRITEApply
- AFXCTL/COlePropertyPage::IsModified
- AFXCTL/COlePropertyPage::OnEditProperty
- AFXCTL/COlePropertyPage::OnHelp
- AFXCTL/COlePropertyPage::OnInitDialog
- AFXCTL/COlePropertyPage::OnObjectsChanged
- AFXCTL/COlePropertyPage::OnSetPageSite
- AFXCTL/COlePropertyPage::SetControlStatus
- AFXCTL/COlePropertyPage::SetDialogResource
- AFXCTL/COlePropertyPage::SetHelpInfo
- AFXCTL/COlePropertyPage::SetModifiedFlag
- AFXCTL/COlePropertyPage::SetPageName
dev_langs:
- C++
helpviewer_keywords:
- COlePropertyPage [MFC], COlePropertyPage
- COlePropertyPage [MFC], GetControlStatus
- COlePropertyPage [MFC], GetObjectArray
- COlePropertyPage [MFC], GetPageSite
- COlePropertyPage [MFC], IgnoreApply
- COlePropertyPage [MFC], IsModified
- COlePropertyPage [MFC], OnEditProperty
- COlePropertyPage [MFC], OnHelp
- COlePropertyPage [MFC], OnInitDialog
- COlePropertyPage [MFC], OnObjectsChanged
- COlePropertyPage [MFC], OnSetPageSite
- COlePropertyPage [MFC], SetControlStatus
- COlePropertyPage [MFC], SetDialogResource
- COlePropertyPage [MFC], SetHelpInfo
- COlePropertyPage [MFC], SetModifiedFlag
- COlePropertyPage [MFC], SetPageName
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7db08ae9b9c2899709f4c6511478714869475ae7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386437"
---
# <a name="colepropertypage-class"></a>COlePropertyPage sınıfı

Özel bir denetimin özelliklerini iletişim kutusuna benzer bir grafik arabiriminde görüntülemek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE COlePropertyPage : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COlePropertyPage::COlePropertyPage](#colepropertypage)|Oluşturur bir `COlePropertyPage` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COlePropertyPage::GetControlStatus](#getcontrolstatus)|Kullanıcının denetimdeki değeri değiştirilmesi olup olmadığını belirtir.|
|[COlePropertyPage::GetObjectArray](#getobjectarray)|Özellik sayfası tarafından düzenlenen nesneler dizisi döndürür.|
|[COlePropertyPage::GetPageSite](#getpagesite)|Özellik sayfasına ait bir işaretçi döndürür `IPropertyPageSite` arabirimi.|
|[COlePropertyPage::IgnoreApply](#ignoreapply)|Uygula düğmesini hangi denetimlerin etkinleştirmeyin belirler.|
|[COlePropertyPage::IsModified](#ismodified)|Kullanıcı özellik sayfası bir değişiklik olup olmadığını gösterir.|
|[COlePropertyPage::OnEditProperty](#oneditproperty)|Kullanıcı bir özelliği düzenlediğinde framework tarafından çağırılır.|
|[COlePropertyPage::OnHelp](#onhelp)|Kullanıcı Yardımı çağırdığında framework tarafından çağırılır.|
|[COlePropertyPage::OnInitDialog](#oninitdialog)|Özellik sayfasını başlatıldığında framework tarafından çağırılır.|
|[COlePropertyPage::OnObjectsChanged](#onobjectschanged)|Yeni özelliklerle başka bir OLE denetimi seçildiğinde framework tarafından çağırılır.|
|[COlePropertyPage::OnSetPageSite](#onsetpagesite)|Özellik çerçevesi sayfanın sitesini sağladığında framework tarafından çağırılır.|
|[COlePropertyPage::SetControlStatus](#setcontrolstatus)|Kullanıcı denetiminde değeri değiştirmiş olup olmadığını belirten bir bayrak ayarlar.|
|[COlePropertyPage::SetDialogResource](#setdialogresource)|Özellik sayfasının iletişim kutusu kaynağı ayarlar.|
|[COlePropertyPage::SetHelpInfo](#sethelpinfo)|Özellik sayfasının kısa Yardım metni, Yardım dosyasını ve onun Yardım içeriği adını ayarlar.|
|[COlePropertyPage::SetModifiedFlag](#setmodifiedflag)|Kullanıcı özellik sayfası bir değişiklik olup olmadığını belirten bir bayrak ayarlar.|
|[COlePropertyPage::SetPageName](#setpagename)|Özellik sayfasının adını (başlık) ayarlar.|

## <a name="remarks"></a>Açıklamalar

Örneğin, bir özellik sayfası görüntüleme ve denetimin resim yazısı özelliğini değiştirme kullanıcıya izin veren bir düzenleme denetimi içerebilir.

Her özel veya stok denetimi özelliği, geçerli özellik değerini görüntüleyin ve gerekirse bu değeri değiştirmek denetimin kullanıcı veren bir iletişim denetimi olabilir.

Kullanma hakkında daha fazla bilgi için `COlePropertyPage`, makaleye göz atın [ActiveX denetimleri: özellik sayfaları](../../mfc/mfc-activex-controls-property-pages.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`COlePropertyPage`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxctl.h

##  <a name="colepropertypage"></a>  COlePropertyPage::COlePropertyPage

Oluşturur bir `COlePropertyPage` nesne.

```
COlePropertyPage(
    UINT idDlg,
    UINT idCaption);
```

### <a name="parameters"></a>Parametreler

*idDlg*<br/>
İletişim şablonu kaynak kimliği.

*idCaption*<br/>
Kaynak Kimliği özelliği sayfa başlığı.

### <a name="remarks"></a>Açıklamalar

Öğesinin uyguladığınızda `COlePropertyPage`, alt sınıfın Oluşturucusu kullanması gereken `COlePropertyPage` oluşturucu üzerinde iletişim şablon kaynağı tanımlamak için özellik sayfası dayalı olarak ve resim yazısını içeren dize kaynağı.

##  <a name="getcontrolstatus"></a>  COlePropertyPage::GetControlStatus

Kullanıcı özellik sayfası denetimi ile belirtilen kaynak kimliği değerini değiştirdi olup olmadığını belirler

```
BOOL GetControlStatus(UINT nID);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Bir özellik sayfası denetimi kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

Denetim değeri değiştirilmişse TRUE; Aksi durumda FALSE.

##  <a name="getobjectarray"></a>  COlePropertyPage::GetObjectArray

Özellik sayfası tarafından düzenlenen nesneler dizisi döndürür.

```
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```

### <a name="parameters"></a>Parametreler

*pnObjects*<br/>
Sayfa tarafından düzenlenmekte olan nesne sayısını alacak bir işaretsiz uzun tamsayı işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Bir dizi işaretçi `IDispatch` her denetimin özellik sayfasında özelliklerine erişmek için kullanılan işaretçisi. Çağıranın bu arabirim işaretçilerini serbest gerekir.

### <a name="remarks"></a>Açıklamalar

Her özellik sayfa nesnesi bir işaretçiler dizisi tutar `IDispatch` arabirimleri sayfanın düzenlenmekte olan nesne. Bu işlev ayarlar kendi *pnObjects* bağımsız değişkeni, dizideki öğelerin sayısını ve dizinin ilk öğesi için bir işaretçi döndürür.

##  <a name="getpagesite"></a>  COlePropertyPage::GetPageSite

Özellik sayfasına ait bir işaretçi alır `IPropertyPageSite` arabirimi.

```
LPPROPERTYPAGESITE GetPageSite();
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfasının bir işaretçiye `IPropertyPageSite` arabirimi.

### <a name="remarks"></a>Açıklamalar

Kullanıcıların göz atın ve denetim özelliklerini düzenleme denetimleri ve kapsayıcıları işbirliği yapar. Özellik sayfaları, her biri kullanıcının ilgili bir özellikler kümesini düzenlemesine izin veren bir OLE nesnesi olan bir denetim sağlar. Kapsayıcı özellik sayfalarını görüntüler özelliği bir çerçeve sağlar. Her bir sayfa için özellik çerçevesi destekleyen bir sayfa site sağlar `IPropertyPageSite` arabirimi.

##  <a name="ignoreapply"></a>  COlePropertyPage::IgnoreApply

Uygula düğmesini hangi denetimlerin etkinleştirmeyin belirler.

```
void IgnoreApply(UINT nID);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Yok sayılacak denetiminin kimliği.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası denetimlerin değerleri yalnızca değiştirilmiş olduğunda özellik Sayfa Uygula düğmesi etkinleştirilir. Uygula düğmesini değerlerine değiştirdiğinizde etkinleştirilmesini neden olmaz denetimleri belirlemek için bu işlevi kullanın.

##  <a name="ismodified"></a>  COlePropertyPage::IsModified

Kullanıcının herhangi bir değeri özellik sayfasında değiştirilip değiştirilmediğini belirler.

```
BOOL IsModified();
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfasını değiştirilmişse TRUE.

##  <a name="oneditproperty"></a>  COlePropertyPage::OnEditProperty

Belirli bir özelliğine düzenlenecek olduğunda framework bu işlevi çağırır.

```
virtual BOOL OnEditProperty(DISPID dispid);
```

### <a name="parameters"></a>Parametreler

*DISPID*<br/>
Düzenlenmekte olan özellik kimliği gönderme.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama false değerini döndürür. Bu işlevin geçersiz kılmaları TRUE döndürmelidir.

### <a name="remarks"></a>Açıklamalar

Sayfasında uygun denetim odağı koymak için geçersiz kılabilirsiniz. Varsayılan uygulama, hiçbir şey yapmaz ve false değerini döndürür.

##  <a name="onhelp"></a>  COlePropertyPage::OnHelp

Kullanıcının çevrimiçi Yardım istediğinde framework bu işlevi çağırır.

```
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```

### <a name="parameters"></a>Parametreler

*lpszHelpDir*<br/>
Özellik sayfasının Yardım dosyasını içeren dizin.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı Yardım eriştiğinde, özellik sayfası özel bir eylem gerçekleştirmeniz gerekirse geçersiz kılar. Varsayılan uygulama, hiçbir şey yapmaz ve WinHelp çağırmak için framework bildirir false değerini döndürür.

##  <a name="oninitdialog"></a>  COlePropertyPage::OnInitDialog

Özellik sayfasının iletişim başlatıldığında framework bu işlevi çağırır.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İletişim başlatılırken özel bir eylem gerekmiyorsa, geçersiz kılar. Varsayılan Uygulama çağrıları `CDialog::OnInitDialog` ve false değerini döndürür.

##  <a name="onobjectschanged"></a>  COlePropertyPage::OnObjectsChanged

Yeni özelliklerle başka bir OLE denetimi seçildiğinde framework tarafından çağırılır.

```
virtual void OnObjectsChanged();
```

### <a name="remarks"></a>Açıklamalar

Geliştirici Ortamı'ndaki bir OLE denetim özelliklerini görüntülerken, modsuz iletişim kutusu, özellik sayfaları görüntülemek için kullanılır. Başka bir denetim seçili durumdayken, farklı bir dizi özellik sayfası için yeni özellikler kümesini görüntülenmesi gerekir. Framework özellik sayfası değişikliğinin bildirmek için bu işlevi çağırır.

Bu eylem bildirim alacak ve özel eylemleri gerçekleştirmek için bu işlevi geçersiz kılar.

##  <a name="onsetpagesite"></a>  COlePropertyPage::OnSetPageSite

Özellik çerçevesi özelliği sayfanın sayfanın sitesini sağladığında framework bu işlevi çağırır.

```
virtual void OnSetPageSite();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, sayfanın başlığı yükler ve iletişim kutusu kaynağı sayfanın boyutunu belirlemeye çalışır. Başka bir eylem, özellik sayfası gerektiriyorsa, bu işlev geçersiz kılınamıyor; geçersiz kılma temel sınıf uygulamasını çağırmanız gerekir.

##  <a name="setcontrolstatus"></a>  COlePropertyPage::SetControlStatus

Bir özellik sayfası denetiminin durumunu değiştirir.

```
BOOL SetControlStatus(
    UINT nID,
    BOOL bDirty);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Bir özellik sayfası denetimi Kimliğini içerir.

*bDirty*<br/>
Özellik sayfasının bir alan değiştirilip değiştirilmediğini belirtir. Alan değiştirilmiş FALSE değil değiştirilmişse TRUE olarak ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen denetim ayarlandıysa TRUE, Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Uygula düğmesini seçilir ya da özellik sayfasını kapalı bir özellik sayfası denetimi durumunu kirli denetimin özellik uygun değeri ile güncelleştirilecektir.

##  <a name="setdialogresource"></a>  COlePropertyPage::SetDialogResource

Özellik sayfasının iletişim kutusu kaynağı ayarlar.

```
void SetDialogResource(HGLOBAL hDialog);
```

### <a name="parameters"></a>Parametreler

*hDialog*<br/>
Özellik sayfasının iletişim kaynağına işleyin.

##  <a name="sethelpinfo"></a>  COlePropertyPage::SetHelpInfo

Araç ipucu bilgisini ve Yardım dosya adı, özellik sayfası için Yardım içeriği belirtir.

```
void SetHelpInfo(
    LPCTSTR lpszDocString,
    LPCTSTR lpszHelpFile = NULL,
    DWORD dwHelpContext = 0);
```

### <a name="parameters"></a>Parametreler

*lpszDocString*<br/>
Görüntülenmek üzere bir durum çubuğu veya başka bir konuma kısa Yardım bilgilerini içeren bir dize.

*lpszHelpFile*<br/>
Özellik sayfasının Yardım dosyasının adı.

*dwHelpContext*<br/>
Özellik sayfası için Yardım bağlamı.

##  <a name="setmodifiedflag"></a>  COlePropertyPage::SetModifiedFlag

Kullanıcı özellik sayfası bir değişiklik olup olmadığını gösterir.

```
void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Parametreler

*bModified*<br/>
Yeni özellik sayfa değiştirilmiş bayrağı için bir değer belirtir.

##  <a name="setpagename"></a>  COlePropertyPage::SetPageName

Özellik çerçevesi sayfanın sekmesinde genellikle görüntüler özellik sayfasının adını ayarlar.

```
void SetPageName(LPCTSTR lpszPageName);
```

### <a name="parameters"></a>Parametreler

*lpszPageName*<br/>
Özellik sayfasının adını içeren bir dize işaretçisi.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek CIRC3](../../visual-cpp-samples.md)<br/>
[MFC örnek TESTHELP](../../visual-cpp-samples.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
