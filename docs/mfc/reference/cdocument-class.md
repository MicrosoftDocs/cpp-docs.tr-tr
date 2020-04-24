---
title: Kişniş Sınıfı
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
ms.openlocfilehash: d356ba6b6134221c2fc9595fc6d78f91961c5b7f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753251"
---
# <a name="cdocument-class"></a>Kişniş Sınıfı

Kullanıcı tanımlı belge sınıfları için temel işlevselliği sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CDocument : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Kbelge::Kdocument](#cdocument)|Bir `CDocument` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDocument::AddView](#addview)|Belgeye bir görünüm bağlar.|
|[KDocument::BeginReadChunks](#beginreadchunks)|Yığın okumayı başharfe iter.|
|[Kdocument::CanCloseFrame](#cancloseframe)|Gelişmiş overridable; bu belgeyi görüntüleyen bir çerçeve pencereyi kapatmadan önce çağrılır.|
|[Kdocument::ClearChunklist](#clearchunklist)|Yığın listesini temizler.|
|[Kdocument::ClearPathName](#clearpathname)|Belge nesnesinin yolunu temizler.|
|[KKK::DeleteContents](#deletecontents)|Belgenin temizlenmesini gerçekleştirmek için çağrıldı.|
|[Kdocument::FindChunk](#findchunk)|Belirtilen GUID ile bir yığın arar.|
|[KKK:GetAdapter](#getadapter)|Nesne uygulama `IDocument` arabirimi için bir işaretçi döndürür.|
|[Kdocument::GetDocTemplate](#getdoctemplate)|Belge türünü açıklayan belge şablonuna bir işaretçi döndürür.|
|[Kdocument::GetFile](#getfile)|İstenilen `CFile` nesneye bir işaretçi döndürür.|
|[Kdocument::GetFirstViewPosition](#getfirstviewposition)|Görünümler listesindeki ilk konumu verir; yinelemeye başlamak için kullanılır.|
|[Kdocument::GetNextView](#getnextview)|Belgeyle ilişkili görünümler listesi aracılığıyla yineler.|
|[Kdocument::GetPathName](#getpathname)|Belgenin veri dosyasının yolunu döndürür.|
|[KDocument::GetThumbnail](#getthumbnail)|Küçük resmi görüntülemek için küçük resim sağlayıcısı tarafından kullanılacak bir bit eşlemi oluşturmak için çağrılır.|
|[Kkişnasyon::Başlık Alma](#gettitle)|Belgenin başlığını döndürür.|
|[KKK::InitializeSearchContent](#initializesearchcontent)|Arama İşleyicisi için arama içeriğini başlatmaya çağrıldı.|
|[Kdocument::Değiştirilmiş](#ismodified)|Belgenin son kaydedildiği tarihten beri değiştirilip değiştirilmediğini gösterir.|
|[KDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|Bu nesne örneğinin `CDocument` Arama & Düzenle işleyicisi için oluşturulup oluşturulmadığını söyler.|
|[Kdocument::loaddocumentfromstream](#loaddocumentfromstream)|Akıştan belge verilerini yüklemek için çağrıldı.|
|[Kdocument::OnBeforerichPreviewFontChanged](#onbeforerichpreviewfontchanged)|Zengin Önizleme yazı tipi değiştirilmeden önce çağrılır.|
|[Kdocument::OnChangedViewList](#onchangedviewlist)|Görünüm eklendikten veya belgeden kaldırıldıktan sonra çağrılır.|
|[Kdocument::OnCloseDocument](#onclosedocument)|Belgeyi kapatmak için çağrıldı.|
|[Kdocument::OnCreatePreviewFrame](#oncreatepreviewframe)|Zengin Önizleme için bir önizleme çerçevesi oluşturması gerektiğinde çerçeve tarafından çağrılır.|
|[Kdocument::OndocumentEvent](#ondocumentevent)|Bir belge olayına yanıt olarak çerçeve tarafından çağrılır.|
|[KDocument::OnDrawThumbnail](#ondrawthumbnail)|Küçük resmin içeriğini çizmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.|
|[Kdocument::OnloadDocumentFromstream](#onloaddocumentfromstream)|Belge verilerini akıştan yüklemesi gerektiğinde çerçeve tarafından çağrılır.|
|[Kdocument::Onnewdocument](#onnewdocument)|Yeni bir belge oluşturmak için çağrıldı.|
|[Kdocument::OnOpenDocument](#onopendocument)|Varolan bir belgeyi açmak için çağrıldı.|
|[KBelge::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|HWND'yi GetFocus Işlevini aramaktan döndürmek için önizleme işleyicisini yönlendirir.|
|[KBelge::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|Önizleme işleyicisinin çalıştırıldığı işlemin ileti pompasından geçen bir tuş vuruşunu işlemek için önizleme işleyicisini yönlendirir.|
|[Kdocument::OnrichPreviewbackColorChanged](#onrichpreviewbackcolorchanged)|Zengin Önizleme arka plan rengi değiştiğinde çağrılır.|
|[Kdocument::OnrichPreviewFontChanged](#onrichpreviewfontchanged)|Zengin Önizleme yazı tipi değiştiğinde çağrılır.|
|[Kdocument::OnrichPreviewSite Değiştirildi](#onrichpreviewsitechanged)|Rich Preview sitesi değiştiğinde çağrılır.|
|[Kdocument::OnrichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|Zengin Önizleme metin rengi değiştiğinde çağrılır.|
|[Kdocument::OnSaveDocument](#onsavedocument)|Belgeyi diske kaydetmek için çağrıldı.|
|[KBelge::OnUnloadHandler](#onunloadhandler)|Önizleme işleyicisi indirilirken çerçeve tarafından çağrılır.|
|[KKK::PreCloseFrame](#precloseframe)|Çerçeve penceresi kapanmadan önce çağrılır.|
|[Cdocument::ReadNextChunkValue](#readnextchunkvalue)|Sonraki öbek değerini okur.|
|[Kdocument::ReleaseFile](#releasefile)|Diğer uygulamalar tarafından kullanılabilir hale getirmek için bir dosya yayımlar.|
|[Kdocument::RemoveChunk](#removechunk)|Belirtilen GUID ile bir öbek kaldırır.|
|[Kdocument::RemoveView](#removeview)|Görünümü belgeden ayırır.|
|[Kdocument::ReportSaveLoadException](#reportsaveloadexception)|Gelişmiş overridable; bir özel durum nedeniyle bir açık veya kaydet işlemi tamamlanamadığında çağrılır.|
|[Kdocument::SaveModified](#savemodified)|Gelişmiş overridable; belgenin kaydedilip kaydedilmemesi gerektiğini sormak için kullanıcıya çağrıldı.|
|[Kdocument::SetChunkValue](#setchunkvalue)|Bir yığın değeri ayarlar.|
|[Kdocument::SetModifiedFlag](#setmodifiedflag)|Belgenin en son kaydedildiği tarihten beri değiştirildiğinibelirten bir bayrak ayarlar.|
|[Kdocument::SetPathName](#setpathname)|Belge tarafından kullanılan veri dosyasının yolunu ayarlar.|
|[Kkişnasyon::SetTitle](#settitle)|Belgenin başlığını ayarlar.|
|[Kdocument::UpdateAllViews](#updateallviews)|Belgenin değiştirildiğini niçin tüm görünümleri not alameti.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Kdocument::OnFileSendMail](#onfilesendmail)|Belge eklenmiş bir posta iletisi gönderir.|
|[Kdocument::OnUpdateFileSendMail](#onupdatefilesendmail)|Posta desteği varsa Posta Gönder komutunu etkinleştirin.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[Çknö:m_bGetThumbnailMode](#m_bgetthumbnailmode)|Bu nesnenin `CDocument` küçük resimler için dllhost tarafından oluşturulduğunu belirtir. Giriş `CView::OnDraw`yapılmalı.|
|[Çknö:m_bPreviewHandlerMode](#m_bpreviewhandlermode)|Bu `CDocument` nesne için prevhost tarafından `Rich Preview`oluşturulan belirtir. Giriş `CView::OnDraw`yapılmalı.|
|[Çknö:m_bSearchMode](#m_bsearchmode)|Bu nesnenin `CDocument` dizin leyici veya başka bir arama uygulaması tarafından oluşturulduğunu belirtir.|
|[Çknö:m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Zengin Önizleme penceresinin arka plan rengini belirtir. Bu renk ana bilgisayar tarafından ayarlanır.|
|[Çknö:m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Zengin Önizleme penceresinin ön plan rengini belirtir. Bu renk ana bilgisayar tarafından ayarlanır.|
|[Çknö:m_lfRichPreviewFont](#m_lfrichpreviewfont)|Zengin Önizleme penceresi için metin yazı tipini belirtir. Bu yazı tipi bilgileri ana bilgisayar tarafından ayarlanır.|

## <a name="remarks"></a>Açıklamalar

Belge, kullanıcının genellikle Dosya Aç komutuyla açtığı ve Dosya Kaydet komutuyla kaydettiği veri birimini temsil eder.

`CDocument`belge oluşturma, yükleme ve kaydetme gibi standart işlemleri destekler. Çerçeve, `CDocument`'' tarafından tanımlanan arabirimi kullanarak belgeleri manipüle eder.

Bir uygulama birden fazla belge türünü destekleyebilir; örneğin, bir uygulama hem elektronik tabloları hem de metin belgelerini destekleyebilir. Her belge türünde ilişkili bir belge şablonu vardır; belge şablonu, bu belge türü için hangi kaynakların (örneğin, menü, simge veya hızlandırıcı tablosu) kullanıldığını belirtir. Her belge ilişkili `CDocTemplate` nesneiçin bir işaretçi içerir.

Kullanıcılar, bir belgeyle ilişkili [CView](../../mfc/reference/cview-class.md) nesnesi(ler) aracılığıyla etkileşimde bulunmaktadır. Görünüm, çerçeve penceresinde belgenin görüntüsünü işler ve kullanıcı girişini belgedeki işlemler olarak yorumlar. Bir belgeyle ilişkili birden çok görünüm eolabilir. Kullanıcı belgeüzerinde bir pencere açtığında, çerçeve bir görünüm oluşturur ve belgeye bağlar. Belge şablonu, her belge türünü görüntülemek için ne tür bir görünüm ve çerçeve penceresi nin kullanıldığını belirtir.

Belgeler çerçevenin standart komut yönlendirmesinin bir parçasıdır ve sonuç olarak standart kullanıcı arabirimi bileşenlerinden (Dosya Kaydet menü öğesi gibi) komutlar alır. Belge, etkin görünüm tarafından iletilen komutları alır. Belge belirli bir komutu işlemiyorsa, komutu onu yöneten belge şablonuna iletilir.

Bir belgenin verileri değiştirildiğinde, görünümlerinin her biri bu değişiklikleri yansıtmalıdır. `CDocument`bu tür değişikliklerin görünümlerini bildirmeniz için [UpdateAllViews](#updateallviews) üye işlevini sağlar, böylece görünümler gerektiğinde kendilerini yeniden boyayabilir. Çerçeve ayrıca, kullanıcıdan değiştirilen bir dosyayı kapatmadan önce kaydetmesini ister.

Belgeleri tipik bir uygulamada uygulamak için aşağıdakileri yapmanız gerekir:

- Her belge türü `CDocument` için bir sınıf türetin.

- Her belgenin verilerini depolamak için üye değişkenler ekleyin.

- Belgenin verilerini okumak ve değiştirmek için üye işlevleri uygulayın. Belgenin görünümleri bu üye işlevlerin en önemli kullanıcılarıdır.

- [CObject geçersiz kılın::Belge](../../mfc/reference/cobject-class.md#serialize) sınıfınızdaki üye işlevini diske ve diskten yazmak ve okumak için serileştirin.

`CDocument`posta desteği (MAPI) varsa belgenizi posta yoluyla göndermeyi destekler. [MFC'deki MAPI](../../mfc/mapi.md) ve [MAPI Desteği makalelerini](../../mfc/mapi-support-in-mfc.md)görün.

Daha fazla `CDocument`bilgi için , bkz [Serialization](../../mfc/serialization-in-mfc.md), [Belge / Görünüm Mimari Konular](../../mfc/document-view-architecture.md), ve Belge / Görünüm [Oluşturma](../../mfc/document-view-creation.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`CDocument`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cdocumentaddview"></a><a name="addview"></a>CDocument::AddView

Belgeye görünüm eklemek için bu işlevi arayın.

```cpp
void AddView(CView* pView);
```

### <a name="parameters"></a>Parametreler

*pGörünüm*<br/>
Eklenen görünüme işaret edilir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, belirtilen görünümü belgeyle ilişkili görünümler listesine ekler; işlev, görünümün bu belgeye belge işaretçisini de ayarlar. Çerçeve, yeni oluşturulan bir görünüm nesnesini belgeye takarken bu işlevi çağırır; bu, Dosya Yeni, Dosya Aç veya Yeni Pencere komutuna yanıt olarak veya bir ayırıcı penceresi bölündüğünde oluşur.

Bu işlevi yalnızca bir görünümü el ile oluşturuyor ve bağlıyorsanız arayın. Genellikle, belge sınıfını, görünüm sınıfını ve çerçeve pencere sınıfını ilişkilendirmek için bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesi tanımlayarak çerçevenin belgeleri ve görünümleri bağlamasına izin verilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]

## <a name="cdocumentbeginreadchunks"></a><a name="beginreadchunks"></a>KDocument::BeginReadChunks

Yığın okumayı başharfe iter.

```
virtual void BeginReadChunks ();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentcancloseframe"></a><a name="cancloseframe"></a>Kdocument::CanCloseFrame

Belgeyi görüntüleyen bir çerçeve penceresi kapanmadan önce çerçeve tarafından çağrılır.

```
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Parametreler

*pFrame*<br/>
Belgeye iliştirilmiş bir görünümün çerçeve penceresine işaret edilir.

### <a name="return-value"></a>Dönüş Değeri

Çerçeve penceresini kapatmak güvenliyse sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, belgeyi görüntüleyen başka çerçeve pencereleri olup olmadığını denetler. Belirtilen çerçeve penceresi belgeyi görüntüleyen son pencereyse, işlev kullanıcıdan belgeyi kaydetmesini ister. Çerçeve penceresi kapatıldığında özel işleme gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz.

## <a name="cdocumentcdocument"></a><a name="cdocument"></a>Kbelge::Kdocument

Bir `CDocument` nesne inşa eder.

```
CDocument();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve sizin için belge oluşturma işler. Belge başına başlatma yı gerçekleştirmek için [OnNewDocument](#onnewdocument) üye işlevini geçersiz kılın; bu özellikle tek belge arabirimi (SDI) uygulamalarında önemlidir.

## <a name="cdocumentclearchunklist"></a><a name="clearchunklist"></a>Kdocument::ClearChunklist

Yığın listesini temizler.

```
virtual void ClearChunkList ();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentclearpathname"></a><a name="clearpathname"></a>Kdocument::ClearPathName

Belge nesnesinin yolunu temizler.

```
virtual void ClearPathName();
```

### <a name="remarks"></a>Açıklamalar

Bir `CDocument` nesneden yolu temizlemek, belge bir sonraki kaydedildiğinde uygulamanın kullanıcıdan istenmesine neden olur. Bu, **Kaydet** komutu'nun Bir **Farklı Kaydet** komutu gibi görünmesini sağlar.

## <a name="cdocumentdeletecontents"></a><a name="deletecontents"></a>KKK::DeleteContents

`CDocument` Nesnenin kendisini yok etmeden belgenin verilerini silmek için çerçeve tarafından çağrılır.

```
virtual void DeleteContents();
```

### <a name="remarks"></a>Açıklamalar

Belge imha edilmeden hemen önce çağrılır. Ayrıca, belgenin yeniden kullanılmadan önce boş olduğundan emin olmak için de çağrılır. Bu, özellikle yalnızca bir belge kullanan bir SDI uygulaması için önemlidir; kullanıcı başka bir belge oluşturduğunda veya açtığında belge yeniden kullanılır. Belgenin tüm verilerini silen bir "Tümünü Temizle" veya benzer bir komut uygulamak için bu işlevi arayın. Bu işlevin varsayılan uygulaması hiçbir şey yapmaz. Belgenizdeki verileri silmek için bu işlevi geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]

## <a name="cdocumentfindchunk"></a><a name="findchunk"></a>Kdocument::FindChunk

Belirli bir GUID ile bir yığın arar.

```
virtual POSITION FindChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Parametreler

*Guıd*<br/>
Bulmak için bir yığının GUID belirtir.

*Pıd*<br/>
Bulmak için bir yığın bir PID belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa iç yığın listesinde konumlandırın. Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentgetadapter"></a><a name="getadapter"></a>KKK:GetAdapter

Arabirimi uygulayan `IDocument` bir nesneye işaretçi döndürür.

```
virtual ATL::IDocument* GetAdapter();
```

### <a name="return-value"></a>Dönüş Değeri

`IDocument` Arabirimi uygulayan bir nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentgetdoctemplate"></a><a name="getdoctemplate"></a>Kdocument::GetDocTemplate

Bu belge türü için belge şablonuna işaretçi almak için bu işlevi arayın.

```
CDocTemplate* GetDocTemplate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu belge türü için belge şablonuna işaretçi veya belge bir belge şablonu tarafından yönetilmiyorsa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]

## <a name="cdocumentgetfile"></a><a name="getfile"></a>Kdocument::GetFile

Bir `CFile` nesneye işaretçi almak için bu üye işlevi arayın.

```
virtual CFile* GetFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
İstenilen dosyaya giden yol olan dize. Yol göreceli veya mutlak olabilir.

*pHata*<br/>
İşlemin tamamlanma durumunu gösteren varolan bir dosya özel durum nesnesinin işaretçisi.

*nOpen Bayraklar*<br/>
Paylaşım ve erişim modu. Dosyayı açarken yapılacak eylemi belirtir. CFile oluşturucu [CFile::CFile'da](../../mfc/reference/cfile-class.md#cfile) listelenen seçenekleri bitwise OR (&#124;) işleci kullanarak birleştirebilirsiniz. Bir erişim izni ve bir paylaşım seçeneği gereklidir; `modeCreate` ve `modeNoInherit` modları isteğe bağlıdır.

### <a name="return-value"></a>Dönüş Değeri

Bir `CFile` nesneye işaretçi.

## <a name="cdocumentgetfirstviewposition"></a><a name="getfirstviewposition"></a>Kdocument::GetFirstViewPosition

Belgeyle ilişkili görünümler listesindeki ilk görünümün konumunu almak için bu işlevi arayın.

```
virtual POSITION GetFirstViewPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

[GetNextView](#getnextview) üye işlevi ile yineleme için kullanılabilecek bir POSITION değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

## <a name="cdocumentgetnextview"></a><a name="getnextview"></a>Kdocument::GetNextView

Bu işlevi, belgenin tüm görünümlerini yinelemek için çağırın.

```
virtual CView* GetNextView(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*Rposition*<br/>
Önceki bir aramayla veya `GetNextView` [GetFirstViewPosition](#getfirstviewposition) üye işlevlerine yapılan bir aramayla döndürülen BIR KONUM değerine başvuru. Bu değer NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

*rPosition*tarafından tanımlanan görünüme işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlev *rPosition* tarafından tanımlanan görünümü döndürür ve sonra *rPosition'ı* listedeki bir sonraki görünümün KONUM değerine ayarlar. Alınan görünüm listenin son görüntüsüyse, *rPosition* NULL olarak ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

## <a name="cdocumentgetpathname"></a><a name="getpathname"></a>Kdocument::GetPathName

Belgenin disk dosyasının tam nitelikli yolunu almak için bu işlevi arayın.

```
const CString& GetPathName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin tam nitelikli yolu. Belge kaydedilmediyse veya onunla ilişkili bir disk dosyası yoksa bu dize boştur.

## <a name="cdocumentgetthumbnail"></a><a name="getthumbnail"></a>KDocument::GetThumbnail

Küçük resmi görüntülemek için küçük resim sağlayıcısı tarafından kullanılacak bir bit eşlemi oluşturur.

```
virtual BOOL GetThumbnail(
    UINT cx,
    HBITMAP* phbmp,
    DWORD* pdwAlpha);
```

### <a name="parameters"></a>Parametreler

*Cx*<br/>
Bit eşleminin genişliğini ve yüksekliğini belirtir.

*phbmp*<br/>
İşlev başarılı bir şekilde döndüğünde biteşe bir tanıtıcı içerir.

*pdwAlpha*<br/>
İşlev başarılı bir şekilde döndüğünde alfa kanal değerini belirten bir DWORD içerir.

### <a name="return-value"></a>Dönüş Değeri

Küçük resim için bir bit eşlemi başarıyla oluşturulduysa TRUE döndürür; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentgettitle"></a><a name="gettitle"></a>Kkişnasyon::Başlık Alma

Genellikle belgenin dosya adından türetilen belgenin başlığını almak için bu işlevi arayın.

```
const CString& GetTitle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin başlığı.

## <a name="cdocumentinitializesearchcontent"></a><a name="initializesearchcontent"></a>KKK::InitializeSearchContent

Arama İşleyicisi için arama içeriğini başlatmaya çağrıldı.

```
virtual void InitializeSearchContent ();
```

### <a name="remarks"></a>Açıklamalar

Arama içeriğini başlatmayı türemiş bir sınıfta bu yöntemi geçersiz kılın. İçerik, ";" ile sınırlandırılmış parçalariçeren bir dize olmalıdır. Örneğin, "nokta; dikdörtgen; ole öğe".

## <a name="cdocumentismodified"></a><a name="ismodified"></a>Kdocument::Değiştirilmiş

Belgenin en son kaydedildiği tarihten beri değiştirilip değiştirilmediğini belirlemek için bu işlevi arayın.

```
virtual BOOL IsModified();
```

### <a name="return-value"></a>Dönüş Değeri

Belge son kaydedildiği için değiştirildiyse sıfırsız; aksi takdirde 0.

## <a name="cdocumentissearchandorganizehandler"></a><a name="issearchandorganizehandler"></a>KDocument::IsSearchAndOrganizeHandler

Bu örneğin `CDocument` Arama & Düzenle işleyicisi için oluşturulup oluşturulmadığını bildirir.

```
BOOL IsSearchAndOrganizeHandler() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu örnek Arama `CDocument` & Düzenle işleyicisi için oluşturulduysa TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Şu anda bu işlev true yalnızca işlem dışı bir sunucuda uygulanan Zengin Önizleme işleyicileri için döndürür. Bu işlevin DOĞRU döndürülmesini sağlamak için uygulama düzeyinize uygun bayrakları (m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode) ayarlayabilirsiniz.

## <a name="cdocumentloaddocumentfromstream"></a><a name="loaddocumentfromstream"></a>Kdocument::loaddocumentfromstream

Bir akıştan belge verilerini yüklemek için çağrıldı.

```
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,
    DWORD dwGrfMode);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
Akış için bir işaretçi. Bu akış Shell tarafından sağlanır.

*dwGrfMode*<br/>
Akışa erişim modu.

### <a name="return-value"></a>Dönüş Değeri

S_OK yük işlemi başarılı olursa, aksi takdirde bir hata kodu ile HRESULT.

### <a name="remarks"></a>Açıklamalar

Akıştan veri yükleme yöntemini özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılabilirsiniz.

## <a name="cdocumentm_bgetthumbnailmode"></a><a name="m_bgetthumbnailmode"></a>Çknö:m_bGetThumbnailMode

Nesnenin `CDocument` küçük resimler için dllhost tarafından oluşturulduğunu belirtir. Giriş `CView::OnDraw`yapılmalı.

```
BOOL m_bGetThumbnailMode;
```

### <a name="remarks"></a>Açıklamalar

`TRUE`belgenin küçük resimler için dllhost tarafından oluşturulduğunu gösterir.

## <a name="cdocumentm_bpreviewhandlermode"></a><a name="m_bpreviewhandlermode"></a>Çknö:m_bPreviewHandlerMode

Nesnenin `CDocument` Rich Preview için prevhost tarafından oluşturulduğunu belirtir. Giriş `CView::OnDraw`yapılmalı.

```
BOOL m_bPreviewHandlerMode;
```

### <a name="remarks"></a>Açıklamalar

TRUE, belgenin Rich Preview için prevhost tarafından oluşturulduğunu gösterir.

## <a name="cdocumentm_bsearchmode"></a><a name="m_bsearchmode"></a>Çknö:m_bSearchMode

Nesnenin dizinleyici `CDocument` veya başka bir arama uygulaması tarafından oluşturulduğunu belirtir.

```
BOOL m_bSearchMode;
```

### <a name="remarks"></a>Açıklamalar

`TRUE`belgenin dizin leyici veya başka bir arama uygulaması tarafından oluşturulduğunu gösterir.

## <a name="cdocumentm_clrrichpreviewbackcolor"></a><a name="m_clrrichpreviewbackcolor"></a>Çknö:m_clrRichPreviewBackColor

Zengin Önizleme penceresinin arka plan rengini belirtir. Bu renk ana bilgisayar tarafından ayarlanır.

```
COLORREF m_clrRichPreviewBackColor;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentm_clrrichpreviewtextcolor"></a><a name="m_clrrichpreviewtextcolor"></a>Çknö:m_clrRichPreviewTextColor

Zengin Önizleme penceresinin ön plan rengini belirtir. Bu renk ana bilgisayar tarafından ayarlanır.

```
COLORREF m_clrRichPreviewTextColor;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentm_lfrichpreviewfont"></a><a name="m_lfrichpreviewfont"></a>Çknö:m_lfRichPreviewFont

Zengin Önizleme penceresi için metin yazı tipini belirtir. Bu yazı tipi bilgileri ana bilgisayar tarafından ayarlanır.

```
CFont m_lfRichPreviewFont;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentonbeforerichpreviewfontchanged"></a><a name="onbeforerichpreviewfontchanged"></a>Kdocument::OnBeforerichPreviewFontChanged

Zengin Önizleme yazı tipi değiştirilmeden önce çağrılır.

```
virtual void OnBeforeRichPreviewFontChanged();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentonchangedviewlist"></a><a name="onchangedviewlist"></a>Kdocument::OnChangedViewList

Görünüm eklendikten veya belgeden kaldırıldıktan sonra çerçeve tarafından çağrılır.

```
virtual void OnChangedViewList();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması, son görünümün kaldırılıp kaldırılmadığını denetler ve varsa belgeyi siler. Çerçeve bir görünüm eklendiğinde veya kaldırdığında özel işleme gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Örneğin, bir belgenin görünüm eklenmemiş olsa bile açık kalmasını istiyorsanız, bu işlevi geçersiz kılın.

## <a name="cdocumentonclosedocument"></a><a name="onclosedocument"></a>Kdocument::OnCloseDocument

Belge kapatıldığında, genellikle Dosya Kapat komutunun bir parçası olarak çerçeve tarafından çağrılır.

```
virtual void OnCloseDocument();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması belgeyi görüntülemek için kullanılan tüm çerçeveleri yok eder, görünümü kapatır, belgenin içeriğini temizler ve belgenin verilerini silmek için [DeleteContents](#deletecontents) üye işlevini arar.

Çerçeve bir belgeyi kapattığında özel temizleme işleme gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Örneğin, belge bir veritabanındaki bir kaydı temsil ederse, veritabanını kapatmak için bu işlevi geçersiz kılmak isteyebilirsiniz. Geçersiz kılmanızdan bu işlevin taban sınıf sürümünü aramalısınız.

## <a name="cdocumentoncreatepreviewframe"></a><a name="oncreatepreviewframe"></a>Kdocument::OnCreatePreviewFrame

Zengin Önizleme için bir önizleme çerçevesi oluşturması gerektiğinde çerçeve tarafından çağrılır.

```
virtual BOOL OnCreatePreviewFrame();
```

### <a name="return-value"></a>Dönüş Değeri

Çerçeve başarıyla oluşturulursa TRUE döndürür; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentondocumentevent"></a><a name="ondocumentevent"></a>Kdocument::OndocumentEvent

Bir belge olayına yanıt olarak çerçeve tarafından çağrılır.

```
virtual void OnDocumentEvent(DocumentEvent deEvent);
```

### <a name="parameters"></a>Parametreler

*deOlay*<br/>
[içinde] Olay türünü açıklayan numaralandırılmış bir veri türü.

### <a name="remarks"></a>Açıklamalar

Belge olayları birden çok sınıfı etkileyebilir. Bu yöntem, [CDocument Sınıfı](../../mfc/reference/cdocument-class.md)dışındaki sınıfları etkileyen belge olaylarını işlemekten sorumludur. Şu anda, belge olaylarına yanıt vermesi gereken tek sınıf [CDataRecoveryHandler Sınıfıdır.](../../mfc/reference/cdatarecoveryhandler-class.md) Sınıfın, `CDocument` `CDocument`'' nin üzerindeki etkiyi işlemekten sorumlu başka geçersiz yöntemleri vardır.

Aşağıdaki tabloda *deEvent* için olası değerler ve bunların karşılık gelen olaylar listelenmektedir.

|Değer|İlgili Olay|
|-----------|-------------------------|
|`onAfterNewDocument`|Yeni bir belge oluşturuldu.|
|`onAfterOpenDocument`|Yeni bir belge açıldı.|
|`onAfterSaveDocument`|Belge kaydedildi.|
|`onAfterCloseDocument`|Belge kapatıldı.|

## <a name="cdocumentondrawthumbnail"></a><a name="ondrawthumbnail"></a>KDocument::OnDrawThumbnail

Küçük resmi çizmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

```
virtual void OnDrawThumbnail(
    CDC& dc,
    LPRECT lprcBounds);
```

### <a name="parameters"></a>Parametreler

*Dc*<br/>
Aygıt bağlamına başvuru.

*lprcBounds*<br/>
Küçük resmin çizilmesi gereken alanın sınırlayıcı bir dikdörtgenini belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentonfilesendmail"></a><a name="onfilesendmail"></a>Kdocument::OnFileSendMail

Yerleşik posta ana bilgisayarı (varsa) üzerinden belgeek olarak ileti gönderir.

```cpp
void OnFileSendMail();
```

### <a name="remarks"></a>Açıklamalar

`OnFileSendMail`[OnSaveDocument'ı,](#onsavedocument) adsız ve değiştirilmiş belgeleri, daha sonra elektronik posta yoluyla gönderilen geçici bir dosyaya seri hale getirmek (kaydetmeye) çağırır. Belge değiştirilmemişse, geçici bir dosya gerekmez; orijinal gönderilir. `OnFileSendMail`MAPI32 yükler. DLL zaten yüklenmediyse.

`OnFileSendMail` [COleDocument](../../mfc/reference/coledocument-class.md) için özel bir uygulama bileşik dosyaları doğru işler.

`CDocument`posta desteği (MAPI) varsa belgenizi posta yoluyla göndermeyi destekler. [MFC'deki MAPI Topics](../../mfc/mapi.md) ve [MAPI Desteği makalelerini](../../mfc/mapi-support-in-mfc.md)görün.

## <a name="cdocumentonloaddocumentfromstream"></a><a name="onloaddocumentfromstream"></a>Kdocument::OnloadDocumentFromstream

Belge verilerini bir akıştan yüklemesi gerektiğinde çerçeve tarafından çağrılır.

```
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,
    DWORD grfMode);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
Gelen bir akış için bir işaretçi.

*grfMode*<br/>
Akışa erişim modu.

### <a name="return-value"></a>Dönüş Değeri

yük başarılı olursa S_OK; aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentonnewdocument"></a><a name="onnewdocument"></a>Kdocument::Onnewdocument

Yeni Dosya komutunun bir parçası olarak çerçeve tarafından çağrılır.

```
virtual BOOL OnNewDocument();
```

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla başharfe vurulduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması, belgenin boş olduğundan emin olmak için [DeleteContents](#deletecontents) üye işlevini çağırır ve ardından yeni belgeyi temiz olarak işaretler. Yeni bir belge için veri yapısını başlatmayı sağlamak için bu işlevi geçersiz kılın. Geçersiz kılmanızdan bu işlevin taban sınıf sürümünü aramalısınız.

Kullanıcı bir SDI uygulamasında Yeni Dosya komutunu seçerse, çerçeve yeni bir belge oluşturmak yerine varolan belgeyi yeniden başlatmak için bu işlevi kullanır. Kullanıcı birden çok belge arabirimi (MDI) uygulamasında Yeni Dosya'yı seçerse, çerçeve her seferinde yeni bir belge oluşturur ve sonra bu işlevi başlatmayı çağırır. SDI uygulamalarında etkili olması için Yeni Dosya komutunun oluşturucuyerine bu işlevde başlatma kodunuzu yerleştirmeniz gerekir.

İki kez çağrılan `OnNewDocument` durumlar olduğunu unutmayın. Bu, belge ActiveX Document Server olarak katıştırıldığında oluşur. İşlev ilk `CreateInstance` olarak yöntem `COleObjectFactory`(türetilmiş sınıf tarafından maruz) ve `InitNew` ikinci kez `COleServerDoc`yöntem (-türetilmiş sınıf tarafından maruz) tarafından çağrılır.

### <a name="example"></a>Örnek

Aşağıdaki örnekler, bir belge nesnesini başlatmanın alternatif yöntemlerini göstermektedir.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

## <a name="cdocumentonopendocument"></a><a name="onopendocument"></a>Kdocument::OnOpenDocument

Dosya Aç komutunun bir parçası olarak çerçeve tarafından çağrılır.

```
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Açılacak belgenin yolunu işaret edin.

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla yüklenmişse sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması belirtilen dosyayı açar, belgenin boş olduğundan emin olmak için [DeleteContents](#deletecontents) üye işlevini çağırır, [CObject'i çağırır::Dosyanın](../../mfc/reference/cobject-class.md#serialize) içeriğini okumak için serihale getirir ve belgeyi temiz olarak işaretler. Arşiv mekanizması veya dosya mekanizması dışında bir şey kullanmak istiyorsanız bu işlevi geçersiz kılın. Örneğin, belgelerin ayrı dosyalar yerine bir veritabanındaki kayıtları temsil ettiği bir uygulama yazabilirsiniz.

Kullanıcı bir SDI uygulamasında Dosya Aç komutunu seçerse, çerçeve yeni bir `CDocument` nesne oluşturmak yerine varolan nesneyi yeniden başlatmak için bu işlevi kullanır. Kullanıcı bir MDI uygulamasında Dosya Aç'ı seçerse, `CDocument` çerçeve her seferinde yeni bir nesne oluşturuyor ve sonra bu işlevi başlatması için çağırır. SDI uygulamalarında etkili olması için Dosya Aç komutunun oluşturucu yerine bu işlevde başlatma kodunuzu yerleştirmeniz gerekir.

### <a name="example"></a>Örnek

Aşağıdaki örnekler, bir belge nesnesini başlatmanın alternatif yöntemlerini göstermektedir.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

[!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]

## <a name="cdocumentonpreviewhandlerqueryfocus"></a><a name="onpreviewhandlerqueryfocus"></a>KBelge::OnPreviewHandlerQueryFocus

`GetFocus` Önizleme işleyicisini işlevi çağırmaktan alınan HWND'yi döndürmek için yönlendirir.

```
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```

### <a name="parameters"></a>Parametreler

*phwnd*<br/>
[çıkış] Bu yöntem döndüğünde, önizleme işleyicisinin ön plan `GetFocus` iş parçacığı işlevi çağıran HWND döndürülen bir işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK verir; veya başka bir hata değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentonpreviewhandlertranslateaccelerator"></a><a name="onpreviewhandlertranslateaccelerator"></a>KBelge::OnPreviewHandlerTranslateAccelerator

Önizleme işleyicisinin çalıştırıldığı işlemin ileti pompasından geçen bir tuş vuruşunu işlemek için önizleme işleyicisini yönlendirir.

```
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```

### <a name="parameters"></a>Parametreler

*pmsg*<br/>
[içinde] Pencere iletisi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Tuş vuruşu iletisi önizleme işleyicisi tarafından işlenebilirse, işleyici bunu işler ve S_OK döndürür. Önizleme işleyicisi tuş vuruşu iletisini işleyemiyorsa, bunu ana bilgisayara . `IPreviewHandlerFrame::TranslateAccelerator` Ana bilgisayar iletiyi işlerse, bu yöntem S_OK döndürür. Ana bilgisayar iletiyi işlemiyorsa, bu yöntem S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentonrichpreviewbackcolorchanged"></a><a name="onrichpreviewbackcolorchanged"></a>Kdocument::OnrichPreviewbackColorChanged

Zengin Önizleme arka plan rengi değiştiğinde çağrılır.

```
virtual void OnRichPreviewBackColorChanged();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentonrichpreviewfontchanged"></a><a name="onrichpreviewfontchanged"></a>Kdocument::OnrichPreviewFontChanged

Zengin Önizleme yazı tipi değiştiğinde çağrılır.

```
virtual void OnRichPreviewFontChanged();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentonrichpreviewsitechanged"></a><a name="onrichpreviewsitechanged"></a>Kdocument::OnrichPreviewSite Değiştirildi

Zengin Önizleme sitesi değiştiğinde çağrılır.

```
virtual void OnRichPreviewSiteChanged();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentonrichpreviewtextcolorchanged"></a><a name="onrichpreviewtextcolorchanged"></a>Kdocument::OnrichPreviewTextColorChanged

Zengin Önizleme metin rengi değiştiğinde çağrılır.

```
virtual void OnRichPreviewTextColorChanged();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentonsavedocument"></a><a name="onsavedocument"></a>Kdocument::OnSaveDocument

Dosya Kaydet veya Dosya Kaydet Komutu'nun bir parçası olarak çerçeve tarafından çağrılır.

```
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Dosyanın kaydedilmesi gereken tam nitelikli yolu işaret edin.

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla kaydedildiyse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması belirtilen dosyayı açar, [CObject'i çağırır::Belgenin](../../mfc/reference/cobject-class.md#serialize) verilerini dosyaya yazmak için serihale getirin ve belgeyi temiz olarak işaretler. Çerçeve bir belge kaydettiğinde özel işleme gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Örneğin, belgelerin ayrı dosyalar yerine bir veritabanındaki kayıtları temsil ettiği bir uygulama yazabilirsiniz.

## <a name="cdocumentonunloadhandler"></a><a name="onunloadhandler"></a>KBelge::OnUnloadHandler

Önizleme işleyicisi boşaldığında çerçeve tarafından çağrılır.

```
virtual void OnUnloadHandler();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentonupdatefilesendmail"></a><a name="onupdatefilesendmail"></a>Kdocument::OnUpdateFileSendMail

Posta desteği (MAPI) varsa ID_FILE_SEND_MAIL komutunu etkinleştirin.

```cpp
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
ID_FILE_SEND_MAIL komutuyla ilişkili [CCmdUI](../../mfc/reference/ccmdui-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Aksi takdirde işlev, menü öğesinin üstündeki veya altındaki ayırıcılar da dahil olmak üzere menüden ID_FILE_SEND_MAIL komutunu kaldırır. MAPI32 ise MAPI etkindir. DLL yolda ve WIN'in [Posta] bölümünde bulunur. INI dosyası, MAPI=1. Çoğu uygulama bu komutu Dosya menüsüne koyar.

`CDocument`posta desteği (MAPI) varsa belgenizi posta yoluyla göndermeyi destekler. [MFC'deki MAPI Topics](../../mfc/mapi.md) ve [MAPI Desteği makalelerini](../../mfc/mapi-support-in-mfc.md)görün.

## <a name="cdocumentprecloseframe"></a><a name="precloseframe"></a>KKK::PreCloseFrame

Bu üye işlev, çerçeve penceresi yok edilmeden önce çerçeve tarafından çağrılır.

```
virtual void PreCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Parametreler

*pFrame*<br/>
İlişkili nesneyi tutan [CFrameWnd](../../mfc/reference/cframewnd-class.md) işaretçisi. `CDocument`

### <a name="remarks"></a>Açıklamalar

Özel temizleme sağlamak için geçersiz kılınabilir, ancak taban sınıfı da aradığından emin olun.

Varsayılan hiçbir `PreCloseFrame` şey `CDocument`yapmaz. Türetilmiş `CDocument`sınıflar [COleDocument](../../mfc/reference/coledocument-class.md) ve [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) bu üye işlevi kullanır.

## <a name="cdocumentreadnextchunkvalue"></a><a name="readnextchunkvalue"></a>Cdocument::ReadNextChunkValue

Sonraki öbek değerini okur.

```
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```

### <a name="parameters"></a>Parametreler

*ppDeğer*<br/>
[çıkış] İşlev döndüğünde, *ppValue* okunan değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentreleasefile"></a><a name="releasefile"></a>Kdocument::ReleaseFile

Bu üye işlev, bir dosyayı serbest bırakmak için çerçeve tarafından çağrılır ve bu da dosyayı diğer uygulamalar tarafından kullanılabilir hale getirir.

```
virtual void ReleaseFile(
    CFile* pFile,
    BOOL bAbort);
```

### <a name="parameters"></a>Parametreler

*pFile*<br/>
CFile nesnesinin bir işaretçisi serbest bırakılacak.

*bAbort*<br/>
Dosyanın ya da `CFile::Close` 'yı `CFile::Abort`kullanarak serbest bırakılıp bırakılmayacağını belirtir. Dosya CFile kullanılarak çıkacaksa [YANLIŞ::Kapat](../../mfc/reference/cfile-class.md#close); DOSYA CFile kullanılarak yayımlanacaksa [DOĞRU::İptal](../../mfc/reference/cfile-class.md#abort).

### <a name="remarks"></a>Açıklamalar

*bAbort* TRUE `ReleaseFile` ise, `CFile::Abort`aramalar ve dosya serbest bırakılır. `CFile::Abort`bir istisna atmaz.

*bAbort* FALSE `ReleaseFile` ise, `CFile::Close` aramalar ve dosya serbest bırakılır.

Dosya yayımlanmadan önce kullanıcı tarafından bir eylem gerektirecek şekilde bu üye işlevini geçersiz kılın.

## <a name="cdocumentremovechunk"></a><a name="removechunk"></a>Kdocument::RemoveChunk

Belirtilen GUID ile bir öbek kaldırır.

```
virtual void RemoveChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Parametreler

*Guıd*<br/>
Kaldırılacak bir yığının GUID'sini belirtir.

*Pıd*<br/>
Kaldırılacak bir yığının PID'sini belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentremoveview"></a><a name="removeview"></a>Kdocument::RemoveView

Bir belgeden görünümü ayırmak için bu işlevi çağırın.

```cpp
void RemoveView(CView* pView);
```

### <a name="parameters"></a>Parametreler

*pGörünüm*<br/>
Görünümün kaldırıldığını işaret eden.

### <a name="remarks"></a>Açıklamalar

Bu işlev, belirtilen görünümü belgeyle ilişkili görünümler listesinden kaldırır; ayrıca görünümün belge işaretçisini NULL olarak ayarlar. Çerçeve penceresi kapatıldığında veya ayırıcı penceresinin bölmesi kapatıldığında bu işlev çerçeve tarafından çağrılır.

Yalnızca bir görünümü el ile ayırıyorsanız bu işlevi arayın. Genellikle, bir belge sınıfını, görünüm sınıfını ve çerçeve pencere sınıfını ilişkilendirmek için bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesi tanımlayarak çerçevenin belgeleri ve görünümleri ayırmasına izin verebilirsiniz.

Örnek bir uygulama için [AddView'deki](#addview) örneğe bakın.

## <a name="cdocumentreportsaveloadexception"></a><a name="reportsaveloadexception"></a>Kdocument::ReportSaveLoadException

Belgeyi kaydederken veya yüklerken bir özel durum (genellikle [CFileException](../../mfc/reference/cfileexception-class.md) veya [CArchiveException)](../../mfc/reference/carchiveexception-class.md)atılırsa çağrılır.

```
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,
    CException* e,
    BOOL bSaving,
    UINT nIDPDefault);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Kaydedilen veya yüklenen belgenin adını işaret eden noktalar.

*E*<br/>
Atılan özel durum işaret. NULL olabilir.

*bTasarruf*<br/>
Hangi işlemin devam ettiğini belirten bayrak; belge kaydediliyorsa sıfırdan, belge yükleniyorsa 0.

*nIDPVarsayılan*<br/>
İşlev daha spesifik bir ileti belirtmiyorsa görüntülenecek hata iletisinin tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama özel durum nesnesini inceler ve özellikle nedenini açıklayan bir hata iletisi arar. Belirli bir ileti bulunamazsa veya *e* NULL ise, *nIDPDefault* parametresi tarafından belirtilen genel ileti kullanılır. İşlev daha sonra hata iletisini içeren bir ileti kutusu görüntüler. Ek, özelleştirilmiş hata iletileri sağlamak istiyorsanız bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz.

## <a name="cdocumentsavemodified"></a><a name="savemodified"></a>Kdocument::SaveModified

Değiştirilen bir belge kapatılmadan önce çerçeve tarafından çağrılır.

```
virtual BOOL SaveModified();
```

### <a name="return-value"></a>Dönüş Değeri

Belgeyi devam etmek ve kapatmak güvenliyse sıfıra inme; Belge kapatılmazsa 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması, kullanıcıya belgedeki değişiklikleri kaydedip kaydetmemesini isteyen bir ileti kutusu görüntüler. Programınız farklı bir istek yordamı gerektiriyorsa bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz.

## <a name="cdocumentsetchunkvalue"></a><a name="setchunkvalue"></a>Kdocument::SetChunkValue

Bir yığın değeri ayarlar.

```
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Parametreler

*pDeğer*<br/>
Ayarlamak için bir yığın değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

## <a name="cdocumentsetmodifiedflag"></a><a name="setmodifiedflag"></a>Kdocument::SetModifiedFlag

Belgede herhangi bir değişiklik yaptıktan sonra bu işlevi arayın.

```
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Parametreler

*bModideğişiklik*<br/>
Belgenin değiştirilip değiştirilmediğini belirten bayrak.

### <a name="remarks"></a>Açıklamalar

Bu işlevi tutarlı bir şekilde çağırarak, çerçevenin bir belgeyi kapatmadan önce kullanıcıdan değişiklikleri kaydetmesini ister. Genellikle *bModiparametresi* için TRUE varsayılan değerini kullanmanız gerekir. Bir belgeyi temiz (değiştirilmemiş) olarak işaretlemek için, bu işlevi FALSE değeriyle çağırın.

## <a name="cdocumentsetpathname"></a><a name="setpathname"></a>Kdocument::SetPathName

Belgenin disk dosyasının tam nitelikli yolunu belirtmek için bu işlevi arayın.

```
virtual void SetPathName(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Belgenin yolu olarak kullanılacak dizeyi işaret edin.

*bAddToMRU*<br/>
Dosya adının en son kullanılan (MRU) dosya listesine eklenip eklenmediğini belirler. TRUE ise, dosya adı eklenir; FALSE ise, eklenmez.

### <a name="remarks"></a>Açıklamalar

*bAddToMRU* değerine bağlı olarak yol, uygulama tarafından tutulan MRU listesine eklenir veya eklenmez. Bazı belgelerin bir disk dosyasıyla ilişkili olmadığını unutmayın. Yalnızca çerçeve tarafından kullanılan dosyaları açmak ve kaydetmek için varsayılan uygulamayı geçersiz kılıyorsanız bu işlevi arayın.

## <a name="cdocumentsettitle"></a><a name="settitle"></a>Kkişnasyon::SetTitle

Belgenin başlığını (çerçeve penceresinin başlık çubuğunda görüntülenen dize) belirtmek için bu işlevi arayın.

```
virtual void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Parametreler

*lpszTitle*<br/>
Belgenin başlığı olarak kullanılacak dizeyi işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmak, belgeyi görüntüleyen tüm çerçeve pencerelerinin başlıklarını güncelleştirir.

## <a name="cdocumentupdateallviews"></a><a name="updateallviews"></a>Kdocument::UpdateAllViews

Belge değiştirildikten sonra bu işlevi çağırın.

```cpp
void UpdateAllViews(
    CView* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL);
```

### <a name="parameters"></a>Parametreler

*pSender*<br/>
Belgeyi değiştiren görünüme veya tüm görünümler güncelleştirilecekse NULL'a işaret ediyor.

*Lhint*<br/>
Değişiklik hakkında bilgi içerir.

*pHint*<br/>
Değişiklik le ilgili bilgileri depolayan bir nesneyi işaret ediyor.

### <a name="remarks"></a>Açıklamalar

[SetModifiedFlag](#setmodifiedflag) üye işlevini aradıktan sonra bu işlevi aramalısınız. Bu işlev, *pSender*tarafından belirtilen görünüm dışında belgeye iliştirilen her görünümü, belgenin değiştirildiğini bildirir. Kullanıcı belgeyi bir görünüm üzerinden değiştirdikten sonra genellikle bu işlevi görünüm sınıfınızdan çağırırsınız.

Bu işlev [CView çağırır::OnUpdate](../../mfc/reference/cview-class.md#onupdate) üye işlevi gönderme görünümü dışında belgenin görünümleri her biri için, *pHint* ve *lHint*geçen . Belgede yapılan değişikliklerle ilgili görünümlere bilgi aktarmak için bu parametreleri kullanın. *LHint* kullanarak bilgileri kodlayabilir ve/veya değişiklikler hakkında bilgi depolamak ve *pHint*kullanarak o sınıfın bir nesnesini geçirmek için [CObject](../../mfc/reference/cobject-class.md)türetilmiş bir sınıf tanımlayabilirsiniz. [CView](../../mfc/reference/cview-class.md) `CView::OnUpdate` türetilmiş sınıfınızdaki üye işlevini geçersiz kılın ve geçirilen bilgilere göre görünümün görünümünün güncelleştirilmesini en iyi duruma getirin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek NPP](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)
