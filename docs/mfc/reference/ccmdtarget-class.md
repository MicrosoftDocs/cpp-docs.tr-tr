---
title: CCmdTarget Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCmdTarget
- AFXWIN/CCmdTarget
- AFXWIN/CCmdTarget::CCmdTarget
- AFXWIN/CCmdTarget::BeginWaitCursor
- AFXWIN/CCmdTarget::DoOleVerb
- AFXWIN/CCmdTarget::EnableAutomation
- AFXWIN/CCmdTarget::EnableConnections
- AFXWIN/CCmdTarget::EnableTypeLib
- AFXWIN/CCmdTarget::EndWaitCursor
- AFXWIN/CCmdTarget::EnumOleVerbs
- AFXWIN/CCmdTarget::FromIDispatch
- AFXWIN/CCmdTarget::GetDispatchIID
- AFXWIN/CCmdTarget::GetIDispatch
- AFXWIN/CCmdTarget::GetTypeInfoCount
- AFXWIN/CCmdTarget::GetTypeInfoOfGuid
- AFXWIN/CCmdTarget::GetTypeLib
- AFXWIN/CCmdTarget::GetTypeLibCache
- AFXWIN/CCmdTarget::IsInvokeAllowed
- AFXWIN/CCmdTarget::IsResultExpected
- AFXWIN/CCmdTarget::OnCmdMsg
- AFXWIN/CCmdTarget::OnFinalRelease
- AFXWIN/CCmdTarget::RestoreWaitCursor
helpviewer_keywords:
- CCmdTarget [MFC], CCmdTarget
- CCmdTarget [MFC], BeginWaitCursor
- CCmdTarget [MFC], DoOleVerb
- CCmdTarget [MFC], EnableAutomation
- CCmdTarget [MFC], EnableConnections
- CCmdTarget [MFC], EnableTypeLib
- CCmdTarget [MFC], EndWaitCursor
- CCmdTarget [MFC], EnumOleVerbs
- CCmdTarget [MFC], FromIDispatch
- CCmdTarget [MFC], GetDispatchIID
- CCmdTarget [MFC], GetIDispatch
- CCmdTarget [MFC], GetTypeInfoCount
- CCmdTarget [MFC], GetTypeInfoOfGuid
- CCmdTarget [MFC], GetTypeLib
- CCmdTarget [MFC], GetTypeLibCache
- CCmdTarget [MFC], IsInvokeAllowed
- CCmdTarget [MFC], IsResultExpected
- CCmdTarget [MFC], OnCmdMsg
- CCmdTarget [MFC], OnFinalRelease
- CCmdTarget [MFC], RestoreWaitCursor
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
ms.openlocfilehash: 1ef7040f3be1e4c30a6dc19e6093727299c9f1c3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752718"
---
# <a name="ccmdtarget-class"></a>CCmdTarget Sınıfı

Microsoft Hazırlık Sınıfı Kitaplığı ileti-eş mimarisinin temel sınıfı.

## <a name="syntax"></a>Sözdizimi

```
class CCmdTarget : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CCmdTarget::CCmdHedef](#ccmdtarget)|Bir `CCmdTarget` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|İmleci kum saati imleci olarak görüntüler.|
|[CCmdTarget::DoOleVerb](#dooleverb)|OLE fiili tarafından belirtilen bir eylemin gerçekleştirilmeye neden olur.|
|[CCmdTarget::EnableAutomation](#enableautomation)|Nesne için OLE `CCmdTarget` otomasyonuna izin verir.|
|[CCmdTarget::Bağlantıları Etkinleştir](#enableconnections)|Bağlantı noktaları üzerinden olay ateşlemesağlar.|
|[CCmdTarget::EnableTypeLib](#enabletypelib)|Bir nesnenin tür kitaplığını etkinleştirir.|
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|Önceki imleç döner.|
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|Bir nesnenin OLE fiillerini obirikarlar.|
|[CCmdTarget::FromIDispatch](#fromidispatch)|İşaretçiyle ilişkili `CCmdTarget` nesneye `IDispatch` bir işaretçi döndürür.|
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|Birincil sevk arabirimi kimliğini alır.|
|[CCmdTarget::GetIDispatch](#getidispatch)|Bir işaretçiyi `IDispatch` nesneyle `CCmdTarget` ilişkili nesneye döndürür.|
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|Bir nesnenin sağladığı tür bilgi arabirimlerinin sayısını alır.|
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|Belirtilen GUID'e karşılık gelen tür açıklamasını alır.|
|[CCmdTarget::GetTypeLib](#gettypelib)|Bir tür kitaplığı için bir işaretçi alır.|
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|Tür kitaplığı önbelleğini alır.|
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|Otomasyon yöntemi çağırmayı sağlar.|
|[CCmdTarget::IsResultExpected](#isresultexpected)|Bir otomasyon işlevi bir değer döndürürse sıfırsız döndürür.|
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|Komut iletilerini yönlendirir ve gönderir.|
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|Son OLE başvurusu yayınlandıktan sonra temizler.|
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|Kum saati imlecini geri yükler.|

## <a name="remarks"></a>Açıklamalar

İleti eşlemi, komutları veya iletileri işlemek için yazdığınız üye işlevlere yönlendirir. (Komut, menü öğesi, komut düğmesi veya hızlandırıcı anahtarından gelen bir iletidir.)

CView, `CCmdTarget` [CWinApp,](../../mfc/reference/cwinapp-class.md) [CDocument,](../../mfc/reference/cdocument-class.md) [CWnd](../../mfc/reference/cwnd-class.md)ve [CFrameWnd'den](../../mfc/reference/cframewnd-class.md)türetilen temel çerçeve sınıfları. [CView](../../mfc/reference/cview-class.md) İletileri işlemek için yeni bir sınıf hedefliyorsanız, sınıfı bu `CCmdTarget`türetilmiş sınıflardan türetin. Nadiren `CCmdTarget` doğrudan bir sınıf türetmek olacaktır.

Komut hedeflerine ve `OnCmdMsg` yönlendirmeye genel bir bakış [Command Routing](../../mfc/command-routing.md)için [bkz.](../../mfc/command-targets.md) [Mapping Messages](../../mfc/mapping-messages.md)

`CCmdTarget`kum saati imlecinin görüntülenmesini sağlayan üye işlevleri içerir. Bir komutun yürütülmesi için fark edilir bir zaman aralığı almasını beklerken kum saati imlecini görüntüleyin.

İleti eşlemlerine benzer gönderi meşin haritaları, OLE otomasyon `IDispatch` işlevini ortaya çıkarmak için kullanılır. Bu arabirimi açığa çıkararak, diğer uygulamalar (Visual Basic gibi) uygulamanızı arayabilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CCmdTarget`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="ccmdtargetbeginwaitcursor"></a><a name="beginwaitcursor"></a>CCmdTarget::BeginWaitCursor

Bir komutun yürütülmesi için fark edilir bir zaman aralığı almasını beklerken imleci kum saati olarak görüntülemek için bu işlevi arayın.

```cpp
void BeginWaitCursor();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, kullanıcıya meşgul olduğunu göstermek için bu işlevi `CDocument` çağırır (örneğin, bir nesne yüklendiğinde veya kendisini bir dosyaya kaydeder.

İşleme `BeginWaitCursor` gibi `OnSetCursor` diğer eylemler imleci değiştirebileceğinden, eylemleri tek bir ileti işleyicisi dışında her zaman etkili değildir.

Önceki `EndWaitCursor` imleci geri yüklemek için arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="ccmdtargetccmdtarget"></a><a name="ccmdtarget"></a>CCmdTarget::CCmdHedef

Bir `CCmdTarget` nesne inşa eder.

```
CCmdTarget();
```

## <a name="ccmdtargetdooleverb"></a><a name="dooleverb"></a>CCmdTarget::DoOleVerb

OLE fiili tarafından belirtilen bir eylemin gerçekleştirilmeye neden olur.

```
BOOL DoOleVerb(
    LONG iVerb,
    LPMSG lpMsg,
    HWND hWndParent,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*iFiil*<br/>
Fiilin sayısal tanımlayıcısı.

*lpMsg*<br/>
Fiili çağıran olayı (çift tıklatma gibi) açıklayan [MSG](/windows/win32/api/winuser/ns-winuser-msg) yapısına işaretçi.

*hWndParent*<br/>
Nesneyi içeren belge penceresinin tutamacı.

*Lprect*<br/>
Bir nesnenin *hwndParent'de*sınırlayıcı dikdörtgenini tanımlayan koordinatları içeren [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU eğer başarılı, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev temelde [IOleObject bir uygulamadır::DoVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb). Olası eylemler [CCmdTarget tarafından numaralandırılır::EnumOleVerbs](#enumoleverbs).

## <a name="ccmdtargetenableautomation"></a><a name="enableautomation"></a>CCmdTarget::EnableAutomation

Bir nesne için OLE otomasyonunu etkinleştirmek için bu işlevi arayın.

```cpp
void EnableAutomation();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle nesnenizin oluşturucusundan çağrılır ve yalnızca sınıf için bir gönderme eşlemi bildirilmişse çağrılmalıdır. Otomasyon hakkında daha fazla bilgi için, [Otomasyon İstemcileri](../../mfc/automation-clients.md) ve [Otomasyon Sunucuları](../../mfc/automation-servers.md)makalelerine bakın.

## <a name="ccmdtargetenableconnections"></a><a name="enableconnections"></a>CCmdTarget::Bağlantıları Etkinleştir

Bağlantı noktaları üzerinden olay ateşlemesağlar.

```cpp
void EnableConnections();
```

### <a name="remarks"></a>Açıklamalar

Bağlantı noktalarını etkinleştirmek için, türemiş sınıfınızın oluşturucusunda bu üye işlevi arayın.

## <a name="ccmdtargetenabletypelib"></a><a name="enabletypelib"></a>CCmdTarget::EnableTypeLib

Bir nesnenin tür kitaplığını etkinleştirir.

```cpp
void EnableTypeLib();
```

### <a name="remarks"></a>Açıklamalar

Tür bilgileri sağlıyorsa, türetilmiş nesnenizin `CCmdTarget`oluşturucusunda bu üye işlevi çağırın.

## <a name="ccmdtargetendwaitcursor"></a><a name="endwaitcursor"></a>CCmdTarget::EndWaitCursor

Kum saati imlecinden `BeginWaitCursor` önceki imleçiçin dönmek için üye işlevi aradıktan sonra bu işlevi arayın.

```cpp
void EndWaitCursor();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, kum saati imlecini çağırdıktan sonra bu üye işlevi de çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="ccmdtargetenumoleverbs"></a><a name="enumoleverbs"></a>CCmdTarget::EnumOleVerbs

Bir nesnenin OLE fiillerini obirikarlar.

```
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```

### <a name="parameters"></a>Parametreler

*ppenumOleVerb*<br/>
[IEnumOLEVERB](/windows/win32/api/oleidl/nn-oleidl-ienumoleverb) arabirimine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer nesne en az bir OLE \* fiilini destekliyorsa (bu `IEnumOLEVERB` durumda *ppenumOleVerb* bir sayı arabirimine işaret ediyor), aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev temelde [IOleObject bir uygulamadır::EnumVerbs](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs).

## <a name="ccmdtargetfromidispatch"></a><a name="fromidispatch"></a>CCmdTarget::FromIDispatch

Bir sınıfın otomasyon `IDispatch` üye işlevlerinden alınan bir işaretçiyi `CCmdTarget` `IDispatch` nesnenin arabirimlerini uygulayan nesneye eşlemek için bu işlevi arayın.

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
Bir `IDispatch` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

*lpDispatch*ile `CCmdTarget` ilişkili nesneye bir işaretçi. `IDispatch` Nesne Microsoft Foundation Class `IDispatch` nesnesi olarak tanınmazsa, bu işlev NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlevin sonucu, üye işleviçin `GetIDispatch`bir çağrıters olduğunu.

## <a name="ccmdtargetgetdispatchiid"></a><a name="getdispatchiid"></a>CCmdTarget::GetDispatchIID

Birincil sevk arabirimi kimliğini alır.

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>Parametreler

*pIID*<br/>
Arabirim kimliğine işaretçi ([GUID](/windows/win32/api/guiddef/ns-guiddef-guid.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU eğer başarılı, aksi takdirde FALSE. Başarılı olursa, \* *pIID* birincil gönderme arabirimi kimliğine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Türetilen sınıflar bu üye işlevi geçersiz kılmalı `GetDispatchIID` (geçersiz kılınmışsa, FALSE döndürür). [Bkz. COleControl](../../mfc/reference/colecontrol-class.md).

## <a name="ccmdtargetgetidispatch"></a><a name="getidispatch"></a>CCmdTarget::GetIDispatch

İşaretçiyi `IDispatch` bir `IDispatch` işaretçi döndüren veya başvuruyla işaretçi `IDispatch` alan bir otomasyon yönteminden işaretçi almak için bu üye işlevi arayın.

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>Parametreler

*bAddRef*<br/>
Nesne için başvuru sayısını artımlı olarak belirtin.

### <a name="return-value"></a>Dönüş Değeri

Nesneyle `IDispatch` ilişkili işaretçi.

### <a name="remarks"></a>Açıklamalar

Oluşturucularını çağıran `EnableAutomation` ve otomasyonu etkinleştiren nesneler için bu işlev, `IDispatch` `IDispatch` arabirim üzerinden iletişim kuran istemciler tarafından kullanılan Hazırlık Sınıfı uygulamasına bir işaretçi döndürür. Bu işlevi aramak otomatik olarak işaretçiye bir başvuru ekler, bu nedenle [IUnknown::AddRef'e](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)arama yapmak gerekli değildir.

## <a name="ccmdtargetgettypeinfocount"></a><a name="gettypeinfocount"></a>CCmdTarget::GetTypeInfoCount

Bir nesnenin sağladığı tür bilgi arabirimlerinin sayısını alır.

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tür bilgi arabirimlerinin sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi temelde [IDispatch uygular::GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount).

Türetilen sınıflar, sağlanan tür bilgi arabirimleri (0 veya 1) sayısını döndürmek için bu işlevi geçersiz kılmalıdır. Geçersiz kılınmış değilse, `GetTypeInfoCount` 0 döndürür. Geçersiz kılmak için, [aynı](../../mfc/reference/type-library-access.md#implement_oletypelib) zamanda uygular `GetTypeLib` ve `GetTypeLibCache`IMPLEMENT_OLETYPELIB makro kullanın.

## <a name="ccmdtargetgettypeinfoofguid"></a><a name="gettypeinfoofguid"></a>CCmdTarget::GetTypeInfoOfGuid

Belirtilen GUID'e karşılık gelen tür açıklamasını alır.

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>Parametreler

*lcid*<br/>
Yerel tanımlayıcı ( `LCID`).

*Guıd*<br/>
[GUID](/windows/win32/api/guiddef/ns-guiddef-guid of the type description.

*ppTypeInfo*<br/>
Arabirimi işaretçisi. `ITypeInfo`

### <a name="return-value"></a>Dönüş Değeri

Aramanın başarısını veya başarısızlığını gösteren bir HRESULT. Başarılı olursa, \* *ppTypeInfo* tür bilgi arabirimine işaret ediyor.

## <a name="ccmdtargetgettypelib"></a><a name="gettypelib"></a>CCmdTarget::GetTypeLib

Bir tür kitaplığı için bir işaretçi alır.

```
virtual HRESULT GetTypeLib(
    LCID lcid,
    LPTYPELIB* ppTypeLib);
```

### <a name="parameters"></a>Parametreler

*lcid*<br/>
Yerel bir tanımlayıcı (LCID).

*ppTypeLib*<br/>
`ITypeLib` Arabirimi için bir işaretçi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Aramanın başarısını veya başarısızlığını gösteren bir HRESULT. Başarılı olursa, \* *ppTypeLib* tür kitaplığı arabirimini işaret eder.

### <a name="remarks"></a>Açıklamalar

Türetilen sınıflar bu üye işlevi geçersiz kılmalı `GetTypeLib` (geçersiz kılınmazsa, TYPE_E_CANTLOADLIBRARY döndürür). [Aynı](../../mfc/reference/type-library-access.md#implement_oletypelib) zamanda uygular `GetTypeInfoCount` ve `GetTypeLibCache`IMPLEMENT_OLETYPELIB makro, kullanın.

## <a name="ccmdtargetgettypelibcache"></a><a name="gettypelibcache"></a>CCmdTarget::GetTypeLibCache

Tür kitaplığı önbelleğini alır.

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CTypeLibCache` nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Türetilen sınıflar bu üye işlevi geçersiz kılmalı `GetTypeLibCache` (geçersiz kılındıysa, NULL döndürür). [Aynı](../../mfc/reference/type-library-access.md#implement_oletypelib) zamanda uygular `GetTypeInfoCount` ve `GetTypeLib`IMPLEMENT_OLETYPELIB makro, kullanın.

## <a name="ccmdtargetisinvokeallowed"></a><a name="isinvokeallowed"></a>CCmdTarget::IsInvokeAllowed

Bu işlev, MFC'nin belirli `IDispatch::Invoke` bir otomasyon yönteminin *(dispid*tarafından tanımlanan) çağrılabilir olup olmadığını belirlemek için uygulanması ile çağrılır.

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>Parametreler

*Dıspıd*<br/>
Sevk kimliği.

### <a name="return-value"></a>Dönüş Değeri

Doğru yöntem çağrılabilir, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

TRUE `IsInvokeAllowed` döndürürse, `Invoke` yöntemi aramak için ilerler; aksi `Invoke` takdirde, E_UNEXPECTED dönen, başarısız olur.

Türetilen sınıflar uygun değerleri döndürmek için bu işlevi geçersiz `IsInvokeAllowed` kılabilir (geçersiz kılınmış değilse, TRUE döndürür). Bkz. özellikle [COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).

## <a name="ccmdtargetisresultexpected"></a><a name="isresultexpected"></a>CCmdTarget::IsResultExpected

İstemcinin çağrısından bir otomasyon işlevine iade değeri beklep beklemediğini belirlemek için kullanın. `IsResultExpected`

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>Dönüş Değeri

Bir otomasyon işlevi bir değer döndürmelidir sıfır; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

OLE arabirimi, istemcinin bir işlev çağrısının sonucunu kullanıp kullanmadığı veya yoksaymadığı hakkında MFC'ye bilgi sağlar `IsResultExpected`ve MFC de bu bilgileri bir çağrının sonucunu belirlemek için kullanır. İade değerinin üretimi zaman veya kaynak yoğunsa, iade değerini hesaplamadan önce bu işlevi arayarak verimliliği artırabilirsiniz.

Bu işlev, istemcinin çağırdığı otomasyon işlevinden ararsanız diğer otomasyon işlevlerinden geçerli iade değerlerini almak için yalnızca bir kez 0 döndürür.

`IsResultExpected`otomasyon işlevi çağrısı devam etmiyorsa çağrıldığında sıfır olmayan bir değer döndürür.

## <a name="ccmdtargetoncmdmsg"></a><a name="oncmdmsg"></a>CCmdTarget::OnCmdMsg

Komut iletilerini yönlendirmek ve göndermek ve komut kullanıcı arabirimi nesnelerinin güncelleştirmesini işlemek için çerçeve tarafından çağrılır.

```
virtual BOOL OnCmdMsg(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Komut kimliğini içerir.

*Ncode*<br/>
Komut bildirim kodunu tanımlar. *nCode*değerleri hakkında daha fazla bilgi için **Açıklamalar'a** bakın.

*pEkstra*<br/>
*nCode*değerine göre kullanılır. *pExtra*hakkında daha fazla bilgi için **Açıklamalar'a** bakın.

*pHandlerInfo*<br/>
NULL değilse, `OnCmdMsg` komutu göndermek yerine *pHandlerInfo* yapısının *pTarget* ve *PMF* üyelerini doldurur. Genellikle, bu parametre NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu, çerçeve komut mimarisinin ana uygulama yordamıdır.

Çalışma zamanında, `OnCmdMsg` diğer nesnelere bir komut gönderir veya kök sınıfını `CCmdTarget::OnCmdMsg`arayarak komutun kendisini işler, bu da gerçek ileti-eş aramayı yapar. Varsayılan komut yönlendirmesinin tam açıklaması için [İleti İşleme ve Eşleme Konuları](../../mfc/message-handling-and-mapping.md)bölümüne bakın.

Nadir durumlarda, çerçevenin standart komut yönlendirmesini genişletmek için bu üye işlevi geçersiz kılmak isteyebilirsiniz. Komut yönlendirme mimarisinin gelişmiş ayrıntıları için [Teknik Not 21'e](../../mfc/tn021-command-and-message-routing.md) bakın.

Geçersiz `OnCmdMsg`kılarsanız, *nCode*için uygun değeri sağlamanız gerekir , komut bildirim kodu, ve *pExtra*, *nCode*değerine bağlıdır . Aşağıdaki tabloda karşılık gelen değerleri listelenebvardır:

|*nKod* değeri|*pEkstra* değer|
|-------------------|--------------------|
|CN_COMMAND|[Ccmduı](../../mfc/reference/ccmdui-class.md)\*|
|CN_EVENT|AFX_EVENT\*|
|CN_UPDATE_COMMAND_UI|Ccmduı\*|
|CN_OLECOMMAND|[Colecmduı](../../mfc/reference/colecmdui-class.md)\*|
|CN_OLE_UNREGISTER|NULL|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]

## <a name="ccmdtargetonfinalrelease"></a><a name="onfinalrelease"></a>CCmdTarget::OnFinalRelease

Nesneye veya nesneye son OLE başvurusu serbest bırakıldığında çerçeve tarafından çağrılır.

```
virtual void OnFinalRelease();
```

### <a name="remarks"></a>Açıklamalar

Bu durum için özel işleme sağlamak için bu işlevi geçersiz kılın. Varsayılan uygulama nesneyi siler.

## <a name="ccmdtargetrestorewaitcursor"></a><a name="restorewaitcursor"></a>CCmdTarget::RestoreWaitCursor

Sistem imleci değiştikten sonra uygun kum saati imlecini geri yüklemek için bu işlevi arayın (örneğin, uzun bir işlemin ortasındayken bir ileti kutusu açılıp kapandıktan sonra).

```cpp
void RestoreWaitCursor();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek ACDUAL](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdUI Sınıfı](../../mfc/reference/ccmdui-class.md)<br/>
[Kişniş Sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CWinApp Sınıfı](../../mfc/reference/cwinapp-class.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[COleDispatchDriver Sınıfı](../../mfc/reference/coledispatchdriver-class.md)
