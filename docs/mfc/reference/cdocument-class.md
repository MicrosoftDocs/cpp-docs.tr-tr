---
title: CDocument sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDocument
- AFXWIN/CDocument
- AFXWIN/CDocument::CDocument
- AFXWIN/CDocument::AddView
- AFXWIN/CDocument::BeginReadChunks
- AFXWIN/CDocument::CanCloseFrame
- AFXWIN/CDocument::ClearChunkList
- AFXWIN/CDocument::ClearPathName
- AFXWIN/CDocument::DeleteContents
- AFXWIN/CDocument::FindChunk
- AFXWIN/CDocument::GetAdapter
- AFXWIN/CDocument::GetDocTemplate
- AFXWIN/CDocument::GetFile
- AFXWIN/CDocument::GetFirstViewPosition
- AFXWIN/CDocument::GetNextView
- AFXWIN/CDocument::GetPathName
- AFXWIN/CDocument::GetThumbnail
- AFXWIN/CDocument::GetTitle
- AFXWIN/CDocument::InitializeSearchContent
- AFXWIN/CDocument::IsModified
- AFXWIN/CDocument::IsSearchAndOrganizeHandler
- AFXWIN/CDocument::LoadDocumentFromStream
- AFXWIN/CDocument::OnBeforeRichPreviewFontChanged
- AFXWIN/CDocument::OnChangedViewList
- AFXWIN/CDocument::OnCloseDocument
- AFXWIN/CDocument::OnCreatePreviewFrame
- AFXWIN/CDocument::OnDocumentEvent
- AFXWIN/CDocument::OnDrawThumbnail
- AFXWIN/CDocument::OnLoadDocumentFromStream
- AFXWIN/CDocument::OnNewDocument
- AFXWIN/CDocument::OnOpenDocument
- AFXWIN/CDocument::OnPreviewHandlerQueryFocus
- AFXWIN/CDocument::OnPreviewHandlerTranslateAccelerator
- AFXWIN/CDocument::OnRichPreviewBackColorChanged
- AFXWIN/CDocument::OnRichPreviewFontChanged
- AFXWIN/CDocument::OnRichPreviewSiteChanged
- AFXWIN/CDocument::OnRichPreviewTextColorChanged
- AFXWIN/CDocument::OnSaveDocument
- AFXWIN/CDocument::OnUnloadHandler
- AFXWIN/CDocument::PreCloseFrame
- AFXWIN/CDocument::ReadNextChunkValue
- AFXWIN/CDocument::ReleaseFile
- AFXWIN/CDocument::RemoveChunk
- AFXWIN/CDocument::RemoveView
- AFXWIN/CDocument::ReportSaveLoadException
- AFXWIN/CDocument::SaveModified
- AFXWIN/CDocument::SetChunkValue
- AFXWIN/CDocument::SetModifiedFlag
- AFXWIN/CDocument::SetPathName
- AFXWIN/CDocument::SetTitle
- AFXWIN/CDocument::UpdateAllViews
- AFXWIN/CDocument::OnFileSendMail
- AFXWIN/CDocument::OnUpdateFileSendMail
- AFXWIN/CDocument::m_bGetThumbnailMode
- AFXWIN/CDocument::m_bPreviewHandlerMode
- AFXWIN/CDocument::m_bSearchMode
- AFXWIN/CDocument::m_clrRichPreviewBackColor
- AFXWIN/CDocument::m_clrRichPreviewTextColor
- AFXWIN/CDocument::m_lfRichPreviewFont
helpviewer_keywords:
- CDocument [MFC], CDocument
- CDocument [MFC], AddView
- CDocument [MFC], BeginReadChunks
- CDocument [MFC], CanCloseFrame
- CDocument [MFC], ClearChunkList
- CDocument [MFC], ClearPathName
- CDocument [MFC], DeleteContents
- CDocument [MFC], FindChunk
- CDocument [MFC], GetAdapter
- CDocument [MFC], GetDocTemplate
- CDocument [MFC], GetFile
- CDocument [MFC], GetFirstViewPosition
- CDocument [MFC], GetNextView
- CDocument [MFC], GetPathName
- CDocument [MFC], GetThumbnail
- CDocument [MFC], GetTitle
- CDocument [MFC], InitializeSearchContent
- CDocument [MFC], IsModified
- CDocument [MFC], IsSearchAndOrganizeHandler
- CDocument [MFC], LoadDocumentFromStream
- CDocument [MFC], OnBeforeRichPreviewFontChanged
- CDocument [MFC], OnChangedViewList
- CDocument [MFC], OnCloseDocument
- CDocument [MFC], OnCreatePreviewFrame
- CDocument [MFC], OnDocumentEvent
- CDocument [MFC], OnDrawThumbnail
- CDocument [MFC], OnLoadDocumentFromStream
- CDocument [MFC], OnNewDocument
- CDocument [MFC], OnOpenDocument
- CDocument [MFC], OnPreviewHandlerQueryFocus
- CDocument [MFC], OnPreviewHandlerTranslateAccelerator
- CDocument [MFC], OnRichPreviewBackColorChanged
- CDocument [MFC], OnRichPreviewFontChanged
- CDocument [MFC], OnRichPreviewSiteChanged
- CDocument [MFC], OnRichPreviewTextColorChanged
- CDocument [MFC], OnSaveDocument
- CDocument [MFC], OnUnloadHandler
- CDocument [MFC], PreCloseFrame
- CDocument [MFC], ReadNextChunkValue
- CDocument [MFC], ReleaseFile
- CDocument [MFC], RemoveChunk
- CDocument [MFC], RemoveView
- CDocument [MFC], ReportSaveLoadException
- CDocument [MFC], SaveModified
- CDocument [MFC], SetChunkValue
- CDocument [MFC], SetModifiedFlag
- CDocument [MFC], SetPathName
- CDocument [MFC], SetTitle
- CDocument [MFC], UpdateAllViews
- CDocument [MFC], OnFileSendMail
- CDocument [MFC], OnUpdateFileSendMail
- CDocument [MFC], m_bGetThumbnailMode
- CDocument [MFC], m_bPreviewHandlerMode
- CDocument [MFC], m_bSearchMode
- CDocument [MFC], m_clrRichPreviewBackColor
- CDocument [MFC], m_clrRichPreviewTextColor
- CDocument [MFC], m_lfRichPreviewFont
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
ms.openlocfilehash: 2d87ff67000fb5b70c0a5c965638875e6f50b22c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164129"
---
# <a name="cdocument-class"></a>CDocument sınıfı

Kullanıcı tanımlı belge sınıfları için temel işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CDocument : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDocument::CDocument](#cdocument)|Oluşturur bir `CDocument` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDocument::AddView](#addview)|Bir görünüm belgeye ekler.|
|[CDocument::BeginReadChunks](#beginreadchunks)|Başlatır okuma öbek.|
|[CDocument::CanCloseFrame](#cancloseframe)|Geçersiz kılınabilir Gelişmiş; Bu belge görüntüleme bir çerçeve penceresi kapatmadan önce çağrılır.|
|[CDocument::ClearChunkList](#clearchunklist)|Öbek listesini temizler.|
|[CDocument::ClearPathName](#clearpathname)|Belge nesnesi yolunu temizler.|
|[CDocument::DeleteContents](#deletecontents)|Belgenin temizleme işlemini gerçekleştirmek için çağrılır.|
|[CDocument::FindChunk](#findchunk)|Belirtilen GUID'e sahip bir öbek arar.|
|[CDocument::GetAdapter](#getadapter)|Nesneyi uygulama için bir işaretçi döndürür `IDocument` arabirimi.|
|[CDocument::GetDocTemplate](#getdoctemplate)|Belge türünü açıklayan belge şablonu için bir işaretçi döndürür.|
|[CDocument::GetFile](#getfile)|İstenen bir işaretçi döndürür `CFile` nesne.|
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|İlk konumunu döndürür; görünümler listesinden Yineleme başlatmak için kullanılır.|
|[CDocument::GetNextView](#getnextview)|Belgeyle ilişkili görünüm listesi üzerinden yinelenir.|
|[CDocument::GetPathName](#getpathname)|Belgenin veri dosyasının yolunu döndürür.|
|[CDocument::GetThumbnail](#getthumbnail)|Küçük resim görüntülemek için küçük bir sağlayıcı tarafından kullanılacak bir bit eşlem oluşturmak üzere çağrılır.|
|[CDocument::GetTitle](#gettitle)|Belgenin başlığını döndürür.|
|[CDocument::InitializeSearchContent](#initializesearchcontent)|Arama işleyicisi için arama içeriğini başlatmak üzere çağrılır.|
|[CDocument::IsModified](#ismodified)|Belgenin son kez kaydedildiğinden beri değiştirilmiş olup olmadığını gösterir.|
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|Belirtir olup olmadığını, bu örneği `CDocument` nesne için arama ve düzenleme işleyicisi oluşturuldu.|
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|Akıştan belge verileri yüklemek için çağrılır.|
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|Zengin Önizleme yazı tipi değiştirilmeden önce çağrılır.|
|[CDocument::OnChangedViewList](#onchangedviewlist)|Bir görünüm eklendiğinde veya bir belgeden kaldırılması sonra çağrılır.|
|[CDocument::OnCloseDocument](#onclosedocument)|Belge kapatmak için çağrılır.|
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|Bir önizleme çerçeve Zengin Önizleme için oluşturun gerektiğinde framework tarafından çağırılır.|
|[CDocument::OnDocumentEvent](#ondocumentevent)|Bir belge olaya yanıt olarak framework tarafından çağırılır.|
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|Türetilen bir sınıfta küçük resim içeriğini çizmek için bu yöntemi yok sayın.|
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|Akıştan belge verileri yüklemek gerektiğinde framework tarafından çağırılır.|
|[CDocument::OnNewDocument](#onnewdocument)|Yeni bir belge oluşturmak üzere çağrılır.|
|[CDocument::OnOpenDocument](#onopendocument)|Var olan bir belgeyi açmak için çağrılır.|
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|HWND tıklatma işlevini çağırma döndürülecek işleyicisinin yönlendirir.|
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|İleti pompası işleyicisinin çalıştığı işlemin aktarılabilir bir tuş vuruşu işlemek için Önizleme işleyicisi yönlendirir.|
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|Zengin ön izleme arka plan rengi değiştiğinde çağrılır.|
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|Zengin Önizleme yazı tipini değiştirdiği zaman çağrılır.|
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|Zengin Önizleme site değiştiğinde çağırılır.|
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|Zengin Önizleme metin rengi değiştiğinde çağırılır.|
|[CDocument::OnSaveDocument](#onsavedocument)|Belgeyi diske kaydetmek için çağrılır.|
|[CDocument::OnUnloadHandler](#onunloadhandler)|Önizleme işleyicisi kaldırılıyorken framework tarafından çağırılır.|
|[CDocument::PreCloseFrame](#precloseframe)|Çerçeve penceresi kapatılmadan hemen önce çağrılır.|
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|Sonraki öbek değerini okur.|
|[CDocument::ReleaseFile](#releasefile)|Diğer uygulamalar tarafından kullanım için kullanılabilir hale getirmek için bir dosya serbest bırakır.|
|[CDocument::RemoveChunk](#removechunk)|Belirtilen GUID'e sahip bir öbek kaldırır.|
|[CDocument::RemoveView](#removeview)|Belgeden bir görünüm ayırır.|
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|Geçersiz kılınabilir Gelişmiş; açık ya da bir özel durum nedeniyle işlemi tamamlanamadı.|
|[CDocument::SaveModified](#savemodified)|Geçersiz kılınabilir Gelişmiş; belgenin kaydedilip kullanıcıdan için çağrılır.|
|[CDocument::SetChunkValue](#setchunkvalue)|Öbek değerini ayarlar.|
|[CDocument::SetModifiedFlag](#setmodifiedflag)|Son kez kaydedildiğinden beri belge değiştirilmiş belirten bir bayrak ayarlar.|
|[CDocument::SetPathName](#setpathname)|Belge tarafından kullanılan veri dosyasının yolunu ayarlar.|
|[CDocument::SetTitle](#settitle)|Belgenin başlığını ayarlar.|
|[CDocument::UpdateAllViews](#updateallviews)|Belge tüm görünümlere değiştirilmiş bildirir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDocument::OnFileSendMail](#onfilesendmail)|Belge iliştirilmiş bir posta iletisi gönderir.|
|[CDocument::OnUpdateFileSendMail](#onupdatefilesendmail)|Posta Gönder komutu varsa posta desteği sağlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|Belirten `CDocument` nesne küçük resimleri için dllhost tarafından oluşturuldu. İade edilmelidir `CView::OnDraw`.|
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|Belirten `CDocument` nesne için prevhost tarafından oluşturuldu `Rich Preview`. İade edilmelidir `CView::OnDraw`.|
|[CDocument::m_bSearchMode](#m_bsearchmode)|Belirten `CDocument` nesne, dizin oluşturucu veya başka bir arama uygulaması tarafından oluşturuldu.|
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Zengin Önizleme penceresi arka plan rengini belirtir. Bu renk, ana bilgisayar tarafından ayarlanır.|
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Zengin Önizleme penceresini ön plan rengini belirtir. Bu renk, ana bilgisayar tarafından ayarlanır.|
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|Zengin Önizleme penceresini metin yazı tipini belirtir. Bu yazı tipi bilgileri, ana bilgisayar tarafından ayarlanır.|

## <a name="remarks"></a>Açıklamalar

Bir belge, kullanıcı genellikle Dosya Aç komutu ile açılır ve dosyayı kaydedin komutuyla kaydeden veri birimini temsil eder.

`CDocument` Belge oluşturma, bu yükleme ve kaydetme gibi standart işlemlerini destekler. Framework tarafından tanımlanan arabirimi kullanarak belgeleri yöneten `CDocument`.

Bir uygulamanın birden fazla belge türünü destekler; Örneğin, bir uygulama, elektronik tablolar hem metin belgeleri destekleyebilir. Her tür belgeyi bir ilişkili belge şablonu; yine de sahip istiyor musunuz? Belge türü için hangi kaynaklara (örneğin, menü, simge ya da Hızlandırıcı tablo) kullanılan belge şablonunu belirtir. Her belge için ilişkili bir işaretçi içeren `CDocTemplate` nesne.

Kullanıcılar, bir belge içinde etkileşimde [CView](../../mfc/reference/cview-class.md) ilişkili nesne. Belge çerçeve penceresi içinde bir görüntüsünü işler ve belge işlemleri olarak kullanıcı girişini yorumlama görünümü. Bir belge, kendisiyle ilişkili birden çok görünüm olabilir. Bir belge penceresinde kullanıcı oturum açtığında, framework bir görünüm oluşturur ve belgeye ekler. Ne tür bir görünüm ve çerçeve penceresi, her tür belgeyi görüntülemek için kullanılır, belge şablonunu belirtir.

Belgeler, framework'ün standart bir parçası olan komut Yönlendirme ve sonuç olarak standart kullanıcı arabirimi bileşenleri (örneğin, dosyayı kaydetmek menü öğesi) komutları alacak. Bir belge komutları tarafından etkin görünüme iletilen alır. Belgenin belirtilen komut işlemezse yönettiği belge şablonu komutu iletir.

Bir belgenin verilerinin değiştirildiğinde görünümlerinin her söz konusu değişiklikler yansıtmalıdır. `CDocument` sağlar [UpdateAllViews](#updateallviews) görünümleri kendilerini gerektiği şekilde repaint, böylece bu tür değişiklikleri görünümlerini bildirmek, üye işlevi. Framework, aynı zamanda değiştirilmiş bir dosyayı kapatmadan önce kaydetmek için kullanıcıya sorar.

Tipik bir uygulamada belgeleri uygulamak için aşağıdakileri yapmanız gerekir:

- Öğesinden bir sınıf türetin `CDocument` her tür belgeyi için.

- Her belgenin verilerini depolamak için üye değişkenleri ekleyin.

- Belgenin verilerini değiştirme ve okuma için üye işlevleri uygulayın. Belgenin görünümler bu üye işlevleri en önemli kullanıcılarıdır.

- Geçersiz kılma [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) belgenin verilerini ve diskten okunup yazılacağını belge sınıfınızdaki üye işlevi.

`CDocument` e-posta desteği (MAPI) varsa, belgenizi e-posta yoluyla göndermeyi destekler. Makalelerine bakın [MAPI](../../mfc/mapi.md) ve [MFC'de MAPI desteği](../../mfc/mapi-support-in-mfc.md).

Daha fazla bilgi için `CDocument`, bkz: [serileştirme](../../mfc/serialization-in-mfc.md), [belge/görünüm mimarisi konuları](../../mfc/document-view-architecture.md), ve [belge/görünüm oluşturma](../../mfc/document-view-creation.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocument`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="addview"></a>  CDocument::AddView

Belgeye bir görünüm eklemek için bu işlevi çağırın.

```
void AddView(CView* pView);
```

### <a name="parameters"></a>Parametreler

*pView*<br/>
Eklenen görünüm işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlev belirtilen görünümü belgeyle ilişkili görünümler listesine ekler; işlev, bu belgeye ayrıca görünümün belge işaretçisi ayarlar. Framework, yeni oluşturulan view nesnesinin bir belgeye eklenirken bu işlevi çağırır; Bu yeni dosya, dosya açık veya yeni bir pencere bir komutu veya bir ayırıcı penceresi böldüğünüzde yanıtta oluşur.

Yalnızca el ile oluşturuyor ve bir görünüm ekleme, bu işlevi çağırın. Genellikle belgeler ve görünümler tanımlayarak bağlanmak framework olanak tanıyan bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) belge sınıfı, görünüm sınıfı ve pencere sınıfını ilişkilendirilecek bir nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]

##  <a name="beginreadchunks"></a>  CDocument::BeginReadChunks

Başlatır okuma öbek.

```
virtual void BeginReadChunks ();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="cancloseframe"></a>  CDocument::CanCloseFrame

Belgeyi görüntüleyen bir çerçeve pencere kapatılmadan hemen önce framework tarafından çağırılır.

```
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Parametreler

*pFrame*<br/>
Çerçeve penceresi işaret belgeye eklenen görünüm.

### <a name="return-value"></a>Dönüş Değeri

Çerçeve penceresini kapatmak güvenlidir olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, belge görüntüleme diğer çerçeve pencereleri olup olmadığını denetler. Belirtilen çerçeve penceresi belgeyi görüntüler sonuncu ise, işlev değiştirildi belgeyi tasarruf etmek kullanıcıya sorar. Çerçeve penceresi kapatıldığında özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar. Bu gelişmiş bir, geçersiz kılınabilir.

##  <a name="cdocument"></a>  CDocument::CDocument

Oluşturur bir `CDocument` nesne.

```
CDocument();
```

### <a name="remarks"></a>Açıklamalar

Framework belge oluşturma sizin için işler. Geçersiz kılma [OnNewDocument](#onnewdocument) üye işlevi bir belge başına temelinde; başlatma gerçekleştirmek için bu tek Belgeli Arabirim (SDI) uygulamalarda özellikle önemlidir.

##  <a name="clearchunklist"></a>  CDocument::ClearChunkList

Öbek listesini temizler.

```
virtual void ClearChunkList ();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="clearpathname"></a>  CDocument::ClearPathName

Belge nesnesi yolunu temizler.

```
virtual void ClearPathName();
```

### <a name="remarks"></a>Açıklamalar

Yolundan temizleyerek bir `CDocument` nesne belge sonraki kaydedildiğinde kullanıcıdan uygulamaya neden olur. Böylece bir **Kaydet** komut davranır gibi bir **Kaydet** komutu.

##  <a name="deletecontents"></a>  CDocument::DeleteContents

Zarar vermeden belgenin verilerini silmek için framework tarafından çağırılır `CDocument` nesnenin kendisi.

```
virtual void DeleteContents();
```

### <a name="remarks"></a>Açıklamalar

Yalnızca belge yok edilecek önce çağrılır. Ayrıca, yeniden kullanılmadan önce bir belge boş olduğundan emin olmak için çağrılır. Bu yalnızca bir belge kullanan bir SDI uygulaması için özellikle önemlidir; Her bir kullanıcı oluşturur veya başka bir belge açılır, belgeyi yeniden kullanılır. Bir "Düzenleme Tümünü Temizle" veya tüm belgenin verilerini siler benzer komutu uygulamak için bu işlevi çağırın. Bu işlevin varsayılan uygulama, hiçbir şey yapmaz. Belgenizde verileri silmek için bu işlevi geçersiz kılar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]

##  <a name="findchunk"></a>  CDocument::FindChunk

Belirtilen GUID'e sahip bir öbek arar.

```
virtual POSITION FindChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Parametreler

*GUID*<br/>
Bulunacak bir öbeğin GUID belirtir.

*PID*<br/>
Bulmak için bir PID bir öbeğin belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa iç öbek listenin konumu. Bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

##  <a name="getadapter"></a>  CDocument::GetAdapter

Bir nesneyi uygulama için bir işaretçi döndürür `IDocument` arabirimi.

```
virtual ATL::IDocument* GetAdapter();
```

### <a name="return-value"></a>Dönüş Değeri

Bir nesneyi uygulama için bir işaretçi `IDocument` arabirimi.

### <a name="remarks"></a>Açıklamalar

##  <a name="getdoctemplate"></a>  CDocument::GetDocTemplate

Bir işaretçi, bu belge türü için belge şablonuna almak için bu işlevi çağırın.

```
CDocTemplate* GetDocTemplate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belge şablonu bu belge türü veya belge bir belge şablonu tarafından yönetilmiyorsa NULL bir işaretçi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]

##  <a name="getfile"></a>  CDocument::GetFile

Bir işaretçi almak için bu üye işlevi çağrısı bir `CFile` nesne.

```
virtual CFile* GetFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
İstenen dosya yolu bir dize. Göreli veya mutlak yol olabilir.

*pError*<br/>
Var olan bir dosya özel durumu nesneye işleminin tamamlanma durumunu gösteren bir işaretçi.

*nOpenFlags*<br/>
Paylaşım ve erişim modu. Dosyayı açarken gerçekleştirilecek eylemi belirtir. CFile oluşturucuda listelenen seçenekler birleştirebilirsiniz [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) bit düzeyinde OR kullanarak (&#124;) işleci. Bir erişim izni ve bir paylaşım seçeneği gereklidir; `modeCreate` ve `modeNoInherit` modlarıdır isteğe bağlı.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CFile` nesne.

##  <a name="getfirstviewposition"></a>  CDocument::GetFirstViewPosition

Listesinde görünümleri belgeyle ilişkili ilk görünüm konumunu almak için bu işlevi çağırın.

```
virtual POSITION GetFirstViewPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme ile için kullanılabilecek bir konum değeri [GetNextView](#getnextview) üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="getnextview"></a>  CDocument::GetNextView

Tüm belge görünümleri yineleme yapmak için bu işlevi çağırın.

```
virtual CView* GetNextView(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*rPosition*<br/>
KONUM değeri başvurusu döndürülen önceki bir çağrı tarafından `GetNextView` veya [GetFirstViewPosition](#getfirstviewposition) üye işlevleri. Bu değer NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi tarafından tanımlanan Görünüm *rPosition*.

### <a name="remarks"></a>Açıklamalar

İşlev tarafından tanımlanan görünüm döndürür *rPosition* ve ardından ayarlar *rPosition* için listedeki sonraki görünüme konum değeri. Alınan görünümü son listede, ardından olup olmadığını *rPosition* NULL olarak ayarlandı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="getpathname"></a>  CDocument::GetPathName

Belgenin disk dosyasının tam yolunu almak için bu işlevi çağırın.

```
const CString& GetPathName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin tam yolu. Belge kaydedilmedi veya ilişkili bir disk dosyası yok. Bu boş bir dizedir.

##  <a name="getthumbnail"></a>  CDocument::GetThumbnail

Küçük resim görüntülemek için küçük resim sağlayıcısı tarafından kullanılacak bir bit eşlem oluşturur.

```
virtual BOOL GetThumbnail(
    UINT cx,
    HBITMAP* phbmp,
    DWORD* pdwAlpha);
```

### <a name="parameters"></a>Parametreler

*cx*<br/>
Bit eşlem yüksekliğini ve genişliğini belirtir.

*phbmp*<br/>
İşlev başarıyla geri döndüğünde bir tanıtıcı bir bit eşlemi içerir.

*pdwAlpha*<br/>
İşlev başarıyla geri döndüğünde alfa kanalı değerini belirten bir DWORD içerir.

### <a name="return-value"></a>Dönüş Değeri

Bir bit eşlem, küçük resim TRUE döndürür başarıyla oluşturulduğunu; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="gettitle"></a>  CDocument::GetTitle

Belgenin dosya genellikle türetildiği belgenin başlığını almak için bu işlevi çağırın.

```
const CString& GetTitle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin başlığı.

##  <a name="initializesearchcontent"></a>  CDocument::InitializeSearchContent

Arama işleyicisi için arama içeriğini başlatmak üzere çağrılır.

```
virtual void InitializeSearchContent ();
```

### <a name="remarks"></a>Açıklamalar

Türetilen bir sınıfta içerik Ara başlatmak için bu yöntemi yok sayın. İçerik parçaları tarafından ayrılmış olan bir dize olmalıdır ";". Örneğin, "işaret; Dikdörtgen; OLE öğesini".

##  <a name="ismodified"></a>  CDocument::IsModified

Belgenin son kez kaydedildiğinden beri değiştirilmiş olup olmadığını belirlemek için bu işlevi çağırın.

```
virtual BOOL IsModified();
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin son kez kaydedildiğinden beri değiştirilmiş olursa sıfır dışı; Aksi durumda 0.

##  <a name="issearchandorganizehandler"></a>  CDocument::IsSearchAndOrganizeHandler

Belirtir olup olmadığını, bu örneği `CDocument` arama & düzenleme işleyicisi için oluşturuldu.

```
BOOL IsSearchAndOrganizeHandler() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu, TRUE döndürür örneğini `CDocument` arama & düzenleme işleyicisi için oluşturuldu.

### <a name="remarks"></a>Açıklamalar

Şu anda bu işlev, yalnızca işlem sunucusunun yetersiz içinde uygulanan Zengin Önizleme işleyicileri için TRUE döndürür. Bu işlev TRUE döndürün yapmak için uygulama düzeyinde uygun bayrakları (m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode) ayarlayabilirsiniz.

##  <a name="loaddocumentfromstream"></a>  CDocument::LoadDocumentFromStream

Bir akıştan belge verileri yüklemek için çağrılır.

```
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,
    DWORD dwGrfMode);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
Bir akış için bir işaretçi. Bu akış, kabuk tarafından sağlanır.

*dwGrfMode*<br/>
Erişim modu akış.

### <a name="return-value"></a>Dönüş Değeri

Yükleme işlemi başarılı olursa, aksi takdirde HRESULT hata koduyla S_OK.

### <a name="remarks"></a>Açıklamalar

Türetilen bir sınıfta akıştan veri yükleme özelleştirmek için bu yöntemi geçersiz kılabilirsiniz.

##  <a name="m_bgetthumbnailmode"></a>  CDocument::m_bGetThumbnailMode

Belirten `CDocument` nesne küçük resimleri için dllhost tarafından oluşturuldu. İade edilmelidir `CView::OnDraw`.

```
BOOL m_bGetThumbnailMode;
```

### <a name="remarks"></a>Açıklamalar

`TRUE` Belge küçük resimleri için dllhost tarafından oluşturulduğunu belirtir.

##  <a name="m_bpreviewhandlermode"></a>  CDocument::m_bPreviewHandlerMode

Belirten `CDocument` nesne tarafından prevhost Zengin Önizleme için oluşturuldu. İade edilmelidir `CView::OnDraw`.

```
BOOL m_bPreviewHandlerMode;
```

### <a name="remarks"></a>Açıklamalar

TRUE, belge Zengin Önizleme için prevhost tarafından oluşturulduğunu gösterir.

##  <a name="m_bsearchmode"></a>  CDocument::m_bSearchMode

Belirten `CDocument` nesne, dizin oluşturucu veya başka bir arama uygulaması tarafından oluşturuldu.

```
BOOL m_bSearchMode;
```

### <a name="remarks"></a>Açıklamalar

`TRUE` Belge, dizin oluşturucu veya başka bir arama uygulaması tarafından oluşturulduğunu belirtir.

##  <a name="m_clrrichpreviewbackcolor"></a>  CDocument::m_clrRichPreviewBackColor

Zengin Önizleme penceresini arka plan rengini belirtir. Bu renk, ana bilgisayar tarafından ayarlanır.

```
COLORREF m_clrRichPreviewBackColor;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_clrrichpreviewtextcolor"></a>  CDocument::m_clrRichPreviewTextColor

Zengin Önizleme penceresini ön plan rengini belirtir. Bu renk, ana bilgisayar tarafından ayarlanır.

```
COLORREF m_clrRichPreviewTextColor;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_lfrichpreviewfont"></a>  CDocument::m_lfRichPreviewFont

Zengin Önizleme penceresini metin yazı tipini belirtir. Bu yazı tipi bilgileri, ana bilgisayar tarafından ayarlanır.

```
CFont m_lfRichPreviewFont;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onbeforerichpreviewfontchanged"></a>  CDocument::OnBeforeRichPreviewFontChanged

Zengin Önizleme yazı tipi değiştirilmeden önce çağrılır.

```
virtual void OnBeforeRichPreviewFontChanged();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onchangedviewlist"></a>  CDocument::OnChangedViewList

Bir görünüm eklendiğinde veya bir belgeden kaldırılması sonra framework tarafından çağırılır.

```
virtual void OnChangedViewList();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını son görünümü kaldırılıyor ve bu durumda, belgenin siler olup olmadığını denetler. Framework ekler veya bir görünüm kaldırdığında özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar. Örneğin, bir belge, Görünüm yok bağlı olduğunda bile açık kalmasına istiyorsanız, bu işlev geçersiz kılar.

##  <a name="onclosedocument"></a>  CDocument::OnCloseDocument

Belge, genellikle Dosya Kapat komutunun bir parçası kapatıldığı zaman framework tarafından çağırılır.

```
virtual void OnCloseDocument();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını tüm belgeyi görüntülemek için kullanılan çerçeve yok eder, görünüm kapatır, belgenin içeriği temizler ve ardından çağırır [DeleteContents](#deletecontents) belgenin silmek için üye işlevi veriler.

Framework bir belge kapatıldığında, özel bir temizleme işlemi işleme gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar. Örneğin, bir veritabanındaki bir kaydı belgeyi temsil ediyorsa, veritabanı kapatmak için bu işlevi geçersiz kılmak isteyebilirsiniz. Geçersiz kılma temel sınıftaki sürümün bu işlevi çağırmanız gerekir.

##  <a name="oncreatepreviewframe"></a>  CDocument::OnCreatePreviewFrame

Bir önizleme çerçeve Zengin Önizleme için oluşturun gerektiğinde framework tarafından çağırılır.

```
virtual BOOL OnCreatePreviewFrame();
```

### <a name="return-value"></a>Dönüş Değeri

Çerçeve başarıyla oluşturulursa TRUE döndürür; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondocumentevent"></a>  CDocument::OnDocumentEvent

Bir belge olaya yanıt olarak framework tarafından çağırılır.

```
virtual void OnDocumentEvent(DocumentEvent deEvent);
```

### <a name="parameters"></a>Parametreler

*deEvent*<br/>
[in] Olayın türünü tanımlayan numaralandırılmış veri türü.

### <a name="remarks"></a>Açıklamalar

Belge olayları birden çok sınıf etkileyebilir. Bu yöntem, sınıf dışındaki etkileyen belge olayları işlenmesinden sorumludur [CDocument sınıfı](../../mfc/reference/cdocument-class.md). Şu anda, belge olaylara yanıt vermesi gereken tek sınıftır [CDataRecoveryHandler sınıfı](../../mfc/reference/cdatarecoveryhandler-class.md). `CDocument` Sınıfında diğer geçersiz kılınabilir yöntemleri üzerinde etkisi işlenmesinden sorumludur `CDocument`.

İçin olası değerler aşağıdaki tabloda *deEvent* ve bunların karşılık gelen olayları.

|Değer|Karşılık gelen bir olay|
|-----------|-------------------------|
|`onAfterNewDocument`|Yeni bir belge oluşturulur.|
|`onAfterOpenDocument`|Yeni bir belge açıldı.|
|`onAfterSaveDocument`|Belge kaydedildi.|
|`onAfterCloseDocument`|Belge kapatıldı.|

##  <a name="ondrawthumbnail"></a>  CDocument::OnDrawThumbnail

Türetilen bir sınıfta küçük çizmek için bu yöntemi yok sayın.

```
virtual void OnDrawThumbnail(
    CDC& dc,
    LPRECT lprcBounds);
```

### <a name="parameters"></a>Parametreler

*DC*<br/>
Bir cihaz bağlamına başvuru.

*lprcBounds*<br/>
Sınırlayıcı bir dikdörtgen alanının nerede küçük çizileceğini belirtir.

### <a name="remarks"></a>Açıklamalar

##  <a name="onfilesendmail"></a>  CDocument::OnFileSendMail

Yerleşik posta ana bilgisayar üzerinden bir ileti ile belge (varsa) ek olarak gönderir.

```
void OnFileSendMail();
```

### <a name="remarks"></a>Açıklamalar

`OnFileSendMail` çağrıları [OnSaveDocument](#onsavedocument) (Kaydet) adsız ve değiştirilen belgeler elektronik posta gönderilmesi geçici bir dosyaya serileştirmek için. Belge değiştirilmemiş, geçici bir dosya gerekli değildir; özgün gönderilir. `OnFileSendMail` MAPI32 yükler. DLL zaten yüklü.

Özel uygulanışı `OnFileSendMail` için [COleDocument](../../mfc/reference/coledocument-class.md) tanıtıcıları bileşik dosyaları doğru.

`CDocument` e-posta desteği (MAPI) varsa, belgenizi e-posta yoluyla göndermeyi destekler. Makalelerine bakın [MAPI konuları](../../mfc/mapi.md) ve [MFC'de MAPI desteği](../../mfc/mapi-support-in-mfc.md).

##  <a name="onloaddocumentfromstream"></a>  CDocument::OnLoadDocumentFromStream

Bir akıştan belge verileri yüklemek gerektiğinde framework tarafından çağırılır.

```
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,
    DWORD grfMode);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
Gelen bir akış için bir işaretçi.

*grfMode*<br/>
Erişim modu akış.

### <a name="return-value"></a>Dönüş Değeri

Yükleme başarılıysa S_OK; Aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

##  <a name="onnewdocument"></a>  CDocument::OnNewDocument

Dosya yeni komutunun bir parçası olarak framework tarafından çağırılır.

```
virtual BOOL OnNewDocument();
```

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla başlatıldı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını çağırır [DeleteContents](#deletecontents) belge boş ve ardından yeni bir belge temiz olarak işaretler emin olmak için üye işlevi. Yeni bir belge için veri yapısı başlatmak için bu işlevi geçersiz kılar. Geçersiz kılma temel sınıftaki sürümün bu işlevi çağırmanız gerekir.

Kullanıcı bir SDI uygulamasında dosya yeni komutunun seçerse, çerçeve yeni bir tane oluşturmak yerine var olan bir belgeyi yeniden başlatmak için bu işlevi kullanır. Kullanıcı dosya yeni bir birden çok belge arabirimi (MDI) uygulamasında seçerse, framework her seferinde yeni bir belge oluşturur ve ardından başlatmak için bu işlevi çağırır. Bu işlevde yerine SDI uygulamaları etkili olması dosya yeni komutunun oluşturucusu başlatma kodlarınızı koymanız gerekir.

Vardır Not durumlara `OnNewDocument` iki kez çağrılır. Bu durum, belgeyi bir ActiveX belge sunucusu olarak katıştırılır oluşur. İşlevin ilk çağıran `CreateInstance` yöntemi (tarafından kullanıma sunulan `COleObjectFactory`-türetilmiş sınıf) ve bir kez `InitNew` yöntemi (tarafından kullanıma sunulan `COleServerDoc`-türetilmiş sınıf).

### <a name="example"></a>Örnek

Aşağıdaki örnekler, bir belge nesnesi başlatılırken alternatif yöntemleri gösterir.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

##  <a name="onopendocument"></a>  CDocument::OnOpenDocument

Dosya Aç komutunun bir parçası olarak framework tarafından çağırılır.

```
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Açılacak belgesinin yolu işaret.

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla yüklendi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını çağrıları belirtilen dosyayı açar [DeleteContents](#deletecontents) belge boş olduğundan emin olmak için üye işlevini çağırır [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) dosya okunamadı içeriği ve sonra belgeyi temiz olarak işaretler. Arşiv mekanizması veya dosya mekanizması dışında bir şey kullanmak istiyorsanız, bu işlev yok sayın. Örneğin, burada ayrı dosyalar yerine bir veritabanı kayıtlarda belgeleri temsil eder bir uygulama yazabilirsiniz.

Kullanıcı bir SDI uygulamasında Dosya Aç komutunun seçerse, çerçeve varolan yeniden başlatmak için bu işlevi kullanır `CDocument` yeni bir tane oluşturmak yerine nesne. Kullanıcı dosya açık bir MDI uygulamasında seçerse, framework yeni bir oluşturur `CDocument` her nesne ve ardından başlatmak için bu işlevi çağırır. Bu işlevde yerine SDI uygulamaları etkili olması Dosya Aç komutunun oluşturucusu başlatma kodlarınızı koymanız gerekir.

### <a name="example"></a>Örnek

Aşağıdaki örnekler, bir belge nesnesi başlatılırken alternatif yöntemleri gösterir.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

[!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]

##  <a name="onpreviewhandlerqueryfocus"></a>  CDocument::OnPreviewHandlerQueryFocus

HWND arama öğesinden alınan döndürülecek işleyicisinin yönlendirir `GetFocus` işlevi.

```
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```

### <a name="parameters"></a>Parametreler

*phwnd*<br/>
[out] Bu yöntem döndürüldüğünde, arama öğesinden döndürülen HWND bir işaretçi içeren `GetFocus` Önizleme işleyicinin ön plan iş parçacığından işlevi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa; başarılıysa S_OK döndürür ya da aksi takdirde bir hata değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="onpreviewhandlertranslateaccelerator"></a>  CDocument::OnPreviewHandlerTranslateAccelerator

İleti pompası işleyicisinin çalıştığı işlemin aktarılabilir bir tuş vuruşu işlemek için Önizleme işleyicisi yönlendirir.

```
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```

### <a name="parameters"></a>Parametreler

*pmsg*<br/>
[in] Bir pencere iletisi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Tuş vuruşu ileti Önizleme işleyici tarafından işlenebilir, işleyici işler ve S_OK döndürür. Önizleme işleyicisi tuş vuruşu iletiyi işleyemezse bu konağa sunduğu `IPreviewHandlerFrame::TranslateAccelerator`. Ana ileti işlediğinde, bu yöntem S_OK döndürür. Bu yöntem, konak ileti işlemezse S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="onrichpreviewbackcolorchanged"></a>  CDocument::OnRichPreviewBackColorChanged

Zengin ön izleme arka plan rengi değiştiğinde çağırılır.

```
virtual void OnRichPreviewBackColorChanged();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onrichpreviewfontchanged"></a>  CDocument::OnRichPreviewFontChanged

Zengin Önizleme yazı tipini değiştirdiği zaman çağrılır.

```
virtual void OnRichPreviewFontChanged();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onrichpreviewsitechanged"></a>  CDocument::OnRichPreviewSiteChanged

Zengin Önizleme site değiştiğinde çağırılır.

```
virtual void OnRichPreviewSiteChanged();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onrichpreviewtextcolorchanged"></a>  CDocument::OnRichPreviewTextColorChanged

Zengin Önizleme metin rengi değiştiğinde çağırılır.

```
virtual void OnRichPreviewTextColorChanged();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onsavedocument"></a>  CDocument::OnSaveDocument

Dosyayı kaydedin veya dosyayı farklı Kaydet komutunun bir parçası olarak framework tarafından çağırılır.

```
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Dosyanın kaydedilmesi gereken tam yolunu işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla kaydedildi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını çağrıları belirtilen dosyayı açar [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) belgenin verilerini yazmak için belgenin dosyasını ve ardından işaretleri temizleyin. Framework bir belgesini kaydettiğinde özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar. Örneğin, burada ayrı dosyalar yerine bir veritabanı kayıtlarda belgeleri temsil eder bir uygulama yazabilirsiniz.

##  <a name="onunloadhandler"></a>  CDocument::OnUnloadHandler

Önizleme işleyicisi kaldırıldığında framework tarafından çağırılır.

```
virtual void OnUnloadHandler();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onupdatefilesendmail"></a>  CDocument::OnUpdateFileSendMail

E-posta desteği (MAPI) varsa ID_FILE_SEND_MAIL komutunu etkinleştirir.

```
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Bir işaretçi [Ccmduı](../../mfc/reference/ccmdui-class.md) ID_FILE_SEND_MAIL komutla ilişkilendirilmiş nesne.

### <a name="remarks"></a>Açıklamalar

Aksi takdirde işlev menüden uygun şekilde menü öğesinin altına veya üstüne ayırıcılar dahil olmak üzere ID_FILE_SEND_MAIL komutu kaldırır. MAPI etkin olup MAPI32. DLL, yolda ve WIN [adres] bölümünde yok. INI dosyası MAPI = 1. Uygulamaların çoğu bu komut, Dosya menüsünden yerleştirin.

`CDocument` e-posta desteği (MAPI) varsa, belgenizi e-posta yoluyla göndermeyi destekler. Makalelerine bakın [MAPI konuları](../../mfc/mapi.md) ve [MFC'de MAPI desteği](../../mfc/mapi-support-in-mfc.md).

##  <a name="precloseframe"></a>  CDocument::PreCloseFrame

Çerçeve penceresi yok önce bu üye işlevi çerçeve tarafından çağrılır.

```
virtual void PreCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Parametreler

*pFrame*<br/>
İşaretçi [CFrameWnd](../../mfc/reference/cframewnd-class.md) ilişkili tutan `CDocument` nesne.

### <a name="remarks"></a>Açıklamalar

Özel temizleme sağlar, ancak temel sınıfı da çağırdığınızdan emin olun kılınabilir.

Varsayılan değer olan `PreCloseFrame` hiçbir şey yapmaz `CDocument`. `CDocument`-Türetilmiş sınıflar [COleDocument](../../mfc/reference/coledocument-class.md) ve [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) bu üye işlevini kullanın.

##  <a name="readnextchunkvalue"></a>  CDocument::ReadNextChunkValue

Sonraki öbek değerini okur.

```
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```

### <a name="parameters"></a>Parametreler

*ppValue*<br/>
[out] İşlevi döndüğünde *ppValue* okundu değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="releasefile"></a>  CDocument::ReleaseFile

Bu üye işlevi, diğer uygulamalar tarafından kullanılabilir hale getirerek, bir dosya serbest bırakmak için framework tarafından çağırılır.

```
virtual void ReleaseFile(
    CFile* pFile,
    BOOL bAbort);
```

### <a name="parameters"></a>Parametreler

*pFile*<br/>
Yayımlanacak CFile nesnesine bir işaretçi.

*bAbort*<br/>
Dosyanın kullanarak yayımlanacak olup olmadığını belirtir `CFile::Close` veya `CFile::Abort`. YANLIŞ dosyası kullanarak serbest bırakılacağı [CFile::Close](../../mfc/reference/cfile-class.md#close); Dosyayı kullanarak yayımlanacak ise TRUE [CFile::Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="remarks"></a>Açıklamalar

Varsa *bAbort* TRUE ise `ReleaseFile` çağrıları `CFile::Abort`, ve dosyayı serbest bırakılır. `CFile::Abort` bir özel durum oluşturması beklenmiyor.

Varsa *bAbort* false değerine `ReleaseFile` çağrıları `CFile::Close` ve dosya serbest bırakılır.

Dosya kullanıma sunulmadan önce bir eylem kullanıcı tarafından zorunlu tutmak için bu üye işlevini geçersiz kılar.

##  <a name="removechunk"></a>  CDocument::RemoveChunk

Belirtilen GUID'e sahip bir öbek kaldırır.

```
virtual void RemoveChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Parametreler

*GUID*<br/>
Kaldırılacak bir öbeğin GUID belirtir.

*PID*<br/>
Kaldırılacak bir öbeğin PID belirtir.

### <a name="remarks"></a>Açıklamalar

##  <a name="removeview"></a>  CDocument::RemoveView

Belgeden bir görünüm ayırmak için bu işlevi çağırın.

```
void RemoveView(CView* pView);
```

### <a name="parameters"></a>Parametreler

*pView*<br/>
Kaldırılmakta olan Görünüm işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlev belirtilen görünümü belgeyle ilişkili görünümler listesinden kaldırır; Ayrıca görünümün belge işaretçisi NULL olarak ayarlar. Bu işlev, bir çerçeve penceresi kapatıldığında veya bir bölme ayırıcı penceresi kapatıldığında çerçeve tarafından çağrılır.

Yalnızca el ile bir görünüm ayırma, bu işlevi çağırın. Genellikle, belgeler ve görünümler tanımlayarak ayırma framework olanak tanıyacak bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) belge sınıfı, görünüm sınıfı ve pencere sınıfını ilişkilendirilecek bir nesne.

Örneğe bakın [AddView](#addview) örnek uygulama için.

##  <a name="reportsaveloadexception"></a>  CDocument::ReportSaveLoadException

Bir özel durum oluşursa çağrılır (genellikle bir [CFileException](../../mfc/reference/cfileexception-class.md) veya [CArchiveException](../../mfc/reference/carchiveexception-class.md)) kaydetme veya belge yükleniyor.

```
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,
    CException* e,
    BOOL bSaving,
    UINT nIDPDefault);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Çalıştırılmakta olan belgenin adına işaret kaydedildi veya yüklendi.

*e*<br/>
Oluşturulan özel durumun işaret eder. NULL olabilir.

*bSaving*<br/>
Hangi işlem devam ediyordu belirten bayrak; Belge değiştirilirken olursa sıfır dışı kaydettiyseniz, 0 belge yüklendi.

*nIDPDefault*<br/>
İşlev daha belirli bir belirtmezse görüntülenecek hata iletisi tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, özel durum nesnesini inceler ve özellikle nedenini açıklayan bir hata iletisi görünür. Belirli bir ileti bulunamazsa veya *e* null, belirtilen genel bir ileti *nIDPDefault* parametresi kullanılır. İşlevi, ardından hata iletisini içeren bir ileti kutusu görüntüler. Özelleştirilmiş, ek hata iletileri sağlamak istiyorsanız, bu işlev geçersiz kılar. Bu gelişmiş bir, geçersiz kılınabilir.

##  <a name="savemodified"></a>  CDocument::SaveModified

Değiştirilmiş belge kapatılmadan önce framework tarafından çağırılır.

```
virtual BOOL SaveModified();
```

### <a name="return-value"></a>Dönüş Değeri

Devam etmek ve belgeyi Kapat güvenlidir olursa sıfır dışı; 0 Belge kapatılamıyor.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını herhangi yapılmadıysa kullanıcı belgesine, değişikliklerin kaydedilip edilmeyeceğini soran bir ileti kutusu görüntüler. Farklı bir kullanıcıdan yordam programınızı gerektiriyorsa, bu işlev geçersiz kılar. Bu gelişmiş bir, geçersiz kılınabilir.

##  <a name="setchunkvalue"></a>  CDocument::SetChunkValue

Öbek değerini ayarlar.

```
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Parametreler

*pValue*<br/>
Ayarlanacak bir öbek değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="setmodifiedflag"></a>  CDocument::SetModifiedFlag

Belge herhangi bir değişiklik yaptıktan sonra bu işlevi çağırın.

```
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Parametreler

*bModified*<br/>
Belge değiştirilmiş olup olmadığını belirten bayrak.

### <a name="remarks"></a>Açıklamalar

Bu işlev tutarlı bir şekilde çağrılarak framework belge kapatılmadan önce değişiklikleri kaydetmek için kullanıcı komut istemleri emin olun. Varsayılan değer olan TRUE kullanmalısınız *bModified* parametresi. Temiz bir belge (değiştirilmemiş) işaretlemek için FALSE değerini bu işlevi çağırın.

##  <a name="setpathname"></a>  CDocument::SetPathName

Belgenin disk dosyasının tam yolunu belirtmek için bu işlevi çağırın.

```
virtual void SetPathName(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Belge yolu olarak kullanılacak dize işaret eder.

*bAddToMRU*<br/>
Dosya adı için eklenip en son (MRU) dosya listesi kullanılan belirler. TRUE ise dosya adı eklenir; FALSE ise eklenmez.

### <a name="remarks"></a>Açıklamalar

Değerine bağlı olarak *bAddToMRU* yol eklendiğinde veya, uygulama tarafından korunan MRU listesine eklenmedi. Bazı belgeler bir disk dosyası ile ilişkili olmadığına dikkat edin. Yalnızca varsayılan uygulama için framework tarafından kullanılan dosyaları açma ve kaydetme kılıyorsa, bu işlevi çağırın.

##  <a name="settitle"></a>  CDocument::SetTitle

Belgenin başlığını (bir çerçeve penceresinin başlık çubuğunda görüntülenen dizeyi) belirtmek için bu işlevi çağırın.

```
virtual void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Parametreler

*lpszTitle*<br/>
Belgenin başlığı olarak kullanılacak dize işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu fonksiyonu çağıran belgeyi gösteren tüm çerçeve pencereleri başlıklarını güncelleştirir.

##  <a name="updateallviews"></a>  CDocument::UpdateAllViews

Belge değiştirildikten sonra bu işlevi çağırın.

```
void UpdateAllViews(
    CView* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL);
```

### <a name="parameters"></a>Parametreler

*pSender*<br/>
Dokument görünümüne işaret eden veya tüm görünümlerin güncelleştirilmesi gerekmeyen yoksa NULL.

*lHint*<br/>
Değiştirme hakkında bilgi içerir.

*pHint*<br/>
Değiştirme hakkında bilgi depolamak için bir nesneye işaret eder.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra bu işlevi çağırmanız gerekir [SetModifiedFlag](#setmodifiedflag) üye işlevi. Bu işlev tarafından belirtilen görünüm dışında belgeye ekli her görünüm bildirir *pSender*, belge değiştirilmiş. Kullanıcı bir görünüm aracılığıyla belge değiştirildikten sonra Görünüm sınıftan genellikle bu işlevi çağırın.

Bu işlev çağrıları [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) üye işlevi her gönderme dışında belgenin görünümlerini görüntülemek, geçirme *pHint* ve *lHint*. Görünümlere belgeye yapılan değişiklikler hakkında bilgi geçirmek için şu parametreleri kullan. Bilgi'ı kullanarak kodlama *lHint* ve/veya tanımlayabileceğiniz bir [CObject](../../mfc/reference/cobject-class.md)-türetilmiş sınıf değişiklikler hakkında bilgi depolayabilir ve bu sınıfı kullanmanın bir nesne için *pHint*. Geçersiz kılma `CView::OnUpdate` üye işlevinde, [CView](../../mfc/reference/cview-class.md)-türetilmiş sınıf geçirilen bilgilere göre görünümün görüntüleme güncelleştirme en iyi duruma getirme.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek NPP](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)
