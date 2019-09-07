---
title: Cotaserverıtem sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleServerItem
- AFXOLE/COleServerItem
- AFXOLE/COleServerItem::COleServerItem
- AFXOLE/COleServerItem::AddOtherClipboardData
- AFXOLE/COleServerItem::CopyToClipboard
- AFXOLE/COleServerItem::DoDragDrop
- AFXOLE/COleServerItem::GetClipboardData
- AFXOLE/COleServerItem::GetDocument
- AFXOLE/COleServerItem::GetEmbedSourceData
- AFXOLE/COleServerItem::GetItemName
- AFXOLE/COleServerItem::GetLinkSourceData
- AFXOLE/COleServerItem::GetObjectDescriptorData
- AFXOLE/COleServerItem::IsConnected
- AFXOLE/COleServerItem::IsLinkedItem
- AFXOLE/COleServerItem::NotifyChanged
- AFXOLE/COleServerItem::OnDoVerb
- AFXOLE/COleServerItem::OnDraw
- AFXOLE/COleServerItem::OnDrawEx
- AFXOLE/COleServerItem::OnGetClipboardData
- AFXOLE/COleServerItem::OnGetExtent
- AFXOLE/COleServerItem::OnInitFromData
- AFXOLE/COleServerItem::OnQueryUpdateItems
- AFXOLE/COleServerItem::OnRenderData
- AFXOLE/COleServerItem::OnRenderFileData
- AFXOLE/COleServerItem::OnRenderGlobalData
- AFXOLE/COleServerItem::OnSetColorScheme
- AFXOLE/COleServerItem::OnSetData
- AFXOLE/COleServerItem::OnSetExtent
- AFXOLE/COleServerItem::OnUpdate
- AFXOLE/COleServerItem::OnUpdateItems
- AFXOLE/COleServerItem::SetItemName
- AFXOLE/COleServerItem::GetDataSource
- AFXOLE/COleServerItem::OnHide
- AFXOLE/COleServerItem::OnOpen
- AFXOLE/COleServerItem::OnShow
- AFXOLE/COleServerItem::m_sizeExtent
helpviewer_keywords:
- COleServerItem [MFC], COleServerItem
- COleServerItem [MFC], AddOtherClipboardData
- COleServerItem [MFC], CopyToClipboard
- COleServerItem [MFC], DoDragDrop
- COleServerItem [MFC], GetClipboardData
- COleServerItem [MFC], GetDocument
- COleServerItem [MFC], GetEmbedSourceData
- COleServerItem [MFC], GetItemName
- COleServerItem [MFC], GetLinkSourceData
- COleServerItem [MFC], GetObjectDescriptorData
- COleServerItem [MFC], IsConnected
- COleServerItem [MFC], IsLinkedItem
- COleServerItem [MFC], NotifyChanged
- COleServerItem [MFC], OnDoVerb
- COleServerItem [MFC], OnDraw
- COleServerItem [MFC], OnDrawEx
- COleServerItem [MFC], OnGetClipboardData
- COleServerItem [MFC], OnGetExtent
- COleServerItem [MFC], OnInitFromData
- COleServerItem [MFC], OnQueryUpdateItems
- COleServerItem [MFC], OnRenderData
- COleServerItem [MFC], OnRenderFileData
- COleServerItem [MFC], OnRenderGlobalData
- COleServerItem [MFC], OnSetColorScheme
- COleServerItem [MFC], OnSetData
- COleServerItem [MFC], OnSetExtent
- COleServerItem [MFC], OnUpdate
- COleServerItem [MFC], OnUpdateItems
- COleServerItem [MFC], SetItemName
- COleServerItem [MFC], GetDataSource
- COleServerItem [MFC], OnHide
- COleServerItem [MFC], OnOpen
- COleServerItem [MFC], OnShow
- COleServerItem [MFC], m_sizeExtent
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
ms.openlocfilehash: dcae304e8571ecb5743002638ea23f13c3e21517
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741341"
---
# <a name="coleserveritem-class"></a>Cotaserverıtem sınıfı

OLE öğelerine sunucu arabirimi sağlar.

## <a name="syntax"></a>Sözdizimi

```
class COleServerItem : public CDocItem
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Copaserverıtem:: Cotaserverıtem](#coleserveritem)|Bir `COleServerItem` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotaserverıtem:: AddOtherClipboardData](#addotherclipboarddata)|Bir `COleDataSource` nesneye sunum ve dönüştürme biçimleri koyar.|
|[Cotaserverıtem:: CopyToClipboard](#copytoclipboard)|Öğeyi panoya kopyalar.|
|[Cotaserverıtem::D oDragDrop](#dodragdrop)|Bir sürükle ve bırak işlemi gerçekleştirir.|
|[Cotaserverıtem:: GetClipboardData](#getclipboarddata)|Veri aktarımında kullanılacak veri kaynağını alır (sürükleyip bırakma veya Pano).|
|[Cotaserverıtem:: GetDocument](#getdocument)|Öğeyi içeren sunucu belgesini döndürür.|
|[Cotaserverıtem:: GetEmbedSourceData](#getembedsourcedata)|OLE öğesi için CF_EMBEDSOURCE verilerini alır.|
|[Cotaserverıtem:: GetItemName](#getitemname)|Öğenin adını döndürür. Yalnızca bağlantılı öğeler için kullanılır.|
|[Cotaserverıtem:: GetLinkSourceData](#getlinksourcedata)|OLE öğesi için CF_LINKSOURCE verilerini alır.|
|[Cotaserverıtem:: GetObjectDescriptorData](#getobjectdescriptordata)|OLE öğesi için CF_OBJECTDESCRIPTOR verilerini alır.|
|[Cotaserverıtem:: IsConnected](#isconnected)|Öğenin şu anda etkin bir kapsayıcıya bağlı olup olmadığını gösterir.|
|[Copaserverıtem:: IsLinkedItem](#islinkeditem)|Öğenin bağlantılı OLE öğesini temsil edip etmediğini gösterir.|
|[Cotaserverıtem:: NotifyChanged](#notifychanged)|Tüm kapsayıcıları otomatik bağlantı güncelleştirmesi ile güncelleştirir.|
|[Cotaserverıtem:: OnDoVerb](#ondoverb)|Bir fiil yürütmek için çağırılır.|
|[Cotaserverıtem:: OnDraw](#ondraw)|Kapsayıcı öğeyi çizmek için istediğinde çağırılır; uygulama gerekiyor.|
|[Cotaserverıtem:: OnDrawEx](#ondrawex)|Özel öğe çizimi için çağırılır.|
|[Cotaserverıtem:: OnGetClipboardData](#ongetclipboarddata)|Panoya kopyalanacak verileri almak için Framework tarafından çağırılır.|
|[Cotaserverıtem:: OnGetExtent](#ongetextent)|OLE öğesinin boyutunu almak için Framework tarafından çağırılır.|
|[Copaserverıtem:: Onınitfromdata](#oninitfromdata)|Belirtilen veri aktarımı nesnesinin içeriğini kullanarak bir OLE öğesini başlatmak için Framework tarafından çağırılır.|
|[Cotaserverıtem:: Onqueryupdateıtems](#onqueryupdateitems)|Bağlantılı öğelerin güncelleştirilmesi gerekip gerekmediğini anlamak için çağırılır.|
|[Cotaserverıtem:: OnRenderData](#onrenderdata)|Verileri gecikmeli işlemenin bir parçası olarak alır.|
|[Cotaserverıtem:: OnRenderFileData](#onrenderfiledata)|Gecikmeli işlemenin bir parçası `CFile` olarak bir nesneye veri alır.|
|[Cotaserverıtem:: OnRenderGlobalData](#onrenderglobaldata)|Gecikmeli işleme kapsamında verileri bir HGLOBAL 'e alır.|
|[Cotaserverıtem:: OnSetColorScheme](#onsetcolorscheme)|Öğenin renk düzenini ayarlamak için çağırılır.|
|[Copaserverıtem:: OnSetData](#onsetdata)|Öğenin verilerini ayarlamak için çağırılır.|
|[Cotaserverıtem:: OnSetExtent](#onsetextent)|OLE öğesinin boyutunu ayarlamak için Framework tarafından çağırılır.|
|[Cotaserverıtem:: OnUpdate](#onupdate)|Öğenin ait olduğu belgenin bir bölümü değiştirildiğinde çağırılır.|
|[Cotaserverıtem:: Onupdateıtems](#onupdateitems)|Sunucu belgesindeki tüm öğelerin sunu önbelleğini güncelleştirmek için çağırılır.|
|[Cotaserverıtem:: setItemName](#setitemname)|Öğenin adını ayarlar. Yalnızca bağlantılı öğeler için kullanılır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotaserverıtem:: GetDataSource](#getdatasource)|Dönüştürme biçimlerini depolamak için kullanılan nesneyi alır.|
|[Cotaserverıtem:: OnHide](#onhide)|OLE öğesini gizlemek için Framework tarafından çağırılır.|
|[Cotaserverıtem:: OnOpen](#onopen)|OLE öğesini kendi üst düzey penceresinde göstermek için Framework tarafından çağırılır.|
|[Cotaserverıtem:: OnShow](#onshow)|Kapsayıcı öğeyi göstermek için istediğinde çağırılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Copaserverıtem:: m_sizeExtent](#m_sizeextent)|OLE öğesinin ne kadarının görünür olduğunu sunucuya bildirir.|

## <a name="remarks"></a>Açıklamalar

Bağlantılı bir öğe, bir sunucu belgesinin bazılarını veya tümünü temsil edebilir. Katıştırılmış bir öğe her zaman bir sunucu belgesinin tamamını temsil eder.

`COleServerItem` Sınıfı, genellikle kapsayıcı uygulamadan gelen isteklere yanıt olarak OLE sistem dinamik bağlantı kitaplıkları (dll 'ler) tarafından çağrılan çeşitli geçersiz kılınabilir üye işlevlerini tanımlar. Bu üye işlevleri, kapsayıcı uygulamanın öğeyi görüntüleme, fiillerini yürütme veya verilerini çeşitli biçimlerde alma gibi çeşitli yollarla dolaylı olarak işlemesini sağlar.

Kullanmak `COleServerItem`için, öğesinden bir sınıf türetirsiniz ve [OnDraw](#ondraw) ve [serileştirme](../../mfc/reference/cobject-class.md#serialize) üye işlevlerini uygulayın. `OnDraw` İşlevi bir öğenin meta dosyası gösterimini sağlar ve bir kapsayıcı uygulaması bileşik bir belge açtığında görüntülenmesine izin verir. İşlevi, bir öğenin yerel temsilini sağlarvebu,sunucuvekapsayıcıuygulamalarıarasındagömülübiröğeaktarılmasınaizinverir.`CObject` `Serialize` [OnGetExtent](#ongetextent) , kapsayıcının öğenin boyutunu, kapsayıcıyı etkinleştirerek kapsayıcıya sağlar.

Sunucular ve ilgili konular hakkında daha fazla bilgi için, bkz. [makale sunucuları: ](../../mfc/servers-implementing-a-server.md) Makale[kapsayıcılarında bir sunucu uygulama ve "kapsayıcı/sunucu uygulaması oluşturma": Gelişmiş Özellikler](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

`COleServerItem`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

##  <a name="addotherclipboarddata"></a>Cotaserverıtem:: AddOtherClipboardData

Belirtilen `COleDataSource` nesnedeki OLE öğesi için sunuyu ve dönüştürme biçimlerini yerleştirmek için bu işlevi çağırın.

```
void AddOtherClipboardData(COleDataSource* pDataSource);
```

### <a name="parameters"></a>Parametreler

*pDataSource*<br/>
Verilerin yerleştirilmesi gereken nesnenin işaretçisi. `COleDataSource`

### <a name="remarks"></a>Açıklamalar

Öğe için sunum biçimini (bir meta dosyası resmi) sağlamak üzere [OnDraw](#ondraw) üye işlevini uygulamış olmanız gerekir. Diğer dönüştürme biçimlerini desteklemek için, onları [GetDataSource](#getdatasource) tarafından döndürülen [cotadatasource](../../mfc/reference/coledatasource-class.md) nesnesini kullanarak kaydedin ve verileri desteklemek Istediğiniz biçimlerde sağlamak için [OnRenderData](#onrenderdata) üye işlevini geçersiz kılın.

##  <a name="coleserveritem"></a>Copaserverıtem:: Cotaserverıtem

Bir `COleServerItem` nesnesi oluşturur ve onu sunucu belgesinin belge öğeleri koleksiyonuna ekler.

```
COleServerItem(
    COleServerDoc* pServerDoc,
    BOOL bAutoDelete);
```

### <a name="parameters"></a>Parametreler

*pServerDoc*<br/>
Yeni öğeyi içerecek olan belgeye yönelik işaretçi.

*bAutoDelete*<br/>
Bir bağlantı serbest bırakıldığında nesnenin silinip silinemeyeceğini belirten bayrak. Nesne, `COleServerItem` belgenizin verilerinin, silmeniz gereken tam bir parçası ise bu değeri false olarak ayarlayın. Nesne, çerçeve tarafından silinebilen belge verilerinde bir aralığı tanımlamak için kullanılan ikincil bir yapıdır, bunu TRUE olarak ayarlayın.

##  <a name="copytoclipboard"></a>Cotaserverıtem:: CopyToClipboard

OLE öğesini panoya kopyalamak için bu işlevi çağırın.

```
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```

### <a name="parameters"></a>Parametreler

*bIncludeLink*<br/>
Bağlama verileri panoya kopyalanırsa bunu TRUE olarak ayarlayın. Sunucu uygulamanız bağlantıları desteklemiyorsa bu değeri FALSE olarak ayarlayın.

### <a name="remarks"></a>Açıklamalar

İşlevi, desteklenen biçimlerde OLE öğesinin verilerini içeren bir [Cotadatasource](../../mfc/reference/coledatasource-class.md) nesnesi oluşturmak Için [OnGetClipboardData](#ongetclipboarddata) üye işlevini kullanır. İşlev daha sonra `COleDataSource` [cotadatasource:: SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) işlevini kullanarak nesneyi panoya yerleştirir. `COleDataSource` Nesnesi, öğenin yerel verilerini ve gösterimini CF_METAFILEPICT biçiminde, Ayrıca, desteklemeyi tercih ettiğiniz herhangi bir dönüştürme biçiminde olan verileri içerir. Bu üye işlevin çalışması için [serileştirme](../../mfc/reference/cobject-class.md#serialize) ve [OnDraw](#ondraw) uygulamış olmanız gerekir.

##  <a name="dodragdrop"></a>Cotaserverıtem::D oDragDrop

Bir sürükle ve bırak işlemi gerçekleştirmek için üyeişleviniçağırın.`DoDragDrop`

```
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,
    CPoint ptOffset,
    BOOL bIncludeLink = FALSE,
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,
    LPCRECT lpRectStartDrag = NULL);
```

### <a name="parameters"></a>Parametreler

*Lprectıtem*<br/>
Öğenin, ekranda, istemci alanına göre piksel cinsinden dikdörtgeni.

*ptOffset*<br/>
, Fare konumunun sürükleme sırasında olduğu *lpItemRect* öğesinden gelen fark.

*bIncludeLink*<br/>
Bağlama verileri panoya kopyalanırsa bunu TRUE olarak ayarlayın. Uygulamanız bağlantıları desteklemiyorsa, bu değeri FALSE olarak ayarlayın.

*dwEffects*<br/>
Sürükleme kaynağının sürükleme işleminde izin verilecek etkileri (kopyalama, taşıma ve bağlantı birleşimi) belirler.

*lpRectStartDrag*<br/>
Sürüklediğiniz yerin gerçekten başladığı dikdörtgeni tanımlayan dikdörtgen işaretçisi. Daha fazla bilgi için aşağıdaki Açıklamalar bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

DROPEFFECT numaralandırmasından bir değer. DROPEFFECT_MOVE ise, özgün verilerin kaldırılması gerekir.

### <a name="remarks"></a>Açıklamalar

Sürükle ve bırak işlemi hemen başlamaz. Fare imleci, *lpRectStartDrag* tarafından belirtilen dikdörtgenden ayrılana veya belirtilen sayıda milisaniyeye geçene kadar bekler. *LpRectStartDrag* null ise, fare imleci bir piksel taşırken sürüklemeye başlaması için varsayılan dikdörtgen kullanılır.

Gecikme süresi bir kayıt defteri anahtarı ayarıyla belirtilir. , [CWinApp:: WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) veya [CWinApp:: writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)çağırarak gecikme süresini değiştirebilirsiniz. Gecikme süresini belirtmezseniz, varsayılan 200 milisaniyelik bir değer kullanılır. Sürükleme gecikmesi süresi şu şekilde depolanır:

- Windows NT sürükleme gecikmesi süresi HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay. içinde depolanır

- Windows 3. x sürükleme gecikmesi süresi WIN 'da depolanır. INı dosyası, [Windows} bölümü altında.

- Windows 95/98 sürükleme gecikmesi süresi, WIN 'ın önbelleğe alınmış bir sürümünde depolanıyor. Dosyası.

Sürükleme gecikmesi bilgilerinin kayıt defterinde veya ' de nasıl depolandığını hakkında daha fazla bilgi için. INı dosyası, Windows SDK bkz. [WriteProfileString](/windows/win32/api/winbase/nf-winbase-writeprofilestringw) .

##  <a name="getclipboarddata"></a>Cotaserverıtem:: GetClipboardData

[CopyToClipboard](#copytoclipboard) çağrılırsa, belirtilen [cotadatasource](../../mfc/reference/coledatasource-class.md) nesnesini panoya kopyalanacak tüm verilerle doldurmak için bu Işlevi çağırın ( [DoDragDrop](#dodragdrop)çağrılırsa aynı veriler de aktarılır).

```
void GetClipboardData(
    COleDataSource* pDataSource,
    BOOL bIncludeLink = FALSE,
    LPPOINT lpOffset = NULL,
    LPSIZE lpSize = NULL);
```

### <a name="parameters"></a>Parametreler

*pDataSource*<br/>
Desteklenen tüm biçimlerde `COleDataSource` OLE öğesinin verilerini alacak nesneye yönelik işaretçi.

*bIncludeLink*<br/>
Bağlantı verilerinin panoya kopyalanması gerekiyorsa TRUE. Sunucu uygulamanız bağlantıları desteklemiyorsa FALSE.

*LPX boşluğu*<br/>
Nesnenin kaynağından fare imlecinin piksel cinsinden değeri.

*lpSize*<br/>
Nesnenin piksel cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Bu işlev, OLE öğesine ait yerel verileri almak için [GetEmbedSourceData](#getembedsourcedata) üye işlevini çağırır ve sunum biçimini ve desteklenen herhangi bir dönüştürme biçimini almak Için [AddOtherClipboardData](#addotherclipboarddata) üye işlevini çağırır. *Bincludelink* true ise, işlev Ayrıca öğe için bağlantı verilerini almak üzere [GetLinkSourceData](#getlinksourcedata) öğesini çağırır.

`COleDataSource` Tarafından`CopyToClipboard`sağlanan biçimlerden önce veya sonra bir nesneye biçim koymak istiyorsanız bu işlevi geçersiz kılın.

##  <a name="getdatasource"></a>Cotaserverıtem:: GetDataSource

Sunucu uygulamasının desteklediği dönüştürme biçimlerini depolamak için kullanılan [Cotadatasource](../../mfc/reference/coledatasource-class.md) nesnesini almak için bu işlevi çağırın.

```
COleDataSource* GetDataSource();
```

### <a name="return-value"></a>Dönüş Değeri

Dönüştürme biçimlerini depolamak için `COleDataSource` kullanılan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Sunucu uygulamanızın veri aktarımı işlemleri sırasında çeşitli biçimlerde veri sunmasını istiyorsanız bu biçimleri `COleDataSource` bu işlev tarafından döndürülen nesneyle kaydedin. Örneğin, pano veya sürükle ve bırak işlemleri için OLE öğesinin cf_text temsilini sağlamak istiyorsanız, bu işlevin döndürdüğü `COleDataSource` nesneyle biçimi kaydeder ve sonra `OnRenderXxxData` üye işlevini şu şekilde geçersiz kılın verileri sağlayın.

##  <a name="getdocument"></a>Cotaserverıtem:: GetDocument

Öğeyi içeren belgeye bir işaretçi almak için bu işlevi çağırın.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeyi içeren belgeye yönelik bir işaretçi; Öğe bir belgenin parçası değilse NULL.

### <a name="remarks"></a>Açıklamalar

Bu, `COleServerItem` oluşturucuya bir bağımsız değişken olarak geçirilmiş sunucu belgesine erişim sağlar.

##  <a name="getembedsourcedata"></a>Cotaserverıtem:: GetEmbedSourceData

OLE öğesi için CF_EMBEDSOURCE verilerini almak üzere bu işlevi çağırın.

```
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parametreler

*Lpstgorta*<br/>
OLE öğesi için CF_EMBEDSOURCE verilerini alacak olan [Stgorta](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu biçim öğenin yerel verilerini içerir. Bu işlevin düzgün çalışması için `Serialize` üye işlevini uygulamış olmanız gerekir.

Sonuç daha sonra [Cotadatasource:: CacheData](../../mfc/reference/coledatasource-class.md#cachedata)kullanılarak bir veri kaynağına eklenebilir. Bu işlev [Coelserverıtem:: OnGetClipboardData](#ongetclipboarddata)tarafından otomatik olarak çağrılır.

Daha fazla bilgi için Windows SDK bkz. [Stgmedium](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) .

##  <a name="getitemname"></a>Cotaserverıtem:: GetItemName

Öğenin adını almak için bu işlevi çağırın.

```
const CString& GetItemName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğenin adı.

### <a name="remarks"></a>Açıklamalar

Genellikle bu işlevi yalnızca bağlı öğeler için çağırabilirsiniz.

##  <a name="getlinksourcedata"></a>Cotaserverıtem:: GetLinkSourceData

OLE öğesi için CF_LINKSOURCE verilerini almak üzere bu işlevi çağırın.

```
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parametreler

*Lpstgorta*<br/>
OLE öğesi için CF_LINKSOURCE verilerini alacak olan [Stgorta](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu biçim, OLE öğesinin türünü ve OLE öğesini içeren belgeyi bulmak için gereken bilgileri açıklayan CLSID 'yi içerir.

Sonuç daha sonra [Cotadatasource:: CacheData](../../mfc/reference/coledatasource-class.md#cachedata)ile bir veri kaynağına eklenebilir. Bu işlev [OnGetClipboardData](#ongetclipboarddata)tarafından otomatik olarak çağrılır.

Daha fazla bilgi için Windows SDK bkz. [Stgmedium](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) .

##  <a name="getobjectdescriptordata"></a>Cotaserverıtem:: GetObjectDescriptorData

OLE öğesi için CF_OBJECTDESCRIPTOR verilerini almak üzere bu işlevi çağırın.

```
void GetObjectDescriptorData(
    LPPOINT lpOffset,
    LPSIZE lpSize,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parametreler

*LPX boşluğu*<br/>
OLE öğesinin sol üst köşesinden fare tıklamasını kaydır. NULL olabilir.

*lpSize*<br/>
OLE öğesinin boyutu. NULL olabilir.

*Lpstgorta*<br/>
OLE öğesi için CF_OBJECTDESCRIPTOR verilerini alacak olan [Stgorta](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bilgiler, `STGMEDIUM` *lpStgMedium*tarafından işaret edilen yapıya kopyalanır. Bu biçim Özel Yapıştır iletişim kutusu için gereken bilgileri içerir.

Daha fazla bilgi için Windows SDK bkz. [Stgmedium](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) .

##  <a name="isconnected"></a>Cotaserverıtem:: IsConnected

OLE öğesinin bağlı olup olmadığını görmek için bu işlevi çağırın.

```
BOOL IsConnected() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe bağlıysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir veya daha fazla kapsayıcının öğeye başvuruları varsa, OLE öğesi bağlı olarak kabul edilir. Başvuru sayısı 0 ' dan büyükse veya gömülü bir öğe ise, öğe bağlanır.

##  <a name="islinkeditem"></a>Copaserverıtem:: IsLinkedItem

OLE öğesinin bağlantılı bir öğe olup olmadığını görmek için bu işlevi çağırın.

```
BOOL IsLinkedItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe bağlantılı bir öğe ise sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Öğe geçerliyse bir öğe bağlanır ve belgenin katıştırılmış öğeler listesinde döndürülmezse. Bağlantılı bir öğe bir kapsayıcıya bağlı olmayabilir veya olmayabilir.

Hem bağlantılı hem de katıştırılmış öğeler için aynı sınıfın kullanılması yaygındır. `IsLinkedItem`birçok kez kodun yaygın olmasına rağmen bağlantılı öğelerin gömülü öğelerden farklı davranmasına olanak sağlar.

##  <a name="m_sizeextent"></a>Copaserverıtem:: m_sizeExtent

Bu üye, sunucuya kapsayıcı belgesinde nesnenin ne kadarının görünür olduğunu söyler.

```
CSize m_sizeExtent;
```

### <a name="remarks"></a>Açıklamalar

[OnSetExtent](#onsetextent) 'in varsayılan uygulamasında bu üye ayarlanır.

##  <a name="notifychanged"></a>Cotaserverıtem:: NotifyChanged

Bağlantılı öğe değiştirildikten sonra bu işlevi çağırın.

```
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>Parametreler

*nDrawAspect*<br/>
DVASPECT numaralandırmasından, OLE öğesinin hangi yönün değiştiğini belirten bir değer. Bu parametre aşağıdaki değerlerden herhangi birine sahip olabilir:

- DVASPECT_CONTENT öğesi, kapsayıcısı içinde katıştırılmış bir nesne olarak görüntülenebilecek şekilde temsil edilir.

- DVASPECT_THUMBNAIL öğesi, bir tarama aracında görüntülenebilmesi için bir "küçük resim" gösteriminde işlenir.

- DVASPECT_ICON öğesi bir simge ile temsil edilir.

- DVASPECT_DOCPRINT öğesi, Dosya menüsündeki Yazdır komutu kullanılarak yazdırılmış gibi gösterilir.

### <a name="remarks"></a>Açıklamalar

Bir kapsayıcı öğe bir otomatik bağlantı ile belgeye bağlanmışsa, öğe değişiklikleri yansıtacak şekilde güncelleştirilir. Microsoft Foundation Class Kitaplığı kullanılarak yazılan kapsayıcı uygulamalarında [Colet Clienentidıtem:: OnChange](../../mfc/reference/coleclientitem-class.md#onchange) , yanıt olarak çağırılır.

##  <a name="ondoverb"></a>Cotaserverıtem:: OnDoVerb

Belirtilen fiili yürütmek için Framework tarafından çağırılır.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Parametreler

*ıverb*<br/>
Yürütülecek fiili belirtir. Aşağıdakilerden biri olabilir:

|Değer|Açıklama|Sembol|
|-----------|-------------|------------|
|0|Birincil fiil|OLEIVERB_PRIMARY|
|1\.|İkincil fiil|Seçim|
|- 1|Öğeyi düzenlenmek üzere görüntüle|OLEIVERB_SHOW|
|- 2|Öğeyi ayrı pencerede Düzenle|OLEIVERB_OPEN|
|- 3|Öğeyi Gizle|OLEIVERB_HIDE|

-1 değeri genellikle başka bir fiil için diğer addır. Açık düzenlemeler desteklenmiyorsa-2-1 ile aynı etkiye sahiptir. Ek değerler için bkz. [IOleObject::D oVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulama Microsoft Foundation Class Kitaplığı yazılmışsa, bu işlev, karşılık gelen `COleClientItem` nesnenin [cotaclientidıtem:: Activate](../../mfc/reference/coleclientitem-class.md#activate) üye işlevi çağrıldığında çağrılır. Varsayılan uygulama, birincil fiil veya OLEIVERB_SHOW belirtilmişse [OnShow](#onshow) üye işlevini çağırır, ikincil FIIL veya OLEIVERB_OPEN [belirtilmişse ve](#onopen) OLEIVERB_HIDE belirtilmişse [OnHide](#onhide) . *Iverb* , yukarıda `OnShow` listelenen fiillerden biri değilse, varsayılan uygulama çağırır.

Birincil fiiliniz öğeyi göstermezse bu işlevi geçersiz kılın. Örneğin, öğe bir ses kaydı ise ve birincil fiili yürütülme ise, öğeyi yürütmek için sunucu uygulamasını göstermek zorunda değilsiniz.

Daha fazla bilgi için bkz. [IOleObject::D oVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK.

##  <a name="ondraw"></a>Cotaserverıtem:: OnDraw

OLE öğesini bir meta dosyasında işlemek için çerçeve tarafından çağırılır.

```
virtual BOOL OnDraw(
    CDC* pDC,
    CSize& rSize) = 0;
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Öğenin çizildiği [CDC](../../mfc/reference/cdc-class.md) nesnesine yönelik bir işaretçi. Görüntüleme bağlamı, öznitelik görüntüleme bağlamına otomatik olarak bağlanır, ancak bunu yaparsanız dosya cihazına özgü hale getirebilirsiniz.

*rSize*<br/>
Boyut, meta dosyasının çizileceği, HIMETRIK birimlerde.

### <a name="return-value"></a>Dönüş Değeri

Öğe başarıyla çizildiyse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

OLE öğesinin meta dosyası temsili, öğeyi kapsayıcı uygulamasında göstermek için kullanılır. Kapsayıcı uygulama Microsoft Foundation Class Kitaplığı yazılmışsa, meta dosyası, karşılık gelen [Cotaclientıtem](../../mfc/reference/coleclientitem-class.md) nesnesinin [Draw](../../mfc/reference/coleclientitem-class.md#draw) üye işlevi tarafından kullanılır. Varsayılan uygulama yok. Belirtilen cihaz bağlamına öğe çizmek için bu işlevi geçersiz kılmalısınız.

##  <a name="ondrawex"></a>Cotaserverıtem:: OnDrawEx

Tüm çizim için Framework tarafından çağırılır.

```
virtual BOOL OnDrawEx(
    CDC* pDC,
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Öğenin çizildiği [CDC](../../mfc/reference/cdc-class.md) nesnesine yönelik bir işaretçi. DC, öznitelik işlevlerini çağırmak için otomatik olarak DC 'ye bağlanır, ancak bunu yaparsanız dosya cihazına özgü hale getirebilirsiniz.

*nDrawAspect*<br/>
DVASPECT numaralandırmasından bir değer. Bu parametre aşağıdaki değerlerden herhangi birine sahip olabilir:

- DVASPECT_CONTENT öğesi, kapsayıcısı içinde katıştırılmış bir nesne olarak görüntülenebilecek şekilde temsil edilir.

- DVASPECT_THUMBNAIL öğesi, bir tarama aracında görüntülenebilmesi için bir "küçük resim" gösteriminde işlenir.

- DVASPECT_ICON öğesi bir simge ile temsil edilir.

- DVASPECT_DOCPRINT öğesi, Dosya menüsündeki Yazdır komutu kullanılarak yazdırılmış gibi gösterilir.

*rSize*<br/>
HIMETRIK birimlerde öğenin boyutu.

### <a name="return-value"></a>Dönüş Değeri

Öğe başarıyla çizildiyse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

DVASPECT `OnDraw` DVASPECT_CONTENT 'e eşitse varsayılan uygulama çağırır; aksi takdirde başarısız olur.

DVASPECT_ICON veya DVASPECT_THUMBNAIL gibi DVASPECT_CONTENT dışındaki yönleri için sunum verileri sağlamak üzere bu işlevi geçersiz kılın.

##  <a name="ongetclipboarddata"></a>Cotaserverıtem:: OnGetClipboardData

[CopyToClipboard](#copytoclipboard) üye işlevine yapılan bir `COleDataSource` çağrı ile panoya yerleştirilecek tüm verileri içeren bir nesne almak için Framework tarafından çağırılır.

```
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,
    LPPOINT lpOffset,
    LPSIZE lpSize);
```

### <a name="parameters"></a>Parametreler

*bIncludeLink*<br/>
Bağlama verileri panoya kopyalanırsa bunu TRUE olarak ayarlayın. Sunucu uygulamanız bağlantıları desteklemiyorsa bu değeri FALSE olarak ayarlayın.

*LPX boşluğu*<br/>
Fare imlecinin nesnenin kaynağından piksel cinsinden boşluğu.

*lpSize*<br/>
Nesnenin piksel cinsinden boyutu.

### <a name="return-value"></a>Dönüş Değeri

Pano verilerini içeren [Cotadatasource](../../mfc/reference/coledatasource-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulanması [GetClipboardData](#getclipboarddata)öğesini çağırır.

##  <a name="ongetextent"></a>Cotaserverıtem:: OnGetExtent

, OLE öğesinin HIMETRIK birimleri cinsinden boyutunu almak için Framework tarafından çağırılır.

```
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Parametreler

*nDrawAspect*<br/>
Sınırları alınacak olan OLE öğesinin yönünü belirtir. Bu parametre aşağıdaki değerlerden herhangi birine sahip olabilir:

- DVASPECT_CONTENT öğesi, kapsayıcısı içinde katıştırılmış bir nesne olarak görüntülenebilecek şekilde temsil edilir.

- DVASPECT_THUMBNAIL öğesi, bir tarama aracında görüntülenebilmesi için bir "küçük resim" gösteriminde işlenir.

- DVASPECT_ICON öğesi bir simge ile temsil edilir.

- DVASPECT_DOCPRINT öğesi, Dosya menüsündeki Yazdır komutu kullanılarak yazdırılmış gibi gösterilir.

*rSize*<br/>
OLE öğesinin boyutunu `CSize` alacak bir nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulama Microsoft Foundation Class Kitaplığı yazılmışsa, ilgili `COleClientItem` nesnenin [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) üye işlevi çağrıldığında bu işlev çağrılır. Varsayılan uygulama hiçbir şey yapmaz. Kendiniz uygulamanız gerekir. OLE öğesinin boyutu için bir istek işlerken özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

##  <a name="onhide"></a>Cotaserverıtem:: OnHide

OLE öğesini gizlemek için Framework tarafından çağırılır.

```
virtual void OnHide();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan çağrılar `COleServerDoc::OnShowDocument( FALSE )`. İşlevi kapsayıcıyı OLE öğesinin gizlenmiş olduğunu da bildirir. OLE öğesini gizlerken özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

##  <a name="oninitfromdata"></a>Copaserverıtem:: Onınitfromdata

Bir OLE öğesini, *pDataObject*içeriğini kullanarak başlatmak için Framework tarafından çağırılır.

```
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,
    BOOL bCreation);
```

### <a name="parameters"></a>Parametreler

*pDataObject*<br/>
OLE öğesini başlatmak için çeşitli biçimlerdeki verileri içeren OLE veri nesnesine yönelik işaretçi.

*Boluşturma*<br/>
Bir kapsayıcı uygulama tarafından yeni oluşturulan OLE öğesini başlatmak için işlev çağrılırsa TRUE. Zaten var olan bir OLE öğesinin içeriğini değiştirmek için işlev çağrılırsa FALSE.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*Boluşturma* true ise, bir kapsayıcı geçerli seçime göre yeni nesne Ekle ' yi uygularsa bu işlev çağrılır. Yeni OLE öğesi oluşturulurken seçilen veriler kullanılır. Örneğin, bir elektronik tablo programında bir hücre aralığı seçerken ve sonra seçili aralıktaki değerlere göre bir grafik oluşturmak için yeni nesne Ekle ' yi kullanarak. Varsayılan uygulama hiçbir şey yapmaz. *PDataObject* tarafından sunulmadan kabul edilebilir bir biçim seçmek için bu işlevi geçersiz kılın ve sağlanan VERILERE göre OLE öğesini başlatın. Bu gelişmiş bir geçersiz kılınabilir.

Daha fazla bilgi için, bkz. Windows SDK [IOleObject:: InitFromData](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata) .

##  <a name="onopen"></a>Cotaserverıtem:: OnOpen

OLE öğesini yerine sunucu uygulamasının ayrı bir örneğinde göstermek için Framework tarafından çağırılır.

```
virtual void OnOpen();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, OLE öğesini içeren belgeyi görüntüleyen ilk kare penceresini etkinleştirir; uygulama bir mini sunucu ise, varsayılan uygulama ana pencereyi gösterir. İşlevi kapsayıcıyı OLE öğesinin açıldığını da bildirir.

OLE öğesini açarken özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Bu özellikle, açıldığında bağlantıyı bir bağlantı olarak ayarlamak istediğiniz bağlantılı öğelerle yaygın bir seçimdir.

Daha fazla bilgi için Windows SDK [IOleClientSite:: OnShowWindow](/windows/win32/api/oleidl/nf-oleidl-ioleclientsite-onshowwindow) bölümüne bakın.

##  <a name="onqueryupdateitems"></a>Cotaserverıtem:: Onqueryupdateıtems

Geçerli sunucu belgesindeki bağlantılı öğelerin güncel olup olmadığını anlamak için Framework tarafından çağırılır.

```
virtual BOOL OnQueryUpdateItems();
```

### <a name="return-value"></a>Dönüş Değeri

Belgede güncelleştirmelerin olması gereken öğeler varsa sıfır dışında; tüm öğeler güncel ise 0.

### <a name="remarks"></a>Açıklamalar

Kaynak belgesi değiştirildiyse bir öğe güncel değil, ancak bağlantılı öğe belgedeki değişiklikleri yansıtacak şekilde güncellenmemişse.

##  <a name="onrenderdata"></a>Cotaserverıtem:: OnRenderData

Verileri belirtilen biçimde almak için Framework tarafından çağırılır.

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
Bilgilerin istendiği biçimi belirten [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder.

*Lpstgorta*<br/>
Verilerin döndürüleceği bir [Stgorta](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim, Gecikmeli işleme için `COleDataSource` [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) veya [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) üye işlevi kullanılarak nesnesine daha önce yerleştirilmiş bir biçimdir. Bu işlevin varsayılan uygulanması, sağlanan depolama ortamı bir dosya ya da bellek ise sırasıyla [OnRenderFileData](#onrenderfiledata) veya [OnRenderGlobalData](#onrenderglobaldata)' ı çağırır. Bu biçimlerin hiçbiri sağlanmazsa, varsayılan uygulama 0 döndürür ve hiçbir şey yapmaz.

*LpStgMedium*-> *TYMED* TYMED_NULL ise, stgmedium, *lpFormatEtc-> TYMED*tarafından belirtilen şekilde ayrılmalı ve doldurulmalıdır. TYMED_NULL değilse, STGMEDIUM, verilerle birlikte doldurulmalıdır.

Bu gelişmiş bir geçersiz kılınabilir. Verilerinizi istenen biçimde ve ortamda sağlamak için bu işlevi geçersiz kılın. Verilerinize bağlı olarak, bunun yerine bu işlevin diğer sürümlerinden birini geçersiz kılmak isteyebilirsiniz. Verileriniz küçük ve boyut olarak düzeltildiğinde, geçersiz kılın `OnRenderGlobalData`. Verileriniz bir dosya içinde veya değişken boyutunda ise, geçersiz kılın `OnRenderFileData`.

Daha fazla bilgi için, bkz. Windows SDK [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata), [stgmedium](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1), [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)ve [TYMED](/windows/win32/api/objidl/ne-objidl-tymed) .

##  <a name="onrenderfiledata"></a>Cotaserverıtem:: OnRenderFileData

Depolama ortamı bir dosya olduğunda, belirtilen biçimdeki verileri almak için Framework tarafından çağırılır.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
Bilgilerin istendiği biçimi belirten [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder.

*pFile*<br/>
Verilerin işlendiği bir `CFile` nesneyi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim, Gecikmeli işleme için `COleDataSource` [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) üye işlevi kullanılarak nesnesine daha önce yerleştirilmiş bir biçimdir. Bu işlevin varsayılan uygulanması yalnızca FALSE değerini döndürür.

Bu gelişmiş bir geçersiz kılınabilir. Verilerinizi istenen biçimde ve ortamda sağlamak için bu işlevi geçersiz kılın. Verilerinize bağlı olarak, bunun yerine bu işlevin diğer sürümlerinden birini geçersiz kılmak isteyebilirsiniz. Birden çok depolama ortamını işlemek istiyorsanız, [OnRenderData](#onrenderdata)öğesini geçersiz kılın. Verileriniz bir dosya veya değişken boyutda ise, [OnRenderFileData](#onrenderfiledata)öğesini geçersiz kılın.

Daha fazla bilgi için Windows SDK bkz. [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) ve [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) .

##  <a name="onrenderglobaldata"></a>Cotaserverıtem:: OnRenderGlobalData

Belirtilen depolama ortamı genel bellek olduğunda, belirtilen biçimdeki verileri almak için Framework tarafından çağırılır.

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
Bilgilerin istendiği biçimi belirten [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder.

*phGlobal*<br/>
Verilerin döndürüleceği genel belleğe yönelik bir tanıtıcıya işaret eder. Bellek ayrılmışsa, bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim, Gecikmeli işleme için `COleDataSource` [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) üye işlevi kullanılarak nesnesine daha önce yerleştirilmiş bir biçimdir. Bu işlevin varsayılan uygulanması yalnızca FALSE değerini döndürür.

*PhGlobal* değeri null ise, yenı bır hglobalin ayrılmalı ve *phGlobal*'te döndürülmelidir. Aksi takdirde, *phGlobal* tarafından belirtilen HGLOBAL, verilerle doldurulmalıdır. HGLOBAL 'e yerleştirilmiş veri miktarı, bellek bloğunun geçerli boyutunu aşmamalıdır. Ayrıca, blok daha büyük bir boyuta yeniden ayrılamaz.

Bu gelişmiş bir geçersiz kılınabilir. Verilerinizi istenen biçimde ve ortamda sağlamak için bu işlevi geçersiz kılın. Verilerinize bağlı olarak, bunun yerine bu işlevin diğer sürümlerinden birini geçersiz kılmak isteyebilirsiniz. Birden çok depolama ortamını işlemek istiyorsanız, [OnRenderData](#onrenderdata)öğesini geçersiz kılın. Verileriniz bir dosya veya değişken boyutda ise, [OnRenderFileData](#onrenderfiledata)öğesini geçersiz kılın.

Daha fazla bilgi için Windows SDK bkz. [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) ve [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) .

##  <a name="onsetcolorscheme"></a>Cotaserverıtem:: OnSetColorScheme

OLE öğesi düzenlenirken kullanılacak bir renk paleti belirtmek için Framework tarafından çağırılır.

```
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```

### <a name="parameters"></a>Parametreler

*lpLogPalette*<br/>
Windows [LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Renk paleti kullanılıyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulaması Microsoft Foundation Class Kitaplığı kullanılarak yazılmışsa, ilgili `COleClientItem` nesnenin [IOleObject:: SetColorScheme](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) işlevi çağrıldığında bu işlev çağrılır. Varsayılan uygulama yanlış döndürür. Önerilen paleti kullanmak istiyorsanız bu işlevi geçersiz kılın. Önerilen paleti kullanmak için sunucu uygulaması gerekli değildir.

Daha fazla bilgi için Windows SDK [IOleObject:: SetColorScheme](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) bölümüne bakın.

##  <a name="onsetdata"></a>Copaserverıtem:: OnSetData

OLE öğesinin verilerini belirtilen verilerle değiştirmek için Framework tarafından çağırılır.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
Verilerin biçimini belirten bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına yönelik işaretçi.

*Lpstgorta*<br/>
Verilerin bulunduğu bir [Stgorta](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına yönelik işaretçi.

*bRelease*<br/>
İşlev çağrısını tamamladıktan sonra kimin depolama ortamının sahipliğini olduğunu gösterir. Çağıran, depolama ortamı adına ayrılan kaynakları serbest bırakmaktan sorumlu kişiye karar veriyor. Çağıran bunu *bRelease*'i ayarlayarak yapar. *BRelease* sıfır değilse, sunucu öğesi sahipliğini alır ve onu kullanmayı bitirdiğinde ortamı serbest bırakır. *BRelease* 0 olduğunda, çağıran sahipliği korur ve sunucu öğesi depolama ortamını yalnızca çağrının süresi boyunca kullanabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sunucu öğesi, başarıyla edinene kadar verilerin sahipliğini almaz. Diğer bir deyişle, 0 döndürürse sahiplik almaz. Veri kaynağı sahiplik alırsa, [ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) işlevini çağırarak depolama ortamını serbest bırakır.

Varsayılan uygulama hiçbir şey yapmaz. OLE öğesinin verilerini belirtilen verilerle değiştirmek için bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz kılınabilir.

Daha fazla bilgi için Windows SDK bkz. [Stgmedium](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1), [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)ve [ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) .

##  <a name="onsetextent"></a>Cotaserverıtem:: OnSetExtent

OLE öğesine kapsayıcı belgesinde ne kadar kullanılabilir alan olduğunu söylemek için Framework tarafından çağırılır.

```
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,
    const CSize& size);
```

### <a name="parameters"></a>Parametreler

*nDrawAspect*<br/>
Sınırları belirtilmekte olan OLE öğesinin yönünü belirtir. Bu parametre aşağıdaki değerlerden herhangi birine sahip olabilir:

- DVASPECT_CONTENT öğesi, kapsayıcısı içinde katıştırılmış bir nesne olarak görüntülenebilecek şekilde temsil edilir.

- DVASPECT_THUMBNAIL öğesi, bir tarama aracında görüntülenebilmesi için bir "küçük resim" gösteriminde işlenir.

- DVASPECT_ICON öğesi bir simge ile temsil edilir.

- DVASPECT_DOCPRINT öğesi, Dosya menüsündeki Yazdır komutu kullanılarak yazdırılmış gibi gösterilir.

*boyutla*<br/>
OLE öğesinin yeni boyutunu belirten bir [CSize](../../atl-mfc-shared/reference/csize-class.md) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulama Microsoft Foundation Class Kitaplığı yazılmışsa, ilgili `COleClientItem` nesnenin [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) üye işlevi çağrıldığında bu işlev çağrılır. Varsayılan uygulama, *nDrawAspect* DVASPECT_CONTENT Ise, [m_sizeExtent](#m_sizeextent) üyesini belirtilen boyuta ayarlar; Aksi takdirde 0 döndürür. Öğenin boyutunu değiştirirken özel işleme gerçekleştirmek için bu işlevi geçersiz kılın.

##  <a name="onshow"></a>Cotaserverıtem:: OnShow

Sunucu uygulamasının OLE öğesini yerinde görüntülemesini istemek için Framework tarafından çağırılır.

```
virtual void OnShow();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle kapsayıcı uygulamasının kullanıcısı bir öğe oluşturduğunda veya öğenin gösterilmesi gereken Düzenle gibi bir fiil yürüttüğünde çağrılır. Varsayılan uygulama yerinde etkinleştirmeyi dener. Bu başarısız olursa, işlev OLE öğesini ayrı `OnOpen` bir pencerede göstermek için üye işlevini çağırır.

Bir OLE öğesi gösterildiğinde özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

##  <a name="onupdate"></a>Cotaserverıtem:: OnUpdate

Bir öğe değiştirildiğinde Framework tarafından çağırılır.

```
virtual void OnUpdate(
    COleServerItem* pSender,
    LPARAM lHint,
    CObject* pHint,
    DVASPECT nDrawAspect);
```

### <a name="parameters"></a>Parametreler

*pSender*<br/>
Belgeyi değiştiren öğenin işaretçisi. NULL olabilir.

*Lipucu*<br/>
Değişiklik hakkındaki bilgileri içerir.

*Phınt*<br/>
Değişiklik hakkında bilgi depolayan bir nesne işaretçisi.

*nDrawAspect*<br/>
DVASPECT numaralandırmasından bir değer. Bu parametre aşağıdaki değerlerden herhangi birine sahip olabilir:

- DVASPECT_CONTENT öğesi, kapsayıcısı içinde katıştırılmış bir nesne olarak görüntülenebilecek şekilde temsil edilir.

- DVASPECT_THUMBNAIL öğesi, bir tarama aracında görüntülenebilmesi için bir "küçük resim" gösteriminde işlenir.

- DVASPECT_ICON öğesi bir simge ile temsil edilir.

- DVASPECT_DOCPRINT öğesi, Dosya menüsündeki Yazdır komutu kullanılarak yazdırılmış gibi gösterilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, ipucunu veya göndericiden bağımsız olarak, [NotifyChanged](#notifychanged)yöntemini çağırır.

##  <a name="onupdateitems"></a>Cotaserverıtem:: Onupdateıtems

Sunucu belgesindeki tüm öğeleri güncelleştirmek için Framework tarafından çağırılır.

```
virtual void OnUpdateItems();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, belgedeki tüm `COleClientItem` nesneler için [UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink) 'i çağırır.

##  <a name="setitemname"></a>Cotaserverıtem:: setItemName

Adını ayarlamak için bağlantılı bir öğe oluşturduğunuzda bu işlevi çağırın.

```
void SetItemName(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parametreler

*lpszItemName*<br/>
Öğenin yeni adına yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Ad belge içinde benzersiz olmalıdır. Bağlı öğeyi düzenlemek için bir sunucu uygulaması çağrıldığında, uygulama bu adı kullanarak öğeyi bulur. Katıştırılmış öğeler için bu işlevi çağırmanız gerekmez.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CDocItem Sınıfı](../../mfc/reference/cdocitem-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[COleServerDoc Sınıfı](../../mfc/reference/coleserverdoc-class.md)<br/>
[COleTemplateServer Sınıfı](../../mfc/reference/coletemplateserver-class.md)
