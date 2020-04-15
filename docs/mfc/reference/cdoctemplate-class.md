---
title: CDocTemplate Sınıfı
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
ms.openlocfilehash: 3376b8febe8ae4586ce649f3f83386875acb678f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375507"
---
# <a name="cdoctemplate-class"></a>CDocTemplate Sınıfı

Belge şablonları için temel işlevselliği tanımlayan soyut bir taban sınıfı.

## <a name="syntax"></a>Sözdizimi

```
class CDocTemplate : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDocTemplate::CDocTemplate](#cdoctemplate)|Bir `CDocTemplate` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CdocTemplate::Adddocument](#adddocument)|Şablona belge ekler.|
|[CdocTemplate::CloseAllDocuments](#closealldocuments)|Bu şablonla ilişkili tüm belgeleri kapatır.|
|[CdocTemplate::CreateNewDocument](#createnewdocument)|Yeni bir belge oluşturur.|
|[CdocTemplate::CreateNewFrame](#createnewframe)|Belge ve görünüm içeren yeni bir çerçeve penceresi oluşturur.|
|[CDocTemplate::CreateOleFrame](#createoleframe)|OLE özellikli bir çerçeve penceresi oluşturur.|
|[CDocTemplate::CreatePreviewFrame](#createpreviewframe)|Rich Preview için kullanılan bir alt çerçeve oluşturur.|
|[CDocTemplate::GetDocString](#getdocstring)|Belge türüyle ilişkili bir dize alır.|
|[CDocTemplate::GetFirstDocPosition](#getfirstdocposition)|Bu şablonla ilişkili ilk belgenin konumunu alır.|
|[CdocTemplate::GetNextDoc](#getnextdoc)|Bir belgeyi ve bir sonrakinin konumunu alır.|
|[CDocTemplate::InitialUpdateFrame](#initialupdateframe)|Çerçeve penceresini başolarak karşılar ve isteğe bağlı olarak görünür hale getirir.|
|[CDocTemplate::LoadTemplate](#loadtemplate)|Belirli `CDocTemplate` veya türetilmiş bir sınıfın kaynaklarını yükler.|
|[CDocTemplate::MatchDocType](#matchdoctype)|Belge türü yle bu şablon arasındaki eşleşmedeki güven derecesini belirler.|
|[CDocTemplate::OpenDocumentFile](#opendocumentfile)|Yol adında niçin belirtilen bir dosyayı açar.|
|[CDocTemplate::RemoveDocument](#removedocument)|Belgeyi şablondan kaldırır.|
|[CdocTemplate::SaveAllModi](#saveallmodified)|Değiştirilen bu şablonla ilişkili tüm belgeleri kaydeder.|
|[CdocTemplate::SetContainerInfo](#setcontainerinfo)|Yerinde ole öğesini düzenlerken OLE kapsayıcılarının kaynaklarını belirler.|
|[CdocTemplate::SetDefaultTitle](#setdefaulttitle)|Belge penceresinin başlık çubuğunda varsayılan başlığı görüntüler.|
|[CDocTemplate::SetPreviewInfo](#setpreviewinfo)|İşlem önizleme işleyicisi dışında kurulumlar.|
|[CDocTemplate::SetServerInfo](#setserverinfo)|Sunucu belgesi eklendiğinde veya yerinde düzenlendiğinde kaynakları ve sınıfları belirler.|

## <a name="remarks"></a>Açıklamalar

Genellikle uygulamanızın `InitInstance` işlevinin uygulanmasında bir veya daha fazla belge şablonu oluşturursunuz. Belge şablonu, üç sınıf türü arasındaki ilişkileri tanımlar:

- Türetilmiştir `CDocument`bir belge sınıfı,

- Yukarıda listelenen belge sınıfından verileri görüntüleyen bir görünüm sınıfı. Bu `CView`sınıfı , , `CScrollView` `CFormView`, veya `CEditView`. (Ayrıca doğrudan `CEditView` kullanabilirsiniz.)

- Görünümü içeren bir çerçeve penceresi sınıfı. Tek bir belge arabirimi (SDI) uygulaması için `CFrameWnd`bu sınıfı . Birden çok belge arabirimi (MDI) uygulaması için `CMDIChildWnd`bu sınıfı . Çerçeve penceresinin davranışını özelleştirmeniz gerekmiyorsa, kendi sınıfınızı `CMDIChildWnd` türetmeden veya doğrudan kullanabilirsiniz. `CFrameWnd`

Uygulamanızda desteklediği her belge türü için bir belge şablonu vardır. Örneğin, uygulamanız hem elektronik tabloları hem de metin belgelerini destekliyorsa, uygulamanın iki belge şablonnesnesi vardır. Her belge şablonu, türündeki tüm belgelerin oluşturulmasından ve yönetilmesinden sorumludur.

Belge şablonu, belge, `CRuntimeClass` görünüm ve çerçeve penceresi sınıfları için nesnelere işaretçiler ilerler. Bu `CRuntimeClass` nesneler, belge şablonu yapılırken belirtilir.

Belge şablonu, belge türüyle birlikte kullanılan kaynakların kimliğini (menü, simge veya hızlandırıcı tablo kaynakları gibi) içerir. Belge şablonu, belge türü hakkında ek bilgiler içeren dizeleri de vardır. Bunlar belge türünün (örneğin, "Çalışma Sayfası") ve dosya uzantısını (örneğin, ".xls") içerir. İsteğe bağlı olarak, uygulamanın kullanıcı arabirimi, Windows Dosya Yöneticisi ve Nesne Bağlama ve Katıştırma (OLE) desteği tarafından kullanılan diğer dizeleri içerebilir.

Uygulamanız bir OLE kapsayıcısı ve/veya sunucusuysa, belge şablonu yerinde etkinleştirme sırasında kullanılan menünün kimliğini de tanımlar. Uygulamanız bir OLE sunucusuysa, belge şablonu yerinde etkinleştirme sırasında kullanılan araç çubuğunun ve menünün kimliğini tanımlar. Bu ek OLE kaynaklarını `SetContainerInfo` arayarak belirtirsiniz ve. `SetServerInfo`

Soyut `CDocTemplate` bir sınıf olduğundan, sınıfı doğrudan kullanamazsınız. Tipik bir uygulama, Microsoft `CDocTemplate`Foundation Class Library tarafından sağlanan `CSingleDocTemplate`iki türemiş sınıftan `CMultiDocTemplate`birini kullanır: SDI'yi uygulayan ve MDI'yi uygulayan. Belge şablonlarını kullanma hakkında daha fazla bilgi için bu sınıflara bakın.

Uygulamanız, SDI veya MDI'den temelde farklı bir kullanıcı arabirimi paradigması `CDocTemplate`gerektiriyorsa, kendi sınıfınızı .

Daha fazla `CDocTemplate`bilgi için [Belge Şablonları ve Belge/Görünüm Oluşturma İşlemi'ne](../../mfc/document-templates-and-the-document-view-creation-process.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`CDocTemplate`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cdoctemplateadddocument"></a><a name="adddocument"></a>CdocTemplate::Adddocument

Şablona belge eklemek için bu işlevi kullanın.

```
virtual void AddDocument(CDocument* pDoc);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Eklenecek belgeiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

CMultiDocTemplate ve [CSingleDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) türemiş sınıflar bu işlevi geçersiz kılar. [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) Kendi belge şablonu sınıfınızı `CDocTemplate`türetilmişseniz, türemiş sınıfınızın bu işlevi geçersiz kılması gerekir.

## <a name="cdoctemplatecdoctemplate"></a><a name="cdoctemplate"></a>CDocTemplate::CDocTemplate

Bir `CDocTemplate` nesne inşa eder.

```
CDocTemplate (
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Parametreler

*nIDKaynak*<br/>
Belge türüyle birlikte kullanılan kaynakların kimliğini belirtir. Bu menü, simge, hızlandırıcı tablo ve dize kaynaklarını içerebilir.

Dize kaynağı ,'\n' karakteriyle ayrılmış en fazla yedi alt dizeden oluşur (bir alt dize dahil değilse yer tutucu olarak '\n' karakteri gereklidir; ancak,'\n' karakterleri izleyerek gerekli değildir); bu alt dizeleri belge türünü açıklar. Alt dizeleri hakkında bilgi için [GetDocString'e](#getdocstring)bakın. Bu dize kaynağı, uygulamanın kaynak dosyasında bulunur. Örneğin:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

Dize '\n' karakteriyle başladığını unutmayın; bunun nedeni, ilk alt dizeMin MDI uygulamaları için kullanılmaması ve bu nedenle dahil olmamasıdır. Bu dizeyi dize düzenleyicisini kullanarak edebilirsiniz; dize tüm dizeleri, yedi ayrı girişleri olarak değil, String Düzenleyicisi tek bir giriş olarak görünür.

*pDocClass*<br/>
Belge sınıfının `CRuntimeClass` nesnesine işaret edin. Bu sınıf, `CDocument`belgelerinizi temsil etmek üzere tanımladığınız türetilmiş bir sınıftır.

*pFrameClass*<br/>
Çerçeve penceresi `CRuntimeClass` sınıfının nesnesine işaret ediyor. Bu sınıf türetilmiş bir `CFrameWnd`sınıf olabilir `CFrameWnd` veya ana çerçeve pencereniz için varsayılan davranış istiyorsanız kendisi olabilir.

*pViewClass*<br/>
Görünüm sınıfının `CRuntimeClass` nesnesine işaret edin. Bu sınıf, `CView`belgelerinizi görüntülemek için tanımladığınız türetilmiş bir sınıftır.

### <a name="remarks"></a>Açıklamalar

Bir `CDocTemplate` nesne oluşturmak için bu üye işlevi kullanın. Bir `CDocTemplate` nesneyi dinamik olarak ayırın ve uygulama sınıfınızın `InitInstance` üye işlevinden [AddDocTemplate'e](../../mfc/reference/cwinapp-class.md#adddoctemplate) aktarın.

## <a name="cdoctemplateclosealldocuments"></a><a name="closealldocuments"></a>CdocTemplate::CloseAllDocuments

Tüm açık belgeleri kapatmak için bu üye işlevini arayın.

```
virtual void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>Parametreler

*bEndSession*<br/>
Kullanılmadı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev genellikle Dosya Çıkışı komutunun bir parçası olarak kullanılır. Bu işlevin varsayılan uygulaması, belgenin verilerini silmek için [CDocument::DeleteContents](../../mfc/reference/cdocument-class.md#deletecontents) üye işlevini çağırır ve belgeye eklenen tüm görünümler için çerçeve pencerelerini kapatır.

Kullanıcının belge kapanmadan önce özel temizleme işlemi gerçekleştirmesini istiyorsanız bu işlevi geçersiz kılın. Örneğin, belge bir veritabanındaki bir kaydı temsil ederse, veritabanını kapatmak için bu işlevi geçersiz kılmak isteyebilirsiniz.

## <a name="cdoctemplatecreatenewdocument"></a><a name="createnewdocument"></a>CdocTemplate::CreateNewDocument

Bu belge şablonuyla ilişkili türde yeni bir belge oluşturmak için bu üye işlevini çağırın.

```
virtual CDocument* CreateNewDocument();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan belgeiçin bir işaretçi veya bir hata oluşursa NULL.

## <a name="cdoctemplatecreatenewframe"></a><a name="createnewframe"></a>CdocTemplate::CreateNewFrame

Belge ve görünüm içeren yeni bir çerçeve penceresi oluşturur.

```
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,
    CFrameWnd* pOther);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Yeni çerçeve penceresinin başvurması gereken belge. NULL olabilir.

*pDiğer*<br/>
Yeni çerçeve penceresinin temel alınabilmek için çerçeve penceresi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan çerçeve penceresiiçin bir işaretçi veya bir hata oluşursa NULL.

### <a name="remarks"></a>Açıklamalar

`CreateNewFrame`görünüm `CRuntimeClass` ve belge ekli yeni bir çerçeve penceresi oluşturmak için oluşturucuya geçirilen nesneleri kullanır. *pDoc* parametresi NULL ise, çerçeve bir TRACE iletisi çıkar.

*pOther* parametresi Pencere Yeni komutunu uygulamak için kullanılır. Yeni çerçeve penceresimodeliçin bir çerçeve penceresi sağlar. Yeni çerçeve penceresi genellikle görünmez oluşturulur. Dosya Yeni ve Dosya Aç'ın standart çerçeve uygulaması dışında çerçeve pencereleri oluşturmak için bu işlevi arayın.

## <a name="cdoctemplatecreateoleframe"></a><a name="createoleframe"></a>CDocTemplate::CreateOleFrame

OLE çerçeve penceresi oluşturur.

```
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,
    CDocument* pDoc,
    BOOL bCreateView);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Çerçevenin ana penceresine işaretçi.

*pDoc*<br/>
Yeni OLE çerçeve penceresinin başvurması gereken belgenin işaretçisi.

*bCreateView*<br/>
Çerçeveyle birlikte bir görünüm oluşturulup oluşturulmadığını belirler.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa çerçeve penceresine işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

*bCreateView* sıfırise boş bir çerçeve oluşturulur.

## <a name="cdoctemplategetdocstring"></a><a name="getdocstring"></a>CDocTemplate::GetDocString

Belge türüyle ilişkili bir dize alır.

```
virtual BOOL GetDocString(
    CString& rString,
    enum DocStringIndex index) const;
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
İşlev döndüğünde `CString` dizeyi içerecek bir nesneye başvuru.

*Dizin*<br/>
Belge türünü açıklayan dizeden alınan alt dizenin dizini. Bu parametre aşağıdaki değerlerden birine sahip olabilir:

- `CDocTemplate::windowTitle`Uygulama penceresinin başlık çubuğunda görünen ad (örneğin, "Microsoft Excel"). Yalnızca SDI uygulamaları için belge şablonunda sunun.

- `CDocTemplate::docName`Varsayılan belge adı için kök (örneğin, "Sayfa"). Bu kök ve bir sayı, kullanıcı Dosya menüsünden Yeni komutu seçtiğinde (örneğin, "Sheet1" veya "Sheet2") bu tür yeni bir belgenin varsayılan adı için kullanılır. Belirtilmemişse, varsayılan olarak "Adsız" kullanılır.

- `CDocTemplate::fileNewName`Bu belge türünün adı. Uygulama birden fazla belge türünü destekliyorsa, bu dize Yeni Dosya iletişim kutusunda görüntülenir (örneğin, "Çalışma Sayfası"). Belirtilmemişse, Yeni Dosya komutu kullanılarak belge türüne erişilemez.

- `CDocTemplate::filterName`Belge türünün açıklaması ve bu tür belgelerle eşleşen joker karakter filtresi. Bu dize, Dosya Aç iletişim kutusundaki Tür açılır listesi listesinde görüntülenir (örneğin, "Çalışma Sayfaları (*.xls)"). Belirtilmemişse, Dosya Aç komutunu kullanarak belge türüne erişilemez.

- `CDocTemplate::filterExt`Bu tür belgelerin uzantısı (örneğin, ".xls"). Belirtilmemişse, Dosya Aç komutunu kullanarak belge türüne erişilemez.

- `CDocTemplate::regFileTypeId`Belge türünün Windows tarafından tutulan kayıt veritabanında depolanacak olması için tanımlayıcı. Bu dize yalnızca dahili kullanım içindir (örneğin, "ExcelWorksheet"). Belirtilmemişse, belge türü Windows Dosya Yöneticisi'ne kaydedilemez.

- `CDocTemplate::regFileTypeName`Kayıt veritabanında depolanacak belge türünün adı. Bu dize, kayıt veritabanına erişen uygulamaların iletişim kutularında görüntülenebilir (örneğin, "Microsoft Excel Çalışma Sayfası").

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alt dize bulunursa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belge türünü açıklayan belirli bir alt dize almak için bu işlevi çağırın. Bu alt dizeleri içeren dize belge şablonunda depolanır ve uygulama için kaynak dosyasındaki bir dizeden türetilir. Çerçeve, uygulamanın kullanıcı arabirimi için gereken dizeleri almak için bu işlevi çağırır. Uygulamanızın belgeleri için bir dosya adı uzantısı belirttiyseniz, çerçeve Windows kayıt veritabanına bir giriş eklerken de bu işlevi çağırır; bu, belgelerin Windows Dosya Yöneticisi'nden açılmasını sağlar.

Bu işlevi yalnızca kendi sınıfınızı `CDocTemplate`.

## <a name="cdoctemplategetfirstdocposition"></a><a name="getfirstdocposition"></a>CDocTemplate::GetFirstDocPosition

Bu şablonla ilişkili ilk belgenin konumunu alır.

```
virtual POSITION GetFirstDocPosition() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu belge şablonuyla ilişkili belgelerin listesi boyunca yinelemek için kullanılabilecek bir KONUM değeri; veya liste boşsa NULL.

### <a name="remarks"></a>Açıklamalar

Bu şablonla ilişkili belgeler listesindeki ilk belgenin konumunu almak için bu işlevi kullanın. ŞABLONLA ilişkili belgelerin listesini yinelemek için KONUM değerini CDocTemplate için bağımsız değişken olarak [kullanın::Şablonla](#getnextdoc) ilişkili belgelerin listesini yinelemek için GetNextDoc.

[CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) ve [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) her ikisi de bu saf sanal işlevi geçersiz kılar. Türetin ettiğiniz `CDocTemplate` herhangi bir sınıf da bu işlevi geçersiz kılmalıdır.

## <a name="cdoctemplategetnextdoc"></a><a name="getnextdoc"></a>CdocTemplate::GetNextDoc

*rPos*tarafından tanımlanan liste öğesini alır ve *rPos'u* listedeki bir sonraki girişin KONUM değerine ayarlar.

```
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu şablonla ilişkili belgeler listesinde ki sonraki belgenin işaretçisi.

### <a name="parameters"></a>Parametreler

*rPos*<br/>
[GetFirstDocPosition](#getfirstdocposition) veya `GetNextDoc`.

### <a name="remarks"></a>Açıklamalar

Alınan öğe listenin son öğesiyse, *rPos'un* yeni değeri NULL olarak ayarlanır.

`GetNextDoc` [GetFirstDocPosition'a](#getfirstdocposition)bir çağrı ile ilk konumu belirlerseniz, bir ileri yineleme döngüsünde kullanabilirsiniz.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

## <a name="cdoctemplateinitialupdateframe"></a><a name="initialupdateframe"></a>CDocTemplate::InitialUpdateFrame

Çerçeve penceresini başolarak karşılar ve isteğe bağlı olarak görünür hale getirir.

```
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,
    CDocument* pDoc,
    BOOL bMakeVisible = TRUE);
```

### <a name="parameters"></a>Parametreler

*pFrame*<br/>
İlk güncelleştirmeye ihtiyaç olan çerçeve penceresi.

*pDoc*<br/>
Çerçevenin ilişkili olduğu belge. NULL olabilir.

*bMakeVisible*<br/>
Çerçevenin görünür ve etkin olup olmaması gerektiğini gösterir.

### <a name="remarks"></a>Açıklamalar

Yeni `IntitialUpdateFrame` bir çerçeve oluşturduktan sonra `CreateNewFrame`arayın. Bu işlevi çağırmak, bu çerçeve penceresindeki `OnInitialUpdate` görünümlerin çağrılarını almasına neden olur. Ayrıca, daha önce etkin bir görünüm yoksa, çerçeve penceresinin birincil görünümü etkin hale getirilir; birincil görünüm, AFX_IDW_PANE_FIRST çocuk kimliğine sahip bir görünümdür. Son olarak, *bMakeVisible* sıfır değilse çerçeve penceresi görünür hale getirilir. *bMakeVisible* sıfır ise, çerçeve penceresinin geçerli odak ve görünür durumu değişmeden kalır.

Dosya Yeni ve Dosya Aç'ın çerçevesinin uygulamasını kullanırken bu işlevi aramak gerekli değildir.

## <a name="cdoctemplateloadtemplate"></a><a name="loadtemplate"></a>CDocTemplate::LoadTemplate

Belirli `CDocTemplate` veya türetilmiş bir sınıfın kaynaklarını yükler.

```
virtual void LoadTemplate();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, belirli veya türetilmiş `CDocTemplate` bir sınıfın kaynaklarını yüklemek için çerçeve tarafından çağrılır. Normalde, şablonun genel olarak oluşturuldurduğu durumlar dışında, inşaat sırasında çağrılır. Bu durumda, arama `LoadTemplate` CWinApp kadar geciktirilir::AddDocTemplate denir. [CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate)

## <a name="cdoctemplatematchdoctype"></a><a name="matchdoctype"></a>CDocTemplate::MatchDocType

Belge türü yle bu şablon arasındaki eşleşmedeki güven derecesini belirler.

```
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,
    CDocument*& rpDocMatch);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Türü belirlenecek dosyanın yol adı.

*rpDocMatch*<br/>
*LpszPathName* tarafından belirtilen dosya zaten açıksa, eşleşen belgeatanan bir belgeyi işaretle.

### <a name="return-value"></a>Dönüş Değeri

**Güven** numaralandırmasından bir değer, aşağıdaki gibi tanımlanır:

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

Dosyaaçmak için kullanılacak belge şablonu türünü belirlemek için bu işlevi kullanın. Örneğin, uygulamanız birden çok dosya türünü destekliyorsa, her şabloniçin sırayla çağrıda bulunarak `MatchDocType` ve döndürülen güven değerine göre şablon seçerek, kullanılabilir belge şablonlarından hangisinin belirli bir dosya için uygun olduğunu belirlemek için bu işlevi kullanabilirsiniz.

*lpszPathName* tarafından belirtilen dosya zaten açıksa, bu işlev döndürür `CDocTemplate::yesAlreadyOpen` ve dosyanın `CDocument` nesnesini *rpDocMatch'te*nesneye kopyalar.

Dosya açık değilse ancak *lpszPathName'deki* uzantı, `CDocTemplate::filterExt` `CDocTemplate::yesAttemptNative` *rpDocMatch'i* NULL olarak döndürür ve ayarlar. Hakkında daha `CDocTemplate::filterExt`fazla bilgi için [bkz: CDocTemplate::GetDocString](#getdocstring).

Her iki durum da doğruysa, işlev döndürür. `CDocTemplate::yesAttemptForeign`

Varsayılan uygulama geri `CDocTemplate::maybeAttemptForeign` dönmüyor veya `CDocTemplate::maybeAttemptNative`. Uygulamanız için uygun tür eşleştirme mantığını uygulamak için bu işlevi geçersiz kılın, belki de **Güven** numaralandırmasından bu iki değeri kullanarak.

## <a name="cdoctemplateopendocumentfile"></a><a name="opendocumentfile"></a>CDocTemplate::OpenDocumentFile

Yol tarafından belirtilen bir dosyayı açar.

```
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;

virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU) = 0;
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
[içinde] Açılacak belgeyi içeren dosyanın yolunu işaretçi.

*bAddToMRU*<br/>
[içinde] TRUE, belgenin en son dosyalardan biri olduğunu gösterir; FALSE, belgenin en son dosyalardan biri olmadığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Dosyası *lpszPathName*tarafından adlandırılan belgeiçin bir işaretçi; Başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Yolu *lpszPathName*tarafından belirtilen dosyayı açar. *lpszPathName* NULL ise, bu şablonla ilişkili türbir belge içeren yeni bir dosya oluşturulur.

## <a name="cdoctemplateremovedocument"></a><a name="removedocument"></a>CDocTemplate::RemoveDocument

*pDoc* tarafından işaret edilen belgeyi bu şablonla ilişkili belgeler listesinden kaldırır.

```
virtual void RemoveDocument(CDocument* pDoc);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Kaldırılacak belgenin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Türetilen `CMultiDocTemplate` sınıflar `CSingleDocTemplate` ve bu işlevi geçersiz kılar. Kendi belge şablonu sınıfınızı `CDocTemplate`türetilmişseniz, türemiş sınıfınızın bu işlevi geçersiz kılması gerekir.

## <a name="cdoctemplatesaveallmodified"></a><a name="saveallmodified"></a>CdocTemplate::SaveAllModi

Değiştirilen tüm belgeleri kaydeder.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır sız; aksi takdirde 0.

## <a name="cdoctemplatesetcontainerinfo"></a><a name="setcontainerinfo"></a>CdocTemplate::SetContainerInfo

Yerinde ole öğesini düzenlerken OLE kapsayıcılarının kaynaklarını belirler.

```
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```

### <a name="parameters"></a>Parametreler

*nIDOleInPlaceKonteyner*<br/>
Katıştırılmış bir nesne etkinleştirildiğinde kullanılan kaynakların kimliği.

### <a name="remarks"></a>Açıklamalar

Bir OLE nesnesi yerinde etkinleştirildiğinde kullanılacak kaynakları ayarlamak için bu işlevi çağırın. Bu kaynaklar menüler ve hızlandırıcı tabloları içerebilir. Bu işlev genellikle [CWinApp denir::Uygulamanızın InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) fonksiyonu.

*nIDOleInPlaceContainer* ile ilişkili menü, etkinleştirilen yerinde öğenin menüsünün kapsayıcı uygulamasının menüsüyle birleşmesini sağlayan ayırıcılar içerir. Sunucu ve kapsayıcı menülerini birleştirme hakkında daha fazla bilgi için [Menüler ve Kaynaklar (OLE)](../../mfc/menus-and-resources-ole.md)makalesine bakın.

## <a name="cdoctemplatesetdefaulttitle"></a><a name="setdefaulttitle"></a>CdocTemplate::SetDefaultTitle

Belgenin varsayılan başlığını yüklemek ve belgenin başlık çubuğunda görüntülemek için bu işlevi arayın.

```
virtual void SetDefaultTitle(CDocument* pDocument) = 0;
```

### <a name="parameters"></a>Parametreler

*pBelge*<br/>
Başlığı ayarlanacak belgeyi işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan başlık hakkında bilgi için `CDocTemplate::docName` [CDocTemplate::GetDocString'deki](#getdocstring)açıklamaya bakın.

## <a name="cdoctemplatesetserverinfo"></a><a name="setserverinfo"></a>CDocTemplate::SetServerInfo

Sunucu belgesi eklendiğinde veya yerinde düzenlendiğinde kaynakları ve sınıfları belirler.

```
void SetServerInfo(
    UINT nIDOleEmbedding,
    UINT nIDOleInPlaceServer = 0,
    CRuntimeClass* pOleFrameClass = NULL,
    CRuntimeClass* pOleViewClass = NULL);
```

### <a name="parameters"></a>Parametreler

*nIDOleGömme*<br/>
Katıştırılmış bir nesne ayrı bir pencerede açıldığında kullanılan kaynakların kimliği.

*nIDOleInPlaceServer*<br/>
Katıştırılmış bir nesne yerinde etkinleştirildiğinde kullanılan kaynakların kimliği.

*pOleFrameClass*<br/>
Yerinde etkinleştirme gerçekleştiğinde oluşturulan çerçeve penceresi nesnesi için sınıf bilgilerini içeren bir [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısıişaretçisi.

*pOleViewClass*<br/>
Yerinde etkinleştirme gerçekleştiğinde oluşturulan görünüm nesnesi için sınıf bilgilerini içeren bir `CRuntimeClass` yapıyı işaretçi.

### <a name="remarks"></a>Açıklamalar

Kullanıcı katıştırılmış bir nesnenin etkinleştirilmesi istediğinde sunucu uygulaması tarafından kullanılacak kaynakları tanımlamak için bu üye işlevi arayın. Bu kaynaklar menüler ve hızlandırıcı tablolardan oluşur. Bu işlev genellikle uygulamanızın adıdır. `InitInstance`

*nIDOleInPlaceServer* ile ilişkili menü, sunucu menüsünün kapsayıcının menüsüyle birleşmesini sağlayan ayırıcılar içerir. Sunucu ve kapsayıcı menülerini birleştirme hakkında daha fazla bilgi için [Menüler ve Kaynaklar (OLE)](../../mfc/menus-and-resources-ole.md)makalesine bakın.

## <a name="cdoctemplatecreatepreviewframe"></a><a name="createpreviewframe"></a>CDocTemplate::CreatePreviewFrame

Rich Preview için kullanılan bir alt çerçeve oluşturur.

```
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,
    CDocument* pDoc);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Üst pencereiçin bir işaretçi (genellikle Shell tarafından sağlanmıştır).

*pDoc*<br/>
İçeriği öngösterilecek olan bir belge nesnesi için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bir nesneye `CFrameWnd` geçerli bir işaretçi veya oluşturma başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cdoctemplatesetpreviewinfo"></a><a name="setpreviewinfo"></a>CDocTemplate::SetPreviewInfo

İşlem dışı önizleme işleyicisini ayarlar.

```
void SetPreviewInfo(
    UINT nIDPreviewFrame,
    CRuntimeClass* pPreviewFrameClass = NULL,
    CRuntimeClass* pPreviewViewClass = NULL);
```

### <a name="parameters"></a>Parametreler

*nIDPreviewFrame*<br/>
Önizleme çerçevesinin kaynak kimliğini belirtir.

*pPreviewFrameClass*<br/>
Önizleme çerçevesinin çalışma zamanı sınıf bilgi yapısına işaretçi belirtir.

*pPreviewViewClass*<br/>
Önizleme görünümünün çalışma zamanı sınıf bilgi yapısına işaretçi belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSingledocTemplate Sınıfı](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CMultidocTemplate Sınıfı](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[Kişniş Sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CScrollView Sınıfı](../../mfc/reference/cscrollview-class.md)<br/>
[CEditView Sınıfı](../../mfc/reference/ceditview-class.md)<br/>
[CFormView Sınıfı](../../mfc/reference/cformview-class.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[CMDIChildWnd Sınıfı](../../mfc/reference/cmdichildwnd-class.md)
