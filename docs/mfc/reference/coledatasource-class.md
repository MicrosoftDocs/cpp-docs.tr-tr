---
title: Cotadatasource sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 5cd573590bc1adb303e0b4c5cd600b9fa6c685b2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127861"
---
# <a name="coledatasource-class"></a>Cotadatasource sınıfı

, Bir uygulamanın pano veya sürükle ve bırak işlemleri gibi veri aktarımı işlemleri sırasında sunabileceği verileri yerleştirdiği bir önbellek gibi davranır.

## <a name="syntax"></a>Sözdizimi

```
class COleDataSource : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cotadatasource:: Cotadatasource](#coledatasource)|`COleDataSource` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotadatasource:: CacheData](#cachedata)|`STGMEDIUM` yapısını kullanarak verileri belirtilen biçimde sunar.|
|[Cotadatasource:: CacheGlobalData](#cacheglobaldata)|Verileri bir HGLOBAL kullanarak belirtilen biçimde sunar.|
|[Cotadatasource::D elayRenderData](#delayrenderdata)|Gecikmeli işleme kullanarak verileri belirtilen biçimde sunar.|
|[Cotadatasource::D elayRenderFileData](#delayrenderfiledata)|`CFile` İşaretçisinde verileri belirtilen biçimde sunar.|
|[Cotadatasource::D elaySetData](#delaysetdata)|`OnSetData`desteklenen her biçim için çağırılır.|
|[Cotadatasource::D oDragDrop](#dodragdrop)|Bir veri kaynağıyla sürükle ve bırak işlemleri gerçekleştirir.|
|[Cotadatasource:: Empty](#empty)|Verilerin `COleDataSource` nesnesini boşaltır.|
|[Cotadatasource:: FlushClipboard](#flushclipboard)|Tüm verileri panoya işler.|
|[Cotadatasource:: GetClipboardOwner](#getclipboardowner)|Panoya yerleştirilmiş verilerin hala orada bulunduğunu doğrular.|
|[Cotadatasource:: OnRenderData](#onrenderdata)|Verileri gecikmeli işlemenin bir parçası olarak alır.|
|[Cotadatasource:: OnRenderFileData](#onrenderfiledata)|Verileri gecikmeli işlemenin bir parçası olarak bir `CFile` alır.|
|[Cotadatasource:: OnRenderGlobalData](#onrenderglobaldata)|Gecikmeli işleme kapsamında verileri bir HGLOBAL 'e alır.|
|[Cotadatasource:: OnSetData](#onsetdata)|`COleDataSource` nesnesindeki verileri değiştirmek için çağırılır.|
|[Cotadatasource:: SetClipboard](#setclipboard)|Panoya bir `COleDataSource` nesnesi yerleştirir.|

## <a name="remarks"></a>Açıklamalar

Doğrudan OLE veri kaynakları oluşturabilirsiniz. Alternatif olarak, [Colet clientıtem](../../mfc/reference/coleclientitem-class.md) ve [Copaserveritem](../../mfc/reference/coleserveritem-class.md) sınıfları, `CopyToClipboard` ve `DoDragDrop` üye işlevlerine yanıt olarak OLE veri kaynakları oluşturur. Kısa bir açıklama için bkz. [Coelserverıtem:: CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard) . `CopyToClipboard` veya `DoDragDrop` üye işlevi için oluşturulan OLE veri kaynağındaki verilere ek Pano biçimleri eklemek için istemci öğe veya sunucu öğesi sınıfınızın `OnGetClipboardData` üye işlevini geçersiz kılın.

Bir aktarım için veri hazırlamak istediğinizde, bu sınıfın bir nesnesini oluşturmanız ve verileriniz için en uygun yöntemi kullanarak verilerinize doldurmanız gerekir. Verilerin hemen (anında işleme) ya da isteğe bağlı (Gecikmeli işleme) olarak sağlanmasıyla, bir veri kaynağına eklenme şekli doğrudan etkilenir. Pano biçimini kullanılacak şekilde geçirerek (ve isteğe bağlı [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısı) veri sağlayan her Pano biçimi Için, [DelayRenderData](#delayrenderdata)' ı çağırın.

Veri kaynakları ve veri aktarımı hakkında daha fazla bilgi için bkz. [veri nesneleri ve veri kaynakları (OLE)](../../mfc/data-objects-and-data-sources-ole.md). Buna ek olarak, [Pano konuları](../../mfc/clipboard.md) başlıklı OLE panosu mekanizması açıklanmaktadır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDataSource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

##  <a name="cachedata"></a>Cotadatasource:: CacheData

Veri aktarım işlemleri sırasında verilerin sunulduğu bir biçim belirtmek için bu işlevi çağırın.

```
void CacheData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin sunulacağı Pano biçimi. Bu parametre, önceden tanımlanmış Pano biçimlerinden biri veya yerel Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*Lpstgorta*<br/>
Verileri belirtilen biçimde içeren bir [Stgorta](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına işaret eder.

*lpFormatEtc*<br/>
Verilerin sunulacağı biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *CfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer girin. NULL ise, `FORMATETC` yapısındaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu işlev, anında işleme kullanarak bunu sağladığından verileri sağlamalısınız. Veriler, gerekli olana kadar önbelleğe alınır.

Verileri bir [Stgmedium](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısı kullanarak sağlayın. Ayrıca, Aradığınız veri miktarı bir HGLOBAL kullanılarak etkin bir şekilde aktarılmayacak kadar küçükse, `CacheGlobalData` üye işlevini de kullanabilirsiniz.

`lpFormatEtc` `ptd` üyesini `CacheData` çağrının ve *lpStgMedium* içeriğinin, çağıran tarafından değil, veri nesnesi tarafından sahiplenildiğinden sonra.

Gecikmeli işleme kullanmak için [DelayRenderData](#delayrenderdata) veya [DelayRenderFileData](#delayrenderfiledata) üye işlevini çağırın. MFC tarafından işlenmiş şekilde gecikmeli işleme hakkında daha fazla bilgi için [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md)makalesine bakın.

Daha fazla bilgi için Windows SDK bkz. [Stgmedium](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) ve [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapıları.

Daha fazla bilgi için Windows SDK [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bölümüne bakın.

##  <a name="cacheglobaldata"></a>Cotadatasource:: CacheGlobalData

Veri aktarım işlemleri sırasında verilerin sunulduğu bir biçim belirtmek için bu işlevi çağırın.

```
void CacheGlobalData(
    CLIPFORMAT cfFormat,
    HGLOBAL hGlobal,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin sunulacağı Pano biçimi. Bu parametre, önceden tanımlanmış Pano biçimlerinden biri veya yerel Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*hGlobal*<br/>
Verileri belirtilen biçimde içeren genel bellek bloğunun tanıtıcısı.

*lpFormatEtc*<br/>
Verilerin sunulacağı biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *CfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer girin. NULL ise, `FORMATETC` yapısındaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu işlev, verileri anında işleme kullanarak sağlar; bu nedenle, işlevi çağırırken verileri sağlamalısınız; veriler, gerekli olana kadar önbelleğe alınır. Büyük miktarda veri tedarik ediyorsanız veya yapılandırılmış bir depolama ortamı gerekiyorsa `CacheData` üye işlevini kullanın.

Gecikmeli işleme kullanmak için [DelayRenderData](#delayrenderdata) veya [DelayRenderFileData](#delayrenderfiledata) üye işlevini çağırın. MFC tarafından işlenmiş şekilde gecikmeli işleme hakkında daha fazla bilgi için [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md)makalesine bakın.

Daha fazla bilgi için Windows SDK [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına bakın.

Daha fazla bilgi için Windows SDK [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bölümüne bakın.

##  <a name="coledatasource"></a>Cotadatasource:: Cotadatasource

`COleDataSource` nesnesi oluşturur.

```
COleDataSource();
```

##  <a name="delayrenderdata"></a>Cotadatasource::D elayRenderData

Veri aktarım işlemleri sırasında verilerin sunulduğu bir biçim belirtmek için bu işlevi çağırın.

```
void DelayRenderData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin sunulacağı Pano biçimi. Bu parametre, önceden tanımlanmış Pano biçimlerinden biri veya yerel Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpFormatEtc*<br/>
Verilerin sunulacağı biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *CfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer girin. NULL ise, `FORMATETC` yapısındaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu işlev gecikmeli işleme kullanarak verileri sağlar, bu nedenle veriler hemen sağlanmaz. Veri istemek için [OnRenderData](#onrenderdata) veya [OnRenderGlobalData](#onrenderglobaldata) üye işlevi çağırılır.

Verilerinizi bir `CFile` nesnesi üzerinden sağlayacaksanız bu işlevi kullanın. Verileri bir `CFile` nesnesi üzerinden sağlayacaksanız [DelayRenderFileData](#delayrenderfiledata) üye işlevini çağırın. MFC tarafından işlenmiş şekilde gecikmeli işleme hakkında daha fazla bilgi için [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md)makalesine bakın.

Anında işlemeyi kullanmak için [CacheData](#cachedata) veya [CacheGlobalData](#cacheglobaldata) üye işlevini çağırın.

Daha fazla bilgi için Windows SDK [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına bakın.

Daha fazla bilgi için Windows SDK [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bölümüne bakın.

##  <a name="delayrenderfiledata"></a>Cotadatasource::D elayRenderFileData

Veri aktarım işlemleri sırasında verilerin sunulduğu bir biçim belirtmek için bu işlevi çağırın.

```
void DelayRenderFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin sunulacağı Pano biçimi. Bu parametre, önceden tanımlanmış Pano biçimlerinden biri veya yerel Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpFormatEtc*<br/>
Verilerin sunulacağı biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *CfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer girin. NULL ise, `FORMATETC` yapısındaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu işlev gecikmeli işleme kullanarak verileri sağlar, bu nedenle veriler hemen sağlanmaz. [OnRenderFileData](#onrenderfiledata) üye işlevi, verileri istemek için çağrılır.

Verileri sağlamak için bir `CFile` nesnesi kullanacaksanız, bu işlevi kullanın. `CFile` nesne kullanacaksanız, [DelayRenderData](#delayrenderdata) üye işlevini çağırın. MFC tarafından işlenmiş şekilde gecikmeli işleme hakkında daha fazla bilgi için [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md)makalesine bakın.

Anında işlemeyi kullanmak için [CacheData](#cachedata) veya [CacheGlobalData](#cacheglobaldata) üye işlevini çağırın.

Daha fazla bilgi için Windows SDK [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına bakın.

Daha fazla bilgi için Windows SDK [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bölümüne bakın.

##  <a name="delaysetdata"></a>Cotadatasource::D elaySetData

Veri kaynağının içeriğini değiştirmeyi desteklemek için bu işlevi çağırın.

```
void DelaySetData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin yerleştirileceği Pano biçimi. Bu parametre, önceden tanımlanmış Pano biçimlerinden biri veya yerel Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpFormatEtc*<br/>
Verilerin değiştirildiği biçimi açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *CfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgilerini belirtmek istiyorsanız bu parametre için bir değer girin. NULL ise, `FORMATETC` yapısındaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu gerçekleştiğinde [OnSetData](#onsetdata) Framework tarafından çağırılır. Bu yalnızca Framework [Copaserverıtem:: GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource)öğesinden veri kaynağını döndürdüğünde kullanılır. `DelaySetData` çağrılmadıysa, `OnSetData` işleviniz hiçbir şekilde çağırılmaz. `DelaySetData`, destekettiğiniz her Pano veya `FORMATETC` biçimi için çağrılmalıdır.

Daha fazla bilgi için Windows SDK [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına bakın.

Daha fazla bilgi için Windows SDK [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bölümüne bakın.

##  <a name="dodragdrop"></a>Cotadatasource::D oDragDrop

Genellikle bir [CWnd:: Onlbuttonaþaðý](../../mfc/reference/cwnd-class.md#onlbuttondown) Handler içinde bu veri kaynağı için sürükle ve bırak işlemi gerçekleştirmek üzere `DoDragDrop` member işlevini çağırın.

```
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,
    LPCRECT lpRectStartDrag = NULL,
    COleDropSource* pDropSource = NULL);
```

### <a name="parameters"></a>Parametreler

*dwEffects*<br/>
Bu veri kaynağında izin verilen sürükle ve bırak işlemleri. Aşağıdakilerden biri veya daha fazlası olabilir:

- Kopyalama işlemi DROPEFFECT_COPY gerçekleştirilemiyor.

- Taşıma işlemi DROPEFFECT_MOVE gerçekleştirilemiyor.

- Bırakılan verilerden özgün verilere bir bağlantı DROPEFFECT_LINK kurulacaktır.

- DROPEFFECT_SCROLL, bir sürükleme kaydırma işleminin oluşabileceği anlamına gelir.

*lpRectStartDrag*<br/>
Sürüklediğiniz yerin gerçekten başladığı dikdörtgeni tanımlayan dikdörtgen işaretçisi. Daha fazla bilgi için aşağıdaki Açıklamalar bölümüne bakın.

*pDropSource*<br/>
Bırakma kaynağını işaret eder. NULL ise [COleDropSource](../../mfc/reference/coledropsource-class.md) 'un varsayılan bir kopyası kullanılacaktır.

### <a name="return-value"></a>Dönüş Değeri

Sürükle ve bırak işlemi tarafından oluşturulan bırakma efekti; Aksi takdirde, Kullanıcı, sağlanan dikdörtgenden çıkmadan önce fare düğmesini yayımladığından, işlem hiçbir şekilde başlamadıysa DROPEFFECT_NONE.

### <a name="remarks"></a>Açıklamalar

Sürükle ve bırak işlemi hemen başlamaz. Fare imleci, *lpRectStartDrag* tarafından belirtilen dikdörtgenden ayrılana veya belirtilen sayıda milisaniyeye geçene kadar bekler. *LpRectStartDrag* null ise, dikdörtgenin boyutu bir piksel olur.

Gecikme süresi bir kayıt defteri anahtarı ayarıyla belirtilir. , [CWinApp:: WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) veya [CWinApp:: writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)çağırarak gecikme süresini değiştirebilirsiniz. Gecikme süresini belirtmezseniz, varsayılan 200 milisaniyelik bir değer kullanılır. Sürükleme gecikmesi süresi şu şekilde depolanır:

- Windows NT sürükleme gecikmesi süresi HKEY_LOCAL_MACHINE \Software\microsoft\windows\nt\currentversion\ınıfilemapping\win.exe dizininde depolanır.

- Windows 3. x sürükleme gecikmesi süresi WIN 'da depolanır. INı dosyası, [Windows} bölümü altında.

- Windows 95/98 sürükleme gecikmesi süresi, WIN 'ın önbelleğe alınmış bir sürümünde depolanıyor. Dosyası.

Sürükleme gecikmesi bilgilerinin kayıt defterinde veya ' de nasıl depolandığını hakkında daha fazla bilgi için. INı dosyası, Windows SDK bkz. [WriteProfileString](/windows/win32/api/winbase/nf-winbase-writeprofilestringw) .

Daha fazla bilgi için [OLE sürükle ve bırak](../../mfc/drag-and-drop-ole.md)makalesine bakın.

##  <a name="empty"></a>Cotadatasource:: Empty

Verilerin `COleDataSource` nesnesini boşaltmak için bu işlevi çağırın.

```
void Empty();
```

### <a name="remarks"></a>Açıklamalar

Hem önbelleğe alınmış hem de gecikmeli işleme biçimleri yeniden kullanılabilmesi için boşaltılır.

Daha fazla bilgi için Windows SDK [ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) bölümüne bakın.

##  <a name="flushclipboard"></a>Cotadatasource:: FlushClipboard

Panodaki verileri işler ve sonra uygulamanız kapandıktan sonra panodaki verileri yapıştırmanıza olanak tanır.

```
static void PASCAL FlushClipboard();
```

### <a name="remarks"></a>Açıklamalar

Panodaki verileri yerleştirmek için [SetClipboard](#setclipboard) 'u kullanın.

##  <a name="getclipboardowner"></a>Cotadatasource:: GetClipboardOwner

[SetClipboard](#setclipboard) 'un son çağrılmasından bu yana panodaki verilerin değişip değişmediğini belirler ve varsa, geçerli sahibini tanımlar.

```
static COleDataSource* PASCAL GetClipboardOwner();
```

### <a name="return-value"></a>Dönüş Değeri

Panodaki veri kaynağı veya Pano üzerinde hiçbir şey yoksa ya da Pano çağıran uygulamaya ait değilse NULL.

##  <a name="onrenderdata"></a>Cotadatasource:: OnRenderData

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

Belirtilen biçim, Gecikmeli işleme için [DelayRenderData](#delayrenderdata) veya [DelayRenderFileData](#delayrenderfiledata) üye işlevi kullanılarak `COleDataSource` nesnesine daha önce yerleştirilmiş bir biçimdir. Sağlanan depolama ortamı sırasıyla bir dosya veya bellek ise, bu işlevin varsayılan uygulanması [OnRenderFileData](#onrenderfiledata) veya [OnRenderGlobalData](#onrenderglobaldata) ' ı çağırır. Bu biçimlerin hiçbiri sağlanmazsa, varsayılan uygulama 0 döndürür ve hiçbir şey yapmaz. MFC tarafından işlenmiş şekilde gecikmeli işleme hakkında daha fazla bilgi için [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md)makalesine bakın.

*Lpstgorta*-> *tymed* TYMED_NULL, `STGMEDIUM`, *lpformatetc-> TYMED*tarafından belirtilen şekilde ayrılmalı ve doldurulmalıdır. TYMED_NULL değilse, `STGMEDIUM` verilerle birlikte doldurulmalıdır.

Bu gelişmiş bir geçersiz kılınabilir. Verilerinizi istenen biçimde ve ortamda sağlamak için bu işlevi geçersiz kılın. Verilerinize bağlı olarak, bunun yerine bu işlevin diğer sürümlerinden birini geçersiz kılmak isteyebilirsiniz. Verileriniz küçük ve boyut olarak sabitlenmiştir `OnRenderGlobalData`geçersiz kılın. Verileriniz bir dosya veya değişken boyutda ise `OnRenderFileData`geçersiz kılın.

Daha fazla bilgi için bkz. [Stgmedium](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) ve [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapıları, [tymed](/windows/win32/api/objidl/ne-objidl-tymed) numaralandırma [türü ve Windows SDK](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) .

##  <a name="onrenderfiledata"></a>Cotadatasource:: OnRenderFileData

Belirtilen depolama ortamı bir dosya olduğunda, belirtilen biçimdeki verileri almak için Framework tarafından çağırılır.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
Bilgilerin istendiği biçimi belirten [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder.

*pFile*<br/>
Verilerin işlendiği bir [CFile](../../mfc/reference/cfile-class.md) nesnesine işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim, Gecikmeli işleme için [DelayRenderData](#delayrenderdata) üye işlevi kullanılarak `COleDataSource` nesnesine daha önce yerleştirilmiş bir biçimdir. Bu işlevin varsayılan uygulanması yalnızca FALSE değerini döndürür.

Bu gelişmiş bir geçersiz kılınabilir. Verilerinizi istenen biçimde ve ortamda sağlamak için bu işlevi geçersiz kılın. Verilerinize bağlı olarak, bunun yerine bu işlevin diğer sürümlerinden birini geçersiz kılmak isteyebilirsiniz. Birden çok depolama ortamını işlemek istiyorsanız [OnRenderData](#onrenderdata)öğesini geçersiz kılın. Verileriniz bir dosya veya değişken boyutda ise `OnRenderFileData`geçersiz kılın. MFC tarafından işlenmiş şekilde gecikmeli işleme hakkında daha fazla bilgi için [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md)makalesine bakın.

Daha fazla bilgi için Windows SDK [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına ve [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) ' na bakın.

##  <a name="onrenderglobaldata"></a>Cotadatasource:: OnRenderGlobalData

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
Verilerin döndürüleceği genel belleğe yönelik bir tanıtıcıya işaret eder. Henüz ayrılmadıysa, bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim, Gecikmeli işleme için [DelayRenderData](#delayrenderdata) üye işlevi kullanılarak `COleDataSource` nesnesine daha önce yerleştirilmiş bir biçimdir. Bu işlevin varsayılan uygulanması yalnızca FALSE değerini döndürür.

*PhGlobal* değeri null ise, yenı bır hglobalin ayrılmalı ve *phGlobal*'te döndürülmelidir. Aksi takdirde, *phGlobal* tarafından belirtilen HGLOBAL, verilerle doldurulmalıdır. HGLOBAL 'e yerleştirilmiş veri miktarı, bellek bloğunun geçerli boyutunu aşmamalıdır. Ayrıca, blok daha büyük bir boyuta yeniden ayrılamaz.

Bu gelişmiş bir geçersiz kılınabilir. Verilerinizi istenen biçimde ve ortamda sağlamak için bu işlevi geçersiz kılın. Verilerinize bağlı olarak, bunun yerine bu işlevin diğer sürümlerinden birini geçersiz kılmak isteyebilirsiniz. Birden çok depolama ortamını işlemek istiyorsanız [OnRenderData](#onrenderdata)öğesini geçersiz kılın. Verileriniz bir dosya veya değişken boyutda ise, [OnRenderFileData](#onrenderfiledata)öğesini geçersiz kılın. MFC tarafından işlenmiş şekilde gecikmeli işleme hakkında daha fazla bilgi için [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md)makalesine bakın.

Daha fazla bilgi için Windows SDK [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına ve [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) ' na bakın.

##  <a name="onsetdata"></a>Cotadatasource:: OnSetData

`COleDataSource` nesnesindeki verileri belirtilen biçimde ayarlamak veya değiştirmek için Framework tarafından çağırılır.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
Verilerin değiştirildiği biçimi belirten [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder.

*Lpstgorta*<br/>
`COleDataSource` nesnesinin geçerli içeriklerinin yerini alacak olan verileri içeren [Stgorta](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına işaret eder.

*bRelease*<br/>
İşlev çağrısını tamamladıktan sonra kimin depolama ortamının sahipliğini olduğunu gösterir. Çağıran, depolama ortamı adına ayrılan kaynakları serbest bırakmaktan sorumlu kişiye karar veriyor. Çağıran bunu *bRelease*'i ayarlayarak yapar. *BRelease* sıfırdan farklı ise, veri kaynağı sahiplik alır ve onu kullanmayı bitirdiğinde ortamı serbest bırakır. *BRelease* 0 olduğunda, çağıran sahipliği korur ve veri kaynağı depolama ortamını yalnızca çağrının süresi boyunca kullanabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı, verileri başarıyla edinene kadar verilerin sahipliğini almaz. Diğer bir deyişle, `OnSetData` 0 döndürürse sahiplik almaz. Veri kaynağı sahiplik alırsa, [ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) işlevini çağırarak depolama ortamını serbest bırakır.

Varsayılan uygulama hiçbir şey yapmaz. Belirtilen biçimdeki verileri değiştirmek için bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz kılınabilir.

Daha fazla bilgi için Windows SDK [Stgmedium](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) ve [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapıları ve [ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) ve [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) işlevlerine bakın.

##  <a name="setclipboard"></a>Cotadatasource:: SetClipboard

Aşağıdaki işlevlerden birini çağırdıktan sonra panodaki `COleDataSource` nesnesine dahil edilen verileri koyar: [CacheData](#cachedata), [CacheGlobalData](#cacheglobaldata), [DelayRenderData](#delayrenderdata)veya [DelayRenderFileData](#delayrenderfiledata).

```
void SetClipboard();
```

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDataObject Sınıfı](../../mfc/reference/coledataobject-class.md)
