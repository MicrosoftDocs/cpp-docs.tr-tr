---
title: COleDataSource Sınıfı
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
ms.openlocfilehash: 8746be43e3f2a31558904323392983b183d4f198
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753903"
---
# <a name="coledatasource-class"></a>COleDataSource Sınıfı

Bir uygulamanın, Pano veya sürükle-bırak işlemleri gibi veri aktarım işlemleri sırasında sunacağı verileri yerleştirdiği bir önbellek görevi görür.

## <a name="syntax"></a>Sözdizimi

```
class COleDataSource : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleDataSource::COleDataSource](#coledatasource)|Bir `COleDataSource` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleDataSource::Önbellek Verileri](#cachedata)|Bir `STGMEDIUM` yapı kullanarak belirli bir biçimde veri sunar.|
|[COleDataSource::CacheGlobalData](#cacheglobaldata)|Bir HGLOBAL kullanarak belirli bir biçimde veri sunar.|
|[COleDataSource::DelayRenderData](#delayrenderdata)|Gecikmiş işlemeyi kullanarak verileri belirli bir biçimde sunar.|
|[COleDataSource::DelayRenderFileData](#delayrenderfiledata)|Verileri işaretçide `CFile` belirli bir biçimde sunar.|
|[COleDataSource::DelaySetData](#delaysetdata)|Desteklenen her biçim için çağrıda `OnSetData`bulunuldu.|
|[COleDataSource::DoDragDrop](#dodragdrop)|Bir veri kaynağıyla sürükle ve bırak işlemleri gerçekleştirir.|
|[COleDataSource::Boş](#empty)|Veri nesnesini `COleDataSource` boşaltır.|
|[COleDataSource::FlushClipboard](#flushclipboard)|Tüm verileri Pano'ya işler.|
|[COleDataSource::GetClipboardSahibi](#getclipboardowner)|Panoya yerleştirilen verilerin hala orada olduğunu doğrular.|
|[COleDataSource::OnRenderData](#onrenderdata)|Gecikmiş işlemenin bir parçası olarak verileri alır.|
|[COleDataSource::OnRenderFileData](#onrenderfiledata)|Gecikmiş işlemenin `CFile` bir parçası olarak verileri alır.|
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|Gecikmiş işlemenin bir parçası olarak verileri bir HGLOBAL'a alır.|
|[COleDataSource::OnSetData](#onsetdata)|`COleDataSource` Nesnedeki verileri değiştirmek için çağrıldı.|
|[COleDataSource::SetClipboard](#setclipboard)|Panoya `COleDataSource` bir nesne yerleştirir.|

## <a name="remarks"></a>Açıklamalar

Doğrudan OLE veri kaynakları oluşturabilirsiniz. Alternatif olarak, [COleClientItem](../../mfc/reference/coleclientitem-class.md) ve [COleServerItem](../../mfc/reference/coleserveritem-class.md) sınıfları, kendi `CopyToClipboard` ve `DoDragDrop` üye işlevlerine yanıt olarak OLE veri kaynakları oluşturur. Bkz. [COleServerItem::Kısa](../../mfc/reference/coleserveritem-class.md#copytoclipboard) bir açıklama için CopyToClipboard. İstemci `OnGetClipboardData` öğesi veya sunucu öğesi sınıfının üye işlevini geçersiz kılın ve bu aygıt `CopyToClipboard` veya `DoDragDrop` üye işlev için oluşturulan OLE veri kaynağındaki verilere ek Pano biçimleri ekleyin.

Bir aktarım için veri hazırlamak istediğinizde, bu sınıfın bir nesnesini oluşturmalı ve verileriniz için en uygun yöntemi kullanarak verilerinizi doldurmalısınız. Bir veri kaynağına takılma şekli, verilerin hemen (anında işleme) veya isteğe bağlı olarak (gecikmeli işleme) sağlanıp sağlanmadığından doğrudan etkilenir. Kullanılacak Pano biçimini (ve isteğe bağlı [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısını) geçirerek veri sağladığınız her Pano biçimi için [DelayRenderData'yı](#delayrenderdata)arayın.

Veri kaynakları ve veri aktarımı hakkında daha fazla bilgi için [Veri Nesneleri ve Veri Kaynakları (OLE) makalesine](../../mfc/data-objects-and-data-sources-ole.md)bakın. Buna ek olarak, makale [Pano Konular](../../mfc/clipboard.md) OLE Pano mekanizması açıklar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`COleDataSource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="coledatasourcecachedata"></a><a name="cachedata"></a>COleDataSource::Önbellek Verileri

Veri aktarım işlemleri sırasında verilerin sunulduğu bir biçim belirtmek için bu işlevi arayın.

```cpp
void CacheData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin sunulabilmek için pano biçimi. Bu parametre önceden tanımlanmış Pano biçimlerinden veya ana Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpStgMedium*<br/>
Belirtilen biçimdeki verileri içeren bir [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına işaret eder.

*lpFormatEtc*<br/>
Verilerin sunulabilmek için biçimini açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *cfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgileri belirtmek istiyorsanız bu parametre için bir değer sağlayın. NULL ise, `FORMATETC` yapıdaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu işlev, hemen işleme kullanarak sağladığından, verileri sağlamanız gerekir. Veriler gerekli olana kadar önbelleğe alındı.

Verileri [bir STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısı kullanarak verin. Sağladığınız veri `CacheGlobalData` miktarı bir HGLOBAL kullanarak verimli bir şekilde aktarılabilmek için yeterince küçükse, üye işlevini de kullanabilirsiniz.

Üyeye `CacheData` yapılan aramadan `lpFormatEtc` sonra ve *lpStgMedium'un* içeriği arayana değil, veri nesnesine aittir. `ptd`

Gecikmeli işlemeyi kullanmak için [DelayRenderData veya DelayRenderFileData](#delayrenderdata) üye işlevini arayın. [DelayRenderFileData](#delayrenderfiledata) MFC tarafından işlenen gecikmiş işleme hakkında daha fazla bilgi için [Bkz. Veri Nesneleri ve Veri Kaynakları: Manipülasyon.](../../mfc/data-objects-and-data-sources-manipulation.md)

Daha fazla bilgi için Windows SDK'daki [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) ve [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapılarına bakın.

Daha fazla bilgi için Windows SDK'daki [RegisterClipboardFormat'a](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bakın.

## <a name="coledatasourcecacheglobaldata"></a><a name="cacheglobaldata"></a>COleDataSource::CacheGlobalData

Veri aktarım işlemleri sırasında verilerin sunulduğu bir biçim belirtmek için bu işlevi arayın.

```cpp
void CacheGlobalData(
    CLIPFORMAT cfFormat,
    HGLOBAL hGlobal,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin sunulabilmek için pano biçimi. Bu parametre önceden tanımlanmış Pano biçimlerinden veya ana Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*Hglobal*<br/>
Belirtilen biçimdeki verileri içeren genel bellek bloğuna işle.

*lpFormatEtc*<br/>
Verilerin sunulabilmek için biçimini açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *cfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgileri belirtmek istiyorsanız bu parametre için bir değer sağlayın. NULL ise, `FORMATETC` yapıdaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu işlev, verileri anında işleme kullanarak sağlar, bu nedenle işlevi ararken verileri sağlamanız gerekir; veri gerekli olana kadar önbelleğe verilir. Büyük `CacheData` miktarda veri sağlıyorsanız veya yapılandırılmış bir depolama ortamına ihtiyaç duyuyorsanız üye işlevini kullanın.

Gecikmeli işlemeyi kullanmak için [DelayRenderData veya DelayRenderFileData](#delayrenderdata) üye işlevini arayın. [DelayRenderFileData](#delayrenderfiledata) MFC tarafından işlenen gecikmiş işleme hakkında daha fazla bilgi için [Bkz. Veri Nesneleri ve Veri Kaynakları: Manipülasyon.](../../mfc/data-objects-and-data-sources-manipulation.md)

Daha fazla bilgi için Windows SDK'daki [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına bakın.

Daha fazla bilgi için Windows SDK'daki [RegisterClipboardFormat'a](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bakın.

## <a name="coledatasourcecoledatasource"></a><a name="coledatasource"></a>COleDataSource::COleDataSource

Bir `COleDataSource` nesne inşa eder.

```
COleDataSource();
```

## <a name="coledatasourcedelayrenderdata"></a><a name="delayrenderdata"></a>COleDataSource::DelayRenderData

Veri aktarım işlemleri sırasında verilerin sunulduğu bir biçim belirtmek için bu işlevi arayın.

```cpp
void DelayRenderData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin sunulabilmek için pano biçimi. Bu parametre önceden tanımlanmış Pano biçimlerinden veya ana Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpFormatEtc*<br/>
Verilerin sunulabilmek için biçimini açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *cfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgileri belirtmek istiyorsanız bu parametre için bir değer sağlayın. NULL ise, `FORMATETC` yapıdaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu işlev, verileri gecikmeli işleme kullanarak sağlar, bu nedenle veriler hemen sağlanmaz. Verileri istemek için [OnRenderData](#onrenderdata) veya [OnRenderGlobalData](#onrenderglobaldata) üye işlevi çağrılır.

Verilerinizi bir `CFile` nesne üzerinden sağlamayacaksanız bu işlevi kullanın. Verileri bir `CFile` nesne üzerinden tedarik edecekseniz, [DelayRenderFileData](#delayrenderfiledata) üye işlevini arayın. MFC tarafından işlenen gecikmiş işleme hakkında daha fazla bilgi için [Bkz. Veri Nesneleri ve Veri Kaynakları: Manipülasyon.](../../mfc/data-objects-and-data-sources-manipulation.md)

Hemen işleme kullanmak için [CacheData](#cachedata) veya [CacheGlobalData](#cacheglobaldata) üye işlevini arayın.

Daha fazla bilgi için Windows SDK'daki [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına bakın.

Daha fazla bilgi için Windows SDK'daki [RegisterClipboardFormat'a](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bakın.

## <a name="coledatasourcedelayrenderfiledata"></a><a name="delayrenderfiledata"></a>COleDataSource::DelayRenderFileData

Veri aktarım işlemleri sırasında verilerin sunulduğu bir biçim belirtmek için bu işlevi arayın.

```cpp
void DelayRenderFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin sunulabilmek için pano biçimi. Bu parametre önceden tanımlanmış Pano biçimlerinden veya ana Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpFormatEtc*<br/>
Verilerin sunulabilmek için biçimini açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *cfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgileri belirtmek istiyorsanız bu parametre için bir değer sağlayın. NULL ise, `FORMATETC` yapıdaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu işlev, verileri gecikmeli işleme kullanarak sağlar, bu nedenle veriler hemen sağlanmaz. Verileri istemek için [OnRenderFileData](#onrenderfiledata) üye işlevi çağrılır.

Verileri sağlamak için bir `CFile` nesne kullanacaksanız bu işlevi kullanın. Bir `CFile` nesne kullanmayacaksanız, [DelayRenderData](#delayrenderdata) üye işlevini arayın. MFC tarafından işlenen gecikmiş işleme hakkında daha fazla bilgi için [Bkz. Veri Nesneleri ve Veri Kaynakları: Manipülasyon.](../../mfc/data-objects-and-data-sources-manipulation.md)

Hemen işleme kullanmak için [CacheData](#cachedata) veya [CacheGlobalData](#cacheglobaldata) üye işlevini arayın.

Daha fazla bilgi için Windows SDK'daki [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına bakın.

Daha fazla bilgi için Windows SDK'daki [RegisterClipboardFormat'a](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bakın.

## <a name="coledatasourcedelaysetdata"></a><a name="delaysetdata"></a>COleDataSource::DelaySetData

Veri kaynağının içeriğini değiştirmeyi desteklemek için bu işlevi arayın.

```cpp
void DelaySetData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parametreler

*cfFormat*<br/>
Verilerin yerleştirilmeye alındığı Pano biçimi. Bu parametre önceden tanımlanmış Pano biçimlerinden veya ana Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevi tarafından döndürülen değerden biri olabilir.

*lpFormatEtc*<br/>
Verilerin değiştirilme biçimini açıklayan bir [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder. *cfFormat*tarafından belirtilen Pano biçiminin ötesinde ek biçim bilgileri belirtmek istiyorsanız bu parametre için bir değer sağlayın. NULL ise, `FORMATETC` yapıdaki diğer alanlar için varsayılan değerler kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu durumda [OnSetData](#onsetdata) çerçeve tarafından çağrılacaktır. Bu yalnızca çerçeve COleServerItem veri kaynağını döndürdüğünde [kullanılır::GetDataSource.](../../mfc/reference/coleserveritem-class.md#getdatasource) `DelaySetData` Çağrılmazsa, işleviniz `OnSetData` asla çağrılmaz. `DelaySetData`desteklediğiniz her Pano veya `FORMATETC` biçim için çağrılmalıdır.

Daha fazla bilgi için Windows SDK'daki [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına bakın.

Daha fazla bilgi için Windows SDK'daki [RegisterClipboardFormat'a](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) bakın.

## <a name="coledatasourcedodragdrop"></a><a name="dodragdrop"></a>COleDataSource::DoDragDrop

Bu `DoDragDrop` veri kaynağı için genellikle [cwnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) işleyicisi bir sürükle ve bırak işlemi gerçekleştirmek için üye işlevi arayın.

```
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,
    LPCRECT lpRectStartDrag = NULL,
    COleDropSource* pDropSource = NULL);
```

### <a name="parameters"></a>Parametreler

*dwEfektler*<br/>
Bu veri kaynağında izin verilen sürükle ve bırak işlemleri. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_COPY Bir kopyalama işlemi gerçekleştirilebilir.

- DROPEFFECT_MOVE Bir hareket işlemi gerçekleştirilebilir.

- DROPEFFECT_LINK Bırakılan verilerden özgün verilere bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL Sürükle kaydırma işleminin oluşabileceğini gösterir.

*lpRectStartDrag*<br/>
Sürüklemenin gerçekte nerede başladığını tanımlayan dikdörtgeni işaretle. Daha fazla bilgi için aşağıdaki Açıklamalar bölümüne bakın.

*pDropSource*<br/>
Bir düşüş kaynağına işaret. NULL sonra [COleDropSource](../../mfc/reference/coledropsource-class.md) varsayılan bir uygulama kullanılacaktır.

### <a name="return-value"></a>Dönüş Değeri

Sürükle ve bırak işlemi tarafından oluşturulan bırakma efekti; kullanıcı sağlanan dikdörtgenayrılmadan önce fare düğmesini yayımladı çünkü işlem hiç başlamazsa aksi DROPEFFECT_NONE.

### <a name="remarks"></a>Açıklamalar

Sürükle ve bırak işlemi hemen başlamaz. Fare *imleci, lpRectStartDrag* tarafından belirtilen dikdörtgeni bırakana veya belirli sayıda milisaniye geçene kadar bekler. *lpRectStartDrag* NULL ise, dikdörtgenin boyutu bir pikseldir.

Gecikme süresi bir kayıt defteri anahtarı ayarı ile belirtilir. CWinApp'ı arayarak gecikme süresini [değiştirebilirsiniz::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) veya [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Gecikme süresini belirtmezseniz, varsayılan değeri 200 milisaniye olarak kullanılır. Sürükleme gecikme süresi aşağıdaki gibi depolanır:

- Windows NT Sürükle gecikme süresi HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay'da depolanır.

- Windows 3.x Sürükleme gecikme süresi WIN'de depolanır. INI dosyası, [Windows} bölümünün altında.

- Windows 95/98 Sürükleme gecikme süresi WIN'in önbelleğe alınmış sürümünde depolanır. ını.

Sürükleme gecikmesi bilgilerinin kayıt defterinde veya .' de nasıl depolandırılabilen hakkında daha fazla bilgi için. INI dosyası, Windows SDK'daki [WriteProfileString'e](/windows/win32/api/winbase/nf-winbase-writeprofilestringw) bakın.

Daha fazla bilgi için, makale [OLE sürükleyin ve bırakın](../../mfc/drag-and-drop-ole.md)bakın.

## <a name="coledatasourceempty"></a><a name="empty"></a>COleDataSource::Boş

Veri nesnesini `COleDataSource` boşaltmak için bu işlevi çağırın.

```cpp
void Empty();
```

### <a name="remarks"></a>Açıklamalar

Önbelleğe alınmış ve gecikme li render biçimleri yeniden kullanılabilecek şekilde boşaltılır.

Daha fazla bilgi için Windows SDK'daki [ReleaseStgMedium'a](/windows/win32/api/ole2/nf-ole2-releasestgmedium) bakın.

## <a name="coledatasourceflushclipboard"></a><a name="flushclipboard"></a>COleDataSource::FlushClipboard

Pano'daki verileri işler ve uygulamanız kapandıktan sonra Pano'dan veri yapıştırmamanızı sağlar.

```
static void PASCAL FlushClipboard();
```

### <a name="remarks"></a>Açıklamalar

Panoya veri koymak için [SetClipboard'u](#setclipboard) kullanın.

## <a name="coledatasourcegetclipboardowner"></a><a name="getclipboardowner"></a>COleDataSource::GetClipboardSahibi

[SetClipboard](#setclipboard) en son çağrıldığından beri Panodaki verilerin değişip değişmediğini belirler ve varsa geçerli sahibini tanımlar.

```
static COleDataSource* PASCAL GetClipboardOwner();
```

### <a name="return-value"></a>Dönüş Değeri

Pano'da şu anda bulunan veri kaynağı veya Pano'da hiçbir şey yoksa veya Pano arama uygulamasına ait değilse NULL.

## <a name="coledatasourceonrenderdata"></a><a name="onrenderdata"></a>COleDataSource::OnRenderData

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

Belirtilen biçim, gecikmiş işleme için `COleDataSource` DelayRenderData veya [DelayRenderFileData](#delayrenderfiledata) üye işlevini kullanarak nesneye daha önce yerleştirilen biçimdir. [DelayRenderData](#delayrenderdata) Sağlanan depolama ortamı sırasıyla bir dosya veya bellek ise, bu işlevin varsayılan uygulaması [OnRenderFileData](#onrenderfiledata) veya [OnRenderGlobalData](#onrenderglobaldata) çağırır. Bu biçimlerin hiçbiri sağlanmışsa, varsayılan uygulama 0 döndürecek ve hiçbir şey yapmaz. MFC tarafından işlenen gecikmiş işleme hakkında daha fazla bilgi için [Bkz. Veri Nesneleri ve Veri Kaynakları: Manipülasyon.](../../mfc/data-objects-and-data-sources-manipulation.md)

*lpStgMedium*-> *tymed* TYMED_NULL ise, `STGMEDIUM` *lpFormatEtc->tymed*tarafından belirtildiği şekilde tahsis edilmeli ve doldurulmalıdır. TYMED_NULL değilse, verilerle `STGMEDIUM` birlikte doldurulmalıdır.

Bu gelişmiş bir geçersiz. Verilerinizi istenen biçimde ve ortamda sağlamak için bu işlevi geçersiz kılın. Verilerinize bağlı olarak, bunun yerine bu işlevin diğer sürümlerinden birini geçersiz kılmak isteyebilirsiniz. Verileriniz küçükse ve boyutu sabitse, geçersiz kılın. `OnRenderGlobalData` Verileriniz bir dosyadaysa veya değişken boyuttaysa `OnRenderFileData`geçersiz kılın.

Daha fazla bilgi için [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) ve [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapıları, [TYMED](/windows/win32/api/objidl/ne-objidl-tymed) numaralandırma türü ve [IDataObject::Windows](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) SDK'daki Verileri alın.

## <a name="coledatasourceonrenderfiledata"></a><a name="onrenderfiledata"></a>COleDataSource::OnRenderFileData

Belirtilen depolama ortamı bir dosya olduğunda belirtilen biçimde veri almak için çerçeve tarafından çağrılır.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
Bilgilerin istendiği biçimi belirten [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder.

*pFile*<br/>
Verilerin oluşturulacak olduğu bir [CFile](../../mfc/reference/cfile-class.md) nesnesine işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim, gecikmiş işleme için `COleDataSource` [DelayRenderData](#delayrenderdata) üye işlevini kullanarak nesneye daha önce yerleştirilen biçimdir. Bu işlevin varsayılan uygulaması sadece FALSE döndürür.

Bu gelişmiş bir geçersiz. Verilerinizi istenen biçimde ve ortamda sağlamak için bu işlevi geçersiz kılın. Verilerinize bağlı olarak, bunun yerine bu işlevin diğer sürümlerinden birini geçersiz kılmak isteyebilirsiniz. Birden çok depolama ortamını işlemek istiyorsanız, [OnRenderData'yı](#onrenderdata)geçersiz kılın. Verileriniz bir dosyadaysa veya değişken boyuttaysa `OnRenderFileData`geçersiz kılın. MFC tarafından işlenen gecikmiş işleme hakkında daha fazla bilgi için [Bkz. Veri Nesneleri ve Veri Kaynakları: Manipülasyon.](../../mfc/data-objects-and-data-sources-manipulation.md)

Daha fazla bilgi için [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına ve [IDataObject::Windows](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) SDK'daki Verileri Alın.

## <a name="coledatasourceonrenderglobaldata"></a><a name="onrenderglobaldata"></a>COleDataSource::OnRenderGlobalData

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
Verilerin döndürülmek üzere olduğu genel belleğe işaret eder. Henüz tahsis edilmemişse, bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belirtilen biçim, gecikmiş işleme için `COleDataSource` [DelayRenderData](#delayrenderdata) üye işlevini kullanarak nesneye daha önce yerleştirilen biçimdir. Bu işlevin varsayılan uygulaması sadece FALSE döndürür.

*phGlobal* NULL ise, o zaman yeni bir HGLOBAL tahsis edilmeli ve *phGlobal*döndürülmelidir. Aksi takdirde, *phGlobal* tarafından belirtilen HGLOBAL verilerle doldurulmalıdır. HGLOBAL'a yerleştirilen veri miktarı bellek bloğunun geçerli boyutunu aşmamalıdır. Ayrıca, blok daha büyük bir boyuta yeniden tahsis edilemez.

Bu gelişmiş bir geçersiz. Verilerinizi istenen biçimde ve ortamda sağlamak için bu işlevi geçersiz kılın. Verilerinize bağlı olarak, bunun yerine bu işlevin diğer sürümlerinden birini geçersiz kılmak isteyebilirsiniz. Birden çok depolama ortamını işlemek istiyorsanız, [OnRenderData'yı](#onrenderdata)geçersiz kılın. Verileriniz bir dosyadaysa veya değişken boyutundaysa, [OnRenderFileData'yı](#onrenderfiledata)geçersiz kılın. MFC tarafından işlenen gecikmiş işleme hakkında daha fazla bilgi için [Bkz. Veri Nesneleri ve Veri Kaynakları: Manipülasyon.](../../mfc/data-objects-and-data-sources-manipulation.md)

Daha fazla bilgi için [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına ve [IDataObject::Windows](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) SDK'daki Verileri Alın.

## <a name="coledatasourceonsetdata"></a><a name="onsetdata"></a>COleDataSource::OnSetData

`COleDataSource` Belirtilen biçimde nesnedeki verileri ayarlamak veya değiştirmek için çerçeve tarafından çağrılır.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>Parametreler

*lpFormatEtc*<br/>
Verilerin değiştirildiği biçimi belirten [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapısına işaret eder.

*lpStgMedium*<br/>
Nesnenin geçerli içeriğini değiştirecek verileri içeren [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) yapısına işaret eder. `COleDataSource`

*bRelease*<br/>
İşlev çağrısını tamamladıktan sonra depolama ortamının sahipliğini kimde olduğunu gösterir. Arayan, depolama ortamı adına ayrılan kaynakların serbest bırakılmasından kimin sorumlu olduğuna karar verir. Arayan bunu *bRelease*ayarlayarak yapar. *bRelease* sıfır değilse, veri kaynağı sahipliğini alır ve kullanımı tamamlandığında ortamı serbest bırakarak. *bRelease* 0 olduğunda, arayan sahipliğini korur ve veri kaynağı depolama ortamını yalnızca arama süresince kullanabilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı, verileri başarıyla elde edene kadar sahiplenmez. Diğer bir se, 0 `OnSetData` döndürürse sahiplenmez. Veri kaynağı sahipliği alırsa, [ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) işlevini arayarak depolama ortamını serbest düşürür.

Varsayılan uygulama hiçbir şey yapmaz. Belirtilen biçimdeki verileri değiştirmek için bu işlevi geçersiz kılın. Bu gelişmiş bir geçersiz.

Daha fazla bilgi için [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) ve [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) yapıları ve [ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) ve [IDataObject::Windows](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) SDK'daki GetData işlevlerine bakın.

## <a name="coledatasourcesetclipboard"></a><a name="setclipboard"></a>COleDataSource::SetClipboard

Aşağıdaki işlevlerden birini `COleDataSource` aradıktan sonra nesnede bulunan verileri Panoya koyar: [CacheData](#cachedata), [CacheGlobalData,](#cacheglobaldata) [DelayRenderData](#delayrenderdata)veya [DelayRenderFileData](#delayrenderfiledata).

```cpp
void SetClipboard();
```

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDataObject Sınıfı](../../mfc/reference/coledataobject-class.md)
