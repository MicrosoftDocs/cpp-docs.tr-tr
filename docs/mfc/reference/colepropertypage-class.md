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
ms.openlocfilehash: e8328fb4987044c5a28b1a6a6ce19c674039dea9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="colepropertypage-class"></a>COlePropertyPage sınıfı
Bir iletişim kutusu için benzer bir grafik arabiriminde bir özel denetim özelliklerini görüntülemek için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class AFX_NOVTABLE COlePropertyPage : public CDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COlePropertyPage::COlePropertyPage](#colepropertypage)|Oluşturan bir `COlePropertyPage` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COlePropertyPage::GetControlStatus](#getcontrolstatus)|Kullanıcı denetimi değerinde değiştirdi olup olmadığını gösterir.|  
|[COlePropertyPage::GetObjectArray](#getobjectarray)|Özellik sayfası tarafından düzenlenen nesneler dizisi döndürür.|  
|[COlePropertyPage::GetPageSite](#getpagesite)|Özellik sayfasına ait bir işaretçi döndüren `IPropertyPageSite` arabirimi.|  
|[COlePropertyPage::IgnoreApply](#ignoreapply)|Hangi denetimlerin Uygula düğmesini etkinleştirmeyin belirler.|  
|[COlePropertyPage::IsModified](#ismodified)|Özellik sayfası kullanıcı değiştirdi olup olmadığını gösterir.|  
|[COlePropertyPage::OnEditProperty](#oneditproperty)|Kullanıcı bir özellik düzenlediğinde çerçevesi tarafından çağrılır.|  
|[COlePropertyPage::OnHelp](#onhelp)|Kullanıcı Yardım istediğinde çerçevesi tarafından çağrılır.|  
|[COlePropertyPage::OnInitDialog](#oninitdialog)|Özellik sayfası başlatıldığında çerçevesi tarafından çağrılır.|  
|[COlePropertyPage::OnObjectsChanged](#onobjectschanged)|Yeni özelliklere sahip başka bir OLE Denetim seçildiğinde çerçevesi tarafından çağrılır.|  
|[COlePropertyPage::OnSetPageSite](#onsetpagesite)|Özellik çerçeve sayfanın site sağladığında çerçevesi tarafından çağrılır.|  
|[COlePropertyPage::SetControlStatus](#setcontrolstatus)|Kullanıcı denetimi değerinde değiştirdi olup olmadığını belirten bir bayrak ayarlar.|  
|[COlePropertyPage::SetDialogResource](#setdialogresource)|Özellik sayfasının iletişim kutusu kaynağı ayarlar.|  
|[COlePropertyPage::SetHelpInfo](#sethelpinfo)|Özellik sayfasının kısa Yardım metni, Yardım dosyasını ve onun Yardım içeriği adını ayarlar.|  
|[COlePropertyPage::SetModifiedFlag](#setmodifiedflag)|Özellik sayfası kullanıcı değiştirdi olup olmadığını belirten bir bayrak ayarlar.|  
|[COlePropertyPage::SetPageName](#setpagename)|Özellik sayfasının adı (başlık) ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin, bir özellik sayfası görüntülemek ve denetimin resim yazısı özelliğini değiştirmek kullanıcının sağlayan bir düzenleme denetimi içerebilir.  
  
 Her özel veya stok denetim özelliği geçerli değerini görüntülemek ve gerekirse bu değeri değiştirmek denetimin kullanıcı sağlayan bir iletişim kutusu denetimi olabilir.  
  
 Kullanma hakkında daha fazla bilgi için `COlePropertyPage`, makaleye bakın [ActiveX denetimleri: özellik sayfaları](../../mfc/mfc-activex-controls-property-pages.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `COlePropertyPage`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxctl.h  
  
##  <a name="colepropertypage"></a>  COlePropertyPage::COlePropertyPage  
 Oluşturan bir `COlePropertyPage` nesnesi.  
  
```  
COlePropertyPage(
    UINT idDlg,  
    UINT idCaption);
```  
  
### <a name="parameters"></a>Parametreler  
 *idDlg*  
 İletişim şablonu kaynak kimliği.  
  
 *idCaption*  
 Kaynak Kimliği özelliği sayfanın başlığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğesinin bir alt kümesi uygulayan zaman `COlePropertyPage`, alt sınıfın Oluşturucusu kullanması gereken `COlePropertyPage` üzerinde iletişim şablon kaynağı tanımlamak için Oluşturucusu özellik sayfası temel alır ve kendi resim yazısını içeren dize kaynağı.  
  
##  <a name="getcontrolstatus"></a>  COlePropertyPage::GetControlStatus  
 Kullanıcı belirtilen kaynak kimliğiyle özellik sayfası denetiminin değeri değiştirdi olup olmadığını belirler  
  
```  
BOOL GetControlStatus(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Özellik sayfası denetimi kaynak kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** denetim değeri olması durumunda, aksi değiştirilmiş **FALSE**.  
  
##  <a name="getobjectarray"></a>  COlePropertyPage::GetObjectArray  
 Özellik sayfası tarafından düzenlenen nesneler dizisi döndürür.  
  
```  
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```  
  
### <a name="parameters"></a>Parametreler  
 `pnObjects`  
 Sayfa tarafından düzenlenen nesne sayısı alacak imzalanmamış uzun tamsayı işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir dizi işaretçi `IDispatch` özellik sayfasında her denetim özelliklerine erişmek için kullanılan işaretçileri. Çağıranın bu arabirim işaretçileri sürüm değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Her özellik sayfası nesnesi bir dizi işaretçiler tutar `IDispatch` sayfa tarafından düzenlenen nesnelerin arabirimleri. Bu işlev ayarlar kendi `pnObjects` o dizideki öğeler sayıda bağımsız değişken ve dizinin ilk öğesi için bir işaretçi döndürür.  
  
##  <a name="getpagesite"></a>  COlePropertyPage::GetPageSite  
 Özellik sayfasına ait bir işaretçi alır `IPropertyPageSite` arabirimi.  
  
```  
LPPROPERTYPAGESITE GetPageSite();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özellik sayfasının bir işaretçi `IPropertyPageSite` arabirimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Böylece kullanıcılar göz atın ve denetim özelliklerini düzenleme denetimleri ve kapsayıcıları işbirliği yapar. Özellik sayfaları, her biri ilgili bir özellikler kümesi düzenlemesine olanak tanır bir OLE nesnedir denetimi sağlar. Kapsayıcı özellik sayfalarını görüntüleyen bir özellik çerçevesi sağlar. Her bir sayfa için özellik çerçevesini destekleyen bir sayfa site sağlar `IPropertyPageSite` arabirimi.  
  
##  <a name="ignoreapply"></a>  COlePropertyPage::IgnoreApply  
 Hangi denetimlerin Uygula düğmesini etkinleştirmeyin belirler.  
  
```  
void IgnoreApply(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Yok sayılacak denetimi kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik sayfası denetimleri değerleri yalnızca değiştirdikten sonra özellik sayfanın Uygula düğmesi etkinleştirilir. Değerlerine değiştirdiğinizde etkinleştirilmesi için Uygula düğmesini neden olmaz denetimleri belirtmek için bu işlevi kullanın.  
  
##  <a name="ismodified"></a>  COlePropertyPage::IsModified  
 Kullanıcının herhangi bir değeri özellik sayfasında değiştirilip değiştirilmediğini belirler.  
  
```  
BOOL IsModified();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** özellik sayfası değiştirdiyseniz.  
  
##  <a name="oneditproperty"></a>  COlePropertyPage::OnEditProperty  
 Belirli bir özellik düzenlenmesi olduğunda framework bu işlevi çağırır.  
  
```  
virtual BOOL OnEditProperty(DISPID dispid);
```  
  
### <a name="parameters"></a>Parametreler  
 `dispid`  
 Düzenlenen özelliği gönderme kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama döndürür **FALSE**. Bu işlevin geçersiz kılmaları döndürmelidir **doğru**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sayfada uygun denetimi odağı koymak için geçersiz kılabilirsiniz. Varsayılan uygulama hiçbir şey yapmaz ve döndürür **FALSE**.  
  
##  <a name="onhelp"></a>  COlePropertyPage::OnHelp  
 Kullanıcının çevrimiçi Yardım istediğinde framework bu işlevi çağırır.  
  
```  
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszHelpDir*  
 Özellik sayfasının Yardım dosyasının bulunduğu dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama döndürür **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı Yardım eriştiğinde, özellik sayfasında tüm özel eylemleri gerçekleştirmeniz gerekirse geçersiz kılar. Varsayılan uygulama hiçbir şey yapmaz ve döndürür **yanlış**, WinHelp çağrılacak framework talimatı verir.  
  
##  <a name="oninitdialog"></a>  COlePropertyPage::OnInitDialog  
 Özellik sayfasının iletişim başlatıldığında framework bu işlevi çağırır.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan uygulama döndürür **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim kutusu başlatıldığında herhangi bir özel eylem gerekli olduğunda geçersiz kılar. Varsayılan Uygulama çağrıları `CDialog::OnInitDialog` ve döndürür **FALSE**.  
  
##  <a name="onobjectschanged"></a>  COlePropertyPage::OnObjectsChanged  
 Yeni özelliklere sahip başka bir OLE Denetim seçildiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnObjectsChanged();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geliştirici ortamında OLE denetimi özelliklerini görüntülerken, kalıcı olmayan iletişim kutusu özellik sayfalarının görüntülemek için kullanılır. Başka bir denetim seçtiyseniz, özellikler yeni küme için farklı bir dizi özellik sayfası görüntülenmesi gerekir. Framework özellik sayfası değişikliği bildirmek için bu işlevi çağırır.  
  
 Bu eylem bildirim almak ve özel eylemleri gerçekleştirmek için bu işlevi geçersiz kılar.  
  
##  <a name="onsetpagesite"></a>  COlePropertyPage::OnSetPageSite  
 Özellik çerçeve özelliği sayfanın sayfa site sağladığında framework bu işlevi çağırır.  
  
```  
virtual void OnSetPageSite();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama sayfanın başlığı yükler ve iletişim kutusu kaynağı sayfa boyutundan belirlemeye çalışır. Özellik sayfası başka bir eylem gerektiriyorsa, bu işlevi geçersiz; geçersiz kılma temel sınıf uygulamayı çağırması gerekir.  
  
##  <a name="setcontrolstatus"></a>  COlePropertyPage::SetControlStatus  
 Özellik sayfası denetimi durumunu değiştirir.  
  
```  
BOOL SetControlStatus(
    UINT nID,  
    BOOL bDirty);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Özellik sayfası denetimi Kimliğini içerir.  
  
 `bDirty`  
 Özellik sayfasının bir alan değiştirilip değiştirilmediğini belirtir. Kümesine **TRUE** alan değiştirilirse **FALSE** değil güncellendiyse.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU**, belirtilen denetim olduysa ayarlayın; Aksi takdirde **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik sayfası denetimi durumunu Uygula düğmesini seçilir ya da özellik sayfası kapalı kirli ise, denetimin özelliğini uygun değeriyle güncelleştirilir.  
  
##  <a name="setdialogresource"></a>  COlePropertyPage::SetDialogResource  
 Özellik sayfasının iletişim kutusu kaynağı ayarlar.  
  
```  
void SetDialogResource(HGLOBAL hDialog);
```  
  
### <a name="parameters"></a>Parametreler  
 *hDialog*  
 Özellik sayfasının iletişim kutusu kaynağı için tanıtıcı.  
  
##  <a name="sethelpinfo"></a>  COlePropertyPage::SetHelpInfo  
 Araç İpucu bilgileri, Yardım filename ve özellik sayfası Yardım bağlamının belirtir.  
  
```  
void SetHelpInfo(
    LPCTSTR lpszDocString,  
    LPCTSTR lpszHelpFile = NULL,  
    DWORD dwHelpContext = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszDocString*  
 Durum çubuğu veya başka bir konuma görüntülemek kısa Yardım bilgilerini içeren bir dize.  
  
 `lpszHelpFile`  
 Özellik sayfasının Yardım dosyasının adı.  
  
 *dwHelpContext*  
 Özellik sayfası için Yardım bağlamı.  
  
##  <a name="setmodifiedflag"></a>  COlePropertyPage::SetModifiedFlag  
 Özellik sayfası kullanıcı değiştirdi olup olmadığını gösterir.  
  
```  
void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bModified`  
 Yeni özellik sayfasının değiştirilmiş bayrağı için bir değer belirtir.  
  
##  <a name="setpagename"></a>  COlePropertyPage::SetPageName  
 Özellik çerçeve genellikle sayfanın sekmesinde görüntülenir özelliği sayfanın adını ayarlar.  
  
```  
void SetPageName(LPCTSTR lpszPageName);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszPageName*  
 İşaretçi özelliği sayfanın adını içeren dize.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CIRC3](../../visual-cpp-samples.md)   
 [MFC örnek TESTHELP](../../visual-cpp-samples.md)   
 [CDialog sınıfı](../../mfc/reference/cdialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
