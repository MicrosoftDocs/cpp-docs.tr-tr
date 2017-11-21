---
title: "CDocument sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c6cfe4dc779fb4ad50f2171ef8811785f48275a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdocument-class"></a>CDocument sınıfı
Temel işlevleri için kullanıcı tanımlı belge sınıfları sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDocument : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocument::CDocument](#cdocument)|Oluşturan bir `CDocument` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocument::AddView](#addview)|Bir görünüm belgeye ekler.|  
|[CDocument::BeginReadChunks](#beginreadchunks)|Başlatır okuma öbek.|  
|[CDocument::CanCloseFrame](#cancloseframe)|Geçersiz kılınabilir Gelişmiş; Bu belge görüntüleme bir çerçeve penceresinde kapatmadan önce çağrılır.|  
|[CDocument::ClearChunkList](#clearchunklist)|Öbek listesini temizler.|  
|[CDocument::ClearPathName](#clearpathname)|Belge nesne yolunu temizler.|  
|[CDocument::DeleteContents](#deletecontents)|Belgenin temizlenmesini için çağrılır.|  
|[CDocument::FindChunk](#findchunk)|Belirtilen GUID'ye sahip bir öbek arar.|  
|[CDocument::GetAdapter](#getadapter)|Nesne uygulama için bir işaretçi döndüren `IDocument` arabirimi.|  
|[CDocument::GetDocTemplate](#getdoctemplate)|Bir işaretçi belge türünü tanımlayan belge şablonu döndürür.|  
|[CDocument::GetFile](#getfile)|İşaretçi istenen döndüren `CFile` nesnesi.|  
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|İlk konumunu döndürür; görünümlerinin listesinde Yineleme başlamak için kullanılır.|  
|[CDocument::GetNextView](#getnextview)|Belgeyle ilişkilendirilen görünümlerin listesi dolaşır.|  
|[CDocument::GetPathName](#getpathname)|Belgenin veri dosyasının yolunu döndürür.|  
|[CDocument::GetThumbnail](#getthumbnail)|Küçük resim görüntülemek için küçük resim sağlayıcısı tarafından kullanılacak bir bit eşlem oluşturmak için çağrılır.|  
|[CDocument::GetTitle](#gettitle)|Belgenin başlığı döndürür.|  
|[CDocument::InitializeSearchContent](#initializesearchcontent)|Arama içeriği için arama işleyicisi başlatmak için çağrılır.|  
|[CDocument::IsModified](#ismodified)|Son kaydedilişinden belgenin değiştirilmiş olup olmadığını gösterir.|  
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|Söyler olup, bu örneği `CDocument` nesnesi için arama & düzenleme işleyicisi oluşturuldu.|  
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|Belge verileri akışından yüklemek için çağrılır.|  
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|Zengin Önizleme yazı tipi değiştirilmeden önce çağrılır.|  
|[CDocument::OnChangedViewList](#onchangedviewlist)|Bir görünüm listeye eklenen veya belgeden çıkarılan sonra çağrılır.|  
|[CDocument::OnCloseDocument](#onclosedocument)|Belge kapatmak için çağrılır.|  
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|Önizleme çerçevesi Zengin Önizleme için oluşturun gerektiğinde çerçevesi tarafından çağrılır.|  
|[CDocument::OnDocumentEvent](#ondocumentevent)|Belge olaya yanıt olarak çerçevesi tarafından çağrılır.|  
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|Küçük resim içeriğini çizmek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.|  
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|Belge verileri akışından yükleme gerektiğinde çerçevesi tarafından çağrılır.|  
|[CDocument::OnNewDocument](#onnewdocument)|Yeni bir belge oluşturmak için çağrılır.|  
|[CDocument::OnOpenDocument](#onopendocument)|Var olan bir belgeyi açmak için çağrılır.|  
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|HWND tıklatma işlevini çağırma döndürmek için Önizleme işleyicisi yönlendirir.|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|Önizleme işleyicisi çalıştığı işlem ileti Pompalama aktarılabilir bir tuş vuruşu işlemek için Önizleme işleyicisi yönlendirir.|  
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|Zengin Önizleme arka plan rengi değiştirildiğinde çağrılır.|  
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|Zengin Önizleme yazı tipi değiştirildiğinde çağrılır.|  
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|Zengin Önizleme site değiştirildiğinde çağrılır.|  
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|Zengin Önizleme metin rengi değiştirildiğinde çağrılır.|  
|[CDocument::OnSaveDocument](#onsavedocument)|Belge diske kaydetmek için çağrılır.|  
|[CDocument::OnUnloadHandler](#onunloadhandler)|Önizleme işleyicisi kaldırıldığında çerçevesi tarafından çağrılır.|  
|[CDocument::PreCloseFrame](#precloseframe)|Çerçeve penceresi kapatılmadan önce çağrılır.|  
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|Sonraki öbek değerini okur.|  
|[CDocument::ReleaseFile](#releasefile)|Diğer uygulamalar tarafından kullanılmak üzere kullanılabilir hale getirmek için bir dosya serbest bırakır.|  
|[CDocument::RemoveChunk](#removechunk)|Belirtilen GUID'ye sahip bir öbek kaldırır.|  
|[CDocument::RemoveView](#removeview)|Belge görünümünden ayırır.|  
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|Geçersiz kılınabilir Gelişmiş; açık olduğunda çağrılır veya bir özel durum nedeniyle işlemi tamamlanamıyor.|  
|[CDocument::SaveModified](#savemodified)|Geçersiz kılınabilir Gelişmiş; kullanıcının belgeyi kaydedilip sormak için çağrılır.|  
|[CDocument::SetChunkValue](#setchunkvalue)|Öbek değerini ayarlar.|  
|[CDocument::SetModifiedFlag](#setmodifiedflag)|Son kaydedilişinden belge değiştirdiniz belirten bir bayrak ayarlar.|  
|[CDocument::SetPathName](#setpathname)|Belgenin tarafından kullanılan veri dosyasının yolunu ayarlar.|  
|[CDocument::SetTitle](#settitle)|Belgenin başlığı ayarlar.|  
|[CDocument::UpdateAllViews](#updateallviews)|Belge tüm görünümleri değiştirildi bildirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocument::OnFileSendMail](#onfilesendmail)|Bir posta iletisi belge ekli gönderir.|  
|[CDocument::OnUpdateFileSendMail](#onupdatefilesendmail)|Posta desteği mevcut değilse posta Gönder komutunu etkinleştirir.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|Belirleyen `CDocument` nesne küçük resimleri için dllhost tarafından oluşturuldu. Denetlenmesi `CView::OnDraw`.|  
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|Belirleyen `CDocument` nesne için prevhost tarafından oluşturulmuş `Rich Preview`. Denetlenmesi `CView::OnDraw`.|  
|[CDocument::m_bSearchMode](#m_bsearchmode)|Belirleyen `CDocument` nesne dizin oluşturucu veya diğer arama uygulaması tarafından oluşturuldu.|  
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Zengin Önizleme penceresinin arka plan rengini belirtir. Bu renk ana bilgisayar tarafından ayarlanır.|  
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Zengin Önizleme penceresi ön plan rengini belirtir. Bu renk ana bilgisayar tarafından ayarlanır.|  
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|Zengin Önizleme penceresi için metin yazı tipini belirtir. Bu yazı tipi bilgileri ana bilgisayar tarafından ayarlanır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir belge kullanıcı genellikle Dosya Aç komutu ile açar ve dosyayı kaydedin komutuyla kaydeden veri birimi temsil eder.  
  
 **CDocument** bir belge oluşturma, bunu yüklemek ve kaydederek gibi standart işlemlerini destekler. Framework tarafından tanımlanan arabirimi kullanarak belgeleri işleyen **CDocument**.  
  
 Bir uygulama birden fazla belge türünü destekler; Örneğin, bir uygulama, elektronik tablolar ve metin belgeleri desteklemiyor olabilir. Belge türlerinin ilişkili belge şablonu; yine de sahip istiyor musunuz? Belge şablonu, bu belge türü için hangi kaynakların (örneğin, menü, simge veya Hızlandırıcı tablosu) kullanıldığını belirtir. Her belge için ilişkili bir işaretçi içeriyor `CDocTemplate` nesnesi.  
  
 Kullanıcıların etkileşim bir belgeyle [CView](../../mfc/reference/cview-class.md) ilişkili nesne. Bir görünüm belgenin bir çerçeve penceresinde görüntüsünü oluşturur ve kullanıcı girişi belge üzerinde işlemler olarak yorumlar. Bir belge, kendisiyle ilişkili birden çok görünüm olabilir. Kullanıcı bir belge üzerinde bir penceresi açıldığında, framework bir görünüm oluşturur ve belgeye ekler. Belge şablonu ne tür bir görünüm ve çerçeve penceresi belge türlerinin görüntülemek için kullanılan belirtir.  
  
 Belgeleri framework'ün standart bir parçası olan komut Yönlendirme ve sonuç olarak komutları standart kullanıcı arabirimi bileşenleri (örneğin, dosyayı Kaydet menü öğesi) alacak. Bir belgeyi etkin görünüm tarafından iletilen komutları alır. Belge verilen komut işleyemez, yönettiği belge şablonu komutuna iletir.  
  
 Bir belgenin veri değiştirildiğinde, her görünümlerinin bu değişiklikleri yansıtması gerekir. **CDocument** sağlar [UpdateAllViews](#updateallviews) , görünümleri kendilerini gerektiği gibi yeniden boyamak şekilde bu değişiklikleri görünümlerini bildirmek üye işlevi. Çerçeve ayrıca kapatmadan önce değiştirilmiş bir dosya kaydetmek için kullanıcıya sorar.  
  
 Tipik bir uygulamada belgeleri uygulamak için aşağıdakileri yapmanız gerekir:  
  
-   Öğesinden bir sınıf türetin **CDocument** her belge türü için.  
  
-   Her bir belgenin verileri depolamak için üye değişkenleri ekleyin.  
  
-   Okuma ve belgenin verileri değiştirmek için üye işlevlerini uygular. Belgenin, bu üye işlevleri en önemli kullanıcılarının görünümlerdir.  
  
-   Geçersiz kılma [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) yazmak ve disk belgenin veri okumak için belge sınıfında üye işlevi.  
  
 **CDocument** posta desteği (MAPI) varsa, belgenizi posta aracılığıyla göndermeyi destekler. Makalelerine bakın [MAPI](../../mfc/mapi.md) ve [MFC içinde MAPI desteği](../../mfc/mapi-support-in-mfc.md).  
  
 Daha fazla bilgi için **CDocument**, bkz: [seri hale getirme](../../mfc/serialization-in-mfc.md), [belge/görünüm mimarisi konuları](../../mfc/document-view-architecture.md), ve [belge/görünüm oluşturma](../../mfc/document-view-creation.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="addview"></a>CDocument::AddView  
 Belgeye bir görünüm eklemek için bu işlevini çağırın.  
  
```  
void AddView(CView* pView);
```  
  
### <a name="parameters"></a>Parametreler  
 `pView`  
 Eklenmekte olan Görünüm noktalarına.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev belirtilen görünüm belgeyle ilişkilendirilen görünümler listesine ekler; işlevi de bu belgeye görünümün belge işaretçi ayarlar. Çerçeve, yeni oluşturulan Görünüm nesnesi bir belgeye eklerken bu işlevi çağırır; Bu dosya yeni, Dosya Aç veya yeni bir pencere komutu veya bir Bölümlendirici pencere böldüğünüzde yanıtta oluşur.  
  
 Bu işlev yalnızca el ile oluşturuyor ve bir görünüm ekleme çağırır. Belgeler ve görünümler tanımlayarak bağlanmak framework genellikle sağlayacak bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) bir belge sınıfı, görünüm sınıfı ve çerçeve pencere sınıfı ilişkilendirmek için nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]  
  
##  <a name="beginreadchunks"></a>CDocument::BeginReadChunks  
 Başlatır okuma öbek.  
  
```  
virtual void BeginReadChunks ();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cancloseframe"></a>CDocument::CanCloseFrame  
 Belge görüntüleyen bir çerçeve pencere kapatılmadan önce çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFrame`  
 Çerçeve penceresi noktalarına belgeye iliştirilmiş bir görünüm.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve penceresi kapatmak güvenli ise sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama, belgeyi görüntüleme diğer çerçeve pencereleri olup olmadığını denetler. Belirtilen çerçeve penceresi belgeyi görüntüler sonuncu ise, işlev, güncellendiyse belgeyi kaydetmek için kullanıcıya sorar. Çerçeve penceresi kapatıldığında özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar. Gelişmiş budur geçersiz kılınabilir.  
  
##  <a name="cdocument"></a>CDocument::CDocument  
 Oluşturan bir **CDocument** nesnesi.  
  
```  
CDocument();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Framework belge oluşturma sizin için işler. Geçersiz kılma [OnNewDocument](#onnewdocument) bir belge başına temelinde; başlatılmasını gerçekleştirmek için üye işlevi bu tek belge arabirimi (SDI) uygulamalarında özellikle önemlidir.  
  
##  <a name="clearchunklist"></a>CDocument::ClearChunkList  
 Öbek listesini temizler.  
  
```  
virtual void ClearChunkList ();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="clearpathname"></a>CDocument::ClearPathName  
 Belge nesne yolunu temizler.  
  
```  
virtual void ClearPathName();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yolundan temizleyerek bir `CDocument` nesne belge sonraki kaydedildiğinde kullanıcıdan uygulamaya neden olur. Böylece bir **kaydetmek** komutu davranır gibi bir **Kaydet** komutu.  
  
##  <a name="deletecontents"></a>CDocument::DeleteContents  
 Yok etme olmadan belgenin verilerini silmek için framework tarafından çağrılan **CDocument** nesnesinin kendisi.  
  
```  
virtual void DeleteContents();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca belge yok edilmesi için önce çağrılır. Ayrıca, yeniden kullanılmadan önce bir belge boş olduğundan emin olmak için de denir. Bu yalnızca bir belge kullanan bir SDI uygulama için özellikle önemlidir; Her kullanıcı oluşturur veya başka bir belge açılır belgeyi yeniden kullanılır. Bir "Düzenle Tümünü Temizle" veya belgenin verilerin tümünü siler benzer komutu uygulamak için bu işlevini çağırın. Bu işlev varsayılan uygulaması hiçbir şey yapmaz. Bu işlev, belgedeki verileri silmek için geçersiz kılar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]  
  
##  <a name="findchunk"></a>CDocument::FindChunk  
 Belirtilen GUID'ye sahip bir öbek arar.  
  
```  
virtual POSITION FindChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>Parametreler  
 `guid`  
 Bulmak için bir öbek GUİD'si belirtir.  
  
 `pid`  
 Bulmak için bir öbek PID belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa iç öbek listesindeki konumu. Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getadapter"></a>CDocument::GetAdapter  
 Uygulama nesnesi için bir işaretçi döndüren `IDocument` arabirimi.  
  
```  
virtual ATL::IDocument* GetAdapter();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir nesne uygulama için bir işaretçi `IDocument` arabirimi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getdoctemplate"></a>CDocument::GetDocTemplate  
 Bu belge türü için belge şablonu için bir işaretçi almak için bu işlevini çağırın.  
  
```  
CDocTemplate* GetDocTemplate() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu belge türü için belge şablonu için bir işaretçi veya **NULL** belgenin belge şablonu tarafından yönetilmiyorsa.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]  
  
##  <a name="getfile"></a>CDocument::GetFile  
 Bir işaretçi almak için bu üye işlevini çağırın bir `CFile` nesnesi.  
  
```  
virtual CFile* GetFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFileName`  
 İstenen dosyanın yolu olan bir dize. Yol, göreli veya mutlak olabilir.  
  
 `pError`  
 Bir işaretçi var olan bir dosya özel durumu nesneye işleminin tamamlanma durumunu gösteren.  
  
 `nOpenFlags`  
 Paylaşım ve erişim modu. Dosyayı açarken gerçekleştirilecek eylemi belirtir. CFile oluşturucuda listelenen seçenekleri birleştirebilirsiniz [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) bit düzeyinde OR (&#124;) kullanarak işleci. Bir erişim izni ve bir paylaşım seçeneği gereklidir; **modeCreate** ve **modeNoInherit** modları isteğe bağlıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CFile` nesnesi.  
  
##  <a name="getfirstviewposition"></a>CDocument::GetFirstViewPosition  
 Belgeyle ilişkilendirilen görünümlerinin listedeki ilk görünüm konumunu almak için bu işlevini çağırın.  
  
```  
virtual POSITION GetFirstViewPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** bir yineleme için kullanılan değeri [GetNextView](#getnextview) üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="getnextview"></a>CDocument::GetNextView  
 Tüm belgenin görünümleri yinelemek için bu işlevini çağırın.  
  
```  
virtual CView* GetNextView(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `rPosition`  
 Bir başvuru bir **konumu** önceki bir çağrı tarafından döndürülen değer `GetNextView` veya [GetFirstViewPosition](#getfirstviewposition) üye işlevleri. Bu değer olmamalıdır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından tanımlanan görünüm için bir işaretçi `rPosition`.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından tanımlanan görünüm işlevi döndürür `rPosition` ve ardından ayarlar `rPosition` için **konumu** listesinde sonraki görünüme değeri. Alınan Görünüm listesinde, son sonra olup olmadığını `rPosition` ayarlanır **NULL**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="getpathname"></a>CDocument::GetPathName  
 Belgenin disk dosyasının tam yolunu almak için bu işlevini çağırın.  
  
```  
const CString& GetPathName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belgenin tam yolu. Belge kaydedilmedi ya da ilişkili disk dosyası yok. Bu boş bir dizedir.  
  
##  <a name="getthumbnail"></a>CDocument::GetThumbnail  
 Küçük resim görüntülemek için küçük resim sağlayıcı tarafından kullanılacak bir bit eşlem oluşturur.  
  
```  
virtual BOOL GetThumbnail(
    UINT cx,  
    HBITMAP* phbmp,  
    DWORD* pdwAlpha);
```  
  
### <a name="parameters"></a>Parametreler  
 `cx`  
 Bit eşlem yüksekliğini ve genişliğini belirtir.  
  
 `phbmp`  
 İşlev başarıyla döndürüldüğünde bir bit eşlem için bir tanıtıcı içerir.  
  
 `pdwAlpha`  
 İşlev başarıyla geri döndüğünde alfa kanal değerini belirleyen bir DWORD içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` bir bit eşlem küçük resim oluşturulup oluşturulmadığını başarıyla; Aksi halde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettitle"></a>CDocument::GetTitle  
 Belgenin dosya adlarından genellikle türetilmiş belgenin başlığını almak için bu işlevini çağırın.  
  
```  
const CString& GetTitle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belgenin başlığı.  
  
##  <a name="initializesearchcontent"></a>CDocument::InitializeSearchContent  
 Arama içerik arama işleyicisi başlatmak üzere çağrılır.  
  
```  
virtual void InitializeSearchContent ();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Arama içeriği başlatmak için bir türetilmiş sınıfta bu yöntemi geçersiz kılın. İçerik virgülle ayrılan bölümleri içeren bir dize olmalıdır ";". Örneğin, "noktası; Dikdörtgen; OLE öğesi".  
  
##  <a name="ismodified"></a>CDocument::IsModified  
 Son kaydedilişinden belgenin değiştirilmiş olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
virtual BOOL IsModified();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Son kaydedilişinden belge güncellendiyse sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="issearchandorganizehandler"></a>CDocument::IsSearchAndOrganizeHandler  
 Söyler olup, bu örneği `CDocument` arama & düzenleme işleyicisi oluşturuldu.  
  
```  
BOOL IsSearchAndOrganizeHandler() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` varsa, bu örneği `CDocument` arama & düzenleme işleyicisi oluşturuldu.  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda bu işlevi döndürür `TRUE` dışı bir işlem sunucusu uygulanan Zengin Önizleme işleyicileri için. Bu işlev dönmesi için uygulama düzeyinde uygun bayrakları (m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode) ayarlayabilirsiniz `TRUE`.  
  
##  <a name="loaddocumentfromstream"></a>CDocument::LoadDocumentFromStream  
 Belge verileri bir akıştan yüklemek için çağrılır.  
  
```  
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,  
    DWORD dwGrfMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `pStream`  
 Bir akış için bir işaretçi. Bu akış Kabuk tarafından sağlanır.  
  
 `dwGrfMode`  
 Akış erişim modu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yükleme işlemi başarılı olursa, aksi takdirde HRESULT hata koduyla birlikte S_OK.  
  
### <a name="remarks"></a>Açıklamalar  
 Veriler akıştan yükleme özelleştirmek için bir türetilmiş sınıfta bu yöntemin üzerine yazabilir.  
  
##  <a name="m_bgetthumbnailmode"></a>CDocument::m_bGetThumbnailMode  
 Belirleyen `CDocument` nesne küçük resimleri için dllhost tarafından oluşturuldu. Denetlenmesi `CView::OnDraw`.  
  
```  
BOOL m_bGetThumbnailMode;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `TRUE`Belge küçük resimleri için dllhost tarafından oluşturulduğunu gösterir.  
  
##  <a name="m_bpreviewhandlermode"></a>CDocument::m_bPreviewHandlerMode  
 Belirleyen `CDocument` nesne için Zengin Önizleme prevhost tarafından oluşturuldu. Denetlenmesi `CView::OnDraw`.  
  
```  
BOOL m_bPreviewHandlerMode;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `TRUE`Belge için Zengin Önizleme prevhost tarafından oluşturulduğunu gösterir.  
  
##  <a name="m_bsearchmode"></a>CDocument::m_bSearchMode  
 Belirleyen `CDocument` nesne dizin oluşturucu veya başka bir arama uygulaması tarafından oluşturuldu.  
  
```  
BOOL m_bSearchMode;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `TRUE`Belge, dizin oluşturucu veya başka bir arama uygulaması tarafından oluşturulduğunu gösterir.  
  
##  <a name="m_clrrichpreviewbackcolor"></a>CDocument::m_clrRichPreviewBackColor  
 Zengin Önizleme penceresi arka plan rengini belirtir. Bu renk ana bilgisayar tarafından ayarlanır.  
  
```  
COLORREF m_clrRichPreviewBackColor;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_clrrichpreviewtextcolor"></a>CDocument::m_clrRichPreviewTextColor  
 Zengin Önizleme penceresi ön plan rengini belirtir. Bu renk ana bilgisayar tarafından ayarlanır.  
  
```  
COLORREF m_clrRichPreviewTextColor;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_lfrichpreviewfont"></a>CDocument::m_lfRichPreviewFont  
 Zengin Önizleme penceresi metin yazı tipini belirtir. Bu yazı tipi bilgileri ana bilgisayar tarafından ayarlanır.  
  
```  
CFont m_lfRichPreviewFont;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onbeforerichpreviewfontchanged"></a>CDocument::OnBeforeRichPreviewFontChanged  
 Zengin Önizleme yazı tipi değiştirilmeden önce çağrılır.  
  
```  
virtual void OnBeforeRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onchangedviewlist"></a>CDocument::OnChangedViewList  
 Bir görünüm listeye eklenen veya belgeden çıkarılan sonra çerçevesi tarafından çağrılır.  
  
```  
virtual void OnChangedViewList();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulaması son görünümü kaldırılıyor varsa, belge siler olup olmadığını denetler ve. Framework ekler veya bir görünüm kaldırdığında özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar. Örneğin, bir belgenin bağlı Görünüm olduğunda bile açık kalmasını istiyorsanız, bu işlev geçersiz kılar.  
  
##  <a name="onclosedocument"></a>CDocument::OnCloseDocument  
 Belge, genellikle Dosya Kapat komutunu bir parçası olarak kapatıldığı zaman çerçevesi tarafından çağrılır.  
  
```  
virtual void OnCloseDocument();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulaması tüm belgeyi görüntülemek için kullanılan çerçeve yok eder, görünüm kapatır, belgenin içeriği temizler ve ardından çağırır [DeleteContents](#deletecontents) belgenin silmek için üye işlevi veriler.  
  
 Çerçeve bir belge kapandığında özel temizleme işleme gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar. Örneğin, bir veritabanındaki bir kaydı belgeyi temsil ediyorsa, veritabanını kapatmak için bu işlevi geçersiz isteyebilirsiniz. Bu işlev temel sınıf sürümü geçersiz kılma çağırmalıdır.  
  
##  <a name="oncreatepreviewframe"></a>CDocument::OnCreatePreviewFrame  
 Önizleme çerçevesi Zengin Önizleme için oluşturun gerektiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnCreatePreviewFrame();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` çerçeve oluşturduysanız, başarılı bir şekilde; Aksi halde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondocumentevent"></a>CDocument::OnDocumentEvent  
 Belge olaya yanıt olarak çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDocumentEvent(DocumentEvent deEvent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`deEvent`  
 Olay türünü tanımlayan bir numaralandırılmış veri türü.  
  
### <a name="remarks"></a>Açıklamalar  
 Belge olaylarını birden çok sınıf etkileyebilir. Bu yöntem dışında sınıfları etkileyen belge olayları işlemekten sorumludur [CDocument sınıfı](../../mfc/reference/cdocument-class.md). Şu anda, belge olaylarına yanıt vermesi gereken tek sınıf olan [CDataRecoveryHandler sınıfı](../../mfc/reference/cdatarecoveryhandler-class.md). `CDocument` Sınıfına sahip diğer geçersiz kılınabilir yöntemleri üzerinde etkisi işlenmesinden sorumludur `CDocument`.  
  
 İçin olası değerler aşağıdaki tabloda listelenmektedir `deEvent` ve bunların karşılık gelen olayları.  
  
|Değer|Karşılık gelen olay|  
|-----------|-------------------------|  
|`onAfterNewDocument`|Yeni bir belge oluşturuldu.|  
|`onAfterOpenDocument`|Yeni bir belge açıldı.|  
|`onAfterSaveDocument`|Belge kaydedildi.|  
|`onAfterCloseDocument`|Belge kapatıldı.|  
  
##  <a name="ondrawthumbnail"></a>CDocument::OnDrawThumbnail  
 Küçük resim çizmek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
```  
virtual void OnDrawThumbnail(
    CDC& dc,  
    LPRECT lprcBounds);
```  
  
### <a name="parameters"></a>Parametreler  
 `dc`  
 Bir cihaz bağlamı referansı.  
  
 `lprcBounds`  
 Küçük resim nerede çizileceğini alanının sınırlayıcı dikdörtgenini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onfilesendmail"></a>CDocument::OnFileSendMail  
 Yerleşik posta ana bilgisayar üzerinden bir ileti (varsa) belgeyle ek olarak gönderir.  
  
```  
void OnFileSendMail();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `OnFileSendMail`çağrıları [OnSaveDocument](#onsavedocument) (Kaydet) adsız ve değiştirilmiş belgeleri elektronik posta gönderilir geçici bir dosya için seri hale getirilemedi. Belge değiştirilmedi, geçici bir dosya gerekli değildir; özgün gönderilir. `OnFileSendMail`MAPI32 yükler. DLL zaten yüklü.  
  
 Özel bir uyarlamasını `OnFileSendMail` için [COleDocument](../../mfc/reference/coledocument-class.md) tanıtıcıları bileşik dosyaları doğru.  
  
 **CDocument** posta desteği (MAPI) varsa, belgenizi posta aracılığıyla göndermeyi destekler. Makalelerine bakın [MAPI konuları](../../mfc/mapi.md) ve [MFC içinde MAPI desteği](../../mfc/mapi-support-in-mfc.md).  
  
##  <a name="onloaddocumentfromstream"></a>CDocument::OnLoadDocumentFromStream  
 Belge verileri bir akıştan yükleme gerektiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,  
    DWORD grfMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `pStream`  
 Gelen bir akış için bir işaretçi.  
  
 `grfMode`  
 Akış erişim modu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yükleme başarılı olursa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onnewdocument"></a>CDocument::OnNewDocument  
 Dosya yeni komutun parçası olarak çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnNewDocument();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belge başarıyla başlatıldı, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulamasını çağıran [DeleteContents](#deletecontents) belgenin boş ve yeni belge temiz olarak işaretler emin olmak için üye işlevi. Yeni bir belge için veri yapısı başlatmak için bu işlevi geçersiz kılar. Bu işlev temel sınıf sürümü geçersiz kılma çağırmalıdır.  
  
 Kullanıcı bir SDI uygulamasında dosya yeni komutu seçerse çerçevesi yeni bir tane oluşturmak yerine var olan belgeyi yeniden başlatmak için bu işlevi kullanır. Kullanıcı dosya yeni bir birden çok belge arabirimi (MDI) uygulaması seçerse, framework her saat yeni bir belge oluşturur ve bunu başlatmak için bu işlevi çağırır. SDI uygulamaları etkili olması için dosya yeni komutu oluşturucuda yerine bu işlevde başlatma kodunuzu yerleştirmeniz gerekir.  
  
 Vardır Not durumlara `OnNewDocument` iki kez çağrılır. Bu durum, belgeyi bir ActiveX belge sunucusu olarak katıştırılır oluşur. İşlev ilk çağrılan `CreateInstance` yöntemi (tarafından sunulan `COleObjectFactory`-türetilmiş sınıf) ve ikinci kez tarafından `InitNew` yöntemi (tarafından sunulan `COleServerDoc`-türetilmiş sınıf).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekler bir belge nesnesi başlatılırken alternatif yöntemleri gösterir.  
  
 [!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
##  <a name="onopendocument"></a>CDocument::OnOpenDocument  
 Dosya Aç komutu bir parçası olarak çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszPathName`  
 Açılacak belgenin noktaları yolu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belge başarıyla yüklendiyse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen dosya, çağrıları bu işlev varsayılan uygulaması açılır [DeleteContents](#deletecontents) belge boş olduğundan emin olmak için üye işlevi çağırır [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) dosyanın okumak için içeriği ve sonra belgeyi temiz olarak işaretler. Arşiv mekanizması veya dosya mekanizması dışında bir şey kullanmak istiyorsanız, bu işlev geçersiz kılar. Örneğin, burada belgeleri ayrı dosyalar yerine bir veritabanı kayıtları temsil bir uygulama yazabilirsiniz.  
  
 Kullanıcı bir SDI uygulamasında Dosya Aç komutu seçerse, çerçeve varolan yeniden başlatmak için bu işlevi kullanır **CDocument** yeni bir tane oluşturmak yerine nesne. Kullanıcı Dosya Aç MDI uygulamada seçerse, framework yeni yapıları **CDocument** nesne her zaman ve ardından başlatmak için bu işlevi çağırır. SDI uygulamaları etkili olması için Dosya Aç komutu oluşturucuda yerine bu işlevde başlatma kodunuzu yerleştirmeniz gerekir.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekler bir belge nesnesi başlatılırken alternatif yöntemleri gösterir.  
  
 [!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]  
  
##  <a name="onpreviewhandlerqueryfocus"></a>CDocument::OnPreviewHandlerQueryFocus  
 HWND arama öğesinden alınan döndürmek için Önizleme işleyicisi yönlendirir `GetFocus` işlevi.  
  
```  
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `phwnd`  
 [out] Bu yöntem döndürüldüğünde, arama öğesinden döndürülen HWND gösteren bir işaretçi içeriyor `GetFocus` Önizleme işleyicinin ön plan iş parçacığı işlevinden.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa; S_OK döndürür ya da aksi takdirde bir hata değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onpreviewhandlertranslateaccelerator"></a>CDocument::OnPreviewHandlerTranslateAccelerator  
 Önizleme işleyicisi çalıştığı işlem ileti Pompalama aktarılabilir bir tuş vuruşu işlemek için Önizleme işleyicisi yönlendirir.  
  
```  
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```  
  
### <a name="parameters"></a>Parametreler  
 `pmsg`  
 [in] Pencere iletisi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tuş vuruşu ileti Önizleme işleyici tarafından işlenebilir, işleyici işler ve S_OK döndürür. Önizleme işleyicisi tuş vuruşu iletiyi işleyemezse onu aracılığıyla konak sunduğu `IPreviewHandlerFrame::TranslateAccelerator`. Ana bilgisayar ileti işlediğinde, bu yöntem S_OK döndürür. Bu yöntem, ana bilgisayar iletiyi işlemezse S_FALSE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onrichpreviewbackcolorchanged"></a>CDocument::OnRichPreviewBackColorChanged  
 Zengin Önizleme arka plan rengi değiştirildiğinde çağrılır.  
  
```  
virtual void OnRichPreviewBackColorChanged();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onrichpreviewfontchanged"></a>CDocument::OnRichPreviewFontChanged  
 Zengin Önizleme yazı tipi değiştirildiğinde çağrılır.  
  
```  
virtual void OnRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onrichpreviewsitechanged"></a>CDocument::OnRichPreviewSiteChanged  
 Zengin Önizleme site değiştirildiğinde çağrılır.  
  
```  
virtual void OnRichPreviewSiteChanged();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onrichpreviewtextcolorchanged"></a>CDocument::OnRichPreviewTextColorChanged  
 Zengin Önizleme metin rengi değiştirildiğinde çağrılır.  
  
```  
virtual void OnRichPreviewTextColorChanged();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsavedocument"></a>CDocument::OnSaveDocument  
 Dosya dosyasını Kaydet veya komutun parçası olarak çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszPathName`  
 Dosyanın kaydedilmesi gereken tam nitelenmiş bir yol noktalarına.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belge başarıyla kaydedildi, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen dosya, çağrıları bu işlev varsayılan uygulaması açılır [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) belgenin veri yazmak için dosya ve ardından işaretleri belgesi olarak temizleyin. Framework belgeyi kaydettiğinde özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar. Örneğin, burada belgeleri ayrı dosyalar yerine bir veritabanı kayıtları temsil bir uygulama yazabilirsiniz.  
  
##  <a name="onunloadhandler"></a>CDocument::OnUnloadHandler  
 Önizleme işleyicisi kaldırıldığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnUnloadHandler();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onupdatefilesendmail"></a>CDocument::OnUpdateFileSendMail  
 Etkinleştirir **ID_FILE_SEND_MAIL** posta desteği (MAPI) yüklü olup olmadığını komutu.  
  
```  
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCmdUI`  
 Bir işaretçi [Ccmduı](../../mfc/reference/ccmdui-class.md) ilişkili nesne **ID_FILE_SEND_MAIL** komutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Aksi takdirde işlevi kaldırır **ID_FILE_SEND_MAIL** ayırıcılar yukarıdaki dahil olmak üzere menüsünden veya menü öğesi uygun şekilde altında komutu. MAPI etkin olmadığını MAPI32. DLL yolunda ve WIN [posta] bölümünde bulunur. INI dosyası, MAPI = 1. Uygulamaların çoğu bu komut dosyası menüsünde yerleştirin.  
  
 **CDocument** posta desteği (MAPI) varsa, belgenizi posta aracılığıyla göndermeyi destekler. Makalelerine bakın [MAPI konuları](../../mfc/mapi.md) ve [MFC içinde MAPI desteği](../../mfc/mapi-support-in-mfc.md).  
  
##  <a name="precloseframe"></a>CDocument::PreCloseFrame  
 Çerçeve penceresi yok önce bu üye işlev çerçevesi tarafından çağrılır.  
  
```  
virtual void PreCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFrame`  
 İşaretçi [CFrameWnd](../../mfc/reference/cframewnd-class.md) ilişkili tutan **CDocument** nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel temizleme sağlar, ancak temel sınıfı da çağırdığınızdan emin kılınabilir.  
  
 Varsayılan değer olan `PreCloseFrame` hiçbir şey yapmaz **CDocument**. **CDocument**-türetilmiş sınıfları [COleDocument](../../mfc/reference/coledocument-class.md) ve [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) bu üye işlevini kullanın.  
  
##  <a name="readnextchunkvalue"></a>CDocument::ReadNextChunkValue  
 Sonraki öbek değerini okur.  
  
```  
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppValue`  
 [out] İşlevi döndüğünde `ppValue` okundu değeri içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="releasefile"></a>CDocument::ReleaseFile  
 Bu üye işlevi, diğer uygulamalar tarafından kullanılabilir hale getirerek bir dosya yayımlamayı çerçevesi tarafından çağrılır.  
  
```  
virtual void ReleaseFile(
    CFile* pFile,  
    BOOL bAbort);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFile`  
 CFile nesne serbest bırakılacak bir işaretçi.  
  
 `bAbort`  
 Dosyanın kullanarak yayımlanacak olup olmadığını belirtir `CFile::Close` veya `CFile::Abort`. **YANLIŞ** dosya kullanarak yayımlanacak ise [CFile::Close](../../mfc/reference/cfile-class.md#close); **TRUE** dosya kullanarak yayımlanacak ise [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bAbort` olan **TRUE**, `ReleaseFile` çağrıları `CFile::Abort`, ve dosyayı serbest bırakılır. `CFile::Abort`bir özel durum oluşturmayacaksa.  
  
 Varsa `bAbort` olan **FALSE**, `ReleaseFile` çağrıları `CFile::Close` ve dosyayı serbest bırakılır.  
  
 Dosya yayımlanmadan önce kullanıcı tarafından bir eylem gerektirecek şekilde bu üye işlevi geçersiz kılar.  
  
##  <a name="removechunk"></a>CDocument::RemoveChunk  
 Belirtilen GUID'ye sahip bir öbek kaldırır.  
  
```  
virtual void RemoveChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>Parametreler  
 `Guid`  
 Kaldırılacak bir öbek GUİD'si belirtir.  
  
 `Pid`  
 Kaldırılacak bir öbek PID belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removeview"></a>CDocument::RemoveView  
 Bir belgeden bir görünüm ayırmak için bu işlevini çağırın.  
  
```  
void RemoveView(CView* pView);
```  
  
### <a name="parameters"></a>Parametreler  
 `pView`  
 Kaldırılmakta olan Görünüm noktalarına.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev belirtilen görünüm belgeyle ilişkilendirilen görünümleri listesinden kaldırır; Ayrıca görünümün belge işaretçi ayarlar **NULL**. Bu işlev bir çerçeve penceresi kapatıldığında veya bir bölme bir Bölümlendirici Pencere kapatıldığında çerçevesi tarafından çağrılır.  
  
 Bu işlev yalnızca el ile bir görünüm ayırma çağırır. Belgeler ve görünümler tanımlayarak detach framework genellikle sağlayacak bir [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) bir belge sınıfı, görünüm sınıfı ve çerçeve pencere sınıfı ilişkilendirmek için nesne.  
  
 Örneğe bakın [AddView](#addview) örnek uygulama için.  
  
##  <a name="reportsaveloadexception"></a>CDocument::ReportSaveLoadException  
 Bir özel durum durdurulduysa (genellikle bir [CFileException](../../mfc/reference/cfileexception-class.md) veya [CArchiveException](../../mfc/reference/carchiveexception-class.md)) kaydetme veya belge yükleme.  
  
```  
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,  
    CException* e,  
    BOOL bSaving,  
    UINT nIDPDefault);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszPathName`  
 İşaret çalıştırılmakta belge adına kaydedilmiş veya yüklenemedi.  
  
 *e*  
 Noktaları için özel durum oluştu. Olabilir **NULL**.  
  
 *bSaving*  
 Hangi işlemi devam ederken belirten bayrak; Belge değiştirilirken, sıfır olmayan kaydettiyseniz, 0 belge yüklendi.  
  
 `nIDPDefault`  
 İşlev daha belirli bir belirlemezse görüntülenecek hata iletisi tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama, özel durum nesnesini inceler ve özellikle nedenini açıklayan bir hata iletisi görünür. Belirli bir ileti bulunamadı veya gerekiyorsa *e* olan **NULL**, tarafından belirtilen genel bir ileti `nIDPDefault` parametresi kullanılır. İşlev sonra hata iletisini içeren bir ileti kutusu görüntüler. Özelleştirilmiş, ek hata iletileri sağlamak istiyorsanız bu işlev geçersiz kılar. Gelişmiş budur geçersiz kılınabilir.  
  
##  <a name="savemodified"></a>CDocument::SaveModified  
 Değiştirilmiş bir belgeyi kapatılması önce çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL SaveModified();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Devam etmek ve belgeyi Kapat güvenliyse sıfır olmayan; 0 Belge kapatılamıyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulaması herhangi yapılıp yapılmadığını kullanıcı değişiklikleri belgeye kaydedilip kaydedilmeyeceğini soran bir ileti kutusu görüntüler. Farklı bir sorulma yordam programınızı gerektiriyorsa, bu işlev geçersiz kılar. Gelişmiş budur geçersiz kılınabilir.  
  
##  <a name="setchunkvalue"></a>CDocument::SetChunkValue  
 Öbek değerini ayarlar.  
  
```  
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `pValue`  
 Ayarlamak için bir öbek değer belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setmodifiedflag"></a>CDocument::SetModifiedFlag  
 Belge yapılan tüm değişiklikleri yaptıktan sonra bu işlevini çağırın.  
  
```  
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bModified`  
 Belge değişiklik olup olmadığını belirten bayrak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev tutarlı bir şekilde çağırarak framework bir belgeyi kapatmadan önce değişiklikleri kaydetmek için kullanıcı komut istemleri emin olun. Genellikle varsayılan değeri kullanması gereken **TRUE** için `bModified` parametresi. Temiz bir belge (değiştirilmemiş) işaretlemek için değerini bu işlev çağrısı **FALSE**.  
  
##  <a name="setpathname"></a>CDocument::SetPathName  
 Belgenin disk dosyasının tam yolunu belirtmek için bu işlevini çağırın.  
  
```  
virtual void SetPathName(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszPathName`  
 Belge için yol olarak kullanılacak dizeye noktaları.  
  
 `bAddToMRU`  
 Dosya adı eklenir olup olmadığını en son (MRU) dosya listesi kullanılan belirler. Varsa **TRUE,** filename; eklenir **yanlış**, onu eklenmez.  
  
### <a name="remarks"></a>Açıklamalar  
 Değerine bağlı olarak `bAddToMRU` yol eklenen veya, uygulama tarafından tutulan MRU listesine eklenmedi. Bazı belgeleri bir disk dosyası ile ilişkili değildir. Bu işlev yalnızca çerçevesi tarafından kullanılan dosyaları açma ve kaydetme için varsayılan uygulama kılıyorsa çağırın.  
  
##  <a name="settitle"></a>CDocument::SetTitle  
 Belgenin başlığı (dize bir çerçeve penceresinin başlık çubuğunda görüntülenir) belirtmek için bu işlevini çağırın.  
  
```  
virtual void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszTitle`  
 Belgenin başlığı olarak kullanılacak dizeye noktaları.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağırma belgeyi görüntülemek tüm çerçeve pencereleri başlıklarını güncelleştirir.  
  
##  <a name="updateallviews"></a>CDocument::UpdateAllViews  
 Belge değiştirildikten sonra bu işlevini çağırın.  
  
```  
void UpdateAllViews(
    CView* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSender`  
 İşaret belge değiştiren görünümüne veya **NULL** tüm görünümleri güncelleştirilmesi gerekiyorsa.  
  
 `lHint`  
 Değiştirme hakkında bilgi içerir.  
  
 `pHint`  
 Nesneyi değiştirme hakkında bilgi depolamak için noktaları.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra bu işlev çağırmalıdır [SetModifiedFlag](#setmodifiedflag) üye işlevi. Bu işlev tarafından belirtilen görünümü dışında belgeye bağlı her görünüm bildirir `pSender`, belgenin değiştirilmiş. Kullanıcı bir görünümü aracılığıyla belge değiştikten sonra Görünüm sınıfından genellikle bu işlevini çağırın.  
  
 Bu işlev çağrılarını [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) üye işlevi her gönderme dışında belgenin görünümleri görüntülemek, geçirme `pHint` ve `lHint`. Görünümlere belgede yapılan değişiklikler hakkında bilgi geçirmek için şu parametreleri kullan. Bilgi kodlama `lHint` ve/veya tanımlayabileceğiniz bir [CObject](../../mfc/reference/cobject-class.md)-türetilmiş sınıf değişiklikler hakkında bilgi depolamak ve bu sınıfı kullanarak bir nesneyi geçirmek için `pHint`. Geçersiz kılma `CView::OnUpdate` üye işlevinde, [CView](../../mfc/reference/cview-class.md)-türetilmiş sınıf geçirilen bilgilere göre görünümün görüntüleme güncelleştirme en iyi duruma getirme.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC örnek SNAPVW](../../visual-cpp-samples.md)   
 [MFC örnek NPP](../../visual-cpp-samples.md)   
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [CView sınıfı](../../mfc/reference/cview-class.md)   
 [CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)
