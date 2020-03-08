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
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855516"
---
# <a name="cdoctemplate-class"></a>CDocTemplate sınıfı

Belge şablonları için temel işlevselliği tanımlayan bir soyut temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CDocTemplate : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDocTemplate:: CDocTemplate](#cdoctemplate)|`CDocTemplate` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDocTemplate:: AddDocument](#adddocument)|Bir şablona belge ekler.|
|[CDocTemplate:: CloseAllDocuments](#closealldocuments)|Bu şablonla ilişkili tüm belgeleri kapatır.|
|[CDocTemplate:: CreateNewDocument](#createnewdocument)|Yeni bir belge oluşturur.|
|[CDocTemplate:: CreateNewFrame](#createnewframe)|Belge ve görünüm içeren yeni bir çerçeve penceresi oluşturur.|
|[CDocTemplate:: CreateOleFrame](#createoleframe)|OLE etkin bir çerçeve penceresi oluşturur.|
|[CDocTemplate:: Createönizleme çerçevesi](#createpreviewframe)|Zengin Önizleme için kullanılan bir alt çerçeve oluşturur.|
|[CDocTemplate:: GetDocString](#getdocstring)|Belge türüyle ilişkili bir dize alır.|
|[CDocTemplate:: GetFirstDocPosition](#getfirstdocposition)|Bu şablonla ilişkili ilk belgenin konumunu alır.|
|[CDocTemplate:: GetNextDoc](#getnextdoc)|Bir belgeyi ve bir sonraki konumunu alır.|
|[CDocTemplate:: ınitialupdateframe](#initialupdateframe)|Çerçeve penceresini başlatır ve isteğe bağlı olarak görünür hale getirir.|
|[CDocTemplate:: LoadTemplate](#loadtemplate)|Belirli bir `CDocTemplate` veya türetilmiş sınıf için kaynakları yükler.|
|[CDocTemplate:: MatchDocType](#matchdoctype)|Bir belge türü ve bu şablon arasındaki eşleşmenin güven derecesini belirler.|
|[CDocTemplate:: OpenDocumentFile](#opendocumentfile)|Bir yol adıyla belirtilen bir dosya açar.|
|[CDocTemplate:: RemoveDocument](#removedocument)|Bir şablondan belge kaldırır.|
|[CDocTemplate:: SaveAllModified](#saveallmodified)|Bu şablonla ilişkili tüm belgeleri kaydeder.|
|[CDocTemplate:: SetContainerInfo](#setcontainerinfo)|Yerinde OLE öğesi düzenlenirken OLE kapsayıcılarının kaynaklarını belirler.|
|[CDocTemplate:: SetDefaultTitle](#setdefaulttitle)|Belge penceresinin başlık çubuğundaki varsayılan başlığı görüntüler.|
|[CDocTemplate:: Setpreviewınınfo](#setpreviewinfo)|İşlem Önizleme işleyicisini ayarlar.|
|[CDocTemplate:: SetServerInfo](#setserverinfo)|Sunucu belgesi katıştırılmış veya yerinde düzenlendiğinde kaynakları ve sınıfları belirler.|

## <a name="remarks"></a>Açıklamalar

Genellikle uygulamanızın `InitInstance` işlevinin uygulamasında bir veya daha fazla belge şablonu oluşturursunuz. Belge şablonu, üç tür sınıf arasındaki ilişkileri tanımlar:

- `CDocument`türettiğiniz bir belge sınıfı.

- Yukarıda listelenen belge sınıfından verileri görüntüleyen bir görünüm sınıfı. Bu sınıfı `CView`, `CScrollView`, `CFormView`veya `CEditView`türetilebilir. (`CEditView` doğrudan de kullanabilirsiniz.)

- Görünümü içeren bir çerçeve pencere sınıfı. Tek belgeli arabirim (SDI) uygulaması için, bu sınıfı `CFrameWnd`türetirsiniz. Birden çok belge arabirimi (MDI) uygulaması için, bu sınıfı `CMDIChildWnd`türetirsiniz. Çerçeve penceresinin davranışını özelleştirmeniz gerekmiyorsa, doğrudan kendi sınıfınızı türetmeden `CFrameWnd` veya `CMDIChildWnd` kullanabilirsiniz.

Uygulamanızda desteklediği her belge türü için bir belge şablonu vardır. Örneğin, uygulamanız hem elektronik tabloları hem de metin belgelerini destekliyorsa, uygulamanın iki belge şablonu nesnesi vardır. Her belge şablonu, türünün tüm belgelerini oluşturmaktan ve yönetmekten sorumludur.

Belge şablonu, belge, görünüm ve çerçeve penceresi sınıfları için `CRuntimeClass` nesnelerine işaretçiler depolar. Bu `CRuntimeClass` nesneleri bir belge şablonu oluşturulurken belirtilir.

Belge şablonu, belge türü (menü, simge veya Hızlandırıcı tablo kaynakları gibi) ile kullanılan kaynakların KIMLIĞINI içerir. Belge şablonunda Ayrıca belge türü hakkında ek bilgiler içeren dizeler de vardır. Bunlar belge türünün adını (örneğin, "çalışma sayfası") ve dosya uzantısını (örneğin, ". xls") içerir. İsteğe bağlı olarak, uygulamanın kullanıcı arabirimi, Windows Dosya Yöneticisi ve nesne bağlama ve Katıştırma (OLE) desteği tarafından kullanılan diğer dizeleri içerebilir.

Uygulamanız bir OLE kapsayıcısı ve/veya sunucusu ise, belge şablonu Ayrıca yerinde etkinleştirme sırasında kullanılan menünün KIMLIĞINI de tanımlar. Uygulamanız bir OLE sunucusu ise, belge şablonu, yerinde etkinleştirme sırasında kullanılan araç çubuğunun ve menünün KIMLIĞINI tanımlar. Bu ek OLE kaynaklarını `SetContainerInfo` ve `SetServerInfo`çağırarak belirlersiniz.

`CDocTemplate` soyut bir sınıf olduğundan, sınıfı doğrudan kullanamazsınız. Tipik bir uygulama, Microsoft Foundation Class Kitaplığı tarafından sunulan iki `CDocTemplate`türetilmiş sınıftan birini kullanır: SDI uygulayan `CSingleDocTemplate`ve MDI uygulayan `CMultiDocTemplate`. Belge şablonlarını kullanma hakkında daha fazla bilgi için bu sınıflara bakın.

Uygulamanız SDI veya MDI 'dan temelde farklılık gösteren bir kullanıcı arabirimi paradigmasını gerektiriyorsa, `CDocTemplate`kendi sınıfınızı türetebilirsiniz.

`CDocTemplate`hakkında daha fazla bilgi için bkz. [Belge şablonları ve belge/görünüm oluşturma işlemi](../../mfc/document-templates-and-the-document-view-creation-process.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocTemplate`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="adddocument"></a>CDocTemplate:: AddDocument

Bir şablona belge eklemek için bu işlevi kullanın.

```
virtual void AddDocument(CDocument* pDoc);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Eklenecek belgeye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflar [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) ve [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) bu işlevi geçersiz kılar. Kendi belge şablonu sınıfınızı `CDocTemplate`türettiğinizde, türetilmiş sınıfınız bu işlevi geçersiz kılmalıdır.

##  <a name="cdoctemplate"></a>CDocTemplate:: CDocTemplate

`CDocTemplate` nesnesi oluşturur.

```
CDocTemplate (
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Parametreler

*nIDResource*<br/>
Belge türüyle kullanılan kaynakların KIMLIĞINI belirtir. Bu, menü, simge, Hızlandırıcı tablosu ve dize kaynakları içerebilir.

Dize kaynağı, ' \n ' karakteriyle ayrılmış en fazla yedi alt dizeden oluşur (alt dize dahil değilse, bir yer tutucu olarak ' \n ' karakteri gerekir; ancak sondaki ' \n ' karakterleri gerekli değildir); Bu alt dizeler belge türünü anlatmaktadır. Alt dizeler hakkında daha fazla bilgi için bkz. [GetDocString](#getdocstring). Bu dize kaynağı, uygulamanın kaynak dosyasında bulunur. Örnek:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

Dizenin bir ' \n ' karakteriyle başlayacağını unutmayın; Bunun nedeni, ilk alt dizenin MDI uygulamaları için kullanılmadığından ve bu nedenle dahil edilmez. Bu dizeyi dize düzenleyicisini kullanarak düzenleyebilirsiniz; Tüm dize, dize düzenleyicisinde yedi ayrı girdi olarak değil tek bir girdi olarak görünür.

*pDocClass*<br/>
Belge sınıfının `CRuntimeClass` nesnesine işaret eder. Bu sınıf, belgelerinizi temsil etmek için tanımladığınız `CDocument`türetilmiş bir sınıftır.

*pFrameClass*<br/>
Çerçeve penceresi sınıfının `CRuntimeClass` nesnesine işaret eder. Bu sınıf `CFrameWnd`türetilmiş bir sınıf olabilir veya ana çerçeve pencerenizin varsayılan davranışını istiyorsanız `CFrameWnd` olabilir.

*pViewClass*<br/>
Görünüm sınıfının `CRuntimeClass` nesnesine işaret eder. Bu sınıf, belgelerinizi göstermek için tanımladığınız `CView`türetilmiş bir sınıftır.

### <a name="remarks"></a>Açıklamalar

`CDocTemplate` nesnesi oluşturmak için bu üye işlevini kullanın. `CDocTemplate` nesnesini dinamik olarak ayırın ve uygulama sınıfınızın `InitInstance` üye işlevinden [CWinApp:: AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) 'e geçirin.

##  <a name="closealldocuments"></a>CDocTemplate:: CloseAllDocuments

Tüm açık belgeleri kapatmak için bu üye işlevini çağırın.

```
virtual void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>Parametreler

*bEndSession*<br/>
Kullanılmadı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev genellikle dosya çıkış komutunun bir parçası olarak kullanılır. Bu işlevin varsayılan uygulanması [CDocument::D eleteContents](../../mfc/reference/cdocument-class.md#deletecontents) üye işlevini çağırarak belgenin verilerini siler ve ardından belgeye ekli tüm görünümlerin çerçeve pencerelerini kapatır.

Kullanıcının Belge kapatılmadan önce özel temizleme işlemi gerçekleştirmesini gerektirmek istiyorsanız bu işlevi geçersiz kılın. Örneğin, belge bir veritabanındaki kaydı temsil ediyorsa, veritabanını kapatmak için bu işlevi geçersiz kılmak isteyebilirsiniz.

##  <a name="createnewdocument"></a>CDocTemplate:: CreateNewDocument

Bu belge şablonuyla ilişkili türde yeni bir belge oluşturmak için bu üye işlevini çağırın.

```
virtual CDocument* CreateNewDocument();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan belgeye yönelik bir işaretçi veya bir hata oluşursa NULL.

##  <a name="createnewframe"></a>CDocTemplate:: CreateNewFrame

Belge ve görünüm içeren yeni bir çerçeve penceresi oluşturur.

```
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,
    CFrameWnd* pOther);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Yeni çerçeve penceresinin başvurması gereken belge. NULL olabilir.

*pOther*<br/>
Yeni çerçeve penceresinin temel alınacağı çerçeve penceresi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan çerçeve penceresine yönelik bir işaretçi veya bir hata oluşursa NULL.

### <a name="remarks"></a>Açıklamalar

`CreateNewFrame`, bir görünüm ve belge eklenmiş yeni bir çerçeve penceresi oluşturmak için oluşturucuya geçirilen `CRuntimeClass` nesnelerini kullanır. *PDoc* parametresi null ise, çerçeve bir izleme iletisi çıkarır.

*Pother* parametresi pencere yeni komutunu uygulamak için kullanılır. Yeni çerçeve penceresini modelleyebilir bir çerçeve penceresi sağlar. Yeni çerçeve penceresi genellikle görünmez olarak oluşturulur. Yeni dosya ve dosya aç standart Framework uygulamasının dışında çerçeve pencereleri oluşturmak için bu işlevi çağırın.

##  <a name="createoleframe"></a>CDocTemplate:: CreateOleFrame

OLE çerçevesi penceresi oluşturur.

```
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,
    CDocument* pDoc,
    BOOL bCreateView);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Çerçevenin üst penceresine yönelik bir işaretçi.

*pDoc*<br/>
Yeni OLE çerçevesi penceresinin başvurması gereken belgeye yönelik bir işaretçi.

*bCreateView*<br/>
Kareyle birlikte bir görünümün oluşturulup oluşturulmayacağını belirler.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa çerçeve penceresine yönelik bir işaretçi; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

*BCreateView* sıfırsa boş bir çerçeve oluşturulur.

##  <a name="getdocstring"></a>CDocTemplate:: GetDocString

Belge türüyle ilişkili bir dize alır.

```
virtual BOOL GetDocString(
    CString& rString,
    enum DocStringIndex index) const;
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
İşlevin döndürdüğü dizeyi içeren `CString` nesnesine bir başvuru.

*indeks*<br/>
Belge türünü tanımlayan dizeden alınan alt dizenin bir dizini. Bu parametre aşağıdaki değerlerden birine sahip olabilir:

- uygulama penceresinin başlık çubuğunda görünen adı `CDocTemplate::windowTitle` (örneğin, "Microsoft Excel"). Yalnızca SDI uygulamalarına ait belge şablonunda bulunur.

- Varsayılan belge adı için kök `CDocTemplate::docName` (örneğin, "sayfa"). Bu kök, ve bir sayı, Kullanıcı Dosya menüsünden Yeni komutu seçtiğinde bu türün varsayılan adı için kullanılır (örneğin, "Sheet1" veya "Sheet2"). Belirtilmemişse, varsayılan olarak "Başlıksız" kullanılır.

- Bu belge türünün adı `CDocTemplate::fileNewName`. Uygulama birden fazla belge türünü destekliyorsa, bu dize dosya yeni iletişim kutusunda (örneğin, "çalışma sayfası") görüntülenir. Belirtilmezse, dosya yeni komutu kullanılarak belge türüne erişilemez.

- belge türünün açıklaması ve bu türdeki belgelerle eşleşen bir joker karakter filtresi `CDocTemplate::filterName`. Bu dize, dosya Aç iletişim kutusunda (örneğin, "çalışma sayfaları (*. xls)") açılan liste dosyalarını Listele listesinde görüntülenir. Belirtilmemişse, dosya Aç komutu kullanılarak belge türüne erişilemez.

- Bu türdeki belgeler için `CDocTemplate::filterExt` uzantısı (örneğin, ". xls"). Belirtilmemişse, dosya Aç komutu kullanılarak belge türüne erişilemez.

- Windows tarafından tutulan kayıt veritabanında depolanacak belge türü için tanımlayıcı `CDocTemplate::regFileTypeId`. Bu dize yalnızca iç kullanım içindir (örneğin, "ExcelWorksheet"). Belirtilmemişse, belge türü Windows Dosya Yöneticisi ile kaydedilemez.

- kayıt veritabanında depolanacak belge türünün adı `CDocTemplate::regFileTypeName`. Bu dize, kayıt veritabanına erişen uygulamaların iletişim kutularında görüntülenebilir (örneğin, "Microsoft Excel çalışma sayfası").

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alt dize bulunursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belge türünü açıklayan belirli bir alt dizeyi almak için bu işlevi çağırın. Bu alt dizeleri içeren dize, belge şablonunda depolanır ve uygulamanın kaynak dosyasındaki bir dizeden türetilir. Framework, uygulamanın kullanıcı arabirimi için ihtiyaç duyacağı dizeleri almak için bu işlevi çağırır. Uygulamanızın belgeleri için bir dosya adı uzantısı belirttiyseniz, çerçeve Windows kayıt veritabanına bir giriş eklerken bu işlevi de çağırır; Bu, belgelerin Windows Dosya Yöneticisi 'nden açılmasını sağlar.

Yalnızca kendi sınıfınızı `CDocTemplate`türetmeniz durumunda bu işlevi çağırın.

##  <a name="getfirstdocposition"></a>CDocTemplate:: GetFirstDocPosition

Bu şablonla ilişkili ilk belgenin konumunu alır.

```
virtual POSITION GetFirstDocPosition() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu belge şablonuyla ilişkili belge listesinde yinelemek için kullanılabilen bir konum değeri; veya liste boşsa NULL.

### <a name="remarks"></a>Açıklamalar

Bu şablonla ilişkili belge listesindeki ilk belgenin konumunu almak için bu işlevi kullanın. Şablonla ilişkili belge listesini yinelemek için [CDocTemplate:: GetNextDoc](#getnextdoc) için bir bağımsız DEĞIŞKEN olarak konum değerini kullanın.

[CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) ve [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) her ikisi de bu saf sanal işlevi geçersiz kılar. `CDocTemplate` türettiğiniz herhangi bir sınıf Ayrıca bu işlevi geçersiz kılmalıdır.

##  <a name="getnextdoc"></a>CDocTemplate:: GetNextDoc

*RPos*tarafından tanımlanan liste öğesini alır ve *rPos* 'u LISTEDEKI bir sonraki girdinin konum değerine ayarlar.

```
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bu şablonla ilişkili belge listesindeki sonraki belgeye yönelik bir işaretçi.

### <a name="parameters"></a>Parametreler

*RPO 'lar*<br/>
Önceki [GetFirstDocPosition](#getfirstdocposition) veya `GetNextDoc`çağrısıyla döndürülen bir konum değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Alınan öğe listedeki son ise, *rPos* 'un yenı değeri null olarak ayarlanır.

İlk konumu [GetFirstDocPosition](#getfirstdocposition)çağrısıyla birlikte ayarlarsanız, bir iletme yineleme döngüsünde `GetNextDoc` kullanabilirsiniz.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

##  <a name="initialupdateframe"></a>CDocTemplate:: ınitialupdateframe

Çerçeve penceresini başlatır ve isteğe bağlı olarak görünür hale getirir.

```
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,
    CDocument* pDoc,
    BOOL bMakeVisible = TRUE);
```

### <a name="parameters"></a>Parametreler

*pFrame*<br/>
İlk güncelleştirmeye ihtiyacı olan çerçeve penceresi.

*pDoc*<br/>
Çerçevenin ilişkilendirildiği belge. NULL olabilir.

*bMakeVisible*<br/>
Çerçevenin görünür ve etkin hale gelmesi gerekip gerekmediğini gösterir.

### <a name="remarks"></a>Açıklamalar

`CreateNewFrame`ile yeni bir çerçeve oluşturduktan sonra `IntitialUpdateFrame` çağırın. Bu işlevi çağırmak, bu çerçeve penceresindeki görünümlerin `OnInitialUpdate` çağrılarını almasına neden olur. Ayrıca, daha önce etkin bir görünüm yoksa, çerçeve penceresinin birincil görünümü etkin hale getirilir; birincil görünüm, AFX_IDW_PANE_FIRST alt KIMLIĞI olan bir görünümüdür. Son olarak, *bMakeVisible* sıfır değilse çerçeve penceresi görünür hale getirilir. *BMakeVisible* sıfırsa, çerçeve penceresinin geçerli odağı ve görünür durumu değişmeden kalır.

Framework 'ün yeni dosya ve dosya açma uygulamasının uygulanması kullanılırken bu işlevi çağırmak gerekli değildir.

##  <a name="loadtemplate"></a>CDocTemplate:: LoadTemplate

Belirli bir `CDocTemplate` veya türetilmiş sınıf için kaynakları yükler.

```
virtual void LoadTemplate();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, belirli bir `CDocTemplate` veya türetilmiş sınıf için kaynakları yüklemek üzere çerçevesi tarafından çağırılır. Normalde oluşturma sırasında, şablonun Global olarak oluşturulması dışında çağrılır. Bu durumda, [CWinApp:: AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) çağrılana kadar `LoadTemplate` çağrısı gecikir.

##  <a name="matchdoctype"></a>CDocTemplate:: MatchDocType

Bir belge türü ve bu şablon arasındaki eşleşmenin güven derecesini belirler.

```
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,
    CDocument*& rpDocMatch);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Türü belirlenecek dosyanın yol adı.

*rpDocMatch*<br/>
*LpszPathName* tarafından belirtilen dosya zaten açıksa, eşleşen belgeye atanan bir belgeye yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

**Güven** numaralandırmasından aşağıdaki şekilde tanımlanan bir değer:

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

Dosya açmak için kullanılacak belge şablonu türünü öğrenmek için bu işlevi kullanın. Uygulamanız birden çok dosya türünü destekliyorsa, örneğin, her bir şablon için `MatchDocType` çağırarak ve döndürülen güvenirlik değerine göre bir şablon seçerek, kullanılabilir belge şablonlarının hangisinin belirli bir dosyaya uygun olduğunu belirlemek için bu işlevi kullanabilirsiniz.

*LpszPathName* tarafından belirtilen dosya zaten açıksa, bu işlev `CDocTemplate::yesAlreadyOpen` döndürür ve dosyanın `CDocument` nesnesini *rpDocMatch*konumundaki nesneye kopyalar.

Dosya açık değilse ancak *lpszPathName* 'deki uzantı `CDocTemplate::filterExt`tarafından belirtilen uzantıyla eşleşiyorsa, bu işlev `CDocTemplate::yesAttemptNative` döndürür ve *RPDOCMATCH* 'i null olarak ayarlar. `CDocTemplate::filterExt`hakkında daha fazla bilgi için bkz. [CDocTemplate:: GetDocString](#getdocstring).

Hiçbir durum doğru değilse, işlev `CDocTemplate::yesAttemptForeign`döndürür.

Varsayılan uygulama `CDocTemplate::maybeAttemptForeign` veya `CDocTemplate::maybeAttemptNative`döndürmez. Güvenilir **Numaralandırmadaki** bu iki değeri kullanarak, uygulamanıza uygun tür eşleştirme mantığını uygulamak için bu işlevi geçersiz kılın.

##  <a name="opendocumentfile"></a>CDocTemplate:: OpenDocumentFile

Bir yol tarafından belirtilen bir dosya açar.

```
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;

virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU) = 0;
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
'ndaki Açılacak belgeyi içeren dosyanın yolu işaretçisi.

*bAddToMRU*<br/>
'ndaki TRUE, belgenin en son dosyalardan biri olduğunu belirtir; FALSE, belgenin en son dosyalardan biri olmadığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Dosyası *lpszPathName*tarafından adlandırılan belgeye yönelik işaretçi Başarısız ise NULL.

### <a name="remarks"></a>Açıklamalar

Yolu *lpszPathName*tarafından belirtilen dosyayı açar. *LPSZPATHNAME* null ise, bu şablonla ilişkili türdeki bir belgeyi içeren yeni bir dosya oluşturulur.

##  <a name="removedocument"></a>CDocTemplate:: RemoveDocument

Bu şablonla ilişkili belge listesinden *pDoc* tarafından işaret edilen belgeyi kaldırır.

```
virtual void RemoveDocument(CDocument* pDoc);
```

### <a name="parameters"></a>Parametreler

*pDoc*<br/>
Kaldırılacak belgeye yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflar `CMultiDocTemplate` ve `CSingleDocTemplate` bu işlevi geçersiz kılar. Kendi belge şablonu sınıfınızı `CDocTemplate`türettiğinizde, türetilmiş sınıfınız bu işlevi geçersiz kılmalıdır.

##  <a name="saveallmodified"></a>CDocTemplate:: SaveAllModified

Değiştirilen tüm belgeleri kaydeder.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır dışı; Aksi takdirde 0.

##  <a name="setcontainerinfo"></a>CDocTemplate:: SetContainerInfo

Yerinde OLE öğesi düzenlenirken OLE kapsayıcılarının kaynaklarını belirler.

```
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```

### <a name="parameters"></a>Parametreler

*Nidokaınplacecontainer*<br/>
Katıştırılmış bir nesne etkinleştirildiğinde kullanılan kaynakların KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bir OLE nesnesi yerinde etkinleştirildiğinde kullanılacak kaynakları ayarlamak için bu işlevi çağırın. Bu kaynaklar, menüler ve Hızlandırıcı tabloları içerebilir. Bu işlev genellikle uygulamanızın [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) işlevinde çağrılır.

*Nidopainplacecontainer* ile ilişkili menü, etkinleştirilmiş yerinde öğenin menüsünün kapsayıcı uygulamasının menüsüyle birleştirilmesine izin veren ayırıcılar içerir. Sunucu ve kapsayıcı menülerini birleştirme hakkında daha fazla bilgi için bkz. [menüler ve kaynaklar (OLE)](../../mfc/menus-and-resources-ole.md).

##  <a name="setdefaulttitle"></a>CDocTemplate:: SetDefaultTitle

Belgenin varsayılan başlığını yüklemek ve belgenin başlık çubuğunda göstermek için bu işlevi çağırın.

```
virtual void SetDefaultTitle(CDocument* pDocument) = 0;
```

### <a name="parameters"></a>Parametreler

*pDocument*<br/>
Başlığı ayarlanacak belgeye yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan başlık hakkında daha fazla bilgi için [CDocTemplate:: GetDocString](#getdocstring)içindeki `CDocTemplate::docName` açıklamasına bakın.

##  <a name="setserverinfo"></a>CDocTemplate:: SetServerInfo

Sunucu belgesi katıştırılmış veya yerinde düzenlendiğinde kaynakları ve sınıfları belirler.

```
void SetServerInfo(
    UINT nIDOleEmbedding,
    UINT nIDOleInPlaceServer = 0,
    CRuntimeClass* pOleFrameClass = NULL,
    CRuntimeClass* pOleViewClass = NULL);
```

### <a name="parameters"></a>Parametreler

*Nidolet katıştırma*<br/>
Katıştırılmış bir nesne ayrı bir pencerede açıldığında kullanılan kaynakların KIMLIĞI.

*Nidokaınplaceserver*<br/>
Yerleşik bir nesne yerinde etkinleştirildiğinde kullanılan kaynakların KIMLIĞI.

*Potaframeclass*<br/>
Yerinde etkinleştirme gerçekleştiğinde oluşturulan çerçeve penceresi nesnesi için sınıf bilgilerini içeren bir [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına yönelik işaretçi.

*Potaviewclass*<br/>
Yerinde etkinleştirme gerçekleştiğinde oluşturulan görünüm nesnesi için sınıf bilgilerini içeren `CRuntimeClass` yapısına yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Kullanıcı katıştırılmış bir nesnenin etkinleştirmesini istediğinde sunucu uygulaması tarafından kullanılacak kaynakları belirlemek için bu üye işlevini çağırın. Bu kaynaklar menüler ve Hızlandırıcı tablolarından oluşur. Bu işlev genellikle uygulamanızın `InitInstance` çağırılır.

*Nidotainplaceserver* ile ilişkili menü, sunucu menüsünün kapsayıcının menüsüyle birleştirilmesine izin veren ayırıcılar içerir. Sunucu ve kapsayıcı menülerini birleştirme hakkında daha fazla bilgi için bkz. [menüler ve kaynaklar (OLE)](../../mfc/menus-and-resources-ole.md).

##  <a name="createpreviewframe"></a>CDocTemplate:: Createönizleme çerçevesi

Zengin Önizleme için kullanılan bir alt çerçeve oluşturur.

```
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,
    CDocument* pDoc);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Üst pencere (genellikle kabuk tarafından sağlanmış) işaretçisi.

*pDoc*<br/>
İçerik önizlemesi görüntülenecek bir belge nesnesi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

`CFrameWnd` nesnesine yönelik geçerli bir işaretçi veya oluşturma başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

##  <a name="setpreviewinfo"></a>CDocTemplate:: Setpreviewınınfo

İşlem dışı önizleme işleyicisini ayarlar.

```
void SetPreviewInfo(
    UINT nIDPreviewFrame,
    CRuntimeClass* pPreviewFrameClass = NULL,
    CRuntimeClass* pPreviewViewClass = NULL);
```

### <a name="parameters"></a>Parametreler

*Nıdönizleme çerçevesi*<br/>
Önizleme çerçevesinin kaynak KIMLIĞINI belirtir.

*Pönizleme Frameclass*<br/>
Önizleme çerçevesinin çalışma zamanı sınıfı bilgi yapısına yönelik bir işaretçi belirtir.

*Pönizleme Viewclass*<br/>
Önizleme görünümünün çalışma zamanı sınıfı bilgi yapısına yönelik bir işaretçi belirtir.

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
