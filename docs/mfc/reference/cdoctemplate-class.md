---
title: CDocTemplate sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 3b2d84af9be8e5c606cde8794b51e12207dcdec9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62163993"
---
# <a name="cdoctemplate-class"></a>CDocTemplate sınıfı

Belge şablonları için temel işlevselliği tanımlayan soyut bir temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CDocTemplate : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDocTemplate::CDocTemplate](#cdoctemplate)|Oluşturur bir `CDocTemplate` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDocTemplate::AddDocument](#adddocument)|Bir belge için bir şablon ekler.|
|[CDocTemplate::CloseAllDocuments](#closealldocuments)|Bu şablonla ilişkili tüm belgeleri kapatır.|
|[CDocTemplate::CreateNewDocument](#createnewdocument)|Yeni bir belge oluşturulur.|
|[CDocTemplate::CreateNewFrame](#createnewframe)|Bir belge ve görünüm içeren yeni bir çerçeve penceresi oluşturur.|
|[CDocTemplate::CreateOleFrame](#createoleframe)|Bir OLE etkin çerçeve penceresi oluşturur.|
|[CDocTemplate::CreatePreviewFrame](#createpreviewframe)|Zengin Önizleme için kullanılan bir alt pencere oluşturur.|
|[CDocTemplate::GetDocString](#getdocstring)|Belge türü ile ilişkili bir dize alır.|
|[CDocTemplate::GetFirstDocPosition](#getfirstdocposition)|Bu şablonla ilişkili ilk belgenin konumunu alır.|
|[CDocTemplate::GetNextDoc](#getnextdoc)|Bir belge ve bir sonraki konumunu alır.|
|[CDocTemplate::InitialUpdateFrame](#initialupdateframe)|Çerçeve penceresi başlatır ve isteğe bağlı olarak görünür yapar.|
|[CDocTemplate::LoadTemplate](#loadtemplate)|Kaynaklar için yükleyen bir verilen `CDocTemplate` veya türetilmiş sınıf.|
|[CDocTemplate::MatchDocType](#matchdoctype)|Eşleşme bir belge türü ve bu şablonu arasındaki güven düzeyini belirler.|
|[CDocTemplate::OpenDocumentFile](#opendocumentfile)|Bir yol tarafından belirtilen bir dosya açar.|
|[CDocTemplate::RemoveDocument](#removedocument)|Bir şablondan bir belge kaldırır.|
|[CDocTemplate::SaveAllModified](#saveallmodified)|Değiştirilmiş bu şablonla ilişkili tüm belgeleri kaydeder.|
|[CDocTemplate::SetContainerInfo](#setcontainerinfo)|OLE kapsayıcıları için kaynakları yerinde OLE öğesini düzenlerken belirler.|
|[CDocTemplate::SetDefaultTitle](#setdefaulttitle)|Varsayılan başlık, belge pencerenin başlık çubuğunda görüntülenir.|
|[CDocTemplate::SetPreviewInfo](#setpreviewinfo)|İşlem dışı kurulumları Önizleme işleyicisi.|
|[CDocTemplate::SetServerInfo](#setserverinfo)|Sunucu belgesinin katıştırılmış ya da yerinde düzenlenirken, kaynak ve sınıflarını belirler.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızın uygulamada genellikle bir veya daha fazla belge şablonu oluşturma `InitInstance` işlevi. Üç tür sınıflar arasındaki ilişkileri bir belge şablonu tanımlar:

- Öğesinden türetilen bir belge sınıfı `CDocument`.

- Yukarıda listelenen belge sınıfı verileri görüntüleyen bir görünüm sınıfı. Bu sınıftan türetilip `CView`, `CScrollView`, `CFormView`, veya `CEditView`. (Ayrıca `CEditView` doğrudan.)

- Görünüm içeren bir çerçeve penceresi sınıfı. Tek Belgeli Arabirim (SDI) uygulaması için bu sınıftan türetilen `CFrameWnd`. Bu sınıftan türetilen bir birden çok belge arabirimi (MDI) uygulaması için `CMDIChildWnd`. Çerçeve penceresi davranışını özelleştirmek gerekmiyorsa, kullanabileceğiniz `CFrameWnd` veya `CMDIChildWnd` kendi sınıf türetme olmadan doğrudan.

Uygulamanızın desteklediği belge her tür için bir belge şablonu vardır. Örneğin, elektronik tablolar hem metin belgeleri uygulamanız destekliyorsa, uygulama iki belge şablonu nesnesi vardır. Her bir belge şablonu oluşturma ve kendi türünün tüm belgeleri yönetme sorumludur.

Belge şablonu işaretçileri depolar `CRuntimeClass` belge, Görünüm ve çerçeve penceresi sınıfları için nesneleri. Bunlar `CRuntimeClass` nesneleri, bir belge şablonu oluşturma sırasında belirtilir.

Belge şablonu belge türlerinin (örneğin, menü, simge veya Hızlandırıcı tablo kaynaklarını) ile birlikte kullanılan kaynak Kimliğini içerir. Belge şablonu dizeleri kendi belge türü hakkında ek bilgi içeren de vardır. Bunlar belge türü (örneğin, "Çalışma") ve dosya uzantısını (örneğin, ".xls") adını içerir. İsteğe bağlı olarak, uygulamanın kullanıcı arabirimini, Windows Dosya Yöneticisi ve nesne bağlama ve Katıştırma (OLE) desteği tarafından kullanılan diğer dizeleri içerebilir.

Uygulamanız bir OLE kapsayıcısı ve/veya sunucu ise, belge şablonunu da yerinde etkinleştirme sırasında kullanılan menü kimliği tanımlar. Uygulamanız OLE sunucusu ise, araç çubuğu ve menü yerinde etkinleştirme sırasında kullanılan kimliği belge şablonu tanımlar. Çağırarak bu ek OLE kaynakları belirtmek `SetContainerInfo` ve `SetServerInfo`.

Çünkü `CDocTemplate` soyut bir sınıf olan sınıf doğrudan kullanamazsınız. Tipik bir uygulaması iki birini kullanan `CDocTemplate`-türetilmiş sınıflar Microsoft Foundation Class Kitaplığı tarafından sağlanan: `CSingleDocTemplate`, SDI, uygular ve `CMultiDocTemplate`, MDI uygular. Belge şablonlarını kullanma hakkında daha fazla bilgi için bu sınıflar bakın.

Uygulamanız SDI veya MDI tamamen farklı bir kullanıcı arabirimi paradigma gerektiriyorsa, kendi sınıfınızı türetebilirsiniz `CDocTemplate`.

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

*pDoc*<br/>
Eklenecek belgeye bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Türetilen sınıfların [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) ve [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) bu işlevi geçersiz. Kendi belge şablonu sınıfından türetilen `CDocTemplate`, bu işlev, türetilmiş sınıf geçersiz kılmanız gerekir.

##  <a name="cdoctemplate"></a>  CDocTemplate::CDocTemplate

Oluşturur bir `CDocTemplate` nesne.

```
CDocTemplate (
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Parametreler

*nIDResource*<br/>
Belge türü ile kullanılan kaynakları Kimliğini belirtir. Bu menü, simge, Hızlandırıcı tablosu ve dize kaynakları içerebilir.

'\N' karakteriyle ayrılmış en fazla yedi alt dizeler dize kaynağını oluşur ('\n' karakteri bir alt dizesi değilse, bir yer tutucu gereklidir; ancak, sonunda '\n' karakterler gerekli değildir) Bu alt dizeleri belge türü açıklar. Alt dizeler hakkında daha fazla bilgi için bkz: [GetDocString](#getdocstring). Bu dize kaynağı uygulama kaynak dosyası bulunamadı. Örneğin:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

Unutmayın; dize '\n' karakteri ile başlar. ilk alt dizeyi MDI uygulamaları için kullanılmaz ve bu nedenle dahil olmadığından budur. Dize Düzenleyicisi'ni kullanarak bu dizeni düzenleyebilirsiniz; Tüm dize tek bir giriş dizesini Düzenleyicisi'nde, olarak değil yedi ayrı girişleri olarak görünür.

*pDocClass*<br/>
İşaret `CRuntimeClass` belge sınıfının nesne. Bu sınıf, bir `CDocument`-türetilmiş tanımladığınız belgelerinizi temsil eden sınıf.

*pFrameClass*<br/>
İşaret `CRuntimeClass` çerçeve penceresi sınıfın nesnesi. Bu sınıf olabilir bir `CFrameWnd`-derived class veya olabilir `CFrameWnd` kendisi için ana çerçeve penceresinin varsayılan davranışı istiyorsanız.

*pViewClass*<br/>
İşaret `CRuntimeClass` nesne görünüm sınıfı. Bu sınıf, bir `CView`-türetilmiş sınıf belgelerinizi görüntülenecek tanımlayın.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi oluşturmak için kullanmak bir `CDocTemplate` nesne. Dinamik olarak ayırabilir bir `CDocTemplate` nesne ve geçirin [CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) gelen `InitInstance` uygulama sınıfının üye işlevi.

##  <a name="closealldocuments"></a>  CDocTemplate::CloseAllDocuments

Tüm açık belgeleri kapatmak için bu üye işlevini çağırın.

```
virtual void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>Parametreler

*bEndSession*<br/>
Kullanılmadı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, genellikle dosya Çıkış komutunun bir parçası kullanılır. Bu işlev varsayılan uygulamasını çağırır [CDocument::DeleteContents](../../mfc/reference/cdocument-class.md#deletecontents) belgenin verilerini ve ardından tüm görünümleri için çerçeve pencereleri ekli belgeyi kapatır, üye işlevi.

Belge kapatılmadan önce özel bir temizleme işlemi işlem gerçekleştirmesine izin istemek bu işlevi geçersiz. Örneğin, bir veritabanındaki bir kaydı belgeyi temsil ediyorsa, veritabanı kapatmak için bu işlevi geçersiz kılmak isteyebilirsiniz.

##  <a name="createnewdocument"></a>  CDocTemplate::CreateNewDocument

Bu belge şablonuyla ilişkili türün yeni bir belge oluşturmak için bu üye işlevini çağırın.

```
virtual CDocument* CreateNewDocument();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan belgeyi veya bir hata oluşursa NULL bir işaretçi.

##  <a name="createnewframe"></a>  CDocTemplate::CreateNewFrame

Bir belge ve görünüm içeren yeni bir çerçeve penceresi oluşturur.

```
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,
    CFrameWnd* pOther);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Belgeyi yeni bir çerçeve penceresi başvurmanız gerekir. NULL olabilir.

*pOther*<br/>
Çerçeve penceresi temel olan yeni bir çerçeve penceresi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan çerçeve penceresi ya da bir hata oluşursa NULL bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CreateNewFrame` kullanan `CRuntimeClass` nesneleri geçirilen bir görünümü ve ekli belge ile yeni bir çerçeve penceresi oluşturmak için oluşturucu. Varsa *pDoc* parametre NULL ise, framework izleme iletisi üreten.

*POther* parametresi, komut penceresinde yeni uygulamak için kullanılır. Bu, bir çerçeve penceresinde, yeni bir çerçeve penceresi modeli sağlar. Yeni bir çerçeve penceresi genellikle görünmez oluşturulur. Çerçeve pencereleri dışında dosya yeni ve dosya açık standart framework uygulamasını oluşturmak için bu işlevi çağırın.

##  <a name="createoleframe"></a>  CDocTemplate::CreateOleFrame

Bir OLE çerçeve penceresi oluşturur.

```
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,
    CDocument* pDoc,
    BOOL bCreateView);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Çerçevenin üst penceresine bir işaretçi.

*pDoc*<br/>
Bir işaretçi belgeye yeni bir OLE çerçeve penceresi başvurmanız gerekir.

*bCreateView*<br/>
Bir görünüm birlikte çerçeve oluşturulup oluşturulmayacağını belirler.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bir çerçeve penceresi için bir işaretçi; bulunmazsa null değerini DÖNDÜRÜR.

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

*rString*<br/>
Bir başvuru bir `CString` işlevi döndüğünde dizeyi içeren nesne.

*Dizin*<br/>
Belge türü tanımlayan dizeden alınan alt dizini. Bu parametre aşağıdaki değerlerden biri olabilir:

- `CDocTemplate::windowTitle` Uygulama pencerenin başlık çubuğunu (örneğin, "Microsoft Excel") görünen adı. SDI uygulamaları için belge şablonunda yalnızca sunar.

- `CDocTemplate::docName` Varsayılan belge adı (örneğin, "Sayfası") için kök. Bu kök yanı sıra, birkaç kullanıcı (örneğin, "Sayfa1" veya "Sheet2") ve Dosya menüsünden Yeni bir komut seçtiği zaman bu türdeki yeni bir belge için varsayılan ad kullanılır. Belirtilmezse, "Adsız" varsayılan olarak kullanılır.

- `CDocTemplate::fileNewName` Bu belge türü adı. Uygulama birden fazla belge türünü destekliyorsa, bu dize (örneğin, "Çalışma") yeni dosya iletişim kutusunda görüntülenir. Belirtilmezse, belge türü kullanarak dosya yeni komutunun erişilemiyor.

- `CDocTemplate::filterName` Belge türü ve bu tür belgeleri eşleşen bir joker karakter filtresi açıklaması. Bu dize, Dosya Aç iletişim kutusunda (örneğin, "çalışma (*.xls)") listelenecek dosya türü açılan listesinde görüntülenir. Belirtilmezse, belge türü Dosya Aç komutunu kullanarak erişilemiyor.

- `CDocTemplate::filterExt` Bu tür (örneğin, ".xls") belgeleri için uzantısı. Belirtilmezse, belge türü Dosya Aç komutunu kullanarak erişilemiyor.

- `CDocTemplate::regFileTypeId` Windows tarafından tutulan kayıt defteri veritabanında depolanacak belge türü için tanımlayıcı. Yalnızca iç kullanım için (örneğin, "ExcelWorksheet") dizedir. Belirtilmezse, belge türü Windows Dosya Yöneticisi ile kaydedilemez.

- `CDocTemplate::regFileTypeName` Kayıt defteri veritabanındaki depolanacak belge türü adı. Bu dize (örneğin, "Microsoft Excel çalışma sayfası") kayıt defteri veritabanında erişen uygulamalar iletişim kutularında görüntülenebilir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alt dizeyle bulundu olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Belge türü açıklayan belirli bir alt dizeyi almak için bu işlevi çağırın. Bu alt dizeleri içeren dize, belge şablonunda depolanır ve uygulama için kaynak dosyasındaki dizesinden türetilir. Framework, uygulamanın kullanıcı arabirimini için ihtiyaç duyduğu dizelerini almak için bu işlevi çağırır. Uygulamanızın belgeleri için bir dosya adı uzantısı belirtilmişse framework bir giriş için Windows kayıt defteri veritabanında eklerken de bu işlevi çağırır; Bu, Windows Dosya Yöneticisi'nden açılması belgeler sağlar.

Yalnızca kendi sınıftan türetme, bu işlevi çağırın `CDocTemplate`.

##  <a name="getfirstdocposition"></a>  CDocTemplate::GetFirstDocPosition

Bu şablonla ilişkili ilk belgenin konumunu alır.

```
virtual POSITION GetFirstDocPosition() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu belge şablonuyla ilişkili belgelerin listesini yinelemek için kullanılabilecek bir konum değeri; veya liste boşsa, NULL.

### <a name="remarks"></a>Açıklamalar

Bu şablonla ilişkili belgeler listesinde ilk belgenin konumunu almak için bu işlevi kullanın. Bağımsız değişken olarak konum değerini kullanmak [CDocTemplate::GetNextDoc](#getnextdoc) şablonuyla ilişkili belgelerin listesini yinelemek için.

[CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) ve [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) hem de bu saf sanal işlevi geçersiz. Herhangi bir sınıf, türetilen `CDocTemplate` bu işlev geçersiz kılmanız gerekir.

##  <a name="getnextdoc"></a>  CDocTemplate::GetNextDoc

Tarafından tanımlanan liste öğesi alır *RPO'lar*, ardından ayarlar *RPO'lar* konumu değerine listedeki sonraki giriş.

```
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu şablonla ilişkili belgelerin listesini sonraki belgeye yönelik işaretçi.

### <a name="parameters"></a>Parametreler

*RPO*<br/>
Önceki bir çağrı tarafından döndürülen bir konum değeri başvurusu [GetFirstDocPosition](#getfirstdocposition) veya `GetNextDoc`.

### <a name="remarks"></a>Açıklamalar

Alınan öğe listesinde, son öğesinin yeni değeri ise *RPO'lar* NULL olarak ayarlandı.

Kullanabileceğiniz `GetNextDoc` çağrısıyla ilk konumunu kurarsanız ileriye doğru yineleme döngüsünde [GetFirstDocPosition](#getfirstdocposition).

KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.

##  <a name="initialupdateframe"></a>  CDocTemplate::InitialUpdateFrame

Çerçeve penceresi başlatır ve isteğe bağlı olarak görünür yapar.

```
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,
    CDocument* pDoc,
    BOOL bMakeVisible = TRUE);
```

### <a name="parameters"></a>Parametreler

*pFrame*<br/>
İlk Güncelleştirme Onayı gereken çerçeve penceresi.

*pDoc*<br/>
Belge çerçeve ilişkilidir. NULL olabilir.

*bMakeVisible*<br/>
Çerçeve görünür ve etkin olup olmayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Çağrı `IntitialUpdateFrame` ile yeni bir çerçeve oluşturduktan sonra `CreateNewFrame`. Bu işlevi çağırmak, görünümleri almak için bu çerçeve penceresinde neden kendi `OnInitialUpdate` çağırır. Ayrıca, yoksa daha önce etkin bir görünüm, çerçeve penceresinin birincil görünüm etkinleştirilir; birincil görünüm Kimliği'nın AFX_IDW_PANE_FIRST alt ile bir görünümüdür. Son olarak, çerçeve penceresi görünür hale gelir, *bMakeVisible* sıfır değil. Varsa *bMakeVisible* sıfırsa, geçerli odak ve çerçeve penceresi görünür durumunu değişmeden kalır.

Framework'ün uygulaması dosya yeni ve Dosya Aç kullanırken bu işlevi çağırmak gerekli değildir.

##  <a name="loadtemplate"></a>  CDocTemplate::LoadTemplate

Kaynaklar için yükleyen bir verilen `CDocTemplate` veya türetilmiş sınıf.

```
virtual void LoadTemplate();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, kaynaklar için yüklemek için framework tarafından çağrılan bir verilen `CDocTemplate` veya türetilmiş sınıf. Şablon genel yapılandırılmakta olan normal olarak, oluşturma sırasında dışında çağrılır. Bu durumda, çağrı `LoadTemplate` kadar Gecikmeli [CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) çağrılır.

##  <a name="matchdoctype"></a>  CDocTemplate::MatchDocType

Eşleşme bir belge türü ve bu şablonu arasındaki güven düzeyini belirler.

```
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,
    CDocument*& rpDocMatch);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Belirlenecek türü olan dosyasının yol adı.

*rpDocMatch*<br/>
Belirtilen dosya, eşleşen belgenin atandığı bir belge işaretçisi *lpszPathName* zaten açıktır.

### <a name="return-value"></a>Dönüş Değeri

Bir değer **güvenle** sabit listesi aşağıdaki gibi tanımlanır:

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

Bir dosyanın açılması için kullanılacak belge şablonunu türünü belirlemek için bu işlevi kullanın. Örneğin, uygulamanızın birden çok dosya türünü destekliyorsa, kullanılabilir şablonların çağırarak belirli bir dosya için uygun olduğunu belirlemek için bu işlevi kullanabilirsiniz `MatchDocType` her şablonunun etkinleştirin ve bir şablonu konusuna göre seçme döndürülen olasılık değeri.

Dosya belirtilen *lpszPathName* bu işlevi döndürür, açıksa `CDocTemplate::yesAlreadyOpen` ve dosya kopyalar `CDocument` nesne nesnesine *rpDocMatch*.

Dosya uzantısı'nda ancak açık değilse *lpszPathName* tarafından belirtilen uzantı eşleşen `CDocTemplate::filterExt`, bu işlevi döndürür `CDocTemplate::yesAttemptNative` ve ayarlar *rpDocMatch* null. Daha fazla bilgi için `CDocTemplate::filterExt`, bkz: [CDocTemplate::GetDocString](#getdocstring).

Hiçbir durum true ise işlev döndürür `CDocTemplate::yesAttemptForeign`.

Varsayılan uygulama döndürmez `CDocTemplate::maybeAttemptForeign` veya `CDocTemplate::maybeAttemptNative`. Belki de iki bu değerleri kullanarak uygulamanıza uygun türü eşleştirme mantığını uygulamak için bu işlevi geçersiz kılma **güvenle** sabit listesi.

##  <a name="opendocumentfile"></a>  CDocTemplate::OpenDocumentFile

Bir yolu tarafından belirtilen bir dosya açar.

```
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;

virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU) = 0;
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
[in] İşaretçi açılacak belgeyi içeren dosyanın yolu.

*bAddToMRU*<br/>
[in] Belgenin en son dosyaları biri TRUE gösterir; FALSE, belge en son dosyalardan biri değil gösterir.

### <a name="return-value"></a>Dönüş Değeri

Olarak adlandırılan, dosya belge işaretçisi *lpszPathName*; İşlem başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Yolu tarafından belirtilen dosyayı açar *lpszPathName*. Varsa *lpszPathName* NULL ise bir belge türü bu şablonla ilişkili içeren yeni bir dosya oluşturulur.

##  <a name="removedocument"></a>  CDocTemplate::RemoveDocument

İşaret ettiği belge kaldırır *pDoc* listesinden bu şablonla ilişkili belgeler.

```
virtual void RemoveDocument(CDocument* pDoc);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Kaldırılacak belgeye yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Türetilen sınıfların `CMultiDocTemplate` ve `CSingleDocTemplate` bu işlevi geçersiz. Kendi belge şablonu sınıfından türetilen `CDocTemplate`, bu işlev, türetilmiş sınıf geçersiz kılmanız gerekir.

##  <a name="saveallmodified"></a>  CDocTemplate::SaveAllModified

Değiştirilmiş tüm belgeleri kaydeder.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan başarılıysa; Aksi durumda 0.

##  <a name="setcontainerinfo"></a>  CDocTemplate::SetContainerInfo

OLE kapsayıcıları için kaynakları yerinde OLE öğesini düzenlerken belirler.

```
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```

### <a name="parameters"></a>Parametreler

*nIDOleInPlaceContainer*<br/>
Katıştırılmış nesne etkinleştirildiğinde kullanılan kaynakları kimliği.

### <a name="remarks"></a>Açıklamalar

Bir OLE nesne yerinde etkin olduğunda kullanılacak kaynakları ayarlamak için bu işlevi çağırın. Bu kaynaklar, menüler ve Hızlandırıcı tablolarını içerebilir. Bu işlevin genellikle çağrılma yeri [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) uygulamanızın işlevi.

İle ilişkili menü *nIDOleInPlaceContainer* kapsayıcı uygulamasını menüsünü birleştirmek için etkinleştirilmiş yerinde öğesi menüsü ver ayırıcılar içerir. Sunucu ve kapsayıcının menülerini birleştirme hakkında daha fazla bilgi için bkz [menüler ve kaynaklar (OLE)](../../mfc/menus-and-resources-ole.md).

##  <a name="setdefaulttitle"></a>  CDocTemplate::SetDefaultTitle

Belgenin varsayılan başlık yüklemek ve belgenin başlık çubuğunda görüntülemek için bu işlevi çağırın.

```
virtual void SetDefaultTitle(CDocument* pDocument) = 0;
```

### <a name="parameters"></a>Parametreler

*pDocument*<br/>
Ayarlanacak ayarlanmış başlık olan belge işaretçisi.

### <a name="remarks"></a>Açıklamalar

Varsayılan başlığı hakkında daha fazla bilgi için açıklamasına bakın `CDocTemplate::docName` içinde [CDocTemplate::GetDocString](#getdocstring).

##  <a name="setserverinfo"></a>  CDocTemplate::SetServerInfo

Sunucu belgesinin katıştırılmış ya da yerinde düzenlenirken, kaynak ve sınıflarını belirler.

```
void SetServerInfo(
    UINT nIDOleEmbedding,
    UINT nIDOleInPlaceServer = 0,
    CRuntimeClass* pOleFrameClass = NULL,
    CRuntimeClass* pOleViewClass = NULL);
```

### <a name="parameters"></a>Parametreler

*nIDOleEmbedding*<br/>
Katıştırılmış nesne ayrı bir pencerede açıldığında kullanılan kaynakları kimliği.

*nIDOleInPlaceServer*<br/>
Katıştırılmış nesne olduğunda kullanılan kaynakları kimliği yerinde etkinleştirilmiş.

*pOleFrameClass*<br/>
İşaretçi bir [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yerinde etkinleştirme oluştuğunda oluşturulan çerçeve pencere nesnesi için sınıf bilgileri içeren yapısı.

*pOleViewClass*<br/>
İşaretçi bir `CRuntimeClass` yerinde etkinleştirme oluştuğunda oluşturulan Görünüm nesnesi için sınıf bilgileri içeren yapısı.

### <a name="remarks"></a>Açıklamalar

Kullanıcı etkinleştirme gömülü bir nesnenin istediğinde, sunucu uygulaması tarafından kullanılan kaynakları belirlemek üzere bu üye işlevini çağırın. Bu kaynaklar menülerini ve Hızlandırıcı tablolarını oluşur. Bu işlevin genellikle çağrılma yeri `InitInstance` uygulamanızın.

İle ilişkili menü *nIDOleInPlaceServer* birleştirmek sunucu menüsü kapsayıcının menüsüyle izin ayırıcılar içerir. Sunucu ve kapsayıcının menülerini birleştirme hakkında daha fazla bilgi için bkz [menüler ve kaynaklar (OLE)](../../mfc/menus-and-resources-ole.md).

##  <a name="createpreviewframe"></a>  CDocTemplate::CreatePreviewFrame

Zengin Önizleme için kullanılan bir alt pencere oluşturur.

```
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,
    CDocument* pDoc);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
(Genellikle Kabuk tarafından sağlanan) bir üst penceresine bir işaretçi.

*pDoc*<br/>
İçerikleri önizlemesi bir belge nesnesi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir işaretçi bir `CFrameWnd` nesne veya oluşturulması başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

##  <a name="setpreviewinfo"></a>  CDocTemplate::SetPreviewInfo

İşlem Önizleme işleyicisinin çıkış ayarlar.

```
void SetPreviewInfo(
    UINT nIDPreviewFrame,
    CRuntimeClass* pPreviewFrameClass = NULL,
    CRuntimeClass* pPreviewViewClass = NULL);
```

### <a name="parameters"></a>Parametreler

*nIDPreviewFrame*<br/>
Önizleme çerçevenin bir kaynak Kimliğini belirtir.

*pPreviewFrameClass*<br/>
Bir çalışma zamanı sınıf bilgileri yapısı Önizleme çerçeve işaretçisi belirtir.

*pPreviewViewClass*<br/>
Bir çalışma zamanı sınıf bilgileri yapısı Önizleme görünümü için bir işaretçi belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSingleDocTemplate Sınıfı](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CMultiDocTemplate Sınıfı](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[CDocument Sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CScrollView Sınıfı](../../mfc/reference/cscrollview-class.md)<br/>
[CEditView Sınıfı](../../mfc/reference/ceditview-class.md)<br/>
[CFormView Sınıfı](../../mfc/reference/cformview-class.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[CMDIChildWnd Sınıfı](../../mfc/reference/cmdichildwnd-class.md)
