---
title: COlePropertyPage sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 8253b2c2fa6b93ec51c7ede983ef710eed039970
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421095"
---
# <a name="colepropertypage-class"></a>COlePropertyPage sınıfı

Bir iletişim kutusuna benzer şekilde bir grafik arabirimde özel bir denetimin özelliklerini göstermek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE COlePropertyPage : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[COlePropertyPage:: COlePropertyPage](#colepropertypage)|`COlePropertyPage` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[COlePropertyPage:: GetControlStatus](#getcontrolstatus)|Kullanıcının denetimdeki değeri değiştirilip değiştirilmediğini belirtir.|
|[COlePropertyPage:: GetObjectArray](#getobjectarray)|Özellik sayfası tarafından düzenlenmekte olan nesnelerin dizisini döndürür.|
|[COlePropertyPage:: GetPageSite](#getpagesite)|Özellik sayfasının `IPropertyPageSite` arabirimine bir işaretçi döndürür.|
|[COlePropertyPage:: IgnoreApply](#ignoreapply)|Hangi denetimlerin Uygula düğmesini etkinleştirmeyeceğini belirler.|
|[COlePropertyPage:: IsModified](#ismodified)|Kullanıcının özellik sayfasını değiştirilip değiştirilmediğini belirtir.|
|[COlePropertyPage:: OnEditProperty](#oneditproperty)|Kullanıcı bir özelliği düzenlediğinde Framework tarafından çağırılır.|
|[COlePropertyPage:: OnHelp](#onhelp)|Kullanıcı yardım istediğinde framework tarafından çağırılır.|
|[COlePropertyPage:: OnInitDialog](#oninitdialog)|Özellik sayfası başlatıldığında Framework tarafından çağırılır.|
|[COlePropertyPage:: Onnesneler değişti](#onobjectschanged)|Yeni özelliklerle başka bir OLE denetimi seçildiğinde Framework tarafından çağırılır.|
|[COlePropertyPage:: OnSetPageSite](#onsetpagesite)|Özellik çerçevesi sayfanın sitesini sağladığı zaman Framework tarafından çağırılır.|
|[COlePropertyPage:: SetControlStatus](#setcontrolstatus)|Kullanıcının denetimdeki değeri değiştirip değiştirilmediğini belirten bir bayrak ayarlar.|
|[COlePropertyPage:: SetDialogResource](#setdialogresource)|Özellik sayfasının iletişim kaynağını ayarlar.|
|[COlePropertyPage:: SetHelpInfo](#sethelpinfo)|Özellik sayfasının kısa yardım metnini, yardım dosyasının adını ve yardım bağlamını ayarlar.|
|[COlePropertyPage:: SetModifiedFlag](#setmodifiedflag)|Kullanıcının özellik sayfasını değiştirmediğini belirten bir bayrak ayarlar.|
|[COlePropertyPage:: SetPageName](#setpagename)|Özellik sayfasının adını (resim yazısı) ayarlar.|

## <a name="remarks"></a>Açıklamalar

Örneğin, bir özellik sayfası kullanıcının denetimin açıklamalı başlık özelliğini görüntülemesine ve değiştirmesine izin veren bir düzenleme denetimi içerebilir.

Her özel veya hisse senedi denetim özelliği, denetimin kullanıcısının geçerli özellik değerini görüntülemesine ve gerekirse bu değeri değiştirmesine izin veren bir iletişim kutusu denetimine sahip olabilir.

`COlePropertyPage`kullanma hakkında daha fazla bilgi için bkz. [ActiveX denetimleri: Özellik sayfaları](../../mfc/mfc-activex-controls-property-pages.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`COlePropertyPage`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxctl. h

##  <a name="colepropertypage"></a>COlePropertyPage:: COlePropertyPage

`COlePropertyPage` nesnesi oluşturur.

```
COlePropertyPage(
    UINT idDlg,
    UINT idCaption);
```

### <a name="parameters"></a>Parametreler

*ıddlg*<br/>
İletişim kutusu şablonunun kaynak KIMLIĞI.

*ıdcaption*<br/>
Özellik sayfasının başlık başlığının kaynak KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bir `COlePropertyPage`alt sınıfını uyguladığınızda, alt sınıfınızın Oluşturucusu, özellik sayfasının temel aldığı iletişim şablonu kaynağını ve onun başlığını içeren dize kaynağını belirlemek için `COlePropertyPage` oluşturucusunu kullanmalıdır.

##  <a name="getcontrolstatus"></a>COlePropertyPage:: GetControlStatus

Kullanıcının özellik sayfası denetiminin değerini belirtilen kaynak KIMLIĞIYLE değiştirip değiştirilmediğini belirler.

```
BOOL GetControlStatus(UINT nID);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Özellik sayfası denetiminin kaynak KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Denetim değeri değiştirilmişse TRUE; Aksi halde yanlış.

##  <a name="getobjectarray"></a>COlePropertyPage:: GetObjectArray

Özellik sayfası tarafından düzenlenmekte olan nesnelerin dizisini döndürür.

```
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```

### <a name="parameters"></a>Parametreler

*pnObjects*<br/>
Sayfa tarafından düzenlenmekte olan nesne sayısını alacak işaretsiz uzun tamsayı işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfasındaki her bir denetimin özelliklerine erişmek için kullanılan `IDispatch` işaretçileri dizisine yönelik işaretçi. Çağıranın bu arabirim işaretçilerini serbest bırakmamalıdır.

### <a name="remarks"></a>Açıklamalar

Her özellik sayfası nesnesi, sayfa tarafından düzenlenmekte olan nesnelerin `IDispatch` arabirimlerine bir işaretçiler dizisi tutar. Bu işlev, *pnObjects* bağımsız değişkenini bu dizideki öğelerin sayısına ayarlar ve dizinin ilk öğesine bir işaretçi döndürür.

##  <a name="getpagesite"></a>COlePropertyPage:: GetPageSite

Özellik sayfasının `IPropertyPageSite` arabirimine yönelik bir işaretçi alır.

```
LPPROPERTYPAGESITE GetPageSite();
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfasının `IPropertyPageSite` arabirimine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Denetimler ve kapsayıcılar, kullanıcıların denetim özelliklerine gözatabilmeleri ve düzenleyebilmeleri için birlikte çalışır. Denetim, her biri kullanıcının ilgili özellik kümesini düzenlemesine izin veren bir OLE nesnesi olan özellik sayfaları sağlar. Kapsayıcı, özellik sayfalarını görüntüleyen bir özellik çerçevesi sağlar. Her sayfa için, özellik çerçevesi `IPropertyPageSite` arabirimini destekleyen bir sayfa sitesi sağlar.

##  <a name="ignoreapply"></a>COlePropertyPage:: IgnoreApply

Hangi denetimlerin Uygula düğmesini etkinleştirmeyeceğini belirler.

```
void IgnoreApply(UINT nID);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Yok sayılacak denetimin KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Özellik sayfasının Uygula düğmesi yalnızca özellik sayfası denetimlerinin değerleri değiştirildiğinde etkindir. Değerleri değiştiğinde Uygula düğmesinin etkin olmasına neden olmayan denetimleri belirtmek için bu işlevi kullanın.

##  <a name="ismodified"></a>COlePropertyPage:: IsModified

Kullanıcının özellik sayfasında herhangi bir değeri değiştirip değiştirilmediğini belirler.

```
BOOL IsModified();
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfası değiştirilmişse TRUE.

##  <a name="oneditproperty"></a>COlePropertyPage:: OnEditProperty

Belirli bir özellik düzenlenirken Framework bu işlevi çağırır.

```
virtual BOOL OnEditProperty(DISPID dispid);
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
Düzenlenmekte olan özelliğin dağıtım KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama yanlış döndürür. Bu işlevin geçersiz kılmaları TRUE döndürmelidir.

### <a name="remarks"></a>Açıklamalar

Odağı sayfada uygun denetime göre ayarlamak için geçersiz kılabilirsiniz. Varsayılan uygulama hiçbir şey yapmaz ve FALSE döndürür.

##  <a name="onhelp"></a>COlePropertyPage:: OnHelp

Kullanıcı çevrimiçi yardım istediğinde framework bu işlevi çağırır.

```
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```

### <a name="parameters"></a>Parametreler

*lpszHelpDir*<br/>
Özellik sayfasının yardım dosyasını içeren dizin.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama yanlış döndürür.

### <a name="remarks"></a>Açıklamalar

Özellik sayfanız, Kullanıcı yardım 'a eriştiğinde özel bir eylem gerçekleştirmek zorunda ise bunu geçersiz kılın. Varsayılan uygulama hiçbir şey yapmaz ve FALSE döndürür. Bu, çerçeveye WinHelp çağrısını yönlendirir.

##  <a name="oninitdialog"></a>COlePropertyPage:: OnInitDialog

Özellik sayfasının iletişim kutusu başlatıldığında Framework bu işlevi çağırır.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama yanlış döndürür.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu başlatıldığında özel bir eylem gerekliyse Bunu geçersiz kılın. Varsayılan uygulama `CDialog::OnInitDialog` çağırır ve FALSE döndürür.

##  <a name="onobjectschanged"></a>COlePropertyPage:: Onnesneler değişti

Yeni özelliklerle başka bir OLE denetimi seçildiğinde Framework tarafından çağırılır.

```
virtual void OnObjectsChanged();
```

### <a name="remarks"></a>Açıklamalar

Geliştirici ortamında OLE denetiminin özelliklerini görüntülerken, özellik sayfalarını görüntülemek için kalıcı olmayan bir iletişim kutusu kullanılır. Başka bir denetim seçilirse, yeni özellikler kümesi için farklı bir özellik sayfaları kümesi görüntülenmelidir. Framework, değişikliğin Özellik sayfasına bildirimde bulunan bu işlevi çağırır.

Bu eylemin bildirimini almak ve özel eylemler gerçekleştirmek için bu işlevi geçersiz kılın.

##  <a name="onsetpagesite"></a>COlePropertyPage:: OnSetPageSite

Özellik çerçevesi Özellik sayfasının sayfa sitesini sağladığı zaman Framework bu işlevi çağırır.

```
virtual void OnSetPageSite();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama sayfanın başlığını yükler ve iletişim kaynağından sayfanın boyutunu saptamaya çalışır. Özellik sayfanız başka bir eylem gerektiriyorsa bu işlevi geçersiz kılın; geçersiz kılma, temel sınıf uygulamasını çağırmalıdır.

##  <a name="setcontrolstatus"></a>COlePropertyPage:: SetControlStatus

Özellik sayfası denetiminin durumunu değiştirir.

```
BOOL SetControlStatus(
    UINT nID,
    BOOL bDirty);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Özellik sayfası denetiminin KIMLIĞINI içerir.

*bDirty*<br/>
Özellik sayfasının bir alanının değiştirilip değiştirilmediğini belirtir. Alan değiştirildiyse TRUE olarak ayarlayın, bu değer değiştirilmediyse FALSE.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen denetim ayarlandıysa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası kapalıyken veya Uygula düğmesi seçildiğinde bir özellik sayfası denetiminin durumu kirli ise, denetimin özelliği uygun değerle güncelleştirilir.

##  <a name="setdialogresource"></a>COlePropertyPage:: SetDialogResource

Özellik sayfasının iletişim kaynağını ayarlar.

```
void SetDialogResource(HGLOBAL hDialog);
```

### <a name="parameters"></a>Parametreler

*hDialog*<br/>
Özellik sayfasının iletişim kaynağı için tanıtıcı.

##  <a name="sethelpinfo"></a>COlePropertyPage:: SetHelpInfo

Araç ipucu bilgilerini, yardım dosya adını ve özellik sayfanız için yardım bağlamını belirtir.

```
void SetHelpInfo(
    LPCTSTR lpszDocString,
    LPCTSTR lpszHelpFile = NULL,
    DWORD dwHelpContext = 0);
```

### <a name="parameters"></a>Parametreler

*lpszDocString*<br/>
Bir durum çubuğunda veya başka bir konumda görüntülenmek üzere kısa yardım bilgisi içeren bir dize.

*lpszHelpFile*<br/>
Özellik sayfasının yardım dosyasının adı.

*dwHelpContext*<br/>
Özellik sayfası için yardım bağlamı.

##  <a name="setmodifiedflag"></a>COlePropertyPage:: SetModifiedFlag

Kullanıcının özellik sayfasını değiştirilip değiştirilmediğini belirtir.

```
void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Parametreler

*bModified*<br/>
Özellik sayfasının değiştirilmiş bayrağı için yeni değeri belirtir.

##  <a name="setpagename"></a>COlePropertyPage:: SetPageName

Özellik çerçevesinin, genellikle sayfanın sekmesinde görüntüleyeceği Özellik sayfasının adını ayarlar.

```
void SetPageName(LPCTSTR lpszPageName);
```

### <a name="parameters"></a>Parametreler

*lpszPageName*<br/>
Özellik sayfasının adını içeren bir dize işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CIRC3](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek TESTHELP](../../overview/visual-cpp-samples.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
