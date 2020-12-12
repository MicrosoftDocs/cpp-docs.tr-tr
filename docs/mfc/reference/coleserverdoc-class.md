---
description: 'Daha fazla bilgi edinin: Cotaserverdoc sınıfı'
title: Cotaserverdoc sınıfı
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
ms.openlocfilehash: b96327f2e3e59d4c9941a8e930be70aee3bb58e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226694"
---
# <a name="coleserverdoc-class"></a>Cotaserverdoc sınıfı

OLE sunucu belgeleri için temel sınıf.

## <a name="syntax"></a>Syntax

```
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Copaserverdoc:: Cotaserverdoc](#coleserverdoc)|Bir `COleServerDoc` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotaserverdoc:: ActivateDocObject](#activatedocobject)|İlişkili DocObject belgesini etkinleştirir.|
|[Cotaserverdoc:: ActivateInPlace](#activateinplace)|Belgeyi yerinde düzenlenmek üzere etkinleştirir.|
|[Cotaserverdoc::D eactivateAndUndo](#deactivateandundo)|Sunucunun kullanıcı arabirimini devre dışı bırakır.|
|[Cotaserverdoc::D SCC](#discardundostate)|Geri alma durumu bilgisini atar.|
|[Cotaserverdoc:: GetClientSite](#getclientsite)|Temel alınan arabirime bir işaretçi alır `IOleClientSite` .|
|[Cotaserverdoc:: Getembeddedıtem](#getembeddeditem)|Tüm belgeyi temsil eden bir öğeye yönelik bir işaretçi döndürür.|
|[Cotaserverdoc:: Getıtemcliprect](#getitemcliprect)|Yerinde düzenlenmek üzere geçerli kırpma dikdörtgenini döndürür.|
|[Cotaserverdoc:: GetItemPosition](#getitemposition)|Yerinde düzenlenmek üzere kapsayıcı uygulamasının istemci alanına göre geçerli konum dikdörtgenini döndürür.|
|[Cotaserverdoc:: GetZoomFactor](#getzoomfactor)|Piksel cinsinden yakınlaştırma faktörünü döndürür.|
|[Cotaserverdoc:: ısdocobject](#isdocobject)|Belgenin bir DocObject olup olmadığını belirler.|
|[Copaserverdoc:: ıstreammbedded](#isembedded)|Belgenin bir kapsayıcı belgeye katıştırıldığını veya tek başına çalıştığını gösterir.|
|[Cotaserverdoc:: ısınplaceactıve](#isinplaceactive)|Öğe halen etkin etkinleştirilmişse, TRUE döndürür.|
|[Cotaserverdoc:: NotifyChanged](#notifychanged)|Kullanıcının belgeyi değiştirdiği kapsayıcıları bilgilendirir.|
|[Cotaserverdoc:: NotifyClosed](#notifyclosed)|Kullanıcının belgeyi kapatan kapsayıcıları bilgilendirir.|
|[Cotaserverdoc:: NotifyRename](#notifyrename)|Kullanıcının belgeyi yeniden adlandırdığını kapsayıcıların bilgilendirir.|
|[Cotaserverdoc:: NotifySaved](#notifysaved)|Kullanıcının belgeyi kaydettiği kapsayıcıları bilgilendirir.|
|[Cotaserverdoc:: OnDeactivate](#ondeactivate)|Kullanıcı yerinde etkinleştirilmiş bir öğeyi devre dışı bıraktığında Framework tarafından çağırılır.|
|[Cotaserverdoc:: OnDeactivateUI](#ondeactivateui)|Denetimleri ve yerinde etkinleştirme için oluşturulan diğer kullanıcı arabirimi öğelerini yok etmek için Framework tarafından çağırılır.|
|[Cotaserverdoc:: OnDocWindowActivate](#ondocwindowactivate)|Kapsayıcının belge çerçevesi penceresi etkinleştirildiğinde veya devre dışı bırakıldığında Framework tarafından çağırılır.|
|[Cotaserverdoc:: OnResizeBorder](#onresizeborder)|Kapsayıcı uygulamasının çerçeve penceresi veya belge penceresi yeniden boyutlandırılırken Framework tarafından çağırılır.|
|[Cotaserverdoc:: Onshowcontrolçubuklar](#onshowcontrolbars)|Yerinde düzenlenmek üzere denetim çubuklarını göstermek veya gizlemek için Framework tarafından çağırılır.|
|[Cotaserverdoc:: OnUpdateDocument](#onupdatedocument)|Katıştırılmış bir öğe olan bir sunucu belgesi kaydedildiğinde, kapsayıcının öğenin kopyasını güncelleştirerek Framework tarafından çağırılır.|
|[Cotaserverdoc:: RequestPositionChange](#requestpositionchange)|Yerinde düzenleyen çerçevesinin konumunu değiştirir.|
|[Cotaserverdoc:: Savekatıştırma](#saveembedding)|Kapsayıcı uygulamasına belgeyi kaydetmesini söyler.|
|[Cotaserverdoc:: ScrollContainerBy](#scrollcontainerby)|Kapsayıcı belgesini kaydırır.|
|[Cotaserverdoc:: UpdateAllItems](#updateallitems)|Kullanıcının belgeyi değiştirdiği kapsayıcıları bilgilendirir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotaserverdoc:: Createınplaceframe](#createinplaceframe)|Yerinde düzenlenmek üzere bir çerçeve penceresi oluşturmak için Framework tarafından çağırılır.|
|[Cotaserverdoc::D Estroınplaceframe](#destroyinplaceframe)|Yerinde düzenlenmek üzere bir çerçeve penceresini yok etmek için Framework tarafından çağırılır.|
|[Cotaserverdoc:: GetDocObjectServer](#getdocobjectserver)|Yeni bir `CDocObjectServer` nesne oluşturmak ve bu belgenin bir DocObject kapsayıcısı olduğunu göstermek için bu işlevi geçersiz kılın.|
|[Cotaserverdoc:: OnClose](#onclose)|Bir kapsayıcı belgeyi kapatmak istediğinde framework tarafından çağırılır.|
|[Copaserverdoc:: Onexecoelcmd](#onexecolecmd)|Belirtilen komutu yürütür veya komut için yardımı görüntüler.|
|[Cotaserverdoc:: OnFrameWindowActivate](#onframewindowactivate)|Kapsayıcının çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında Framework tarafından çağırılır.|
|[Cotaserverdoc:: OnGetEmbeddedItem](#ongetembeddeditem)|`COleServerItem`Tüm belgeyi temsil eden öğesine ulaşmak için çağırılır; gömülü bir öğeyi almak için kullanılır. Uygulama gerekiyor.|
|[Cotaserverdoc:: OnReactivateAndUndo](#onreactivateandundo)|Yerinde düzenlenmek sırasında yapılan değişiklikleri geri almak için Framework tarafından çağırılır.|
|[Cotaserverdoc:: OnSetHostNames](#onsethostnames)|Bir kapsayıcı katıştırılmış bir nesne için pencere başlığını ayarladığında Framework tarafından çağırılır.|
|[Cotaserverdoc:: OnSetItemRects](#onsetitemrects)|Kapsayıcı uygulamasının penceresi içindeki yerinde Düzenle çerçevesi penceresini konumlandırmak için Framework tarafından çağırılır.|
|[Cotaserverdoc:: OnShowDocument](#onshowdocument)|Belgeyi göstermek veya gizlemek için Framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Bir sunucu belgesi, gömülü veya bağlantılı öğelere sunucu arabirimini temsil eden [Cotaserverıtem](../../mfc/reference/coleserveritem-class.md) nesnelerini içerebilir. Bir sunucu uygulaması bir kapsayıcı tarafından katıştırılmış bir öğeyi düzenlemek için başlatıldığında, öğe kendi sunucu belgesi olarak yüklenir; `COleServerDoc` nesne, `COleServerItem` Tüm belgeden oluşan yalnızca bir nesne içerir. Bir sunucu uygulaması, bağlantılı bir öğeyi düzenlemek için bir kapsayıcı tarafından başlatıldığında, mevcut bir belge diskten yüklenir; Belge içeriğinin bir bölümü, bağlantılı öğeyi gösterecek şekilde vurgulanır.

`COleServerDoc` nesneler [Cotaclientidıtem](../../mfc/reference/coleclientitem-class.md) sınıfının öğelerini de içerebilir. Bu, kapsayıcı-sunucu uygulamaları oluşturmanıza olanak sağlar. Framework, `COleClientItem` nesneleri hizmet verirken öğeleri düzgün bir şekilde depolamak için işlevler sağlar `COleServerItem` .

Sunucu uygulamanız bağlantıları desteklemiyorsa, bir sunucu belgesi her zaman tek bir sunucu öğesi içerir ve bu, katıştırılmış nesnenin tamamını bir belge olarak temsil eder. Sunucu uygulamanız bağlantıları destekliyorsa, her seçim panoya kopyalanırken bir sunucu öğesi oluşturulması gerekir.

Kullanmak için `COleServerDoc` , öğesinden bir sınıf türetirsiniz ve [OnGetEmbeddedItem](#ongetembeddeditem) üye işlevini uygulayıp sunucunuzun katıştırılmış öğeleri desteklemesini sağlar. `COleServerItem`Belgelerinizdeki öğeleri uygulamak ve bu sınıfın içindeki nesneleri döndürmek için öğesinden bir sınıf türetirsiniz `OnGetEmbeddedItem` .

Bağlantılı öğeleri desteklemek için `COleServerDoc` [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) üye işlevini sağlar. Belge öğelerini yönetme yönteminiz varsa, varsayılan uygulamayı kullanabilir veya geçersiz kılabilirsiniz.

`COleServerDoc`Uygulamanızın desteklediği her bir sunucu belgesi türü için tek türetilmiş bir sınıfa ihtiyacınız vardır. Örneğin, sunucu uygulamanız çalışma sayfalarını ve grafikleri destekliyorsa, iki türetilmiş sınıfa ihtiyacınız vardır `COleServerDoc` .

Sunucular hakkında daha fazla bilgi için bkz. [sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[Colet belgesi](../../mfc/reference/coledocument-class.md)

[Cotalinkingdoc](../../mfc/reference/colelinkingdoc-class.md)

`COleServerDoc`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="coleserverdocactivatedocobject"></a><a name="activatedocobject"></a> Cotaserverdoc:: ActivateDocObject

İlişkili DocObject belgesini etkinleştirir.

```cpp
void ActivateDocObject();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `COleServerDoc` etkin belgeleri (DocObjects olarak da bilinir) desteklemez. Bu desteği etkinleştirmek için bkz. [GetDocObjectServer](#getdocobjectserver) ve Class [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md).

## <a name="coleserverdocactivateinplace"></a><a name="activateinplace"></a> Cotaserverdoc:: ActivateInPlace

Öğeyi yerinde düzenlenmek üzere etkinleştirir.

```
BOOL ActivateInPlace();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0, öğenin tamamen açık olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, yerinde etkinleştirme için gereken tüm işlemleri gerçekleştirir. Yerinde bir çerçeve penceresi oluşturur, etkinleştirir ve öğeye göre boyutlandırır, paylaşılan menüleri ve diğer denetimleri ayarlar, öğeyi görünüme kaydırır ve odağı yerinde çerçeve penceresine ayarlar.

Bu işlev, [Cotaserverıtem:: OnShow](../../mfc/reference/coleserveritem-class.md#onshow)öğesinin varsayılan uygulamasıyla çağrılır. Uygulamanız yerinde etkinleştirme (örneğin, yürütme) için başka bir fiil destekliyorsa bu işlevi çağırın.

## <a name="coleserverdoccoleserverdoc"></a><a name="coleserverdoc"></a> Copaserverdoc:: Cotaserverdoc

`COleServerDoc`OLE sistem dll 'leriyle bağlantı olmadan bir nesne oluşturur.

```
COleServerDoc();
```

### <a name="remarks"></a>Açıklamalar

OLE ile iletişimleri açmak için [Cotalinkingdoc:: Register](../../mfc/reference/colelinkingdoc-class.md#register) öğesini çağırmanız gerekir. Uygulamanızda [Coeltemplateserver](../../mfc/reference/coletemplateserver-class.md) kullanıyorsanız,, `COleLinkingDoc::Register` ve uygulaması tarafından sizin için çağırılır `COleLinkingDoc` `OnNewDocument` `OnOpenDocument` `OnSaveDocument` .

## <a name="coleserverdoccreateinplaceframe"></a><a name="createinplaceframe"></a> Cotaserverdoc:: Createınplaceframe

Framework, yerinde düzenlemede bir çerçeve penceresi oluşturmak için bu işlevi çağırır.

```
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Kapsayıcı uygulamasının üst penceresine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yerinde çerçeve penceresine yönelik bir işaretçi veya başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, çerçeveyi oluşturmak için belge şablonunda belirtilen bilgileri kullanır. Kullanılan görünüm, belge için oluşturulan ilk görünümüdür. Bu görünüm özgün kareden geçici olarak ayrılır ve yeni oluşturulan çerçeveye eklenir.

Bu gelişmiş bir geçersiz kılınabilir.

## <a name="coleserverdocdeactivateandundo"></a><a name="deactivateandundo"></a> Cotaserverdoc::D eactivateAndUndo

Uygulamanız geri almayı destekliyorsa ve Kullanıcı bir öğeyi etkinleştirdikten sonra ancak düzenlemeden önce geri al ' i seçerse bu işlevi çağırın.

```
BOOL DeactivateAndUndo();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırdan farklı, başarılı olma; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulaması Microsoft Foundation Class Kitaplığı kullanılarak yazılmışsa, bu işlevi çağırmak, sunucunun kullanıcı arabirimini devre dışı bırakmak için [Codenclienentidıtem:: OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) çağrılmasını sağlar.

## <a name="coleserverdocdestroyinplaceframe"></a><a name="destroyinplaceframe"></a> Cotaserverdoc::D Estroınplaceframe

Çerçeve, bir yerinde çerçeve penceresini yok etmek ve yerinde etkinleştirmeden önce sunucu uygulamasının belge penceresini durumuna döndürmek için bu işlevi çağırır.

```
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>Parametreler

*pFrameWnd*<br/>
Yok etmek için yerinde çerçeve penceresine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu gelişmiş bir geçersiz kılınabilir.

## <a name="coleserverdocdiscardundostate"></a><a name="discardundostate"></a> Cotaserverdoc::D SCC

Kullanıcı geri alınamaz bir işleme işlemi gerçekleştiriyorsa, kapsayıcı uygulamanın geri alma-durum bilgilerini atmasını zorlamak için bu işlevi çağırın.

```
BOOL DiscardUndoState();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırdan farklı, başarılı olma; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, geri almayı destekleyen sunucuların, aksi takdirde kullanılamayan geri alma durumu bilgileri tarafından tüketilen kaynakları serbest bırakabilmesini sağlayacak şekilde sağlanır.

## <a name="coleserverdocgetclientsite"></a><a name="getclientsite"></a> Cotaserverdoc:: GetClientSite

Temel alınan arabirime bir işaretçi alır `IOleClientSite` .

```
LPOLECLIENTSITE GetClientSite() const;
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan [IOleClientSite](/windows/win32/api/oleidl/nn-oleidl-ioleclientsite) arabirimine bir işaretçi alır.

## <a name="coleserverdocgetdocobjectserver"></a><a name="getdocobjectserver"></a> Cotaserverdoc:: GetDocObjectServer

Yeni bir `CDocObjectServer` öğe oluşturmak ve ona bir işaretçi döndürmek için bu işlevi geçersiz kılın.

```
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```

### <a name="parameters"></a>Parametreler

*Pdocsıte*<br/>
`IOleDocumentSite`Bu belgeyi sunucuya bağlayacaksınız arabirimi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçisi `CDocObjectServer` ; İşlem başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Bir DocObject sunucusu etkinleştirildiğinde, NULL olmayan bir işaretçinin geri dönmesi, istemcinin DocObjects destekleyecan olduğunu gösterir. Varsayılan uygulama NULL değerini döndürür.

DocObjects 'i destekleyen bir belge için tipik bir uygulama, yalnızca yeni bir `CDocObjectServer` nesne ayırır ve bunu çağırana döndürür. Örneğin:

[!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]

## <a name="coleserverdocgetembeddeditem"></a><a name="getembeddeditem"></a> Cotaserverdoc:: Getembeddedıtem

Tüm belgeyi temsil eden bir öğeye yönelik bir işaretçi almak için bu işlevi çağırın.

```
COleServerItem* GetEmbeddedItem();
```

### <a name="return-value"></a>Dönüş Değeri

Tüm belgeyi temsil eden öğe işaretçisi; İşlem başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama içermeyen bir sanal işlev olan [Cotaserverdoc:: OnGetEmbeddedItem](#ongetembeddeditem)öğesini çağırır.

## <a name="coleserverdocgetitemcliprect"></a><a name="getitemcliprect"></a> Cotaserverdoc:: Getıtemcliprect

`GetItemClipRect`Yerinde düzenlenmekte olan öğenin kırpma dikdörtgeni koordinatlarını almak için üye işlevini çağırın.

```cpp
void GetItemClipRect(LPRECT lpClipRect) const;
```

### <a name="parameters"></a>Parametreler

*lpClipRect*<br/>
`RECT` `CRect` Öğenin kırpma dikdörtgeni koordinatlarını almak için bir yapıya veya nesneye yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Koordinatlar, kapsayıcı uygulama penceresinin istemci alanına göre piksel cinsinden yapılır.

Çizim, kırpma dikdörtgeninin dışında gerçekleşmemelidir. Genellikle, çizim otomatik olarak kısıtlıdır. Kullanıcının belgenin görünür bölümünün dışına kaydırıp kaydırmadığını öğrenmek için bu işlevi kullanın; Bu durumda, bir [ScrollContainerBy](#scrollcontainerby)çağrısı yoluyla kapsayıcı belgeyi gereken şekilde kaydırın.

## <a name="coleserverdocgetitemposition"></a><a name="getitemposition"></a> Cotaserverdoc:: GetItemPosition

`GetItemPosition`Düzenlenmekte olan öğenin koordinatlarını almak için üye işlevini çağırın.

```cpp
void GetItemPosition(LPRECT lpPosRect) const;
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
`RECT` `CRect` Öğenin koordinatlarını almak için bir yapıya veya nesneye yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Koordinatlar, kapsayıcı uygulama penceresinin istemci alanına göre piksel cinsinden yapılır.

Öğenin konumu, ekranda görünür (veya görünür değil) kapsamını belirleyebilmek için geçerli kırpma dikdörtgeniyle karşılaştırılabilir.

## <a name="coleserverdocgetzoomfactor"></a><a name="getzoomfactor"></a> Cotaserverdoc:: GetZoomFactor

`GetZoomFactor`Üye işlevi, yerinde düzenlenmek üzere etkinleştirilen bir öğenin "yakınlaştırma faktörünü" belirler.

```
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,
    LPSIZE lpSizeDenom = NULL,
    LPCRECT lpPosRect = NULL) const;
```

### <a name="parameters"></a>Parametreler

*lpSizeNum*<br/>
`CSize`Yakınlaştırma faktörü payının bulunduğu sınıfın nesnesine yönelik işaretçi. NULL olabilir.

*lpSizeDenom*<br/>
`CSize`Yakınlaştırma faktörünün paydasını tutacak sınıfın nesnesine yönelik işaretçi. NULL olabilir.

*lpPosRect*<br/>
`CRect`Öğenin yeni konumunu açıklayan sınıfın nesnesine yönelik işaretçi. Bu bağımsız değişken NULL ise, işlev öğenin geçerli konumunu kullanır.

### <a name="return-value"></a>Dönüş Değeri

Öğe yerinde düzenlenmek üzere etkinleştirildiyse ve yakınlaştırma faktörü %100 (1:1) dışında bir değer içeriyorsa sıfır dışında. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Piksel cinsinden yakınlaştırma faktörü, öğenin boyutunun geçerli olan boyutuna oranını sağlar. Kapsayıcı uygulama öğenin kapsamını ayarlanmamışsa, doğal kapsamı ( [Copaserverıtem:: OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)tarafından belirlendiği şekilde) kullanılır.

İşlevi, ilk iki bağımsız değişkenini öğenin "yakınlaştırma faktörü" payı ve paydası olarak ayarlar. Öğe yerinde düzenlenmediği takdirde, işlev bu bağımsız değişkenleri varsayılan %100 (veya 1:1) değerine ayarlar ve sıfır döndürür. Daha fazla bilgi için bkz. teknik notta 40, [MFC/OLE In-Place yeniden boyutlandırma ve yakınlaştırma](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).

## <a name="coleserverdocisdocobject"></a><a name="isdocobject"></a> Cotaserverdoc:: ısdocobject

Belgenin bir DocObject olup olmadığını belirler.

```
BOOL IsDocObject() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belge bir DocObject ise doğru; Aksi halde yanlış.

## <a name="coleserverdocisembedded"></a><a name="isembedded"></a> Copaserverdoc:: ıstreammbedded

`IsEmbedded`Belgenin bir kapsayıcıda gömülü bir nesneyi temsil edip etmediğini anlamak için üye işlevini çağırın.

```
BOOL IsEmbedded() const;
```

### <a name="return-value"></a>Dönüş Değeri

`COleServerDoc`Nesne, kapsayıcıda gömülü bir nesneyi temsil eden bir belgese sıfır olmayan bir belgedir; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir dosyadan yüklenen belge, bir kapsayıcı uygulama tarafından bağlantı olarak işlenebilse de Katıştırılamaz. Bir kapsayıcı belgeye gömülü bir belge gömülü olarak kabul edilir.

## <a name="coleserverdocisinplaceactive"></a><a name="isinplaceactive"></a> Cotaserverdoc:: ısınplaceactıve

`IsInPlaceActive`Öğenin şu anda yerinde etkin durumda olup olmadığını öğrenmek için üye işlevini çağırın.

```
BOOL IsInPlaceActive() const;
```

### <a name="return-value"></a>Dönüş Değeri

`COleServerDoc`Nesne etkin ise sıfır dışı; Aksi durumda 0.

## <a name="coleserverdocnotifychanged"></a><a name="notifychanged"></a> Cotaserverdoc:: NotifyChanged

Belgenin değiştiği belgeye bağlı tüm bağlantılı öğeleri bilgilendirmek için bu işlevi çağırın.

```cpp
void NotifyChanged();
```

### <a name="remarks"></a>Açıklamalar

Genellikle, Kullanıcı sunucu belgesinin boyutları gibi bazı genel öznitelikleri değiştirdikten sonra bu işlevi çağırın. Bir OLE öğesi belgeye otomatik bağlantı ile bağlanmışsa, öğe değişiklikleri yansıtacak şekilde güncelleştirilir. Microsoft Foundation Class Kitaplığı yazılan kapsayıcı uygulamalarında, ' nin [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevi `COleClientItem` çağırılır.

> [!NOTE]
> Bu işlev, OLE 1 ile uyumluluk için eklenmiştir. Yeni uygulamalar [UpdateAllItems](#updateallitems)kullanmalıdır.

## <a name="coleserverdocnotifyclosed"></a><a name="notifyclosed"></a> Cotaserverdoc:: NotifyClosed

Bu işlevi, belgenin kapatıldığı kapsayıcıyı (ler) bilgilendirmek için çağırın.

```cpp
void NotifyClosed();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı, Dosya menüsünden Kapat komutunu seçtiğinde, `NotifyClosed` `COleServerDoc` [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) üye işlevinin uygulamasına göre çağırılır. Microsoft Foundation Class Kitaplığı yazılan kapsayıcı uygulamalarında, ' nin [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevi `COleClientItem` çağırılır.

## <a name="coleserverdocnotifyrename"></a><a name="notifyrename"></a> Cotaserverdoc:: NotifyRename

Kullanıcı sunucu belgesini yeniden adlandırdıktan sonra bu işlevi çağırın.

```cpp
void NotifyRename(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Parametreler

*lpszNewName*<br/>
Sunucu belgesinin yeni adını belirten bir dize işaretçisi; Bu genellikle tam bir yoldur.

### <a name="remarks"></a>Açıklamalar

Kullanıcı, Dosya menüsünden farklı Kaydet komutunu seçtiğinde, `NotifyRename` `COleServerDoc` [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) üye işlevinin uygulamasına göre çağırılır. Bu işlev OLE sistem dll 'Lerine bildirimde bulunur ve bu da kapsayıcıları bilgilendirir. Microsoft Foundation Class Kitaplığı yazılan kapsayıcı uygulamalarında, ' nin [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevi `COleClientItem` çağırılır.

## <a name="coleserverdocnotifysaved"></a><a name="notifysaved"></a> Cotaserverdoc:: NotifySaved

Kullanıcı sunucu belgesini kaydettikten sonra bu işlevi çağırın.

```cpp
void NotifySaved();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı, Dosya menüsünden Kaydet komutunu seçtiğinde, `NotifySaved` sizin tarafınızdan `COleServerDoc` [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument)uygulamasına göre çağırılır. Bu işlev OLE sistem dll 'Lerine bildirimde bulunur ve bu da kapsayıcıları bilgilendirir. Microsoft Foundation Class Kitaplığı yazılan kapsayıcı uygulamalarında, ' nin [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevi `COleClientItem` çağırılır.

## <a name="coleserverdoconclose"></a><a name="onclose"></a> Cotaserverdoc:: OnClose

Bir kapsayıcı sunucu belgesinin kapatılmasını istediğinde framework tarafından çağırılır.

```
virtual void OnClose(OLECLOSE dwCloseOption);
```

### <a name="parameters"></a>Parametreler

*Dwcloseseçeneği*<br/>
OLECLOSE numaralandırmasındaki bir değer. Bu parametre aşağıdaki değerlerden birine sahip olabilir:

- OLECLOSE_SAVEIFDIRTY, dosya değiştirildiyse kaydedilir.

- OLECLOSE_NOSAVE dosya kaydedilmeden kapatıldı.

- OLECLOSE_PROMPTSAVE dosya değiştirildiyse, kullanıcıdan dosyayı kaydetmesi istenir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama çağrıları `CDocument::OnCloseDocument` .

Daha fazla bilgi ve ek değer için Windows SDK [OLECLOSE](/windows/win32/api/oleidl/ne-oleidl-oleclose) bölümüne bakın.

## <a name="coleserverdocondeactivate"></a><a name="ondeactivate"></a> Cotaserverdoc:: OnDeactivate

Kullanıcı şu anda yerinde etkin olan eklenmiş veya bağlantılı bir öğeyi devre dışı bıraktığında Framework tarafından çağırılır.

```
virtual void OnDeactivate();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev kapsayıcı uygulamasının Kullanıcı arabirimini özgün durumuna geri yükler ve yerinde etkinleştirme için oluşturulan menüleri ve diğer denetimleri yok eder.

Geri alma durumu bilgileri bu noktada koşulsuz olarak yayınlanmamalıdır.

Daha fazla bilgi için [etkinleştirme](../../mfc/activation-cpp.md)makalesine bakın.

## <a name="coleserverdocondeactivateui"></a><a name="ondeactivateui"></a> Cotaserverdoc:: OnDeactivateUI

Kullanıcı yerinde etkinleştirilmiş bir öğeyi devre dışı bıraktığında çağırılır.

```
virtual void OnDeactivateUI(BOOL bUndoable);
```

### <a name="parameters"></a>Parametreler

*Geçici olarak sürdürülebilir*<br/>
Düzenlemenin değişmesinin geri döndürülüp alınamayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, kapsayıcı uygulamanın kullanıcı arabirimini özgün durumuna geri yükler ve yerinde etkinleştirme için oluşturulan tüm menüleri ve diğer denetimleri gizler.

Framework her zaman, her zaman *yanlış olarak ayarlanır* . Sunucu geri almayı destekliyorsa ve geri alınabilecek bir işlem varsa, *Bdoable* ile temel sınıf uygulamasını doğru olarak ayarlayın.

## <a name="coleserverdocondocwindowactivate"></a><a name="ondocwindowactivate"></a> Cotaserverdoc:: OnDocWindowActivate

Framework, yerinde düzenlemede bir belge penceresini etkinleştirmek veya devre dışı bırakmak için bu işlevi çağırır.

```
virtual void OnDocWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*Bacetkinleştir*<br/>
Belge penceresinin etkinleştirileceğini veya devre dışı bırakılıp başlatılmayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, çerçeve düzeyindeki Kullanıcı arabirimi öğelerini kaldırır veya uygun şekilde ekler. Öğeyi içeren belge etkinleştirildiğinde veya devre dışı bırakıldığında ek eylemler gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

Daha fazla bilgi için [etkinleştirme](../../mfc/activation-cpp.md)makalesine bakın.

## <a name="coleserverdoconexecolecmd"></a><a name="onexecolecmd"></a> Copaserverdoc:: Onexecoelcmd

Çerçeve, belirtilen bir komutu yürütmek veya komut için Yardımı göstermek üzere bu işlevi çağırır.

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
Bir komut kümesini tanımlayan GUID için bir işaretçi. Varsayılan komut grubunu göstermek için NULL olabilir.

*nCmdID*<br/>
Yürütülecek komut. *PguidCmdGroup* tarafından tanımlanan grupta olmalıdır.

*Ncmdexekout*<br/>
Nesnenin komutu yürütmesi, OLECMDEXECOPT numaralandırmasındaki aşağıdaki değerlerden bir veya daha fazlası:

OLECMDEXECOPT_DODEFAULT

OLECMDEXECOPT_PROMPTUSER

OLECMDEXECOPT_DONTPROMPTUSER

OLECMDEXECOPT_SHOWHELP

*pvarargIn*<br/>
Komut için giriş bağımsız değişkenlerini içeren bir VARIANTARG işaretçisi. NULL olabilir.

*pvarargOut*<br/>
Komutun çıkış dönüş değerlerini almak için bir VARIANTARG işaretçisi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK döndürür; Aksi takdirde, aşağıdaki hata kodlarından biri:

|Değer|Açıklama|
|-----------|-----------------|
|E_UNEXPECTED|Beklenmeyen bir hata oluştu|
|E_FAIL|Hata oluştu|
|E_NOTIMPL|MFC 'nin, komutu çevirme ve dağıtma denemesi gerektiğini belirtir|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup* null değil, ancak tanınan bir komut grubu belirtmiyor|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* , *pguidCmdGroup* grubunda geçerli bir komut olarak tanınmıyor|
|OLECMDERR_DISABLED|*NCmdID* tarafından tanımlanan komut devre dışı bırakıldı ve yürütülemiyor|
|OLECMDERR_NOHELP|Çağıran, *nCmdID* tarafından tanımlanan komutla ilgili yardım almak istedi, ancak kullanılabilir yardım yok|
|OLECMDERR_CANCELED|Kullanıcı yürütmeyi iptal etti|

### <a name="remarks"></a>Açıklamalar

`COleCmdUI` DocObject Kullanıcı arabirimi komutlarının diğer özelliklerini etkinleştirmek, güncelleştirmek ve ayarlamak için kullanılabilir. Komutlar başlatıldıktan sonra, bunları ile çalıştırabilirsiniz `OnExecOleCmd` .

Çerçeve, bir OLE belgesi komutunu çevirmeye ve yüklemeye çalışmadan önce işlevi çağırır. Standart OLE belge komutlarını işlemek için bu işlevi geçersiz kılmalısınız, ancak kendi özel komutlarınızı işlemek istiyorsanız veya parametreleri kabul eden komutları veya sonuçları döndüren komutları işlemek istiyorsanız bu işleve bir geçersiz kılma sağlamanız gerekir.

Komutların çoğu bağımsız değişkenleri veya dönüş değerlerini almaz. Komutların çoğu için çağıranın, *pvarargIn* ve *pvarargOut* için null değerleri geçirebilirler. Giriş değerlerini bekleyen komutlar için, çağıran bir VARIANTARG değişkeni bildirip başlatabilir ve *Pvarargiçindeki* değişkene bir işaretçi geçirebilir. Tek bir değer gerektiren komutlarda, bağımsız değişken doğrudan VARIANTARG içinde depolanabilir ve işleve geçirilir. Desteklenen türlerden biri (ve SAFEARRAY) kullanılarak VARIANTARG içinde birden çok bağımsız değişken paketlenmesi gerekir `IDispatch` .

Benzer şekilde, bir komut bağımsız değişken döndürürse, çağıranın bir VARIANTARG bildirmesi, VT_EMPTY için başlatması ve adresini *pvarargOut* içinde geçirmesi beklenir. Bir komut tek bir değer döndürürse, nesne bu değeri doğrudan *pvarargOut* içinde depolayabilirler. Birden çok çıkış değeri, VARIANTARG için uygun bir şekilde paketlenmesi gerekir.

Bu işlevin temel sınıfı uygulama, komut hedefi ile ilişkili OLE_COMMAND_MAP yapılarını gösterecektir ve komutu uygun bir işleyiciye göndermeye çalışır. Temel sınıf uygulama yalnızca bağımsız değişkenleri veya dönüş değerlerini kabul etmeyin komutlarla birlikte kullanılabilir. Bağımsız değişkenleri veya dönüş değerlerini kabul eden komutları işlemeniz gerekiyorsa, bu işlevi geçersiz kılmalısınız ve *pvarargIn* ve *pvarargOut* parametreleriyle birlikte çalışmanız gerekir.

## <a name="coleserverdoconframewindowactivate"></a><a name="onframewindowactivate"></a> Cotaserverdoc:: OnFrameWindowActivate

Kapsayıcı uygulamasının çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında çerçeve bu işlevi çağırır.

```
virtual void OnFrameWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*Bacetkinleştir*<br/>
Çerçeve penceresinin etkinleştirileceğini veya devre dışı bırakılıp başlatılmayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, çerçeve penceresinin içinde olabileceği tüm yardım modlarını iptal eder. Çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

Daha fazla bilgi için [etkinleştirme](../../mfc/activation-cpp.md)makalesine bakın.

## <a name="coleserverdocongetembeddeditem"></a><a name="ongetembeddeditem"></a> Cotaserverdoc:: OnGetEmbeddedItem

Bir kapsayıcı uygulaması, katıştırılmış bir öğe oluşturmak veya düzenlemek için sunucu uygulamasını çağırdığında Framework tarafından çağırılır.

```
virtual COleServerItem* OnGetEmbeddedItem() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Tüm belgeyi temsil eden öğe işaretçisi; İşlem başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama yok. Tüm belgeyi temsil eden bir öğe döndürmek için bu işlevi geçersiz kılmanız gerekir. Bu dönüş değeri, türetilmiş bir sınıfın nesnesi olmalıdır `COleServerItem` .

## <a name="coleserverdoconreactivateandundo"></a><a name="onreactivateandundo"></a> Cotaserverdoc:: OnReactivateAndUndo

Kullanıcı yerinde etkinleştirilen, değiştirilen ve daha sonra devre dışı bırakılmış bir öğede yapılan değişiklikleri geri almayı seçtiğinde, bu işlevi çağırır.

```
virtual BOOL OnReactivateAndUndo();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, hatayı göstermek için FALSE döndürür hariç hiçbir şey yapmaz.

Uygulamanız geri almayı destekliyorsa bu işlevi geçersiz kılın. Genellikle geri alma işlemini gerçekleştirir ve ardından öğesini çağırarak etkinleştirin `ActivateInPlace` . Kapsayıcı uygulama Microsoft Foundation Class Kitaplığı yazılmışsa, çağırma `COleClientItem::ReactivateAndUndo` Bu işlevin çağrılmasına neden olur.

## <a name="coleserverdoconresizeborder"></a><a name="onresizeborder"></a> Cotaserverdoc:: OnResizeBorder

Kapsayıcı uygulamasının çerçeve pencereleri boyutu değiştiğinde Framework bu işlevi çağırır.

```
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,
    LPOLEINPLACEUIWINDOW lpUIWindow,
    BOOL bFrame);
```

### <a name="parameters"></a>Parametreler

*lpRectBorder*<br/>
`RECT`Kenarlığın koordinatlarını belirten bir yapıya veya `CRect` nesneye yönelik işaretçi.

*lpUIWindow*<br/>
`IOleInPlaceUIWindow`Geçerli yerinde düzenleyen oturumunun sahibi olan sınıfın nesnesine yönelik işaretçi.

*bFrame*<br/>
*LpUIWindow* kapsayıcı uygulamasının en üst düzey çerçeve penceresine Işaret ediyorsa true, *lpUIWindow* kapsayıcı uygulamasının belge düzeyi çerçeve penceresine işaret ediyorsa false.

### <a name="remarks"></a>Açıklamalar

Bu işlev, araç çubuklarını ve diğer kullanıcı arabirimi öğelerini yeni pencere boyutuna uygun olarak yeniden boyutlandırır ve ayarlar.

Daha fazla bilgi için Windows SDK içindeki [IOleInPlaceUIWindow](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceuiwindow) bölümüne bakın.

Bu gelişmiş bir geçersiz kılınabilir.

## <a name="coleserverdoconsethostnames"></a><a name="onsethostnames"></a> Cotaserverdoc:: OnSetHostNames

Kapsayıcı, bu belgenin ana bilgisayar adlarını ayarladığında veya değiştirdiğinde Framework tarafından çağırılır.

```
virtual void OnSetHostNames(
    LPCTSTR lpszHost,
    LPCTSTR lpszHostObj);
```

### <a name="parameters"></a>Parametreler

*lpszHost*<br/>
Kapsayıcı uygulamasının adını belirten bir dize işaretçisi.

*lpszHostObj*<br/>
Belge için kapsayıcının adını belirten bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, bu belgeye başvuran tüm görünümlerin belge başlığını değiştirir.

Uygulamanız başlıkları farklı bir mekanizmaya ayarlarsa bu işlevi geçersiz kılın.

## <a name="coleserverdoconsetitemrects"></a><a name="onsetitemrects"></a> Cotaserverdoc:: OnSetItemRects

Framework, kapsayıcı uygulamasının çerçeve penceresinde yerinde Düzenle çerçevesi penceresini konumlandırmak için bu işlevi çağırır.

```
virtual void OnSetItemRects(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
`RECT` `CRect` Kapsayıcı uygulamasının istemci alanına göre yerinde çerçeve penceresinin konumunu belirten bir yapıya veya nesneye yönelik işaretçi.

*lpClipRect*<br/>
`RECT` `CRect` Kapsayıcı uygulamasının istemci alanına göre, yerinde çerçeve penceresinin kırpma dikdörtgenini belirten bir yapıya veya nesneye yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Gerekirse, görünümün yakınlaştırma faktörünü güncelleştirmek için bu işlevi geçersiz kılın.

Bu işlev genellikle çağrıya yanıt olarak çağrılır `RequestPositionChange` , ancak kapsayıcı tarafından, yerinde öğe için bir konum değişikliği istemek için herhangi bir zamanda çağrılabilir.

## <a name="coleserverdoconshowcontrolbars"></a><a name="onshowcontrolbars"></a> Cotaserverdoc:: Onshowcontrolçubuklar

Framework, *pFrameWnd* tarafından tanımlanan çerçeve penceresiyle ilişkili sunucu uygulamasının denetim çubuklarını göstermek veya gizlemek için bu işlevi çağırır.

```
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,
    BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*pFrameWnd*<br/>
Denetim çubuklarının gizlenmesi veya gösterilmesi gereken çerçeve penceresi işaretçisi.

*bShow*<br/>
Denetim çubuklarının gösterilip gösterilmeyeceğini veya gizlenip gizlenmeyeceğini belirler.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, bu çerçeve penceresinin sahip olduğu tüm denetim çubuklarını sıralar ve bunları gizler veya gösterir.

## <a name="coleserverdoconshowdocument"></a><a name="onshowdocument"></a> Cotaserverdoc:: OnShowDocument

Çerçeve, `OnShowDocument` sunucu belgesinin gizlenmesi ya da gösterilmesi gerektiğinde işlevi çağırır.

```
virtual void OnShowDocument(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
Belge için Kullanıcı arabiriminin gösterilip gösterilmeyeceğini veya gizlenmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

*BShow* true ise, varsayılan uygulama, gerekirse sunucu uygulamasını etkinleştirir ve kapsayıcı uygulamanın, öğe görünür olacak şekilde pencere kaydırmasına neden olur. *BShow* false ise, varsayılan uygulama öğesini öğesine bir çağrı aracılığıyla devre dışı bırakır `OnDeactivate` , sonra, ilk tane hariç belge için oluşturulmuş tüm çerçeve pencerelerini yok eder veya gizler. Görünür bir belge kalırsa, varsayılan uygulama sunucu uygulamasını gizler.

## <a name="coleserverdoconupdatedocument"></a><a name="onupdatedocument"></a> Cotaserverdoc:: OnUpdateDocument

Bileşik bir belgeye katıştırılmış öğe olan bir belge kaydedilirken Framework tarafından çağırılır.

```
virtual BOOL OnUpdateDocument();
```

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla güncelleştirilirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama [COleServerDoc:: NotifySaved](#notifysaved) ve [COleServerDoc:: savesaved](#saveembedding) üye işlevlerini çağırır ve sonra belgeyi temiz olarak işaretler. Katıştırılmış bir öğeyi güncelleştirirken özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

## <a name="coleserverdocrequestpositionchange"></a><a name="requestpositionchange"></a> Cotaserverdoc:: RequestPositionChange

Kapsayıcı uygulamasının öğenin konumunu değiştirmesi için bu üye işlevi çağırın.

```cpp
void RequestPositionChange(LPCRECT lpPosRect);
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
Bir `RECT` yapıya veya `CRect` öğenin yeni konumunu içeren bir nesneye yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle `UpdateAllItems` bir yerinde etkin öğe içindeki veriler değiştiğinde çağrılır (ile birlikte). Bu çağrıdan sonra kapsayıcı, çağırarak değişikliği gerçekleştirmeyebilir veya gerçekleştiremeyebilir `OnSetItemRects` . Elde edilen konum, istenenden farklı olabilir.

## <a name="coleserverdocsaveembedding"></a><a name="saveembedding"></a> Cotaserverdoc:: Savekatıştırma

Kapsayıcı uygulamasına katıştırılmış nesneyi kaydetmesini söylemek için bu işlevi çağırın.

```cpp
void SaveEmbedding();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, öğesinden otomatik olarak çağrılır `OnUpdateDocument` . Bu işlevin, öğenin diskte güncelleştirilmesine neden olduğuna, genellikle yalnızca belirli bir kullanıcı eyleminin sonucu olarak çağrdığına emin olun.

## <a name="coleserverdocscrollcontainerby"></a><a name="scrollcontainerby"></a> Cotaserverdoc:: ScrollContainerBy

`ScrollContainerBy`Kapsayıcı belgesini, piksel cinsinden gösterilen miktara göre kaydırmak için üye işlevini çağırın `sizeScroll` .

```
BOOL ScrollContainerBy(CSize sizeScroll);
```

### <a name="parameters"></a>Parametreler

*sizeScroll*<br/>
Kapsayıcı belgenin ne kadar kaydırılacağını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Pozitif değerler aşağı kaydırmayı ve sağa doğru gösterir; negatif değerler yukarı ve sola kaydırma gösterir.

## <a name="coleserverdocupdateallitems"></a><a name="updateallitems"></a> Cotaserverdoc:: UpdateAllItems

Belgenin değiştiği belgeye bağlı tüm bağlantılı öğeleri bilgilendirmek için bu işlevi çağırın.

```cpp
void UpdateAllItems(
    COleServerItem* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL,
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>Parametreler

*pSender*<br/>
Belgeyi değiştiren öğenin işaretçisi veya tüm öğeler güncelleniyorsa NULL.

*Lipucu*<br/>
Değişiklik hakkındaki bilgileri içerir.

*Phınt*<br/>
Değişiklik hakkında bilgi depolayan bir nesne işaretçisi.

*nDrawAspect*<br/>
Öğenin nasıl çizileceğini belirler. Bu, DVASPECT numaralandırmasındaki bir değerdir. Bu parametre aşağıdaki değerlerden birine sahip olabilir:

- DVASPECT_CONTENT öğe, kapsayıcısı içinde katıştırılmış bir nesne olarak görüntülenebilecek şekilde temsil edilir.

- DVASPECT_THUMBNAIL öğe, bir tarama aracında görüntülenebilmesi için bir "küçük resim" gösteriminde işlenir.

- DVASPECT_ICON öğe bir simge ile temsil edilir.

- DVASPECT_DOCPRINT öğe, Dosya menüsündeki Yazdır komutu kullanılarak yazdırılmış gibi gösterilir.

### <a name="remarks"></a>Açıklamalar

Genellikle bu işlevi, Kullanıcı sunucu belgesini değiştirdikten sonra çağırabilirsiniz. Bir OLE öğesi belgeye otomatik bağlantı ile bağlanmışsa, öğe değişiklikleri yansıtacak şekilde güncelleştirilir. Microsoft Foundation Class Kitaplığı yazılan kapsayıcı uygulamalarında, ' nin [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevi `COleClientItem` çağırılır.

Bu işlev, `OnUpdate` Gönderen öğe, geçen *pHint*, *Lipucu* ve *nDrawAspect* gibi belge öğelerinin her biri için üye işlevini çağırır. Belgede yapılan değişikliklerle ilgili bilgileri maddelere iletmek için bu parametreleri kullanın. *Lipucu* kullanarak bilgileri kodlayabilir veya bir `CObject` türetilmiş sınıf tanımlayarak, değişiklikler hakkında bilgi saklayabilir ve *pHint* kullanarak bu sınıfın bir nesnesini geçirebilirsiniz. `OnUpdate` `COleServerItem` Sununun değişip değişmediğini bağlı olarak her bir öğenin güncelleştirilmesini iyileştirmek için türetilmiş sınıfdaki üye işlevini geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Cotalinkingdoc sınıfı](../../mfc/reference/colelinkingdoc-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Cotadocument sınıfı](../../mfc/reference/coledocument-class.md)<br/>
[Cotalinkingdoc sınıfı](../../mfc/reference/colelinkingdoc-class.md)<br/>
[Cotatemplateserver sınıfı](../../mfc/reference/coletemplateserver-class.md)
