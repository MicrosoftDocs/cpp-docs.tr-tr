---
title: COleServerItem Sınıfı
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
ms.openlocfilehash: 5373075cf6dfc54e6e2368e46f48f317fcec64d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376111"
---
# <a name="coleserveritem-class"></a>COleServerItem Sınıfı

OLE öğelerine sunucu arabirimi sağlar.

## <a name="syntax"></a>Sözdizimi

```
class COleServerItem : public CDocItem
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleServerItem::COleServerItem](#coleserveritem)|Bir `COleServerItem` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|Sunu ve dönüştürme biçimlerini `COleDataSource` bir nesneye yerleştirir.|
|[COleServerItem::CopyToClipboard](#copytoclipboard)|Öğeyi Pano'ya kopyalar.|
|[COleServerItem::DoDragDrop](#dodragdrop)|Sürükle ve bırak işlemi gerçekleştirir.|
|[COleServerItem::GetClipboardData](#getclipboarddata)|Veri aktarımı (sürükle ve bırak veya Pano) kullanılmak üzere veri kaynağını alır.|
|[COleServerItem::GetDocument](#getdocument)|Öğeyi içeren sunucu belgesini döndürür.|
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|Bir OLE öğesi için CF_EMBEDSOURCE veri alır.|
|[COleServerItem::GetItemName](#getitemname)|Öğenin adını döndürür. Yalnızca bağlantılı öğeler için kullanılır.|
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|Bir OLE öğesi için CF_LINKSOURCE verileri alır.|
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|Bir OLE öğesi için CF_OBJECTDESCRIPTOR verileri alır.|
|[COleServerItem::Bağlı](#isconnected)|Maddenin şu anda etkin bir kapsayıcıya bağlı olup olmadığını gösterir.|
|[COleServerItem::IsLinkedItem](#islinkeditem)|Maddenin bağlantılı bir OLE öğesini temsil edip etmediğini gösterir.|
|[COleServerItem::NotifyChanged](#notifychanged)|Otomatik bağlantı güncelleştirmesi ile tüm kapsayıcıları güncelleştirir.|
|[COleServerItem::OnDoVerb](#ondoverb)|Bir fiili yürütmek için çağrıldı.|
|[COleServerItem::OnDraw](#ondraw)|Kapsayıcı öğeyi çizmek istediğinde çağrılır; uygulanması gereklidir.|
|[COleServerItem::OnDrawEx](#ondrawex)|Özel madde çizimi için çağrıda bulunuldu.|
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|Pano'ya kopyalanacak verileri almak için çerçeve tarafından çağrılır.|
|[COleServerItem::OnGetExtent](#ongetextent)|OLE öğesinin boyutunu almak için çerçeve tarafından çağrılır.|
|[COleServerItem::OnInitFromData](#oninitfromdata)|Belirtilen veri aktarım nesnesinin içeriğini kullanarak bir OLE öğesini başlatmaçerçevesi tarafından çağrılır.|
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|Bağlantılı öğelerin güncelleştirme gerekip gerekmediğini belirlemek için çağrılır.|
|[COleServerItem::OnRenderData](#onrenderdata)|Gecikmiş işlemenin bir parçası olarak verileri alır.|
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|Gecikmiş işlemenin `CFile` bir parçası olarak verileri bir nesneye alır.|
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|Gecikmiş işlemenin bir parçası olarak verileri bir HGLOBAL'a alır.|
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|Öğenin renk düzenini ayarlamak için çağrıldı.|
|[COleServerItem::OnSetData](#onsetdata)|Öğenin verilerini ayarlamak için çağrıldı.|
|[COleServerItem::OnSetExtent](#onsetextent)|OLE öğesinin boyutunu ayarlamak için çerçeve tarafından çağrılır.|
|[COleServerItem::OnUpdate](#onupdate)|Maddenin ait olduğu belgenin bir bölümü değiştirildiğinde çağrılır.|
|[COleServerItem::OnUpdateItems](#onupdateitems)|Sunucu belgesindeki tüm öğelerin sunu önbelleğini güncelleştirmek için çağrıldı.|
|[COleServerItem::SetItemName](#setitemname)|Öğenin adını ayarlar. Yalnızca bağlantılı öğeler için kullanılır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleServerItem::GetDataSource](#getdatasource)|Dönüşüm biçimlerini depolamak için kullanılan nesneyi alır.|
|[COleServerItem::OnHide](#onhide)|OLE öğesini gizlemek için çerçeve tarafından çağrılır.|
|[COleServerItem::Açık](#onopen)|OLE öğesini kendi üst düzey penceresinde görüntülemek için çerçeve tarafından çağrılır.|
|[COleServerItem::OnShow](#onshow)|Kapsayıcı öğeyi göstermek istediğinde çağrılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleServerItem::m_sizeExtent](#m_sizeextent)|Sunucuya OLE öğesinin ne kadarının görünür olduğu hakkında bilgi verir.|

## <a name="remarks"></a>Açıklamalar

Bağlantılı öğe, sunucu belgesinin bazılarını veya tümünün temsil edilebilir. Katışdırılmış öğe her zaman tüm sunucu belgesini temsil eder.

Sınıf, `COleServerItem` genellikle kapsayıcı uygulamasından gelen isteklere yanıt olarak, OLE sistem dinamik bağlantı kitaplıkları (DLs) tarafından çağrılan birkaç geçersiz ögemeden üye işlev tanımlar. Bu üye işlevler, kapsayıcı uygulamasının öğeyi görüntülemek, fiillerini yürütmek veya verilerini çeşitli biçimlerde almak gibi çeşitli şekillerde dolaylı olarak işlemesine olanak sağlar.

Kullanmak `COleServerItem`için, ondan bir sınıf türetmek ve [OnDraw](#ondraw) ve [Serialize](../../mfc/reference/cobject-class.md#serialize) üye işlevleri uygulamak. İşlev, `OnDraw` bir kapsayıcı uygulaması bileşik bir belge açtığında görüntülenmesine izin veren bir öğenin metadosya gösterimini sağlar. `Serialize` İşlev, `CObject` katışılmış bir öğenin sunucu ve kapsayıcı uygulamaları arasında aktarılmasına izin vererek bir öğenin yerel temsilini sağlar. [OnGetExtent,](#ongetextent) kabın maddeyi boyutlandırmasını sağlayarak maddenin doğal boyutunu kapsayıcıya sağlar.

Sunucular ve ilgili konular hakkında daha fazla bilgi için, makale [Sunucuları bakın: Bir Sunucu uygulama](../../mfc/servers-implementing-a-server.md) ve "Bir Kapsayıcı / Sunucu Uygulaması Oluşturma" makale [Kapsayıcılar: Gelişmiş Özellikler](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

`COleServerItem`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="coleserveritemaddotherclipboarddata"></a><a name="addotherclipboarddata"></a>COleServerItem::AddOtherClipboardData

OLE öğesinin sunusunu ve dönüşüm biçimlerini belirtilen `COleDataSource` nesneye yerleştirmek için bu işlevi çağırın.

```
void AddOtherClipboardData(COleDataSource* pDataSource);
```

### <a name="parameters"></a>Parametreler

*pDataSource*<br/>
Verilerin yerleştirilmesi `COleDataSource` gereken nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Öğeiçin sunu biçimini (metadosya resmi) sağlamak için [OnDraw](#ondraw) üye işlevini uygulamış olmalısınız. Diğer dönüşüm biçimlerini desteklemek için, [GetDataSource](#getdatasource) tarafından döndürülen [COleDataSource](../../mfc/reference/coledatasource-class.md) nesnesini kullanarak kaydedin ve desteklemek istediğiniz biçimlerde veri sağlamak için [OnRenderData](#onrenderdata) üye işlevini geçersiz kılın.

## <a name="coleserveritemcoleserveritem"></a><a name="coleserveritem"></a>COleServerItem::COleServerItem

Bir `COleServerItem` nesne inşa eder ve sunucu belgesinin belge öğeleri koleksiyonuna ekler.

```
COleServerItem(
    COleServerDoc* pServerDoc,
    BOOL bAutoDelete);
```

### <a name="parameters"></a>Parametreler

*pServerDoc*<br/>
Yeni öğeyi içerecek belgeyi işaretçi.

*bAutoDelete*<br/>
Bir bağlantı yayımlandığında nesnenin silinip silinemeyeceğini belirten bayrak. Nesne belgenizin `COleServerItem` verilerinin silinmesi gereken ayrılmaz bir parçasıysa bunu FALSE olarak ayarlayın. Nesne, belgenizin verilerinde çerçeve tarafından silinebilecek bir aralığı tanımlamak için kullanılan ikincil bir yapıysa bunu TRUE olarak ayarlayın.

## <a name="coleserveritemcopytoclipboard"></a><a name="copytoclipboard"></a>COleServerItem::CopyToClipboard

OLE öğesini Pano'ya kopyalamak için bu işlevi arayın.

```
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```

### <a name="parameters"></a>Parametreler

*bIncludeLink*<br/>
Bağlantı verilerinin Pano'ya kopyaedilmesi gerekiyorsa bunu TRUE olarak ayarlayın. Sunucu uygulamanız bağlantıları desteklemiyorsa bunu FALSE olarak ayarlayın.

### <a name="remarks"></a>Açıklamalar

İşlev, OLE öğesinin verilerini destekleyen biçimlerde içeren bir [COleDataSource](../../mfc/reference/coledatasource-class.md) nesnesi oluşturmak için [OnGetClipboardData](#ongetclipboarddata) üye işlevini kullanır. İşlev daha `COleDataSource` sonra [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) işlevini kullanarak nesneyi Pano'ya yerleştirir. Nesne, `COleDataSource` öğenin yerel verilerini ve CF_METAFILEPICT biçimindeki gösteriminin yanı sıra desteklemeyi seçtiğiniz dönüşüm biçimlerindeki verileri de içerir. Bu üye işlevin çalışması için [Serialize](../../mfc/reference/cobject-class.md#serialize) ve [OnDraw](#ondraw) uygulamış olmalısınız.

## <a name="coleserveritemdodragdrop"></a><a name="dodragdrop"></a>COleServerItem::DoDragDrop

Sürükle `DoDragDrop` ve bırak işlemi gerçekleştirmek için üye işlevi arayın.

```
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,
    CPoint ptOffset,
    BOOL bIncludeLink = FALSE,
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,
    LPCRECT lpRectStartDrag = NULL);
```

### <a name="parameters"></a>Parametreler

*lpRectItem*<br/>
Öğenin ekranda, piksellerde, istemci alanına göre dikdörtgeni.

*ptOffset*<br/>
Sürükleme sırasında fare konumunun bulunduğu *lpItemRect'ten* ofset.

*bIncludeLink*<br/>
Bağlantı verilerinin Pano'ya kopyaedilmesi gerekiyorsa bunu TRUE olarak ayarlayın. Uygulamanız bağlantıları desteklemiyorsa FALSE olarak ayarlayın.

*dwEfektler*<br/>
Sürükleme kaynağının sürükleme işleminde izin verdiği efektleri (Kopyala, Taşı ve Bağlantı'nın bir leşimi) belirler.

*lpRectStartDrag*<br/>
Sürüklemenin gerçekte nerede başladığını tanımlayan dikdörtgeni işaretle. Daha fazla bilgi için aşağıdaki Açıklamalar bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

DROPEFFECT numaralandırmasından bir değer. DROPEFFECT_MOVE ise, özgün veriler kaldırılmalıdır.

### <a name="remarks"></a>Açıklamalar

Sürükle ve bırak işlemi hemen başlamaz. Fare *imleci, lpRectStartDrag* tarafından belirtilen dikdörtgeni bırakana veya belirli sayıda milisaniye geçene kadar bekler. *lpRectStartDrag* NULL ise, fare imleci bir pikseli hareket ettirdiğinde sürüklemenin başlaması için varsayılan bir dikdörtgen kullanılır.

Gecikme süresi bir kayıt defteri anahtarı ayarı ile belirtilir. CWinApp'ı arayarak gecikme süresini [değiştirebilirsiniz::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) veya [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Gecikme süresini belirtmezseniz, varsayılan değeri 200 milisaniye olarak kullanılır. Sürükleme gecikme süresi aşağıdaki gibi depolanır:

- Windows NT Sürükle gecikme süresi HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay'da depolanır.

- Windows 3.x Sürükleme gecikme süresi WIN'de depolanır. INI dosyası, [Windows} bölümünün altında.

- Windows 95/98 Sürükleme gecikme süresi WIN'in önbelleğe alınmış sürümünde depolanır. ını.

Sürükleme gecikmesi bilgilerinin kayıt defterinde veya .' de nasıl depolandırılabilen hakkında daha fazla bilgi için. INI dosyası, Windows SDK'daki [WriteProfileString'e](/windows/win32/api/winbase/nf-winbase-writeprofilestringw) bakın.

## <a name="coleserveritemgetclipboarddata"></a><a name="getclipboarddata"></a>COleServerItem::GetClipboardData

[CopyToClipboard](#copytoclipboard) 'u aradıysanız, belirtilen [COleDataSource](../../mfc/reference/coledatasource-class.md) nesnesini Pano'ya kopyalanacak tüm verilerle doldurmak için bu işlevi arayın [(DoDragDrop'u](#dodragdrop)ararsanız aynı veriler de aktarılır).

```
void GetClipboardData(
    COleDataSource* pDataSource,
    BOOL bIncludeLink = FALSE,
    LPPOINT lpOffset = NULL,
    LPSIZE lpSize = NULL);
```

### <a name="parameters"></a>Parametreler

*pDataSource*<br/>
Desteklenen tüm `COleDataSource` biçimlerde OLE öğesinin verilerini alacak nesneyi işaretleyin.

*bIncludeLink*<br/>
Bağlantı verilerinin Pano'ya kopyaedilmesi gerekiyorsa DOĞRU. Sunucu uygulamanız bağlantıları desteklemiyorsa FALSE.

*lpOffset*<br/>
Nesnenin kaynağından fare imlecinin piksel olarak ofset.

*lpSize*<br/>
Piksellerde nesnenin boyutu.

### <a name="remarks"></a>Açıklamalar

Bu işlev, OLE öğesinin yerel verilerini almak için [GetEmbedSourceData](#getembedsourcedata) üye işlevini çağırır ve sunu biçimini ve desteklenen dönüşüm biçimlerini almak için [AddOtherClipboardData](#addotherclipboarddata) üye işlevini çağırır. *bIncludeLink* TRUE ise, işlev öğenin bağlantı verilerini almak için [GetLinkSourceData'yı](#getlinksourcedata) da çağırır.

Bu biçimlerden önce veya sonra bir `COleDataSource` nesneye biçimler koymak istiyorsanız `CopyToClipboard`bu işlevi geçersiz kılın.

## <a name="coleserveritemgetdatasource"></a><a name="getdatasource"></a>COleServerItem::GetDataSource

Sunucu uygulamasının desteklediği dönüştürme biçimlerini depolamak için kullanılan [COleDataSource](../../mfc/reference/coledatasource-class.md) nesnesini almak için bu işlevi arayın.

```
COleDataSource* GetDataSource();
```

### <a name="return-value"></a>Dönüş Değeri

Dönüşüm biçimlerini `COleDataSource` depolamak için kullanılan nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Sunucu uygulamanızın veri aktarım işlemleri sırasında çeşitli biçimlerde veri sunmasını istiyorsanız, `COleDataSource` bu biçimleri bu işlev tarafından döndürülen nesneye kaydedin. Örneğin, Pano veya sürükle ve bırak işlemleri için OLE öğesinin CF_TEXT bir temsilini sağlamak `COleDataSource` istiyorsanız, biçimi bu işlevin `OnRenderXxxData` döndürüğü nesneye kaydeder ve ardından verileri sağlamak için üye işlevi geçersiz kılarsınız.

## <a name="coleserveritemgetdocument"></a><a name="getdocument"></a>COleServerItem::GetDocument

Öğeyi içeren belgeye işaretçi almak için bu işlevi arayın.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeyi içeren belgenin işaretçisi; Öğe belgenin bir parçası değilse NULL.

### <a name="remarks"></a>Açıklamalar

Bu, bağımsız değişken olarak aktardığınız sunucu belgesine `COleServerItem` erişim sağlar.

## <a name="coleserveritemgetembedsourcedata"></a><a name="getembedsourcedata"></a>COleServerItem::GetEmbedSourceData

Bir OLE öğesi için CF_EMBEDSOURCE verilerini almak için bu işlevi arayın.

```
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parametreler

*lpStgMedium*<br/>
OLE öğesi için CF_EMBEDSOURCE verilerini alacak [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısını işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu biçim, öğenin yerel verilerini içerir. Bu işlevin `Serialize` düzgün çalışması için üye işlevi uygulamış olmalısınız.

Sonuç daha sonra [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata)kullanılarak bir veri kaynağına eklenebilir. Bu fonksiyon Otomatik olarak [COleServerItem tarafından çağrılır::OnGetClipboardData](#ongetclipboarddata).

Daha fazla bilgi için Windows SDK'daki [STGMEDIUM'a](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) bakın.

## <a name="coleserveritemgetitemname"></a><a name="getitemname"></a>COleServerItem::GetItemName

Öğenin adını almak için bu işlevi arayın.

```
const CString& GetItemName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğenin adı.

### <a name="remarks"></a>Açıklamalar

Bu işlevi genellikle yalnızca bağlantılı öğeler için çağırırsınız.

## <a name="coleserveritemgetlinksourcedata"></a><a name="getlinksourcedata"></a>COleServerItem::GetLinkSourceData

Bir OLE öğesinin CF_LINKSOURCE verilerini almak için bu işlevi arayın.

```
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parametreler

*lpStgMedium*<br/>
OLE öğesi için CF_LINKSOURCE verilerini alacak [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısını işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu biçim, OLE öğesinin türünü açıklayan CLSID'yi ve OLE öğesini içeren belgeyi bulmak için gereken bilgileri içerir.

Sonuç daha sonra COleDataSource ile bir veri kaynağına [eklenebilir::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Bu [işlev, OnGetClipboardData](#ongetclipboarddata)tarafından otomatik olarak çağrılır.

Daha fazla bilgi için Windows SDK'daki [STGMEDIUM'a](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) bakın.

## <a name="coleserveritemgetobjectdescriptordata"></a><a name="getobjectdescriptordata"></a>COleServerItem::GetObjectDescriptorData

Bir OLE öğesinin CF_OBJECTDESCRIPTOR verilerini almak için bu işlevi arayın.

```
void GetObjectDescriptorData(
    LPPOINT lpOffset,
    LPSIZE lpSize,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parametreler

*lpOffset*<br/>
Farenin ofset ole öğenin sol üst köşesinden tıklayın. NULL olabilir.

*lpSize*<br/>
OLE öğesinin boyutu. NULL olabilir.

*lpStgMedium*<br/>
OLE öğesi için CF_OBJECTDESCRIPTOR verilerini alacak [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısını işaretleyin.

### <a name="remarks"></a>Açıklamalar

Bilgiler *lpStgMedium* `STGMEDIUM` tarafından işaret edilen yapıya kopyalanır. Bu biçim, Özel Yapıştır iletişim kutusu için gereken bilgileri içerir.

Daha fazla bilgi için Windows SDK'daki [STGMEDIUM'a](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) bakın.

## <a name="coleserveritemisconnected"></a><a name="isconnected"></a>COleServerItem::Bağlı

OLE öğesinin bağlı olup olmadığını görmek için bu işlevi arayın.

```
BOOL IsConnected() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe bağlıysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir veya daha fazla kapsayıcıda öğeye başvuru varsa, OLE öğesi bağlı olarak kabul edilir. Başvuru sayısı 0'dan büyükse veya katıştırılmış bir öğeyse, öğe bağlanır.

## <a name="coleserveritemislinkeditem"></a><a name="islinkeditem"></a>COleServerItem::IsLinkedItem

OLE öğesinin bağlantılı bir öğe olup olmadığını görmek için bu işlevi arayın.

```
BOOL IsLinkedItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe bağlantılı bir öğeyse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Öğe geçerliyse ve belgenin katıştırılmış öğeler listesinde döndürülmezse bir öğe bağlanır. Bağlı bir öğe bir kapsayıcıya bağlı olabilir veya olmayabilir.

Hem bağlantılı hem de katıştırılmış öğeler için aynı sınıfı kullanmak yaygındır. `IsLinkedItem`birçok kez kod yaygın olsa da, bağlantılı öğelerin katıştırılmış öğelerden farklı davranmasını sağlar.

## <a name="coleserveritemm_sizeextent"></a><a name="m_sizeextent"></a>COleServerItem::m_sizeExtent

Bu üye sunucuya nesnenin ne kadarının kapsayıcı belgede görünür olduğunu söyler.

```
CSize m_sizeExtent;
```

### <a name="remarks"></a>Açıklamalar

[OnSetExtent'in](#onsetextent) varsayılan uygulaması bu üyeyi ayarlar.

## <a name="coleserveritemnotifychanged"></a><a name="notifychanged"></a>COleServerItem::NotifyChanged

Bağlı öğe değiştirildikten sonra bu işlevi arayın.

```
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>Parametreler

*nDrawAspect*<br/>
DVASPECT numaralandırmasından, OLE öğesinin hangi yönünün değiştiğini gösteren bir değer. Bu parametre aşağıdaki değerlerden herhangi biri olabilir:

- DVASPECT_CONTENT Öğe, kapsayıcının içinde katıştırılmış bir nesne olarak görüntülenecek şekilde temsil edilir.

- DVASPECT_THUMBNAIL Öğesi, bir tarama aracında görüntülenebilecek şekilde "küçük resim" gösteriminde işlenir.

- DVASPECT_ICON Öğe bir simge ile temsil edilir.

- DVASPECT_DOCPRINT Öğe, Dosya menüsünden Yazdır komutu kullanılarak basılmış gibi temsil edilir.

### <a name="remarks"></a>Açıklamalar

Bir kapsayıcı öğesi belgeye otomatik bağlantıyla bağlıysa, öğe değişiklikleri yansıtacak şekilde güncelleştirilir. Microsoft Foundation Class Kitaplığı kullanılarak yazılan kapsayıcı uygulamalarında [COleClientItem::OnChange](../../mfc/reference/coleclientitem-class.md#onchange) yanıt olarak çağrılır.

## <a name="coleserveritemondoverb"></a><a name="ondoverb"></a>COleServerItem::OnDoVerb

Belirtilen fiili yürütmek için çerçeve tarafından çağrılır.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Parametreler

*iFiil*<br/>
Yürütmek için fiil belirtir. Aşağıdakilerden herhangi biri olabilir:

|Değer|Anlamı|Sembol|
|-----------|-------------|------------|
|0|Birincil fiil|OLEIVERB_PRIMARY|
|1|İkincil fiil|(Yok)|
|- 1|Düzenleme için öğeyi görüntüleme|OLEIVERB_SHOW|
|- 2|Öğeyi ayrı bir pencerede edin|OLEIVERB_OPEN|
|- 3|Öğeyi gizle|OLEIVERB_HIDE|

-1 değeri genellikle başka bir fiilin diğer adıdır. Açık düzenleme desteklenmiyorsa, -2 -1 ile aynı etkiye sahiptir. Ek değerler için Windows SDK'daki [IOleObject::DoVerb'e](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) bakın.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulaması Microsoft Foundation Class Library ile yazılmışsa, [COleClientItem::İlgili](../../mfc/reference/coleclientitem-class.md#activate) `COleClientItem` nesnenin üye işlevini etkinleştir'i çağrıldığında bu işlev çağrılır. Varsayılan uygulama, birincil fiil veya OLEIVERB_SHOW belirtilmişse [OnShow](#onshow) üye işlevini, ikincil fiil veya OLEIVERB_OPEN belirtilmişse [OnOpen'i](#onopen) ve OLEIVERB_HIDE belirtilmişse [OnHide'yi](#onhide) çağırır. *iVerb* yukarıda `OnShow` listelenen fiillerden biri değilse varsayılan uygulama çağırır.

Birincil fiiliniz öğeyi göstermiyorsa bu işlevi geçersiz kılın. Örneğin, öğe bir ses kaydıysa ve birincil fiili Oynat ise, öğeyi oynatmak için sunucu uygulamasını görüntülemeniz gerekmez.

Daha fazla bilgi için Windows SDK'daki [IOleObject::DoVerb'e](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) bakın.

## <a name="coleserveritemondraw"></a><a name="ondraw"></a>COleServerItem::OnDraw

OLE öğesini meta bir dosyaya işlemek için çerçeve tarafından çağrılır.

```
virtual BOOL OnDraw(
    CDC* pDC,
    CSize& rSize) = 0;
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Öğeyi çizmek [CDC](../../mfc/reference/cdc-class.md) için CDC nesnesine bir işaretçi. Görüntü bağlamı otomatik olarak öznitelik görüntüleme bağlamına bağlanır, böylece öznitelik işlevlerini çağırabilirsiniz, ancak bunu yapmak metadosya aygıtına özgü olmasını sağlar.

*rBoyut*<br/>
Metadosyayı çizmek için HIMETRIC birimlerinde boyut.

### <a name="return-value"></a>Dönüş Değeri

Öğe başarıyla çizilmişse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

OLE öğesinin metadosya gösterimi, öğeyi kapsayıcı uygulamasında görüntülemek için kullanılır. Kapsayıcı uygulaması Microsoft Hazırlık Sınıfı Kitaplığı ile yazılmışsa, metadosya ilgili [COleClientItem](../../mfc/reference/coleclientitem-class.md) nesnesinin [Draw](../../mfc/reference/coleclientitem-class.md#draw) üye işlevi tarafından kullanılır. Varsayılan uygulama yoktur. Öğeyi belirtilen aygıt bağlamına çekmek için bu işlevi geçersiz kılmanız gerekir.

## <a name="coleserveritemondrawex"></a><a name="ondrawex"></a>COleServerItem::OnDrawEx

Tüm çizim için çerçeve tarafından çağrıldı.

```
virtual BOOL OnDrawEx(
    CDC* pDC,
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Öğeyi çizmek [CDC](../../mfc/reference/cdc-class.md) için CDC nesnesine bir işaretçi. DC, öznitelik işlevlerini arayabilmeniz için öznitelik DC'ye otomatik olarak bağlanır, ancak bunu yapmak metadosya aygıtına özgü olmasını sağlar.

*nDrawAspect*<br/>
DVASPECT numaralandırmasından bir değer. Bu parametre aşağıdaki değerlerden herhangi biri olabilir:

- DVASPECT_CONTENT Öğe, kapsayıcının içinde katıştırılmış bir nesne olarak görüntülenecek şekilde temsil edilir.

- DVASPECT_THUMBNAIL Öğesi, bir tarama aracında görüntülenebilecek şekilde "küçük resim" gösteriminde işlenir.

- DVASPECT_ICON Öğe bir simge ile temsil edilir.

- DVASPECT_DOCPRINT Öğe, Dosya menüsünden Yazdır komutu kullanılarak basılmış gibi temsil edilir.

*rBoyut*<br/>
HIMETRIC birimlerindeki maddenin boyutu.

### <a name="return-value"></a>Dönüş Değeri

Öğe başarıyla çizilmişse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

DVASPECT `OnDraw` DVASPECT_CONTENT eşit olduğunda varsayılan uygulama çağırır; aksi takdirde başarısız olur.

DVASPECT_ICON veya DVASPECT_THUMBNAIL gibi DVASPECT_CONTENT dışındaki yönlerin sunu verilerini sağlamak için bu işlevi geçersiz kılın.

## <a name="coleserveritemongetclipboarddata"></a><a name="ongetclipboarddata"></a>COleServerItem::OnGetClipboardData

[CopyToClipboard](#copytoclipboard) üye `COleDataSource` işlevine yapılan bir çağrı yla Panoya yerleştirilecek tüm verileri içeren bir nesneyi almak için çerçeve tarafından çağrılır.

```
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,
    LPPOINT lpOffset,
    LPSIZE lpSize);
```

### <a name="parameters"></a>Parametreler

*bIncludeLink*<br/>
Bağlantı verilerinin Pano'ya kopyaedilmesi gerekiyorsa bunu TRUE olarak ayarlayın. Sunucu uygulamanız bağlantıları desteklemiyorsa bunu FALSE olarak ayarlayın.

*lpOffset*<br/>
Fare imlecinin piksellerde nesnenin kaynağından mahsup.

*lpSize*<br/>
Piksellerde nesnenin boyutu.

### <a name="return-value"></a>Dönüş Değeri

Pano verilerini içeren [bir COleDataSource](../../mfc/reference/coledatasource-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması [GetClipboardData](#getclipboarddata)çağırır.

## <a name="coleserveritemongetextent"></a><a name="ongetextent"></a>COleServerItem::OnGetExtent

HiMETRIC birimlerinde OLE öğesinin boyutunu almak için çerçeve tarafından çağrılır.

```
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Parametreler

*nDrawAspect*<br/>
OLE öğesinin sınırları alınacak yönünü belirtir. Bu parametre aşağıdaki değerlerden herhangi biri olabilir:

- DVASPECT_CONTENT Öğe, kapsayıcının içinde katıştırılmış bir nesne olarak görüntülenecek şekilde temsil edilir.

- DVASPECT_THUMBNAIL Öğesi, bir tarama aracında görüntülenebilecek şekilde "küçük resim" gösteriminde işlenir.

- DVASPECT_ICON Öğe bir simge ile temsil edilir.

- DVASPECT_DOCPRINT Öğe, Dosya menüsünden Yazdır komutu kullanılarak basılmış gibi temsil edilir.

*rBoyut*<br/>
OLE `CSize` öğesinin boyutunu alacak bir nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulaması Microsoft Hazırlık Sınıfı Kitaplığı ile yazılmışsa, bu işlev, ilgili `COleClientItem` nesnenin [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) üye işlevi çağrıldığında çağrılır. Varsayılan uygulama hiçbir şey yapmaz. Bunu kendin uygulamalısın. OLE öğesinin boyutu için bir istek işlerken özel işleme gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

## <a name="coleserveritemonhide"></a><a name="onhide"></a>COleServerItem::OnHide

OLE öğesini gizlemek için çerçeve tarafından çağrılır.

```
virtual void OnHide();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan çağrılar `COleServerDoc::OnShowDocument( FALSE )`. İşlev ayrıca ole öğesinin gizlendiğini kapsayıcıya da haber vetir. Bir OLE öğesini gizlediğinde özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

## <a name="coleserveritemoninitfromdata"></a><a name="oninitfromdata"></a>COleServerItem::OnInitFromData

*pDataObject*içeriğini kullanarak bir OLE öğesini başlatmayı çerçeve tarafından çağrıldı.

```
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,
    BOOL bCreation);
```

### <a name="parameters"></a>Parametreler

*pDataObject*<br/>
OLE öğesini başlatmaiçin çeşitli biçimlerde veri içeren bir OLE veri nesnesine işaretçi.

*bCreation*<br/>
İşlev, bir kapsayıcı uygulaması tarafından yeni oluşturulan bir OLE öğesini başlatmaya çağrılırsa DOĞRU. İşlev zaten varolan bir OLE öğesinin içeriğini değiştirmek için çağrılırsa FALSE.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*bCreation* TRUE ise, bir kapsayıcı geçerli seçimi temel alan Yeni Nesne Ekle uygularsa bu işlev çağrılır. Seçilen veriler, yeni OLE öğesi oluşturulurken kullanılır. Örneğin, bir elektronik tablo programında bir hücre aralığı seçip ardından seçili aralıktaki değerleri temel alan bir grafik oluşturmak için Yeni Nesne Ekle'yi kullanırken. Varsayılan uygulama hiçbir şey yapmaz. *pDataObject* tarafından sunulanlardan kabul edilebilir bir biçim seçmek ve sağlanan verilere dayanarak OLE öğesini başlatmak için bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz.

Daha fazla bilgi için [Bkz. IOleObject::InitFromData](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata) in windows SDK.

## <a name="coleserveritemonopen"></a><a name="onopen"></a>COleServerItem::Açık

OLE öğesini yerinde değil, sunucu uygulamasının ayrı bir örneğinde görüntülemek için çerçeve tarafından çağrılır.

```
virtual void OnOpen();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, OLE öğesini içeren belgeyi görüntüleyen ilk kare penceresini etkinleştirir; uygulama bir mini sunucuysa, varsayılan uygulama ana pencereyi gösterir. İşlev ayrıca OLE öğesinin açıldığını kapsayıcıya da haber vetir.

Bir OLE öğesini açarken özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Bu, özellikle açıldığında seçimi bağlantıya ayarlamak istediğiniz bağlantılı öğelerde yaygındır.

Daha fazla bilgi için Bkz. Windows SDK'daki [IOleClientSite::OnShowWindow.](/windows/win32/api/oleidl/nf-oleidl-ioleclientsite-onshowwindow)

## <a name="coleserveritemonqueryupdateitems"></a><a name="onqueryupdateitems"></a>COleServerItem::OnQueryUpdateItems

Geçerli sunucu belgesinde bağlantılı öğelerin güncel olup olmadığını belirlemek için çerçeve tarafından çağrılır.

```
virtual BOOL OnQueryUpdateItems();
```

### <a name="return-value"></a>Dönüş Değeri

Belgede güncelleştirmeye ihtiyaç duyan öğeler varsa sıfıra değil; Tüm öğeler güncelse 0.

### <a name="remarks"></a>Açıklamalar

Kaynak belgesi değiştirildiyse, ancak bağlı madde belgedeki değişiklikleri yansıtacak şekilde güncelleştirilmediyse, öğe güncel değildir.

## <a name="coleserveritemonrenderdata"></a><a name="onrenderdata"></a>COleServerItem::OnRenderData

Belirtilen biçimde veri almak için çerçeve tarafından çağrılır.

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
Bilgilerin istendiği biçimi belirten [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder.

*lpStgMedium*<br/>
Verilerin döndürülmek üzere olduğu bir [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim, gecikmiş işleme için `COleDataSource` DelayRenderData veya [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) üye işlevini kullanarak nesneye daha önce yerleştirilen biçimdir. [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Bu işlevin varsayılan uygulaması, sağlanan depolama ortamı bir dosya veya bellek ise, sırasıyla [OnRenderFileData](#onrenderfiledata) veya [OnRenderGlobalData](#onrenderglobaldata)çağırır. Bu biçimlerin hiçbiri sağlanmazsa, varsayılan uygulama 0 döndürür ve hiçbir şey yapmaz.

*LPStgMedium*-> *tymed* TYMED_NULL ise, STGMEDIUM *lpFormatEtc->tymed*tarafından belirtildiği şekilde tahsis edilmeli ve doldurulmalıdır. TYMED_NULL değilse, STGMEDIUM verilerle birlikte doldurulmalıdır.

Bu gelişmiş bir geçersiz. Verilerinizi istenen biçimde ve ortamda sağlamak için bu işlevi geçersiz kılın. Verilerinize bağlı olarak, bunun yerine bu işlevin diğer sürümlerinden birini geçersiz kılmak isteyebilirsiniz. Verileriniz küçükse ve boyutu sabitse, geçersiz kılın. `OnRenderGlobalData` Verileriniz bir dosyadaysa veya değişken boyuttaysa `OnRenderFileData`geçersiz kılın.

Daha fazla bilgi için Windows SDK'da [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata), [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1), [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)ve [TYMED'e](/windows/win32/api/objidl/ne-objidl-tymed) bakın.

## <a name="coleserveritemonrenderfiledata"></a><a name="onrenderfiledata"></a>COleServerItem::OnRenderFileData

Depolama ortamı bir dosya olduğunda, belirtilen biçimde veri almak için çerçeve tarafından çağrılır.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
Bilgilerin istendiği biçimi belirten [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder.

*pFile*<br/>
Verilerin oluşturulacak olduğu nesneyi `CFile` işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim, gecikmiş işleme için `COleDataSource` [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) üye işlevini kullanarak nesneye daha önce yerleştirilen biçimdir. Bu işlevin varsayılan uygulaması sadece FALSE döndürür.

Bu gelişmiş bir geçersiz. Verilerinizi istenen biçimde ve ortamda sağlamak için bu işlevi geçersiz kılın. Verilerinize bağlı olarak, bunun yerine bu işlevin diğer sürümlerinden birini geçersiz kılmak isteyebilirsiniz. Birden çok depolama ortamını işlemek istiyorsanız, [OnRenderData'yı](#onrenderdata)geçersiz kılın. Verileriniz bir dosyadaysa veya değişken boyutundaysa, [OnRenderFileData'yı](#onrenderfiledata)geçersiz kılın.

Daha fazla bilgi için Bkz. Windows SDK'da [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) ve [FORMATETC.](/windows/win32/api/objidl/ns-objidl-formatetc)

## <a name="coleserveritemonrenderglobaldata"></a><a name="onrenderglobaldata"></a>COleServerItem::OnRenderGlobalData

Belirtilen depolama ortamı genel bellek olduğunda, belirtilen biçimde veri almak için çerçeve tarafından çağrılır.

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
Bilgilerin istendiği biçimi belirten [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder.

*phGlobal*<br/>
Verilerin döndürülmek üzere olduğu genel belleğe işaret eder. Bellek ayrılmamışsa, bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim, gecikmiş işleme için `COleDataSource` [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) üye işlevini kullanarak nesneye daha önce yerleştirilen biçimdir. Bu işlevin varsayılan uygulaması sadece FALSE döndürür.

*phGlobal* NULL ise, o zaman yeni bir HGLOBAL tahsis edilmeli ve *phGlobal*döndürülmelidir. Aksi takdirde, *phGlobal* tarafından belirtilen HGLOBAL verilerle doldurulmalıdır. HGLOBAL'a yerleştirilen veri miktarı bellek bloğunun geçerli boyutunu aşmamalıdır. Ayrıca, blok daha büyük bir boyuta yeniden tahsis edilemez.

Bu gelişmiş bir geçersiz. Verilerinizi istenen biçimde ve ortamda sağlamak için bu işlevi geçersiz kılın. Verilerinize bağlı olarak, bunun yerine bu işlevin diğer sürümlerinden birini geçersiz kılmak isteyebilirsiniz. Birden çok depolama ortamını işlemek istiyorsanız, [OnRenderData'yı](#onrenderdata)geçersiz kılın. Verileriniz bir dosyadaysa veya değişken boyutundaysa, [OnRenderFileData'yı](#onrenderfiledata)geçersiz kılın.

Daha fazla bilgi için Bkz. Windows SDK'da [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) ve [FORMATETC.](/windows/win32/api/objidl/ns-objidl-formatetc)

## <a name="coleserveritemonsetcolorscheme"></a><a name="onsetcolorscheme"></a>COleServerItem::OnSetColorScheme

OLE öğesini düzenlerken kullanılacak bir renk paleti belirtmek için çerçeve tarafından çağrılır.

```
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```

### <a name="parameters"></a>Parametreler

*lpLogPalette*<br/>
Windows [LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette) yapısıiçin işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Renk paleti kullanılırsa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulaması Microsoft Hazırlık Sınıfı Kitaplığı kullanılarak yazılmışsa, bu işlev, ilgili `COleClientItem` nesnenin [IOleObject::SetColorScheme](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) işlevi çağrıldığında çağrılır. Varsayılan uygulama FALSE döndürür. Önerilen paletkullanmak istiyorsanız bu işlevi geçersiz kılın. Sunucu uygulaması önerilen palet kullanmak için gerekli değildir.

Daha fazla bilgi için Bkz. Windows SDK'da [IOleObject::SetColorScheme.](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme)

## <a name="coleserveritemonsetdata"></a><a name="onsetdata"></a>COleServerItem::OnSetData

OLE öğesinin verilerini belirtilen verilerle değiştirmek için çerçeve tarafından çağrılır.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
Verilerin biçimini belirten bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaretçi.

*lpStgMedium*<br/>
Verilerin bulunduğu [BIR STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına işaretçi.

*bRelease*<br/>
İşlev çağrısını tamamladıktan sonra depolama ortamının sahipliğini kimde olduğunu gösterir. Arayan, depolama ortamı adına ayrılan kaynakların serbest bırakılmasından kimin sorumlu olduğuna karar verir. Arayan bunu *bRelease*ayarlayarak yapar. *bRelease* sıfır değilse, sunucu öğesi sahipliğini alır ve kullanımı tamamlandığında ortamı serbest bırakarak. *bRelease* 0 olduğunda, arayan sahipliğini korur ve sunucu öğesi depolama ortamını yalnızca arama süresi boyunca kullanabilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sunucu öğesi, verileri başarıyla elde edene kadar verilerin sahipliğini almaz. Diğer bir se, 0 döndürürse sahiplenmez. Veri kaynağı sahipliği alırsa, [ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) işlevini arayarak depolama ortamını serbest düşürür.

Varsayılan uygulama hiçbir şey yapmaz. OLE öğesinin verilerini belirtilen verilerle değiştirmek için bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz.

Daha fazla bilgi için Windows SDK'daki [STGMEDIUM,](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)ve [ReleaseStgMedium'a](/windows/win32/api/ole2/nf-ole2-releasestgmedium) bakın.

## <a name="coleserveritemonsetextent"></a><a name="onsetextent"></a>COleServerItem::OnSetExtent

OLE öğesine kapsayıcı belgesinde ne kadar alan olduğunu söylemek için çerçeve tarafından çağrılır.

```
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,
    const CSize& size);
```

### <a name="parameters"></a>Parametreler

*nDrawAspect*<br/>
Sınırları belirtilen OLE öğesinin yönünü belirtir. Bu parametre aşağıdaki değerlerden herhangi biri olabilir:

- DVASPECT_CONTENT Öğe, kapsayıcının içinde katıştırılmış bir nesne olarak görüntülenecek şekilde temsil edilir.

- DVASPECT_THUMBNAIL Öğesi, bir tarama aracında görüntülenebilecek şekilde "küçük resim" gösteriminde işlenir.

- DVASPECT_ICON Öğe bir simge ile temsil edilir.

- DVASPECT_DOCPRINT Öğe, Dosya menüsünden Yazdır komutu kullanılarak basılmış gibi temsil edilir.

*Boyutu*<br/>
OLE öğesinin yeni boyutunu belirten bir [CSize](../../atl-mfc-shared/reference/csize-class.md) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulaması Microsoft Hazırlık Sınıfı Kitaplığı ile yazılmışsa, bu işlev, ilgili `COleClientItem` nesnenin [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) üye işlevi çağrıldığında çağrılır. Varsayılan uygulama, *nDrawAspect* DVASPECT_CONTENT ise [m_sizeExtent](#m_sizeextent) üyeyi belirtilen boyuta ayarlar; aksi takdirde 0 döndürür. Öğenin boyutunu değiştirdiğinizde özel işleme gerçekleştirmek için bu işlevi geçersiz kılın.

## <a name="coleserveritemonshow"></a><a name="onshow"></a>COleServerItem::OnShow

Sunucu uygulamasına OLE öğesini yerinde görüntülemesini vermek için çerçeve tarafından çağrılır.

```
virtual void OnShow();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle kapsayıcı uygulamasının kullanıcısı bir öğe oluşturduğunda veya öğenin gösterilmesini gerektiren Edit gibi bir fiili işlediğinde çağrılır. Varsayılan uygulama yerinde etkinleştirme çalışır. Bu başarısız olursa, işlev `OnOpen` üye işlevi ayrı bir pencerede OLE öğesini görüntülemek için çağırır.

Bir OLE öğesi gösterildiğinde özel işleme gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

## <a name="coleserveritemonupdate"></a><a name="onupdate"></a>COleServerItem::OnUpdate

Bir öğe değiştirildiğinde çerçeve tarafından çağrılır.

```
virtual void OnUpdate(
    COleServerItem* pSender,
    LPARAM lHint,
    CObject* pHint,
    DVASPECT nDrawAspect);
```

### <a name="parameters"></a>Parametreler

*pSender*<br/>
Belgeyi değiştiren öğeyi işaretçi. NULL olabilir.

*Lhint*<br/>
Değişiklik hakkında bilgi içerir.

*pHint*<br/>
Değişiklik le ilgili bilgileri depolayan bir nesneye işaretçi.

*nDrawAspect*<br/>
DVASPECT numaralandırmasından bir değer. Bu parametre aşağıdaki değerlerden herhangi birine sahip olabilir:

- DVASPECT_CONTENT Öğe, kapsayıcının içinde katıştırılmış bir nesne olarak görüntülenecek şekilde temsil edilir.

- DVASPECT_THUMBNAIL Öğesi, bir tarama aracında görüntülenebilecek şekilde "küçük resim" gösteriminde işlenir.

- DVASPECT_ICON Öğe bir simge ile temsil edilir.

- DVASPECT_DOCPRINT Öğe, Dosya menüsünden Yazdır komutu kullanılarak basılmış gibi temsil edilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, ipucu veya gönderenden bağımsız olarak [NotifyChanged'u](#notifychanged)çağırır.

## <a name="coleserveritemonupdateitems"></a><a name="onupdateitems"></a>COleServerItem::OnUpdateItems

Sunucu belgesindeki tüm öğeleri güncelleştirmek için çerçeve tarafından çağrılır.

```
virtual void OnUpdateItems();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, belgedeki `COleClientItem` tüm nesneler için [UpdateLink'i](../../mfc/reference/coleclientitem-class.md#updatelink) çağırır.

## <a name="coleserveritemsetitemname"></a><a name="setitemname"></a>COleServerItem::SetItemName

Adını ayarlamak için bağlantılı bir öğe oluştururken bu işlevi çağırın.

```
void SetItemName(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parametreler

*lpszItemName*<br/>
Öğenin yeni adına işaretçi.

### <a name="remarks"></a>Açıklamalar

Ad belge içinde benzersiz olmalıdır. Bağlı bir öğeyi düzenlemek için bir sunucu uygulaması çağrıldığında, uygulama öğeyi bulmak için bu adı kullanır. Katıştırılmış öğeler için bu işlevi aramanız gerekmez.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CdocItem Sınıfı](../../mfc/reference/cdocitem-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[COleServerDoc Sınıfı](../../mfc/reference/coleserverdoc-class.md)<br/>
[COleTemplateServer Sınıfı](../../mfc/reference/coletemplateserver-class.md)
