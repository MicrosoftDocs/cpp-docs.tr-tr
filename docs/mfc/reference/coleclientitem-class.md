---
title: COleClientItem sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleClientItem
- AFXOLE/COleClientItem
- AFXOLE/COleClientItem::COleClientItem
- AFXOLE/COleClientItem::Activate
- AFXOLE/COleClientItem::ActivateAs
- AFXOLE/COleClientItem::AttachDataObject
- AFXOLE/COleClientItem::CanCreateFromData
- AFXOLE/COleClientItem::CanCreateLinkFromData
- AFXOLE/COleClientItem::CanPaste
- AFXOLE/COleClientItem::CanPasteLink
- AFXOLE/COleClientItem::Close
- AFXOLE/COleClientItem::ConvertTo
- AFXOLE/COleClientItem::CopyToClipboard
- AFXOLE/COleClientItem::CreateCloneFrom
- AFXOLE/COleClientItem::CreateFromClipboard
- AFXOLE/COleClientItem::CreateFromData
- AFXOLE/COleClientItem::CreateFromFile
- AFXOLE/COleClientItem::CreateLinkFromClipboard
- AFXOLE/COleClientItem::CreateLinkFromData
- AFXOLE/COleClientItem::CreateLinkFromFile
- AFXOLE/COleClientItem::CreateNewItem
- AFXOLE/COleClientItem::CreateStaticFromClipboard
- AFXOLE/COleClientItem::CreateStaticFromData
- AFXOLE/COleClientItem::Deactivate
- AFXOLE/COleClientItem::DeactivateUI
- AFXOLE/COleClientItem::Delete
- AFXOLE/COleClientItem::DoDragDrop
- AFXOLE/COleClientItem::DoVerb
- AFXOLE/COleClientItem::Draw
- AFXOLE/COleClientItem::GetActiveView
- AFXOLE/COleClientItem::GetCachedExtent
- AFXOLE/COleClientItem::GetClassID
- AFXOLE/COleClientItem::GetClipboardData
- AFXOLE/COleClientItem::GetDocument
- AFXOLE/COleClientItem::GetDrawAspect
- AFXOLE/COleClientItem::GetExtent
- AFXOLE/COleClientItem::GetIconFromRegistry
- AFXOLE/COleClientItem::GetIconicMetafile
- AFXOLE/COleClientItem::GetInPlaceWindow
- AFXOLE/COleClientItem::GetItemState
- AFXOLE/COleClientItem::GetLastStatus
- AFXOLE/COleClientItem::GetLinkUpdateOptions
- AFXOLE/COleClientItem::GetType
- AFXOLE/COleClientItem::GetUserType
- AFXOLE/COleClientItem::IsInPlaceActive
- AFXOLE/COleClientItem::IsLinkUpToDate
- AFXOLE/COleClientItem::IsModified
- AFXOLE/COleClientItem::IsOpen
- AFXOLE/COleClientItem::IsRunning
- AFXOLE/COleClientItem::OnActivate
- AFXOLE/COleClientItem::OnActivateUI
- AFXOLE/COleClientItem::OnChange
- AFXOLE/COleClientItem::OnDeactivate
- AFXOLE/COleClientItem::OnDeactivateUI
- AFXOLE/COleClientItem::OnGetClipboardData
- AFXOLE/COleClientItem::OnInsertMenus
- AFXOLE/COleClientItem::OnRemoveMenus
- AFXOLE/COleClientItem::OnSetMenu
- AFXOLE/COleClientItem::OnShowControlBars
- AFXOLE/COleClientItem::OnUpdateFrameTitle
- AFXOLE/COleClientItem::ReactivateAndUndo
- AFXOLE/COleClientItem::Release
- AFXOLE/COleClientItem::Reload
- AFXOLE/COleClientItem::Run
- AFXOLE/COleClientItem::SetDrawAspect
- AFXOLE/COleClientItem::SetExtent
- AFXOLE/COleClientItem::SetHostNames
- AFXOLE/COleClientItem::SetIconicMetafile
- AFXOLE/COleClientItem::SetItemRects
- AFXOLE/COleClientItem::SetLinkUpdateOptions
- AFXOLE/COleClientItem::SetPrintDevice
- AFXOLE/COleClientItem::UpdateLink
- AFXOLE/COleClientItem::CanActivate
- AFXOLE/COleClientItem::OnChangeItemPosition
- AFXOLE/COleClientItem::OnDeactivateAndUndo
- AFXOLE/COleClientItem::OnDiscardUndoState
- AFXOLE/COleClientItem::OnGetClipRect
- AFXOLE/COleClientItem::OnGetItemPosition
- AFXOLE/COleClientItem::OnGetWindowContext
- AFXOLE/COleClientItem::OnScrollBy
- AFXOLE/COleClientItem::OnShowItem
dev_langs:
- C++
helpviewer_keywords:
- COleClientItem [MFC], COleClientItem
- COleClientItem [MFC], Activate
- COleClientItem [MFC], ActivateAs
- COleClientItem [MFC], AttachDataObject
- COleClientItem [MFC], CanCreateFromData
- COleClientItem [MFC], CanCreateLinkFromData
- COleClientItem [MFC], CanPaste
- COleClientItem [MFC], CanPasteLink
- COleClientItem [MFC], Close
- COleClientItem [MFC], ConvertTo
- COleClientItem [MFC], CopyToClipboard
- COleClientItem [MFC], CreateCloneFrom
- COleClientItem [MFC], CreateFromClipboard
- COleClientItem [MFC], CreateFromData
- COleClientItem [MFC], CreateFromFile
- COleClientItem [MFC], CreateLinkFromClipboard
- COleClientItem [MFC], CreateLinkFromData
- COleClientItem [MFC], CreateLinkFromFile
- COleClientItem [MFC], CreateNewItem
- COleClientItem [MFC], CreateStaticFromClipboard
- COleClientItem [MFC], CreateStaticFromData
- COleClientItem [MFC], Deactivate
- COleClientItem [MFC], DeactivateUI
- COleClientItem [MFC], Delete
- COleClientItem [MFC], DoDragDrop
- COleClientItem [MFC], DoVerb
- COleClientItem [MFC], Draw
- COleClientItem [MFC], GetActiveView
- COleClientItem [MFC], GetCachedExtent
- COleClientItem [MFC], GetClassID
- COleClientItem [MFC], GetClipboardData
- COleClientItem [MFC], GetDocument
- COleClientItem [MFC], GetDrawAspect
- COleClientItem [MFC], GetExtent
- COleClientItem [MFC], GetIconFromRegistry
- COleClientItem [MFC], GetIconicMetafile
- COleClientItem [MFC], GetInPlaceWindow
- COleClientItem [MFC], GetItemState
- COleClientItem [MFC], GetLastStatus
- COleClientItem [MFC], GetLinkUpdateOptions
- COleClientItem [MFC], GetType
- COleClientItem [MFC], GetUserType
- COleClientItem [MFC], IsInPlaceActive
- COleClientItem [MFC], IsLinkUpToDate
- COleClientItem [MFC], IsModified
- COleClientItem [MFC], IsOpen
- COleClientItem [MFC], IsRunning
- COleClientItem [MFC], OnActivate
- COleClientItem [MFC], OnActivateUI
- COleClientItem [MFC], OnChange
- COleClientItem [MFC], OnDeactivate
- COleClientItem [MFC], OnDeactivateUI
- COleClientItem [MFC], OnGetClipboardData
- COleClientItem [MFC], OnInsertMenus
- COleClientItem [MFC], OnRemoveMenus
- COleClientItem [MFC], OnSetMenu
- COleClientItem [MFC], OnShowControlBars
- COleClientItem [MFC], OnUpdateFrameTitle
- COleClientItem [MFC], ReactivateAndUndo
- COleClientItem [MFC], Release
- COleClientItem [MFC], Reload
- COleClientItem [MFC], Run
- COleClientItem [MFC], SetDrawAspect
- COleClientItem [MFC], SetExtent
- COleClientItem [MFC], SetHostNames
- COleClientItem [MFC], SetIconicMetafile
- COleClientItem [MFC], SetItemRects
- COleClientItem [MFC], SetLinkUpdateOptions
- COleClientItem [MFC], SetPrintDevice
- COleClientItem [MFC], UpdateLink
- COleClientItem [MFC], CanActivate
- COleClientItem [MFC], OnChangeItemPosition
- COleClientItem [MFC], OnDeactivateAndUndo
- COleClientItem [MFC], OnDiscardUndoState
- COleClientItem [MFC], OnGetClipRect
- COleClientItem [MFC], OnGetItemPosition
- COleClientItem [MFC], OnGetWindowContext
- COleClientItem [MFC], OnScrollBy
- COleClientItem [MFC], OnShowItem
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89a277293cd4b192af0a8a069b82b1b1614490a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378767"
---
# <a name="coleclientitem-class"></a>COleClientItem sınıfı
OLE öğeleri kapsayıcı arabirimi tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleClientItem : public CDocItem  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleClientItem::COleClientItem](#coleclientitem)|Oluşturan bir `COleClientItem` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleClientItem::Activate](#activate)|OLE öğesi bir işlem için açılır ve belirtilen fiil çalıştırır.|  
|[COleClientItem::ActivateAs](#activateas)|Öğe, başka bir tür olarak etkinleştirir.|  
|[COleClientItem::AttachDataObject](#attachdataobject)|OLE nesnesindeki veri erişir.|  
|[COleClientItem::CanCreateFromData](#cancreatefromdata)|Bir kapsayıcı uygulama katıştırılmış nesne oluşturma olup olmadığını gösterir.|  
|[COleClientItem::CanCreateLinkFromData](#cancreatelinkfromdata)|Bir kapsayıcı uygulama bağlantılı nesne oluşturma olup olmadığını gösterir.|  
|[COleClientItem::CanPaste](#canpaste)|Pano gömülebilir veya statik OLE öğeyi içerip içermediğini belirtir.|  
|[COleClientItem::CanPasteLink](#canpastelink)|Pano linkable OLE öğesi içerip içermediğini belirtir.|  
|[COleClientItem::Close](#close)|Bir sunucu bağlantısı kapatır, ancak OLE öğesi yok etmez.|  
|[COleClientItem::ConvertTo](#convertto)|Öğe, başka bir türüne dönüştürür.|  
|[COleClientItem::CopyToClipboard](#copytoclipboard)|OLE öğesi panoya kopyalar.|  
|[COleClientItem::CreateCloneFrom](#createclonefrom)|Var olan öğenin bir kopyasını oluşturur.|  
|[COleClientItem::CreateFromClipboard](#createfromclipboard)|Katıştırılmış bir öğe panodan oluşturur.|  
|[COleClientItem::CreateFromData](#createfromdata)|Katıştırılmış bir öğesi bir veri nesnesi oluşturur.|  
|[COleClientItem::CreateFromFile](#createfromfile)|Katıştırılmış bir öğe, bir dosya oluşturur.|  
|[COleClientItem::CreateLinkFromClipboard](#createlinkfromclipboard)|Bağlantılı bir öğe panodan oluşturur.|  
|[COleClientItem::CreateLinkFromData](#createlinkfromdata)|Bağlantılı bir öğe, bir veri nesnesi oluşturur.|  
|[COleClientItem::CreateLinkFromFile](#createlinkfromfile)|Bağlantılı bir öğe, bir dosya oluşturur.|  
|[COleClientItem::CreateNewItem](#createnewitem)|Sunucu uygulaması başlatarak yeni bir katıştırılmış öğesi oluşturur.|  
|[COleClientItem::CreateStaticFromClipboard](#createstaticfromclipboard)|Statik bir öğe panodan oluşturur.|  
|[COleClientItem::CreateStaticFromData](#createstaticfromdata)|Bir statik öğesi bir veri nesnesi oluşturur.|  
|[COleClientItem::Deactivate](#deactivate)|Öğesini devre dışı bırakır.|  
|[COleClientItem::DeactivateUI](#deactivateui)|Kapsayıcı uygulamanın kullanıcı arabirimi özgün durumuna geri yükler.|  
|[COleClientItem::Delete](#delete)|Siler veya bağlantılı bir öğe ise OLE öğesi kapatır.|  
|[COleClientItem::DoDragDrop](#dodragdrop)|Sürükle ve bırak işlemi gerçekleştirir.|  
|[COleClientItem::DoVerb](#doverb)|Belirtilen fiil çalıştırır.|  
|[COleClientItem::Draw](#draw)|OLE öğesi çizer.|  
|[COleClientItem::GetActiveView](#getactiveview)|Öğe yerinde etkinleştirilir görünümünü alır.|  
|[COleClientItem::GetCachedExtent](#getcachedextent)|OLE öğesi'nin dikdörtgen sınırlarına döndürür.|  
|[COleClientItem::GetClassID](#getclassid)|Mevcut öğenin sınıfı kimliği alır.|  
|[COleClientItem::GetClipboardData](#getclipboarddata)|Pano'ya çağırarak konulabilir verileri alır `CopyToClipboard` üye işlevi.|  
|[COleClientItem::GetDocument](#getdocument)|Döndürür `COleDocument` mevcut öğe içeren nesne.|  
|[COleClientItem::GetDrawAspect](#getdrawaspect)|Öğenin geçerli görünüm için işleme alır.|  
|[COleClientItem::GetExtent](#getextent)|OLE öğesi'nin dikdörtgen sınırlarına döndürür.|  
|[COleClientItem::GetIconFromRegistry](#geticonfromregistry)|Belirli bir CLSID sunucu ile ilişkilendirilen bir simge işleyici alır.|  
|[COleClientItem::GetIconicMetafile](#geticonicmetafile)|Öğenin simgesini çizmek için kullanılan meta dosyası alır.|  
|[COleClientItem::GetInPlaceWindow](#getinplacewindow)|Bir işaretçi öğesi'nin yerinde düzenleme penceresine döndürür.|  
|[COleClientItem::GetItemState](#getitemstate)|Öğenin geçerli durumunu alır.|  
|[COleClientItem::GetLastStatus](#getlaststatus)|Son OLE işlemin durumunu döndürür.|  
|[COleClientItem::GetLinkUpdateOptions](#getlinkupdateoptions)|Bağlantılı bir öğe (Gelişmiş özelliği) için güncelleştirme modunu döndürür.|  
|[COleClientItem::GetType](#gettype)|OLE öğesi türünü (katıştırılmış, bağlantılı veya statik) döndürür.|  
|[COleClientItem::GetUserType](#getusertype)|Öğenin türünü tanımlayan bir dize alır.|  
|[COleClientItem::IsInPlaceActive](#isinplaceactive)|Döndürür `TRUE` öğe yerinde etkin ise.|  
|[COleClientItem::IsLinkUpToDate](#islinkuptodate)|Döndürür **TRUE** bağlantılı bir öğe, kaynak belge güncel olması durumunda.|  
|[COleClientItem::IsModified](#ismodified)|Döndürür `TRUE` son kaydedilişinden öğesi güncellendiyse.|  
|[COleClientItem::IsOpen](#isopen)|Döndürür `TRUE` öğe sunucu uygulamada açık ise.|  
|[COleClientItem::IsRunning](#isrunning)|Döndürür `TRUE` öğesi'nin sunucu uygulaması çalıştırıyorsa.|  
|[COleClientItem::OnActivate](#onactivate)|Öğe etkinleştirilmiş olduğunu bildirmek için çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnActivateUI](#onactivateui)|Öğe etkinleştirilir ve kullanıcı arabirimiyle gösterilip gösterilmeyeceğini bildirmek için çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnChange](#onchange)|Sunucu OLE öğesi değiştirdiğinde çağrılır. Gerekli uygulama.|  
|[COleClientItem::OnDeactivate](#ondeactivate)|Bir öğe devre dışı bırakıldığında çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnDeactivateUI](#ondeactivateui)|Sunucu yerinde kullanıcı arabirimiyle kaldırıldığında çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnGetClipboardData](#ongetclipboarddata)|Panoya kopyalamak için verileri almak için çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnInsertMenus](#oninsertmenus)|Bileşik menü oluşturmak için çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnRemoveMenus](#onremovemenus)|Kapsayıcının menüleri bileşik menüden kaldırmak için çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnSetMenu](#onsetmenu)|Yükleme ve kaldırma bileşik menü çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnShowControlBars](#onshowcontrolbars)|Göstermek ve denetim çubukları gizlemek için çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnUpdateFrameTitle](#onupdateframetitle)|Çerçeve penceresinin başlık çubuğunu güncelleştirmek için çerçevesi tarafından çağrılır.|  
|[COleClientItem::ReactivateAndUndo](#reactivateandundo)|Öğe yeniden etkinleştirir ve son yerinde düzenleme işlemini geri alır.|  
|[COleClientItem::Release](#release)|Öğesi bağlı bir OLE bağlantısı serbest bırakır ve açık olması durumunda kapatır. İstemci öğesi yok.|  
|[COleClientItem::Reload](#reload)|Öğe için bir çağrı sonra yeniden yükler `ActivateAs`.|  
|[COleClientItem::Run](#run)|Bu öğeyle ilişkili uygulama çalışır.|  
|[COleClientItem::SetDrawAspect](#setdrawaspect)|Öğenin geçerli görünüm oluşturma işlemi için ayarlar.|  
|[COleClientItem::SetExtent](#setextent)|OLE öğesi sınırlayıcı dikdörtgenini ayarlar.|  
|[COleClientItem::SetHostNames](#sethostnames)|OLE öğesi düzenlerken sunucu görüntüler adlarını ayarlar.|  
|[COleClientItem::SetIconicMetafile](#seticonicmetafile)|Öğenin simgesini çizmek için kullanılan meta dosyası önbelleğe alır.|  
|[COleClientItem::SetItemRects](#setitemrects)|Öğenin sınırlayıcı dikdörtgenini ayarlar.|  
|[COleClientItem::SetLinkUpdateOptions](#setlinkupdateoptions)|Bağlantılı bir öğe (Gelişmiş özelliği) için güncelleştirme modunu ayarlar.|  
|[COleClientItem::SetPrintDevice](#setprintdevice)|Bu istemci öğesi için yazdırma hedef aygıt ayarlar.|  
|[COleClientItem::UpdateLink](#updatelink)|Bir öğenin sunu önbelleğini güncelleştirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleClientItem::CanActivate](#canactivate)|Yerinde etkinleştirme izin verilip verilmediğini belirlemek için çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnChangeItemPosition](#onchangeitemposition)|Bir öğenin konumu değiştiğinde çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnDeactivateAndUndo](#ondeactivateandundo)|Etkinleştirildikten sonra geri çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnDiscardUndoState](#ondiscardundostate)|Öğenin geri alma işlemi durum bilgilerini atmak için çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnGetClipRect](#ongetcliprect)|Öğenin dikdörtgen kırpma koordinatlarını alma çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnGetItemPosition](#ongetitemposition)|Öğesi'nin konumuna göre görünümü almak için çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnGetWindowContext](#ongetwindowcontext)|Bir öğe yerinde etkinleştirildiğinde çerçevesi tarafından çağrılır.|  
|[COleClientItem::OnScrollBy](#onscrollby)|Öğe görünüme gidin framework tarafından çağrılır.|  
|[COleClientItem::OnShowItem](#onshowitem)|OLE öğesi görüntülenecek çerçevesi tarafından çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 OLE öğeyi oluşturulmuş ve bir belgeye "sorunsuz" birleştirilebilir ve böylece tek bir belgenin kullanıcıya görüntülenen bir sunucu uygulaması tarafından korunan verileri temsil eder. Sonuç "içeren bir belge OLE öğesi ve oluşan bir bileşik belge" olur.  
  
 OLE öğeyi katıştırılmış bağlantılı ya da. Katıştırılmış olan, kendi veri bileşik belge bir parçası olarak depolanır. Bağlıysa, verileri ayrı bir dosya sunucu uygulaması tarafından oluşturulan bir parçası olarak depolanır ve yalnızca o dosyaya bir bağlantı bileşik belge içinde depolanır. Tüm OLE öğelerini düzenlemek için çağrılmalıdır sunucu uygulaması belirten bilgiler içerir.  
  
 `COleClientItem` Sunucu uygulaması gelen isteklere yanıt olarak adlandırılan birden fazla geçersiz kılınabilir işlevler tanımlar; Bu geçersiz kılınabilir genellikle bildirimleri olarak davranır. OLE öğesi düzenlerken kullanıcının yaptığı değişiklikler kapsayıcı bildirmek veya düzenleme sırasında gerekli bilgileri almak için sunucu uygulaması sağlar.  
  
 `COleClientItem` ile birlikte kullanılabilir [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), veya [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) sınıfı. Kullanılacak `COleClientItem`, buradan bir sınıf türetin ve uygulama [değiştiğinde](#onchange) kapsayıcı öğesine yapılan değişiklikleri nasıl yanıt vereceğini tanımlar üye işlevi. Yerinde etkinleştirme desteklemek için geçersiz kılma [OnGetItemPosition](#ongetitemposition) üye işlevi. Bu işlev OLE öğesi görüntülenen konumu hakkında bilgi sağlar.  
  
 Kapsayıcı arabirimini kullanma hakkında daha fazla bilgi için makalelerine bakın [kapsayıcıları: bir kapsayıcı uygulama](../../mfc/containers-implementing-a-container.md) ve [etkinleştirme](../../mfc/activation-cpp.md).  
  
> [!NOTE]
>  Katıştırılmış ve bağlantılı öğeler "nesne" olarak ifade eder ve "sınıflar." olarak öğelerinin türleri başvurduğu Windows SDK'sını Bu başvuru, OLE varlık karşılık gelen C++ nesnesini ve OLE kategorisi C++ sınıfından ayırt etmek için "type" terimi ayırmak için "öğesi" terimini kullanır.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="activate"></a>  COleClientItem::Activate  
 Belirtilen fiil yerine yürütmek için bu işlevi çağırmak [DoVerb](#doverb) bir özel durum yakalandığında kendi işlem yapabilmesi için.  
  
```  
void Activate(
    LONG nVerb,  
    CView* pView,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `nVerb`  
 Yürütülecek fiili belirtir. Aşağıdakilerden biri olabilir:  
  
|Değer|Açıklama|Simgesi|  
|-----------|-------------|------------|  
|- 0|Birincil fiil|`OLEIVERB_PRIMARY`|  
|- 1|İkincil fiil|(Hiçbiri)|  
|- 1|Görüntü öğesini düzenlemek için|`OLEIVERB_SHOW`|  
|- 2|Ayrı bir pencerede öğesi düzenleme|`OLEIVERB_OPEN`|  
|- 3|Öğe Gizle|`OLEIVERB_HIDE`|  
  
 -1 genellikle başka bir fiil için diğer ad değerdir. Açık düzenleme desteklenmiyorsa, -2 -1 olarak aynı etkiye sahiptir. Ek değerler için bkz: [Rpc_e_serverfault](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK'sındaki.  
  
 `pView`  
 OLE öğeyi içeren kapsayıcı Görünümü penceresi işaretçi; Bu sunucu uygulaması tarafından yerinde etkinleştirme için kullanılır. Bu parametre olmalıdır **NULL** kapsayıcı yerinde etkinleştirme desteklemiyorsa.  
  
 `lpMsg`  
 İşaretçi etkinleştirilmesi için öğeyi neden iletisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Sunucu uygulaması, Microsoft Foundation Class Kitaplığı kullanılarak yazılmış olduğundan, bu işlev neden [OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb) ilgili üye işlevi `COleServerItem` yürütülecek nesne.  
  
 Birincil fiili Düzenle olduğunda ve sıfır belirtilen `nVerb` parametresi, sunucu uygulaması başlatılan düzenlenmesi OLE öğesi izin vermek için. Yerinde etkinleştirme kapsayıcı uygulama destekliyorsa, düzenleme yerinde yapılabilir. Kapsayıcı yerinde etkinleştirme (veya açık fiil belirttiyseniz) desteklemiyorsa, sunucuyu ayrı bir pencerede başlatılır ve düzenleme var. yapılabilir. Genellikle, ne zaman kapsayıcı uygulamanın kullanıcısı çift tıklamalar OLE öğesi, birincil fiil değeri `nVerb` parametre, kullanıcının alabilir hangi eylemini belirler. Sunucu yalnızca bir eylem destekliyorsa, ancak ne olursa olsun değer belirtilen söz konusu eylem sürdüğünü `nVerb` parametresi.  
  
 Daha fazla bilgi için bkz: [Rpc_e_serverfault](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK'sındaki.  
  
##  <a name="activateas"></a>  COleClientItem::ActivateAs  
 Dizinindeymiş gibi bir öğe tarafından belirtilen türde öğe etkinleştirmek için OLE'ın nesne dönüştürme tesis kullanır `clsidNew`.  
  
```  
virtual BOOL ActivateAs(
    LPCTSTR lpszUserType,  
    REFCLSID clsidOld,  
    REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszUserType*  
 Hedef kullanıcı türü "Word belgesi" gibi temsil eden bir dize işaretçi  
  
 *clsidOld*  
 Bir başvuru öğesi'nin geçerli sınıf kimliği Bir bağlantı değilse sınıf kimliği depolandığı şekliyle gerçek nesne türünü temsil etmelidir. Bu durumda, bağlantıyı başvurduğu öğenin CLSID'si olması gerekir. [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md) doğru sınıf kimliği öğe için otomatik olarak sağlar.  
  
 `clsidNew`  
 Başvuru hedef sınıf kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tarafından otomatik olarak adlandırılır [COleConvertDialog::DoConvert](../../mfc/reference/coleconvertdialog-class.md#doconvert). Bu genellikle doğrudan çağrılmaz.  
  
##  <a name="attachdataobject"></a>  COleClientItem::AttachDataObject  
 Başlatmak için bu işlevi çağırmak bir [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE öğesi veri erişimi için.  
  
```  
void AttachDataObject(COleDataObject& rDataObject) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *rDataObject*  
 Başvuru bir `COleDataObject` OLE öğesi veri erişmesine izin vermek üzere başlatılacaktır nesnesi.  
  
##  <a name="canactivate"></a>  COleClientItem::CanActivate  
 Kullanıcı yerinde etkinleştirme OLE öğesinin istediğinde çerçevesi tarafından çağrılır; Bu işlevin dönüş değeri yerinde etkinleştirme izin verilip verilmediğini belirler.  
  
```  
virtual BOOL CanActivate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerinde etkinleştirme izin verilip verilmediğini sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli bir pencere kapsayıcı varsa, varsayılan uygulama yerinde etkinleştirme sağlar. Bu işlevi kabul etme veya etkinleştirme isteği reddediyor için özel bir mantık uygulamanız için geçersiz kılar. Örneğin, bir etkinleştirme isteği OLE öğesi çok küçük veya şu anda görünür ise reddedilebilir.  
  
 Daha fazla bilgi için bkz: [IOleInPlaceSite::CanInPlaceActivate](http://msdn.microsoft.com/library/windows/desktop/ms691236) Windows SDK'sındaki.  
  
##  <a name="cancreatefromdata"></a>  COleClientItem::CanCreateFromData  
 Bir kapsayıcı uygulama katıştırılmış nesne oluşturabilirsiniz olup olmadığını denetler verilen `COleDataObject` nesnesi.  
  
```  
static BOOL PASCAL CanCreateFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataObject`  
 İşaretçi [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE öğesi olduğu oluşturulacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Katıştırılmış nesne kapsayıcısı oluşturup oluşturamayacağını sıfır olmayan `COleDataObject` nesnesi; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `COleDataObject` Sınıfı, veri aktarımları ile sürükle ve bırak, Pano veya katıştırılmış OLE öğeyi çeşitli biçimlerde verileri almak için kullanılır.  
  
 Kapsayıcıları etkinleştirme veya devre dışı kendi Düzenle Yapıştır ve Düzenle Özel Yapıştır komutları karar vermek için bu işlevi kullanabilirsiniz.  
  
 Daha fazla bilgi için bkz: [veri nesneleri ve veri kaynakları (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
##  <a name="cancreatelinkfromdata"></a>  COleClientItem::CanCreateLinkFromData  
 Bir kapsayıcı uygulama içinden bağlantılı nesne oluşturabilirsiniz olup olmadığını denetler verilen `COleDataObject` nesnesi.  
  
```  
static BOOL PASCAL CanCreateLinkFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataObject`  
 İşaretçi [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE öğesi olduğu oluşturulacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsayıcı içinden bağlantılı nesne oluşturup oluşturamayacağını sıfır olmayan `COleDataObject` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `COleDataObject` Sınıfı, veri aktarımları ile sürükle ve bırak, Pano veya katıştırılmış OLE öğeyi çeşitli biçimlerde verileri almak için kullanılır.  
  
 Kapsayıcıları etkinleştirme veya devre dışı kendi özel Yapıştır düzenleyin ve düzenleme Bağlantı Yapıştır komutları karar vermek için bu işlevi kullanabilirsiniz.  
  
 Daha fazla bilgi için bkz: [veri nesneleri ve veri kaynakları (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
##  <a name="canpaste"></a>  COleClientItem::CanPaste  
 Katıştırılmış OLE öğe panodan yapıştırılan olup olmadığını görmek için bu işlevini çağırın.  
  
```  
static BOOL PASCAL CanPaste();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Katıştırılmış OLE öğe panodan yapıştırılan, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778) ve [OleQueryCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms683739) Windows SDK'sındaki.  
  
##  <a name="canpastelink"></a>  COleClientItem::CanPasteLink  
 Bağlantılı bir OLE öğe panodan yapıştırılan olup olmadığını görmek için bu işlevini çağırın.  
  
```  
static BOOL PASCAL CanPasteLink();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlantılı bir OLE öğe panodan yapıştırılan, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778) ve [OleQueryLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms690244) Windows SDK'sındaki.  
  
##  <a name="close"></a>  COleClientItem::Close  
 Yüklenen durumu, diğer bir deyişle, çalışma durumuna bellekte kendi işleyici ile ancak değil çalıştıran sunucuya yüklenen bir OLE öğesi durumunu değiştirmek için bu işlevini çağırın.  
  
```  
void Close(OLECLOSE dwCloseOption = OLECLOSE_SAVEIFDIRTY);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwCloseOption`  
 Yüklenen durumuna geri döndüğünde hangi koşullar altında OLE öğesi kaydedildiğinde belirten bayrak. Aşağıdaki değerlerden biri olabilir:  
  
- `OLECLOSE_SAVEIFDIRTY` OLE öğesi kaydedin.  
  
- `OLECLOSE_NOSAVE` OLE öğesi kaydetmeyin.  
  
- `OLECLOSE_PROMPTSAVE` OLE öğesi kaydedilip kaydedilmeyeceğini kullanıcıya sor  
  
### <a name="remarks"></a>Açıklamalar  
 OLE öğesi çalışmıyorsa bu işlev bir etkisi yoktur.  
  
 Daha fazla bilgi için bkz: [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) Windows SDK'sındaki.  
  
##  <a name="coleclientitem"></a>  COleClientItem::COleClientItem  
 Oluşturan bir `COleClientItem` nesne ve yalnızca C++ nesnesi oluşturur ve tüm OLE başlatma gerçekleştirmez kapsayıcı belgenin koleksiyonuna belge öğeleri ekler.  
  
```  
COleClientItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pContainerDoc`  
 Bu öğeyi içerecek kapsayıcı belge işaretçi. Bu herhangi olabilir [COleDocument](../../mfc/reference/coledocument-class.md) türevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçirirseniz bir **NULL** işaretçi, hiçbir ek kapsayıcı belgeye yapılır. Açıkça çağırmalısınız [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem).  
  
 OLE öğesi kullanmadan önce aşağıdaki oluşturma üye işlevleri birini çağırmalıdır:  
  
- [CreateFromClipboard](#createfromclipboard)  
  
- [CreateFromData](#createfromdata)  
  
- [CreateFromFile](#createfromfile)  
  
- [CreateStaticFromClipboard](#createstaticfromclipboard)  
  
- [CreateStaticFromData](#createstaticfromdata)  
  
- [CreateLinkFromClipboard](#createlinkfromclipboard)  
  
- [CreateLinkFromData](#createlinkfromdata)  
  
- [CreateLinkFromFile](#createlinkfromfile)  
  
- [CreateNewItem](#createnewitem)  
  
- [CreateCloneFrom](#createclonefrom)  
  
##  <a name="convertto"></a>  COleClientItem::ConvertTo  
 Öğesi tarafından belirtilen türüne dönüştürmek için bu üye işlevini çağırın `clsidNew`.  
  
```  
virtual BOOL ConvertTo(REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>Parametreler  
 `clsidNew`  
 Hedef türü sınıfı kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tarafından otomatik olarak adlandırılır [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md). Doğrudan çağırmak gerekli değildir.  
  
##  <a name="copytoclipboard"></a>  COleClientItem::CopyToClipboard  
 OLE öğesi panoya kopyalamak için bu işlevini çağırın.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bIncludeLink`  
 **DOĞRU** bağlantı bilgilerini panoya kopyalandı, yapıştırılan; tersi durumda bağlantılı bir öğe izin vererek **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, bu işlev kopyalama veya kesme komutları için ileti işleyicileri düzenleme menüsünden yazılırken çağırın. Kopyalama veya kesme komutları uygulamak istiyorsanız, kapsayıcı uygulamanızda öğe seçimi uygulamalıdır.  
  
 Daha fazla bilgi için bkz: [OleSetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms686623) Windows SDK'sındaki.  
  
##  <a name="createclonefrom"></a>  COleClientItem::CreateCloneFrom  
 Belirtilen OLE öğenin bir kopyasını oluşturmak için bu işlevini çağırın.  
  
```  
BOOL CreateCloneFrom(const COleClientItem* pSrcItem);
```  
  
### <a name="parameters"></a>Parametreler  
 *pSrcItem*  
 Çoğaltılacak OLE öğesi işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kopya kaynak öğesine aynıdır. Geri alma işlemleri desteklemek için bu işlevi kullanabilirsiniz.  
  
##  <a name="createfromclipboard"></a>  COleClientItem::CreateFromClipboard  
 Pano içeriğini katıştırılmış bir öğe oluşturmak için bu işlevini çağırın.  
  
```  
BOOL CreateFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *İşleme*  
 Sunucu OLE öğesi nasıl kılacak belirten bayrak. Olası değerler için bkz: [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK'sındaki.  
  
 `cfFormat`  
 OLE öğesi oluşturulurken önbelleğe alınması için Pano verileri biçimi belirtir.  
  
 `lpFormatEtc`  
 İşaretçi bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) varsa kullanılan yapısı *işleme* olan **OLERENDER_FORMAT** veya **OLERENDER_DRAW**. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Bu parametresini atlarsanız, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle Düzen menüsünden Yapıştır komut için bu işlevi ileti işleyicisinden çağırın. (Yapıştır komut çerçevesi tarafından etkinleştirilir [CanPaste](#canpaste) üye işlevi sıfır olmayan bir değer döndürür.)  
  
 Daha fazla bilgi için bkz: [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
##  <a name="createfromdata"></a>  COleClientItem::CreateFromData  
 Katıştırılmış bir öğe oluşturmak için bu işlevi çağırmak bir `COleDataObject` nesnesi.  
  
```  
BOOL CreateFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataObject`  
 İşaretçi [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE öğesi olduğu oluşturulacak nesne.  
  
 *İşleme*  
 Sunucu OLE öğesi nasıl kılacak belirten bayrak. Olası değerler için bkz: [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK'sındaki.  
  
 `cfFormat`  
 OLE öğesi oluşturulurken önbelleğe alınması için Pano verileri biçimi belirtir.  
  
 `lpFormatEtc`  
 İşaretçi bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) varsa kullanılan yapısı *işleme* olan **OLERENDER_FORMAT** veya **OLERENDER_DRAW**. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Bu parametresini atlarsanız, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Pano ya da sürükle ve bırak işlemleri yapıştırma gibi veri aktarım işlemleri sağlamak `COleDataObject` bilgilerini içeren bir sunucu uygulaması tarafından sunulan nesneleri. Genellikle geçersiz kılmada kullanılan [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop).  
  
 Daha fazla bilgi için bkz: [OleCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms691211), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
##  <a name="createfromfile"></a>  COleClientItem::CreateFromFile  
 Bir dosyadan bir katıştırılmış OLE öğesi oluşturmak için bu işlevini çağırın.  
  
```  
BOOL CreateFromFile(
    LPCTSTR lpszFileName,  
    REFCLSID clsid = CLSID_NULL,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFileName`  
 OLE öğesi oluşturulacak olduğu dosya adı işaretçi.  
  
 `clsid`  
 Daha sonraki kullanımlar için ayrılmıştır.  
  
 *İşleme*  
 Sunucu OLE öğesi nasıl kılacak belirten bayrak. Olası değerler için bkz: [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK'sındaki.  
  
 `cfFormat`  
 OLE öğesi oluşturulurken önbelleğe alınması için Pano verileri biçimi belirtir.  
  
 `lpFormatEtc`  
 İşaretçi bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) varsa kullanılan yapısı *işleme* olan **OLERENDER_FORMAT** veya **OLERENDER_DRAW**. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Bu parametresini atlarsanız, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevden framework çağırması [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem) dosyası düğmesi Oluştur seçildiğinde kullanıcı Nesne Ekle iletişim kutusundan Tamam seçerse.  
  
 Daha fazla bilgi için bkz: [OleCreateFromFile](http://msdn.microsoft.com/library/windows/desktop/ms690116), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
##  <a name="createlinkfromclipboard"></a>  COleClientItem::CreateLinkFromClipboard  
 Pano içeriğini bağlantılı bir öğe oluşturmak için bu işlevini çağırın.  
  
```  
BOOL CreateLinkFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *İşleme*  
 Sunucu OLE öğesi nasıl kılacak belirten bayrak. Olası değerler için bkz: [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK'sındaki.  
  
 `cfFormat`  
 OLE öğesi oluşturulurken önbelleğe alınması için Pano verileri biçimi belirtir.  
  
 `lpFormatEtc`  
 İşaretçi bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) varsa kullanılan yapısı *işleme* olan **OLERENDER_FORMAT** veya **OLERENDER_DRAW**. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Bu parametresini atlarsanız, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle Düzen menüsünden Yapıştır komutu için bu işlevi ileti işleyicisinden çağırın. (Varsayılan uygulamasında Bağlantı Yapıştır komut etkin [COleDocument](../../mfc/reference/coledocument-class.md) Pano bağlanabilir OLE öğeyi içeriyorsa.)  
  
 Daha fazla bilgi için bkz: [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
##  <a name="createlinkfromdata"></a>  COleClientItem::CreateLinkFromData  
 Bağlantılı bir öğe oluşturmak için bu işlevi çağırmak bir `COleDataObject` nesnesi.  
  
```  
BOOL CreateLinkFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataObject`  
 İşaretçi [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE öğesi olduğu oluşturulacak nesne.  
  
 *İşleme*  
 Sunucu OLE öğesi nasıl kılacak belirten bayrak. Olası değerler için bkz: [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK'sındaki.  
  
 `cfFormat`  
 OLE öğesi oluşturulurken önbelleğe alınması için Pano verileri biçimi belirtir.  
  
 `lpFormatEtc`  
 İşaretçi bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) varsa kullanılan yapısı *işleme* olan **OLERENDER_FORMAT** veya **OLERENDER_DRAW**. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Bu parametresini atlarsanız, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir bağlantı oluşturulmalıdır belirttiğinde bu bırakma işlemi sırasında çağırın. Ayrıca, Yapıştır Düzenle komutu işlemek için de kullanılabilir. Framework'te tarafından çağrılan `COleClientItem::CreateLinkFromClipboard` ve [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) zaman bağlantı seçeneği seçildi.  
  
 Daha fazla bilgi için bkz: [OleCreateLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms680731), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
##  <a name="createlinkfromfile"></a>  COleClientItem::CreateLinkFromFile  
 Bir dosyadan bir bağlantılı OLE öğesi oluşturmak için bu işlevini çağırın.  
  
```  
BOOL CreateLinkFromFile(
    LPCTSTR lpszFileName,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFileName`  
 OLE öğesi oluşturulacak olduğu dosya adı işaretçi.  
  
 *İşleme*  
 Sunucu OLE öğesi nasıl kılacak belirten bayrak. Olası değerler için bkz: [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK'sındaki.  
  
 `cfFormat`  
 OLE öğesi oluşturulurken önbelleğe alınması için Pano verileri biçimi belirtir.  
  
 `lpFormatEtc`  
 İşaretçi bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) varsa kullanılan yapısı *işleme* olan **OLERENDER_FORMAT** veya **OLERENDER_DRAW**. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Bu parametresini atlarsanız, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı Tamam Nesne Ekle iletişim kutusundan dosya düğmesinden Oluştur seçildiğinde ve bağlantı onay kutusunun işaretli olduğundan seçerse framework bu işlevi çağırır. Yönteminden çağrılan [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem).  
  
 Daha fazla bilgi için bkz: [OleCreateLinkToFile](http://msdn.microsoft.com/library/windows/desktop/ms678434), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
##  <a name="createnewitem"></a>  COleClientItem::CreateNewItem  
 Katıştırılmış bir öğe oluşturmak için bu işlevi çağırmak; Bu işlev OLE öğesi oluşturmasına olanak tanır sunucu uygulaması başlatır.  
  
```  
BOOL CreateNewItem(
    REFCLSID clsid,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `clsid`  
 OLE öğesi oluşturmak için türü benzersiz olarak tanıtan kimliği.  
  
 *İşleme*  
 Sunucu OLE öğesi nasıl kılacak belirten bayrak. Olası değerler için bkz: [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK'sındaki.  
  
 `cfFormat`  
 OLE öğesi oluşturulurken önbelleğe alınması için Pano verileri biçimi belirtir.  
  
 `lpFormatEtc`  
 İşaretçi bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) varsa kullanılan yapısı *işleme* olan **OLERENDER_FORMAT** veya **OLERENDER_DRAW**. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Bu parametresini atlarsanız, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni Oluştur düğmesi seçildiğinde kullanıcı Nesne Ekle iletişim kutusundan Tamam seçerse framework bu işlevi çağırır.  
  
 Daha fazla bilgi için bkz: [OleCreate](http://msdn.microsoft.com/library/windows/desktop/ms678409), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
##  <a name="createstaticfromclipboard"></a>  COleClientItem::CreateStaticFromClipboard  
 Pano içeriğini bir statik öğesi oluşturmak için bu işlevini çağırın.  
  
```  
BOOL CreateStaticFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *İşleme*  
 Sunucu OLE öğesi nasıl kılacak belirten bayrak. Olası değerler için bkz: [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK'sındaki.  
  
 `cfFormat`  
 OLE öğesi oluşturulurken önbelleğe alınması için Pano verileri biçimi belirtir.  
  
 `lpFormatEtc`  
 İşaretçi bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) varsa kullanılan yapısı *işleme* olan **OLERENDER_FORMAT** veya **OLERENDER_DRAW**. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Bu parametresini atlarsanız, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Statik bir öğe içeriyor: sunu veri ancak yerel verileri değil; Sonuç olarak düzenlenemez. Genellikle bu işlevi çağırır [CreateFromClipboard](#createfromclipboard) üye işlev başarısız olur.  
  
 Daha fazla bilgi için bkz: [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
##  <a name="createstaticfromdata"></a>  COleClientItem::CreateStaticFromData  
 Bir statik öğesi oluşturmak için bu işlevi çağırmak bir `COleDataObject` nesnesi.  
  
```  
BOOL CreateStaticFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataObject`  
 İşaretçi [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE öğesi olduğu oluşturulacak nesne.  
  
 *İşleme*  
 Sunucu OLE öğesi nasıl kılacak belirten bayrak. Olası değerler için bkz: [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) Windows SDK'sındaki.  
  
 `cfFormat`  
 OLE öğesi oluşturulurken önbelleğe alınması için Pano verileri biçimi belirtir.  
  
 `lpFormatEtc`  
 İşaretçi bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) varsa kullanılan yapısı *işleme* olan **OLERENDER_FORMAT** veya **OLERENDER_DRAW**. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Bu parametresini atlarsanız, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Statik bir öğe içeriyor: sunu veri ancak yerel verileri değil; Sonuç olarak, düzenlenemez. Bu temelde aynıdır [CreateStaticFromClipboard](#createstaticfromclipboard) statik öğe rastgele bir oluşturulabilir ancak bu `COleDataObject`, yalnızca panodan.  
  
 Kullanılan [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) statik seçili olduğunda.  
  
 Daha fazla bilgi için bkz: [OleCreateStaticFromData](http://msdn.microsoft.com/library/windows/desktop/ms687290), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
##  <a name="deactivate"></a>  COleClientItem::Deactivate  
 Bu işlevin OLE öğesi devre dışı bırakın ve ilişkili tüm kaynakları boş çağırın.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı öğenin sınırları dışındaki istemci alanında fare tıklattığında yerinde etkin OLE öğeyi genellikle devre dışı bırakın. OLE öğesi devre dışı bırakma çağrısı olanaksız hale geri alma durumuna atacak Not [ReactivateAndUndo](#reactivateandundo) üye işlevi.  
  
 Geri alma uygulamanız destekliyorsa, çağırmayın `Deactivate`; bunun yerine, çağrı [DeactivateUI](#deactivateui).  
  
 Daha fazla bilgi için bkz: [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) Windows SDK'sındaki.  
  
##  <a name="deactivateui"></a>  COleClientItem::DeactivateUI  
 Yerinde etkinleştirildiği bir öğe kullanıcı devre dışı bırakır, bu işlevini çağırın.  
  
```  
void DeactivateUI();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev kapsayıcı uygulamanın kullanıcı arabirimi menüler ve yerinde etkinleştirme için oluşturulmuş olan diğer denetimleri gizleme özgün durumuna geri yükler.  
  
 Bu öğe için geri alma işlemi durum bilgilerini flush işlevi değil. Bilgi tutulur böylece [ReactivateAndUndo](#reactivateandundo) kapsayıcının undo komutu öğesi hemen devre dışı bırakma sonra seçilen durumda daha sonra sunucu uygulamasında, bir geri alma komut yürütmek için kullanılabilir.  
  
 Daha fazla bilgi için bkz: [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) Windows SDK'sındaki.  
  
##  <a name="delete"></a>  COleClientItem::Delete  
 Kapsayıcı belgeden OLE öğeyi silmek için bu işlevini çağırın.  
  
```  
void Delete(BOOL bAutoDelete = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bAutoDelete`  
 Öğesi belgeden kaldırılacak olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrılarını [sürüm](#release) sırayla öğesi, kalıcı olarak OLE öğesi belgeden kaldırmak için C++ nesneyi siler üye işlevi. OLE öğesi eklendiyse, bu öğenin yerel veriler silinir. Her zaman, çalışan bir sunucuya kapatır; öğesi açık bir bağlantı varsa, bu nedenle, bu işlev kapatılır.  
  
##  <a name="dodragdrop"></a>  COleClientItem::DoDragDrop  
 Çağrı `DoDragDrop` sürükle ve bırak işlemi gerçekleştirmek için üye işlevi.  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpItemRect,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpItemRect`  
 Öğenin dikdörtgen ekranında istemci koordinatları (piksel cinsinden).  
  
 `ptOffset`  
 Uzaklık `lpItemRect` fare konumuna Sürükle aynı anda bulunduğu.  
  
 `bIncludeLink`  
 Bu ayar **TRUE** panoya bağlantı verilerin kopyalanması gereken durumunda. Ayarlamak **FALSE** sunucu uygulamanızı bağlantılar desteklemiyorsa.  
  
 `dwEffects`  
 Sürükleme kaynağı sürükleme işlemi sağlayacak etkilerini belirler.  
  
 `lpRectStartDrag`  
 Sürükle gerçekte başladığı tanımlar dikdörtgen işaretçi. Daha fazla bilgi için aşağıdaki Açıklamalar bölümüne bakın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `DROPEFFECT` değeri. Eğer öyleyse `DROPEFFECT_MOVE`, özgün verilerin kaldırılması gerekir.  
  
### <a name="remarks"></a>Açıklamalar  
 Sürükle ve bırak işlemi hemen başlamaz. Fare imlecini tarafından belirtilen dikdörtgenden bekler `lpRectStartDrag` veya milisaniye belirtilen sayıda geçtiğinde kadar. Varsa `lpRectStartDrag` olan **NULL**, dikdörtgen bir piksel boyutudur.  
  
 Gecikme süresi bir kayıt defteri anahtarı ayarı tarafından belirtilir. Çağırarak gecikme süresini değiştirebilirsiniz [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) veya [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Gecikme süresi belirtmezseniz, varsayılan değer 200 milisaniye olarak kullanılır. Sürükleme gecikme süresi şekilde depolanır:  
  
-   Windows NT Sürükle gecikme süresi içinde HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay depolanır.  
  
-   Windows 3.x Sürükle gecikme süresi WIN depolanır. INI dosyası [Windows} bölümünde.  
  
-   Windows 95/98 Sürükle gecikme süresi WIN önbelleğe alınmış bir sürümünde depolanır. INI.  
  
 Sürükleme hakkında daha fazla bilgi için gecikme bilgilerini ya da kayıt defterinde depolanır veya. INI dosyası bkz [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) Windows SDK'sındaki.  
  
##  <a name="doverb"></a>  COleClientItem::DoVerb  
 Çağrı `DoVerb` belirtilen fiil yürütülecek.  
  
```  
virtual BOOL DoVerb(
    LONG nVerb,  
    CView* pView,
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `nVerb`  
 Yürütülecek fiili belirtir. Aşağıdakilerden birini içerebilir:  
  
|Değer|Açıklama|Simgesi|  
|-----------|-------------|------------|  
|- 0|Birincil fiil|`OLEIVERB_PRIMARY`|  
|- 1|İkincil fiil|(Hiçbiri)|  
|- 1|Görüntü öğesini düzenlemek için|`OLEIVERB_SHOW`|  
|- 2|Ayrı bir pencerede öğesi düzenleme|`OLEIVERB_OPEN`|  
|- 3|Öğe Gizle|`OLEIVERB_HIDE`|  
  
 -1 genellikle başka bir fiil için diğer ad değerdir. Açık düzenleme desteklenmiyorsa, -2 -1 olarak aynı etkiye sahiptir. Ek değerler için bkz: [Rpc_e_serverfault](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK'sındaki.  
  
 `pView`  
 İşaretçi görünüm penceresine; yerinde etkinleştirme için bu sunucu tarafından kullanılır. Bu parametre olmalıdır **NULL** kapsayıcı uygulama yerinde etkinleştirme izin vermiyorsa.  
  
 `lpMsg`  
 İşaretçi etkinleştirilmesi için öğeyi neden iletisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Fiili başarıyla yürütülürse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrılarını [etkinleştirme](#activate) fiili yürütmek için üye işlevi. Ayrıca, özel durumları yakalar ve bir oluşturulursa kullanıcı için bir ileti kutusu görüntüler.  
  
 Birincil fiili Düzenle olduğunda ve sıfır belirtilen `nVerb` parametresi, sunucu uygulaması başlatılan düzenlenmesi OLE öğesi izin vermek için. Yerinde etkinleştirme kapsayıcı uygulama destekliyorsa, düzenleme yerinde yapılabilir. Kapsayıcı yerinde etkinleştirme (veya açık fiil belirttiyseniz) desteklemiyorsa, sunucuyu ayrı bir pencerede başlatılır ve düzenleme var. yapılabilir. Genellikle, ne zaman kapsayıcı uygulamanın kullanıcısı çift tıklamalar OLE öğesi, birincil fiil değeri `nVerb` parametre, kullanıcının alabilir hangi eylemini belirler. Sunucu yalnızca bir eylem destekliyorsa, ancak ne olursa olsun değer belirtilen söz konusu eylem sürdüğünü `nVerb` parametresi.  
  
##  <a name="draw"></a>  COleClientItem::Draw  
 OLE öğesi belirtilen aygıt bağlamını kullanarak belirtilen sınırlayıcı dikdörtgen çizmek için bu işlevini çağırın.  
  
```  
BOOL Draw(
    CDC* pDC,  
    LPCRECT lpBounds,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 İşaretçi bir [CDC](../../mfc/reference/cdc-class.md) OLE öğesi çizmek için kullanılan nesne.  
  
 `lpBounds`  
 İşaretçi bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesne veya `RECT` , OLE öğesi (içindeki mantıksal birimleri cihaz bağlamı tarafından belirlenen) çizmek sınırlayıcı dikdörtgenini tanımlar yapısı.  
  
 `nDrawAspect`  
 OLE yönünü öğesi, diğer bir deyişle, nasıl görüntüleneceğini belirtir. Varsa `nDrawAspect` kullanarak ayarlamak son Boyut -1'dir [SetDrawAspect](#setdrawaspect) kullanılır. Bu bayrak için olası değerler hakkında daha fazla bilgi için bkz: [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev tarafından oluşturulan OLE öğesi meta dosyası gösterimini kullanabilir [OnDraw](../../mfc/reference/coleserveritem-class.md#ondraw) üye işlevini `COleServerItem`.  
  
 Tipik olarak kullandığınız **çizin** ekran görüntüsü için ekran cihaz bağlamı olarak geçirme `pDC`. Bu durumda, yalnızca ilk iki parametreyi belirtmeniz gerekir.  
  
 `lpBounds` Parametre (göre geçerli eşleme modu) hedef cihaz bağlamı dikdörtgende tanımlar. İşleme resmi ölçeklendirme gerektirebilir ve kapsayıcı uygulamaları tarafından görüntülenen görünümü ve son yazdırılan görüntü arasında ölçeklendirir bir görünüm koymak için kullanılabilir.  
  
 Daha fazla bilgi için bkz: [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) Windows SDK'sındaki.  
  
##  <a name="getactiveview"></a>  COleClientItem::GetActiveView  
 Öğe yerinde etkinleştirilmiş olduğu görünümü döndürür.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görünüm için bir işaretçi; Aksi takdirde **NULL** yerinde etkin değilse.  
  
##  <a name="getcachedextent"></a>  COleClientItem::GetCachedExtent  
 OLE öğesi'nin boyut almak için bu işlevini çağırın.  
  
```  
BOOL GetCachedExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpSize`  
 İşaretçi bir **BOYUTU** yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) boyutu bilgileri alacak nesnesi.  
  
 `nDrawAspect`  
 Alınacak olan sınırları olan OLE öğesi yönünü belirtir. Olası değerler için bkz: [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; OLE öğesi boşsa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev aynı bilgileri sağlar [GetExtent](#getextent). Ancak, çağırabilirsiniz `GetCachedExtent` gibi diğer OLE işleyicileri işlemi sırasında kapsam bilgileri almak için [değiştiğinde](#onchange). Boyutlar bulunan `MM_HIMETRIC` birimleri.  
  
 Bu olasıdır çünkü `GetCachedExtent` kullanır [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318) kullanmak yerine arabirim [IOLE nesnesini](http://msdn.microsoft.com/library/windows/desktop/dd542709) bu öğe kapsamını almak için arabirim. **IViewObject2** COM nesnesi önceki çağrısında kullanılan kapsam bilgileri önbelleğe [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655).  
  
 Daha fazla bilgi için bkz: [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) Windows SDK'sındaki.  
  
##  <a name="getclassid"></a>  COleClientItem::GetClassID  
 Gösterdiği belleğe öğesinin sınıfı kimliği döndürür `pClassID`.  
  
```  
void GetClassID(CLSID* pClassID) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pClassID`  
 İşaretçi türünün tanıtıcısı [CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) sınıf kimliğini almak için Hakkında bilgi için **CLSID**, Windows SDK konusuna bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıf kimliği öğesini düzenler uygulama benzersiz olarak tanımlayan bir 128-bit sayıdır.  
  
 Daha fazla bilgi için bkz: [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) Windows SDK'sındaki.  
  
##  <a name="getclipboarddata"></a>  COleClientItem::GetClipboardData  
 Almak için bu işlevi çağırmak bir `COleDataSource` Pano'ya çağrısıyla konulabilir tüm veri içeren bir nesne [CopyToClipboard](#copytoclipboard) üye işlevi.  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataSource`  
 İşaretçi bir [COleDataSource](../../mfc/reference/coledatasource-class.md) OLE öğesinde bulunan verileri alacak nesnesi.  
  
 `bIncludeLink`  
 **DOĞRU** bağlantı veriler olmalıdır, aksi dahil **FALSE**.  
  
 `lpOffset`  
 Fare imlecini kaynaktan nesnesinin piksel cinsinden uzaklığı.  
  
 `lpSize`  
 Nesnesinin piksel cinsinden boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetClipboardData` Varsayılan uygulaması adlandırılır [OnGetClipboardData](#ongetclipboarddata). Geçersiz kılma `OnGetClipboardData` veri biçimleri tarafından sunulan ek olarak sunmak istiyorsanız `CopyToClipboard`. Bu biçimlerde yerleştirin `COleDataSource` nesne önce veya sonra arama `CopyToClipboard`ve ardından geçirmek `COleDataSource` nesnesini [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) işlevi. Örneğin, kendi kapsayıcı Pano'ya eşlik belgeye OLE öğesi'nin konumda istiyorsanız, bu bilgi geçirme için kendi biçimini tanımlamak ve yerleştirileceği `COleDataSource` çağırmadan önce `CopyToClipboard`.  
  
##  <a name="getdocument"></a>  COleClientItem::GetDocument  
 Belgenin OLE öğeyi içeren bir işaretçi almak için bu işlevini çağırın.  
  
```  
COleDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 OLE öğesi içeren belge için bir işaretçi. **NULL** öğesi belgenin bir bölümünü değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işaretçinin erişime izin `COleDocument` bağımsız değişken olarak geçirilen nesne `COleClientItem` Oluşturucusu.  
  
##  <a name="getdrawaspect"></a>  COleClientItem::GetDrawAspect  
 Çağrı `GetDrawAspect` geçerli "boyutu" ya da görünüm, öğenin belirlemek için üye işlevi.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arasında bir değer `DVASPECT` numaralandırma değerleri için başvurusu listelenen, [SetDrawAspect](#setdrawaspect).  
  
### <a name="remarks"></a>Açıklamalar  
 En boy nasıl öğesi işlenmek üzere belirtir.  
  
##  <a name="getextent"></a>  COleClientItem::GetExtent  
 OLE öğesi'nin boyut almak için bu işlevini çağırın.  
  
```  
BOOL GetExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)- 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpSize`  
 İşaretçi bir **BOYUTU** yapısı veya `CSize` boyutu bilgileri alacak nesnesi.  
  
 `nDrawAspect`  
 Alınacak olan sınırları olan OLE öğesi yönünü belirtir. Olası değerler için bkz: [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; OLE öğesi boşsa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sunucu uygulaması, Microsoft Foundation Class Kitaplığı kullanılarak yazılmış olduğundan, bu işlev neden [OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent) ilgili üye işlevi `COleServerItem` çağrılacak nesnesi. Alınan boyutu son küme boyutundan farklı olabilir Not [SetExtent](#setextent) üye işlevi; tarafından belirtilen boyut `SetExtent` öneri olarak kabul edilir. Boyutlar bulunan `MM_HIMETRIC` birimleri.  
  
> [!NOTE]
>  Çağırmayın `GetExtent` bir OLE işleyicisi işlenmesi sırasında gibi [değiştiğinde](#onchange). Çağrı [GetCachedExtent](#getcachedextent) yerine.  
  
 Daha fazla bilgi için bkz: [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) Windows SDK'sındaki.  
  
##  <a name="geticonfromregistry"></a>  COleClientItem::GetIconFromRegistry  
 Belirli bir CLSID sunucu ile ilişkilendirilen bir simge kaynağı için tanıtıcı almak için bu üye işlevini çağırın.  
  
```  
HICON GetIconFromRegistry() const;  
  
static HICON GetIconFromRegistry(CLSID& clsid);
```  
  
### <a name="parameters"></a>Parametreler  
 `clsid`  
 Simge ile ilişkilendirilen sunucu CLSID referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Simge kaynak için geçerli bir tanıtıcı veya **NULL** sunucunun simgesi ya da varsayılan bir simge bulunamazsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi değil sunucu start veya sunucu zaten çalışıyor olsa bile bir simge dinamik olarak alın. Bunun yerine, bu üye işlevi sunucunun yürütülebilir görüntü açar ve kayıtlı olduğu gibi sunucuyla ilişkili statik simgesini alır.  
  
##  <a name="geticonicmetafile"></a>  COleClientItem::GetIconicMetafile  
 Öğenin simgesini çizmek için kullanılan meta dosyası alır.  
  
```  
HGLOBAL GetIconicMetafile();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa meta dosyası için bir tanıtıcı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli bir simge varsayılan bir simge döndürülür. Bu otomatik olarak MFC/OLE iletişim kutuları tarafından çağrılır ve genellikle doğrudan çağrılmaz.  
  
 Bu işlev de çağırır [SetIconicMetafile](#seticonicmetafile) meta dosyası daha sonra kullanmak için önbelleğe almak için.  
  
##  <a name="getinplacewindow"></a>  COleClientItem::GetInPlaceWindow  
 Çağrı `GetInPlaceWindow` yerinde düzenlemek için öğe açıldı penceresine bir işaretçi almak için üye işlevi.  
  
```  
CWnd* GetInPlaceWindow();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi öğesi'nin yerinde düzenleme penceresine; **NULL** öğesi etkin değilse veya kendi sunucu kullanılamıyorsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yerinde etkin olan öğeleri çağrılmalıdır.  
  
##  <a name="getitemstate"></a>  COleClientItem::GetItemState  
 OLE öğesi'nin geçerli durumunu almak için bu işlevini çağırın.  
  
```  
UINT GetItemState() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **COleClientItem::ItemState** numaralandırılan değeri şunlardan biri olabilir: `emptyState`, **loadedState**, `openState`, `activeState`, `activeUIState`. Bu durumu hakkında daha fazla bilgi için bkz: [kapsayıcılar: istemci öğesi durumları](../../mfc/containers-client-item-states.md).  
  
### <a name="remarks"></a>Açıklamalar  
 OLE öğesi'nin durumu değiştiğinde bildirim almak için kullanmak [değiştiğinde](#onchange) üye işlevi.  
  
 Daha fazla bilgi için bkz: [kapsayıcılar: istemci öğesi durumları](../../mfc/containers-client-item-states.md).  
  
##  <a name="getlaststatus"></a>  COleClientItem::GetLastStatus  
 Son OLE işlem durum kodunu döndürür.  
  
```  
SCODE GetLastStatus() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `SCODE` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye için o return işlevlerini bir **BOOL** değerini **FALSE**, veya diğer üye işlevlerini bu iade **NULL**, `GetLastStatus` daha ayrıntılı hata bilgileri döndürür. Çoğu OLE üye işlevleri daha ciddi hatalar için özel durumlar throw unutmayın. Yorumu belirli bilgileri `SCODE` son döndürülen temel OLE çağrısı bağlıdır bir `SCODE` değeri.  
  
 Daha fazla bilgi için `SCODE`, bkz: [COM hata kodları yapısı](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK belgelerinde.  
  
##  <a name="getlinkupdateoptions"></a>  COleClientItem::GetLinkUpdateOptions  
 OLE öğesi bağlantı-update seçeneğine geçerli değerini almak için bu işlevini çağırın.  
  
```  
OLEUPDATE GetLinkUpdateOptions();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden biri:  
  
- `OLEUPDATE_ALWAYS` Mümkün olduğunda bağlantılı öğesi güncelleştirin. Bu seçenek otomatik bağlantı güncelleştirme radyo düğmesi bağlantıları iletişim kutusunda destekler.  
  
- `OLEUPDATE_ONCALL` Yalnızca kapsayıcı uygulama isteğinden bağlantılı öğede güncelleştirme (zaman [UpdateLink](#updatelink) üye işlevi çağrılır). Bu seçeneği el ile bağlantı güncelleştirme radyo düğmesi bağlantıları iletişim kutusunda destekler.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu gelişmiş bir işlemdir.  
  
 Bu işlev tarafından otomatik olarak çağrılır [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) sınıfı.  
  
 Daha fazla bilgi için bkz: [IOleLink::GetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680100) Windows SDK'sındaki.  
  
##  <a name="gettype"></a>  COleClientItem::GetType  
 OLE öğesi katıştırılmış veya bağlı veya statik belirlemek için bu işlevini çağırın.  
  
```  
OLE_OBJTYPE GetType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretsiz tamsayıya aşağıdaki değerlerden birine sahip:  
  
- `OT_LINK` OLE öğesi bir bağlantıdır.  
  
- `OT_EMBEDDED` OLE öğesi katıştırılır.  
  
- `OT_STATIC` OLE öğesi statik, diğer bir deyişle, değil yerel veri yalnızca sunu verileri içerir ve bu nedenle düzenlenemez.  
  
##  <a name="getusertype"></a>  COleClientItem::GetUserType  
 "Word belgesi" gibi OLE öğesi'nin türünü tanımlayan kullanıcıya görünen dize almak için bu işlevi çağırma  
  
```  
void GetUserType(
    USERCLASSTYPE nUserClassType,  
    CString& rString);
```  
  
### <a name="parameters"></a>Parametreler  
 *nUserClassType*  
 OLE öğesi'nin türünü tanımlayan bir dize istenen türevi belirten bir değer. Bu aşağıdaki değerlerden biri olabilir:  
  
- `USERCLASSTYPE_FULL` Kullanıcıya görüntülenen tam tür adı.  
  
- `USERCLASSTYPE_SHORT` Açılır menüler ve bağlantıları Düzenle iletişim kutusunda kullanmak için kısa ad (en çok 15 karakter).  
  
- `USERCLASSTYPE_APPNAME` Sınıf hizmet uygulamasının adı.  
  
 `rString`  
 Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) OLE öğesi'nin türünü tanımlayan bir dize olduğu döndürülecek nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu çoğunlukla sistem kayıt veritabanında girişidir.  
  
 Kısa ad, tam tür adı istenen ancak mevcut değil ise, bunun yerine kullanılır. OLE öğesi türü için bir giriş kayıt veritabanında bulunamadı veya OLE öğesi türü için kayıtlı hiçbir kullanıcı türleri varsa, daha sonra kullanıcı türü şu anda depolanan OLE öğesi kullanılır. Bu kullanıcı tür adı boş bir dize ise, "Bilinmeyen bir nesneye" kullanılır.  
  
 Daha fazla bilgi için bkz: [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) Windows SDK'sındaki.  
  
##  <a name="isinplaceactive"></a>  COleClientItem::IsInPlaceActive  
 OLE öğesi yerinde etkin olup olmadığını görmek için bu işlevini çağırın.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 OLE öğesi yerinde etkin ise sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğe yerinde düzenlenmekte olan bağlı olarak farklı mantığı yürütmek için yaygın bir durumdur. İşlev geçerli öğesi durumu ya da eşit olup olmadığını denetler `activeState` veya `activeUIState`.  
  
##  <a name="islinkuptodate"></a>  COleClientItem::IsLinkUpToDate  
 OLE öğesi güncel olup olmadığını görmek için bu işlevini çağırın.  
  
```  
BOOL IsLinkUpToDate() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 OLE öğesi güncel ise sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlantılı bir öğe, kaynak belge güncelleştirdiyseniz eski olabilir. İçindeki bağlantılar içeren katıştırılmış öğeyi benzer şekilde güncel hale gelebilir. İşlev OLE öğesinin bir özyinelemeli denetimi yapar. OLE öğeyi güncel olup olmadığı belirlenirken bir güncelleştirme gerçekleştirme olarak olarak pahalı olabileceğini unutmayın.  
  
 Bu tarafından otomatik olarak adlandırılır [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) uygulaması.  
  
 Daha fazla bilgi için bkz: [IOleObject::IsUpToDate](http://msdn.microsoft.com/library/windows/desktop/ms686624) Windows SDK'sındaki.  
  
##  <a name="ismodified"></a>  COleClientItem::IsModified  
 OLE öğesi (son kaydedilişinden değiştirilmiş) kirli olup olmadığını görmek için bu işlevini çağırın.  
  
```  
BOOL IsModified() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 OLE öğesi kirli ise sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [IPersistStorage::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) Windows SDK'sındaki.  
  
##  <a name="isopen"></a>  COleClientItem::IsOpen  
 OLE öğesi açık olup olmadığını görmek için bu işlevi çağırmak; diğer bir deyişle, ayrı bir pencerede çalışan sunucu uygulaması örneği açılır.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 OLE öğesi açıksa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarama deseniyle nesne çizmek ne zaman belirlemek için kullanılır. Açık bir nesne, nesne üzerinde çizilmiş tarama deseniyle olması gerekir. Kullanabileceğiniz bir [CRectTracker](../../mfc/reference/crecttracker-class.md) bunu gerçekleştirmek için nesne.  
  
##  <a name="isrunning"></a>  COleClientItem::IsRunning  
 OLE öğesi çalışır durumda olup olmadığını görmek için bu işlevi çağırmak; diğer bir deyişle, öğe yüklü ve çalışan sunucu uygulamasındaki olup.  
  
```  
BOOL IsRunning() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 OLE öğesi çalışıyorsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [OleIsRunning](http://msdn.microsoft.com/library/windows/desktop/ms688705) Windows SDK'sındaki.  
  
##  <a name="onactivate"></a>  COleClientItem::OnActivate  
 Öğesi, yalnızca bir yerde etkinleştirilmiş olduğunu bildirmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnActivate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı arabirimi kapsayıcı uygulamasında yüklü olduğunu göstermek için sunucunun çalıştığını göstermek için bu işlev çağrılır unutmayın. Bu noktada, nesne etkin kullanıcı arabirimine sahip değildir (değil `activeUIState`). Menüleri veya araç yüklenmemiş. [OnActivateUI](#onactivateui) üye işlevi bu durum oluştuğunda çağrılır.  
  
 Varsayılan Uygulama çağrıları [değiştiğinde](#onchange) üye işleviyle **OLE_CHANGEDSTATE** bir parametre olarak. Bu işlev bir öğe yerinde etkin olduğunda özel işlem yapmak için geçersiz kılar.  
  
##  <a name="onactivateui"></a>  COleClientItem::OnActivateUI  
 Framework çağrıları `OnActivateUI` nesne etkin kullanıcı Arabirimi durumu girildikten zaman.  
  
```  
virtual void OnActivateUI();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne artık menüleri ve araç çubuğundaki yükledi.  
  
 Sunucunun varsayılan uygulama hatırlıyor `HWND` için daha sonra **GetServerWindow** çağrıları.  
  
##  <a name="onchange"></a>  COleClientItem::OnChange  
 Kullanıcı değiştirir, kaydeder veya OLE öğesi kapatır çerçevesi tarafından çağrılır.  
  
```  
virtual void OnChange(
    OLE_NOTIFICATION nCode,  
    DWORD dwParam);
```  
  
### <a name="parameters"></a>Parametreler  
 `nCode`  
 Sunucunun neden bu öğe değiştirildi. Aşağıdaki değerlerden biri olabilir:  
  
- `OLE_CHANGED` OLE öğesi'nin görünümü değiştirilmiştir.  
  
- `OLE_SAVED` OLE öğesi kaydedildi.  
  
- `OLE_CLOSED` OLE öğesi kapatıldı.  
  
- `OLE_CHANGED_STATE` OLE öğesi bir durumdan diğerine değişti.  
  
 `dwParam`  
 Varsa `nCode` olan `OLE_SAVED` veya `OLE_CLOSED`, bu parametre kullanılmaz. Varsa `nCode` olan `OLE_CHANGED`, bu parametre değişti OLE öğesi yönünü belirtir. Olası değerler için bkz: `dwParam` parametresinin [COleClientItem::Draw](#draw). Varsa `nCode` olan `OLE_CHANGED_STATE`, bu parametre bir **COleClientItem::ItemState** değeri numaralandırılan ve girilen durumu açıklar. Aşağıdaki değerlerden biri olabilir: `emptyState`, **loadedState**, `openState`, `activeState`, veya `activeUIState`.  
  
### <a name="remarks"></a>Açıklamalar  
 (Sunucu uygulaması Microsoft Foundation Class Kitaplığı kullanılarak yazılmışsa, bu işlev yanıt olarak adlandırılır `Notify` üye işlevlerini `COleServerDoc` veya `COleServerItem`.) Varsayılan uygulama kapsayıcı belge, değiştirilmiş olarak işaretler `nCode` olan `OLE_CHANGED` veya `OLE_SAVED`.  
  
 İçin `OLE_CHANGED_STATE`, döndürülen geçerli durumu [GetItemState](#getitemstate) çıkarılsın önce bu durumu değişikliği geçerli durumu yani eski durum.  
  
 OLE öğesi'nin durumu değişiklikleri yanıt vermesi için bu işlevi geçersiz kılar. Genellikle öğesinin görünümünü öğesi görüntülendiği alanı geçersiz kılmalarını güncelleştirin. Taban sınıfı uygulama geçersiz kılma başında çağırın.  
  
##  <a name="onchangeitemposition"></a>  COleClientItem::OnChangeItemPosition  
 Yerinde etkinleştirme sırasında OLE öğesi'nin ölçüde değişti kapsayıcı bildirmek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnChangeItemPosition(const CRect& rectPos);
```  
  
### <a name="parameters"></a>Parametreler  
 *rectPos*  
 Öğenin konumuna göre kapsayıcı uygulamanın istemci alanını gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesi'nin konumu başarıyla değiştirilirse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Uygulama çağrıları ve OLE öğesi yeni görünür dikdörtgen belirler [SetItemRects](#setitemrects) yeni değerlerle. Varsayılan uygulama görünür dikdörtgen öğesi için hesaplar ve bu bilgileri sunucuya geçirir.  
  
 Özel kurallar yeniden boyutlandırma/taşıma işlemini uygulamak için bu işlevi geçersiz kılar. MFC'de uygulama yazılmışsa, sunucu olarak adlandırılan çünkü bu çağrı sonuçları [COleServerDoc::RequestPositionChange](../../mfc/reference/coleserverdoc-class.md#requestpositionchange).  
  
##  <a name="ondeactivate"></a>  COleClientItem::OnDeactivate  
 OLE öğesi yerinde etkin durumundan geçiş yaptığında çerçevesi tarafından çağrılır ( `activeState`) yüklenen durumuna yerinde etkinleştirildikten sonra etkinliği anlamına gelir.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 OLE öğesi, kullanıcı arabirimiyle kapsayıcı uygulamadan kaldırılmış kapalı olduğunu belirtmek için bu işlev çağrılır unutmayın. Bu durum oluştuğunda [OnDeactivateUI](#ondeactivateui) üye işlevi çağrılır.  
  
 Varsayılan Uygulama çağrıları [değiştiğinde](#onchange) üye işleviyle **OLE_CHANGEDSTATE** bir parametre olarak. Bu işlev bir yerinde etkin öğeyi devre dışı bırakıldığında özel işlem yapmak için geçersiz kılar. Örneğin, kapsayıcı uygulamanızda undo komutu destekliyorsa, öğeyi devre dışı bırakıldıktan sonra OLE öğede gerçekleştirilen son işlem geri alınamaz olduğunu gösteren geri alma durumu atmak için bu işlevi geçersiz kılabilirsiniz.  
  
##  <a name="ondeactivateandundo"></a>  COleClientItem::OnDeactivateAndUndo  
 Kullanıcı yerinde OLE öğesi etkinleştirdikten sonra undo komutu çalıştırdığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDeactivateAndUndo();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Uygulama çağrıları [DeactivateUI](#deactivateui) sunucunun kullanıcı arabirimini devre dışı bırakmak için. Undo komutu kapsayıcı uygulamanızda uyguluyorsanız, bu işlev geçersiz kılar. Geçersiz kılma, işlevi temel sınıf sürümü çağırın ve uygulamanızda yürütülen son komutu geri al.  
  
 Daha fazla bilgi için bkz: [IOleInPlaceSite::DeactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms683743) Windows SDK'sındaki.  
  
##  <a name="ondeactivateui"></a>  COleClientItem::OnDeactivateUI  
 Yerinde etkinleştirildiği bir öğe kullanıcı devre dışı bırakır çağrılır.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Parametreler  
 `bUndoable`  
 Düzenleme değişiklikleri geri alınamaz olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev kapsayıcı uygulamanın kullanıcı arabirimi menüler ve yerinde etkinleştirme için oluşturulmuş olan diğer denetimleri gizleme özgün durumuna geri yükler.  
  
 Varsa `bUndoable` olan **yanlış**, kapsayıcı undo komutu devre dışı bırakmanız gerekir, çünkü son işlem sunucusu tarafından gerçekleştirilen belirtmektedir kapsayıcı geri alma durumunu yürürlükte atılıyor geri alınamaz değil.  
  
##  <a name="ondiscardundostate"></a>  COleClientItem::OnDiscardUndoState  
 Kullanıcı geri alma durumu OLE öğesi düzenlenirken yoksayar bir eylem gerçekleştirdiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDiscardUndoState();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama hiçbir şey yapmaz. Undo komutu kapsayıcı uygulamanızda uyguluyorsanız, bu işlev geçersiz kılar. Geçersiz kılmada kapsayıcı uygulamanın geri alma durumu atın.  
  
 Sunucunun Microsoft Foundation Class Kitaplığı ile yazılmışsa, sunucunun çağırarak çağrılacak bu işlev neden olabilir [COleServerDoc::DiscardUndoState](../../mfc/reference/coleserverdoc-class.md#discardundostate).  
  
 Daha fazla bilgi için bkz: [IOleInPlaceSite::DiscardUndoState](http://msdn.microsoft.com/library/windows/desktop/ms688642) Windows SDK'sındaki.  
  
##  <a name="ongetclipboarddata"></a>  COleClientItem::OnGetClipboardData  
 Alınacak çerçevesi tarafından çağrılır bir `COleDataSource` Pano'ya ya da bir çağrı tarafından konulabilir tüm veri içeren bir nesne [CopyToClipboard](#copytoclipboard) veya [DoDragDrop](#dodragdrop) üye işlevi.  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>Parametreler  
 `bIncludeLink`  
 Bu ayar **TRUE** panoya bağlantı verilerin kopyalanması gereken durumunda. Bu ayar **FALSE** sunucu uygulamanızı bağlantılar desteklemiyorsa.  
  
 `lpOffset`  
 Nesnesinin piksel cinsinden kaynaktan fare imlecini uzaklığını işaretçi.  
  
 `lpSize`  
 Nesnesinin piksel cinsinden boyutu işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [COleDataSource](../../mfc/reference/coledatasource-class.md) Pano veri içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulamasını çağıran [GetClipboardData](#getclipboarddata).  
  
##  <a name="ongetcliprect"></a>  COleClientItem::OnGetClipRect  
 Framework çağrıları `OnGetClipRect` yerinde düzenlenmekte olan öğe kırpması dikdörtgen koordinatlarını alma üye işlevi.  
  
```  
virtual void OnGetClipRect(CRect& rClipRect);
```  
  
### <a name="parameters"></a>Parametreler  
 *rClipRect*  
 Sınıfın bir nesnesi için işaretçi [CRect](../../atl-mfc-shared/reference/crect-class.md) öğe kırpması dikdörtgen koordinatlarını tutun.  
  
### <a name="remarks"></a>Açıklamalar  
 Piksel cinsinden kapsayıcı uygulama penceresinin istemci alanına göre koordinatlar belirlenir.  
  
 Varsayılan uygulama, yalnızca istemci dikdörtgen öğesi yerinde etkin olduğu görünümünün döndürür.  
  
##  <a name="ongetitemposition"></a>  COleClientItem::OnGetItemPosition  
 Framework çağrıları `OnGetItemPosition` yerinde düzenlenmekte olan öğeyi koordinatlarını alma üye işlevi.  
  
```  
virtual void OnGetItemPosition(CRect& rPosition);
```  
  
### <a name="parameters"></a>Parametreler  
 `rPosition`  
 Başvuru [CRect](../../atl-mfc-shared/reference/crect-class.md) öğesi'nin konumu koordinatları içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Piksel cinsinden kapsayıcı uygulama penceresinin istemci alanına göre koordinatlar belirlenir.  
  
 Bu işlev varsayılan uygulaması hiçbir şey yapmaz. Yerinde düzenleme destekleyen uygulamalar uygulaması gerektirir.  
  
##  <a name="ongetwindowcontext"></a>  COleClientItem::OnGetWindowContext  
 Bir öğe yerinde etkinleştirildiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnGetWindowContext(
    CFrameWnd** ppMainFrame,  
    CFrameWnd** ppDocFrame,  
    LPOLEINPLACEFRAMEINFO lpFrameInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppMainFrame`  
 Ana çerçeve penceresi için bir işaretçi işaretçi.  
  
 `ppDocFrame`  
 Belge çerçeve penceresi için bir işaretçi işaretçi.  
  
 `lpFrameInfo`  
 İşaretçi bir [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) çerçeve penceresi bilgilerinin alacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, OLE öğesi'nin üst penceresi hakkında bilgi almak için kullanılır.  
  
 Kapsayıcı MDI uygulama ise, varsayılan uygulaması için bir işaretçi döndürür [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md) nesnesinde `ppMainFrame` ve etkin bir işaretçi [Cmdıchildwnd](../../mfc/reference/cmdichildwnd-class.md) nesnesinde`ppDocFrame`. Kapsayıcı SDI uygulama ise, varsayılan uygulaması için bir işaretçi döndürür [CFrameWnd](../../mfc/reference/cframewnd-class.md) nesnesinde `ppMainFrame` ve döndürür **NULL** içinde `ppDocFrame`. Varsayılan uygulama aynı zamanda üyeleri doldurur `lpFrameInfo`.  
  
 Yalnızca varsayılan uygulama, uygulamanızın uygun değil, bu işlevi geçersiz; Örneğin, uygulamanızda SDI veya MDI farklı bir kullanıcı arabirimi standardı varsa. Gelişmiş budur geçersiz kılınabilir.  
  
 Daha fazla bilgi için bkz: [IOleInPlaceSite::GetWindowContext](http://msdn.microsoft.com/library/windows/desktop/ms694366) ve [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) Windows SDK'sındaki yapısı.  
  
##  <a name="oninsertmenus"></a>  COleClientItem::OnInsertMenus  
 Boş bir menüsüne kapsayıcı uygulamanın menüleri eklemek için yerinde etkinleştirme sırasında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnInsertMenus(
    CMenu* pMenuShared,  
    LPOLEMENUGROUPWIDTHS lpMenuWidths);
```  
  
### <a name="parameters"></a>Parametreler  
 `pMenuShared`  
 Boş bir menü noktalarına.  
  
 `lpMenuWidths`  
 İşaret eden bir dizi altı için **uzun** kaç menüleri her aşağıdaki menü grupları olmadığını belirten değerleri: dosya, düzenleme, kapsayıcı nesne, penceresinde Yardımı. Kapsayıcı uygulama, 0, 2 ve 4 bu dizinin öğelerine karşılık gelen dosya, kapsayıcı ve pencere menü grupları sorumludur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu menü daha sonra bileşik menü oluşturma kendi menüleri ekler sunucusuna geçirilir. Bu işlev, art arda birkaç bileşik menüleri oluşturmak için çağrılabilir.  
  
 Varsayılan uygulama ekler içine `pMenuShared` yerinde kapsayıcı menüleri; diğer bir deyişle, dosya, kapsayıcı ve pencere menü grupları. [CDocTemplate::SetContainerInfo](../../mfc/reference/cdoctemplate-class.md#setcontainerinfo) bu menü kaynağı ayarlamak için kullanılır. Varsayılan uygulama da öğeleri 0, 2 ve 4'te bir uygun değerleri atar. `lpMenuWidths`menüsü kaynak bağlı olarak. Varsayılan uygulama, uygulamanız için uygun değilse, bu işlevi geçersiz; Örneğin, uygulamanızın kaynakları belge türleri ile ilişkilendirmek için belge şablonları kullanmaz. Bu işlev geçersiz kılarsanız, ayrıca geçersiz kılmanız [OnSetMenu](#onsetmenu) ve [OnRemoveMenus](#onremovemenus). Gelişmiş budur geçersiz kılınabilir.  
  
 Daha fazla bilgi için bkz: [IOleInPlaceFrame::InsertMenus](http://msdn.microsoft.com/library/windows/desktop/ms683987) Windows SDK'sındaki.  
  
##  <a name="onremovemenus"></a>  COleClientItem::OnRemoveMenus  
 Yerinde etkinleştirme sona erdiğinde kapsayıcının menüleri belirtilen bileşik menüsünden kaldırmak için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnRemoveMenus(CMenu* pMenuShared);
```  
  
### <a name="parameters"></a>Parametreler  
 `pMenuShared`  
 İşaret yapılan çağrılar tarafından oluşturulan bileşik menüsüne [OnInsertMenus](#oninsertmenus) üye işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama kaldırır `pMenuShared` olan yerinde kapsayıcı menüler, dosya, kapsayıcı ve pencere menü grupları. Varsayılan uygulama, uygulamanız için uygun değilse, bu işlevi geçersiz; Örneğin, uygulamanızın kaynakları belge türleri ile ilişkilendirmek için belge şablonları kullanmaz. Bu işlev geçersiz kılarsanız, büyük olasılıkla kılmalıdır [OnInsertMenus](#oninsertmenus) ve [OnSetMenu](#onsetmenu) de. Gelişmiş budur geçersiz kılınabilir.  
  
 Alt menüler `pMenuShared` sunucunun art arda çağırdı birden fazla bileşik menü tarafından paylaşılan `OnInsertMenus`. Bu nedenle, tüm alt menüler geçersiz kılmada silmemelisiniz `OnRemoveMenus`; yalnızca bunları detach.  
  
 Daha fazla bilgi için bkz: [IOleInPlaceFrame::RemoveMenus](http://msdn.microsoft.com/library/windows/desktop/ms688685) Windows SDK'sındaki.  
  
##  <a name="onscrollby"></a>  COleClientItem::OnScrollBy  
 Sunucudan gelen isteklere yanıt OLE öğesinde kaydırmak için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnScrollBy(CSize sizeExtent);
```  
  
### <a name="parameters"></a>Parametreler  
 *sizeExtent*  
 Uzaklıklar x ve y yönergeleri kaydırmak için piksel cinsinden belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe kaydırırsanız sıfır olmayan; 0 öğe değil kaydırılan.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, OLE öğesi kısmen görülebilir ve yerinde düzenleme işlemi gerçekleştirilirken görünür bölgesinin dışındaki kullanıcı geçerse, imleç görünür durumda tutmak için bu işlev çağrılır. Varsayılan uygulama hiçbir şey yapmaz. Bu işlev belirli bir miktarda öğesi kaydırmak için geçersiz kılar. Kaydırma sonucunda OLE öğesi görünen dilimini değiştirebileceğinizi unutmayın. Çağrı [SetItemRects](#setitemrects) öğesi'nin görünür dikdörtgen güncelleştirmek için.  
  
 Daha fazla bilgi için bkz: [IOleInPlaceSite::Scroll](http://msdn.microsoft.com/library/windows/desktop/ms690291) Windows SDK'sındaki.  
  
##  <a name="onsetmenu"></a>  COleClientItem::OnSetMenu  
 Yerinde etkinleştirme başlar ve biter iki kez çerçevesi tarafından çağrılır; Bileşik menü ve ikinci kez yüklemeye ilk kez (ile `holemenu` eşit **NULL**) kaldırmak için.  
  
```  
virtual void OnSetMenu(
    CMenu* pMenuShared,  
    HOLEMENU holemenu,  
    HWND hwndActiveObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `pMenuShared`  
 İşaretçi yapılan çağrılar tarafından oluşturulan bileşik menüsüne [OnInsertMenus](#oninsertmenus) üye işlevini ve `InsertMenu` işlevi.  
  
 `holemenu`  
 Tanıtıcı tarafından döndürülen menü tanımlayıcısına **OleCreateMenuDescriptor** işlevi veya **NULL** dağıtırken kodu kaldırılacak ise.  
  
 *hwndActiveObject*  
 OLE öğesi düzenleme penceresine işleyin. Bu düzenleme komutları OLE alacak penceredir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama yükler veya bileşik menüsünü kaldırır ve daha sonra çağırır [OleSetMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms692831) yükleme veya kaldırma dağıtırken kod için işlev. Varsayılan uygulama, uygulamanız için uygun değilse, bu işlev geçersiz kılar. Bu işlev geçersiz kılarsanız, büyük olasılıkla kılmalıdır [OnInsertMenus](#oninsertmenus) ve [OnRemoveMenus](#onremovemenus) de. Gelişmiş budur geçersiz kılınabilir.  
  
 Daha fazla bilgi için bkz: [OleCreateMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms691415), [OleSetMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms692831), ve [IOleInPlaceFrame::SetMenu](http://msdn.microsoft.com/library/windows/desktop/ms693713) Windows SDK'sındaki.  
  
##  <a name="onshowcontrolbars"></a>  COleClientItem::OnShowControlBars  
 Göstermek ve kapsayıcı uygulamanın denetim çubukları gizlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFrameWnd`  
 Kapsayıcı uygulamanın çerçeve penceresi işaretçi. Bu, bir ana çerçeve penceresi veya bir MDI alt pencere olabilir.  
  
 `bShow`  
 Denetim çubukları gösterileceğini veya gizleneceğini olup olmadığını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev çağrısı denetim çubukları durumunda bir değişiklik neden olursa sıfır olmayan; 0 çağrı değişikliğe neden olursa veya `pFrameWnd` kapsayıcısının çerçeve penceresi göstermiyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubukları zaten belirtilen durumda ise bu işlev, 0 döndürür. *bBilgi Göster.* Denetim çubukları gizli değilse bu, örneğin, ortaya çıkabilecek ve `bShow` olan **FALSE**.  
  
 Varsayılan uygulama araç en üst düzey çerçeve penceresinden kaldırır.  
  
##  <a name="onshowitem"></a>  COleClientItem::OnShowItem  
 Tamamen görünür düzenleme sırasında kolaylaştırarak OLE öğesi görüntülenecek çerçevesi tarafından çağrılır.  
  
```  
virtual void OnShowItem();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsayıcı uygulamanızı katıştırılmış öğelerine bağlantılar desteklediğinde kullanılır (diğer bir deyişle, belge sınıfından türetilen durumunda [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)). Bu işlev, yerinde etkinleştirme veya OLE öğesi bağlantı bir kaynaktır ve düzenlemek kullanıcının istediği sırasında çağrılır. Varsayılan uygulama kapsayıcı belge ilk görünümde etkinleştirir. OLE öğesi görünür olmasını sağlamak belge kaydırmak için bu işlevi geçersiz kılar.  
  
##  <a name="onupdateframetitle"></a>  COleClientItem::OnUpdateFrameTitle  
 Çerçeve penceresinin başlık çubuğunu güncelleştirmek için yerinde etkinleştirme sırasında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnUpdateFrameTitle();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu, sıfır olmayan işlevi çerçeve başlık başarıyla güncelleştirildi, aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama çerçeve penceresi başlığı değiştirmez. Farklı çerçeve başlığı, uygulamanız için örneğin istiyorsanız, bu işlevi geçersiz " *sunucu uygulama* - *öğesi* içinde *docname*" (olduğu gibi "Microsoft Excel - rapordaki elektronik tablo. DOC"). Gelişmiş budur geçersiz kılınabilir.  
  
##  <a name="reactivateandundo"></a>  COleClientItem::ReactivateAndUndo  
 OLE öğeyi yeniden etkinleştirin ve yerinde düzenleme sırasında kullanıcı tarafından gerçekleştirilen son işlemi geri almak için bu işlevini çağırın.  
  
```  
BOOL ReactivateAndUndo();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Undo komutu kapsayıcı uygulamanız destekliyorsa, kullanıcı OLE öğesi hemen devre dışı bırakma sonra undo komutu seçerse bu işlevini çağırın.  
  
 Sunucu uygulaması Microsoft Foundation Class kitaplıklarıyla yazılmışsa, bu işlevi çağırmak sunucunun neden [COleServerDoc::OnReactivateAndUndo](../../mfc/reference/coleserverdoc-class.md#onreactivateandundo).  
  
 Daha fazla bilgi için bkz: [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) Windows SDK'sındaki.  
  
##  <a name="release"></a>  COleClientItem::Release  
 OLE öğesi tarafından kullanılan kaynakları temizlemek için bu işlevini çağırın.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwCloseOption`  
 Yüklenen durumuna geri döndüğünde hangi koşullar altında OLE öğesi kaydedildiğinde belirten bayrak. Olası değerler listesi için bkz: [COleClientItem::Close](#close).  
  
### <a name="remarks"></a>Açıklamalar  
 **Yayın** tarafından çağrılır `COleClientItem` yıkıcı.  
  
 Daha fazla bilgi için bkz: [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) Windows SDK'sındaki.  
  
##  <a name="reload"></a>  COleClientItem::Reload  
 Kapatır ve öğeyi yeniden yükler.  
  
```  
BOOL Reload();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `Reload` öğesi için bir çağrı tarafından başka bir türünde bir öğe etkinleştirme sonra işlevi [ActivateAs](#activateas).  
  
##  <a name="run"></a>  COleClientItem::Run  
 Bu öğeyle ilişkili uygulama çalışır.  
  
```  
void Run();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı **çalıştırmak** Madde etkinleştirmeyle önce sunucu uygulamayı başlatmak için üye işlevi. Bu işlem tarafından otomatik olarak yapılır [etkinleştirme](#activate) ve [DoVerb](#doverb), genellikle bu işlevi çağırmak gerekli değildir. Bir öğe özniteliği ayarlamak için sunucu çalıştırmak gerekli değilse bu işlevi çağırmak [SetExtent](#setextent), yürütmeden önce [DoVerb](#doverb).  
  
##  <a name="setdrawaspect"></a>  COleClientItem::SetDrawAspect  
 Çağrı `SetDrawAspect` "boyutu" ya da görünüm, öğenin ayarlamak için üye işlevi.  
  
```  
virtual void SetDrawAspect(DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>Parametreler  
 `nDrawAspect`  
 Arasında bir değer `DVASPECT` numaralandırması. Bu parametre aşağıdaki değerlerden biri olabilir:  
  
- `DVASPECT_CONTENT` Öğesi, katıştırılmış nesne kapsayıcısı içinde olarak görüntülenebilir şekilde gösterilir.  
  
- `DVASPECT_THUMBNAIL` Tarama Aracı içinde görüntülenebilir böylece öğesi bir "küçük" gösterimi işlenir.  
  
- `DVASPECT_ICON` Öğe bir simge ile temsil edilir.  
  
- `DVASPECT_DOCPRINT` Dosya menüsünden Yazdır komutunu kullanarak yazdırılan gibi öğeyi temsil edilir.  
  
### <a name="remarks"></a>Açıklamalar  
 En boy nasıl öğesi tarafından işlenmek üzere belirtir [çizin](#draw) olduğunda bu işlev için varsayılan değer `nDrawAspect` bağımsız değişkeninin değeri kullanılır.  
  
 Bu işlev Simge Değiştir (ve arama Simge Değiştir iletişim kutusu doğrudan diğer iletişim kutuları) otomatik olarak adlandırılır kullanıcı tarafından istendiğinde simge ekran en boy etkinleştirmek için.  
  
##  <a name="setextent"></a>  COleClientItem::SetExtent  
 Ne kadar alan OLE öğesine kullanılabilir olduğunu belirtmek için bu işlevini çağırın.  
  
```  
void SetExtent(
    const CSize& size,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Parametreler  
 `size`  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) boyutu bilgileri içeren nesne.  
  
 `nDrawAspect`  
 Ayarlanacak olan sınırları olan OLE öğesi yönünü belirtir. Olası değerler için bkz: [SetDrawAspect](#setdrawaspect).  
  
### <a name="remarks"></a>Açıklamalar  
 Sunucu uygulaması, Microsoft Foundation Class Kitaplığı kullanılarak yazılmış olduğundan, bu neden [OnSetExtent](../../mfc/reference/coleserveritem-class.md#onsetextent) ilgili üye işlevi `COleServerItem` çağrılacak nesnesi. OLE öğesi sonra görünümünü buna göre ayarlayabilirsiniz. Boyutlar olmalıdır `MM_HIMETRIC` birimleri. OLE öğesi kullanıcı göre yeniden boyutlandırır veya düzeni anlaşma çeşit destekliyorsa bu işlevini çağırın.  
  
 Daha fazla bilgi için bkz: [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) Windows SDK'sındaki.  
  
##  <a name="sethostnames"></a>  COleClientItem::SetHostNames  
 Kapsayıcı uygulama adını ve katıştırılmış OLE öğenin kapsayıcının adını belirtmek için bu işlevini çağırın.  
  
```  
void SetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszHost`  
 Kapsayıcı uygulamanın kullanıcıya görünen adı işaretçi.  
  
 `lpszHostObj`  
 OLE öğeyi içeren kapsayıcısının tanımlayıcı bir dizeyi işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Sunucu uygulaması, Microsoft Foundation Class Kitaplığı kullanılarak yazılmış olduğundan, bu işlev çağrıları [OnSetHostNames](../../mfc/reference/coleserverdoc-class.md#onsethostnames) üye işlevini `COleServerDoc` OLE öğesi içeren belge. OLE öğesi düzenlenirken pencere başlıklarını bu bilgiler kullanılır. Bir kapsayıcı belge yüklendiğinde, her zaman framework belgedeki tüm OLE öğeleri için bu işlevi çağırır. `SetHostNames` yalnızca katıştırılmış öğeleri için geçerlidir. Katıştırılmış OLE öğeyi etkinleştirilmiş her zaman düzenlemek için bu işlevi çağırmak gerekli değildir.  
  
 Bu da otomatik olarak uygulama adı ve belge adı ile bir nesne yüklendiğinde veya farklı bir adla bir dosya kaydedildiğinde çağrılır. Buna uygun olarak, bu işlevi doğrudan çağırmak genellikle gerekli değildir.  
  
 Daha fazla bilgi için bkz: [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) Windows SDK'sındaki.  
  
##  <a name="seticonicmetafile"></a>  COleClientItem::SetIconicMetafile  
 Öğenin simgesini çizmek için kullanılan meta dosyası önbelleğe alır.  
  
```  
BOOL SetIconicMetafile(HGLOBAL hMetaPict);
```  
  
### <a name="parameters"></a>Parametreler  
 `hMetaPict`  
 Öğenin simgesini çizmek için kullanılan meta dosyası için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [GetIconicMetafile](#geticonicmetafile) meta dosyası alınamadı.  
  
 `hMetaPict` Parametre öğesine; kopyalanır bu nedenle, `hMetaPict` çağıran tarafından serbest gerekir.  
  
##  <a name="setitemrects"></a>  COleClientItem::SetItemRects  
 Sınırlayıcı dikdörtgenini veya OLE öğesi görünür dikdörtgen ayarlamak için bu işlevini çağırın.  
  
```  
BOOL SetItemRects(
    LPCRECT lpPosRect = NULL,  
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *lprcPosRect*  
 OLE öğesi kendi üst penceresinde istemci koordinatları göre sınırlarına içeren dikdörtgen işaretçi.  
  
 *lprcClipRect*  
 OLE öğesi kendi üst penceresinde istemci koordinatları göre görünen dilimini sınırlarına içeren dikdörtgen işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde, 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulaması tarafından çağrılır [OnChangeItemPosition](#onchangeitemposition) üye işlevi. Konum veya OLE görünen dilimini öğesi değiştiğinde bu işlevini çağırmanız gerekir. Genellikle bu görünümünüzden 's çağrı anlamına gelir [OnSize](../../mfc/reference/cwnd-class.md#onsize) ve [OnScrollBy](../../mfc/reference/cview-class.md#onscrollby) üye işlevleri.  
  
 Daha fazla bilgi için bkz: [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) Windows SDK'sındaki.  
  
##  <a name="setlinkupdateoptions"></a>  COleClientItem::SetLinkUpdateOptions  
 Belirtilen bağlantılı öğesi sunumu bağlantı-update seçeneğine ayarlamak için bu işlevini çağırın.  
  
```  
void SetLinkUpdateOptions(OLEUPDATE dwUpdateOpt);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwUpdateOpt*  
 Bu öğe için bağlantı güncelleştirme seçeneğini değeri. Bu değerin aşağıdakilerden biri olması gerekir:  
  
- `OLEUPDATE_ALWAYS` Mümkün olduğunda bağlantılı öğesi güncelleştirin. Bu seçenek otomatik bağlantı güncelleştirme radyo düğmesi bağlantıları iletişim kutusunda destekler.  
  
- `OLEUPDATE_ONCALL` Yalnızca kapsayıcı uygulama isteğinden bağlantılı öğede güncelleştirme (zaman [UpdateLink](#updatelink) üye işlevi çağrılır). Bu seçeneği el ile bağlantı güncelleştirme radyo düğmesi bağlantıları iletişim kutusunda destekler.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, bağlantıları iletişim kutusunda kullanıcı tarafından seçilen güncelleştirme seçenekleri değiştirmemeniz gerekir.  
  
 Daha fazla bilgi için bkz: [IOleLink::SetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680120) Windows SDK'sındaki.  
  
##  <a name="setprintdevice"></a>  COleClientItem::SetPrintDevice  
 Bu öğe için yazdırma hedef aygıt değiştirmek için bu işlevini çağırın.  
  
```  
BOOL SetPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL SetPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptd`  
 İşaretçi bir [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) yeni yazdırma hedef aygıt hakkındaki bilgileri içeren veri yapısı. Olabilir **NULL**.  
  
 `ppd`  
 İşaretçi bir [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646940) yeni yazdırma hedef aygıt hakkındaki bilgileri içeren veri yapısı. Olabilir **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bir yazdırma hedef cihaz öğesi için güncelleştirir, ancak sunu önbelleğini yenilemez. Bir öğe için sunu önbelleği güncelleştirmek için arama [UpdateLink](#updatelink).  
  
 Bu işlev bağımsız değişkenleri, hedef aygıtı belirlemek için OLE sistem kullanır bilgiler içerir. **PRINTDLG** yapısı ortak Yazdır iletişim kutusunu başlatmak için Windows kullandığı bilgileri içerir. Kullanıcı iletişim kutusunu kapattıktan sonra Windows bu yapısında kullanıcının seçimlerini hakkında bilgi verir. `m_pd` Üyesi bir [CPrintDialog](../../mfc/reference/cprintdialog-class.md) nesne bir **PRINTDLG** yapısı.  
  
 Bu yapı hakkında daha fazla bilgi için bkz: [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Windows SDK'sındaki.  
  
 Daha fazla bilgi için bkz: [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) Windows SDK'sındaki.  
  
##  <a name="updatelink"></a>  COleClientItem::UpdateLink  
 OLE öğesinin sunu verileri hemen güncelleştirmek için bu işlevini çağırın.  
  
```  
BOOL UpdateLink();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlantılı öğeler için OLE öğesi için yeni bir sunu elde etmek için bağlantı kaynağı işlevi bulur. Bu işlem, zaman alıcı olabilir, bir veya daha fazla sunucu uygulamaları çalıştıran gerektirebilir. Katıştırılmış öğeler için işlev katıştırılmış öğesi güncel olabilecek bağlantılar içerip içermediğini denetleme ve güncelleştiren yinelemeli olarak çalışır. Kullanıcı bağlantıları iletişim kutusunu kullanarak tek tek bağlantıları el ile de güncelleştirebilirsiniz.  
  
 Daha fazla bilgi için bkz: [IOleLink::Update](http://msdn.microsoft.com/library/windows/desktop/ms692660) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MFCBIND](../../visual-cpp-samples.md)   
 [MFC örnek OCLIENT](../../visual-cpp-samples.md)   
 [CDocItem sınıfı](../../mfc/reference/cdocitem-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleServerItem Sınıfı](../../mfc/reference/coleserveritem-class.md)
