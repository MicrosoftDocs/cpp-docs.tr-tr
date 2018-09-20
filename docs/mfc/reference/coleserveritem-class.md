---
title: Coleserverıtem sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 466dfbc2407df7985a925accf4bcee0eb815f3e0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442532"
---
# <a name="coleserveritem-class"></a>Coleserverıtem sınıfı

OLE öğelerine ilişkin sunucu arabirimini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class COleServerItem : public CDocItem
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleServerItem::COleServerItem](#coleserveritem)|Oluşturur bir `COleServerItem` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|Sunu ve dönüştürme biçimlerde yerleştirir bir `COleDataSource` nesne.|
|[COleServerItem::CopyToClipboard](#copytoclipboard)|Öğe panoya kopyalar.|
|[COleServerItem::DoDragDrop](#dodragdrop)|Bir Sürükle ve bırak işlemi gerçekleştirir.|
|[COleServerItem::GetClipboardData](#getclipboarddata)|Veri aktarımı (Sürükle ve bırak veya Pano) kullanmak için veri kaynağını alır.|
|[COleServerItem::GetDocument](#getdocument)|Öğeyi içeren sunucu belgeyi döndürür.|
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|CF_EMBEDSOURCE verileri için bir OLE öğesini alır.|
|[COleServerItem::GetItemName](#getitemname)|Öğenin adını döndürür. Bağlantılı öğeler kullanılır.|
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|CF_LINKSOURCE verileri için bir OLE öğesini alır.|
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|CF_OBJECTDESCRIPTOR verileri için bir OLE öğesini alır.|
|[COleServerItem::IsConnected](#isconnected)|Öğe için etkin bir kapsayıcı ekli olup olmadığını gösterir.|
|[COleServerItem::IsLinkedItem](#islinkeditem)|Öğe bağlantılı bir OLE öğesini temsil edip etmediğini belirtir.|
|[COleServerItem::NotifyChanged](#notifychanged)|Tüm kapsayıcıları otomatik bağlantı güncelleştirme ile güncelleştirir.|
|[COleServerItem::OnDoVerb](#ondoverb)|Bir fiili yürütmek için çağrılır.|
|[COleServerItem::OnDraw](#ondraw)|Kapsayıcı öğe çizmek için gerektirdiğinde çağrılır; Gerekli uygulama.|
|[COleServerItem::OnDrawEx](#ondrawex)|Özel öğeleri çiziliyorken çağırılır.|
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|Panoya kopyalandı veri almak için framework tarafından çağırılır.|
|[COleServerItem::OnGetExtent](#ongetextent)|OLE öğesinin boyutunu almak için framework tarafından çağırılır.|
|[COleServerItem::OnInitFromData](#oninitfromdata)|İçeriği belirttiğiniz veri aktarım nesnesini kullanarak bir OLE öğesini başlatmak için framework tarafından çağırılır.|
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|Herhangi bir bağlantılı öğenin güncelleştirilmesi gerekip gerekmediğini belirlemek için çağrılır.|
|[COleServerItem::OnRenderData](#onrenderdata)|Gecikmeli işleme bir parçası olarak verileri alır.|
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|Verileri alır bir `CFile` Gecikmeli işleme bir parçası olarak nesnesi.|
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|Gecikmeli işleme bir parçası olarak bir HGLOBAL içine verileri alır.|
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|Öğenin renk düzenini ayarlamak için çağrılır.|
|[COleServerItem::OnSetData](#onsetdata)|Öğenin veri kümesi için çağrılır.|
|[COleServerItem::OnSetExtent](#onsetextent)|OLE öğesinin boyutunu belirlemek için framework tarafından çağırılır.|
|[COleServerItem::OnUpdate](#onupdate)|Adlı, zaman içinde belge öğesi kısmı ait değiştirilir.|
|[COleServerItem::OnUpdateItems](#onupdateitems)|Sunucu belgedeki tüm öğeleri sunu önbelleği güncelleştirmek için çağrıldı.|
|[COleServerItem::SetItemName](#setitemname)|Öğesi adını ayarlar. Bağlantılı öğeler kullanılır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleServerItem::GetDataSource](#getdatasource)|Dönüştürme biçimleri depolamak için kullanılan nesneyi alır.|
|[COleServerItem::OnHide](#onhide)|OLE öğesini gizlemek için framework tarafından çağırılır.|
|[COleServerItem::OnOpen](#onopen)|OLE öğesi kendi üst düzey penceresinde göstermek için framework tarafından çağırılır.|
|[COleServerItem::OnShow](#onshow)|Kapsayıcı öğe gösterilecek gerektirdiğinde çağrılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleServerItem::m_sizeExtent](#m_sizeextent)|Sunucuya OLE öğesini ne kadarının görünür olduğunu bildirir.|

## <a name="remarks"></a>Açıklamalar

Bağlantılı bir öğe bazılarını veya tümünü bir sunucu belgeyi temsil edebilir. Gömülü bir öğe her zaman bir sunucunun tamamı belgeyi temsil eder.

`COleServerItem` Sınıfı tanımlar OLE Sistem dinamik bağlantı kitaplıkları (DLL'ler) olarak adlandırılan birden fazla geçersiz kılınabilir üye işlevleri genellikle kapsayıcı uygulaması gelen isteklere yanıt. Bu üye işlevleri görüntülemeden, kendi fiilleri yürütme ya da kendi verilerini çeşitli biçimlerde alma gibi çeşitli yollarla öğesinde dolaylı olarak işlemek kapsayıcı uygulamasını sağlar.

Kullanılacak `COleServerItem`, bir sınıf türetmeniz ve uygulama [OnDraw](#ondraw) ve [serileştirme](../../mfc/reference/cobject-class.md#serialize) üye işlevleri. `OnDraw` İşlevi bir bileşik belge kapsayıcı Uygulaması açıldığında görüntülenen izin veren bir öğenin meta dosyası temsili sağlar. `Serialize` İşlevi `CObject` yerel gösterimine izin vererek sunucu ve kapsayıcı uygulamalar arasında aktarılması gömülü bir öğe, bir öğenin sağlar. [OnGetExtent](#ongetextent) öğesi boyutu kapsayıcıya etkinleştirme kapsayıcı öğenin doğal bir boyut sağlar.

Sunucuları ve ilgili konular hakkında daha fazla bilgi için bkz [sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md) ve "Oluşturma bir kapsayıcı/sunucu uygulaması" makalesinde [kapsayıcılar: Gelişmiş Özellikler](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[Cdocıtem](../../mfc/reference/cdocitem-class.md)

`COleServerItem`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="addotherclipboarddata"></a>  COleServerItem::AddOtherClipboardData

OLE öğesini sunu ve dönüştürme biçimleri belirtilen yerleştirmek için bu işlevi çağırın `COleDataSource` nesne.

```
void AddOtherClipboardData(COleDataSource* pDataSource);
```

### <a name="parameters"></a>Parametreler

*pDataSource*<br/>
İşaretçi `COleDataSource` nesne hangi verilerin yerleştirilmesi gerektiğini de.

### <a name="remarks"></a>Açıklamalar

Uyguladınız mı [OnDraw](#ondraw) öğe için sunu biçimi (meta resim) sağlamak için üye işlevi. Diğer dönüştürme biçimleri desteklemek için bunları kaydetme kullanarak [COleDataSource](../../mfc/reference/coledatasource-class.md) tarafından döndürülen nesne [GetDataSource](#getdatasource) ve geçersiz kılma [OnRenderData](#onrenderdata) üye işlevi desteklemek istediğiniz biçimlerde veriler sağlar.

##  <a name="coleserveritem"></a>  COleServerItem::COleServerItem

Oluşturur bir `COleServerItem` nesne ve belge öğeleri sunucu belgenin koleksiyonuna ekler.

```
COleServerItem(
    COleServerDoc* pServerDoc,
    BOOL bAutoDelete);
```

### <a name="parameters"></a>Parametreler

*pServerDoc*<br/>
Yeni öğe içeren belge işaretçisi.

*bAutoDelete*<br/>
Bağlantı yayımlandığında nesnesi silinebilir olup olmadığını belirten bayrak. Bunu FALSE olarak ayarlayın `COleServerItem` nesne silmeniz gerekir, belgenizin veri bütünleyici bir özelliğidir. Bu nesne gerekirse TRUE olarak framework tarafından silinebilir belgenizin veri aralığında tanımlamak için kullanılan ikincil bir yapısı olan.

##  <a name="copytoclipboard"></a>  COleServerItem::CopyToClipboard

OLE öğesini panoya kopyalamak için bu işlevi çağırın.

```
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```

### <a name="parameters"></a>Parametreler

*bIncludeLink*<br/>
Gerekirse TRUE bunu veri bağlantısı panoya kopyalanmalıdır. Sunucunuz için FALSE ise bunu uygulama bağlantılarını desteklemiyor.

### <a name="remarks"></a>Açıklamalar

İşlev kullanır [gerçekleşebilir](#ongetclipboarddata) üye işlevi bir [COleDataSource](../../mfc/reference/coledatasource-class.md) OLE öğesinin verileri desteklenen biçimde içeren nesne. Ardından işlev yerleştirir `COleDataSource` kullanarak Pano nesnesinde [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) işlevi. `COleDataSource` Nesne içeren öğenin yerel veri ve gösterimine desteklemek için seçtiğiniz herhangi bir dönüştürme biçimlerde verilerin yanı sıra CF_METAFILEPICT biçimi. Uyguladınız mı [serileştirme](../../mfc/reference/cobject-class.md#serialize) ve [OnDraw](#ondraw) çalışmak bu üye işlevi.

##  <a name="dodragdrop"></a>  COleServerItem::DoDragDrop

Çağrı `DoDragDrop` bir Sürükle ve bırak işlemi gerçekleştirmek için üye işlevi.

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
Öğenin dikdörtgen ekrandaki piksel cinsinden istemci alanına göre.

*ptOffset*<br/>
Uzaklığı *lpItemRect* sürükleme zamanında olduğu fare konumu.

*bIncludeLink*<br/>
Gerekirse TRUE bunu veri bağlantısı panoya kopyalanmalıdır. Uygulamanızın bağlantılar desteklemiyorsa FALSE olarak ayarlayın.

*dwEffects*<br/>
Sürükleme kaynağı sürükleme işlemi (Kopyala, taşıma ve bağlantı birleşimi) sağlayacak etkileri belirler.

*lpRectStartDrag*<br/>
Sürükleme gerçekten başladığı tanımlar dikdörtgen işaretçisi. Daha fazla bilgi için aşağıdaki Açıklamalar bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

DROPEFFECT sabit bir değer. DROPEFFECT_MOVE ise, özgün verilerin kaldırılması gerekir.

### <a name="remarks"></a>Açıklamalar

Sürükle ve bırak işlemi hemen başlamaz. Fare imlecini tarafından belirtilen dikdörtgen olana kadar bekler *lpRectStartDrag* veya kadar belirtilen sayıda milisaniye geçmiştir. Varsa *lpRectStartDrag* NULL ise varsayılan dikdörtgen bir piksel fare imleci hareket ettiğinde Sürükle başlatır. böylece kullanılır.

Gecikme süresi, bir kayıt defteri anahtarı ayarı tarafından belirtilir. Gecikme süresini çağırarak değiştirebilirsiniz [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) veya [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Gecikme süresini belirtmezseniz varsayılan değeri 200 milisaniye olarak kullanılır. Sürükleme gecikme süresi gibi depolanır:

- Windows NT Sürükle gecikme süresi içinde HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay depolanır.

- Windows 3.x Sürükle gecikme süresi WIN depolanır. INI dosyası, [Windows} bölümünde.

- Windows 95/98 Sürükle gecikme süresi, WIN önbelleğe alınmış bir sürümünde depolanır. INI.

Gecikme bilgilerini sürükleyin hakkında daha fazla bilgi için her iki kayıt defterinde depolanır veya. INI dosyası bkz [WriteProfileString](/windows/desktop/api/winbase/nf-winbase-writeprofilestringa) Windows SDK.

##  <a name="getclipboarddata"></a>  COleServerItem::GetClipboardData

Belirtilen doldurmak için bu işlevi çağırın [COleDataSource](../../mfc/reference/coledatasource-class.md) çağrılırsa, panoya kopyalandı tüm verileri içeren nesne [CopyToClipboard](#copytoclipboard) (aynı verilere Ayrıca, aktarılması, adlı [DoDragDrop](#dodragdrop)).

```
void GetClipboardData(
    COleDataSource* pDataSource,
    BOOL bIncludeLink = FALSE,
    LPPOINT lpOffset = NULL,
    LPSIZE lpSize = NULL);
```

### <a name="parameters"></a>Parametreler

*pDataSource*<br/>
İşaretçi `COleDataSource` nesnesini OLE öğesinin verileri desteklenen tüm biçimlerdeki alır.

*bIncludeLink*<br/>
Veri bağlantısı panoya kopyalanması gereken TRUE. Sunucu uygulamasının bağlantıları desteklemiyorsa FALSE.

*lpOffset*<br/>
Fare imleci nesnenin kaynaktan piksel cinsinden uzaklığı.

*lpSize*<br/>
Nesnesinin piksel cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Bu işlev çağrıları [GetEmbedSourceData](#getembedsourcedata) üye işlevini çağırır ve OLE öğesi için yerel veri almak için [AddOtherClipboardData](#addotherclipboarddata) herhangi ve bir sunu biçimi almak için üye işlevi dönüştürme biçimleri desteklenir. Varsa *bIncludeLink* TRUE, işlev ayrıca çağrıdır [GetLinkSourceData](#getlinksourcedata) öğe için bağlantı verileri almak için.

Biçimleri koymak istiyorsanız, bu işlevi geçersiz bir `COleDataSource` nesne önce veya sonra tarafından sağlanan bu biçimleri `CopyToClipboard`.

##  <a name="getdatasource"></a>  COleServerItem::GetDataSource

Almak için bu işlevi çağırın [COleDataSource](../../mfc/reference/coledatasource-class.md) sunucu uygulamasının desteklediği dönüştürme biçimlerini depolamak için kullanılan nesne.

```
COleDataSource* GetDataSource();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `COleDataSource` dönüştürme biçimleri depolamak için kullanılan nesne.

### <a name="remarks"></a>Açıklamalar

Sunucu uygulamasının veri aktarımı sırasında operations çeşitli biçimlerde verileri sunmak istiyorsanız, bu biçimleriyle kaydetme `COleDataSource` bu işlev tarafından döndürülen nesne. Örneğin, Pano veya sürükle ve bırak işlemleri için bir OLE öğesini CF_TEXT gösterimini sağlamak istiyorsanız, biçimiyle kaydetmek `COleDataSource` nesne bu işlevi döndürür ve sonra geçersiz kılma `OnRenderXxxData` üye işlevi veriler sağlar.

##  <a name="getdocument"></a>  COleServerItem::GetDocument

Öğeyi içeren belge için bir işaretçi almak için bu işlevi çağırın.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeyi içeren belge için bir işaretçi; Bir belge bir parçası değilse null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Bu bağımsız değişken olarak geçirilen sunucu belgeye erişimi verir `COleServerItem` Oluşturucusu.

##  <a name="getembedsourcedata"></a>  COleServerItem::GetEmbedSourceData

CF_EMBEDSOURCE verileri için bir OLE öğesini almak için bu işlevi çağırın.

```
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parametreler

*lpStgMedium*<br/>
İşaretçi [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) OLE öğesini CF_EMBEDSOURCE verileri alacak yapısı.

### <a name="remarks"></a>Açıklamalar

Bu biçim, öğenin yerel veri içerir. Uyguladınız mı `Serialize` düzgün çalışması bu işlevin üye işlevi.

Sonuç ardından bir veri kaynağına kullanılarak eklenebilir [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Bu işlev tarafından otomatik olarak çağrılır [COleServerItem::OnGetClipboardData](#ongetclipboarddata).

Daha fazla bilgi için [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Windows SDK.

##  <a name="getitemname"></a>  COleServerItem::GetItemName

Öğenin adını almak için bu işlevi çağırın.

```
const CString& GetItemName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe adı.

### <a name="remarks"></a>Açıklamalar

Genellikle yalnızca bağlantılı öğeler için bu işlevi çağırın.

##  <a name="getlinksourcedata"></a>  COleServerItem::GetLinkSourceData

CF_LINKSOURCE verileri için bir OLE öğesini almak için bu işlevi çağırın.

```
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parametreler

*lpStgMedium*<br/>
İşaretçi [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) OLE öğesini CF_LINKSOURCE verileri alacak yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu biçim türünü OLE öğesini ve OLE öğesini içeren belge bulmak için gereken bilgileri açıklayan CLSID içerir.

Sonuç ardından bir veri kaynağına eklenebilir [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Bu işlev tarafından otomatik olarak çağrılır [gerçekleşebilir](#ongetclipboarddata).

Daha fazla bilgi için [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Windows SDK.

##  <a name="getobjectdescriptordata"></a>  COleServerItem::GetObjectDescriptorData

CF_OBJECTDESCRIPTOR verileri için bir OLE öğesini almak için bu işlevi çağırın.

```
void GetObjectDescriptorData(
    LPPOINT lpOffset,
    LPSIZE lpSize,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parametreler

*lpOffset*<br/>
OLE öğesinin sol üst köşesinden fare tıklatın uzaklığı. NULL olabilir.

*lpSize*<br/>
OLE öğesinin boyutu. NULL olabilir.

*lpStgMedium*<br/>
İşaretçi [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) OLE öğesini CF_OBJECTDESCRIPTOR verileri alacak yapısı.

### <a name="remarks"></a>Açıklamalar

Bilgiler kopyalanır `STGMEDIUM` yapısı tarafından işaret edilen *lpStgMedium*. Bu biçim Paste Special iletişim kutusu için gereken bilgileri içerir.

Daha fazla bilgi için [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Windows SDK.

##  <a name="isconnected"></a>  COleServerItem::IsConnected

OLE öğesini bağlı olup olmadığını görmek için bu işlevi çağırın.

```
BOOL IsConnected() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe bağlı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

OLE öğesini bir veya daha fazla kapsayıcı öğe başvurusu yapılıyorsa bağlı olarak kabul edilir. Bir öğe varsa, başvuru sayısı 0'dan büyük ya da gömülü bir öğe ise bağlıdır.

##  <a name="islinkeditem"></a>  COleServerItem::IsLinkedItem

OLE öğesini bağlantılı bir öğe olup olmadığını görmek için bu işlevi çağırın.

```
BOOL IsLinkedItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe bağlantılı öğe ise sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir öğe, öğe geçerliyse ve belgenin katıştırılmış öğeler listesinde döndürülmez bağlıdır. Bağlantılı bir öğesi olabilir veya bir kapsayıcıya bağlı olmayabilir.

Hem bağlantılı hem de katıştırılmış öğeler için aynı sınıf kullanmak yaygın bir uygulamadır. `IsLinkedItem` birden çok kez kod yaygın olsa katıştırılmış öğeler, farklı davranır bağlantılı öğeler yapmanızı sağlar.

##  <a name="m_sizeextent"></a>  COleServerItem::m_sizeExtent

Bu üye, sunucu, nesnenin ne kadar kapsayıcı belgede görünür olduğunu bildirir.

```
CSize m_sizeExtent;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulaması [OnSetExtent](#onsetextent) bu üye ayarlar.

##  <a name="notifychanged"></a>  COleServerItem::NotifyChanged

Bağlantılı öğe değiştirildikten sonra bu işlevi çağırın.

```
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>Parametreler

*nDrawAspect*<br/>
OLE öğesinin hangi yönüyle gösteren DVASPECT sabit değerinden değişti. Bu parametre aşağıdaki değerlerden herhangi birini alabilir:

- DVASPECT_ICON öğesi, bir nesnenin kapsayıcısı içindeki olarak görüntülenebilir şekilde temsil edilir.

- Tarama Aracı içinde görüntülenebilen böylece desteklemek istiyorsanız öğesi "küçük" gösteriminde işlenir.

- DVASPECT_ICON öğesi bir simge ile temsil edilir.

- Dosya menüsünden Yazdır komutunu kullanarak yazdırılmış gibi DVASPECT_ICON öğesi gösterilir.

### <a name="remarks"></a>Açıklamalar

Bir kapsayıcı öğesi belgenin otomatik bir bağlantıyla bağlıysa, öğe değişiklikleri yansıtacak şekilde güncelleştirilir. Microsoft Foundation Class Kitaplığı kullanılarak yazılmış kapsayıcı uygulamalarında [COleClientItem::OnChange](../../mfc/reference/coleclientitem-class.md#onchange) yanıt olarak adlandırılır.

##  <a name="ondoverb"></a>  COleServerItem::OnDoVerb

Belirtilen fiili yürütmek için framework tarafından çağırılır.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Parametreler

*iVerb*<br/>
Yürütmek için fiili belirtir. Bu, aşağıdakilerden herhangi biri olabilir:

|Değer|Açıklama|Sembol|
|-----------|-------------|------------|
|0|Birincil fiil|OLEIVERB_PRIMARY|
|1.|İkincil fiili|(Hiçbiri)|
|- 1|Görüntü öğesini düzenlemek için|OLEIVERB_SHOW|
|- 2|Ayrı bir pencerede öğeyi Düzenle|OLEIVERB_OPEN|
|- 3|Öğeyi Gizle|OLEIVERB_HIDE|

-1 değeri, genellikle başka bir eylem için bir diğer ad olduğu. Açık düzenleme desteklenmiyorsa, -2 -1 ile aynı etkiye sahiptir. Ek değerleri için bkz: [Rpc_e_serverfault](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulamasını Microsoft Foundation Class Kitaplığı ile yazılmışsa, bu işlev aldığında çağrılan [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate) üye işlevi, karşılık gelen `COleClientItem` nesne çağrılır. Varsayılan Uygulama çağrıları [OnShow](#onshow) birincil fiil veya OLEIVERB_SHOW belirtilmezse, üye işlevi [açıldığında](#onopen) ikincil fiil veya OLEIVERB_OPEN belirttiyseniz ve [OnHide ](#onhide) OLEIVERB_HIDE belirtilirse. Varsayılan Uygulama çağrıları `OnShow` varsa *iVerb* yukarıda listelenen fiillerden biri değil.

Bu işlev, birincil fiil öğesi göstermez geçersiz kılın. Örneğin, bir ses kaydı öğedir ve alt birincil fiil Play ise, öğeyi yürütmek için sunucu uygulamasının görüntüleme girmesi gerekmez.

Daha fazla bilgi için [Rpc_e_serverfault](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK.

##  <a name="ondraw"></a>  COleServerItem::OnDraw

OLE öğesini bir meta dosyasında işlemek için framework tarafından çağırılır.

```
virtual BOOL OnDraw(
    CDC* pDC,
    CSize& rSize) = 0;
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Bir işaretçi [CDC](../../mfc/reference/cdc-class.md) öğeyi çizmek nesne. Öznitelik işlevleri çağırabilmek yapmak, bu nedenle meta cihaza özgü yapacağınız olsa da görüntüleme bağlamı öznitelik görünen bağlamına otomatik olarak bağlanır.

*rSize*<br/>
Meta dosyası çizmek üzere HIMETRIC birimleri boyutu.

### <a name="return-value"></a>Dönüş Değeri

Öğesi başarıyla çizilmiş olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

OLE öğesinin meta dosyası temsili, kapsayıcı uygulamada öğeyi görüntülemek için kullanılır. Kapsayıcı uygulamasını Microsoft Foundation Class Kitaplığı ile yazılmışsa, meta dosyası tarafından kullanılan [çizmek](../../mfc/reference/coleclientitem-class.md#draw) üye işlevi, karşılık gelen [Coleclientıtem](../../mfc/reference/coleclientitem-class.md) nesne. Varsayılan uygulaması yok. Cihaz bağlamına belirtilen öğeyi çizmek için bu işlevi geçersiz kılmanız gerekir.

##  <a name="ondrawex"></a>  COleServerItem::OnDrawEx

Tüm çizim için framework tarafından çağırılır.

```
virtual BOOL OnDrawEx(
    CDC* pDC,
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Bir işaretçi [CDC](../../mfc/reference/cdc-class.md) öğeyi çizmek nesne. Öznitelik işlevleri çağırabilmek yapmak, bu nedenle meta cihaza özgü yapacağınız rağmen DC DC özniteliğine otomatik olarak bağlanır.

*nDrawAspect*<br/>
DVASPECT sabit bir değer. Bu parametre aşağıdaki değerlerden herhangi birini alabilir:

- DVASPECT_ICON öğesi, bir nesnenin kapsayıcısı içindeki olarak görüntülenebilir şekilde temsil edilir.

- Tarama Aracı içinde görüntülenebilen böylece desteklemek istiyorsanız öğesi "küçük" gösteriminde işlenir.

- DVASPECT_ICON öğesi bir simge ile temsil edilir.

- Dosya menüsünden Yazdır komutunu kullanarak yazdırılmış gibi DVASPECT_ICON öğesi gösterilir.

*rSize*<br/>
HIMETRIC birimleri öğenin boyutu.

### <a name="return-value"></a>Dönüş Değeri

Öğesi başarıyla çizilmiş olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan Uygulama çağrıları `OnDraw` DVASPECT DVASPECT_ICON için; eşit olduğunda yoksa işlem başarısız olur.

DVASPECT_ICON, DVASPECT_ICON veya desteklemek istiyorsanız gibi farklı yönleri için sunu veri sağlamak için bu işlevi geçersiz kılar.

##  <a name="ongetclipboarddata"></a>  COleServerItem::OnGetClipboardData

Almak için framework tarafından çağırılır bir `COleDataSource` panoya yapılan bir çağrıyla konulabilir tüm verileri içeren bir nesne [CopyToClipboard](#copytoclipboard) üye işlevi.

```
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,
    LPPOINT lpOffset,
    LPSIZE lpSize);
```

### <a name="parameters"></a>Parametreler

*bIncludeLink*<br/>
Gerekirse TRUE bunu veri bağlantısı panoya kopyalanmalıdır. Sunucunuz için FALSE ise bunu uygulama bağlantılarını desteklemiyor.

*lpOffset*<br/>
Fare imlecini kaynaktan nesnesinin piksel cinsinden uzaklığı.

*lpSize*<br/>
Nesnesinin piksel cinsinden boyutu.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [COleDataSource](../../mfc/reference/coledatasource-class.md) Pano verilerini içeren nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan uygulamasını çağırır [GetClipboardData](#getclipboarddata).

##  <a name="ongetextent"></a>  COleServerItem::OnGetExtent

HIMETRIC birimleri, OLE öğesinin boyutunu almak için framework tarafından çağırılır.

```
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Parametreler

*nDrawAspect*<br/>
Alınacak olan sınırları olan OLE öğesini yönünü belirtir. Bu parametre aşağıdaki değerlerden herhangi birini alabilir:

- DVASPECT_ICON öğesi, bir nesnenin kapsayıcısı içindeki olarak görüntülenebilir şekilde temsil edilir.

- Tarama Aracı içinde görüntülenebilen böylece desteklemek istiyorsanız öğesi "küçük" gösteriminde işlenir.

- DVASPECT_ICON öğesi bir simge ile temsil edilir.

- Dosya menüsünden Yazdır komutunu kullanarak yazdırılmış gibi DVASPECT_ICON öğesi gösterilir.

*rSize*<br/>
Başvuru bir `CSize` nesnesini OLE öğesinin boyutunu alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulamasını Microsoft Foundation Class Kitaplığı ile yazılmışsa, bu işlev aldığında çağrılan [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) üye işlevi, karşılık gelen `COleClientItem` nesne çağrılır. Varsayılan uygulama, hiçbir şey yapmaz. Bunu kendiniz uygulamalıdır. OLE öğesinin boyutu için bir istek işlenirken özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.

##  <a name="onhide"></a>  COleServerItem::OnHide

OLE öğesini gizlemek için framework tarafından çağırılır.

```
virtual void OnHide();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan çağrıları `COleServerDoc::OnShowDocument( FALSE )`. İşlev OLE öğesini gizli kapsayıcı da bildirir. OLE öğesini gizlerken özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.

##  <a name="oninitfromdata"></a>  COleServerItem::OnInitFromData

İçeriğini kullanarak bir OLE öğesini başlatmak için framework tarafından çağırılır *pDataObject*.

```
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,
    BOOL bCreation);
```

### <a name="parameters"></a>Parametreler

*pDataObject*<br/>
OLE öğesini başlatmak için farklı biçimlerde veri içeren bir OLE veri nesne işaretçisi.

*bCreation*<br/>
Yeni bir kapsayıcı uygulama tarafından oluşturulan OLE öğesini başlatmak için çağrılan işlev TRUE. Varolan bir OLE öğesinin içeriğini değiştirin için çağrılan işlev FALSE.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsa *bCreation* doğru ise, bir kapsayıcı yeni geçerli seçime dayanan Nesne Ekle uyguluyorsa, bu işlev çağrılır. Seçilen verileri yeni OLE öğesi oluşturulurken kullanılır. Örneğin, ne zaman bir elektronik tablo programında bir hücre aralığı seçerek ve ardından bir grafik oluşturmak için Yeni Nesne Ekle kullanarak seçili aralığındaki değerleri temel. Varsayılan uygulama, hiçbir şey yapmaz. Bu işlev tarafından sunulanların kabul edilebilir bir biçimde arasından geçersiz kılma *pDataObject* ve sağlanan verilere dayalı OLE öğesini başlatmak. Bu gelişmiş bir, geçersiz kılınabilir.

Daha fazla bilgi için [IOleObject::InitFromData](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-initfromdata) Windows SDK.

##  <a name="onopen"></a>  COleServerItem::OnOpen

Sunucu uygulaması ayrı bir örneğini yerine yerinde OLE öğesini göstermek için framework tarafından çağırılır.

```
virtual void OnOpen();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama OLE öğesini içeren belge görüntüleme ilk çerçeve penceresi etkinleştirir; Uygulama bir mini sunucu ise, varsayılan uygulama ana pencereyi gösterir. İşlev OLE öğesini açılmış kapsayıcı da bildirir.

OLE öğesini açılırken özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar. Bu, özellikle açıldığında seçimi bağlantısını ayarlamak istediğiniz yerde bağlantılı öğeler ile yaygındır.

Daha fazla bilgi için [IOleClientSite::OnShowWindow](/windows/desktop/api/oleidl/nf-oleidl-ioleclientsite-onshowwindow) Windows SDK.

##  <a name="onqueryupdateitems"></a>  COleServerItem::OnQueryUpdateItems

Herhangi bir bağlantılı öğenin geçerli sunucu belgedeki güncel olup olmadığını belirlemek için framework tarafından çağırılır.

```
virtual BOOL OnQueryUpdateItems();
```

### <a name="return-value"></a>Dönüş Değeri

Belge güncelleştirmeleri gerektiren öğeler varsa, sıfır olmayan; tüm öğeleri güncel olması durumunda 0.

### <a name="remarks"></a>Açıklamalar

Bir öğe, kendi kaynak belge değiştirildi, ancak bağlı öğe belge değişiklikleri yansıtacak şekilde güncelleştirilmemiş güncel değil.

##  <a name="onrenderdata"></a>  COleServerItem::OnRenderData

Belirtilen biçimden veri almak için framework tarafından çağırılır.

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
İşaret [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) içinde bilgi istenen biçimi belirten yapısı.

*lpStgMedium*<br/>
İşaret eden bir [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) veri olduğu döndürülecek yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim biridir daha önce bulundukları `COleDataSource` kullanarak nesne [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) veya [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) Gecikmeli işleme için üye işlevi. Bu işlev varsayılan uygulamasını çağırır [OnRenderFileData](#onrenderfiledata) veya [OnRenderGlobalData](#onrenderglobaldata)sırasıyla sağlanan depolama ortamına bir dosya veya bellek ise. Bu biçimler hiçbiri sağlanmazsa, varsayılan uygulama, 0 döndürür ve hiçbir şey yapmaz.

Varsa *lpStgMedium*-> *ortam türü* TYMED_NULL, olan STGMEDIUM ayrılmış ve tarafından belirtilen doldurulmuş *lpFormatEtc -> ortam türü*. Aksi durumda TYMED_NULL, STGMEDIUM yerde verilerle doldurulması gerekir.

Bu gelişmiş bir, geçersiz kılınabilir. Orta ve istenen biçimi verilerinizdeki sağlamak için bu işlevi geçersiz kılar. Verilerinizi bağlı olarak, bunun yerine bu işlevin diğer sürümlerden biri geçersiz kılmak isteyebilirsiniz. Verilerinizi, küçük ve sabit boyutu ise, geçersiz kılma `OnRenderGlobalData`. Verilerinizi bir dosyaya veya bir değişken boyutu, geçersiz kılma `OnRenderFileData`.

Daha fazla bilgi için [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata), [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium), [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc), ve [ortam türü](/windows/desktop/api/objidl/ne-objidl-tagtymed) Windows SDK.

##  <a name="onrenderfiledata"></a>  COleServerItem::OnRenderFileData

Depolama ortamına bir dosya olduğunda belirtilen biçimden veri almak için framework tarafından çağırılır.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
İşaret [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) içinde bilgi istenen biçimi belirten yapısı.

*pFile*<br/>
İşaret eden bir `CFile` veri olduğu işlenecek nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim biridir daha önce bulundukları `COleDataSource` kullanarak nesne [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Gecikmeli işleme için üye işlevi. Bu işlev varsayılan uygulaması yalnızca false değerini döndürür.

Bu gelişmiş bir, geçersiz kılınabilir. Orta ve istenen biçimi verilerinizdeki sağlamak için bu işlevi geçersiz kılar. Verilerinizi bağlı olarak, bunun yerine, bu işlevin diğer sürümlerden biri geçersiz kılmak isteyebilirsiniz. Birden çok depolama ortamlarının işlemek isterseniz, geçersiz kılma [OnRenderData](#onrenderdata). Verilerinizi bir dosyaya veya bir değişken boyutu, geçersiz kılma [OnRenderFileData](#onrenderfiledata).

Daha fazla bilgi için [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) ve [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK.

##  <a name="onrenderglobaldata"></a>  COleServerItem::OnRenderGlobalData

Belirtilen depolama ortamına genel bellek olduğunda belirtilen biçimden veri almak için framework tarafından çağırılır.

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
İşaret [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) içinde bilgi istenen biçimi belirten yapısı.

*phGlobal*<br/>
Genel bellek verileri döndürülecek olduğu için bir tanıtıcı işaret eder. Ayrılan bellek yok, bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim biridir daha önce bulundukları `COleDataSource` kullanarak nesne [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Gecikmeli işleme için üye işlevi. Bu işlev varsayılan uygulaması yalnızca false değerini döndürür.

Varsa *phGlobal* yeni HGLOBAL ayrılan verilecek ve döndürülen sonra NULL ise *phGlobal*. Aksi takdirde, tarafından belirtilen HGLOBAL *phGlobal* verilerle doldurulması gerekir. Geçerli bellek blok boyutu içinde HGLOBAL yerleştirilen veri miktarı aşmamalıdır. Ayrıca, daha büyük bir boyuta blok ayrılamaz.

Bu gelişmiş bir, geçersiz kılınabilir. Orta ve istenen biçimi verilerinizdeki sağlamak için bu işlevi geçersiz kılar. Verilerinizi bağlı olarak, bunun yerine bu işlevin diğer sürümlerden biri geçersiz kılmak isteyebilirsiniz. Birden çok depolama ortamlarının işlemek isterseniz, geçersiz kılma [OnRenderData](#onrenderdata). Verilerinizi bir dosyaya veya bir değişken boyutu, geçersiz kılma [OnRenderFileData](#onrenderfiledata).

Daha fazla bilgi için [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) ve [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK.

##  <a name="onsetcolorscheme"></a>  COleServerItem::OnSetColorScheme

OLE öğesini düzenlerken kullanılacak renk paletini belirlemek için framework tarafından çağırılır.

```
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```

### <a name="parameters"></a>Parametreler

*lpLogPalette*<br/>
Bir Windows işaretçisine [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Renk paletini kullanılan olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulaması, Microsoft Foundation Class Kitaplığı kullanılarak yazılmış olduğundan, bu işlev aldığında çağrılan [IOleObject::SetColorScheme](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) karşılık gelen işlevi `COleClientItem` nesne çağrılır. Varsayılan uygulama false değerini döndürür. Önerilen paleti kullanmak istiyorsanız, bu işlev geçersiz kılar. Sunucu uygulaması, önerilen paleti kullanmak için gerekli değildir.

Daha fazla bilgi için [IOleObject::SetColorScheme](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) Windows SDK.

##  <a name="onsetdata"></a>  COleServerItem::OnSetData

Belirtilen verilerle OLE öğesinin verileri değiştirmek için framework tarafından çağırılır.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
İşaretçi bir [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) yapısı veri biçimini belirleme.

*lpStgMedium*<br/>
İşaretçi bir [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) verilerin bulunduğu yapı.

*bRelease*<br/>
İşlev çağrısı tamamladıktan sonra depolama ortamı sahipliğini kimlerin gösterir. Çağıranın kimin adına depolama ortamına ayrılan kaynakları serbest bırakmak için sorumlu olduğunu belirler. Çağıranın bu ayarlayarak yapar *bRelease*. Varsa *bRelease* olan sıfır değilse, sunucu öğesi kullanmadan tamamlandığında ortam boşaltma, aittir. Zaman *bRelease* 0 ise, çağırana sahipliği korur ve sunucu öğesi yalnızca çağrı süresi boyunca depolama ortamı kullanabilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Sunucu öğesi, bu alınırken başarıyla kadar veri sahipliğini almaz. Diğer bir deyişle, 0 döndürürse sahipliği almaz. Veri kaynağı sahipliği alırsa, depolama ortamı çağırarak serbest bıraktığı [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) işlevi.

Varsayılan uygulama, hiçbir şey yapmaz. Bu işlev, belirtilen verilerle OLE öğesinin verileri değiştirmek için geçersiz kılın. Bu gelişmiş bir, geçersiz kılınabilir.

Daha fazla bilgi için [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium), [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc), ve [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) Windows SDK.

##  <a name="onsetextent"></a>  COleServerItem::OnSetExtent

OLE öğesini ne kadar kapsayıcı belge için kullanılabilir alanı bildirmek için framework tarafından çağırılır.

```
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,
    const CSize& size);
```

### <a name="parameters"></a>Parametreler

*nDrawAspect*<br/>
En boy olan sınırları belirtilen OLE öğesinin belirtir. Bu parametre aşağıdaki değerlerden herhangi birini alabilir:

- DVASPECT_ICON öğesi, bir nesnenin kapsayıcısı içindeki olarak görüntülenebilir şekilde temsil edilir.

- Tarama Aracı içinde görüntülenebilen böylece desteklemek istiyorsanız öğesi "küçük" gösteriminde işlenir.

- DVASPECT_ICON öğesi bir simge ile temsil edilir.

- Dosya menüsünden Yazdır komutunu kullanarak yazdırılmış gibi DVASPECT_ICON öğesi gösterilir.

*Boyutu*<br/>
A [CSize](../../atl-mfc-shared/reference/csize-class.md) yapısı OLE öğesinin yeni boyutunu belirtme.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulamasını Microsoft Foundation Class Kitaplığı ile yazılmışsa, bu işlev aldığında çağrılan [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) üye işlevi, karşılık gelen `COleClientItem` nesne çağrılır. Varsayılan uygulama kümeleri [m_sizeExtent](#m_sizeextent) üyesi için belirtilen boyut, *nDrawAspect* DVASPECT_ICON; olan 0 döndürür. Bu işlev, öğenin boyutu değiştirdiğinizde, özel işlem gerçekleştirmek için geçersiz kılın.

##  <a name="onshow"></a>  COleServerItem::OnShow

OLE öğesini yerinde görüntülemek için sunucu uygulamasının istemek için framework tarafından çağırılır.

```
virtual void OnShow();
```

### <a name="remarks"></a>Açıklamalar

Kapsayıcı uygulamasının kullanıcı bir öğe oluşturur veya düzenleme gibi bir fiili işler genellikle bu işlev çağrılır gösterilecek öğe gerektirir. Varsayılan uygulama yerinde etkinleştirmesi yapmaya çalışır. Bu başarısız olursa, işlev çağrıları `OnOpen` ayrı bir pencerede OLE öğesini göstermek için üye işlevi.

OLE öğesini gösterildiğinde özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.

##  <a name="onupdate"></a>  COleServerItem::OnUpdate

Bir öğe değiştirildiğinde framework tarafından çağırılır.

```
virtual void OnUpdate(
    COleServerItem* pSender,
    LPARAM lHint,
    CObject* pHint,
    DVASPECT nDrawAspect);
```

### <a name="parameters"></a>Parametreler

*pSender*<br/>
Dokument öğesi işaretçisi. NULL olabilir.

*lHint*<br/>
Değiştirme hakkında bilgi içerir.

*pHint*<br/>
Bir nesne değiştirme hakkında bilgi depolamak için işaretçi.

*nDrawAspect*<br/>
DVASPECT sabit bir değer. Bu parametre aşağıdaki değerlerden biri olabilir:

- DVASPECT_ICON öğesi, bir nesnenin kapsayıcısı içindeki olarak görüntülenebilir şekilde temsil edilir.

- Tarama Aracı içinde görüntülenebilen böylece desteklemek istiyorsanız öğesi "küçük" gösteriminde işlenir.

- DVASPECT_ICON öğesi bir simge ile temsil edilir.

- Dosya menüsünden Yazdır komutunu kullanarak yazdırılmış gibi DVASPECT_ICON öğesi gösterilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan Uygulama çağrıları [NotifyChanged](#notifychanged), ipucu veya gönderen bağımsız olarak.

##  <a name="onupdateitems"></a>  COleServerItem::OnUpdateItems

Sunucu belgedeki tüm öğeleri güncelleştirmek için framework tarafından çağırılır.

```
virtual void OnUpdateItems();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan Uygulama çağrıları [UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink) tüm `COleClientItem` belgedeki nesneleri.

##  <a name="setitemname"></a>  COleServerItem::SetItemName

Adı ayarlamak için bağlantılı bir öğe oluşturduğunuzda, bu işlevi çağırın.

```
void SetItemName(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parametreler

*lpszItemName*<br/>
Öğesinin yeni adı işaretçisi.

### <a name="remarks"></a>Açıklamalar

Ad bu belgenin içinde benzersiz olmalıdır. Bağlantılı bir öğeyi düzenlemek için bir sunucu uygulaması çağrıldığında, uygulama öğeyi bulmak için bu adı kullanır. Katıştırılmış öğeleri için bu işlevi çağırın gerekmez.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek HIERSVR](../../visual-cpp-samples.md)<br/>
[CDocItem Sınıfı](../../mfc/reference/cdocitem-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[COleServerDoc Sınıfı](../../mfc/reference/coleserverdoc-class.md)<br/>
[COleTemplateServer Sınıfı](../../mfc/reference/coletemplateserver-class.md)
