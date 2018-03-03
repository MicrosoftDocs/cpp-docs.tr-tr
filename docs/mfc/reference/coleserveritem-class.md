---
title: "COleServerItem sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd64d6a2cf4fe36e62f5c6599521780c4ee002ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="coleserveritem-class"></a>COleServerItem sınıfı
OLE öğeleri için sunucu arabirimi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleServerItem : public CDocItem  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleServerItem::COleServerItem](#coleserveritem)|Oluşturan bir `COleServerItem` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|Sunu ve dönüştürme biçimlerde yerleştirir bir `COleDataSource` nesnesi.|  
|[COleServerItem::CopyToClipboard](#copytoclipboard)|Öğeyi panoya kopyalar.|  
|[COleServerItem::DoDragDrop](#dodragdrop)|Sürükle ve bırak işlemi gerçekleştirir.|  
|[COleServerItem::GetClipboardData](#getclipboarddata)|Veri aktarımı (Sürükle ve bırak veya Pano) kullanmak için veri kaynağını alır.|  
|[COleServerItem::GetDocument](#getdocument)|Öğeyi içeren sunucu belgeyi döndürür.|  
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|Alır **CF_EMBEDSOURCE** bir OLE öğe için verileri.|  
|[COleServerItem::GetItemName](#getitemname)|Öğenin adını döndürür. Yalnızca bağlantılı öğeler için kullanılır.|  
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|Alır `CF_LINKSOURCE` OLE öğesi için veri.|  
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|Alır **CF_OBJECTDESCRIPTOR** bir OLE öğe için verileri.|  
|[COleServerItem::IsConnected](#isconnected)|Öğe şu anda etkin bir kapsayıcıya eklenmiş olup olmadığını gösterir.|  
|[COleServerItem::IsLinkedItem](#islinkeditem)|Öğe bağlantılı OLE öğesi temsil edip etmediğini gösterir.|  
|[COleServerItem::NotifyChanged](#notifychanged)|Tüm kapsayıcıları otomatik bağlantı güncelleştirme ile güncelleştirir.|  
|[COleServerItem::OnDoVerb](#ondoverb)|Fiil yürütmek için çağrılır.|  
|[COleServerItem::OnDraw](#ondraw)|Kapsayıcı öğe çizmek için gerektirdiğinde çağrılır; Gerekli uygulama.|  
|[COleServerItem::OnDrawEx](#ondrawex)|Özelleştirilmiş öğesi çizim için çağrılır.|  
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|Panoya kopyalanan verileri almak için çerçevesi tarafından çağrılır.|  
|[COleServerItem::OnGetExtent](#ongetextent)|OLE öğenin boyutunu almak için çerçevesi tarafından çağrılır.|  
|[COleServerItem::OnInitFromData](#oninitfromdata)|Belirtilen veri aktarım nesnesini içeriğini kullanarak bir OLE öğesi başlatmak için çerçevesi tarafından çağrılır.|  
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|Bağlantılı öğeler güncelleştirme gerekip gerekmediğini belirlemek için çağrılır.|  
|[COleServerItem::OnRenderData](#onrenderdata)|Gecikmeli işleme bir parçası olarak verileri alır.|  
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|Verileri alır bir `CFile` nesnesi Gecikmeli işleme bir parçası olarak.|  
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|Verileri alır bir `HGLOBAL` Gecikmeli işleme bir parçası olarak.|  
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|Öğenin renk düzenini ayarlamak için çağrılır.|  
|[COleServerItem::OnSetData](#onsetdata)|Öğenin veri kümesi için çağrılır.|  
|[COleServerItem::OnSetExtent](#onsetextent)|OLE öğenin boyutunu ayarlamak için çerçevesi tarafından çağrılır.|  
|[COleServerItem::OnUpdate](#onupdate)|Adlı öğeyi belge kısmı zaman ait olduğunu değiştirilir.|  
|[COleServerItem::OnUpdateItems](#onupdateitems)|Sunu önbellek sunucusu belgedeki tüm öğelerin güncelleştirmek için çağrılır.|  
|[COleServerItem::SetItemName](#setitemname)|Öğenin adını ayarlar. Yalnızca bağlantılı öğeler için kullanılır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleServerItem::GetDataSource](#getdatasource)|Dönüştürme biçimleri depolamak için kullanılan nesneyi alır.|  
|[COleServerItem::OnHide](#onhide)|OLE öğesini gizlemek için çerçevesi tarafından çağrılır.|  
|[COleServerItem::OnOpen](#onopen)|OLE öğesi kendi üst düzey penceresinde görüntülenecek çerçevesi tarafından çağrılır.|  
|[COleServerItem::OnShow](#onshow)|Kapsayıcı öğesini göstermek için gerektirdiğinde çağrılır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleServerItem::m_sizeExtent](#m_sizeextent)|Sunucunun ne kadar OLE öğesi görülebilir hakkında bilgilendirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bağlantılı bir öğe bazılarını veya tümünü bir sunucu belgeyi temsil edebilir. Katıştırılmış bir öğe her zaman bir sunucunun tamamı belgeyi temsil eder.  
  
 `COleServerItem` Sınıfı tanımlayan OLE Sistem dinamik bağlantı kitaplıkları (dll) olarak adlandırılan birden fazla geçersiz kılınabilir üye işlevleri genellikle kapsayıcı uygulamadan gelen isteklere yanıt. Bu üye işlevleri görüntülemeden, kendi fiiller yürütme veya kendi veri çeşitli biçimlerde alma gibi çeşitli şekillerde öğesinde dolaylı olarak işlemek kapsayıcı uygulama izin verme.  
  
 Kullanılacak `COleServerItem`, buradan bir sınıf türetin ve uygulama [OnDraw](#ondraw) ve [serileştirme](../../mfc/reference/cobject-class.md#serialize) üye işlevleri. `OnDraw` İşlevi bileşik bir belge kapsayıcı Uygulaması açıldığında, görüntülenmesine izin veren bir öğe meta dosyası gösterimini sağlar. `Serialize` İşlevinin `CObject` izin verme sunucu ve kapsayıcı uygulamalar arasında aktarılması için katıştırılmış bir öğe, bir öğenin yerel gösterimini sağlar. [OnGetExtent](#ongetextent) öğesi boyutu kapsayıcıya etkinleştirme kapsayıcıya öğenin doğal boyutu sağlar.  
  
 Sunucuları ve ilgili konular hakkında daha fazla bilgi için bkz: [sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md) ve "Oluşturma bir kapsayıcı/sunucu uygulaması" makalesinde [kapsayıcılar: Gelişmiş Özellikler](../../mfc/containers-advanced-features.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="addotherclipboarddata"></a>COleServerItem::AddOtherClipboardData  
 Sunu ve dönüştürme biçimleri OLE öğesi için belirtilen yerleştirmek için bu işlevi çağırmak `COleDataSource` nesnesi.  
  
```  
void AddOtherClipboardData(COleDataSource* pDataSource);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataSource`  
 İşaretçi `COleDataSource` nesne verileri hangi yerleştirilmelidir içinde.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamış olan [OnDraw](#ondraw) öğe için sunu biçimi (meta dosyası resim) sağlamak için üye işlevi. Diğer dönüştürme biçimleri desteklemek için bunları kaydetme kullanarak [COleDataSource](../../mfc/reference/coledatasource-class.md) tarafından döndürülen nesne [GetDataSource](#getdatasource) ve geçersiz kılma [OnRenderData](#onrenderdata) üye işlevi desteklemek istediğiniz biçimlerde veriler sağlar.  
  
##  <a name="coleserveritem"></a>COleServerItem::COleServerItem  
 Oluşturan bir `COleServerItem` nesne ve sunucu belgenin belge öğeleri koleksiyonuna ekler.  
  
```  
COleServerItem(
    COleServerDoc* pServerDoc,  
    BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Parametreler  
 `pServerDoc`  
 Yeni öğe içerecek belge işaretçi.  
  
 `bAutoDelete`  
 Bir bağlantı serbest bırakıldığında nesne silinebilir olup olmadığını belirten bayrak. Bu ayar **FALSE** varsa `COleServerItem` nesnesidir silmeniz gerekir, belgenin veri ayrılmaz bir parçasıdır. Bu ayar **TRUE** nesne çerçevesi tarafından silinebilir belgenizin verileri içindeki bir aralık tanımlamak için kullanılan ikincil bir yapı ise.  
  
##  <a name="copytoclipboard"></a>COleServerItem::CopyToClipboard  
 OLE öğesi panoya kopyalamak için bu işlevini çağırın.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bIncludeLink`  
 Bu ayar **TRUE** panoya bağlantı verilerin kopyalanması gereken durumunda. Bu ayar **FALSE** sunucu uygulamanızı bağlantılar desteklemiyorsa.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevini kullanıyor [OnGetClipboardData](#ongetclipboarddata) oluşturmak için üye işlevi bir [COleDataSource](../../mfc/reference/coledatasource-class.md) desteklenen biçimlerde OLE öğesi'nin veri içeren bir nesne. İşlev sonra yerleştirir `COleDataSource` kullanarak Pano nesnesinde [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) işlevi. `COleDataSource` Nesnesi içerir öğesi'nin yerel veri ve onun gösterimi `CF_METAFILEPICT` desteklemek için seçtiğiniz tüm dönüştürme biçimlerde verileri yanı sıra biçimi. Uygulamış olan [serileştirme](../../mfc/reference/cobject-class.md#serialize) ve [OnDraw](#ondraw) çalışması bu üye işlevi için.  
  
##  <a name="dodragdrop"></a>COleServerItem::DoDragDrop  
 Çağrı `DoDragDrop` sürükle ve bırak işlemi gerçekleştirmek için üye işlevi.  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpRectItem*  
 Öğenin dikdörtgen ekranında, istemci alanını göreli piksel cinsinden.  
  
 `ptOffset`  
 Uzaklık `lpItemRect` fare konumuna Sürükle aynı anda bulunduğu.  
  
 `bIncludeLink`  
 Bu ayar **TRUE** panoya bağlantı verilerin kopyalanması gereken durumunda. Ayarlamak **FALSE** uygulamanızı bağlantılar desteklemiyorsa.  
  
 `dwEffects`  
 Sürükleme kaynağı sürükleme işlemi (kopyalama, taşıma ve bağlantı birleşimi) sağlayacak etkilerini belirler.  
  
 `lpRectStartDrag`  
 Sürükle gerçekte başladığı tanımlar dikdörtgen işaretçi. Daha fazla bilgi için aşağıdaki Açıklamalar bölümüne bakın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arasında bir değer `DROPEFFECT` numaralandırması. Eğer öyleyse `DROPEFFECT_MOVE`, özgün verilerin kaldırılması gerekir.  
  
### <a name="remarks"></a>Açıklamalar  
 Sürükle ve bırak işlemi hemen başlamaz. Fare imlecini tarafından belirtilen dikdörtgenden bekler `lpRectStartDrag` veya milisaniye belirtilen sayıda geçtiğinde kadar. Varsa `lpRectStartDrag` olan **NULL**, böylece sürükleme fare imleci bir piksel taşındığında başlatır varsayılan dikdörtgen kullanılır.  
  
 Gecikme süresi bir kayıt defteri anahtarı ayarı tarafından belirtilir. Çağırarak gecikme süresini değiştirebilirsiniz [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) veya [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Gecikme süresi belirtmezseniz, varsayılan değer 200 milisaniye olarak kullanılır. Sürükleme gecikme süresi şekilde depolanır:  
  
-   Windows NT Sürükle gecikme süresi içinde HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay depolanır.  
  
-   Windows 3.x Sürükle gecikme süresi WIN depolanır. INI dosyası [Windows} bölümünde.  
  
-   Windows 95/98 Sürükle gecikme süresi WIN önbelleğe alınmış bir sürümünde depolanır. INI.  
  
 Sürükleme hakkında daha fazla bilgi için gecikme bilgilerini ya da kayıt defterinde depolanır veya. INI dosyası bkz [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) Windows SDK'sındaki.  
  
##  <a name="getclipboarddata"></a>COleServerItem::GetClipboardData  
 Belirtilen doldurmak için bu işlevi çağırmak [COleDataSource](../../mfc/reference/coledatasource-class.md) , çağrıldıklarında panoya kopyalandı tüm verileri nesnesiyle [CopyToClipboard](#copytoclipboard) (aynı verileri de varsa aktarılması, adlı [DoDragDrop](#dodragdrop)).  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataSource`  
 İşaretçi `COleDataSource` OLE öğesi'nin veri tüm desteklenen biçimlerde alacak nesnesi.  
  
 `bIncludeLink`  
 **DOĞRU** panoya bağlantı verilerin kopyalanması gereken durumunda. **YANLIŞ** sunucu uygulamanızı bağlantılar desteklemiyorsa.  
  
 `lpOffset`  
 Fare imleci nesnenin kaynaktan piksel cinsinden uzaklığı.  
  
 `lpSize`  
 Nesnesinin piksel cinsinden boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrılarını [GetEmbedSourceData](#getembedsourcedata) çağrıları ve OLE öğesi için yerel veri almak için üye işlevini [AddOtherClipboardData](#addotherclipboarddata) sunu biçimi ve tüm almak için üye işlevi dönüştürme biçimleri desteklenir. Varsa `bIncludeLink` olan **TRUE**, işlevi de çağırır [GetLinkSourceData](#getlinksourcedata) öğe için bağlantı veri almak için.  
  
 Biçimleri koymak istiyorsanız, bu işlevi geçersiz bir `COleDataSource` nesne önce veya sonra tarafından sağlanan bu biçimleri `CopyToClipboard`.  
  
##  <a name="getdatasource"></a>COleServerItem::GetDataSource  
 Almak için bu işlevi çağırmak [COleDataSource](../../mfc/reference/coledatasource-class.md) sunucu uygulamasının desteklediği dönüştürme biçimlerini depolamak için kullanılan nesne.  
  
```  
COleDataSource* GetDataSource();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `COleDataSource` dönüştürme biçimleri depolamak için kullanılan nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Operations veri aktarımı sırasında çeşitli biçimlerde verileri sunmak için sunucu uygulamanızı istiyorsanız, bu biçimleriyle kaydetmek `COleDataSource` bu işlev tarafından döndürülen nesne. Örneğin, sağlamak istiyorsanız, bir **CF_TEXT** OLE öğesi bir gösterimini Pano veya sürükle ve bırak işlemleri için biçimiyle kaydetmeniz `COleDataSource` nesne bu işlevi döndürür ve geçersizkılma **OnRenderXxxData** veri sağlamak için üye işlevi.  
  
##  <a name="getdocument"></a>COleServerItem::GetDocument  
 Belgenin öğeyi içeren bir işaretçi almak için bu işlevini çağırın.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeyi içeren belge için bir işaretçi; **NULL** öğesi belgenin bir bölümünü değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bağımsız değişken olarak geçirilen sunucu belgeye erişimi sağlayan `COleServerItem` Oluşturucusu.  
  
##  <a name="getembedsourcedata"></a>COleServerItem::GetEmbedSourceData  
 Almak için bu işlevi çağırmak **CF_EMBEDSOURCE** bir OLE öğe için verileri.  
  
```  
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpStgMedium`  
 İşaretçi [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) alacak yapısı **CF_EMBEDSOURCE** OLE öğesi için veri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu biçim öğesi'nin yerel veri içerir. Uygulamış olan `Serialize` düzgün çalışması bu işlev için üye işlevi.  
  
 Sonuç ardından bir veri kaynağına kullanarak eklenebilir [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Bu işlev tarafından otomatik olarak çağrılır [COleServerItem::OnGetClipboardData](#ongetclipboarddata).  
  
 Daha fazla bilgi için bkz: [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows SDK'sındaki.  
  
##  <a name="getitemname"></a>COleServerItem::GetItemName  
 Öğenin adını almak için bu işlevini çağırın.  
  
```  
const CString& GetItemName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğenin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle yalnızca bağlantılı öğeler için bu işlevini çağırın.  
  
##  <a name="getlinksourcedata"></a>COleServerItem::GetLinkSourceData  
 Almak için bu işlevi çağırmak `CF_LINKSOURCE` OLE öğesi için veri.  
  
```  
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpStgMedium`  
 İşaretçi [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) alacak yapısı `CF_LINKSOURCE` OLE öğesi için veri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu biçim türünü OLE öğesi ve OLE öğesi içeren belgeyi bulmak için gereken bilgileri tanımlayan CLSID içerir.  
  
 Sonuç sonra ile bir veri kaynağı eklenebilir [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Bu işlev tarafından otomatik olarak çağrılır [OnGetClipboardData](#ongetclipboarddata).  
  
 Daha fazla bilgi için bkz: [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows SDK'sındaki.  
  
##  <a name="getobjectdescriptordata"></a>COleServerItem::GetObjectDescriptorData  
 Almak için bu işlevi çağırmak **CF_OBJECTDESCRIPTOR** bir OLE öğe için verileri.  
  
```  
void GetObjectDescriptorData(
    LPPOINT lpOffset,  
    LPSIZE lpSize,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpOffset`  
 Fare uzaklığını OLE öğesinin sol üst köşeden'ı tıklatın. Olabilir **NULL**.  
  
 `lpSize`  
 OLE öğesi boyutu. Olabilir **NULL**.  
  
 `lpStgMedium`  
 İşaretçi [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) alacak yapısı **CF_OBJECTDESCRIPTOR** OLE öğesi için veri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bilgiler kopyalanır **STGMEDIUM** tarafından yapısı işaret için `lpStgMedium`. Bu biçim Özel Yapıştır iletişim kutusu için gereken bilgileri içerir.  
  
 Daha fazla bilgi için bkz: [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows SDK'sındaki.  
  
##  <a name="isconnected"></a>COleServerItem::IsConnected  
 OLE öğesi bağlı olup olmadığını görmek için bu işlevini çağırın.  
  
```  
BOOL IsConnected() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe bağlıysa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 OLE öğesi bir veya daha fazla kapsayıcıları öğesi başvuran bağlı olarak kabul edilir. Bir öğe başvuru sayısı 0'dan büyük veya katıştırılmış bir öğe ise, bağlı.  
  
##  <a name="islinkeditem"></a>COleServerItem::IsLinkedItem  
 OLE öğesi bağlantılı bir öğe olup olmadığını görmek için bu işlevini çağırın.  
  
```  
BOOL IsLinkedItem() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe bağlantılı bir öğe ise sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğe geçerli olduğunu ve belgenin katıştırılmış öğeleri listesinde döndürülmez öğeyi bağlanır. Bağlantılı bir öğe olabilir veya bir kapsayıcıya bağlı değil.  
  
 Bağlantılı ve katıştırılmış öğeleri için aynı sınıfını kullanmak için yaygın bir durumdur. `IsLinkedItem`birçok kez kodu ortak olmasına rağmen katıştırılmış öğeleri farklı davranır bağlantılı öğeler yapmanızı sağlar.  
  
##  <a name="m_sizeextent"></a>COleServerItem::m_sizeExtent  
 Bu üye sunucunun ne kadar nesne kapsayıcısı belgede görünür olduğunu söyler.  
  
```  
CSize m_sizeExtent;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulaması [OnSetExtent](#onsetextent) bu üye ayarlar.  
  
##  <a name="notifychanged"></a>COleServerItem::NotifyChanged  
 Bağlantılı öğesi değiştirildikten sonra bu işlevini çağırın.  
  
```  
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Parametreler  
 `nDrawAspect`  
 Arasında bir değer `DVASPECT` OLE öğesi hangi yönden değiştiğini gösteren numaralandırma. Bu parametre aşağıdaki değerlerden herhangi birini içerebilir:  
  
- `DVASPECT_CONTENT`Öğesi, katıştırılmış nesne kapsayıcısı içinde olarak görüntülenebilir şekilde gösterilir.  
  
- `DVASPECT_THUMBNAIL`Tarama Aracı içinde görüntülenebilir böylece öğesi bir "küçük" gösterimi işlenir.  
  
- `DVASPECT_ICON`Öğe bir simge ile temsil edilir.  
  
- `DVASPECT_DOCPRINT`Dosya menüsünden Yazdır komutunu kullanarak yazdırılan gibi öğeyi temsil edilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kapsayıcı öğe, otomatik bir bağlantıyla belgeye bağlıysa, öğe değişiklikleri yansıtacak şekilde güncelleştirilir. Microsoft Foundation Class Kitaplığı kullanılarak yazılmış kapsayıcı uygulamalarında [COleClientItem::OnChange](../../mfc/reference/coleclientitem-class.md#onchange) yanıt olarak adlandırılır.  
  
##  <a name="ondoverb"></a>COleServerItem::OnDoVerb  
 Belirtilen fiil yürütmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDoVerb(LONG iVerb);
```  
  
### <a name="parameters"></a>Parametreler  
 `iVerb`  
 Yürütülecek fiili belirtir. Aşağıdakilerden herhangi biri olabilir:  
  
|Değer|Açıklama|Simgesi|  
|-----------|-------------|------------|  
|0|Birincil fiil|`OLEIVERB_PRIMARY`|  
|1.|İkincil fiil|(Hiçbiri)|  
|- 1|Görüntü öğesini düzenlemek için|`OLEIVERB_SHOW`|  
|- 2|Ayrı bir pencerede öğesi düzenleme|`OLEIVERB_OPEN`|  
|- 3|Öğe Gizle|`OLEIVERB_HIDE`|  
  
 -1 genellikle başka bir fiil için diğer ad değerdir. Açık düzenleme desteklenmiyorsa, -2 -1 olarak aynı etkiye sahiptir. Ek değerler için bkz: [Rpc_e_serverfault](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK'sındaki.  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsayıcı uygulama Microsoft Foundation Class Kitaplığı ile yazılmışsa, bu işlev aldığında çağrılan [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate) ilgili üye işlevi `COleClientItem` nesne çağrılır. Varsayılan Uygulama çağrıları [OnShow](#onshow) üye işlev, birincil fiil veya `OLEIVERB_SHOW` belirtilirse, [açıldığında](#onopen) ise ikincil fiil veya `OLEIVERB_OPEN` belirtilirse ve [OnHide](#onhide) varsa `OLEIVERB_HIDE` belirtilir. Varsayılan Uygulama çağrıları `OnShow` varsa `iVerb` yukarıda listelenen fiillerden biri değil.  
  
 Birincil fiil öğesi göstermez bu işlev geçersiz kılın. Örneğin, öğesi bir ses kaydetme ve birincil fiil Play ise öğeyi yürütmek için sunucu uygulaması görüntülenecek olurdu değil.  
  
 Daha fazla bilgi için bkz: [Rpc_e_serverfault](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK'sındaki.  
  
##  <a name="ondraw"></a>COleServerItem::OnDraw  
 OLE öğesi meta dosyası olarak işlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnDraw(
    CDC* pDC,  
    CSize& rSize) = 0;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Bir işaretçi [CDC](../../mfc/reference/cdc-class.md) öğesi çizmek nesne. Öznitelik işlevini çağırabilmeniz için bunu yapmak, böylece meta dosyası aygıta özgü yapacağı rağmen görüntüleme bağlamı öznitelik görünen bağlamına otomatik olarak bağlanır.  
  
 `rSize`  
 Boyut, buna **HIMETRIC** , meta dosyası çizmek birim.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe başarıyla çizilmiş, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 OLE öğesi meta dosyası gösterimini kapsayıcı uygulamasında öğeyi görüntülemek için kullanılır. Kapsayıcı uygulama Microsoft Foundation Class Kitaplığı ile yazılmışsa, meta dosyası tarafından kullanılan [çizin](../../mfc/reference/coleclientitem-class.md#draw) ilgili üye işlevi [COleClientItem](../../mfc/reference/coleclientitem-class.md) nesnesi. Varsayılan uygulama yok. Belirtilen cihaz bağlamına öğesi çizmek için bu işlevi geçersiz kılmanız gerekir.  
  
##  <a name="ondrawex"></a>COleServerItem::OnDrawEx  
 Tüm çizim için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnDrawEx(
    CDC* pDC,  
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Bir işaretçi [CDC](../../mfc/reference/cdc-class.md) öğesi çizmek nesne. Öznitelik işlevini çağırabilmeniz için bunu yapmak, böylece meta dosyası aygıta özgü yapacağı rağmen DC DC özniteliğine otomatik olarak bağlanır.  
  
 `nDrawAspect`  
 Arasında bir değer `DVASPECT` numaralandırması. Bu parametre aşağıdaki değerlerden herhangi birini içerebilir:  
  
- `DVASPECT_CONTENT`Öğesi, katıştırılmış nesne kapsayıcısı içinde olarak görüntülenebilir şekilde gösterilir.  
  
- `DVASPECT_THUMBNAIL`Tarama Aracı içinde görüntülenebilir böylece öğesi bir "küçük" gösterimi işlenir.  
  
- `DVASPECT_ICON`Öğe bir simge ile temsil edilir.  
  
- `DVASPECT_DOCPRINT`Dosya menüsünden Yazdır komutunu kullanarak yazdırılan gibi öğeyi temsil edilir.  
  
 `rSize`  
 Öğenin boyutunu **HIMETRIC** birimleri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe başarıyla çizilmiş, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Uygulama çağrıları `OnDraw` zaman `DVASPECT` eşittir `DVASPECT_CONTENT`; Aksi halde başarısız olur.  
  
 Başka bir yönü için sunu veri sağlamak için bu işlevi geçersiz `DVASPECT_CONTENT`, gibi `DVASPECT_ICON` veya `DVASPECT_THUMBNAIL`.  
  
##  <a name="ongetclipboarddata"></a>COleServerItem::OnGetClipboardData  
 Alınacak çerçevesi tarafından çağrılır bir `COleDataSource` Pano'ya çağrısıyla konulabilir tüm veri içeren bir nesne [CopyToClipboard](#copytoclipboard) üye işlevi.  
  
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
 Fare imlecini kaynaktan nesnesinin piksel cinsinden uzaklığı.  
  
 `lpSize`  
 Nesnesinin piksel cinsinden boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [COleDataSource](../../mfc/reference/coledatasource-class.md) Pano veri içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulamasını çağıran [GetClipboardData](#getclipboarddata).  
  
##  <a name="ongetextent"></a>COleServerItem::OnGetExtent  
 İçinde boyutu almak için framework tarafından çağrılan **HIMETRIC** OLE madde sayısı.  
  
```  
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>Parametreler  
 `nDrawAspect`  
 Alınacak olan sınırları olan OLE öğesi yönünü belirtir. Bu parametre aşağıdaki değerlerden herhangi birini içerebilir:  
  
- `DVASPECT_CONTENT`Öğesi, katıştırılmış nesne kapsayıcısı içinde olarak görüntülenebilir şekilde gösterilir.  
  
- `DVASPECT_THUMBNAIL`Tarama Aracı içinde görüntülenebilir böylece öğesi bir "küçük" gösterimi işlenir.  
  
- `DVASPECT_ICON`Öğe bir simge ile temsil edilir.  
  
- `DVASPECT_DOCPRINT`Dosya menüsünden Yazdır komutunu kullanarak yazdırılan gibi öğeyi temsil edilir.  
  
 `rSize`  
 Başvuru bir `CSize` OLE öğenin boyutunu alacak nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsayıcı uygulama Microsoft Foundation Class Kitaplığı ile yazılmışsa, bu işlev aldığında çağrılan [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) ilgili üye işlevi `COleClientItem` nesne çağrılır. Varsayılan uygulama hiçbir şey yapmaz. Bunu kendiniz uygulamalıdır. OLE öğesi boyutu için bir isteği işlerken özel işleme gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.  
  
##  <a name="onhide"></a>COleServerItem::OnHide  
 OLE öğesini gizlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan çağrıları **COleServerDoc::OnShowDocument (FALSE)**. İşlev OLE öğesi gizli kapsayıcı de bildirir. OLE öğeyi gizlerken özel işleme gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.  
  
##  <a name="oninitfromdata"></a>COleServerItem::OnInitFromData  
 OLE öğenin içeriğini kullanarak başlatmak için çerçevesi tarafından çağrılır `pDataObject`.  
  
```  
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,  
    BOOL bCreation);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDataObject`  
 OLE öğesi başlatma için çeşitli biçimlerde verileri içeren bir OLE veri nesnesine işaretçi.  
  
 `bCreation`  
 **DOĞRU** işlevi yeni bir kapsayıcı uygulama tarafından oluşturulan OLE öğeyi başlatmak için çağrılıp çağrılmayacağını. **YANLIŞ** işlevi zaten var olan bir OLE öğesini içeriğini değiştirmek için çağrılıp çağrılmayacağını.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bCreation` olan **doğru**, bir kapsayıcı yeni geçerli seçime dayalı Nesne Ekle uyguluyorsa bu işlev çağrılır. Seçilen verileri yeni OLE öğesi oluşturulurken kullanılır. Örneğin, ne zaman bir hücre aralığı bir elektronik tablo programında seçerek ve ardından bir grafik oluşturmak için Yeni Nesne Ekle kullanarak seçilen aralık değerleri temel. Varsayılan uygulama hiçbir şey yapmaz. Bu işlev tarafından sunulan kabul edilebilir bir biçim arasından geçersiz kılma `pDataObject` ve sağlanan verileri temel alan OLE öğesi başlatma. Gelişmiş budur geçersiz kılınabilir.  
  
 Daha fazla bilgi için bkz: [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) Windows SDK'sındaki.  
  
##  <a name="onopen"></a>COleServerItem::OnOpen  
 Ayrı bir sunucu uygulaması örneği yerine yer OLE öğesi görüntülenecek çerçevesi tarafından çağrılır.  
  
```  
virtual void OnOpen();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama OLE öğesi içeren belgeyi görüntüleme ilk çerçeve penceresi etkinleştirir; uygulamanın kısa bir sunucu ise, varsayılan uygulama ana pencereyi gösterir. İşlev OLE öğesi açılmış kapsayıcı de bildirir.  
  
 OLE öğeyi açılırken özel işleme gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar. Bu, özellikle açıldığında seçimi bağlantısını ayarlamak istediğiniz yerde bağlantılı öğeler ile yaygındır.  
  
 Daha fazla bilgi için bkz: [IOleClientSite::OnShowWindow](http://msdn.microsoft.com/library/windows/desktop/ms688658) Windows SDK'sındaki.  
  
##  <a name="onqueryupdateitems"></a>COleServerItem::OnQueryUpdateItems  
 Geçerli sunucu belgedeki tüm bağlantılı öğeler güncel olup olmadığını belirlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnQueryUpdateItems();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belge güncelleştirmeleri gerek öğeleri varsa sıfır olmayan; tüm öğeleri güncel yoksa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe, kendi kaynak belge değiştirildi, ancak bağlantılı öğesi belgedeki değişiklikleri yansıtacak şekilde güncelleştirilmemiş güncel değil.  
  
##  <a name="onrenderdata"></a>COleServerItem::OnRenderData  
 Belirtilen biçim verileri almak için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFormatEtc`  
 İşaret [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapısı içinde bilgi istenen biçimini belirtme.  
  
 `lpStgMedium`  
 İşaret eden bir [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) veri olduğu döndürülecek yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen biçim biridir önceden yerleştirilen `COleDataSource` kullanarak nesne [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) veya [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) Gecikmeli işleme için üye işlevi. Bu işlev varsayılan uygulamasını çağıran [OnRenderFileData](#onrenderfiledata) veya [OnRenderGlobalData](#onrenderglobaldata), sırasıyla sağlanan depolama ortamına bir dosya veya bellek ise. Bu biçimler hiçbiri sağlanırsa, varsayılan uygulama 0 döndürür ve hiçbir şey yapmaz.  
  
 Varsa `lpStgMedium` ->  *ortam türü* olan **TYMED_NULL**, **STGMEDIUM** ayrılmış ve belirtildiği gibi doldurulmuş *lpFormatEtc -> ortam türü*. Aksi takdirde **TYMED_NULL**, **STGMEDIUM** verilerle yerinde dolu olması gerekir.  
  
 Gelişmiş budur geçersiz kılınabilir. İstenen biçim ve orta verilerinizdeki sağlamak için bu işlevi geçersiz kılar. Verilerinizi bağlı olarak, bu işlevin diğer sürümlerinden birini yerine geçersiz kılmak istediğiniz. Verilerinizi küçük ve sabit boyutu ise, geçersiz kılma `OnRenderGlobalData`. Verilerinizi bir dosyaya veya bir değişken boyutu, geçersiz kılma `OnRenderFileData`.  
  
 Daha fazla bilgi için bkz: [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177), ve [ortam türü](http://msdn.microsoft.com/library/windows/desktop/ms691227) Windows SDK.  
  
##  <a name="onrenderfiledata"></a>COleServerItem::OnRenderFileData  
 Depolama ortamı dosya olduğunda belirtilen biçim verileri almak için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFormatEtc`  
 İşaret [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapısı içinde bilgi istenen biçimini belirtme.  
  
 `pFile`  
 İşaret eden bir `CFile` verileri olduğu işlenecek nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen biçim biridir önceden yerleştirilen `COleDataSource` kullanarak nesne [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Gecikmeli işleme için üye işlevi. Bu işlev varsayılan uygulaması yalnızca döndürür **FALSE**.  
  
 Gelişmiş budur geçersiz kılınabilir. İstenen biçim ve orta verilerinizdeki sağlamak için bu işlevi geçersiz kılar. Verilerinizi bağlı olarak, bu işlevin diğer sürümlerinden birini yerine geçersiz kılmak istediğiniz. Birden çok depolama ortamlarının işlemek istiyorsanız, geçersiz kılma [OnRenderData](#onrenderdata). Verilerinizi bir dosyaya veya bir değişken boyutu, geçersiz kılma [OnRenderFileData](#onrenderfiledata).  
  
 Daha fazla bilgi için bkz: [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
##  <a name="onrenderglobaldata"></a>COleServerItem::OnRenderGlobalData  
 Belirtilen depolama ortamına genel bellek olduğunda belirtilen biçim verileri almak için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFormatEtc`  
 İşaret [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapısı içinde bilgi istenen biçimini belirtme.  
  
 `phGlobal`  
 Verileri döndürülecek olan genel bellek için bir tanıtıcı noktalarına. Bellek ayrıldı, bu parametre olabilir **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen biçim biridir önceden yerleştirilen `COleDataSource` kullanarak nesne [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Gecikmeli işleme için üye işlevi. Bu işlev varsayılan uygulaması yalnızca döndürür **FALSE**.  
  
 Varsa `phGlobal` olan **NULL**, ardından yeni `HGLOBAL` döndürdü ve ayrılan gerekir `phGlobal`. Aksi takdirde, `HGLOBAL` tarafından belirtilen `phGlobal` verilerle dolu olması gerekir. Veri miktarını yerleştirilen `HGLOBAL` bellek bloğu geçerli boyutunu aşmamalıdır. Ayrıca, büyük boyutlu bir blok ayrılamaz.  
  
 Gelişmiş budur geçersiz kılınabilir. İstenen biçim ve orta verilerinizdeki sağlamak için bu işlevi geçersiz kılar. Verilerinizi bağlı olarak, bu işlevin diğer sürümlerinden birini yerine geçersiz kılmak istediğiniz. Birden çok depolama ortamlarının işlemek istiyorsanız, geçersiz kılma [OnRenderData](#onrenderdata). Verilerinizi bir dosyaya veya bir değişken boyutu, geçersiz kılma [OnRenderFileData](#onrenderfiledata).  
  
 Daha fazla bilgi için bkz: [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
##  <a name="onsetcolorscheme"></a>COleServerItem::OnSetColorScheme  
 OLE öğesi düzenlenmesi sırasında kullanılacak bir renk paleti belirtmek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpLogPalette`  
 Bir Windows işaretçi [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Renk paleti kullanılırsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsayıcı uygulama Microsoft Foundation Class Kitaplığı kullanılarak yazılmış olduğundan, bu işlev aldığında çağrılan [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) ilgili işlevi `COleClientItem` nesne çağrılır. Varsayılan uygulama döndürür **FALSE**. Önerilen palet kullanmak istiyorsanız, bu işlev geçersiz kılar. Sunucu uygulaması, önerilen palet kullanmak için gerekli değildir.  
  
 Daha fazla bilgi için bkz: [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) Windows SDK'sındaki.  
  
##  <a name="onsetdata"></a>COleServerItem::OnSetData  
 OLE öğesi'nin verileri belirtilen verilerle değiştirmek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFormatEtc`  
 İşaretçi bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) verilerin biçimini belirten yapısı.  
  
 `lpStgMedium`  
 İşaretçi bir [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) yapısı verilerin bulunduğu.  
  
 `bRelease`  
 İşlev çağrısı tamamladıktan sonra depolama ortamına sahipliğini kimlerin olduğunu gösterir. Arayan adına depolama ortamına ayrılan kaynakları serbest bırakma için sorumlu kim karar verir. Arayan ayarlayarak bunu yapar `bRelease`. Varsa `bRelease` olduğu sıfır olmayan, sunucu öğesini kullanmaya tamamlandığında Orta boşaltma, aittir. Zaman `bRelease` 0'dır, çağıran sahipliği korur ve sunucu öğesini yalnızca çağrı süresince depolama ortamı kullanabilirsiniz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bunu alınırken başarıyla kadar sunucu öğesi veri sahipliğini almaz. Diğer bir deyişle, 0 döndürürse sahipliği almaz. Veri kaynağı sahipliği alırsa, çağırarak depolama ortamına boşaltır [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) işlevi.  
  
 Varsayılan uygulama hiçbir şey yapmaz. OLE öğesi'nin verileri belirtilen verilerle değiştirmek için bu işlevi geçersiz kılar. Gelişmiş budur geçersiz kılınabilir.  
  
 Daha fazla bilgi için bkz: [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177), ve [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) Windows SDK'sındaki.  
  
##  <a name="onsetextent"></a>COleServerItem::OnSetExtent  
 OLE öğesi ne kadar alan kapsayıcı belge için kullanılabilir olup çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,  
    const CSize& size);
```  
  
### <a name="parameters"></a>Parametreler  
 `nDrawAspect`  
 Sınırların belirtilen OLE öğesi yönünü belirtir. Bu parametre aşağıdaki değerlerden herhangi birini içerebilir:  
  
- `DVASPECT_CONTENT`Öğesi, katıştırılmış nesne kapsayıcısı içinde olarak görüntülenebilir şekilde gösterilir.  
  
- `DVASPECT_THUMBNAIL`Tarama Aracı içinde görüntülenebilir böylece öğesi bir "küçük" gösterimi işlenir.  
  
- `DVASPECT_ICON`Öğe bir simge ile temsil edilir.  
  
- `DVASPECT_DOCPRINT`Dosya menüsünden Yazdır komutunu kullanarak yazdırılan gibi öğeyi temsil edilir.  
  
 `size`  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) yapısı OLE öğesi yeni boyutunu belirtme.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsayıcı uygulama Microsoft Foundation Class Kitaplığı ile yazılmışsa, bu işlev aldığında çağrılan [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) ilgili üye işlevi `COleClientItem` nesne çağrılır. Varsayılan uygulama kümeleri [m_sizeExtent](#m_sizeextent) üyesi için belirtilen boyut, `nDrawAspect` olan `DVASPECT_CONTENT`; Aksi halde 0 döndürür. Öğenin boyutunu değiştirdiğinizde özel işlem gerçekleştirmek için bu işlevi geçersiz kılar.  
  
##  <a name="onshow"></a>COleServerItem::OnShow  
 OLE öğesi yerinde görüntülemek için sunucu uygulaması istemek üzere çerçevesi tarafından çağrılır.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev kapsayıcı uygulamasının kullanıcı bir öğeyi oluşturduğunda veya düzenleme gibi bir fiil çalıştırır genellikle çağrılır gösterilecek öğe gerektirir. Varsayılan uygulama yerinde etkinleştirme çalışır. Bu başarısız olursa, işlev çağrıları `OnOpen` ayrı bir pencerede OLE öğesi görüntülenecek üye işlevi.  
  
 OLE öğeyi gösterildiğinde özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.  
  
##  <a name="onupdate"></a>COleServerItem::OnUpdate  
 Bir öğe değiştirildiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnUpdate(
    COleServerItem* pSender,  
    LPARAM lHint,  
    CObject* pHint,  
    DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSender`  
 Belge değiştiren öğesi işaretçisi. Olabilir **NULL**.  
  
 `lHint`  
 Değiştirme hakkında bilgi içerir.  
  
 `pHint`  
 Nesneyi değiştirme hakkında bilgi depolamak için işaretçi.  
  
 `nDrawAspect`  
 Arasında bir değer `DVASPECT` numaralandırması. Bu parametre aşağıdaki değerlerden biri olabilir:  
  
- `DVASPECT_CONTENT`Öğesi, katıştırılmış nesne kapsayıcısı içinde olarak görüntülenebilir şekilde gösterilir.  
  
- `DVASPECT_THUMBNAIL`Tarama Aracı içinde görüntülenebilir böylece öğesi bir "küçük" gösterimi işlenir.  
  
- `DVASPECT_ICON`Öğe bir simge ile temsil edilir.  
  
- `DVASPECT_DOCPRINT`Dosya menüsünden Yazdır komutunu kullanarak yazdırılan gibi öğeyi temsil edilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Uygulama çağrıları [NotifyChanged](#notifychanged)ipucu veya gönderen bağımsız olarak.  
  
##  <a name="onupdateitems"></a>COleServerItem::OnUpdateItems  
 Sunucu belgedeki tüm öğeleri güncelleştirmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnUpdateItems();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Uygulama çağrıları [UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink) tüm `COleClientItem` belgedeki nesneleri.  
  
##  <a name="setitemname"></a>COleServerItem::SetItemName  
 Adını ayarlamak için bağlantılı bir öğe oluşturduğunuzda bu işlevini çağırın.  
  
```  
void SetItemName(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszItemName`  
 Öğesinin yeni adını işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Ad bu belgenin içinde benzersiz olmalıdır. Bağlantılı bir öğe düzenlemek için bir sunucu uygulaması çağrıldığında, uygulama bu adı öğesini bulmak için kullanır. Katıştırılmış öğeleri için bu işlevi çağırmak gerekmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek HIERSVR](../../visual-cpp-samples.md)   
 [CDocItem sınıfı](../../mfc/reference/cdocitem-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleClientItem sınıfı](../../mfc/reference/coleclientitem-class.md)   
 [COleServerDoc sınıfı](../../mfc/reference/coleserverdoc-class.md)   
 [COleTemplateServer Sınıfı](../../mfc/reference/coletemplateserver-class.md)
