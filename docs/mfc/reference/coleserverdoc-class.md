---
title: COleServerDoc sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleServerDoc
- AFXOLE/COleServerDoc
- AFXOLE/COleServerDoc::COleServerDoc
- AFXOLE/COleServerDoc::ActivateDocObject
- AFXOLE/COleServerDoc::ActivateInPlace
- AFXOLE/COleServerDoc::DeactivateAndUndo
- AFXOLE/COleServerDoc::DiscardUndoState
- AFXOLE/COleServerDoc::GetClientSite
- AFXOLE/COleServerDoc::GetEmbeddedItem
- AFXOLE/COleServerDoc::GetItemClipRect
- AFXOLE/COleServerDoc::GetItemPosition
- AFXOLE/COleServerDoc::GetZoomFactor
- AFXOLE/COleServerDoc::IsDocObject
- AFXOLE/COleServerDoc::IsEmbedded
- AFXOLE/COleServerDoc::IsInPlaceActive
- AFXOLE/COleServerDoc::NotifyChanged
- AFXOLE/COleServerDoc::NotifyClosed
- AFXOLE/COleServerDoc::NotifyRename
- AFXOLE/COleServerDoc::NotifySaved
- AFXOLE/COleServerDoc::OnDeactivate
- AFXOLE/COleServerDoc::OnDeactivateUI
- AFXOLE/COleServerDoc::OnDocWindowActivate
- AFXOLE/COleServerDoc::OnResizeBorder
- AFXOLE/COleServerDoc::OnShowControlBars
- AFXOLE/COleServerDoc::OnUpdateDocument
- AFXOLE/COleServerDoc::RequestPositionChange
- AFXOLE/COleServerDoc::SaveEmbedding
- AFXOLE/COleServerDoc::ScrollContainerBy
- AFXOLE/COleServerDoc::UpdateAllItems
- AFXOLE/COleServerDoc::CreateInPlaceFrame
- AFXOLE/COleServerDoc::DestroyInPlaceFrame
- AFXOLE/COleServerDoc::GetDocObjectServer
- AFXOLE/COleServerDoc::OnClose
- AFXOLE/COleServerDoc::OnExecOleCmd
- AFXOLE/COleServerDoc::OnFrameWindowActivate
- AFXOLE/COleServerDoc::OnGetEmbeddedItem
- AFXOLE/COleServerDoc::OnReactivateAndUndo
- AFXOLE/COleServerDoc::OnSetHostNames
- AFXOLE/COleServerDoc::OnSetItemRects
- AFXOLE/COleServerDoc::OnShowDocument
helpviewer_keywords:
- COleServerDoc [MFC], COleServerDoc
- COleServerDoc [MFC], ActivateDocObject
- COleServerDoc [MFC], ActivateInPlace
- COleServerDoc [MFC], DeactivateAndUndo
- COleServerDoc [MFC], DiscardUndoState
- COleServerDoc [MFC], GetClientSite
- COleServerDoc [MFC], GetEmbeddedItem
- COleServerDoc [MFC], GetItemClipRect
- COleServerDoc [MFC], GetItemPosition
- COleServerDoc [MFC], GetZoomFactor
- COleServerDoc [MFC], IsDocObject
- COleServerDoc [MFC], IsEmbedded
- COleServerDoc [MFC], IsInPlaceActive
- COleServerDoc [MFC], NotifyChanged
- COleServerDoc [MFC], NotifyClosed
- COleServerDoc [MFC], NotifyRename
- COleServerDoc [MFC], NotifySaved
- COleServerDoc [MFC], OnDeactivate
- COleServerDoc [MFC], OnDeactivateUI
- COleServerDoc [MFC], OnDocWindowActivate
- COleServerDoc [MFC], OnResizeBorder
- COleServerDoc [MFC], OnShowControlBars
- COleServerDoc [MFC], OnUpdateDocument
- COleServerDoc [MFC], RequestPositionChange
- COleServerDoc [MFC], SaveEmbedding
- COleServerDoc [MFC], ScrollContainerBy
- COleServerDoc [MFC], UpdateAllItems
- COleServerDoc [MFC], CreateInPlaceFrame
- COleServerDoc [MFC], DestroyInPlaceFrame
- COleServerDoc [MFC], GetDocObjectServer
- COleServerDoc [MFC], OnClose
- COleServerDoc [MFC], OnExecOleCmd
- COleServerDoc [MFC], OnFrameWindowActivate
- COleServerDoc [MFC], OnGetEmbeddedItem
- COleServerDoc [MFC], OnReactivateAndUndo
- COleServerDoc [MFC], OnSetHostNames
- COleServerDoc [MFC], OnSetItemRects
- COleServerDoc [MFC], OnShowDocument
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
ms.openlocfilehash: 3069c5f53b37984cbeae8bee1379bb8b0c36ccc3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285288"
---
# <a name="coleserverdoc-class"></a>COleServerDoc sınıfı

OLE sunucu belgeleri için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleServerDoc::COleServerDoc](#coleserverdoc)|Oluşturur bir `COleServerDoc` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleServerDoc::ActivateDocObject](#activatedocobject)|İlişkili DocObject belge etkinleştirir.|
|[COleServerDoc::ActivateInPlace](#activateinplace)|Yerinde düzenleme için belgenin etkinleştirir.|
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|Sunucunun kullanıcı arabirimini devre dışı bırakır.|
|[COleServerDoc::DiscardUndoState](#discardundostate)|Geri alma durumunu bilgilerini atar.|
|[COleServerDoc::GetClientSite](#getclientsite)|Bağlantılı bir işaretçi alır `IOleClientSite` arabirimi.|
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|Tüm belgeyi temsil eden bir öğeye bir işaretçi döndürür.|
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|Yerinde düzenleme için geçerli kırpma dikdörtgenini döndürür.|
|[COleServerDoc::GetItemPosition](#getitemposition)|Yerinde düzenleme için kapsayıcı uygulamasının istemci alanına göre geçerli konumu dikdörtgen döndürür.|
|[COleServerDoc::GetZoomFactor](#getzoomfactor)|Yakınlaştırma faktörünü piksel cinsinden döndürür.|
|[COleServerDoc::IsDocObject](#isdocobject)|Belge DocObject olup olmadığını belirler.|
|[COleServerDoc::IsEmbedded](#isembedded)|Belge kapsayıcısı belgeye katıştırılmış veya tek başına çalışan olup olmadığını belirtir.|
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|Öğe şu anda yerinde etkinleştirilmişse, TRUE döndürür.|
|[COleServerDoc::NotifyChanged](#notifychanged)|Kapsayıcılar, kullanıcı belgenin değiştiğini bildirir.|
|[COleServerDoc::NotifyClosed](#notifyclosed)|Kapsayıcılar, kullanıcı belgenin kapattı bildirir.|
|[COleServerDoc::NotifyRename](#notifyrename)|Kapsayıcılar, kullanıcının belgeyi yeniden adlandırılmış bildirir.|
|[COleServerDoc::NotifySaved](#notifysaved)|Kapsayıcılar, kullanıcı belgenin kaydetti bildirir.|
|[COleServerDoc::OnDeactivate](#ondeactivate)|Kullanıcı yerinde etkin bir öğe bıraktığında framework tarafından çağırılır.|
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|Denetimleri ve yerinde etkinleştirme için oluşturulan diğer kullanıcı arabirimi öğelerini yok etmek için framework tarafından çağırılır.|
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|Kapsayıcının belge çerçeve penceresini etkinleştirmek veya framework tarafından çağırılır.|
|[COleServerDoc::OnResizeBorder](#onresizeborder)|Kapsayıcı uygulamasının çerçeve penceresini ya da belge penceresini yeniden boyutlandırıldığında framework tarafından çağırılır.|
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|Yerinde düzenleme için Denetim çubukları gizlemek veya göstermek için framework tarafından çağırılır.|
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|Gömülü bir öğe olan bir sunucu Belge kaydedildiğinde kapsayıcının öğenin kopyasını güncelleştirme framework tarafından çağırılır.|
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|Yerinde düzenleme çerçevesinin konumunu değiştirir.|
|[COleServerDoc::SaveEmbedding](#saveembedding)|Belgeyi kaydetmek için kapsayıcı uygulaması gösterir.|
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|Kapsayıcı belge kaydırır.|
|[COleServerDoc::UpdateAllItems](#updateallitems)|Kapsayıcılar, kullanıcı belgenin değiştiğini bildirir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|Yerinde düzenleme için bir çerçeve penceresi oluşturmak için framework tarafından çağırılır.|
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|Yerinde düzenleme için bir çerçeve penceresini yok etmek için framework tarafından çağırılır.|
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|Bu işlev, yeni bir geçersiz kılma `CDocObjectServer` nesne ve bu belgenin DocObject kapsayıcı olduğunu gösterir.|
|[COleServerDoc::OnClose](#onclose)|Bir kapsayıcı belgeyi kapatmaya istediğinde framework tarafından çağırılır.|
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|Belirtilen komutu yürütür ya da komut için yardımı görüntüler.|
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|Kapsayıcının çerçeve penceresini etkinleştirmek veya framework tarafından çağırılır.|
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|Almak için çağrılan bir `COleServerItem` , tüm belgeyi temsil eder; gömülü bir öğe almak için kullanılır. Gerekli uygulama.|
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|Yerinde düzenleme sırasında yapılan değişiklikleri geri almak için framework tarafından çağırılır.|
|[COleServerDoc::OnSetHostNames](#onsethostnames)|Pencere Başlığı katıştırılmış nesne için bir kapsayıcı kümeleri kullanırken framework tarafından çağırılır.|
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|Kapsayıcı uygulamasının penceresinde yerinde düzenleme çerçeve penceresi konumlandırmak için framework tarafından çağırılır.|
|[COleServerDoc::OnShowDocument](#onshowdocument)|Belge gizlemek veya göstermek için framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Sunucu belgesinin içerebilir [Coleserverıtem](../../mfc/reference/coleserveritem-class.md) sunucu arabirimi gömülü veya bağlantılı öğeleri temsil eden nesneleri. Sunucu uygulaması gömülü bir öğe düzenlemek için bir kapsayıcı tarafından başlatıldığında, öğenin kendi sunucu belgesi olarak yüklenir; `COleServerDoc` nesnesini içeren tek `COleServerItem` tüm belgenin oluşan nesnesi. Bağlantılı bir öğeyi düzenlemek için bir kapsayıcı tarafından bir sunucu uygulaması başlatıldığında, var olan bir belgeyi diskten yüklenir; Belge içeriğini bir kısmı, bağlantılı öğe belirtmek için vurgulanır.

`COleServerDoc` nesneleri ayrıca öğeleri içeren [Coleclientıtem](../../mfc/reference/coleclientitem-class.md) sınıfı. Bu, kapsayıcı-sunucu uygulamaları oluşturmanıza olanak sağlar. Framework düzgün bir şekilde depolamak için işlevler sağlayan `COleClientItem` bakım öğeyi `COleServerItem` nesneleri.

Sunucu uygulamasının bağlantıları desteklemiyorsa, sunucu belgesi her zaman bir belge olarak tüm katıştırılmış nesneyi temsil eden tek bir sunucu öğesi içerir. Sunucu uygulamasının bağlantıları destekliyorsanız, bu seçim panoya kopyalandı her zaman bir sunucu öğesi oluşturmanız gerekir.

Kullanılacak `COleServerDoc`, bir sınıf türetmeniz ve uygulama [OnGetEmbeddedItem](#ongetembeddeditem) katıştırılmış öğeler desteklemek üzere sunucunuzu sağlayan üye işlevi. Öğesinden bir sınıf türetin `COleServerItem` öğeleri belgelerinize uygulamak ve bu sınıfın nesneleri döndürmek için `OnGetEmbeddedItem`.

Bağlantılı öğeler desteklemek için `COleServerDoc` sağlar [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) üye işlevi. Varsayılan uygulama veya belge öğeleri yönetme kendi yolu varsa bunu geçersiz kılmasına kullanabilirsiniz.

Bir gereksinim duyduğunuz `COleServerDoc`-uygulamanızın desteklediği her sunucu türünü belge için türetilmiş sınıf. Sunucu uygulamanızı çalışma sayfaları ve grafikleri destekler, örneğin, iki gerekiyorsa, `COleServerDoc`-türetilmiş sınıflar.

Sunucuları hakkında daha fazla bilgi için bkz [sunucuları: Sunucu uygulama](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

`COleServerDoc`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="activatedocobject"></a>  COleServerDoc::ActivateDocObject

İlişkili DocObject belge etkinleştirir.

```
void ActivateDocObject();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `COleServerDoc` etkin belgeler (DocObjects da bilinir) desteklemez. Bu desteğini etkinleştirmek için bkz: [GetDocObjectServer](#getdocobjectserver) ve sınıf [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md).

##  <a name="activateinplace"></a>  COleServerDoc::ActivateInPlace

Yerinde düzenleme için öğenin etkinleştirir.

```
BOOL ActivateInPlace();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0, öğesi tam olarak açık olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, yerinde etkinleştirme için gerekli tüm işlemleri gerçekleştirir. Yerinde çerçeve penceresi oluşturur, etkinleştirir ve öğesine boyutları, paylaşılan menüleri ve diğer denetimleri ayarlar, görünüme öğesi gelene ve yerinde çerçeve penceresine odak noktası ayarlar.

Bu işlev varsayılan uygulaması tarafından çağrılır [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow). Yerinde etkinleştirme (örneğin, yürütme) için başka bir eylem uygulamanız destekliyorsa, bu işlevi çağırın.

##  <a name="coleserverdoc"></a>  COleServerDoc::COleServerDoc

Oluşturur bir `COleServerDoc` OLE sistem DLL'lerini bağlanmadan nesne.

```
COleServerDoc();
```

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız [COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) iletişimleri OLE ile açın. Kullanıyorsanız [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) uygulamanızın `COleLinkingDoc::Register` sizin tarafınızdan için çağrılır `COleLinkingDoc`'s uygulaması `OnNewDocument`, `OnOpenDocument`, ve `OnSaveDocument`.

##  <a name="createinplaceframe"></a>  COleServerDoc::CreateInPlaceFrame

Framework, yerinde düzenleme için bir çerçeve penceresi oluşturmak için bu işlevi çağırır.

```
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Kapsayıcı uygulamanın ana pencere işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yerinde çerçeve penceresini ya da başarısız olursa NULL bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama belge şablonunda belirtilen bilgileri kare oluşturmak için kullanır. Kullanılan görünüm, belge için oluşturulan ilk görünümdür. Bu görünüm geçici olarak özgün çerçevesinden kullanımdan çıkarıldı ve yeni oluşturulan çerçeveye bağlı.

Bu gelişmiş bir, geçersiz kılınabilir.

##  <a name="deactivateandundo"></a>  COleServerDoc::DeactivateAndUndo

Uygulamanızın desteklediği Geri Al ve kullanıcı bir öğeyi etkinleştirdikten sonra ancak düzenlemeden önce geri alma seçer, bu işlevi çağırın.

```
BOOL DeactivateAndUndo();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulamasını Microsoft Foundation Class Kitaplığı kullanılarak yazılmış, bu işlev çağrılırken neden [COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) çağrılacak, sunucunun kullanıcı arabirimini bırakır.

##  <a name="destroyinplaceframe"></a>  COleServerDoc::DestroyInPlaceFrame

Framework, bir yerinde çerçeve penceresini yok etmek ve sunucu durumuna yerinde etkinleştirme önce uygulamanın belge penceresine dönmek için bu işlevi çağırır.

```
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>Parametreler

*pFrameWnd*<br/>
Yok edilecek yerinde çerçeve işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu gelişmiş bir, geçersiz kılınabilir.

##  <a name="discardundostate"></a>  COleServerDoc::DiscardUndoState

Kullanıcı geri alınamaz bir düzenleme işlemi gerçekleştirdiğinde, geri alma-durum bilgilerini atmak kapsayıcı uygulaması zorlamak için bu işlevi çağırın.

```
BOOL DiscardUndoState();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, böylece Geri Al'ı destekleyen sunucular ücretsiz kullanılamaz geri alma durumunu bilgi tarafından tüketilen kaynaklar sağlanır.

##  <a name="getclientsite"></a>  COleServerDoc::GetClientSite

Bağlantılı bir işaretçi alır `IOleClientSite` arabirimi.

```
LPOLECLIENTSITE GetClientSite() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bağlantılı bir işaretçi alır [IOleClientSite](/windows/desktop/api/oleidl/nn-oleidl-ioleclientsite) arabirimi.

##  <a name="getdocobjectserver"></a>  COleServerDoc::GetDocObjectServer

Bu işlev, yeni bir geçersiz kılma `CDocObjectServer` öğesini ve ona bir işaretçi döndürür.

```
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```

### <a name="parameters"></a>Parametreler

*pDocSite*<br/>
İşaretçi `IOleDocumentSite` arabirimi bu belge, sunucuya bağlanır.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CDocObjectServer`; İşlem başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

DocObject sunucusuna etkinleştirildiğinde, bir NULL olmayan işaretçi dönüş istemci DocObjects destekleyebildiğini gösterir. Varsayılan uygulama, NULL döndürür.

Tipik bir uygulaması DocObjects destekleyen bir belge için yalnızca yeni bir tahsis `CDocObjectServer` çağırana döndürmesi ve nesne. Örneğin:

[!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]

##  <a name="getembeddeditem"></a>  COleServerDoc::GetEmbeddedItem

Tüm belgeyi temsil eden bir öğeye bir işaretçi almak için bu işlevi çağırın.

```
COleServerItem* GetEmbeddedItem();
```

### <a name="return-value"></a>Dönüş Değeri

Tüm belgeyi temsil eden bir öğe için bir işaretçi; İşlem başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Çağrı [COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem), varsayılan uygulama içermeyen bir sanal işlev.

##  <a name="getitemcliprect"></a>  COleServerDoc::GetItemClipRect

Çağrı `GetItemClipRect` yerinde düzenlenmekte olan öğe dikdörtgen kırpımını koordinatlarını almak için üye işlevi.

```
void GetItemClipRect(LPRECT lpClipRect) const;
```

### <a name="parameters"></a>Parametreler

*lpClipRect*<br/>
İşaretçi bir `RECT` yapısı veya `CRect` öğe dikdörtgen kırpımını koordinatlarını almak için nesne.

### <a name="remarks"></a>Açıklamalar

Piksel kapsayıcı uygulama penceresinin istemci alanına göre koordinatlar belirlenir.

Çizim dışında dikdörtgen kırpımını oluşmamalıdır. Genellikle, çizim otomatik olarak sınırlıdır. Kullanıcı belgeyi görünür bölümünün dışında kaydırılan olup olmadığını belirlemek için bu işlevi kullanın. Bu durumda, kapsayıcı belgeyi bir çağrı yoluyla gerektiği şekilde Kaydır [ScrollContainerBy](#scrollcontainerby).

##  <a name="getitemposition"></a>  COleServerDoc::GetItemPosition

Çağrı `GetItemPosition` yerinde düzenlenmekte olan öğenin koordinatlarını almak için üye işlevi.

```
void GetItemPosition(LPRECT lpPosRect) const;
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
İşaretçi bir `RECT` yapısı veya `CRect` öğenin koordinatlarını almak için nesne.

### <a name="remarks"></a>Açıklamalar

Piksel kapsayıcı uygulama penceresinin istemci alanına göre koordinatlar belirlenir.

Öğenin konumunu öğesi olduğu görünür (veya görünmez) kapsam belirlemek için geçerli dikdörtgen kırpımını ile karşılaştırılabilir ekranında.

##  <a name="getzoomfactor"></a>  COleServerDoc::GetZoomFactor

`GetZoomFactor` Üye işlevi, bir öğenin yerinde düzenleme için etkinleştirildi "yakınlaştırma faktörünü" belirler.

```
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,
    LPSIZE lpSizeDenom = NULL,
    LPCRECT lpPosRect = NULL) const;
```

### <a name="parameters"></a>Parametreler

*lpSizeNum*<br/>
Sınıfın bir nesnesi için işaretçi `CSize` yakınlaştırma faktörünün pay tutun. NULL olabilir.

*lpSizeDenom*<br/>
Sınıfın bir nesnesi için işaretçi `CSize` yakınlaştırma faktörünün paydası tutun. NULL olabilir.

*lpPosRect*<br/>
Sınıfın bir nesnesi için işaretçi `CRect` öğenin yeni konuma, yani açıklar. Bu bağımsız değişken NULL ise, işlev öğenin geçerli konumu kullanır.

### <a name="return-value"></a>Dönüş Değeri

Öğe yerinde için etkinleştirilmişse sıfır olmayan düzenleme ve kendi yakınlaştırma faktörünü olduğunu (1:1); %100 dışında Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yakınlaştırma faktörünü piksel cinsinden geçerli kapsamı öğenin boyutuna oranı ' dir. Kapsayıcı uygulamasını öğesinin içeriği, doğal kapsamı ayarlı değil durumunda (tarafından belirlenen şekilde [COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) kullanılır.

Pay ve paydası öğenin "yakınlaştırma faktörünü.", işlev ilk iki bağımsız değişkenlerinden ayarlar Öğe yerinde düzenlenmekte olan değil, işlev bu bağımsız değişkenler % 100 (veya 1:1) varsayılan değerine ayarlar ve sıfır döndürür. Daha fazla bilgi için bkz. Teknik Not 40 [MFC/OLE yerinde yeniden boyutlandırma ve yakınlaştırma](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).

##  <a name="isdocobject"></a>  COleServerDoc::IsDocObject

Belge DocObject olup olmadığını belirler.

```
BOOL IsDocObject() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belge DocObject ise TRUE; Aksi durumda FALSE.

##  <a name="isembedded"></a>  COleServerDoc::IsEmbedded

Çağrı `IsEmbedded` belgenin bir kapsayıcıda katıştırılmış bir nesneyi temsil edip etmediğini belirlemek için üye işlevi.

```
BOOL IsEmbedded() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gösterimiyse `COleServerDoc` nesnesi olan bir nesneyi temsil eden bir belge katıştırılmış bir kapsayıcıda; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir bağlantı olarak bir kapsayıcı uygulama tarafından yönetilen ancak bir dosyasından yüklenen belge ekli değil. Gömülü olması için bir kapsayıcı belgeye gömülü bir belge olarak kabul edilir.

##  <a name="isinplaceactive"></a>  COleServerDoc::IsInPlaceActive

Çağrı `IsInPlaceActive` öğe şu anda yerinde etkin durumda olup olmadığını belirlemek için üye işlevi.

```
BOOL IsInPlaceActive() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gösterimiyse `COleServerDoc` nesnedir yerinde etkin; Aksi durumda 0.

##  <a name="notifychanged"></a>  COleServerDoc::NotifyChanged

Belge değişti belgeye bağlı tüm bağlantılı öğeler bildirmek için bu işlevi çağırın.

```
void NotifyChanged();
```

### <a name="remarks"></a>Açıklamalar

Genellikle, kullanıcı sunucu belgesinin boyutları gibi bazı genel öznitelik değiştirdikten sonra bu işlevi çağırın. OLE öğesini belgeye otomatik bir bağlantıyla bağlıysa, öğe değişiklikleri yansıtacak şekilde güncelleştirilir. Microsoft Foundation Class Kitaplığı ile kapsayıcı uygulamalarında [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevinin `COleClientItem` çağrılır.

> [!NOTE]
>  Bu işlev, OLE 1 ile uyumluluk için dahildir. Yeni uygulamalar kullanması gereken [UpdateAllItems](#updateallitems).

##  <a name="notifyclosed"></a>  COleServerDoc::NotifyClosed

Belge kapatıldı kapsayıcılarda bildirmek için bu işlevi çağırın.

```
void NotifyClosed();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı Dosya menüsünden Kapat komutunu seçtiğinde `NotifyClosed` tarafından çağrılır `COleServerDoc`'s uygulaması [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) üye işlevi. Microsoft Foundation Class Kitaplığı ile kapsayıcı uygulamalarında [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevinin `COleClientItem` çağrılır.

##  <a name="notifyrename"></a>  COleServerDoc::NotifyRename

Sunucu belgesinin kullanıcı yeniden adlandırır sonra bu işlevi çağırın.

```
void NotifyRename(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Parametreler

*lpszNewName*<br/>
Sunucu belgesinin yeni adını belirten bir dize işaretçisi; Bu genellikle tam nitelikli bir yoludur.

### <a name="remarks"></a>Açıklamalar

Kullanıcı Dosya menüsünden Kaydet komutunu seçtiğinde `NotifyRename` tarafından çağrılır `COleServerDoc`'s uygulaması [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) üye işlevi. Bu işlev, OLE sistemi sırayla kapsayıcıları bildir DLL'leri bildirir. Microsoft Foundation Class Kitaplığı ile kapsayıcı uygulamalarında [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevinin `COleClientItem` çağrılır.

##  <a name="notifysaved"></a>  COleServerDoc::NotifySaved

Sunucu belgesinin kullanıcı kaydettikten sonra bu işlevi çağırın.

```
void NotifySaved();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı Dosya menüsünden Kaydet komutunu seçtiğinde `NotifySaved` sizin tarafınızdan için adlı `COleServerDoc`'s uygulaması [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument). Bu işlev, OLE sistemi sırayla kapsayıcıları bildir DLL'leri bildirir. Microsoft Foundation Class Kitaplığı ile kapsayıcı uygulamalarında [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevinin `COleClientItem` çağrılır.

##  <a name="onclose"></a>  COleServerDoc::OnClose

Bir kapsayıcı sunucu belgesinin kapatılması istediğinde framework tarafından çağırılır.

```
virtual void OnClose(OLECLOSE dwCloseOption);
```

### <a name="parameters"></a>Parametreler

*dwCloseOption*<br/>
OLECLOSE sabit bir değer. Bu parametre aşağıdaki değerlerden biri olabilir:

- OLECLOSE_SAVEIFDIRTY değiştirildi dosyanın kaydedilir.

- Kaydedilen olmadan OLECLOSE_NOSAVE dosya kapatılır.

- OLECLOSE_PROMPTSAVE varsa dosya değiştirildi, kullanıcı kaydetme hakkında istenir.

### <a name="remarks"></a>Açıklamalar

Varsayılan Uygulama çağrıları `CDocument::OnCloseDocument`.

Daha fazla bilgi ve ek değerler için bkz. [OLECLOSE](/windows/desktop/api/oleidl/ne-oleidl-tagoleclose) Windows SDK.

##  <a name="ondeactivate"></a>  COleServerDoc::OnDeactivate

Kullanıcı şu anda yerinde etkin bir gömülü veya bağlantılı bir öğe bıraktığında framework tarafından çağırılır.

```
virtual void OnDeactivate();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, kapsayıcı uygulamasının kullanıcı arabirimini özgün durumuna geri yükler ve menüler ve yerinde etkinleştirme için oluşturulan diğer denetimleri yok eder.

Geri alma durumu bilgilerini koşulsuz olarak bu noktada yayımlanması.

Daha fazla bilgi için bkz [etkinleştirme](../../mfc/activation-cpp.md)...

##  <a name="ondeactivateui"></a>  COleServerDoc::OnDeactivateUI

Kullanıcı yerinde etkin bir öğe bıraktığında çağrılır.

```
virtual void OnDeactivateUI(BOOL bUndoable);
```

### <a name="parameters"></a>Parametreler

*bUndoable*<br/>
Düzenleme değişiklikleri geri yüklenemeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev kapsayıcı uygulamasının kullanıcı arabirimi, menüler ve yerinde etkinleştirme için oluşturulan diğer denetimleri gizleme özgün durumuna geri yükler.

Her zaman çerçevesi ayarlar *bUndoable* false. Sunucunun geri destekliyorsa ve Al. geri alınabilecek bir işlem yoktur, bir taban sınıfı uygulama ile çağrı *bUndoable* TRUE olarak ayarlayın.

##  <a name="ondocwindowactivate"></a>  COleServerDoc::OnDocWindowActivate

Framework etkinleştirme veya devre dışı yerinde düzenleme için bir belge penceresi için bu işlevi çağırır.

```
virtual void OnDocWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*bActivate*<br/>
Belge penceresinde etkin veya devre dışı bırakılması olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan Uygulama Çerçevesi düzeyinde kullanıcı arabirimi öğeleri uygun şekilde ekler veya kaldırır. Öğenizi içeren belge etkin veya devre dışı olduğunda ek eylemleri gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.

Daha fazla bilgi için bkz [etkinleştirme](../../mfc/activation-cpp.md)...

##  <a name="onexecolecmd"></a>  COleServerDoc::OnExecOleCmd

Framework, belirtilen bir komutu çalıştırmak ya da komut için Yardım görüntülemek için bu işlevi çağırır.

```
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,
    DWORD nCmdID,
    DWORD nCmdExecOpt,
    VARIANTARG* pvarargIn,
    VARIANTARG* pvarargOut);
```

### <a name="parameters"></a>Parametreler

*pguidCmdGroup*<br/>
Bir komut kümesini tanımlayan bir GUID için bir işaretçi. Varsayılan komut grubu belirtmek için boş olabilir.

*nCmdID*<br/>
Yürütülecek komut. Tarafından tanımlanan grubunda olmalıdır *pguidCmdGroup*.

*nCmdExecOut*<br/>
Nesne yolu komutu, bir veya daha fazla aşağıdaki değerleri OLECMDEXECOPT sabit listesinden alınmış getirmesi gerekir:

OLECMDEXECOPT_DODEFAULT

OLECMDEXECOPT_PROMPTUSER

OLECMDEXECOPT_DONTPROMPTUSER

OLECMDEXECOPT_SHOWHELP

*pvarargIn*<br/>
Komut için giriş bağımsız değişkenleri içeren bir VARIANTARG işaretçisi. NULL olabilir.

*pvarargOut*<br/>
Komuttan çıkış almak için bir VARIANTARG işaretçi dönüş değerleri. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa; başarılıysa S_OK döndürür Aksi takdirde biri, aşağıdaki hata kodları:

|Değer|Açıklama|
|-----------|-----------------|
|E_UNEXPECTED|Beklenmeyen bir hata oluştu|
|E_FAIL|Hata oluştu|
|E_NOTIMPL|MFC gösterir kendisini çevirin ve komut gönderme denemelidir|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup* NULL değil ancak bir tanınan bir komut grubuyla belirtmiyor|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* grubundaki geçerli bir komut olarak tanınmıyor *pguidCmdGroup*|
|OLECMDERR_DISABLED|Tarafından tanımlanan komutu *nCmdID* devre dışı bırakıldı ve yürütülemez|
|OLECMDERR_NOHELP|Çağıran tarafından tanımlanan komutu hakkında Yardım için sorulan *nCmdID* ancak Yardım yok|
|OLECMDERR_CANCELED|Kullanıcı yürütme iptal edildi|

### <a name="remarks"></a>Açıklamalar

`COleCmdUI` etkinleştirme, güncelleştirme ve DocObject kullanıcı arabirimi komutları diğer özelliklerini ayarlamak için kullanılabilir. Komutlar başlatıldıktan sonra yürütebilir `OnExecOleCmd`.

Framework çevirin ve bir OLE belge komut gönderme çalışmadan önce işlevini çağırır. Standart OLE belge komutları işlemek için bu işlevi geçersiz kılma gerekmez, ancak kendi özel komutları işleyebilir veya parametre kabul eden ya da sonuçları döndürmek komutları işlemek istiyorsanız, bu işlev için bir geçersiz kılma sağlamalısınız.

Komutların çoğu olmayan bir bağımsız değişken almaz veya dönüş değerleri. Komutların çoğu için çağıranın null değerlere geçirebileceğiniz *pvarargIn* ve *pvarargOut*. Giriş değerleri beklediğini komutlar çağırana bildirebilir ve VARIANTARG değişkeni başlatmak ve bir işaretçi değişkeninde geçirmek *pvarargIn*. Tek bir değer gerektiren komutlar bağımsız değişken VARIANTARG doğrudan depolanan ve işleve geçirilen. Birden çok bağımsız değişkeni desteklenen türlerden birini kullanarak VARIANTARG içinde paketlenmesi gerekir (gibi `IDispatch` ve SAFEARRAY'i).

Benzer şekilde, bir komutu çağıran bir VARIANTARG bildirmek için beklenmektedir bağımsız değişkenleri döndürürse, için VT_EMPTY başlatın ve adresini de geçirmeniz *pvarargOut*. Bir komutun tek bir değer döndürürse, nesne doğrudan bu değer depolayabilir *pvarargOut*. Birden çok çıkış değerleri VARIANTARG için uygun şekilde paketlenmesi gerekir.

Bu işlevin temel sınıf uygulamasını komut hedefi ile ilişkili OLE_COMMAND_MAP yapıları yol ve uygun tanıtıcının komutu gönderileceği deneyin. Temel sınıf uygulamasını bağımsız değişkenleri kabul edin veya dönüş değerleri komutları ile çalışır. Bağımsız değişkenleri kabul eden ya da dönüş değerleri komutları işlemek gerekiyorsa, bu işlev geçersiz kılınamıyor gerekir ve çalışmak *pvarargIn* ve *pvarargOut* parametreleri kendiniz.

##  <a name="onframewindowactivate"></a>  COleServerDoc::OnFrameWindowActivate

Framework kapsayıcı uygulamasının çerçeve penceresini etkinleştirmek veya bu işlevi çağırır.

```
virtual void OnFrameWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*bActivate*<br/>
Çerçeve penceresi etkin veya devre dışı bırakılması olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, çerçeve penceresi olabilir herhangi bir Yardım modları iptal eder. Çerçeve penceresi etkin veya devre dışı olduğunda özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.

Daha fazla bilgi için bkz [etkinleştirme](../../mfc/activation-cpp.md)...

##  <a name="ongetembeddeditem"></a>  COleServerDoc::OnGetEmbeddedItem

Bir kapsayıcı uygulaması oluşturma veya düzenleme gömülü bir öğe için sunucu uygulamasının çağırdığında framework tarafından çağırılır.

```
virtual COleServerItem* OnGetEmbeddedItem() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Tüm belgeyi temsil eden bir öğe için bir işaretçi; İşlem başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulaması yok. Tüm belgeyi temsil eden bir öğeyi döndürmek için bu işlevi geçersiz kılmanız gerekir. Bu dönüş değeri bir nesne olmalıdır bir `COleServerItem`-türetilmiş sınıf.

##  <a name="onreactivateandundo"></a>  COleServerDoc::OnReactivateAndUndo

Kullanıcı yerinde etkin, değiştirilmiş, ve daha sonra devre dışı bir öğede yapılan değişiklikleri geri almayı seçtiğinde framework bu işlevi çağırır.

```
virtual BOOL OnReactivateAndUndo();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama başarısızlığı göstermek için false değerini döndürür dışında hiçbir şey yapmaz.

Geri alma uygulamanız destekliyorsa, bu işlev geçersiz kılar. Genellikle, geri alma işlemi gerçekleştirmek, ardından çağırarak öğeyi etkinleştirme `ActivateInPlace`. Kapsayıcı uygulamasını Microsoft Foundation Class Kitaplığı ile yazılmışsa, çağırma `COleClientItem::ReactivateAndUndo` bu işlevin çağrılmasına neden olur.

##  <a name="onresizeborder"></a>  COleServerDoc::OnResizeBorder

Kapsayıcı uygulamasının çerçeve pencereleri boyutu değiştiğinde framework bu işlevi çağırır.

```
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,
    LPOLEINPLACEUIWINDOW lpUIWindow,
    BOOL bFrame);
```

### <a name="parameters"></a>Parametreler

*lpRectBorder*<br/>
İşaretçi bir `RECT` yapısı veya `CRect` nesnesini kenarlık koordinatlarını belirtir.

*lpUIWindow*<br/>
Sınıfın bir nesnesi için işaretçi `IOleInPlaceUIWindow` geçerli yerinde düzenleme oturumunu sahip olan.

*bFrame*<br/>
TRUE ise *lpUIWindow* işaret kapsayıcı uygulamasının en üst düzey bir çerçeve penceresinin veya FALSE ise *lpUIWindow* kapsayıcı uygulamasının belge düzeyinde çerçeve penceresine işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işlev, yeniden boyutlandırır ve araç çubukları ve diğer kullanıcı arabirimi öğeleri yeni pencere boyutuna göre ayarlar.

Daha fazla bilgi için [IOleInPlaceUIWindow](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceuiwindow) Windows SDK.

Bu gelişmiş bir, geçersiz kılınabilir.

##  <a name="onsethostnames"></a>  COleServerDoc::OnSetHostNames

Kapsayıcı ayarlar ya da bu belge için ana bilgisayar adlarını değiştirir framework tarafından çağırılır.

```
virtual void OnSetHostNames(
    LPCTSTR lpszHost,
    LPCTSTR lpszHostObj);
```

### <a name="parameters"></a>Parametreler

*lpszHost*<br/>
Kapsayıcı uygulamasının adını belirten bir dize işaretçisi.

*lpszHostObj*<br/>
Belgenin kapsayıcının adını belirten bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, bu belgeye başvuran tüm görünümleri için belge başlığı değiştirir.

Bu işlev uygulamanızın farklı bir mekanizma aracılığıyla başlıklarını ayarlar geçersiz.

##  <a name="onsetitemrects"></a>  COleServerDoc::OnSetItemRects

Framework, yerinde düzenleme penceresi içinde kapsayıcı uygulamasının çerçeve penceresini konumlandırmak için bu işlevi çağırır.

```
virtual void OnSetItemRects(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
İşaretçi bir `RECT` yapısı veya `CRect` kapsayıcı uygulamasının istemci alanına göre yerinde çerçeve pencerenin konumunu belirten bir nesne.

*lpClipRect*<br/>
İşaretçi bir `RECT` yapısı veya `CRect` nesnesini yerinde çerçeve penceresinin kırpma dikdörtgenini kapsayıcı uygulamasının istemci alanına göre belirtir.

### <a name="remarks"></a>Açıklamalar

Gerekirse görünümün yakınlaştırma faktörünü güncelleştirmek için bu işlevi geçersiz.

Yanıt olarak genellikle bu işlev çağrılır bir `RequestPositionChange` çağırmak istediğiniz zaman, yerinde öğe için bir konum değişiklik isteği için bir kapsayıcı tarafından çağrılabilir.

##  <a name="onshowcontrolbars"></a>  COleServerDoc::OnShowControlBars

Framework tarafından tanımlanan çerçeve penceresi ile ilişkili sunucu uygulamasının denetim çubuklarını gösterme veya gizleme için bu işlevi çağıran *pFrameWnd*.

```
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,
    BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*pFrameWnd*<br/>
Çerçeve penceresi, Denetim çubukları gizli veya gösterilen gereken işaretçisi.

*bBilgi Göster*<br/>
Denetim çubukları gösterilen veya gizli olup olmadığını belirler.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, bu çerçeve penceresi tarafından sahip olunan tüm denetim çubukları numaralandırır ve gizler veya bunları gösterir.

##  <a name="onshowdocument"></a>  COleServerDoc::OnShowDocument

Framework çağrıları `OnShowDocument` işlev sunucu belgesinin gizli veya gösterilen gerekir.

```
virtual void OnShowDocument(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bBilgi Göster*<br/>
Belge için kullanıcı arabirimi yoksa gizli mi olduğunu belirtir.

### <a name="remarks"></a>Açıklamalar

Varsa *bBilgi Göster* doğru ise, varsayılan uygulama gerekirse sunucu uygulaması etkinleştirir ve kendi pencere öğesi görünür olması kaydırmak kapsayıcı uygulaması neden olur. Varsa *bBilgi Göster* false, varsayılan uygulama yapılan bir çağrıyla öğesi devre dışı bırakır. `OnDeactivate`a yok eder veya belge ilk öğe dışında oluşturulan tüm çerçeve pencereleri gizler. Görünür belge kalırsa, sunucu uygulamasının varsayılan uygulama gizler.

##  <a name="onupdatedocument"></a>  COleServerDoc::OnUpdateDocument

Bir belge bir bileşik belgeye gömülü bir öğe olduğunda framework tarafından çağırılır.

```
virtual BOOL OnUpdateDocument();
```

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla güncelleştirildi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan Uygulama çağrıları [COleServerDoc::NotifySaved](#notifysaved) ve [COleServerDoc::SaveEmbedding](#saveembedding) üye işlevleri ve sonra belgeyi temiz olarak işaretler. Özel gömülü bir öğe güncelleştirilirken işleme gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.

##  <a name="requestpositionchange"></a>  COleServerDoc::RequestPositionChange

Kapsayıcı uygulamasını öğenin konumunu değiştirmek için bu üye işlevini çağırın.

```
void RequestPositionChange(LPCRECT lpPosRect);
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
İşaretçi bir `RECT` yapısı veya `CRect` öğenin yeni konumunu içeren nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlev, genellikle çağrılır (birlikte `UpdateAllItems`) yerinde etkin öğeyi verilerin ne zaman değişti. Bu çağrı aşağıdaki kapsayıcı olabilir veya değişiklik çağırarak yerine getirmeyebilir `OnSetItemRects`. Konumu, istenen farklı olabilir.

##  <a name="saveembedding"></a>  COleServerDoc::SaveEmbedding

Katıştırılmış nesneyi kaydetmek için kapsayıcı uygulamaya bildirmek için bu işlevi çağırın.

```
void SaveEmbedding();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev otomatik olarak çağrılır `OnUpdateDocument`. Bu işlev yalnızca belirli bir kullanıcı eylemi sonucunda genellikle çağrıldığı için diskte güncelleştirilecek öğe neden olduğunu unutmayın.

##  <a name="scrollcontainerby"></a>  COleServerDoc::ScrollContainerBy

Çağrı `ScrollContainerBy` piksel cinsinden miktar kapsayıcı belge kaydırmak için üye işlevi tarafından belirtilen `sizeScroll`.

```
BOOL ScrollContainerBy(CSize sizeScroll);
```

### <a name="parameters"></a>Parametreler

*sizeScroll*<br/>
Kaydırmak için ne kadar kapsayıcı belge olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Pozitif değerler aşağı ve sağa doğru kaydırma gösterir; Yukarı ve sola kaydırma, negatif değerleri göstermek.

##  <a name="updateallitems"></a>  COleServerDoc::UpdateAllItems

Belge değişti belgeye bağlı tüm bağlantılı öğeler bildirmek için bu işlevi çağırın.

```
void UpdateAllItems(
    COleServerItem* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL,
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>Parametreler

*pSender*<br/>
Dokument öğeye işaretçi veya güncelleştirilmesi için tüm öğeleri yoksa NULL.

*lHint*<br/>
Değiştirme hakkında bilgi içerir.

*pHint*<br/>
Bir nesne değiştirme hakkında bilgi depolamak için işaretçi.

*nDrawAspect*<br/>
Çizilecek öğesi'ne olduğunu belirler. Bu DVASPECT sabit bir değerdir. Bu parametre aşağıdaki değerlerden biri olabilir:

- DVASPECT_ICON öğesi, bir nesnenin kapsayıcısı içindeki olarak görüntülenebilir şekilde temsil edilir.

- Tarama Aracı içinde görüntülenebilen böylece desteklemek istiyorsanız öğesi "küçük" gösteriminde işlenir.

- DVASPECT_ICON öğesi bir simge ile temsil edilir.

- Dosya menüsünden Yazdır komutunu kullanarak yazdırılmış gibi DVASPECT_ICON öğesi gösterilir.

### <a name="remarks"></a>Açıklamalar

Sunucu belgesinin kullanıcı değiştirdikten sonra genellikle bu işlevi çağırın. OLE öğesini belgeye otomatik bir bağlantıyla bağlıysa, öğe değişiklikleri yansıtacak şekilde güncelleştirilir. Microsoft Foundation Class Kitaplığı ile kapsayıcı uygulamalarında [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevinin `COleClientItem` çağrılır.

Bu işlev çağrıları `OnUpdate` öğesi, geçirme gönderme dışında belgenin öğelerin her biri için üye işlevi *pHint*, *lHint*, ve *nDrawAspect*. Öğeleri belgeye yapılan değişiklikler hakkında bilgi geçirmek için şu parametreleri kullan. Bilgi'ı kullanarak kodlama *lHint* veya tanımlayabilirsiniz bir `CObject`-türetilmiş sınıf değişiklikler hakkında bilgi depolayabilir ve bu sınıfı kullanmanın bir nesne için *pHint*. Geçersiz kılma `OnUpdate` üye işlevinde, `COleServerItem`-türetilmiş sınıf kendi sunusu değiştirilip bağlı olarak her bir öğe güncelleştirilirken en iyi duruma getirme.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../visual-cpp-samples.md)<br/>
[COleLinkingDoc Sınıfı](../../mfc/reference/colelinkingdoc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDocument Sınıfı](../../mfc/reference/coledocument-class.md)<br/>
[COleLinkingDoc Sınıfı](../../mfc/reference/colelinkingdoc-class.md)<br/>
[COleTemplateServer Sınıfı](../../mfc/reference/coletemplateserver-class.md)
