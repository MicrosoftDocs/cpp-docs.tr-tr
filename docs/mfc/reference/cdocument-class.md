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
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856767"
---
# <a name="cdocument-class"></a>CDocument sınıfı

Kullanıcı tanımlı belge sınıfları için temel işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CDocument : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDocument:: CDocument](#cdocument)|`CDocument` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDocument:: AddView](#addview)|Belgeye bir görünüm ekler.|
|[CDocument:: Beginreadöbekleri](#beginreadchunks)|Öbek okumayı başlatır.|
|[CDocument:: CanCloseFrame](#cancloseframe)|Gelişmiş geçersiz kılınabilir; Bu belgeyi görüntüleyen bir çerçeve penceresi kapatılmadan önce çağırılır.|
|[CDocument:: Cletcunklist](#clearchunklist)|Öbek listesini temizler.|
|[CDocument:: ClearPathName](#clearpathname)|Belge nesnesinin yolunu temizler.|
|[CDocument::D eleteContents](#deletecontents)|Belgeyi temizleme işlemini gerçekleştirmek için çağırılır.|
|[CDocument:: FindChunk](#findchunk)|Belirtilen GUID 'e sahip bir öbek arar.|
|[CDocument:: GetAdapter](#getadapter)|`IDocument` arabirimini uygulayan nesneye bir işaretçi döndürür.|
|[CDocument:: GetDocTemplate](#getdoctemplate)|Belge şablonuna belgenin türünü açıklayan bir işaretçi döndürür.|
|[CDocument:: GetFile](#getfile)|İstenen `CFile` nesnesine bir işaretçi döndürür.|
|[CDocument:: GetFirstViewPosition](#getfirstviewposition)|Görünüm listesindeki ilk öğesinin konumunu döndürür; yinelemeye başlamak için kullanılır.|
|[CDocument:: GetNextView](#getnextview)|Belgeyle ilişkili görünümlerin listesi boyunca yinelenir.|
|[CDocument:: GetPathName](#getpathname)|Belgenin veri dosyasının yolunu döndürür.|
|[CDocument:: GetThumbnail](#getthumbnail)|Küçük resmi göstermek için küçük resim sağlayıcısı tarafından kullanılacak bir bit eşlem oluşturmak için çağırılır.|
|[CDocument:: GetTitle](#gettitle)|Belgenin başlığını döndürür.|
|[CDocument:: ınitializesearchcontent](#initializesearchcontent)|Arama Işleyicisi için arama içeriğini başlatmak üzere çağırılır.|
|[CDocument:: IsModified](#ismodified)|Belgenin son kaydedduğundan bu yana değiştirilip değiştirilmediğini belirtir.|
|[CDocument:: IsSearchAndOrganizeHandler](#issearchandorganizehandler)|`CDocument` nesnesinin bu örneğinin arama & düzenleme işleyicisi için oluşturulup oluşturulmayacağını söyler.|
|[CDocument:: Loadbelgetfromstream](#loaddocumentfromstream)|Akıştan belge verilerini yüklemek için çağırılır.|
|[CDocument:: OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|Zengin Önizleme yazı tipi değiştirilmeden önce çağırılır.|
|[CDocument:: OnChangedViewList](#onchangedviewlist)|Belgeye bir görünüm eklendikten veya belgeden kaldırıldıktan sonra çağırılır.|
|[CDocument:: OnCloseDocument](#onclosedocument)|Belgeyi kapatmak için çağırılır.|
|[CDocument:: Oncreateönizleme çerçevesi](#oncreatepreviewframe)|Zengin Önizleme için bir önizleme çerçevesi oluşturması gerektiğinde Framework tarafından çağırılır.|
|[CDocument:: OnDocumentEvent](#ondocumentevent)|Bir belge olayına yanıt olarak Framework tarafından çağırılır.|
|[CDocument:: OnDrawThumbnail](#ondrawthumbnail)|Küçük resmin içeriğini çizmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.|
|[CDocument:: Onloadbelgetfromstream](#onloaddocumentfromstream)|Akıştan belge verilerini yüklemesi gerektiğinde Framework tarafından çağırılır.|
|[CDocument:: OnNewDocument](#onnewdocument)|Yeni bir belge oluşturmak için çağırılır.|
|[CDocument:: OnOpenDocument](#onopendocument)|Mevcut bir belgeyi açmak için çağırılır.|
|[CDocument:: OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|, GetFocus Işlevini çağırarak HWND 'yi döndürecek şekilde önizleme işleyicisini yönlendirir.|
|[CDocument:: OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|Önizleme işleyicisini, önizleme işleyicisinin çalıştığı işlemin ileti göndericiden geçen bir tuş vuruşunu işleyecek şekilde yönlendirir.|
|[CDocument:: Onrichönizleme BackColorChanged](#onrichpreviewbackcolorchanged)|Zengin Önizleme arka plan rengi değiştiğinde çağırılır.|
|[CDocument:: Onrichönizleme FontChanged](#onrichpreviewfontchanged)|Zengin Önizleme yazı tipi değiştiğinde çağırılır.|
|[CDocument:: Onrichönizlemesi Sitedeğişti](#onrichpreviewsitechanged)|Zengin Önizleme sitesi değiştirildiğinde çağırılır.|
|[CDocument:: Onrichönizlemesi Textcolorchanged](#onrichpreviewtextcolorchanged)|Zengin Önizleme metin rengi değiştiğinde çağırılır.|
|[CDocument:: OnSaveDocument](#onsavedocument)|Belgeyi diske kaydetmek için çağırılır.|
|[CDocument:: OnUnloadHandler](#onunloadhandler)|Önizleme işleyicisi kaldırıldığında Framework tarafından çağırılır.|
|[CDocument::P reCloseFrame](#precloseframe)|Çerçeve penceresi kapatılmadan önce çağırılır.|
|[CDocument:: ReadNextChunkValue](#readnextchunkvalue)|Sonraki öbek değerini okur.|
|[CDocument:: ReleaseFile](#releasefile)|Diğer uygulamalar tarafından kullanılabilir hale getirmek için bir dosya yayınlar.|
|[CDocument:: Removeöbek](#removechunk)|Belirtilen GUID 'e sahip bir öbeği kaldırır.|
|[CDocument:: RemoveView](#removeview)|Belgeden bir görünümü ayırır.|
|[CDocument:: ReportSaveLoadException](#reportsaveloadexception)|Gelişmiş geçersiz kılınabilir; bir özel durum nedeniyle açık veya kaydetme işlemi tamamlanamadığından çağırılır.|
|[CDocument:: SaveModified](#savemodified)|Gelişmiş geçersiz kılınabilir; kullanıcının belgenin kaydedilip edilmeyeceğini sormak için çağırılır.|
|[CDocument:: SetChunkValue](#setchunkvalue)|Bir öbek değeri ayarlar.|
|[CDocument:: SetModifiedFlag](#setmodifiedflag)|Belgeyi son kaydedildiğinden beri değiştirmeyeceğinizi belirten bir bayrak ayarlar.|
|[CDocument:: SetPathName](#setpathname)|Belge tarafından kullanılan veri dosyasının yolunu ayarlar.|
|[CDocument:: SetTitle](#settitle)|Belgenin başlığını ayarlar.|
|[CDocument:: UpdateAllViews](#updateallviews)|Belgenin değiştirildiği tüm görünümlere bildirir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDocument:: OnFileSendMail](#onfilesendmail)|Belge ekli olarak bir posta iletisi gönderir.|
|[CDocument:: OnUpdateFileSendMail](#onupdatefilesendmail)|Posta desteği varsa posta Gönder komutunu da sunar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDocument:: m_bGetThumbnailMode](#m_bgetthumbnailmode)|`CDocument` nesnesinin küçük resimler için Dllhost tarafından oluşturulduğunu belirtir. `CView::OnDraw`iade edilmelidir.|
|[CDocument:: m_bPreviewHandlerMode](#m_bpreviewhandlermode)|`Rich Preview`için `CDocument` nesnesinin prevhost tarafından oluşturulduğunu belirtir. `CView::OnDraw`iade edilmelidir.|
|[CDocument:: m_bSearchMode](#m_bsearchmode)|`CDocument` nesnesinin dizin oluşturucu ya da başka bir arama uygulaması tarafından oluşturulduğunu belirtir.|
|[CDocument:: m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Zengin Önizleme penceresinin arka plan rengini belirtir. Bu renk, ana bilgisayar tarafından ayarlanır.|
|[CDocument:: m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Zengin Önizleme penceresinin ön plan rengini belirtir. Bu renk, ana bilgisayar tarafından ayarlanır.|
|[CDocument:: m_lfRichPreviewFont](#m_lfrichpreviewfont)|Zengin Önizleme penceresi için metin yazı tipini belirtir. Bu yazı tipi bilgileri ana bilgisayar tarafından ayarlanır.|

## <a name="remarks"></a>Açıklamalar

Belge, kullanıcının dosya Aç komutuyla genellikle açtığı ve dosya Kaydet komutuyla kaydettiği veri birimini temsil eder.

`CDocument`, belge oluşturma, yükleme ve kaydetme gibi standart işlemleri destekler. Framework, `CDocument`tarafından tanımlanan arabirimi kullanarak belgeleri yönetir.

Uygulama, birden fazla belge türünü destekleyebilir; Örneğin, bir uygulama hem elektronik tabloları hem de metin belgelerini destekleyebilir. Her belge türünün ilişkili bir belge şablonu vardır; belge şablonu, bu tür belgeler için hangi kaynakların (örneğin, menü, simge veya Hızlandırıcı tablosu) kullanıldığını belirtir. Her belge, ilişkili `CDocTemplate` nesnesine bir işaretçi içerir.

Kullanıcılar, ile ilişkili [CView](../../mfc/reference/cview-class.md) nesneleri aracılığıyla bir belge ile etkileşime geçer. Bir görünüm, bir çerçeve penceresinde belgenin bir görüntüsünü oluşturur ve Kullanıcı girişini belgedeki işlemler olarak yorumlar. Bir belgede kendisiyle ilişkili birden çok görünüm bulunabilir. Kullanıcı bir belge üzerinde bir pencere açtığında, çerçeve bir görünüm oluşturur ve belgeye iliştirir. Belge şablonu, her belge türünü görüntülemek için ne tür bir görünüm ve çerçeve penceresi kullanıldığını belirtir.

Belgeler, çerçevenin standart komut yönlendirmenin bir parçasıdır ve sonuç olarak standart Kullanıcı arabirimi bileşenlerinden (Dosya Kaydet menü öğesi gibi) komutlar alın. Bir belge, etkin görünüm tarafından iletilen komutları alır. Belge belirli bir komutu işlemezse, komutu onu yöneten belge şablonuna iletir.

Bir belgenin verileri değiştirildiğinde, görünümlerinin her birinin bu değişiklikleri yansıtması gerekir. `CDocument`, bu değişikliklerin görünümlerine bildirimde bulunabilmeniz için [UpdateAllViews](#updateallviews) üye işlevini sağlar, böylece görünümler gerektiğinde bunları yeniden düzenleyebilir. Çerçeve ayrıca kullanıcıdan kapatmadan önce değiştirilen bir dosyayı kaydetmesini ister.

Belgeleri tipik bir uygulamada uygulamak için aşağıdakileri yapmanız gerekir:

- Her belge türü için `CDocument` bir sınıf türet.

- Her belgenin verilerini depolamak için üye değişkenleri ekleyin.

- Belge verilerini okumak ve değiştirmek için üye işlevlerini uygulayın. Belgenin görünümleri, bu üye işlevlerinin en önemli kullanıcılardır.

- Belge sınıfınızdan [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) üye işlevini geçersiz kılarak belgeye ve diskten verileri yazın ve diske okuyun.

`CDocument`, posta desteği (MAPI) varsa belgenizin posta aracılığıyla gönderilmesini destekler. MFC 'de [MAPI](../../mfc/mapi.md) ve [MAPI desteği](../../mfc/mapi-support-in-mfc.md)makalesine bakın.

`CDocument`hakkında daha fazla bilgi için bkz. [serileştirme](../../mfc/serialization-in-mfc.md), [belge/görünüm mimarisi konuları](../../mfc/document-view-architecture.md)ve [belge/görünüm oluşturma](../../mfc/document-view-creation.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocument`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="addview"></a>CDocument:: AddView

Belgeye bir görünüm iliştirmek için bu işlevi çağırın.

```
void AddView(CView* pView);
```

### <a name="parameters"></a>Parametreler

*pView*<br/>
Eklenmekte olan görünümü işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlev, belirtilen görünümü belgeyle ilişkili görünümler listesine ekler; işlev Ayrıca görünümün belge işaretçisini bu belgeye ayarlar. Çerçeve, yeni oluşturulan bir görünüm nesnesini bir belgeye eklerken bu işlevi çağırır; Bu, dosya yeni, dosya aç veya yeni pencere komutuna veya bir ayırıcı pencere bölündüğünde yanıt olarak oluşur.

Bu işlevi yalnızca bir görünümü el ile oluşturup eklerken çağırın. Genellikle bir belge sınıfını, görünüm sınıfını ve çerçeve pencere sınıfını ilişkilendirmek için bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesi tanımlayarak, çerçeveye belge ve Görünüm bağlama izni verirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]

##  <a name="beginreadchunks"></a>CDocument:: Beginreadöbekleri

Öbek okumayı başlatır.

```
virtual void BeginReadChunks ();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="cancloseframe"></a>CDocument:: CanCloseFrame

Belgeyi görüntüleyen bir çerçeve penceresi kapatılmadan önce Framework tarafından çağırılır.

```
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Parametreler

*pFrame*<br/>
Belgeye bağlı bir görünümün çerçeve penceresine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Çerçeve penceresini kapatmak güvenli ise sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, belgeyi görüntüleyen başka çerçeve pencereleri olup olmadığını denetler. Belirtilen çerçeve penceresi belgeyi görüntüleyen son bir ise, işlev değiştirildiğinde kullanıcıdan belgeyi kaydetmesini ister. Bir çerçeve penceresi kapalıyken özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz kılınabilir.

##  <a name="cdocument"></a>CDocument:: CDocument

`CDocument` nesnesi oluşturur.

```
CDocument();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, belge oluşturmayı sizin için işler. Belge temelinde başlatmayı gerçekleştirmek için [OnNewDocument](#onnewdocument) üye işlevini geçersiz kılın; Bu, özellikle tek belge arabirimi (SDI) uygulamalarında önemlidir.

##  <a name="clearchunklist"></a>CDocument:: Cletcunklist

Öbek listesini temizler.

```
virtual void ClearChunkList ();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="clearpathname"></a>CDocument:: ClearPathName

Belge nesnesinin yolunu temizler.

```
virtual void ClearPathName();
```

### <a name="remarks"></a>Açıklamalar

`CDocument` nesnesinden yol temizleme, uygulamanın belge bir sonraki kaydedildiğinde kullanıcıya sormasını sağlar. Bu, bir **Kaydet** komutunun **farklı kaydet** komutu gibi davranmasına neden olur.

##  <a name="deletecontents"></a>CDocument::D eleteContents

`CDocument` nesnenin kendisini yok etmeden belgenin verilerini silmek için Framework tarafından çağırılır.

```
virtual void DeleteContents();
```

### <a name="remarks"></a>Açıklamalar

Belge yok edileceği için hemen önce çağrılır. Yeniden kullanılmadan önce belgenin boş olduğundan emin olmak için de çağrılır. Bu, özellikle yalnızca bir belge kullanan SDI uygulaması için önemlidir; Kullanıcı başka bir belge oluşturduğunda veya açtığında belge yeniden kullanılır. Tüm belge verilerini silen "Tümünü Düzenle" veya benzer bir komut uygulamak için bu işlevi çağırın. Bu işlevin varsayılan uygulanması hiçbir şey yapmaz. Belgenizdeki verileri silmek için bu işlevi geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]

##  <a name="findchunk"></a>CDocument:: FindChunk

Belirtilen GUID 'e sahip bir öbek arar.

```
virtual POSITION FindChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Parametreler

*'ini*<br/>
Bulunacak öbekin GUID değerini belirtir.

*Kişisel*<br/>
Bulunacak öbekin PID 'sini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa iç öbek listesinin konumu. Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

##  <a name="getadapter"></a>CDocument:: GetAdapter

`IDocument` arabirimini uygulayan nesneye bir işaretçi döndürür.

```
virtual ATL::IDocument* GetAdapter();
```

### <a name="return-value"></a>Dönüş Değeri

`IDocument` arabirimini uygulayan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

##  <a name="getdoctemplate"></a>CDocument:: GetDocTemplate

Bu belge türü için belge şablonuna yönelik bir işaretçi almak için bu işlevi çağırın.

```
CDocTemplate* GetDocTemplate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu belge türü için belge şablonuna yönelik bir işaretçi veya belge bir belge şablonu tarafından yönetilmiyorsa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]

##  <a name="getfile"></a>CDocument:: GetFile

`CFile` nesnesine bir işaretçi almak için bu üye işlevi çağırın.

```
virtual CFile* GetFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
İstenen dosyanın yolu olan bir dize. Yol göreli veya mutlak olabilir.

*pError*<br/>
İşlemin tamamlanma durumunu belirten, var olan bir dosya özel durum nesnesine yönelik bir işaretçi.

*nOpenFlags*<br/>
Paylaşım ve erişim modu. Dosya açılırken gerçekleştirilecek eylemi belirtir. CFile Oluşturucu [CFile:: CFile](../../mfc/reference/cfile-class.md#cfile) içinde listelenen seçenekleri BIT düzeyinde OR (&#124;) işlecini kullanarak birleştirebilirsiniz. Bir erişim izni ve bir paylaşma seçeneği gereklidir; `modeCreate` ve `modeNoInherit` modları isteğe bağlıdır.

### <a name="return-value"></a>Dönüş Değeri

`CFile` nesnesine yönelik bir işaretçi.

##  <a name="getfirstviewposition"></a>CDocument:: GetFirstViewPosition

Belge ile ilişkili görünümler listesindeki ilk görünümün konumunu almak için bu işlevi çağırın.

```
virtual POSITION GetFirstViewPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

[GetNextView](#getnextview) üye işleviyle yineleme için KULLANıLABILEN bir konum değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="getnextview"></a>CDocument:: GetNextView

Belgenin tüm görünümlerini yinelemek için bu işlevi çağırın.

```
virtual CView* GetNextView(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*rPosition*<br/>
`GetNextView` veya [GetFirstViewPosition](#getfirstviewposition) üye işlevlerine yapılan bir çağrı tarafından döndürülen bir konum değerine başvuru. Bu değer NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

*RPosition*tarafından tanımlanan görünüme yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlevi, *rPosition* tarafından tanımlanan görünümü döndürür ve ardından listedeki bir sonrakı görünümün konum değerine *rPosition* değerini ayarlar. Alınan görünüm listedeki son ise *rPosition* değeri null olarak ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="getpathname"></a>CDocument:: GetPathName

Belgenin disk dosyasının tam yolunu almak için bu işlevi çağırın.

```
const CString& GetPathName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin tam yolu. Belge kaydedilmezse veya onunla ilişkili bir disk dosyası yoksa bu dize boştur.

##  <a name="getthumbnail"></a>CDocument:: GetThumbnail

Küçük resmi göstermek için küçük resim sağlayıcısı tarafından kullanılacak bir bit eşlem oluşturur.

```
virtual BOOL GetThumbnail(
    UINT cx,
    HBITMAP* phbmp,
    DWORD* pdwAlpha);
```

### <a name="parameters"></a>Parametreler

*yazmaç*<br/>
Bit eşlemin genişliğini ve yüksekliğini belirtir.

*phbmp*<br/>
İşlevin başarıyla döndürdüğü bir bit eşlem tanıtıcısı içerir.

*pdwAlpha*<br/>
İşlev başarıyla döndürüldüğünde alfa kanalı değerini belirten bir DWORD içerir.

### <a name="return-value"></a>Dönüş Değeri

Küçük resim için bir bit eşlem başarıyla oluşturulduysa TRUE değerini döndürür; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

##  <a name="gettitle"></a>CDocument:: GetTitle

Genellikle belgenin dosya adından türetilen belgenin başlığını almak için bu işlevi çağırın.

```
const CString& GetTitle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin başlığı.

##  <a name="initializesearchcontent"></a>CDocument:: ınitializesearchcontent

Arama Işleyicisi için arama içeriğini başlatmak üzere çağırılır.

```
virtual void InitializeSearchContent ();
```

### <a name="remarks"></a>Açıklamalar

Arama içeriğini başlatmak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın. İçerik, ";" ile ayrılmış parçalar içeren bir dize olmalıdır. Örneğin, "nokta; dikdörtgen ole öğesi ".

##  <a name="ismodified"></a>CDocument:: IsModified

Belgenin son kaydedduğundan bu yana değiştirilip değiştirilmediğini öğrenmek için bu işlevi çağırın.

```
virtual BOOL IsModified();
```

### <a name="return-value"></a>Dönüş Değeri

Belge son kaydedduğundan bu yana değiştirilmişse sıfır dışı; Aksi takdirde 0.

##  <a name="issearchandorganizehandler"></a>CDocument:: IsSearchAndOrganizeHandler

Bu `CDocument` örneğinin, arama & düzenleme işleyicisi için oluşturulup oluşturulmayacağını söyler.

```
BOOL IsSearchAndOrganizeHandler() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `CDocument` örneği, arama & düzenleme işleyicisi için oluşturulduysa TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Şu anda bu işlev, yalnızca işlem dışı bir sunucuda uygulanan zengin önizleme işleyicileri için TRUE değerini döndürür. Bu işlevin doğru döndürmesini sağlamak için uygulama düzeyinizde uygun bayrakları (m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode) ayarlayabilirsiniz.

##  <a name="loaddocumentfromstream"></a>CDocument:: Loadbelgetfromstream

Bir akıştan belge verilerini yüklemek için çağırılır.

```
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,
    DWORD dwGrfMode);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
Akış işaretçisi. Bu akış, kabuk tarafından sağlanır.

*dwGrfMode*<br/>
Akışa erişim modu.

### <a name="return-value"></a>Dönüş Değeri

Yükleme işlemi başarılı olursa S_OK, aksi takdirde HRESULT bir hata koduyla yapılır.

### <a name="remarks"></a>Açıklamalar

Akıştan veri yüklemeyi özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılabilirsiniz.

##  <a name="m_bgetthumbnailmode"></a>CDocument:: m_bGetThumbnailMode

`CDocument` nesnesinin küçük resimler için Dllhost tarafından oluşturulduğunu belirtir. `CView::OnDraw`iade edilmelidir.

```
BOOL m_bGetThumbnailMode;
```

### <a name="remarks"></a>Açıklamalar

`TRUE`, belgenin küçük resimler için Dllhost tarafından oluşturulduğunu gösterir.

##  <a name="m_bpreviewhandlermode"></a>CDocument:: m_bPreviewHandlerMode

`CDocument` nesnesinin zengin önizleme için prevhost tarafından oluşturulduğunu belirtir. `CView::OnDraw`iade edilmelidir.

```
BOOL m_bPreviewHandlerMode;
```

### <a name="remarks"></a>Açıklamalar

TRUE, belgenin zengin önizleme için prevhost tarafından oluşturulduğunu gösterir.

##  <a name="m_bsearchmode"></a>CDocument:: m_bSearchMode

`CDocument` nesnesinin Indexer veya başka bir arama uygulaması tarafından oluşturulduğunu belirtir.

```
BOOL m_bSearchMode;
```

### <a name="remarks"></a>Açıklamalar

`TRUE`, belgenin Dizin Oluşturucu ile veya başka bir arama uygulaması tarafından oluşturulduğunu gösterir.

##  <a name="m_clrrichpreviewbackcolor"></a>CDocument:: m_clrRichPreviewBackColor

Zengin Önizleme penceresinin arka plan rengini belirtir. Bu renk, ana bilgisayar tarafından ayarlanır.

```
COLORREF m_clrRichPreviewBackColor;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_clrrichpreviewtextcolor"></a>CDocument:: m_clrRichPreviewTextColor

Zengin Önizleme penceresinin ön plan rengini belirtir. Bu renk, ana bilgisayar tarafından ayarlanır.

```
COLORREF m_clrRichPreviewTextColor;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_lfrichpreviewfont"></a>CDocument:: m_lfRichPreviewFont

Zengin Önizleme penceresi için metin yazı tipini belirtir. Bu yazı tipi bilgileri ana bilgisayar tarafından ayarlanır.

```
CFont m_lfRichPreviewFont;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onbeforerichpreviewfontchanged"></a>CDocument:: OnBeforeRichPreviewFontChanged

Zengin Önizleme yazı tipi değiştirilmeden önce çağırılır.

```
virtual void OnBeforeRichPreviewFontChanged();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onchangedviewlist"></a>CDocument:: OnChangedViewList

Belgeye bir görünüm eklendikten veya belgeden kaldırıldıktan sonra Framework tarafından çağırılır.

```
virtual void OnChangedViewList();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması, son görünümün kaldırılıp kaldırılmadığını denetler ve varsa belgeyi siler. Framework bir görünüm eklediğinde veya kaldırırken özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Örneğin, kendisine ekli bir görünüm olmadığında bile belgenin açık kalmasını istiyorsanız, bu işlevi geçersiz kılın.

##  <a name="onclosedocument"></a>CDocument:: OnCloseDocument

Belge kapatıldığında, genellikle dosya Kapat komutunun bir parçası olarak, Framework tarafından çağırılır.

```
virtual void OnCloseDocument();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması, belgeyi görüntülemek için kullanılan tüm kareleri yok eder, görünümü kapatır, belgenin içeriğini temizler ve sonra belgenin verilerini silmek için [DeleteContents](#deletecontents) üye işlevini çağırır.

Çerçeve bir belgeyi kapattığında özel temizleme işlemi gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Örneğin, belge bir veritabanındaki kaydı temsil ediyorsa, veritabanını kapatmak için bu işlevi geçersiz kılmak isteyebilirsiniz. Geçersiz kılmanızda bu işlevin temel sınıf sürümünü çağırmalısınız.

##  <a name="oncreatepreviewframe"></a>CDocument:: Oncreateönizleme çerçevesi

Zengin Önizleme için bir önizleme çerçevesi oluşturması gerektiğinde Framework tarafından çağırılır.

```
virtual BOOL OnCreatePreviewFrame();
```

### <a name="return-value"></a>Dönüş Değeri

Çerçeve başarıyla oluşturulursa, doğru değerini döndürür; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondocumentevent"></a>CDocument:: OnDocumentEvent

Bir belge olayına yanıt olarak Framework tarafından çağırılır.

```
virtual void OnDocumentEvent(DocumentEvent deEvent);
```

### <a name="parameters"></a>Parametreler

*Etkinliği kaldırma*<br/>
'ndaki Olay türünü açıklayan bir numaralandırılmış veri türü.

### <a name="remarks"></a>Açıklamalar

Belge olayları, birden çok sınıfı etkileyebilir. Bu yöntem, [CDocument sınıfı](../../mfc/reference/cdocument-class.md)dışındaki sınıfları etkileyen belge olaylarını işlemekten sorumludur. Şu anda, belge olaylarına yanıt vermesi gereken tek sınıf [CDataRecoveryHandler sınıfıdır](../../mfc/reference/cdatarecoveryhandler-class.md). `CDocument` sınıfı, `CDocument`etkisini işlemekten sorumlu diğer geçersiz kılınabilir yöntemlere sahiptir.

Aşağıdaki tabloda, *deEvent* ve karşılık gelen olaylar için olası değerler listelenmiştir.

|Değer|Karşılık gelen olay|
|-----------|-------------------------|
|`onAfterNewDocument`|Yeni bir belge oluşturuldu.|
|`onAfterOpenDocument`|Yeni bir belge açıldı.|
|`onAfterSaveDocument`|Belge kaydedildi.|
|`onAfterCloseDocument`|Belge kapatıldı.|

##  <a name="ondrawthumbnail"></a>CDocument:: OnDrawThumbnail

Küçük resmi çizmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

```
virtual void OnDrawThumbnail(
    CDC& dc,
    LPRECT lprcBounds);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
Bir cihaz bağlamına başvuru.

*Lprcsınır*<br/>
Küçük resmin çizilmesi gereken alanın sınırlayıcı bir dikdörtgenini belirtir.

### <a name="remarks"></a>Açıklamalar

##  <a name="onfilesendmail"></a>CDocument:: OnFileSendMail

Belge eki olan yerleşik posta ana bilgisayarı (varsa) aracılığıyla bir ileti gönderir.

```
void OnFileSendMail();
```

### <a name="remarks"></a>Açıklamalar

`OnFileSendMail`, adsız ve değiştirilmiş belgeleri, daha sonra elektronik posta aracılığıyla gönderilen geçici bir dosyaya seri hale getirmek (kaydetmek) için [OnSaveDocument](#onsavedocument) öğesini çağırır. Belge değiştirilmediyse geçici bir dosya gerekmez; özgün değer gönderilir. `OnFileSendMail` MAPI32 yükler. DLL dosyası zaten yüklü değilse.

[Copadocument](../../mfc/reference/coledocument-class.md) için `OnFileSendMail` özel bir uygulama, bileşik dosyaları doğru bir şekilde işler.

`CDocument`, posta desteği (MAPI) varsa belgenizin posta aracılığıyla gönderilmesini destekler. MFC 'de [MAPI konuları](../../mfc/mapi.md) ve [MAPI desteği](../../mfc/mapi-support-in-mfc.md)makalelerine bakın.

##  <a name="onloaddocumentfromstream"></a>CDocument:: Onloadbelgetfromstream

Bir akıştan belge verilerini yüklemesi gerektiğinde Framework tarafından çağırılır.

```
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,
    DWORD grfMode);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
Gelen akış işaretçisi.

*grfMode*<br/>
Akışa erişim modu.

### <a name="return-value"></a>Dönüş Değeri

Yükleme başarılı olursa S_OK; Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

##  <a name="onnewdocument"></a>CDocument:: OnNewDocument

Dosya yeni komutunun bir parçası olarak Framework tarafından çağırılır.

```
virtual BOOL OnNewDocument();
```

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla başlatılmışsa sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması, belgenin boş olduğundan emin olmak için [DeleteContents](#deletecontents) üye işlevini çağırır ve sonra yeni belgeyi temiz olarak işaretler. Yeni bir belge için veri yapısını başlatmak üzere bu işlevi geçersiz kılın. Geçersiz kılmanızda bu işlevin temel sınıf sürümünü çağırmalısınız.

Kullanıcı bir SDI uygulamasında dosya yeni komutunu seçerse, çerçeve yeni bir tane oluşturmak yerine var olan belgeyi yeniden başlatmak için bu işlevi kullanır. Kullanıcı birden çok belge arabirimi (MDI) uygulamasında yeni dosya seçerse, çerçeve her seferinde yeni bir belge oluşturur ve sonra bunu başlatmak için bu işlevi çağırır. Başlangıç kodunuzu SDI uygulamalarında etkili olması için dosya yeni komutunun Oluşturucusu yerine bu işleve yerleştirmeniz gerekir.

`OnNewDocument` iki kez çağrıldığı durumlar olduğunu unutmayın. Bu, belge bir ActiveX belge sunucusu olarak katıştırıldığında oluşur. İşlev ilk olarak `CreateInstance` yöntemi tarafından çağrılır (`COleObjectFactory`tarafından türetilmiş sınıf tarafından gösterilir) ve ikinci kez `InitNew` yöntemi tarafından (`COleServerDoc`türetilmiş sınıf tarafından gösterilir).

### <a name="example"></a>Örnek

Aşağıdaki örneklerde, bir belge nesnesini başlatmak için alternatif yöntemler gösterilmektedir.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

##  <a name="onopendocument"></a>CDocument:: OnOpenDocument

Dosya Aç komutunun bir parçası olarak Framework tarafından çağırılır.

```
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Açılacak belgenin yolunu işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla yüklenmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulamasında belirtilen dosya açılır, belgenin boş olduğundan emin olmak için [DeleteContents](#deletecontents) üye işlevini çağırır, dosyanın içeriğini okumak için [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) çağırır ve sonra belgeyi temiz olarak işaretler. Arşiv mekanizması veya dosya mekanizması dışında bir şey kullanmak istiyorsanız bu işlevi geçersiz kılın. Örneğin, belgelerin ayrı dosyalar yerine veritabanındaki kayıtları temsil ettiği bir uygulama yazabilirsiniz.

Kullanıcı bir SDI uygulamasında Dosya Aç komutunu seçerse, çerçeve yeni bir tane oluşturmak yerine varolan `CDocument` nesnesini yeniden başlatmak için bu işlevi kullanır. Kullanıcı bir MDI uygulamasında dosya aç seçeneğini seçerse, çerçeve her seferinde yeni bir `CDocument` nesnesi oluşturur ve sonra bunu başlatmak için bu işlevi çağırır. Başlangıç kodunuzu, SDI uygulamalarında etkin olması için dosya aç komutunun Oluşturucusu yerine bu işleve yerleştirmeniz gerekir.

### <a name="example"></a>Örnek

Aşağıdaki örneklerde, bir belge nesnesini başlatmak için alternatif yöntemler gösterilmektedir.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

[!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]

##  <a name="onpreviewhandlerqueryfocus"></a>CDocument:: OnPreviewHandlerQueryFocus

Önizleme işleyicisini, `GetFocus` işlevini çağırarak alınan HWND 'yi döndürecek şekilde yönlendirir.

```
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```

### <a name="parameters"></a>Parametreler

*phwnd*<br/>
dışı Bu yöntem döndüğünde, önizleme işleyicisinin ön plan iş parçacığından `GetFocus` işlevini çağırarak döndürülen HWND için bir işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK döndürür; Aksi halde bir hata değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="onpreviewhandlertranslateaccelerator"></a>CDocument:: OnPreviewHandlerTranslateAccelerator

Önizleme işleyicisini, önizleme işleyicisinin çalıştığı işlemin ileti göndericiden geçen bir tuş vuruşunu işleyecek şekilde yönlendirir.

```
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
'ndaki Pencere iletisine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Tuş vuruşu iletisi önizleme işleyicisi tarafından işlenebiliyorsanız, işleyici onu işler ve S_OK döndürür. Önizleme İşleyicisi tuş vuruşu iletisini işleyemez, `IPreviewHandlerFrame::TranslateAccelerator`aracılığıyla ana bilgisayara sunar. Ana bilgisayar iletiyi işliyorsa, bu yöntem S_OK döndürür. Ana bilgisayar iletiyi işlemezse, bu yöntem S_FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="onrichpreviewbackcolorchanged"></a>CDocument:: Onrichönizleme BackColorChanged

Zengin Önizleme arka plan rengi değiştiğinde çağırılır.

```
virtual void OnRichPreviewBackColorChanged();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onrichpreviewfontchanged"></a>CDocument:: Onrichönizleme FontChanged

Zengin Önizleme yazı tipi değiştiğinde çağırılır.

```
virtual void OnRichPreviewFontChanged();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onrichpreviewsitechanged"></a>CDocument:: Onrichönizlemesi Sitedeğişti

Zengin Önizleme sitesi değiştirildiğinde çağırılır.

```
virtual void OnRichPreviewSiteChanged();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onrichpreviewtextcolorchanged"></a>CDocument:: Onrichönizlemesi Textcolorchanged

Zengin Önizleme metin rengi değiştiğinde çağırılır.

```
virtual void OnRichPreviewTextColorChanged();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onsavedocument"></a>CDocument:: OnSaveDocument

Dosya kaydetme veya dosya farklı Kaydet komutunun bir parçası olarak Framework tarafından çağırılır.

```
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Dosyanın kaydedilmesi gereken tam yolu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla kaydedildiyse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulamasında belirtilen dosya açılır, belge verilerini dosyaya yazmak için [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) çağırır ve sonra belgeyi temiz olarak işaretler. Çerçeve bir belge kaydettiğinde özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Örneğin, belgelerin ayrı dosyalar yerine veritabanındaki kayıtları temsil ettiği bir uygulama yazabilirsiniz.

##  <a name="onunloadhandler"></a>CDocument:: OnUnloadHandler

Önizleme işleyicisi kaldırıldığında Framework tarafından çağırılır.

```
virtual void OnUnloadHandler();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="onupdatefilesendmail"></a>CDocument:: OnUpdateFileSendMail

Posta desteği (MAPI) varsa ID_FILE_SEND_MAIL komutuna izin vermez.

```
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
ID_FILE_SEND_MAIL komutuyla ilişkili [CCmdUI](../../mfc/reference/ccmdui-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Aksi takdirde, işlev, menü öğesinin altındaki veya altındaki ayırıcılar dahil olmak üzere menüden ID_FILE_SEND_MAIL komutunu kaldırır. MAPI32 ise MAPI etkindir. DLL yolunda ve WIN 'nin [mail] bölümünde bulunur. INı dosyası, MAPI = 1. Çoğu uygulama bu komutu Dosya menüsüne koyar.

`CDocument`, posta desteği (MAPI) varsa belgenizin posta aracılığıyla gönderilmesini destekler. MFC 'de [MAPI konuları](../../mfc/mapi.md) ve [MAPI desteği](../../mfc/mapi-support-in-mfc.md)makalelerine bakın.

##  <a name="precloseframe"></a>CDocument::P reCloseFrame

Bu üye işlevi çerçeve penceresi yok edilmadan önce Framework tarafından çağırılır.

```
virtual void PreCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Parametreler

*pFrame*<br/>
İlişkili `CDocument` nesnesini tutan [CFrameWnd](../../mfc/reference/cframewnd-class.md) işaretçisi.

### <a name="remarks"></a>Açıklamalar

Özel temizlik sağlamak için geçersiz kılınabilir, ancak temel sınıfı da çağırdığınızdan emin olun.

`PreCloseFrame` varsayılan `CDocument`hiçbir şey yapmaz. `CDocument`türetilmiş sınıflar [Colet Document](../../mfc/reference/coledocument-class.md) ve [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) Bu üye işlevini kullanır.

##  <a name="readnextchunkvalue"></a>CDocument:: ReadNextChunkValue

Sonraki öbek değerini okur.

```
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```

### <a name="parameters"></a>Parametreler

*ppValue*<br/>
dışı İşlev döndüğünde, *ppValue* okunan değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="releasefile"></a>CDocument:: ReleaseFile

Bu üye işlevi, bir dosyayı serbest bırakmak ve diğer uygulamalar tarafından kullanılabilir hale getirmek için Framework tarafından çağırılır.

```
virtual void ReleaseFile(
    CFile* pFile,
    BOOL bAbort);
```

### <a name="parameters"></a>Parametreler

*pFile*<br/>
Yayımlanacak CFile nesnesine yönelik bir işaretçi.

*bAbort*<br/>
Dosyanın `CFile::Close` ya da `CFile::Abort`kullanılarak yayınlanıp yayınlanmayacağını belirtir. Dosya [CFile:: Close](../../mfc/reference/cfile-class.md#close)kullanılarak YAYıMLANACAKSA false. Dosya [CFile:: Abort](../../mfc/reference/cfile-class.md#abort)kullanılarak YAYıNLANACAKSA true.

### <a name="remarks"></a>Açıklamalar

*BAbort* true ise, `ReleaseFile` `CFile::Abort`çağırır ve dosya serbest bırakılır. `CFile::Abort`, özel durum oluşturmaz.

*BAbort* yanlış ise, `CFile::Close` `ReleaseFile` çağırır ve dosya serbest bırakılır.

Dosya yayınlanmadan önce Kullanıcı tarafından bir eylem gerektirecek şekilde bu üye işlevi geçersiz kılın.

##  <a name="removechunk"></a>CDocument:: Removeöbek

Belirtilen GUID 'e sahip bir öbeği kaldırır.

```
virtual void RemoveChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Parametreler

*'İni*<br/>
Kaldırılacak öbekin GUID değerini belirtir.

*Kişisel*<br/>
Kaldırılacak öbekin PID 'sini belirtir.

### <a name="remarks"></a>Açıklamalar

##  <a name="removeview"></a>CDocument:: RemoveView

Görünümü bir belgeden ayırmak için bu işlevi çağırın.

```
void RemoveView(CView* pView);
```

### <a name="parameters"></a>Parametreler

*pView*<br/>
Kaldırılmakta olan görünümü işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlev, belirtilen görünümü belgeyle ilişkili görünümler listesinden kaldırır; Ayrıca görünümün belge işaretçisini NULL olarak ayarlar. Bu işlev, çerçeve penceresi kapalıyken veya bir ayırıcı pencerenin bölmesi kapatıldığında çerçeve tarafından çağrılır.

Bu işlevi yalnızca bir görünümü el ile ayırdıysanız çağırın. Genellikle, bir belge sınıfını, görünüm sınıfını ve çerçeve pencere sınıfını ilişkilendirmek için bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) nesnesi tanımlayarak Framework 'ün belge ve görünümleri ayırmasına izin verirsiniz.

Örnek bir uygulama için bkz. [AddView](#addview) .

##  <a name="reportsaveloadexception"></a>CDocument:: ReportSaveLoadException

Belgeyi kaydederken veya yüklerken bir özel durum oluşturulursa (genellikle bir [CFileException](../../mfc/reference/cfileexception-class.md) veya [CArchiveException](../../mfc/reference/carchiveexception-class.md)) çağırılır.

```
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,
    CException* e,
    BOOL bSaving,
    UINT nIDPDefault);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Kaydedilmekte veya yüklenmekte olan belgenin adını gösterir.

*a*<br/>
Oluşturulan özel durumu işaret eder. NULL olabilir.

*Bkaydetme*<br/>
Sürmekte olan işlemleri belirten bayrak; Belge kaydediliyorsa sıfır dışında, belge yükleniyorsa 0.

*nIDPDefault*<br/>
İşlevin daha belirli bir tane belirtmediğinde görüntülenecek hata iletisinin tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama özel durum nesnesini inceler ve nedeni özellikle açıklayan bir hata mesajı arar. Belirli bir ileti bulunamazsa veya *e* null Ise, *nIDPDefault* parametresi tarafından belirtilen genel ileti kullanılır. Bu işlev daha sonra hata iletisini içeren bir ileti kutusu görüntüler. Ek, özelleştirilmiş hata iletileri sağlamak istiyorsanız bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz kılınabilir.

##  <a name="savemodified"></a>CDocument:: SaveModified

Değiştirilen bir belge kapatılmadan önce Framework tarafından çağırılır.

```
virtual BOOL SaveModified();
```

### <a name="return-value"></a>Dönüş Değeri

Devam etmek ve belgeyi kapatmak güvenli ise sıfır dışında. Belge kapatılmamalıdır 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulamasında, herhangi bir değişiklik yapıldıysa kullanıcıdan değişiklikleri belgeye kaydedilip edilmeyeceğini soran bir ileti kutusu görüntülenir. Programınız farklı bir istem prosedürü gerektiriyorsa bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz kılınabilir.

##  <a name="setchunkvalue"></a>CDocument:: SetChunkValue

Bir öbek değeri ayarlar.

```
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Parametreler

*pValue*<br/>
Ayarlanacak bir öbek değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="setmodifiedflag"></a>CDocument:: SetModifiedFlag

Belgede herhangi bir değişiklik yaptıktan sonra bu işlevi çağırın.

```
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Parametreler

*bModified*<br/>
Belgenin değiştirilip değiştirilmediğini belirten bayrak.

### <a name="remarks"></a>Açıklamalar

Bu işlevi sürekli çağırarak, Framework 'ün bir belgeyi kapatmadan önce kullanıcının değişiklikleri kaydetmesini istemdiğinden emin olursunuz. Genellikle, *bModified* PARAMETRESI için true varsayılan değerini kullanmalısınız. Bir belgeyi temiz (değiştirilmemiş) olarak işaretlemek için, bu işlevi FALSE değeriyle çağırın.

##  <a name="setpathname"></a>CDocument:: SetPathName

Belgenin disk dosyasının tam yolunu belirtmek için bu işlevi çağırın.

```
virtual void SetPathName(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszPathName*<br/>
Belge yolu olarak kullanılacak dizeyi işaret eder.

*bAddToMRU*<br/>
Dosya adının en son kullanılanlar (MRU) dosya listesine eklenip eklenmeyeceğini belirler. TRUE ise dosya adı eklenir; YANLıŞSA, eklenmez.

### <a name="remarks"></a>Açıklamalar

*BAddToMRU* değerine bağlı olarak yol, uygulama tarafından tutulan MRU listesine eklenir veya eklenmez. Bazı belgelerin bir disk dosyasıyla ilişkilendirilmediğini unutmayın. Bu işlevi yalnızca Framework tarafından kullanılan dosyaları açmak ve kaydetmek için varsayılan uygulamayı geçersiz kılıyorsa çağırın.

##  <a name="settitle"></a>CDocument:: SetTitle

Belgenin başlığını (bir çerçeve penceresinin başlık çubuğunda görünen dize) belirtmek için bu işlevi çağırın.

```
virtual void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Parametreler

*lpszTitle*<br/>
Belgenin başlığı olarak kullanılacak dizeyi işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmak, belgeyi görüntüleyen tüm çerçeve pencerelerinin başlıklarını güncelleştirir.

##  <a name="updateallviews"></a>CDocument:: UpdateAllViews

Belge değiştirildikten sonra bu işlevi çağırın.

```
void UpdateAllViews(
    CView* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL);
```

### <a name="parameters"></a>Parametreler

*pSender*<br/>
Belgeyi değiştiren görünümü işaret eder veya tüm görünümler güncelleniyorsa NULL olur.

*Lipucu*<br/>
Değişiklik hakkındaki bilgileri içerir.

*Phınt*<br/>
Değişiklik hakkında bilgi depolayan bir nesneye işaret eder.

### <a name="remarks"></a>Açıklamalar

[SetModifiedFlag](#setmodifiedflag) üye işlevini çağırdıktan sonra bu işlevi çağırmanız gerekir. Bu işlev, *pSender*tarafından belirtilen görünüm dışında belgenin değiştirildiği, belgeye eklenen her görünümü bilgilendirir. Genellikle bu işlevi, Kullanıcı belgeyi bir görünüm aracılığıyla değiştirdikten sonra Görünüm sınıfınızdan çağırabilirsiniz.

Bu işlev, gönderme görünümü dışındaki her belge görünümü için [CView:: OnUpdate](../../mfc/reference/cview-class.md#onupdate) üye işlevini çağırır ve *pHint* ve *lipucunu*geçirmektedir. Belgede yapılan değişikliklerle ilgili bilgileri görünümlere iletmek için bu parametreleri kullanın. *Lipucu* kullanarak bilgileri kodlayabilir ve/veya, bir [CObject](../../mfc/reference/cobject-class.md)ile türetilmiş sınıfı, değişiklikler hakkında bilgi depolamak ve *pHint*kullanarak bu sınıfın bir nesnesini geçirmek için tanımlayabilirsiniz. Geçirilen bilgilere göre görünümün görünümünün güncelleştirilmesini iyileştirmek için [CView](../../mfc/reference/cview-class.md)-türetilen sınıfınızın `CView::OnUpdate` üye işlevini geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDıDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek NPP](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)
