---
title: COleServerDoc Sınıfı
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
ms.openlocfilehash: 8e75ec5c00c614a225a059a2b3cf97a7a307c61c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753782"
---
# <a name="coleserverdoc-class"></a>COleServerDoc Sınıfı

OLE sunucu belgeleri için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleServerDoc::COleServerDoc](#coleserverdoc)|Bir `COleServerDoc` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleServerDoc::ActivateDocObject](#activatedocobject)|İlişkili DocObject belgesini etkinleştirir.|
|[COleServerDoc::ActivateInPlace](#activateinplace)|Yerinde düzenleme için belgeyi etkinleştirir.|
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|Sunucunun kullanıcı arabirimini devre dışı bırakır.|
|[COleServerDoc::DiscardUndoState](#discardundostate)|Geri ala-durum bilgilerini atar.|
|[COleServerDoc::GetClientSite](#getclientsite)|Alttaki `IOleClientSite` arabirime bir işaretçi alır.|
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|Bir işaretçiyi belgenin tamamını temsil eden bir öğeye döndürür.|
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|Yerinde düzenleme için geçerli kırpma dikdörtgenini döndürür.|
|[COleServerDoc::GetItemPosition](#getitemposition)|Yerinde düzenleme için kapsayıcı uygulamasının istemci alanına göre geçerli konum dikdörtgenini döndürür.|
|[COleServerDoc::GetZoomFactor](#getzoomfactor)|Piksellerde yakınlaştırma faktörlerini döndürür.|
|[COleServerDoc::IsDocObject](#isdocobject)|Belgenin DocObject olup olmadığını belirler.|
|[COleServerDoc::Gömülü](#isembedded)|Belgenin bir kapsayıcı belgesine katıştırılmış mı yoksa tek başına mı çalıştığını gösterir.|
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|Öğe şu anda yerinde etkinleştirilmişse TRUE döndürür.|
|[COleServerDoc::NotifyChanged](#notifychanged)|Kullanıcının belgeyi değiştirdiğini kapsayıcılara bildirimde bulunur.|
|[COleServerDoc::NotifyClosed](#notifyclosed)|Kullanıcının belgeyi kapadığını belirten kapsayıcılar.|
|[COleServerDoc::NotifyRename](#notifyrename)|Kullanıcının belgenin adını yeniden adlandırdığı kapsayıcıları bildirimde bulunur.|
|[COleServerDoc::NotifySaved](#notifysaved)|Kullanıcının belgeyi kaydettiğini belirten kapsayıcılar.|
|[COleServerDoc::OnDeactivate](#ondeactivate)|Kullanıcı yerinde etkinleştirilen bir öğeyi devre dışı bıraktığında çerçeve tarafından çağrılır.|
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|Yerinde etkinleştirme için oluşturulan denetimleri ve diğer kullanıcı arabirimi öğelerini yok etmek için çerçeve tarafından çağrılır.|
|[COleServerDoc::OnDocWindowEtkinleştir](#ondocwindowactivate)|Kapsayıcının belge çerçevesi penceresi etkinleştirildiğinde veya devre dışı bırakıldığında çerçeve tarafından çağrılır.|
|[COleServerDoc::OnResizeBorder](#onresizeborder)|Kapsayıcı uygulamanın çerçeve penceresi veya belge penceresi yeniden boyutlandığında çerçeve tarafından çağrılır.|
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|Yerinde düzenleme için denetim çubuklarını göstermek veya gizlemek için çerçeve tarafından çağrılır.|
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|Katıştırılmış bir öğe olan bir sunucu belgesi kaydedildiğinde, kapsayıcının öğenin kopyasını güncelleştirildiğinde çerçeve tarafından çağrılır.|
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|Yerinde düzenleme çerçevesinin konumunu değiştirir.|
|[COleServerDoc::SaveEmbedding](#saveembedding)|Kapsayıcı uygulamasına belgeyi kaydetmesini söyler.|
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|Kapsayıcı belgesini kaydırır.|
|[COleServerDoc::UpdateAllItems](#updateallitems)|Kullanıcının belgeyi değiştirdiğini kapsayıcılara bildirimde bulunur.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|Yerinde düzenleme için bir çerçeve penceresi oluşturmak için çerçeve tarafından çağrılır.|
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|Yerinde düzenleme için bir çerçeve penceresi yok etmek için çerçeve tarafından çağrılır.|
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|Yeni `CDocObjectServer` bir nesne oluşturmak ve bu belgenin bir DocObject kapsayıcısı olduğunu belirtmek için bu işlevi geçersiz kılın.|
|[COleServerDoc::OnClose](#onclose)|Bir kapsayıcı belgeyi kapatmak istediğinde çerçeve tarafından çağrılır.|
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|Belirtilen bir komutu yürütür veya komut için yardım görüntüler.|
|[COleServerDoc::OnFrameWindowEtkinleştir](#onframewindowactivate)|Kapsayıcının çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında çerçeve tarafından çağrılır.|
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|Belgenin tamamını `COleServerItem` temsil eden bir belge almak için çağrıldı; katışmış bir öğe almak için kullanılır. Uygulama gereklidir.|
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|Yerinde düzenleme sırasında yapılan değişiklikleri geri almak için çerçeve tarafından çağrılır.|
|[COleServerDoc::OnSetHostNames](#onsethostnames)|Bir kapsayıcı katışılmış bir nesne için pencere başlığı ayarlar çerçeve tarafından çağrılır.|
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|Kapsayıcı uygulama penceresi içinde yerinde düzenleme çerçeve penceresi konumlandırmak için çerçeve tarafından çağrılır.|
|[COleServerDoc::OnShowDocument](#onshowdocument)|Belgeyi göstermek veya gizlemek için çerçeve tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

Sunucu belgesi, sunucu arabirimini gömülü veya bağlantılı öğelerle temsil eden [COleServerItem](../../mfc/reference/coleserveritem-class.md) nesneleri içerebilir. Bir sunucu uygulaması katıştırılmış bir öğeyi düzenlemek için bir kapsayıcı tarafından başlatıldığında, öğe kendi sunucu belgesi olarak yüklenir; `COleServerDoc` nesne, belgenin `COleServerItem` tamamından oluşan tek bir nesne içerir. Bağlı bir öğeyi düzenlemek için bir kapsayıcı tarafından bir sunucu uygulaması başlatıldığında, varolan bir belge diskten yüklenir; bağlı öğeyi belirtmek için belgeiçeriğinin bir bölümü vurgulanır.

`COleServerDoc`nesneler, [COleClientItem](../../mfc/reference/coleclientitem-class.md) sınıfının öğelerini de içerebilir. Bu kapsayıcı sunucu uygulamaları oluşturmanıza olanak sağlar. Çerçeve, nesnelere hizmet verirken `COleClientItem` maddeleri düzgün `COleServerItem` şekilde depolamak için işlevler sağlar.

Sunucu uygulamanız bağlantıları desteklemiyorsa, bir sunucu belgesi her zaman katıştırılmış nesnenin tamamını belge olarak temsil eden yalnızca bir sunucu öğesi içerir. Sunucu uygulamanız bağlantıları destekliyorsa, panoya her seçim kopyalandığında bir sunucu öğesi oluşturması gerekir.

Kullanmak `COleServerDoc`için, ondan bir sınıf türetmek ve sunucugömülü öğeleri desteklemek için izin veren [OnGetEmbeddedItem](#ongetembeddeditem) üye işlevini uygulamak. Belgelerinizdeki öğeleri `COleServerItem` uygulamak için bir sınıf türetin ve bu `OnGetEmbeddedItem`sınıfın nesnelerini 'den döndürün.

Bağlantılı öğeleri desteklemek `COleServerDoc` için [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) üye işlevini sağlar. Belge öğelerini yönetme kendi yolunuz varsa varsayılan uygulamayı kullanabilir veya geçersiz kılabilirsiniz.

Uygulamanızın `COleServerDoc`desteklediği her sunucu belgesi türü için bir tür türetilmiş sınıfa ihtiyacınız var. Örneğin, sunucu uygulamanız çalışma sayfalarını ve grafikleri destekliyorsa, iki `COleServerDoc`türemiş sınıfa ihtiyacınız vardır.

Sunucular hakkında daha fazla bilgi için, makale [Sunucuları bakınız: Bir Sunucu uygulama.](../../mfc/servers-implementing-a-server.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cdocument](../../mfc/reference/cdocument-class.md)

[Coledocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

`COleServerDoc`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="coleserverdocactivatedocobject"></a><a name="activatedocobject"></a>COleServerDoc::ActivateDocObject

İlişkili DocObject belgesini etkinleştirir.

```cpp
void ActivateDocObject();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `COleServerDoc` Etkin belgeleri (DocObjects olarak da adlandırılır) desteklemez. Bu desteği etkinleştirmek için [GetDocObjectServer](#getdocobjectserver) ve [cDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)sınıfına bakın.

## <a name="coleserverdocactivateinplace"></a><a name="activateinplace"></a>COleServerDoc::ActivateInPlace

Yerinde düzenleme için öğeyi etkinleştirir.

```
BOOL ActivateInPlace();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0, öğenin tamamen açık olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, yerinde etkinleştirme için gerekli tüm işlemleri gerçekleştirir. Yerinde çerçeve penceresi oluşturur, etkinleştirir ve öğeye boyutlar, paylaşılan menüler ve diğer denetimler ayarlar, öğeyi görünüme kaydırır ve odağı yerinde çerçeve penceresine ayarlar.

Bu [işlev, COleServerItem](../../mfc/reference/coleserveritem-class.md#onshow)varsayılan uygulaması tarafından çağrılır::OnShow . Uygulamanız yerinde etkinleştirme için başka bir fiili destekliyorsa (Oynat gibi) bu işlevi arayın.

## <a name="coleserverdoccoleserverdoc"></a><a name="coleserverdoc"></a>COleServerDoc::COleServerDoc

OLE `COleServerDoc` sistemi DLs ile bağlanmadan bir nesne inşa eder.

```
COleServerDoc();
```

### <a name="remarks"></a>Açıklamalar

OLE ile iletişimi açmak için [COleLinkingDoc::Register'ı](../../mfc/reference/colelinkingdoc-class.md#register) aramanız gerekir. Uygulamanızda [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) `COleLinkingDoc::Register` kullanıyorsanız, '' uygulaması `COleLinkingDoc` `OnNewDocument` `OnOpenDocument`ile sizin için çağrılır , ve `OnSaveDocument`.

## <a name="coleserverdoccreateinplaceframe"></a><a name="createinplaceframe"></a>COleServerDoc::CreateInPlaceFrame

Çerçeve, yerinde düzenleme için bir çerçeve penceresi oluşturmak için bu işlevi çağırır.

```
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Kapsayıcı uygulamanın üst penceresine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yerinde çerçeve penceresiiçin bir işaretçi veya başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, çerçeveyi oluşturmak için belge şablonunda belirtilen bilgileri kullanır. Kullanılan görünüm, belge için oluşturulan ilk görünümdür. Bu görünüm geçici olarak özgün çerçeveden ayrılır ve yeni oluşturulan çerçeveye eklenir.

Bu gelişmiş bir geçersiz.

## <a name="coleserverdocdeactivateandundo"></a><a name="deactivateandundo"></a>COleServerDoc::DeactivateAndUndo

Uygulamanız Geri Le'yi destekliyorsa ve kullanıcı bir öğeyi etkinleştirdikten sonra ancak düzenlemeden önce Geri Alma'yı seçiyorsa bu işlevi arayın.

```
BOOL DeactivateAndUndo();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız başarı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulaması Microsoft Foundation Class Library kullanılarak yazılmışsa, bu işlevi çağırmak [COleClientItem::OnDeactivateAndUndo'nun](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) çağrılması, sunucunun kullanıcı arabirimini devre dışı bırakır.

## <a name="coleserverdocdestroyinplaceframe"></a><a name="destroyinplaceframe"></a>COleServerDoc::DestroyInPlaceFrame

Çerçeve, yerinde bir çerçeve penceresini yok etmek ve sunucu uygulamasının belge penceresini yerinde etkinleştirmeden önce durumuna döndürmek için bu işlevi çağırır.

```
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>Parametreler

*pFrameWnd*<br/>
Yok edilecek yerinde çerçeve penceresi için işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu gelişmiş bir geçersiz.

## <a name="coleserverdocdiscardundostate"></a><a name="discardundostate"></a>COleServerDoc::DiscardUndoState

Kullanıcı geri alınamayan bir düzenleme işlemi gerçekleştirirse, kapsayıcı uygulamasını geri verme durumu bilgilerini atmaya zorlamak için bu işlevi arayın.

```
BOOL DiscardUndoState();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız başarı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Geri Alabilen sunucuların aksi takdirde kullanılamayacak durum bilgileri tarafından tüketilecek kaynakları serbest sunabilmesi için sağlanır.

## <a name="coleserverdocgetclientsite"></a><a name="getclientsite"></a>COleServerDoc::GetClientSite

Alttaki `IOleClientSite` arabirime bir işaretçi alır.

```
LPOLECLIENTSITE GetClientSite() const;
```

### <a name="return-value"></a>Dönüş Değeri

Altta yatan [IOleClientSite](/windows/win32/api/oleidl/nn-oleidl-ioleclientsite) arabirimi için bir işaretçi alır.

## <a name="coleserverdocgetdocobjectserver"></a><a name="getdocobjectserver"></a>COleServerDoc::GetDocObjectServer

Yeni `CDocObjectServer` bir öğe oluşturmak ve bir işaretçi döndürmek için bu işlevi geçersiz kılın.

```
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```

### <a name="parameters"></a>Parametreler

*pDocSite*<br/>
Bu belgeyi sunucuya `IOleDocumentSite` bağlayacak arabirimi işaretleyin.

### <a name="return-value"></a>Dönüş Değeri

Bir `CDocObjectServer`işaretçi; İşlem başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Bir DocObject sunucusu etkinleştirildiğinde, NULL olmayan bir işaretçinin dönüşü istemcinin DocObjects'i destekleyebilir olduğunu gösterir. Varsayılan uygulama NULL döndürür.

DocObjects destekleyen bir belge için tipik bir uygulama `CDocObjectServer` sadece yeni bir nesne tahsis eder ve arayandöndürecek. Örneğin:

[!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]

## <a name="coleserverdocgetembeddeditem"></a><a name="getembeddeditem"></a>COleServerDoc::GetEmbeddedItem

Belgenin tamamını temsil eden bir öğeye işaretçi almak için bu işlevi çağırın.

```
COleServerItem* GetEmbeddedItem();
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin tamamını temsil eden bir öğenin işaretçisi; İşlem başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Bu [COleServerDoc çağırır::OnGetEmbeddedItem](#ongetembeddeditem), hiçbir varsayılan uygulama ile sanal bir işlev.

## <a name="coleserverdocgetitemcliprect"></a><a name="getitemcliprect"></a>COleServerDoc::GetItemClipRect

Yerinde `GetItemClipRect` düzenlenen öğenin kırpma dikdörtgenkoordinatlarını almak için üye işlevi arayın.

```cpp
void GetItemClipRect(LPRECT lpClipRect) const;
```

### <a name="parameters"></a>Parametreler

*lpClipRect*<br/>
Öğenin `RECT` kırpma dikdörtgeni koordinatlarını almak için bir yapıya veya `CRect` nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Koordinatlar, kapsayıcı uygulama penceresinin istemci alanına göre piksel olarak dır.

Çizim kırpma dikdörtgeninin dışında olmamalıdır. Genellikle, çizim otomatik olarak kısıtlanır. Kullanıcının belgenin görünen bölümünün dışına kaydırılıp kaydırılmadığını belirlemek için bu işlevi kullanın; eğer öyleyse, [ScrollContainerBy](#scrollcontainerby)için bir çağrı yoluyla gerektiği gibi kapsayıcı belge kaydırma .

## <a name="coleserverdocgetitemposition"></a><a name="getitemposition"></a>COleServerDoc::GetItemPosition

Düzenlenen `GetItemPosition` öğenin koordinatlarını almak için üye işlevi arayın.

```cpp
void GetItemPosition(LPRECT lpPosRect) const;
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
Maddenin koordinatlarını almak için bir `RECT` yapı veya `CRect` nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Koordinatlar, kapsayıcı uygulama penceresinin istemci alanına göre piksel olarak dır.

Öğenin konumu, öğenin ekranda ne ölçüde görünür (veya görünür değil) ölçüde belirlemek için geçerli kırpma dikdörtgeni ile karşılaştırılabilir.

## <a name="coleserverdocgetzoomfactor"></a><a name="getzoomfactor"></a>COleServerDoc::GetZoomFactor

Üye `GetZoomFactor` işlev, yerinde düzenleme için etkinleştirilen bir öğenin "yakınlaştırma faktör"unu belirler.

```
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,
    LPSIZE lpSizeDenom = NULL,
    LPCRECT lpPosRect = NULL) const;
```

### <a name="parameters"></a>Parametreler

*lpSizeNum*<br/>
Yakınlaştırma faktörünün `CSize` sayısını tutacak bir sınıf nesnesine işaretçi. NULL olabilir.

*lpSizeDenom*<br/>
Yakınlaştırma faktörünün `CSize` paydasını tutacak bir sınıf nesnesini işaretle. NULL olabilir.

*lpPosRect*<br/>
Öğenin yeni konumunu `CRect` açıklayan bir sınıf nesnesine işaretçi. Bu bağımsız değişken NULL ise, işlev öğenin geçerli konumunu kullanır.

### <a name="return-value"></a>Dönüş Değeri

Öğe yerinde düzenleme için etkinleştirilirse ve yakınlaştırma faktörü %100'den (1:1) başka ysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Piksellerde yakınlaştırma faktörü, öğenin boyutunun geçerli boyutuyla orantılıdır. Kapsayıcı uygulaması öğenin kapsamını belirlememişse, doğal kapsamı [(COleServerItem tarafından belirlendiği gibi::OnGetExtent)](../../mfc/reference/coleserveritem-class.md#ongetextent)kullanılır.

İşlev, ilk iki bağımsız değişkenini öğenin "yakınlaştırma faktörü"nün paydası ve paydasına ayarlar. Öğe yerinde düzenlenmiyorsa, işlev bu bağımsız değişkenleri varsayılan değeri %100 (veya 1:1) olarak ayarlar ve sıfır döndürür. Daha fazla bilgi için Teknik Not 40, [MFC/OLE Yerinde Yeniden Boyutlandırma ve Yakınlaştırma'ya](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)bakın.

## <a name="coleserverdocisdocobject"></a><a name="isdocobject"></a>COleServerDoc::IsDocObject

Belgenin DocObject olup olmadığını belirler.

```
BOOL IsDocObject() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belge DocObject ise DOĞRU; aksi takdirde YANLIŞ.

## <a name="coleserverdocisembedded"></a><a name="isembedded"></a>COleServerDoc::Gömülü

Belgenin `IsEmbedded` kapsayıcıya katışılmış bir nesneyi temsil edip etmediğini belirlemek için üye işlevi arayın.

```
BOOL IsEmbedded() const;
```

### <a name="return-value"></a>Dönüş Değeri

`COleServerDoc` Nesne bir kapsayıcıya katıştırılmış bir nesneyi temsil eden bir belgeyse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir dosyadan yüklenen bir belge, bağlantı olarak kapsayıcı uygulaması tarafından manipüle edilse de katıştırılmış değildir. Kapsayıcı belgesine katıştırılmış bir belgenin katıştırılmış olduğu kabul edilir.

## <a name="coleserverdocisinplaceactive"></a><a name="isinplaceactive"></a>COleServerDoc::IsInPlaceActive

Öğenin `IsInPlaceActive` şu anda yerinde etkin durumda olup olmadığını belirlemek için üye işlevi arayın.

```
BOOL IsInPlaceActive() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne yerinde `COleServerDoc` etkinse sıfırsız; aksi takdirde 0.

## <a name="coleserverdocnotifychanged"></a><a name="notifychanged"></a>COleServerDoc::NotifyChanged

Belgeye bağlı tüm bağlantılı öğeleri belgenin değiştirdiğini bildirmek için bu işlevi arayın.

```cpp
void NotifyChanged();
```

### <a name="remarks"></a>Açıklamalar

Genellikle, kullanıcı sunucu belgesinin boyutları gibi bazı genel öznitelik değiştikten sonra bu işlevi çağırırsınız. Bir OLE öğesi belgeye otomatik bağlantıyla bağlıysa, öğe değişiklikleri yansıtacak şekilde güncelleştirilir. Microsoft Foundation Class Library ile yazılmış kapsayıcı uygulamalarında [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevi `COleClientItem` çağrılır.

> [!NOTE]
> Bu işlev OLE 1 ile uyumluluk için dahildir. Yeni uygulamalar [UpdateAllItems](#updateallitems)kullanmalıdır.

## <a name="coleserverdocnotifyclosed"></a><a name="notifyclosed"></a>COleServerDoc::NotifyClosed

Kapsayıcıya belgenin kapatıldığını bildirmek için bu işlevi arayın.

```cpp
void NotifyClosed();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı Dosya menüsünden Kapat komutunu seçtiğinde, `NotifyClosed` `COleServerDoc` ['OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) üye işlevinin uygulanması' olarak adlandırılır. Microsoft Foundation Class Library ile yazılmış kapsayıcı uygulamalarında [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevi `COleClientItem` çağrılır.

## <a name="coleserverdocnotifyrename"></a><a name="notifyrename"></a>COleServerDoc::NotifyRename

Kullanıcı sunucu belgesini yeniden adlandırdıktan sonra bu işlevi arayın.

```cpp
void NotifyRename(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Parametreler

*lpszNewName*<br/>
Sunucu belgesinin yeni adını belirten bir dize işaretçisi; bu genellikle tam nitelikli bir yoldur.

### <a name="remarks"></a>Açıklamalar

Kullanıcı Dosya menüsünden Kaydet komutunu seçtiğinde, `NotifyRename` `COleServerDoc` ['OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) üye işlevinin uygulanması' olarak adlandırılır. Bu işlev, ole sistemi DLs'i bildirir ve bu da kapsayıcıları bildirir. Microsoft Foundation Class Library ile yazılmış kapsayıcı uygulamalarında [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevi `COleClientItem` çağrılır.

## <a name="coleserverdocnotifysaved"></a><a name="notifysaved"></a>COleServerDoc::NotifySaved

Kullanıcı sunucu belgesini kurtardıktan sonra bu işlevi arayın.

```cpp
void NotifySaved();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı Dosya menüsünden Kaydet komutunu `NotifySaved` seçtiğinde, `COleServerDoc` [OnSaveDocument'ın](../../mfc/reference/cdocument-class.md#onsavedocument)uygulanması yla sizin için çağrılır. Bu işlev, ole sistemi DLs'i bildirir ve bu da kapsayıcıları bildirir. Microsoft Foundation Class Library ile yazılmış kapsayıcı uygulamalarında [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevi `COleClientItem` çağrılır.

## <a name="coleserverdoconclose"></a><a name="onclose"></a>COleServerDoc::OnClose

Bir kapsayıcı sunucu belgesinin kapatılmasını istediğinde çerçeve tarafından çağrılır.

```
virtual void OnClose(OLECLOSE dwCloseOption);
```

### <a name="parameters"></a>Parametreler

*dwCloseOption*<br/>
Numaralandırma OLECLOSE bir değer. Bu parametre aşağıdaki değerlerden birine sahip olabilir:

- OLECLOSE_SAVEIFDIRTY Dosya değiştirildiyse kaydedilir.

- OLECLOSE_NOSAVE Dosya kaydedilmeden kapatılır.

- OLECLOSE_PROMPTSAVE Dosya değiştirildiyse, kullanıcıdan dosyayı kaydetmeleri istenir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama `CDocument::OnCloseDocument`çağırır.

Daha fazla bilgi ve ek değerler için Windows SDK'daki [OLECLOSE'a](/windows/win32/api/oleidl/ne-oleidl-oleclose) bakın.

## <a name="coleserverdocondeactivate"></a><a name="ondeactivate"></a>COleServerDoc::OnDeactivate

Kullanıcı, şu anda etkin durumda olan gömülü veya bağlantılı bir öğeyi devre dışı bıraktığunda çerçeve tarafından çağrılır.

```
virtual void OnDeactivate();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, kapsayıcı uygulamasının kullanıcı arabirimini özgün durumuna geri yükler ve yerinde etkinleştirme için oluşturulan menüleri ve diğer denetimleri yok eder.

Geri alma durumu bilgileri bu noktada kayıtsız şartsız serbest bırakılmalıdır.

Daha fazla bilgi için [Etkinleştirme](../../mfc/activation-cpp.md)makalesine bakın...

## <a name="coleserverdocondeactivateui"></a><a name="ondeactivateui"></a>COleServerDoc::OnDeactivateUI

Kullanıcı, yerinde etkinleştirilen bir öğeyi devre dışı bırakınca çağrılır.

```
virtual void OnDeactivateUI(BOOL bUndoable);
```

### <a name="parameters"></a>Parametreler

*bUndoable*<br/>
Düzenleme değişikliklerinin geri alınıp alınamayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, yerinde etkinleştirme için oluşturulan menüleri ve diğer denetimleri gizleyerek kapsayıcı uygulamasının kullanıcı arabirimini özgün durumuna geri yükler.

Çerçeve her zaman FALSE *için bUndoable* ayarlar. Sunucu geri alma'yı destekliyorsa ve geri alınabilecek bir işlem varsa, *bUndoable* kümesi TRUE ile taban sınıf uygulamasını arayın.

## <a name="coleserverdocondocwindowactivate"></a><a name="ondocwindowactivate"></a>COleServerDoc::OnDocWindowEtkinleştir

Çerçeve, yerinde düzenleme için belge penceresini etkinleştirmek veya devre dışı bırakmak için bu işlevi çağırır.

```
virtual void OnDocWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
Belge penceresinin etkinleştirilip etkinleştirilmeyeceğini veya devre dışı bırakılıp atılmayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, çerçeve düzeyindeki kullanıcı arabirimi öğelerini uygun şekilde kaldırır veya ekler. Öğenizi içeren belge etkinleştirildiğinde veya devre dışı bırakıldığında ek eylemler gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

Daha fazla bilgi için [Etkinleştirme](../../mfc/activation-cpp.md)makalesine bakın...

## <a name="coleserverdoconexecolecmd"></a><a name="onexecolecmd"></a>COleServerDoc::OnExecOleCmd

Çerçeve, bu işlevi belirli bir komutu yürütmek veya komut için yardım görüntülemek için çağırır.

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
Bir komut kümesini tanımlayan bir GUID işaretçisi. Varsayılan komut grubunu belirtmek için NULL olabilir.

*nCmdID*<br/>
Yürütme komutu. *pguidCmdGroup*tarafından tanımlanan grupta olmalıdır.

*nCmdExecOut*<br/>
Nesnenin komutu yürütme şekli, OLECMDEXECOPT numaralandırmasından aşağıdaki değerlerden biri veya birkaçı:

OLECMDEXECOPT_DODEFAULT

OLECMDEXECOPT_PROMPTUSER

OLECMDEXECOPT_DONTPROMPTUSER

OLECMDEXECOPT_SHOWHELP

*pvarargIn*<br/>
Komut için giriş bağımsız değişkenleri içeren bir VARIANTARG işaretçisi. NULL olabilir.

*pvarargOut*<br/>
Komuttan çıktı döndürme değerlerini almak için VARIANTARG'a işaretçi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK verir; aksi takdirde, aşağıdaki hata kodlarından biri:

|Değer|Açıklama|
|-----------|-----------------|
|E_unexpected|Beklenmeyen hata oluştu|
|E_faıl|Hata oluştu|
|E_notımpl|MFC'nin komutu çevirmeye ve göndermeye çalışması gerektiğini gösterir|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup* NULL değildir ancak tanınan bir komut grubu belirtmez|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* *pguidCmdGroup* grubunda geçerli bir komut olarak tanınmıyor|
|OLECMDERR_DISABLED|*nCmdID* tarafından tanımlanan komut devre dışı bırakılır ve yürütülemez|
|OLECMDERR_NOHELP|Arayan *nCmdID* tarafından tanımlanan komut hakkında yardım istedi, ancak yardım yok|
|OLECMDERR_CANCELED|Kullanıcı yürütmeyi iptal etti|

### <a name="remarks"></a>Açıklamalar

`COleCmdUI`DocObject kullanıcı arabirimi komutlarının diğer özelliklerini etkinleştirmek, güncelleştirmek ve ayarlamak için kullanılabilir. Komutlar baş harfe ayrıldıktan sonra, `OnExecOleCmd`bunları .

Çerçeve, bir OLE belge komutunu çevirmeye ve göndermeye çalışmadan önce işlevi çağırır. Standart OLE belge komutlarını işlemek için bu işlevi geçersiz kılmanız gerekmez, ancak kendi özel komutlarınızı işlemek veya parametreleri kabul eden veya sonuçları döndüren komutları işlemek istiyorsanız bu işleve geçersiz kılma sağlamanız gerekir.

Komutların çoğu bağımsız değişkenleri veya döndürme değerlerini almaz. Komutların çoğunluğu için arayan *pvarargIn ve pvarargOut* için NULLs geçirebilirsiniz. *pvarargOut* Giriş değerleri bekleyen komutlar için, arayan bir VARIANTARG değişkenini bildirebilir ve açabilir ve *pvarargIn'deki*değişkene bir işaretçi geçirebilir. Tek bir değer gerektiren komutlar için bağımsız değişken doğrudan VARIANTARG'da depolanabilir ve işleve geçirilebilir. Desteklenen türlerden biri (ve SAFEARRAY gibi) `IDispatch` kullanılarak VARIANTARG içinde birden çok bağımsız değişken paketlenmelidir.

Benzer şekilde, bir komut bağımsız değişkenleri döndürürse, arayanın variantARG bildirmesi, VT_EMPTY için başlatılması ve adresini *pvarargOut'ta*geçirmesi beklenir. Bir komut tek bir değer döndürürse, nesne bu değeri doğrudan *pvarargOut'ta*depolayabilir. Birden fazla çıkış değeri variantARG için uygun bir şekilde paketlenmelidir.

Bu işlevin taban sınıf uygulaması komut hedefi ile ilişkili OLE_COMMAND_MAP yapıları yürümek ve uygun bir işleyici komutu göndermeye çalışın. Taban sınıf uygulaması yalnızca bağımsız değişkenleri veya döndürme değerlerini kabul etmeden komutlarla çalışır. Bağımsız değişkenleri kabul eden veya değerleri döndüren komutları işlemeniz gerekiyorsa, bu işlevi geçersiz kılmanız ve *pvarargIn* ve *pvarargOut* parametreleri ile kendiniz çalışmanız gerekir.

## <a name="coleserverdoconframewindowactivate"></a><a name="onframewindowactivate"></a>COleServerDoc::OnFrameWindowEtkinleştir

Kapsayıcı uygulamanın çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında çerçeve bu işlevi çağırır.

```
virtual void OnFrameWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
Çerçeve penceresinin etkinleştirilip etkinleştirilmeyeceğini veya devre dışı bırakılıp atılmayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, çerçeve penceresinin içinde olabileceği tüm yardım modlarını iptal eder. Çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında özel işleme gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

Daha fazla bilgi için [Etkinleştirme](../../mfc/activation-cpp.md)makalesine bakın...

## <a name="coleserverdocongetembeddeditem"></a><a name="ongetembeddeditem"></a>COleServerDoc::OnGetEmbeddedItem

Bir kapsayıcı uygulaması, katıştırılmış bir öğe oluşturmak veya düzenlemek için sunucu uygulamasını aradığında çerçeve tarafından çağrılır.

```
virtual COleServerItem* OnGetEmbeddedItem() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin tamamını temsil eden bir öğenin işaretçisi; İşlem başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama yoktur. Belgenin tamamını temsil eden bir öğeyi döndürmek için bu işlevi geçersiz kılmanız gerekir. Bu iade değeri, türetilmiş bir `COleServerItem`sınıfın nesnesi olmalıdır.

## <a name="coleserverdoconreactivateandundo"></a><a name="onreactivateandundo"></a>COleServerDoc::OnReactivateAndUndo

Kullanıcı, yerinde etkinleştirilmiş, değiştirilmiş ve daha sonra devre dışı bırakılmış bir öğede yapılan değişiklikleri geri almayı seçtiğinde çerçeve bu işlevi çağırır.

```
virtual BOOL OnReactivateAndUndo();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, hatayı belirtmek için FALSE'u döndürmek dışında hiçbir şey yapmaz.

Uygulamanız geri alalı desteklemeliyse bu işlevi geçersiz kılın. Genellikle geri alma işlemini gerçekleştirir, ardından çağırarak `ActivateInPlace`öğeyi etkinleştirirsiniz. Kapsayıcı uygulaması Microsoft Hazırlık Sınıfı Kitaplığı ile `COleClientItem::ReactivateAndUndo` yazılmışsa, arama bu işlevin çağrılmasını neden olur.

## <a name="coleserverdoconresizeborder"></a><a name="onresizeborder"></a>COleServerDoc::OnResizeBorder

Kapsayıcı uygulamanın çerçeve pencereleri boyutunu değiştirdiğinde çerçeve bu işlevi çağırır.

```
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,
    LPOLEINPLACEUIWINDOW lpUIWindow,
    BOOL bFrame);
```

### <a name="parameters"></a>Parametreler

*lpRectBorder*<br/>
Kenarlığ `CRect` ın koordinatlarını belirten bir `RECT` yapıya veya nesneye işveren.

*lpUIWindow*<br/>
Geçerli yerinde düzenleme `IOleInPlaceUIWindow` oturumuna sahip bir sınıf nesnesine işaretçi.

*bFrame*<br/>
*LPUIWindow* kapsayıcı uygulamasının üst düzey çerçeve penceresine işaret ediyorsa DOĞRU veya *lpUIWindow* kapsayıcı uygulamasının belge düzeyi çerçeve penceresine işaret ediyorsa FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işlev, araç çubuklarını ve diğer kullanıcı arabirimi öğelerini yeni pencere boyutuna göre yeniden boyutlandırıp ayarlar.

Daha fazla bilgi için Windows SDK'daki [IOleInPlaceUIWindow'a](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceuiwindow) bakın.

Bu gelişmiş bir geçersiz.

## <a name="coleserverdoconsethostnames"></a><a name="onsethostnames"></a>COleServerDoc::OnSetHostNames

Kapsayıcı, bu belgenin ana bilgisayar adlarını ayarladığında veya değiştirdiğinde çerçeve tarafından çağrılır.

```
virtual void OnSetHostNames(
    LPCTSTR lpszHost,
    LPCTSTR lpszHostObj);
```

### <a name="parameters"></a>Parametreler

*lpszHost*<br/>
Kapsayıcı uygulamanın adını belirten bir dize işaretçi.

*lpszHostObj*<br/>
Belge için kapsayıcının adını belirten bir dize işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, bu belgeye atıfta bulunan tüm görünümler için belge başlığını değiştirir.

Uygulamanız başlıkları farklı bir mekanizma aracılığıyla ayarlıyorsa bu işlevi geçersiz kılın.

## <a name="coleserverdoconsetitemrects"></a><a name="onsetitemrects"></a>COleServerDoc::OnSetItemRects

Çerçeve, bu işlevi, yerinde düzenleme çerçevesi penceresini kapsayıcı uygulamanın çerçeve penceresi içinde konumlandırmak için çağırır.

```
virtual void OnSetItemRects(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
Kapsayıcı uygulamanın istemci `CRect` alanına göre yerinde çerçeve penceresikonumunu belirten bir `RECT` yapı veya nesneye işaretçi.

*lpClipRect*<br/>
İç çerçeve `RECT` penceresinin `CRect` kapsayıcı uygulamasının istemci alanına göre kırpma dikdörtgenini belirten bir yapı veya nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Gerekirse görünümün yakınlaştırma faktörlerini güncelleştirmek için bu işlevi geçersiz kılın.

Bu işlev genellikle bir `RequestPositionChange` çağrıya yanıt olarak çağrılabilir, ancak yerdeki öğe için konum değişikliği istemek için kapsayıcı tarafından herhangi bir zamanda çağrılabilir.

## <a name="coleserverdoconshowcontrolbars"></a><a name="onshowcontrolbars"></a>COleServerDoc::OnShowControlBars

Çerçeve, *pFrameWnd*tarafından tanımlanan çerçeve penceresi ile ilişkili sunucu uygulamasının denetim çubuklarını göstermek veya gizlemek için bu işlevi çağırır.

```
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,
    BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*pFrameWnd*<br/>
Denetim çubukları gizlenmeli veya gösterilmelidir çerçeve penceresi için işaretçi.

*bGöster*<br/>
Denetim çubuklarının gösterilmediğini veya gizlenip gizlenmediğini belirler.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, bu çerçeve penceresine ait tüm denetim çubuklarını numaralandırır ve bunları gizler veya gösterir.

## <a name="coleserverdoconshowdocument"></a><a name="onshowdocument"></a>COleServerDoc::OnShowDocument

Çerçeve, sunucu `OnShowDocument` belgesinin gizlenmesi veya gösterilmesi gerektiğinde işlevi çağırır.

```
virtual void OnShowDocument(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bGöster*<br/>
Belgenin kullanıcı arabiriminin gösterileceğini veya gizleneceğini belirtir.

### <a name="remarks"></a>Açıklamalar

*bShow* TRUE ise, varsayılan uygulama gerekirse sunucu uygulamasını etkinleştirir ve kapsayıcı uygulamasının öğenin görünür olması için penceresini kaydırmasına neden olur. *bShow* FALSE ise, varsayılan uygulama öğeyi bir çağrı `OnDeactivate`yoluyla devre dışı bırakır , sonra ilki hariç, belge için oluşturulan tüm çerçeve pencerelerini yok eder veya gizler. Görünür belge kalmazsa, varsayılan uygulama sunucu uygulamasını gizler.

## <a name="coleserverdoconupdatedocument"></a><a name="onupdatedocument"></a>COleServerDoc::OnUpdateDocument

Bileşik bir belgede katıştırılmış bir öğe olan bir belge yi kaydederken çerçeve tarafından çağrılır.

```
virtual BOOL OnUpdateDocument();
```

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla güncelleştirildiyse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama [COleServerDoc çağırır::NotifySaved](#notifysaved) ve [COleServerDoc::SaveEmbedding](#saveembedding) üye işlevleri ve sonra temiz olarak belge işaretler. Katışdırılmış bir öğeyi güncellerken özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

## <a name="coleserverdocrequestpositionchange"></a><a name="requestpositionchange"></a>COleServerDoc::RequestPositionChange

Kapsayıcı uygulamasının öğenin konumunu değiştirmesi için bu üye işlevi arayın.

```cpp
void RequestPositionChange(LPCRECT lpPosRect);
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
Öğenin `RECT` yeni konumunu `CRect` içeren bir yapı veya nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle yerinde etkin `UpdateAllItems`bir öğedeki veriler değiştiğinde (birlikte) olarak adlandırılır. Bu çağrıyı takiben, kapsayıcı arayarak `OnSetItemRects`değişikliği gerçekleştirebilir veya gerçekleştirmeyebilir. Ortaya çıkan konum, istenenden farklı olabilir.

## <a name="coleserverdocsaveembedding"></a><a name="saveembedding"></a>COleServerDoc::SaveEmbedding

Katıştılmış nesneyi kaydetmesini kapsayıcı uygulamasına söylemek için bu işlevi arayın.

```cpp
void SaveEmbedding();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev otomatik olarak `OnUpdateDocument`. Bu işlevin öğenin diskte güncelleştirilmesine neden olduğunu unutmayın, bu nedenle genellikle yalnızca belirli bir kullanıcı eyleminin sonucu olarak çağrılır.

## <a name="coleserverdocscrollcontainerby"></a><a name="scrollcontainerby"></a>COleServerDoc::ScrollContainerBy

Kapsayıcı `ScrollContainerBy` belgeyi piksel olarak, `sizeScroll`'' tarafından belirtilen miktara göre kaydırmak için üye işlevi arayın.

```
BOOL ScrollContainerBy(CSize sizeScroll);
```

### <a name="parameters"></a>Parametreler

*boyutKaydırma*<br/>
Kapsayıcı belgenin kaydırma ne kadar uzağa kaydırıldığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Pozitif değerler aşağı ve sağa kaydırma gösterir; negatif değerler yukarı ve sola kaydırma gösterir.

## <a name="coleserverdocupdateallitems"></a><a name="updateallitems"></a>COleServerDoc::UpdateAllItems

Belgeye bağlı tüm bağlantılı öğeleri belgenin değiştirdiğini bildirmek için bu işlevi arayın.

```cpp
void UpdateAllItems(
    COleServerItem* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL,
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>Parametreler

*pSender*<br/>
Belgeyi değiştiren öğeyi işaretçi veya tüm öğeler güncelleştirilecekse NULL.

*Lhint*<br/>
Değişiklik hakkında bilgi içerir.

*pHint*<br/>
Değişiklik le ilgili bilgileri depolayan bir nesneye işaretçi.

*nDrawAspect*<br/>
Öğenin nasıl çizilen olacağını belirler. Bu DVASPECT numaralandırma bir değerdir. Bu parametre aşağıdaki değerlerden birine sahip olabilir:

- DVASPECT_CONTENT Öğe, kapsayıcının içinde katıştırılmış bir nesne olarak görüntülenecek şekilde temsil edilir.

- DVASPECT_THUMBNAIL Öğesi, bir tarama aracında görüntülenebilecek şekilde "küçük resim" gösteriminde işlenir.

- DVASPECT_ICON Öğe bir simge ile temsil edilir.

- DVASPECT_DOCPRINT Öğe, Dosya menüsünden Yazdır komutu kullanılarak basılmış gibi temsil edilir.

### <a name="remarks"></a>Açıklamalar

Genellikle kullanıcı sunucu belgesini değiştirdikten sonra bu işlevi çağırırsınız. Bir OLE öğesi belgeye otomatik bağlantıyla bağlıysa, öğe değişiklikleri yansıtacak şekilde güncelleştirilir. Microsoft Foundation Class Library ile yazılmış kapsayıcı uygulamalarında [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevi `COleClientItem` çağrılır.

Bu işlev, `OnUpdate` gönderen öğe dışında belgenin öğelerinin her biri için üye işlevi çağırır, *pHint*, *lHint*ve *nDrawAspect*geçer. Belgede yapılan değişikliklerle ilgili bilgileri öğelere aktarmak için bu parametreleri kullanın. *LHint* kullanarak bilgileri kodlayabilir veya değişiklikler `CObject`hakkında bilgi depolamak ve *pHint*kullanarak o sınıfın bir nesnesini geçirmek için türetilmiş bir sınıf tanımlayabilirsiniz. Sunusunun `OnUpdate` değişip değişmediğine bağlı olarak her öğenin güncelleştirilmesini en iyi duruma getirmek için türetilmiş sınıfınızdaki `COleServerItem`üye işlevi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[COleLinkingDoc Sınıfı](../../mfc/reference/colelinkingdoc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDocument Sınıfı](../../mfc/reference/coledocument-class.md)<br/>
[COleLinkingDoc Sınıfı](../../mfc/reference/colelinkingdoc-class.md)<br/>
[COleTemplateServer Sınıfı](../../mfc/reference/coletemplateserver-class.md)
