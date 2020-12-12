---
description: 'Daha fazla bilgi edinin: CCmdTarget sınıfı'
title: CCmdTarget sınıfı
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
ms.openlocfilehash: c4a579c0f224913cf47f332382fb71c12bdac755
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133022"
---
# <a name="ccmdtarget-class"></a>CCmdTarget sınıfı

Microsoft Foundation Class Kitaplığı ileti eşleme mimarisine yönelik temel sınıf.

## <a name="syntax"></a>Syntax

```
class CCmdTarget : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCmdTarget:: CCmdTarget](#ccmdtarget)|Bir `CCmdTarget` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCmdTarget:: BeginWaitCursor](#beginwaitcursor)|İmleci bir kum saati imleci olarak görüntüler.|
|[CCmdTarget::D Ootaverb](#dooleverb)|OLE fiili tarafından belirtilen bir eylemin gerçekleştirilmesine neden olur.|
|[CCmdTarget:: EnableAutomation](#enableautomation)|Nesne için OLE otomasyonuna izin verir `CCmdTarget` .|
|[CCmdTarget:: EnableConnections](#enableconnections)|Bağlantı noktaları üzerinde olay tetiklemenize izin vermez.|
|[CCmdTarget:: EnableTypeLib](#enabletypelib)|Bir nesnenin tür kitaplığını etkinleştirilir.|
|[CCmdTarget:: EndWaitCursor](#endwaitcursor)|Önceki imlece döner.|
|[CCmdTarget:: EnumOleVerbs](#enumoleverbs)|Bir nesnenin OLE fiillerini numaralandırır.|
|[CCmdTarget:: FromIDispatch](#fromidispatch)|`CCmdTarget`İşaretçiyle ilişkili nesneye bir işaretçi döndürür `IDispatch` .|
|[CCmdTarget:: GetDispatchIID](#getdispatchiid)|Birincil dağıtım arabirim KIMLIĞINI alır.|
|[CCmdTarget:: GetIDispatch](#getidispatch)|`IDispatch`Nesneyle ilişkili nesneye bir işaretçi döndürür `CCmdTarget` .|
|[CCmdTarget:: GetTypeInfoCount](#gettypeinfocount)|Bir nesnenin sağladığı tür bilgisi arabirimlerinin sayısını alır.|
|[CCmdTarget:: GetTypeInfoOfGuid](#gettypeinfoofguid)|Belirtilen GUID 'ye karşılık gelen tür açıklamasını alır.|
|[CCmdTarget:: GetTypeLib](#gettypelib)|Bir tür kitaplığına yönelik bir işaretçi alır.|
|[CCmdTarget:: GetTypeLibCache](#gettypelibcache)|Tür kitaplığı önbelleğini alır.|
|[CCmdTarget:: IsInvokeAllowed](#isinvokeallowed)|Otomasyon yöntemi çağrısını mümkün.|
|[CCmdTarget:: ısresultexyted](#isresultexpected)|Bir Automation işlevinin bir değer döndürmesi gerekiyorsa sıfır olmayan bir değer döndürür.|
|[CCmdTarget:: OnCmdMsg](#oncmdmsg)|Komut iletilerini yönlendirir ve dağıtır.|
|[CCmdTarget:: OnFinalRelease](#onfinalrelease)|Son OLE başvurusu serbest bırakıldıktan sonra temizler.|
|[CCmdTarget:: RestoreWaitCursor](#restorewaitcursor)|Kum saati imlecini geri yükler.|

## <a name="remarks"></a>Açıklamalar

İleti eşleme komutları veya iletileri, bunları işlemek için yazdığınız üye işlevlerine yönlendirir. (Komut bir menü öğesi, komut düğmesi veya hızlandırıcı anahtarından bir iletidir.)

`CCmdTarget` [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md)ve [CFrameWnd](../../mfc/reference/cframewnd-class.md)dahil öğesinden türetilmiş anahtar çerçevesi sınıfları. İletileri işlemek için yeni bir sınıf istiyorsanız, bu türetilmiş sınıflardan birindeki sınıfı türetirsiniz `CCmdTarget` . Genellikle doğrudan bir sınıf türetirsiniz `CCmdTarget` .

Komut hedefleri ve yönlendirmeye genel bir bakış için `OnCmdMsg` bkz. [komut hedefleri](../../mfc/command-targets.md), [komut yönlendirme](../../mfc/command-routing.md)ve [eşleme iletileri](../../mfc/mapping-messages.md).

`CCmdTarget` kum saati imlecinin görüntülenmesini işleyen üye işlevlerini içerir. Bir komutun yürütülmesi için dikkat çekici bir zaman aralığı almayı düşünüyorsanız kum saati imlecini görüntüleyin.

İleti eşlemleriyle benzer olan dağıtım haritaları, OLE Otomasyonu işlevlerini göstermek için kullanılır `IDispatch` . Bu arabirimi kullanıma sunarak diğer uygulamalar (örneğin, Visual Basic) uygulamanıza çağırabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CCmdTarget`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="ccmdtargetbeginwaitcursor"></a><a name="beginwaitcursor"></a> CCmdTarget:: BeginWaitCursor

Komutun yürütülmesi için dikkat çekici bir zaman aralığı almayı beklemeniz durumunda imleci bir kum saati olarak göstermek için bu işlevi çağırın.

```cpp
void BeginWaitCursor();
```

### <a name="remarks"></a>Açıklamalar

Framework, bir `CDocument` nesnenin kendisini bir dosyaya yüklediğinde veya kaydettiğinde olduğu gibi, meşgul olduğunu kullanıcıya göstermek için bu işlevi çağırır.

Eylemleri, `BeginWaitCursor` işleme gibi diğer eylemler, imleci değiştiremediğinden, her zaman tek bir ileti işleyicisinin dışında etkili değildir `OnSetCursor` .

`EndWaitCursor`Önceki imleci geri yüklemek için çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="ccmdtargetccmdtarget"></a><a name="ccmdtarget"></a> CCmdTarget:: CCmdTarget

Bir `CCmdTarget` nesnesi oluşturur.

```
CCmdTarget();
```

## <a name="ccmdtargetdooleverb"></a><a name="dooleverb"></a> CCmdTarget::D Ootaverb

OLE fiili tarafından belirtilen bir eylemin gerçekleştirilmesine neden olur.

```
BOOL DoOleVerb(
    LONG iVerb,
    LPMSG lpMsg,
    HWND hWndParent,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*ıverb*<br/>
Fiilin sayısal tanımlayıcısı.

*lpMsg*<br/>
Fiili çağıran olayı (çift tıklama gibi) açıklayan [msg](/windows/win32/api/winuser/ns-winuser-msg) yapısına yönelik işaretçi.

*hWndParent*<br/>
Nesneyi içeren belge penceresinin tutamacı.

*lpRect*<br/>
*HwndParent* içinde bir nesnenin sınırlayıcı dikdörtgenini tanımlayan koordinatları içeren [dikdörtgen](/windows/win32/api/windef/ns-windef-rect) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE, aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi temel olarak bir [IOleObject uygulamasıdır::D oVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb). Olası eylemler [CCmdTarget:: EnumOleVerbs](#enumoleverbs)tarafından numaralandırılır.

## <a name="ccmdtargetenableautomation"></a><a name="enableautomation"></a> CCmdTarget:: EnableAutomation

Bir nesne için OLE Otomasyonu 'nu etkinleştirmek için bu işlevi çağırın.

```cpp
void EnableAutomation();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle nesnenizin oluşturucusundan çağrılır ve yalnızca sınıf için bir dağıtım eşlemesi bildirilirse çağrılmalıdır. Otomasyon hakkında daha fazla bilgi için bkz. Makale [Otomasyonu istemcileri](../../mfc/automation-clients.md) ve [Otomasyon sunucuları](../../mfc/automation-servers.md).

## <a name="ccmdtargetenableconnections"></a><a name="enableconnections"></a> CCmdTarget:: EnableConnections

Bağlantı noktaları üzerinde olay tetiklemenize izin vermez.

```cpp
void EnableConnections();
```

### <a name="remarks"></a>Açıklamalar

Bağlantı noktalarını etkinleştirmek için, türetilmiş sınıfınızın oluşturucusunda Bu üye işlevini çağırın.

## <a name="ccmdtargetenabletypelib"></a><a name="enabletypelib"></a> CCmdTarget:: EnableTypeLib

Bir nesnenin tür kitaplığını etkinleştirilir.

```cpp
void EnableTypeLib();
```

### <a name="remarks"></a>Açıklamalar

`CCmdTarget`Tür bilgilerini sağlıyorsa türetilmiş nesnenizin oluşturucusunda Bu üye işlevini çağırın.

## <a name="ccmdtargetendwaitcursor"></a><a name="endwaitcursor"></a> CCmdTarget:: EndWaitCursor

Bu işlevi, `BeginWaitCursor` kum saati imlecini önceki imlece döndürmek için üye işlevini çağırdıktan sonra çağırın.

```cpp
void EndWaitCursor();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, bu üye işlevini, kum saati imlecini çağırdıktan sonra da çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="ccmdtargetenumoleverbs"></a><a name="enumoleverbs"></a> CCmdTarget:: EnumOleVerbs

Bir nesnenin OLE fiillerini numaralandırır.

```
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```

### <a name="parameters"></a>Parametreler

*ppenumOleVerb*<br/>
[IEnumOLEVERB](/windows/win32/api/oleidl/nn-oleidl-ienumoleverb) arabirimine yönelik işaretçiye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Nesne en az bir OLE fiilini destekliyorsa (Bu durumda \* *ppenumOleVerb* bir `IEnumOLEVERB` Numaralandırıcı arabirimine işaret ediyorsa), aksi takdirde yanlış olur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi temelde bir [IOleObject:: EnumVerbs](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs)uygulamasıdır.

## <a name="ccmdtargetfromidispatch"></a><a name="fromidispatch"></a> CCmdTarget:: FromIDispatch

`IDispatch`Bir sınıfın Otomasyon üye işlevlerinden alınan bir işaretçiyi `CCmdTarget` nesnenin arabirimlerini uygulayan nesneye eşlemek için bu işlevi çağırın `IDispatch` .

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
Bir `IDispatch` nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

`CCmdTarget` *LpDispatch* ile ilişkili nesneye yönelik bir işaretçi. Bu işlev, `IDispatch` nesne Microsoft Foundation Class nesnesi olarak TANıNMıYORSA null değerini döndürür `IDispatch` .

### <a name="remarks"></a>Açıklamalar

Bu işlevin sonucu, üye işlevine yapılan çağrının tersidir `GetIDispatch` .

## <a name="ccmdtargetgetdispatchiid"></a><a name="getdispatchiid"></a> CCmdTarget:: GetDispatchIID

Birincil dağıtım arabirim KIMLIĞINI alır.

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>Parametreler

*Piıd*<br/>
Arabirim KIMLIĞINE yönelik bir işaretçi (bir [GUID] (/Windows/Win32/api/Guiddef/NS-Guiddef-Guid.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE, aksi durumda FALSE. Başarılı olursa, \* *pIID* BIRINCIL dağıtım arabirimi kimliği olarak ayarlanır.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflar bu üye işlevini geçersiz kılmalıdır (geçersiz kılınmamışsa, `GetDispatchIID` false döndürür). Bkz. [Coelcontrol](../../mfc/reference/colecontrol-class.md).

## <a name="ccmdtargetgetidispatch"></a><a name="getidispatch"></a> CCmdTarget:: GetIDispatch

`IDispatch`Bir `IDispatch` işaretçi döndüren veya başvuruya göre işaretçi alan bir Otomasyon yönteminden işaretçiyi almak için bu üye işlevini çağırın `IDispatch` .

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>Parametreler

*bAddRef*<br/>
Nesnenin başvuru sayısının arttırılıp artırılmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

`IDispatch`Nesneyle ilişkili işaretçi.

### <a name="remarks"></a>Açıklamalar

Oluşturucularını çağıran nesneler için, `EnableAutomation` Otomasyonu etkin hale getirerek bu işlev, `IDispatch` arabirimi aracılığıyla iletişim kuran istemciler tarafından kullanılan temel sınıf uygulamasına bir işaretçi döndürür `IDispatch` . Bu işlevi çağırmak işaretçiye otomatik olarak bir başvuru ekler, bu nedenle [IUnknown:: AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)çağrısı yapmak gerekli değildir.

## <a name="ccmdtargetgettypeinfocount"></a><a name="gettypeinfocount"></a> CCmdTarget:: GetTypeInfoCount

Bir nesnenin sağladığı tür bilgisi arabirimlerinin sayısını alır.

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tür bilgisi arabirimlerinin sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, temel olarak [IDispatch:: GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount)uygular.

Türetilmiş sınıflar, sunulan tür bilgisi arabirimlerinin sayısını (0 veya 1) döndürmek için bu işlevi geçersiz kılmalıdır. Geçersiz kılınmamışsa `GetTypeInfoCount` 0 döndürür. Geçersiz kılmak için, ve de uygulayan [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) makrosunu kullanın `GetTypeLib` `GetTypeLibCache` .

## <a name="ccmdtargetgettypeinfoofguid"></a><a name="gettypeinfoofguid"></a> CCmdTarget:: GetTypeInfoOfGuid

Belirtilen GUID 'ye karşılık gelen tür açıklamasını alır.

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>Parametreler

*lcid*<br/>
Yerel ayar tanımlayıcısı ( `LCID` ).

*guid*<br/>
[GUID] (tür açıklaması/Windows/Win32/api/Guiddef/NS-Guiddef-Guid.

*ppTypeInfo*<br/>
Arabirim işaretçisinin işaretçisi `ITypeInfo` .

### <a name="return-value"></a>Dönüş Değeri

Çağrının başarısını veya başarısızlığını gösteren bir HRESULT. Başarılı olursa, \* *ppTypeInfo* tür bilgisi arabirimine işaret eder.

## <a name="ccmdtargetgettypelib"></a><a name="gettypelib"></a> CCmdTarget:: GetTypeLib

Bir tür kitaplığına yönelik bir işaretçi alır.

```
virtual HRESULT GetTypeLib(
    LCID lcid,
    LPTYPELIB* ppTypeLib);
```

### <a name="parameters"></a>Parametreler

*lcid*<br/>
Bir yerel ayar tanıtıcısı (LCıD).

*ppTypeLib*<br/>
Arabirim işaretçisinin işaretçisi `ITypeLib` .

### <a name="return-value"></a>Dönüş Değeri

Çağrının başarısını veya başarısızlığını gösteren bir HRESULT. Başarılı olursa, \* *ppTypeLib* tür kitaplığı arabirimine işaret eder.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflar bu üye işlevini geçersiz kılmalıdır (geçersiz kılınmamışsa, `GetTypeLib` TYPE_E_CANTLOADLIBRARY döndürür). Ve de uygulayan [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) makrosunu kullanın `GetTypeInfoCount` `GetTypeLibCache` .

## <a name="ccmdtargetgettypelibcache"></a><a name="gettypelibcache"></a> CCmdTarget:: GetTypeLibCache

Tür kitaplığı önbelleğini alır.

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CTypeLibCache` nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflar bu üye işlevini geçersiz kılmalıdır (geçersiz kılınmamışsa, `GetTypeLibCache` null döndürür). Ve de uygulayan [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) makrosunu kullanın `GetTypeInfoCount` `GetTypeLib` .

## <a name="ccmdtargetisinvokeallowed"></a><a name="isinvokeallowed"></a> CCmdTarget:: IsInvokeAllowed

Bu işlev, `IDispatch::Invoke` belirli bir Otomasyon yönteminin ( *DISPID* tarafından tanımlanan) çağrılabilir olup OLMADıĞıNı anlamak için MFC 'nin uygulamasının uygulamasına göre çağrılır.

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
Bir dağıtım KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Yöntem çağrlanacaksa TRUE, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

`IsInvokeAllowed`True değerini döndürürse `Invoke` yöntemi çağırmaya devam eder; Aksi takdirde, `Invoke` E_UNEXPECTED döndürülüyor.

Türetilmiş sınıflar, uygun değerleri döndürmek için bu işlevi geçersiz kılabilir (geçersiz kılınmamışsa, `IsInvokeAllowed` true döndürür). Bkz. belirli [Coelcontrol:: IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).

## <a name="ccmdtargetisresultexpected"></a><a name="isresultexpected"></a> CCmdTarget:: ısresultexyted

`IsResultExpected`Bir istemcinin bir Otomasyon işlevine çağrısından bir dönüş değeri bekleip bekmeyeceğini belirlemek için kullanın.

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>Dönüş Değeri

Bir Otomasyon işlevinin bir değer döndürmesi gerekiyorsa sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

OLE arabirimi, istemcinin bir işlev çağrısının sonucunu kullanıp kullanmadığını ya da yok saymadığını, MFC 'ye bilgi sağlar ve sırasıyla MFC bu bilgileri bir çağrının sonucunu belirlemede kullanır `IsResultExpected` . Dönüş değerinin üretimi zaman veya Kaynak yoğunluklu ise, dönüş değerini hesaplamadan önce bu işlevi çağırarak verimliliği artırabilirsiniz.

Bu işlev yalnızca bir kez 0 döndürür, bu sayede diğer otomasyon işlevlerindeki geçerli dönüş değerlerini istemcinin çağırdığı Otomasyon işlevinden çağırabilirsiniz.

`IsResultExpected` bir Otomasyon işlevi çağrısı devam ederken çağrılırsa sıfır dışında bir değer döndürür.

## <a name="ccmdtargetoncmdmsg"></a><a name="oncmdmsg"></a> CCmdTarget:: OnCmdMsg

Komut iletilerini yönlendirmek ve göndermek ve komut Kullanıcı arabirimi nesnelerinin güncelleştirmesini işlemek için Framework tarafından çağırılır.

```
virtual BOOL OnCmdMsg(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Komut KIMLIĞINI içerir.

*nCode*<br/>
Komut bildirim kodunu tanımlar. *NCode* değerleri hakkında daha fazla bilgi için bkz. **açıklamalar** .

*pExtra*<br/>
*NCode* değerine göre kullanılır. *PExtra* hakkında daha fazla bilgi için bkz. **açıklamalar** .

*pHandlerInfo*<br/>
NULL değilse, `OnCmdMsg` komutu dağıtmadan *pHandlerInfo* yapısının *pTarget* ve *PMF* üyelerini doldurur. Genellikle, bu parametre NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu, Framework komut mimarisinin ana uygulama yordamlamasıdır.

Çalışma zamanında, `OnCmdMsg` diğer nesnelere bir komut gönderir veya `CCmdTarget::OnCmdMsg` asıl ileti eşleme aramasını yapan kök sınıfını çağırarak komutun kendisini işler. Varsayılan komut yönlendirmesinin tamamen açıklaması için bkz. [Ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).

Nadir durumlarda, çerçevenin standart komut yönlendirmesini genişletmek için bu üye işlevini geçersiz kılmak isteyebilirsiniz. Komut yönlendirme mimarisinin gelişmiş ayrıntıları için bkz. [teknik notta 21](../../mfc/tn021-command-and-message-routing.md) .

Geçersiz kıldıysanız `OnCmdMsg` *nCode*, komut bildirim kodu ve *nCode* değerine bağlı olan *pExtra* için uygun değeri sağlamanız gerekir. Aşağıdaki tabloda karşılık gelen değerleri listelenmektedir:

|*nCode* değeri|*pExtra* değeri|
|-------------------|--------------------|
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)\*|
|CN_EVENT|AFX_EVENT\*|
|CN_UPDATE_COMMAND_UI|CCmdUI\*|
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)\*|
|CN_OLE_UNREGISTER|NULL|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]

## <a name="ccmdtargetonfinalrelease"></a><a name="onfinalrelease"></a> CCmdTarget:: OnFinalRelease

Nesnesine veya nesnesinden son OLE başvurusu serbest bırakıldığında Framework tarafından çağırılır.

```
virtual void OnFinalRelease();
```

### <a name="remarks"></a>Açıklamalar

Bu durum için özel işleme sağlamak üzere bu işlevi geçersiz kılın. Varsayılan uygulama, nesneyi siler.

## <a name="ccmdtargetrestorewaitcursor"></a><a name="restorewaitcursor"></a> CCmdTarget:: RestoreWaitCursor

Sistem imleci değiştirildikten sonra uygun kum saati imlecini geri yüklemek için bu işlevi çağırın (örneğin, bir ileti kutusu açıldıktan sonra ve uzun bir işlemin ortasında kapatıldıktan sonra).

```cpp
void RestoreWaitCursor();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek ACDUAL](../../overview/visual-cpp-samples.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdUI sınıfı](../../mfc/reference/ccmdui-class.md)<br/>
[CDocument sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CWinApp sınıfı](../../mfc/reference/cwinapp-class.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CView sınıfı](../../mfc/reference/cview-class.md)<br/>
[CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Cotadispatchdriver sınıfı](../../mfc/reference/coledispatchdriver-class.md)
