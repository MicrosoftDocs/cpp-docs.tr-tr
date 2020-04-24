---
title: COlePropertyPage Sınıfı
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
ms.openlocfilehash: 872ade08438e54098da730012f98cdd906483887
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753796"
---
# <a name="colepropertypage-class"></a>COlePropertyPage Sınıfı

Özel denetimözelliklerini bir iletişim kutusuna benzer bir grafik arabiriminde görüntülemek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE COlePropertyPage : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COlePropertyPage::COlePropertyPage](#colepropertypage)|Bir `COlePropertyPage` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COlePropertyPage::GetControlStatus](#getcontrolstatus)|Kullanıcının denetimdeki değeri değiştirip değiştirmediğini gösterir.|
|[COlePropertyPage::GetObjectArray](#getobjectarray)|Özellik sayfası tarafından düzenlenen nesne dizisini döndürür.|
|[COlePropertyPage::GetPageSite](#getpagesite)|Özellik sayfasının `IPropertyPageSite` arabirimine bir işaretçi döndürür.|
|[COlePropertyPage::IgnoreApply](#ignoreapply)|Hangi denetimlerin Uygula düğmesini etkinleştirmediğini belirler.|
|[COlePropertyPage::Değiştirilmiştir](#ismodified)|Kullanıcının özellik sayfasını değiştirip değiştirmediğini gösterir.|
|[COlePropertyPage::OnEditProperty](#oneditproperty)|Kullanıcı bir özelliği düzenlediğinde çerçeve tarafından çağrılır.|
|[COlePropertyPage::OnHelp](#onhelp)|Kullanıcı yardım çağırdığında çerçeve tarafından çağrılır.|
|[COlePropertyPage::OnInitDialog](#oninitdialog)|Özellik sayfası başharfe çevrilirken çerçeve tarafından çağrılır.|
|[COlePropertyPage::OnObjectsChanged](#onobjectschanged)|Yeni özelliklere sahip başka bir OLE denetimi seçildiğinde çerçeve tarafından çağrılır.|
|[COlePropertyPage::OnSetPageSite](#onsetpagesite)|Özellik çerçevesi sayfanın sitesini sağladığında çerçeve tarafından çağrılır.|
|[COlePropertyPage::SetControlStatus](#setcontrolstatus)|Kullanıcının denetimdeki değeri değiştirip değiştirmediğini belirten bir bayrak ayarlar.|
|[COlePropertyPage::SetDialogResource](#setdialogresource)|Özellik sayfasının iletişim kaynağını ayarlar.|
|[COleEmlakPage::SetHelpInfo](#sethelpinfo)|Özellik sayfasının kısa yardım metnini, yardım dosyasının adını ve yardım bağlamını ayarlar.|
|[COlePropertyPage::SetModifiedFlag](#setmodifiedflag)|Kullanıcının özellik sayfasını değiştirip değiştirmediğini belirten bir bayrak ayarlar.|
|[COlePropertyPage::SetPageName](#setpagename)|Özellik sayfasının adını (resim yazısı) ayarlar.|

## <a name="remarks"></a>Açıklamalar

Örneğin, bir özellik sayfası, kullanıcının denetimin resim yazısı özelliğini görüntülemesine ve değiştirmesine olanak tanıyan bir denetim içerebilir.

Her özel veya stok denetimi özelliği, denetimin kullanıcısının geçerli özellik değerini görüntülemesine ve gerekirse bu değeri değiştirmesine olanak tanıyan bir iletişim denetimine sahip olabilir.

Kullanma `COlePropertyPage`hakkında daha fazla bilgi için [ActiveX Denetimleri makalesine bakın: Özellik Sayfaları.](../../mfc/mfc-activex-controls-property-pages.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

`COlePropertyPage`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxctl.h

## <a name="colepropertypagecolepropertypage"></a><a name="colepropertypage"></a>COlePropertyPage::COlePropertyPage

Bir `COlePropertyPage` nesne inşa eder.

```
COlePropertyPage(
    UINT idDlg,
    UINT idCaption);
```

### <a name="parameters"></a>Parametreler

*idDlg*<br/>
İletişim şablonunun kaynak kimliği.

*idCaption*<br/>
Özellik sayfasının başlığının kaynak kimliği.

### <a name="remarks"></a>Açıklamalar

Bir alt sınıf `COlePropertyPage`uyguladığınızda, alt sınıfının oluşturucusu, özellik sayfasının temel aldığı iletişim şablonu kaynağını ve alt yazı sını içeren dize kaynağını tanımlamak için `COlePropertyPage` oluşturucuyu kullanmalıdır.

## <a name="colepropertypagegetcontrolstatus"></a><a name="getcontrolstatus"></a>COlePropertyPage::GetControlStatus

Kullanıcının özellik sayfası denetiminin değerini belirtilen kaynak kimliğiyle değiştirip değiştirmediğini belirler.

```
BOOL GetControlStatus(UINT nID);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Özellik sayfası denetiminin kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

Denetim değeri değiştirildiyse DOĞRU; aksi takdirde YANLIŞ.

## <a name="colepropertypagegetobjectarray"></a><a name="getobjectarray"></a>COlePropertyPage::GetObjectArray

Özellik sayfası tarafından düzenlenen nesne dizisini döndürür.

```
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```

### <a name="parameters"></a>Parametreler

*pnNesneler*<br/>
Sayfa tarafından düzenlenen nesne sayısını alacak imzasız uzun bir sayama işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfasındaki `IDispatch` her denetimin özelliklerine erişmek için kullanılan bir dizi işaretçiye işaretçi. Arayan bu arabirim işaretçilerini serbest bırakmamalıdır.

### <a name="remarks"></a>Açıklamalar

Her özellik sayfası nesnesi, sayfa `IDispatch` tarafından düzenlenen nesnelerin arabirimlerine işaretçiler dizisi tutar. Bu *işlev, pnObjects* bağımsız değişkenini bu dizideki öğe sayısına ayarlar ve bir işaretçiyi dizinin ilk öğesine döndürür.

## <a name="colepropertypagegetpagesite"></a><a name="getpagesite"></a>COlePropertyPage::GetPageSite

Özellik sayfasının `IPropertyPageSite` arabirimine bir işaretçi alır.

```
LPPROPERTYPAGESITE GetPageSite();
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfasının `IPropertyPageSite` arabirimine işaretçi.

### <a name="remarks"></a>Açıklamalar

Denetimler ve kapsayıcılar, kullanıcıların denetim özelliklerine göz atabilmesi ve düzenlemesi için işbirliği yapar. Denetim, her biri kullanıcının ilgili bir özellik kümesini ayarlamasına olanak tanıyan bir OLE nesnesi olan özellik sayfaları sağlar. Kapsayıcı özellik sayfalarını görüntüleyen bir özellik çerçevesi sağlar. Her sayfa için özellik `IPropertyPageSite` çerçevesi, arabirimi destekleyen bir sayfa sitesi sağlar.

## <a name="colepropertypageignoreapply"></a><a name="ignoreapply"></a>COlePropertyPage::IgnoreApply

Hangi denetimlerin Uygula düğmesini etkinleştirmediğini belirler.

```cpp
void IgnoreApply(UINT nID);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Denetimin kimliği yoksayıldı.

### <a name="remarks"></a>Açıklamalar

Özellik sayfasının Uygula düğmesi yalnızca özellik sayfası denetimlerinin değerleri değiştirildiğinde etkinleştirilir. Değerleri değiştiğinde Uygula düğmesinin etkinleştirilmesine neden olmayan denetimleri belirtmek için bu işlevi kullanın.

## <a name="colepropertypageismodified"></a><a name="ismodified"></a>COlePropertyPage::Değiştirilmiştir

Kullanıcının özellik sayfasındaki değerleri değiştirip değiştirmediğini belirler.

```
BOOL IsModified();
```

### <a name="return-value"></a>Dönüş Değeri

Özellik sayfası değiştirildiyse DOĞRU.

## <a name="colepropertypageoneditproperty"></a><a name="oneditproperty"></a>COlePropertyPage::OnEditProperty

Çerçeve, belirli bir özellik düzenlenecekse bu işlevi çağırır.

```
virtual BOOL OnEditProperty(DISPID dispid);
```

### <a name="parameters"></a>Parametreler

*Dıspıd*<br/>
Düzenlenen özelliğin sevk kimliği.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama FALSE döndürür. Bu işlevin geçersiz kılar DOĞRU döndürmelidir.

### <a name="remarks"></a>Açıklamalar

Sayfadaki uygun denetime odak ayarlamak için bunu geçersiz kılabilirsiniz. Varsayılan uygulama hiçbir şey yapmaz ve FALSE döndürür.

## <a name="colepropertypageonhelp"></a><a name="onhelp"></a>COlePropertyPage::OnHelp

Kullanıcı çevrimiçi yardım istediğinde çerçeve bu işlevi çağırır.

```
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```

### <a name="parameters"></a>Parametreler

*lpszHelpDir*<br/>
Özellik sayfasının yardım dosyasını içeren dizin.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı yardıma erişirken özellik sayfanızın herhangi bir özel eylem gerçekleştirmesi gerekiyorsa geçersiz kılın. Varsayılan uygulama hiçbir şey yapmaz ve winhelp aramak için çerçeve talimatFALSE döndürür.

## <a name="colepropertypageoninitdialog"></a><a name="oninitdialog"></a>COlePropertyPage::OnInitDialog

Özellik sayfasının iletişim kutusu başharfe başlandığında çerçeve bu işlevi çağırır.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan uygulama FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu başolarak başlattığında özel bir eylem gerekiyorsa geçersiz kılın. Varsayılan uygulama `CDialog::OnInitDialog` çağırır ve FALSE döndürür.

## <a name="colepropertypageonobjectschanged"></a><a name="onobjectschanged"></a>COlePropertyPage::OnObjectsChanged

Yeni özelliklere sahip başka bir OLE denetimi seçildiğinde çerçeve tarafından çağrılır.

```
virtual void OnObjectsChanged();
```

### <a name="remarks"></a>Açıklamalar

Geliştirici ortamında bir OLE denetiminin özelliklerini görüntülerken, özellik sayfalarını görüntülemek için modsuz bir iletişim kutusu kullanılır. Başka bir denetim seçilirse, yeni özellik kümesi için farklı bir özellik sayfası kümesinin görüntülenmesi gerekir. Çerçeve, değişikliğin özellik sayfasını bildirmek için bu işlevi çağırır.

Bu eylemin bildirimini almak ve özel eylemler gerçekleştirmek için bu işlevi geçersiz kılın.

## <a name="colepropertypageonsetpagesite"></a><a name="onsetpagesite"></a>COlePropertyPage::OnSetPageSite

Özellik çerçevesi özellik sayfasının sayfa sitesini sağladığında çerçeve bu işlevi çağırır.

```
virtual void OnSetPageSite();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama sayfanın alt yazısını yükler ve iletişim kaynağından sayfanın boyutunu belirlemeye çalışır. Özellik sayfanız başka bir işlem gerektiriyorsa bu işlevi geçersiz kılın; geçersiz kılmanız taban sınıf uygulamasını aramalıdır.

## <a name="colepropertypagesetcontrolstatus"></a><a name="setcontrolstatus"></a>COlePropertyPage::SetControlStatus

Özellik sayfası denetiminin durumunu değiştirir.

```
BOOL SetControlStatus(
    UINT nID,
    BOOL bDirty);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Özellik sayfası denetiminin kimliğini içerir.

*bKirli*<br/>
Özellik sayfasının bir alanı değiştirilmişse belirtir. Alan değiştirildiyse TRUE olarak ayarlayın, değiştirilmemişse FALSE.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU, belirtilen denetim ayarlanmışsa; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası kapatıldığında veya Uygula düğmesi seçildiğinde özellik sayfası denetiminin durumu kirliyse, denetimin özelliği uygun değerle güncelleştirilir.

## <a name="colepropertypagesetdialogresource"></a><a name="setdialogresource"></a>COlePropertyPage::SetDialogResource

Özellik sayfasının iletişim kaynağını ayarlar.

```cpp
void SetDialogResource(HGLOBAL hDialog);
```

### <a name="parameters"></a>Parametreler

*hDialog*<br/>
Özellik sayfasının iletişim kaynağına işleyin.

## <a name="colepropertypagesethelpinfo"></a><a name="sethelpinfo"></a>COleEmlakPage::SetHelpInfo

Araç ipucu bilgilerini, yardım dosya adını ve özellik sayfanızın yardım bağlamını belirtir.

```cpp
void SetHelpInfo(
    LPCTSTR lpszDocString,
    LPCTSTR lpszHelpFile = NULL,
    DWORD dwHelpContext = 0);
```

### <a name="parameters"></a>Parametreler

*lpszDocString*<br/>
Durum çubuğunda veya başka bir konumda görüntülenmek için kısa yardım bilgilerini içeren bir dize.

*lpszHelpFile*<br/>
Özellik sayfasının yardım dosyasının adı.

*dwHelpContext*<br/>
Özellik sayfası için yardım bağlamı.

## <a name="colepropertypagesetmodifiedflag"></a><a name="setmodifiedflag"></a>COlePropertyPage::SetModifiedFlag

Kullanıcının özellik sayfasını değiştirip değiştirmediğini gösterir.

```cpp
void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Parametreler

*bModideğişiklik*<br/>
Özellik sayfasının değiştirilmiş bayrağı için yeni değeri belirtir.

## <a name="colepropertypagesetpagename"></a><a name="setpagename"></a>COlePropertyPage::SetPageName

Özellik sayfasının adını ayarlar ve özellik çerçevesi genellikle sayfanın sekmesinde görüntülenir.

```cpp
void SetPageName(LPCTSTR lpszPageName);
```

### <a name="parameters"></a>Parametreler

*lpszPageName*<br/>
Özellik sayfasının adını içeren bir dize işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CIRC3](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek TESTYARD](../../overview/visual-cpp-samples.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
