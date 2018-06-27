---
title: CDocTemplate sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocTemplate
- AFXWIN/CDocTemplate
- AFXWIN/CDocTemplate::CDocTemplate
- AFXWIN/CDocTemplate::AddDocument
- AFXWIN/CDocTemplate::CloseAllDocuments
- AFXWIN/CDocTemplate::CreateNewDocument
- AFXWIN/CDocTemplate::CreateNewFrame
- AFXWIN/CDocTemplate::CreateOleFrame
- AFXWIN/CDocTemplate::CreatePreviewFrame
- AFXWIN/CDocTemplate::GetDocString
- AFXWIN/CDocTemplate::GetFirstDocPosition
- AFXWIN/CDocTemplate::GetNextDoc
- AFXWIN/CDocTemplate::InitialUpdateFrame
- AFXWIN/CDocTemplate::LoadTemplate
- AFXWIN/CDocTemplate::MatchDocType
- AFXWIN/CDocTemplate::OpenDocumentFile
- AFXWIN/CDocTemplate::RemoveDocument
- AFXWIN/CDocTemplate::SaveAllModified
- AFXWIN/CDocTemplate::SetContainerInfo
- AFXWIN/CDocTemplate::SetDefaultTitle
- AFXWIN/CDocTemplate::SetPreviewInfo
- AFXWIN/CDocTemplate::SetServerInfo
dev_langs:
- C++
helpviewer_keywords:
- CDocTemplate [MFC], CDocTemplate
- CDocTemplate [MFC], AddDocument
- CDocTemplate [MFC], CloseAllDocuments
- CDocTemplate [MFC], CreateNewDocument
- CDocTemplate [MFC], CreateNewFrame
- CDocTemplate [MFC], CreateOleFrame
- CDocTemplate [MFC], CreatePreviewFrame
- CDocTemplate [MFC], GetDocString
- CDocTemplate [MFC], GetFirstDocPosition
- CDocTemplate [MFC], GetNextDoc
- CDocTemplate [MFC], InitialUpdateFrame
- CDocTemplate [MFC], LoadTemplate
- CDocTemplate [MFC], MatchDocType
- CDocTemplate [MFC], OpenDocumentFile
- CDocTemplate [MFC], RemoveDocument
- CDocTemplate [MFC], SaveAllModified
- CDocTemplate [MFC], SetContainerInfo
- CDocTemplate [MFC], SetDefaultTitle
- CDocTemplate [MFC], SetPreviewInfo
- CDocTemplate [MFC], SetServerInfo
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a1ee27994a83206b576452d30b108f01c794353
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957565"
---
# <a name="cdoctemplate-class"></a>CDocTemplate sınıfı
Belge şablonları için temel işlevleri tanımlar Özet bir temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocTemplate::CDocTemplate](#cdoctemplate)|Oluşturan bir `CDocTemplate` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocTemplate::AddDocument](#adddocument)|Bir belge için bir şablon ekler.|  
|[CDocTemplate::CloseAllDocuments](#closealldocuments)|Bu şablonla ilişkili tüm belgeleri kapatır.|  
|[CDocTemplate::CreateNewDocument](#createnewdocument)|Yeni bir belge oluşturur.|  
|[CDocTemplate::CreateNewFrame](#createnewframe)|Bir belge ve görünüm içeren yeni bir çerçeve penceresi oluşturur.|  
|[CDocTemplate::CreateOleFrame](#createoleframe)|OLE etkin çerçeve penceresi oluşturur.|  
|[CDocTemplate::CreatePreviewFrame](#createpreviewframe)|Zengin önizlemesi için kullanılan bir alt çerçeve oluşturur.|  
|[CDocTemplate::GetDocString](#getdocstring)|Belge türü ile ilişkili bir dize alır.|  
|[CDocTemplate::GetFirstDocPosition](#getfirstdocposition)|Bu şablonla ilişkili ilk belgenin konumunu alır.|  
|[CDocTemplate::GetNextDoc](#getnextdoc)|Bir belge ve bir sonraki konumunu alır.|  
|[CDocTemplate::InitialUpdateFrame](#initialupdateframe)|Çerçeve penceresi başlatır ve isteğe bağlı olarak görünür yapar.|  
|[CDocTemplate::LoadTemplate](#loadtemplate)|Kaynaklar için yükleyen bir verilen `CDocTemplate` veya türetilmiş bir sınıf.|  
|[CDocTemplate::MatchDocType](#matchdoctype)|Bir belge türü ve bu şablonu arasında eşleşme güven düzeyini belirler.|  
|[CDocTemplate::OpenDocumentFile](#opendocumentfile)|Pathname tarafından belirtilen bir dosyayı açar.|  
|[CDocTemplate::RemoveDocument](#removedocument)|Bir belgeyi bir şablondan kaldırır.|  
|[CDocTemplate::SaveAllModified](#saveallmodified)|Hangi değiştirilmiş bu şablonla ilişkili tüm belgeleri kaydeder.|  
|[CDocTemplate::SetContainerInfo](#setcontainerinfo)|OLE kapsayıcıları için kaynakları, bir yerinde OLE öğesi düzenlerken belirler.|  
|[CDocTemplate::SetDefaultTitle](#setdefaulttitle)|Varsayılan başlığı belge penceresinin başlık çubuğunda görüntüler.|  
|[CDocTemplate::SetPreviewInfo](#setpreviewinfo)|İşlem dışı kurulumları Önizleme işleyicisi.|  
|[CDocTemplate::SetServerInfo](#setserverinfo)|Sunucu belgesinin katıştırılır veya yerinde düzenlenmiş olduğunda kaynakları ve sınıfları belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulamanızın uygulamasında genellikle bir veya daha fazla belge şablonu oluşturma `InitInstance` işlevi. Belge şablonu sınıfları üç tür arasındaki ilişkileri tanımlar:  
  
-   Öğesinden türetilen bir belge sınıfı `CDocument`.  
  
-   Yukarıda listelenen belge sınıfı verileri görüntüleyen bir görünüm sınıfı. Bu sınıftan türetilen `CView`, `CScrollView`, `CFormView`, veya `CEditView`. (Aynı zamanda `CEditView` doğrudan.)  
  
-   Görünüm içeren bir çerçeve pencere sınıfı. Tek belge arabirimi (SDI) uygulaması için bu sınıftan türeyen `CFrameWnd`. Bu sınıftan türeyen bir birden çok belge arabirimi (MDI) uygulaması için `CMDIChildWnd`. Çerçeve penceresi davranışını özelleştirmek gerekmiyorsa kullanabileceğiniz `CFrameWnd` veya `CMDIChildWnd` kendi sınıf türetme olmadan doğrudan.  
  
 Uygulamanız destekliyorsa belge her türü için bir belge şablonu yok. Örneğin, uygulamanızın elektronik tablolar ve metin belgeleri destekliyorsa, uygulamanın iki belge şablonu nesneleri sahiptir. Her belge şablonu oluşturma ve kendi türünün tüm belgeleri yönetme sorumludur.  
  
 Belge şablonu işaretçileri depolar `CRuntimeClass` nesneleri belge, Görünüm ve çerçeve penceresi sınıfları için. Bunlar `CRuntimeClass` nesneleri, bir belge şablonu oluşturma sırasında belirtilir.  
  
 Belge şablonu belge türü (örneğin, menü, simge veya Hızlandırıcı tablosu kaynakları) ile kullanılan kaynakları Kimliğini içerir. Belge şablonu Ayrıca belge türü hakkında ek bilgi içeren bir dizeler sahiptir. Bu belge türü (örneğin, "çalışma sayfası") ve dosya uzantısını (örneğin, ".xls") adını içerir. İsteğe bağlı olarak, uygulamanın kullanıcı arabirimi, Windows Dosya Yöneticisi ve nesne bağlama ve Katıştırma (OLE) desteği tarafından kullanılan diğer dizeleri içerebilir.  
  
 Uygulamanız bir OLE kapsayıcı ve/veya sunucu ise, belge şablonu de yerinde etkinleştirme sırasında kullanılan menü Kimliğini tanımlar. Uygulamanızı OLE sunucusu ise, belge şablonu araç çubuğu ve menü yerinde etkinleştirme sırasında kullanılan kimliği tanımlar. Bu ek OLE kaynakları çağırarak belirtin `SetContainerInfo` ve `SetServerInfo`.  
  
 Çünkü `CDocTemplate` bir Özet sınıf sınıfı doğrudan kullanamazsınız. Tipik bir uygulama iki birini kullanan `CDocTemplate`-türetilmiş sınıfları Microsoft Foundation Class Kitaplığı tarafından sağlanan: `CSingleDocTemplate`, SDI, uygulayan ve `CMultiDocTemplate`, MDI uygular. Belge şablonları kullanma hakkında daha fazla bilgi için bu sınıfların bakın.  
  
 Uygulamanızı SDI veya MDI temelde farklı bir kullanıcı arabirimi standardı gerektiriyorsa, kendi sınıfından türetilen `CDocTemplate`.  
  
 Daha fazla bilgi için `CDocTemplate`, bkz: [belge şablonları ve belge/görünüm oluşturma işlemi](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocTemplate`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="adddocument"></a>  CDocTemplate::AddDocument  
 Bir belge için bir şablon eklemek için bu işlevi kullanın.  
  
```  
virtual void AddDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDoc*  
 Eklenecek belge için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen sınıflar [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) ve [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) bu işlevi geçersiz. Kendi belge şablonu sınıfından türetilen varsa `CDocTemplate`, bu işlev, türetilmiş bir sınıf geçersiz kılmanız gerekir.  
  
##  <a name="cdoctemplate"></a>  CDocTemplate::CDocTemplate  
 Oluşturan bir `CDocTemplate` nesnesi.  
  
```  
CDocTemplate (
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDResource*  
 Belge türü ile kullanılan kaynakları Kimliğini belirtir. Bu menü, simge, Hızlandırıcı tablosu ve dize kaynaklarını içerebilir.  
  
 En çok yedi alt dizeler '\n' karakteriyle ayrılmış dize kaynağını oluşur (ancak, sonunda '\n' karakterler gerekli değildir; bir alt dizesi dahil edilmezse '\n' karakteri yer tutucu gerekli); Bu alt dizeler belge türü açıklanmaktadır. Alt dizeler hakkında daha fazla bilgi için bkz: [GetDocString](#getdocstring). Bu dize kaynak uygulamanın kaynak dosyası bulunamadı. Örneğin:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 Dize '\n' karakteriyle başlayan unutmayın; ilk alt dizeyi MDI uygulamaları için kullanılmaz ve bu nedenle dahil değildir çünkü budur. Dize Düzenleyicisi'ni kullanarak bu dize düzenleyebilirsiniz; tüm dizeyi tek Dize Düzenleyicisi'nde, bir giriş olarak değil yedi ayrı girişleri olarak görünür.  
  
 *pDocClass*  
 İşaret `CRuntimeClass` belge sınıfın nesnesi. Bu sınıf, bir `CDocument`-türetilmiş sınıf belgelerinizi temsil etmek için tanımlayın.  
  
 *pFrameClass*  
 İşaret `CRuntimeClass` çerçeve penceresi sınıfın nesnesi. Bu sınıf olabilir bir `CFrameWnd`-türetilmiş sınıf veya olabilir `CFrameWnd` kendisini varsayılan davranışı, ana çerçeve penceresi istiyorsanız.  
  
 *pViewClass*  
 İşaret `CRuntimeClass` görünüm sınıfın nesnesi. Bu sınıf, bir `CView`-türetilmiş sınıf belgelerinizi görüntülenecek tanımlayın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi oluşturmak için kullandığı bir `CDocTemplate` nesnesi. Dinamik olarak ayırabilir bir `CDocTemplate` nesne ve ona geçirin [CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) gelen `InitInstance` uygulama sınıfının üye işlevi.  
  
##  <a name="closealldocuments"></a>  CDocTemplate::CloseAllDocuments  
 Tüm açık belgeleri kapatmak için bu üye işlevini çağırın.  
  
```  
virtual void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>Parametreler  
 *bEndSession*  
 Kullanılmadı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi genellikle dosya çıkış komutunu bir parçası olarak kullanılır. Bu işlev varsayılan uygulamasını çağıran [CDocument::DeleteContents](../../mfc/reference/cdocument-class.md#deletecontents) belgenin veri ve ardından tüm görünümleri çerçeve pencereleri ekli belgeyi kapanır silmek için üye işlevi.  
  
 Belge kapatılmadan önce özel temizleme işleme gerçekleştirmek kullanıcının gerektiren istiyorsanız, bu işlev geçersiz kılar. Örneğin, bir veritabanındaki bir kaydı belgeyi temsil ediyorsa, veritabanını kapatmak için bu işlevi geçersiz isteyebilirsiniz.  
  
##  <a name="createnewdocument"></a>  CDocTemplate::CreateNewDocument  
 Bu belge şablonuyla ilişkili türü yeni bir belge oluşturmak için bu üye işlevini çağırın.  
  
```  
virtual CDocument* CreateNewDocument();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan belge için bir işaretçi veya **NULL** bir hata oluşursa.  
  
##  <a name="createnewframe"></a>  CDocTemplate::CreateNewFrame  
 Bir belge ve görünüm içeren yeni bir çerçeve penceresi oluşturur.  
  
```  
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,  
    CFrameWnd* pOther);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDoc*  
 Belge yeni çerçeve penceresi bakmanız gerekir. Olabilir **NULL**.  
  
 *pOther*  
 Temel olduğu yeni bir çerçeve penceresi çerçeve penceresi. Olabilir **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan çerçeve penceresi için bir işaretçi veya **NULL** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 `CreateNewFrame` kullanan `CRuntimeClass` nesneleri geçirilen bir görünüm ve ekli belgeyi ile yeni bir çerçeve penceresi oluşturma Oluşturucu. Varsa *pDoc* parametresi **NULL**, izleme iletisi framework çıkarır.  
  
 *POther* parametresi penceresi yeni komutu uygulamak için kullanılır. Yeni bir çerçeve penceresi modellemek bir çerçeve penceresinde sağlar. Yeni bir çerçeve penceresi çoğunlukla görünmeyen oluşturulur. Çerçeve pencereleri dosya yeni ve Dosya Aç standart framework uygulamasını dışında oluşturmak için bu işlevini çağırın.  
  
##  <a name="createoleframe"></a>  CDocTemplate::CreateOleFrame  
 OLE çerçeve penceresi oluşturur.  
  
```  
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc,  
    BOOL bCreateView);
```  
  
### <a name="parameters"></a>Parametreler  
 *pParentWnd*  
 Çerçeve üst penceresi için bir işaretçi.  
  
 *pDoc*  
 Yeni OLE çerçeve penceresi belge için bir işaretçi başvurmalıdır.  
  
 *bCreateView*  
 Bir görünüm çerçeve birlikte oluşturulup oluşturulmayacağını belirler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve penceresi başarılı olursa bir işaretçi; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *bCreateView* sıfırsa, boş bir çerçeve oluşturulur.  
  
##  <a name="getdocstring"></a>  CDocTemplate::GetDocString  
 Belge türü ile ilişkili bir dize alır.  
  
```  
virtual BOOL GetDocString(
    CString& rString,  
    enum DocStringIndex index) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *rString*  
 Bir başvuru bir `CString` işlevi döndüğünde dizeyi içeren nesne.  
  
 *Dizin*  
 Belge türü açıklayan dizeden alınan substring dizini. Bu parametre aşağıdaki değerlerden biri olabilir:  
  
- **CDocTemplate::windowTitle** uygulama penceresinin başlık çubuğu (örneğin, "Microsoft Excel") olarak görünen adı. SDI uygulamaları için belge şablonundaki yalnızca sunar.  
  
- **CDocTemplate::docName** kök varsayılan belge adı (örneğin, "Sayfası"). Bu kök yanı sıra, bir sayı, kullanıcı yeni bir komut dosyası menüsünden (örneğin, "Sheet1" veya "Sheet2") seçer olduğunda bu türdeki yeni bir belge için varsayılan ad kullanılır. Belirtilmezse, "Adsız" varsayılan olarak kullanılır.  
  
- **CDocTemplate::fileNewName** bu belge türü adı. Uygulama birden fazla belge türünü destekliyorsa, bu dize dosya yeni iletişim kutusunda (örneğin, "çalışma sayfası") görüntülenir. Belirtilmezse, belge türü dosya yeni komutu kullanmayı erişilemiyor.  
  
- **CDocTemplate::filterName** belge türü ve bu tür belgeleri eşleşen bir joker karakter filtresi açıklaması. Bu dize, Dosya Aç iletişim kutusu (örneğin, "çalışma sayfaları (*.xls)") dosya türü listesinde aşağı açılan listesinde görüntülenir. Belirtilmezse, belge türü Dosya Aç komutu kullanılarak erişilemez.  
  
- **CDocTemplate::filterExt** uzantısı için (örneğin, ".xls") bu tür belgeleri. Belirtilmezse, belge türü Dosya Aç komutu kullanılarak erişilemez.  
  
- **CDocTemplate::regFileTypeId** Windows tarafından tutulan kayıt veritabanına depolanacak belge türü için tanımlayıcı. Yalnızca dahili kullanım için (örneğin, "ExcelWorksheet") dizedir. Belirtilmezse, belge türü Windows Dosya Yöneticisi ile kaydedilemedi.  
  
- **CDocTemplate::regFileTypeName** kayıt veritabanında depolanacak belge türü adı. Bu dize (örneğin, "Microsoft Excel çalışma sayfası") kayıt veritabanına erişim uygulamaları iletişim kutularında görüntülenebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen alt dizeyi bulunduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Belge türü açıklayan belirli bir alt dizeyi almak için bu işlevini çağırın. Bu alt dizeler içeren dize belge şablonunda depolanır ve uygulama için kaynak dosyasında bir dize türetilir. Çerçeve, uygulamanın kullanıcı arabirimi için gereken dizeleri almak için bu işlevi çağırır. Bir dosya adı uzantısı, uygulamanızın belgeler için belirtilmişse framework bir girdi için Windows kayıt veritabanı eklerken de bu işlevi çağırır; Bu, Windows Dosya Yöneticisi'nden açılması belgeler sağlar.  
  
 Yalnızca kendi sınıfından türetilen ise bu işlev çağrısı `CDocTemplate`.  
  
##  <a name="getfirstdocposition"></a>  CDocTemplate::GetFirstDocPosition  
 Bu şablonla ilişkili ilk belgenin konumunu alır.  
  
```  
virtual POSITION GetFirstDocPosition() const = 0;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** bu belge şablonuyla; ilişkili belgelerin listesini yinelemek için kullanılabilecek değeri veya **NULL** liste boşsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablonla ilişkili belgelerin listedeki ilk belgeyi konumunu almak için bu işlevi kullanın. Kullanım **konumu** değer bağımsız değişken olarak [CDocTemplate::GetNextDoc](#getnextdoc) şablonuyla ilişkili belgelerin listesini yinelemek için.  
  
 [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) ve [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) hem de bu saf sanal işlevi geçersiz. Öğesinden türetilen herhangi bir sınıf `CDocTemplate` Ayrıca bu işlev geçersiz kılmanız gerekir.  
  
##  <a name="getnextdoc"></a>  CDocTemplate::GetNextDoc  
 Tarafından tanımlanan liste öğesi alır *RPO'lar*, ardından ayarlar *RPO'lar* için **konumu** listesinde sonraki girdisinin değeri.  
  
```  
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu şablonla ilişkili belgeleri listesinde sonraki belge için bir işaretçi.  
  
### <a name="parameters"></a>Parametreler  
 *RPO'lar*  
 Bir başvuru bir **konumu** önceki bir çağrı tarafından döndürülen değer [GetFirstDocPosition](#getfirstdocposition) veya `GetNextDoc`.  
  
### <a name="remarks"></a>Açıklamalar  
 Alınan öğe listesinde, son sonra yeni değeri ise *RPO'lar* ayarlanır **NULL**.  
  
 Kullanabileceğiniz `GetNextDoc` çağrısıyla ilk konum kurarsanız ileriye doğru yineleme döngü [GetFirstDocPosition](#getfirstdocposition).  
  
 Emin olmanız gerekir, **konumu** değer listesinde geçerli bir konumu temsil eder. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
##  <a name="initialupdateframe"></a>  CDocTemplate::InitialUpdateFrame  
 Çerçeve penceresi başlatır ve isteğe bağlı olarak görünür yapar.  
  
```  
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,  
    CDocument* pDoc,  
    BOOL bMakeVisible = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *pFrame*  
 İlk Güncelleştirme Onayı gereken çerçeve penceresi.  
  
 *pDoc*  
 Çerçeve ilişkilendirilen belge. Olabilir **NULL**.  
  
 *bMakeVisible*  
 Çerçeve görünür ve etkin olup olmayacağını gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı **IntitialUpdateFrame** ile yeni bir çerçeve oluşturduktan sonra `CreateNewFrame`. Bu işlev çağırma neden olan görünümleri almak için bu çerçeve penceresinde kendi `OnInitialUpdate` çağrıları. Ayrıca, yoksa daha önce etkin bir görünüm, çerçeve penceresi birincil görünümünü etkinleştirilir; birincil görünüm alt kimliğine sahip bir görünümdür **AFX_IDW_PANE_FIRST**. Son olarak, çerçeve penceresi görünür hale gelir, `bMakeVisible` sıfır değil. Varsa *bMakeVisible* sıfır, geçerli odağa ve çerçeve penceresi görünür durumunu değişmeden kalır.  
  
 Framework'ün uygulama ve dosya yeni dosya Aç kullanırken bu işlevi çağırmak gerekli değildir.  
  
##  <a name="loadtemplate"></a>  CDocTemplate::LoadTemplate  
 Kaynaklar için yükleyen bir verilen `CDocTemplate` veya türetilmiş bir sınıf.  
  
```  
virtual void LoadTemplate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi için kaynakları yüklemek için framework tarafından çağrılan bir verilen `CDocTemplate` veya türetilmiş bir sınıf. Şablon genel oluşturulmuyor normalde, oluşturma sırasında dışında denir. Bu durumda, çağrısı `LoadTemplate` kadar Gecikmeli [CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) olarak adlandırılır.  
  
##  <a name="matchdoctype"></a>  CDocTemplate::MatchDocType  
 Bir belge türü ve bu şablonu arasında eşleşme güven düzeyini belirler.  
  
```  
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,  
    CDocument*& rpDocMatch);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszPathName*  
 Belirlenecek türü olan dosyasının yol adı.  
  
 *rpDocMatch*  
 İşaretçi dosyası tarafından belirttiyseniz, eşleşen belge atanmış bir belgeyi *lpszPathName* zaten açıktır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arasında bir değer **güvenirlik** gibi tanımlanan numaralandırma:  
  
```  
enum Confidence  
    {  
    noAttempt,
    maybeAttemptForeign,
    maybeAttemptNative,
    yesAttemptForeign,
    yesAttemptNative,
    yesAlreadyOpen
    };  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dosyanın açılması için kullanmak üzere belge şablonu türünü belirlemek için bu işlevi kullanın. Örneğin, uygulamanız birden çok dosya türünü destekliyorsa, hangi kullanılabilir şablonların çağırarak belirli bir dosya için uygun olduğunu belirlemek için bu işlevi kullanabilirsiniz `MatchDocType` her şablon Aç ve göre bir şablon seçmek için GÜVENİRLİK değer döndürdü.  
  
 Dosyanın belirtilen *lpszPathName* bu işlevi döndürür, açıksa **CDocTemplate::yesAlreadyOpen** ve dosyanın kopyalar **CDocument** içine nesnesi konumunda nesnesini *rpDocMatch*.  
  
 Dosya uzantısı'nda ancak açık değilse *lpszPathName* tarafından belirtilen uzantısı ile eşleşen **CDocTemplate::filterExt**, bu işlevi döndürür **CDocTemplate::yesAttemptNative** ve ayarlar *rpDocMatch* için **NULL**. Daha fazla bilgi için **CDocTemplate::filterExt**, bkz: [CDocTemplate::GetDocString](#getdocstring).  
  
 Her iki durumda true ise işlevi döndürür **CDocTemplate::yesAttemptForeign**.  
  
 Varsayılan uygulama döndürmez **CDocTemplate::maybeAttemptForeign** veya **CDocTemplate::maybeAttemptNative**. Türüyle eşleşen belki de bu iki değerleri kullanarak uygulamanıza uygun mantığını uygulamak için bu işlevi geçersiz **güvenirlik** numaralandırması.  
  
##  <a name="opendocumentfile"></a>  CDocTemplate::OpenDocumentFile  
 Bir yol tarafından belirtilen bir dosyayı açar.  
  
```  
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;  
 
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU) = 0;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszPathName*  
 İşaretçi açılması belgeye içeren dosyanın yolu.  
  
 [in] *bAddToMRU*  
 `TRUE` Belgenin en son dosyalardan biri olduğunu gösterir; `FALSE` belgenin en son dosyalardan biri olmadığını gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi olarak adlandırılan, dosya belge *lpszPathName*; `NULL` başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizinin yolu tarafından belirtilen dosya açılır *lpszPathName*. Varsa *lpszPathName* olan `NULL`, bir belge türü bu şablonla ilişkili içeren yeni bir dosya oluşturulur.  
  
##  <a name="removedocument"></a>  CDocTemplate::RemoveDocument  
 Gösterdiği belgeyi kaldırır *pDoc* bu şablonla ilişkili belgeleri listesinden.  
  
```  
virtual void RemoveDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDoc*  
 İşaretçi belgenin kaldırılacak.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen sınıflar `CMultiDocTemplate` ve `CSingleDocTemplate` bu işlevi geçersiz. Kendi belge şablonu sınıfından türetilen varsa `CDocTemplate`, bu işlev, türetilmiş bir sınıf geçersiz kılmanız gerekir.  
  
##  <a name="saveallmodified"></a>  CDocTemplate::SaveAllModified  
 Değiştirilmiş tüm belgeleri kaydeder.  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır dışı başarılıysa; Aksi takdirde 0.  
  
##  <a name="setcontainerinfo"></a>  CDocTemplate::SetContainerInfo  
 OLE kapsayıcıları için kaynakları, bir yerinde OLE öğesi düzenlerken belirler.  
  
```  
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDOleInPlaceContainer*  
 Katıştırılmış nesne etkinleştirildiğinde kullanılan kaynakları kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 OLE nesnesi yerinde etkin olduğunda kullanılacak kaynakları ayarlamak için bu işlevini çağırın. Bu kaynaklar, menüleri ve Hızlandırıcı tabloları içerebilir. Bu işlev genellikle adı verilir [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) uygulamanızın işlevi.  
  
 İle ilişkili menü *nIDOleInPlaceContainer* birleştirmek için etkinleştirilmiş yerinde öğesi menü kapsayıcı uygulama menüsüyle izin ayırıcılar içerir. Sunucu ve kapsayıcı menülerini birleştirme hakkında daha fazla bilgi için bkz: [menüleri ve kaynakları (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="setdefaulttitle"></a>  CDocTemplate::SetDefaultTitle  
 Belgenin varsayılan başlık yüklemek ve belgenin başlık çubuğunda görüntülemek için bu işlevini çağırın.  
  
```  
virtual void SetDefaultTitle(CDocument* pDocument) = 0;  
```  
  
### <a name="parameters"></a>Parametreler  
 *pDocument*  
 Ayarlanacak, başlık olan belge işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan başlığı hakkında daha fazla bilgi için açıklamasına bakın **CDocTemplate::docName** içinde [CDocTemplate::GetDocString](#getdocstring).  
  
##  <a name="setserverinfo"></a>  CDocTemplate::SetServerInfo  
 Sunucu belgesinin katıştırılır veya yerinde düzenlenmiş olduğunda kaynakları ve sınıfları belirler.  
  
```  
void SetServerInfo(
    UINT nIDOleEmbedding,  
    UINT nIDOleInPlaceServer = 0,  
    CRuntimeClass* pOleFrameClass = NULL,  
    CRuntimeClass* pOleViewClass = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDOleEmbedding*  
 Katıştırılmış nesne ayrı bir pencerede açıldığında kullanılan kaynakları kimliği.  
  
 *nIDOleInPlaceServer*  
 Katıştırılmış nesne olduğunda kullanılan kaynakları Kimliğini yerinde etkinleştirildi.  
  
 *pOleFrameClass*  
 İşaretçi bir [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yerinde etkinleştirme oluştuğunda oluşturulan çerçeve pencere nesnesi için sınıf bilgileri içeren yapısı.  
  
 *pOleViewClass*  
 İşaretçi bir `CRuntimeClass` yerinde etkinleştirme oluştuğunda oluşturulan Görünüm nesnesi için sınıf bilgileri içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı etkinleştirme katıştırılmış nesne istediğinde sunucu uygulaması tarafından kullanılan kaynakları tanımlamak için bu üye işlevini çağırın. Bu kaynaklar, menüleri ve Hızlandırıcı tabloları oluşur. Bu işlev genellikle adı verilir `InitInstance` uygulamanızın.  
  
 İle ilişkili menü *nIDOleInPlaceServer* birleştirmek sunucu menüsü kapsayıcısının menüsüyle izin ayırıcılar içerir. Sunucu ve kapsayıcı menülerini birleştirme hakkında daha fazla bilgi için bkz: [menüleri ve kaynakları (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="createpreviewframe"></a>  CDocTemplate::CreatePreviewFrame  
 Zengin önizlemesi için kullanılan bir alt çerçeve oluşturur.  
  
```  
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc);
```  
  
### <a name="parameters"></a>Parametreler  
 *pParentWnd*  
 (Genellikle Kabuk tarafından sağlanan) bir üst penceresi için bir işaretçi.  
  
 *pDoc*  
 İçerikleri önizlemesi bir belge nesnesi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi bir `CFrameWnd` nesnesi veya `NULL` oluşturma başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpreviewinfo"></a>  CDocTemplate::SetPreviewInfo  
 İşlem Önizleme işleyicisi dışı ayarlar.  
  
```  
void SetPreviewInfo(
    UINT nIDPreviewFrame,  
    CRuntimeClass* pPreviewFrameClass = NULL,  
    CRuntimeClass* pPreviewViewClass = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDPreviewFrame*  
 Önizleme çerçeve kaynak Kimliğini belirtir.  
  
 *pPreviewFrameClass*  
 Önizleme çerçevesi çalışma zamanı sınıf bilgileri yapısını gösteren bir işaretçi belirtir.  
  
 *pPreviewViewClass*  
 Bir çalışma zamanı sınıf bilgileri yapısı Önizleme görünümü için bir işaretçi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CSingleDocTemplate sınıfı](../../mfc/reference/csingledoctemplate-class.md)   
 [CMultiDocTemplate sınıfı](../../mfc/reference/cmultidoctemplate-class.md)   
 [CDocument sınıfı](../../mfc/reference/cdocument-class.md)   
 [CView sınıfı](../../mfc/reference/cview-class.md)   
 [CScrollView sınıfı](../../mfc/reference/cscrollview-class.md)   
 [CEditView sınıfı](../../mfc/reference/ceditview-class.md)   
 [Cformview'yu sınıfı](../../mfc/reference/cformview-class.md)   
 [CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWnd Sınıfı](../../mfc/reference/cmdichildwnd-class.md)
