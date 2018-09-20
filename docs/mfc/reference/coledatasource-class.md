---
title: COleDataSource sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDataSource
- AFXOLE/COleDataSource
- AFXOLE/COleDataSource::COleDataSource
- AFXOLE/COleDataSource::CacheData
- AFXOLE/COleDataSource::CacheGlobalData
- AFXOLE/COleDataSource::DelayRenderData
- AFXOLE/COleDataSource::DelayRenderFileData
- AFXOLE/COleDataSource::DelaySetData
- AFXOLE/COleDataSource::DoDragDrop
- AFXOLE/COleDataSource::Empty
- AFXOLE/COleDataSource::FlushClipboard
- AFXOLE/COleDataSource::GetClipboardOwner
- AFXOLE/COleDataSource::OnRenderData
- AFXOLE/COleDataSource::OnRenderFileData
- AFXOLE/COleDataSource::OnRenderGlobalData
- AFXOLE/COleDataSource::OnSetData
- AFXOLE/COleDataSource::SetClipboard
dev_langs:
- C++
helpviewer_keywords:
- COleDataSource [MFC], COleDataSource
- COleDataSource [MFC], CacheData
- COleDataSource [MFC], CacheGlobalData
- COleDataSource [MFC], DelayRenderData
- COleDataSource [MFC], DelayRenderFileData
- COleDataSource [MFC], DelaySetData
- COleDataSource [MFC], DoDragDrop
- COleDataSource [MFC], Empty
- COleDataSource [MFC], FlushClipboard
- COleDataSource [MFC], GetClipboardOwner
- COleDataSource [MFC], OnRenderData
- COleDataSource [MFC], OnRenderFileData
- COleDataSource [MFC], OnRenderGlobalData
- COleDataSource [MFC], OnSetData
- COleDataSource [MFC], SetClipboard
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2aa5ea0b95235d778c6491cca5eeb6b4a826b8bd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428115"
---
# <a name="coledatasource-class"></a>COleDataSource sınıfı

İçine bir uygulama oluşturma sırasında yerleşim verilerine sağlayacağı veri yerleştirir bir önbellek olarak görev yapar, Pano veya sürükle ve bırak işlemleri gibi işlemleri aktarın.

## <a name="syntax"></a>Sözdizimi

```
class COleDataSource : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleDataSource::COleDataSource](#coledatasource)|Oluşturur bir `COleDataSource` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDataSource::CacheData](#cachedata)|Belirtilen biçimi kullanarak bir veri sunan bir `STGMEDIUM` yapısı.|
|[COleDataSource::CacheGlobalData](#cacheglobaldata)|Verileri bir HGLOBAL kullanarak belirtilen bir biçimde sunar.|
|[COleDataSource::DelayRenderData](#delayrenderdata)|Verileri kullanarak gecikmeli işleme belirtilen bir biçimde sunar.|
|[COleDataSource::DelayRenderFileData](#delayrenderfiledata)|Belirtilen biçimde veri sunan bir `CFile` işaretçi.|
|[COleDataSource::DelaySetData](#delaysetdata)|Desteklenen her biçim adlı `OnSetData`.|
|[COleDataSource::DoDragDrop](#dodragdrop)|Bir veri kaynağı ile sürükle ve bırak işlemleri gerçekleştirir.|
|[COleDataSource::Empty](#empty)|Boşaltır `COleDataSource` veri nesnesi.|
|[COleDataSource::FlushClipboard](#flushclipboard)|Tüm verileri panoya işler.|
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|Panodaki yerleştirilen verileri hala var olduğunu doğrular.|
|[COleDataSource::OnRenderData](#onrenderdata)|Gecikmeli işleme bir parçası olarak verileri alır.|
|[COleDataSource::OnRenderFileData](#onrenderfiledata)|Verileri alır bir `CFile` Gecikmeli işleme bir parçası olarak.|
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|Gecikmeli işleme bir parçası olarak bir HGLOBAL içine verileri alır.|
|[COleDataSource::OnSetData](#onsetdata)|Verileri değiştirme için çağrılır `COleDataSource` nesne.|
|[COleDataSource::SetClipboard](#setclipboard)|Basamak bir `COleDataSource` Panodaki nesne.|

## <a name="remarks"></a>Açıklamalar

OLE veri kaynaklarını doğrudan oluşturabilirsiniz. Alternatif olarak, [Coleclientıtem](../../mfc/reference/coleclientitem-class.md) ve [Coleserverıtem](../../mfc/reference/coleserveritem-class.md) sınıfları yanıt olarak OLE veri kaynaklarını oluşturmak, `CopyToClipboard` ve `DoDragDrop` üye işlevleri. Bkz: [COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard) kısa bir açıklaması için. Geçersiz kılma `OnGetClipboardData` sınıfının üye işlevinde ek Pano biçimleri OLE veri kaynağındaki verileri eklemek için istemci öğesi veya sunucu öğesi için oluşturulan `CopyToClipboard` veya `DoDragDrop` üye işlevi.

Veri aktarımı için hazırlamak istediğinizde, bu sınıfın bir nesnesi oluşturma ve verileriniz için en uygun yöntemi kullanarak, verilerle doldurmanız gerekir. Bir veri kaynağında eklenir yolu, doğrudan olup verileri hemen sağlanan tarafından etkilenir (anlık görüntü oluşturma) ya da isteğe bağlı (Gecikmeli işleme). İçinde sağlayan veri kullanılacak Pano biçimi geçirerek her Pano biçimi için (ve isteğe bağlı [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) yapısı), çağrı [DelayRenderData](#delayrenderdata).

Veri kaynakları ve veri aktarımı hakkında daha fazla bilgi için bkz [veri nesneleri ve veri kaynakları (OLE)](../../mfc/data-objects-and-data-sources-ole.md). Buna ek olarak, makalenin [Pano konuları](../../mfc/clipboard.md) OLE Pano mekanizmasını açıklar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDataSource`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="cachedata"></a>  COleDataSource::CacheData

Veri aktarımı işlemleri sırasında veri sunulur bir biçimi belirtmek için bu işlevi çağırın.

```
void CacheData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verileri sunmak için olduğu Pano biçimi. Bu parametre bir ön tanımlı Pano biçimlerini veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) işlevi.

*lpStgMedium*<br/>
İşaret eden bir [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) içeren belirtilen biçimde veri yapısı.

*lpFormatEtc*<br/>
İşaret eden bir [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) veri olduğu sunulacak biçimini açıklayan yapısı. Pano biçimi tarafından belirtilen dışında ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer sağlamanız *cfFormat*. NULL ise, diğer alanları için varsayılan değerler kullanılır `FORMATETC` yapısı.

### <a name="remarks"></a>Açıklamalar

Bu işlev hemen işleme kullanarak sağladığı için veri sağlamanız gerekir. Veriler, gerekli olana kadar önbelleğe alınır.

Kullanarak veri kaynağı bir [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) yapısı. Ayrıca `CacheGlobalData` sağladığınız veri miktarı, üye işlevi bir HGLOBAL verimli şekilde kullanma aktarılacak küçük.

Çağrısından sonra `CacheData` `ptd` üyesi `lpFormatEtc` ve içeriğini *lpStgMedium* çağıran tarafından değil bir veri nesnesi tarafından sahip olunan.

Gecikmeli işleme kullanmak için çağrı [DelayRenderData](#delayrenderdata) veya [DelayRenderFileData](#delayrenderfiledata) üye işlevi. MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme bkz [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).

Daha fazla bilgi için [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) ve [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) yapıları, Windows SDK'sı.

Daha fazla bilgi için [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK.

##  <a name="cacheglobaldata"></a>  COleDataSource::CacheGlobalData

Veri aktarımı işlemleri sırasında veri sunulur bir biçimi belirtmek için bu işlevi çağırın.

```
void CacheGlobalData(
    CLIPFORMAT cfFormat,
    HGLOBAL hGlobal,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verileri sunmak için olduğu Pano biçimi. Bu parametre bir ön tanımlı Pano biçimlerini veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) işlevi.

*hGlobal*<br/>
Belirtilen biçimde verileri içeren genel bellek bloğuna işleyin.

*lpFormatEtc*<br/>
İşaret eden bir [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) veri olduğu sunulacak biçimini açıklayan yapısı. Pano biçimi tarafından belirtilen dışında ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer sağlamanız *cfFormat*. NULL ise, diğer alanları için varsayılan değerler kullanılır `FORMATETC` yapısı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, işlev çağrılırken veri sağlamalısınız hemen işleme kullanarak veri sağlar. veriler, gerekli olana kadar önbelleğe alınır. Kullanım `CacheData` büyük miktarda veri veya yapılandırılmış depolama ortamına gerektirip gerektirmediğini sağlamış olursunuz, üye işlevi.

Gecikmeli işleme kullanmak için çağrı [DelayRenderData](#delayrenderdata) veya [DelayRenderFileData](#delayrenderfiledata) üye işlevi. MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme bkz [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).

Daha fazla bilgi için [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK'sındaki yapısı.

Daha fazla bilgi için [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK.

##  <a name="coledatasource"></a>  COleDataSource::COleDataSource

Oluşturur bir `COleDataSource` nesne.

```
COleDataSource();
```

##  <a name="delayrenderdata"></a>  COleDataSource::DelayRenderData

Veri aktarımı işlemleri sırasında veri sunulur bir biçimi belirtmek için bu işlevi çağırın.

```
void DelayRenderData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verileri sunmak için olduğu Pano biçimi. Bu parametre bir ön tanımlı Pano biçimlerini veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) işlevi.

*lpFormatEtc*<br/>
İşaret eden bir [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) veri olduğu sunulacak biçimini açıklayan yapısı. Pano biçimi tarafından belirtilen dışında ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer sağlamanız *cfFormat*. NULL ise, diğer alanları için varsayılan değerler kullanılır `FORMATETC` yapısı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, verileri hemen sağlanmazsa Gecikmeli işleme kullanarak verileri sağlar. [OnRenderData](#onrenderdata) veya [OnRenderGlobalData](#onrenderglobaldata) üye işlevi, veri istemek için çağrılır.

Verilerinizi aracılığıyla sağlamak kullanmayacaksanız bu işlevi kullanın. bir `CFile` nesne. Aracılığıyla veri sağlamak için kullanacaksanız bir `CFile` nesne, çağrı [DelayRenderFileData](#delayrenderfiledata) üye işlevi. MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme bkz [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).

Hemen işleme kullanmak için çağrı [CacheData](#cachedata) veya [CacheGlobalData](#cacheglobaldata) üye işlevi.

Daha fazla bilgi için [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK'sındaki yapısı.

Daha fazla bilgi için [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK.

##  <a name="delayrenderfiledata"></a>  COleDataSource::DelayRenderFileData

Veri aktarımı işlemleri sırasında veri sunulur bir biçimi belirtmek için bu işlevi çağırın.

```
void DelayRenderFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verileri sunmak için olduğu Pano biçimi. Bu parametre bir ön tanımlı Pano biçimlerini veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) işlevi.

*lpFormatEtc*<br/>
İşaret eden bir [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) veri olduğu sunulacak biçimini açıklayan yapısı. Pano biçimi tarafından belirtilen dışında ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer sağlamanız *cfFormat*. NULL ise, diğer alanları için varsayılan değerler kullanılır `FORMATETC` yapısı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, verileri hemen sağlanmazsa Gecikmeli işleme kullanarak verileri sağlar. [OnRenderFileData](#onrenderfiledata) üye işlevi, veri istemek için çağrılır.

Kullanmak için kullanacaksanız bu işlevi kullanın. bir `CFile` veri sağlamak için nesne. Kullanılacak kullanmayacaksanız bir `CFile` nesne, çağrı [DelayRenderData](#delayrenderdata) üye işlevi. MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme bkz [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).

Hemen işleme kullanmak için çağrı [CacheData](#cachedata) veya [CacheGlobalData](#cacheglobaldata) üye işlevi.

Daha fazla bilgi için [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK'sındaki yapısı.

Daha fazla bilgi için [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK.

##  <a name="delaysetdata"></a>  COleDataSource::DelaySetData

Veri kaynağı içeriğini değiştirilmesini desteklemesi için bu işlevi çağırın.

```
void DelaySetData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Veri yerleştirilecek olduğu Pano biçimi. Bu parametre bir ön tanımlı Pano biçimlerini veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) işlevi.

*lpFormatEtc*<br/>
İşaret eden bir [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) veri olduğu değiştirilecek biçimini açıklayan yapısı. Pano biçimi tarafından belirtilen dışında ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer sağlamanız *cfFormat*. NULL ise, diğer alanları için varsayılan değerler kullanılır `FORMATETC` yapısı.

### <a name="remarks"></a>Açıklamalar

[OnSetData](#onsetdata) böyle bir durumda framework tarafından çağırılır. Framework veri kaynağından döndürüldüğünde bu yalnızca kullanılır [COleServerItem::GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource). Varsa `DelaySetData` çağrılmaz, uygulamanızın `OnSetData` işlevi hiçbir zaman çağrılır. `DelaySetData` Her bir Pano için çağrılması gerektiğini veya `FORMATETC` desteklediğiniz biçimi.

Daha fazla bilgi için [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK'sındaki yapısı.

Daha fazla bilgi için [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) Windows SDK.

##  <a name="dodragdrop"></a>  COleDataSource::DoDragDrop

Çağrı `DoDragDrop` üye işlevi, bir Sürükle ve bırak işlemi bu veri kaynağı için genellikle gerçekleştirmek için bir [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) işleyici.

```
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,
    LPCRECT lpRectStartDrag = NULL,
    COleDropSource* pDropSource = NULL);
```

### <a name="parameters"></a>Parametreler

*dwEffects*<br/>
İzin verilen sürükle ve bırak işlemleri bu veri kaynağı. Bir veya daha fazlasını olabilir:

- DROPEFFECT_COPY kopyalama işlemi gerçekleştirilemedi.

- DROPEFFECT_MOVE taşıma işlemi gerçekleştirilemedi.

- Özgün veriler bırakılan verilerden DROPEFFECT_LINK bir bağlantı kurulamadı.

- DROPEFFECT_SCROLL sürükleme kaydırma işlemi oluşabilecek gösterir.

*lpRectStartDrag*<br/>
Sürükleme gerçekten başladığı tanımlar dikdörtgen işaretçisi. Daha fazla bilgi için aşağıdaki Açıklamalar bölümüne bakın.

*pDropSource*<br/>
Bir bırakma kaynağı işaret eder. Ardından varsayılan bir uygulama NULL [COleDropSource](../../mfc/reference/coledropsource-class.md) kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Sürükle ve bırak işlemi tarafından oluşturulan etkin bırakın; Sağlanan dikdörtgen ayrılmadan önce kullanıcının fare düğmesi serbest olduğundan işlemi hiçbir zaman başladığında aksi DROPEFFECT_NONE.

### <a name="remarks"></a>Açıklamalar

Sürükle ve bırak işlemi hemen başlamaz. Fare imlecini tarafından belirtilen dikdörtgen olana kadar bekler *lpRectStartDrag* veya kadar belirtilen sayıda milisaniye geçmiştir. Varsa *lpRectStartDrag* NULL ise bir piksel dikdörtgenin boyutudur.

Gecikme süresi, bir kayıt defteri anahtarı ayarı tarafından belirtilir. Gecikme süresini çağırarak değiştirebilirsiniz [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) veya [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Gecikme süresini belirtmezseniz varsayılan değeri 200 milisaniye olarak kullanılır. Sürükleme gecikme süresi gibi depolanır:

- Windows NT Sürükle gecikme süresi içinde HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay depolanır.

- Windows 3.x Sürükle gecikme süresi WIN depolanır. INI dosyası, [Windows} bölümünde.

- Windows 95/98 Sürükle gecikme süresi, WIN önbelleğe alınmış bir sürümünde depolanır. INI.

Gecikme bilgilerini sürükleyin hakkında daha fazla bilgi için her iki kayıt defterinde depolanır veya. INI dosyası bkz [WriteProfileString](/windows/desktop/api/winbase/nf-winbase-writeprofilestringa) Windows SDK.

Daha fazla bilgi için bkz [sürükle ve bırak: bir bırakma kaynağı uygulama](../../mfc/drag-and-drop-implementing-a-drop-source.md).

##  <a name="empty"></a>  COleDataSource::Empty

Boş için bu işlevi çağırın `COleDataSource` veri nesnesi.

```
void Empty();
```

### <a name="remarks"></a>Açıklamalar

Her ikisi de önbelleğe alınır ve bunların tekrar kullanılabilmesi için gecikme işleme biçimleri boşaltılıp.

Daha fazla bilgi için [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) Windows SDK.

##  <a name="flushclipboard"></a>  COleDataSource::FlushClipboard

Panoya ve ardından uygulamanızı kapandıktan sonra Pano'dan veri yapıştırma olanak tanır, verileri işler.

```
static void PASCAL FlushClipboard();
```

### <a name="remarks"></a>Açıklamalar

Kullanım [SetClipboard](#setclipboard) için verileri Pano'ya yerleştirin.

##  <a name="getclipboardowner"></a>  COleDataSource::GetClipboardOwner

Panodaki veriler bu yana değiştirilip değiştirilmediğini belirler [SetClipboard](#setclipboard) son çağrılır ve bu durumda, geçerli sahibi tanımlar.

```
static COleDataSource* PASCAL GetClipboardOwner();
```

### <a name="return-value"></a>Dönüş Değeri

Verileri Panoda şu anda kaynak, null veya yoksa hiçbir şey panoya veya çağıran uygulama tarafından panoya ait değil.

##  <a name="onrenderdata"></a>  COleDataSource::OnRenderData

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

Belirtilen biçim biridir daha önce bulundukları `COleDataSource` kullanarak nesne [DelayRenderData](#delayrenderdata) veya [DelayRenderFileData](#delayrenderfiledata) Gecikmeli işleme için üye işlevi. Bu işlev varsayılan uygulamasını çağıracak [OnRenderFileData](#onrenderfiledata) veya [OnRenderGlobalData](#onrenderglobaldata) sağlanan depolama ortamına bir dosya veya bellek, sırasıyla ise. Bu biçimler hiçbiri sağlanırsa, ardından varsayılan uygulama 0 döndürür ve hiçbir şey yapma. MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme bkz [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).

Varsa *lpStgMedium*-> *ortam türü* TYMED_NULL, olan `STGMEDIUM` tarafından belirtilen doldurulmuş ve ayrılan gerekir *lpFormatEtc -> ortam türü*. TYMED_NULL, değilse `STGMEDIUM` yerde verilerle doldurulması gerekir.

Bu gelişmiş bir, geçersiz kılınabilir. Bu işlev, Orta ve istenen biçimi verilerinizdeki sağlamak için geçersiz kılın. Verilerinizi bağlı olarak, bunun yerine bu işlevin diğer sürümlerden biri geçersiz kılmak isteyebilirsiniz. Verilerinizi, küçük ve sabit boyutu ise, geçersiz kılma `OnRenderGlobalData`. Verilerinizi bir dosyaya veya bir değişken boyutu, geçersiz kılma `OnRenderFileData`.

Daha fazla bilgi için [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) ve [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) yapıları [ortam türü](/windows/desktop/api/objidl/ne-objidl-tagtymed) numaralandırma türü ve [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) Windows SDK'sı.

##  <a name="onrenderfiledata"></a>  COleDataSource::OnRenderFileData

Belirtilen depolama ortamına bir dosya olduğunda belirtilen biçimden veri almak için framework tarafından çağırılır.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
İşaret [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) içinde bilgi istenen biçimi belirten yapısı.

*pFile*<br/>
İşaret eden bir [CFile](../../mfc/reference/cfile-class.md) veri olduğu işlenecek nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim biridir daha önce bulundukları `COleDataSource` kullanarak nesne [DelayRenderData](#delayrenderdata) Gecikmeli işleme için üye işlevi. Bu işlev varsayılan uygulaması yalnızca false değerini döndürür.

Bu gelişmiş bir, geçersiz kılınabilir. Bu işlev, Orta ve istenen biçimi verilerinizdeki sağlamak için geçersiz kılın. Verilerinizi bağlı olarak, bunun yerine, bu işlevin diğer sürümlerden biri geçersiz kılmak isteyebilirsiniz. Birden çok depolama medyası işlemek isterseniz, geçersiz kılma [OnRenderData](#onrenderdata). Verilerinizi bir dosyaya veya bir değişken boyutu, geçersiz kılma `OnRenderFileData`. MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme bkz [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).

Daha fazla bilgi için [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) yapısı ve [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) Windows SDK.

##  <a name="onrenderglobaldata"></a>  COleDataSource::OnRenderGlobalData

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
Genel bellek verileri döndürülecek olduğu için bir tanıtıcı işaret eder. Bir henüz ayrılmamış, bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim biridir daha önce bulundukları `COleDataSource` kullanarak nesne [DelayRenderData](#delayrenderdata) Gecikmeli işleme için üye işlevi. Bu işlev varsayılan uygulaması yalnızca false değerini döndürür.

Varsa *phGlobal* yeni HGLOBAL ayrılan verilecek ve döndürülen sonra NULL ise *phGlobal*. Aksi takdirde, tarafından belirtilen HGLOBAL *phGlobal* verilerle doldurulması gerekir. Geçerli bellek blok boyutu içinde HGLOBAL yerleştirilen veri miktarı aşmamalıdır. Ayrıca, daha büyük bir boyuta blok ayrılamaz.

Bu gelişmiş bir, geçersiz kılınabilir. Bu işlev, Orta ve istenen biçimi verilerinizdeki sağlamak için geçersiz kılın. Verilerinizi bağlı olarak, bunun yerine bu işlevin diğer sürümlerden biri geçersiz kılmak isteyebilirsiniz. Birden çok depolama medyası işlemek isterseniz, geçersiz kılma [OnRenderData](#onrenderdata). Verilerinizi bir dosyaya veya bir değişken boyutu, geçersiz kılma [OnRenderFileData](#onrenderfiledata). MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme bkz [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).

Daha fazla bilgi için [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) yapısı ve [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) Windows SDK.

##  <a name="onsetdata"></a>  COleDataSource::OnSetData

Ayarlanacak veya değiştirilecek verileri framework tarafından çağırılır `COleDataSource` belirtilen biçimde nesne.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
İşaret [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) yapısı içinde veri değiştirilir biçimini belirleme.

*lpStgMedium*<br/>
İşaret [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) geçerli içerikle değiştirecek verileri içeren yapı `COleDataSource` nesne.

*bRelease*<br/>
İşlev çağrısı tamamladıktan sonra depolama ortamı sahipliğini kimlerin gösterir. Çağıranın kimin adına depolama ortamına ayrılan kaynakları serbest bırakmak için sorumlu olduğunu belirler. Çağıranın bu ayarlayarak yapar *bRelease*. Varsa *bRelease* olan sıfır olmayan, veri kaynağını kullanan tamamlandığında ortam boşaltma, aittir. Zaman *bRelease* 0'dır, çağırana sahipliği korur ve veri kaynağı yalnızca çağrı süresi boyunca depolama ortamı kullanabilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bunu alınırken başarıyla kadar veri kaynağının veri sahipliğini almaz. Diğer bir deyişle, sahipliği varsa almaz `OnSetData` 0 döndürür. Veri kaynağı sahipliği alırsa, depolama ortamı çağırarak serbest bıraktığı [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) işlevi.

Varsayılan uygulama, hiçbir şey yapmaz. Bu işlev belirtilen biçiminde verileri değiştirmek için geçersiz kılın. Bu gelişmiş bir, geçersiz kılınabilir.

Daha fazla bilgi için [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) ve [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) yapıları ve [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) ve [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) Windows SDK'sındaki işlevleri.

##  <a name="setclipboard"></a>  COleDataSource::SetClipboard

İçerdiği veriler koyar `COleDataSource` aşağıdaki işlevlerin birini çağrıldıktan sonra Pano nesnesinde: [CacheData](#cachedata), [CacheGlobalData](#cacheglobaldata), [DelayRenderData](#delayrenderdata), veya [DelayRenderFileData](#delayrenderfiledata).

```
void SetClipboard();
```

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek HIERSVR](../../visual-cpp-samples.md)<br/>
[MFC örnek OCLIENT](../../visual-cpp-samples.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDataObject Sınıfı](../../mfc/reference/coledataobject-class.md)
