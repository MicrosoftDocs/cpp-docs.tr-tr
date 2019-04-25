---
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
ms.openlocfilehash: 9314717fab53b1a89b87d657ec617a4c6bd45b8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206447"
---
# <a name="ccmdtarget-class"></a>CCmdTarget sınıfı

Microsoft Foundation Class Kitaplığı ileti eşleme mimarisi için temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CCmdTarget : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCmdTarget::CCmdTarget](#ccmdtarget)|Oluşturur bir `CCmdTarget` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|İmleç bir kum saati imleç görüntüler.|
|[CCmdTarget::DoOleVerb](#dooleverb)|Gerçekleştirilecek bir OLE fiili belirtilen eylem neden olur.|
|[CCmdTarget::EnableAutomation](#enableautomation)|OLE Otomasyonu için sağlar `CCmdTarget` nesne.|
|[CCmdTarget::EnableConnections](#enableconnections)|Olay tetikleyicisinin tetikleme bağlantı noktaları sağlar.|
|[CCmdTarget::EnableTypeLib](#enabletypelib)|Bir nesnenin tür kitaplığı sağlar.|
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|İmleci önceki geri döner.|
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|Bir nesnenin OLE fiilleri numaralandırır.|
|[CCmdTarget::FromIDispatch](#fromidispatch)|Bir işaretçi döndürür `CCmdTarget` ilişkili nesne `IDispatch` işaretçi.|
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|Birincil dağıtım arabirimi kimliği alır.|
|[CCmdTarget::GetIDispatch](#getidispatch)|Bir işaretçi döndürür `IDispatch` ilişkili nesne `CCmdTarget` nesne.|
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|Bir nesnenin sağladığı tür bilgisi arabirimlerinin sayısını alır.|
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|Belirtilen GUID için karşılık gelen türü açıklaması alır.|
|[CCmdTarget::GetTypeLib](#gettypelib)|Bir tür kitaplığı için bir işaretçi alır.|
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|Tür kitaplığı önbelleğe alır.|
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|Otomasyon yöntemi sağlar.|
|[CCmdTarget::IsResultExpected](#isresultexpected)|Döndürür bir Otomasyon işlevi ise sıfır olmayan bir değer döndürmesi gerekir.|
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|Yönlendirir ve komut iletilerini gönderir.|
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|Son OLE referansı kullanıma sunulduktan sonra temizler.|
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|Kum Saati imleç geri yükler.|

## <a name="remarks"></a>Açıklamalar

İleti eşlemesi komutları veya iletileri işlemeye yazma üye işlevleri için yönlendirir. (Bir iletiye bir menü öğesi, komut düğmesi ya da kısayol tuşu komutudur.)

Anahtar çerçeve sınıflarından türetilen `CCmdTarget` dahil [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md), ve [ CFrameWnd](../../mfc/reference/cframewnd-class.md). Yeni bir sınıf iletileri işlemek istiyorsanız, aşağıdakilerden birini sınıf türetin `CCmdTarget`-türetilmiş sınıflar. Bir sınıftan nadiren derleyeceği `CCmdTarget` doğrudan.

Komut hedefleri genel bakış ve `OnCmdMsg` yönlendirmeyi, bkz: [komut hedefleri](../../mfc/command-targets.md), [komut yönlendirme](../../mfc/command-routing.md), ve [eşleme iletileri](../../mfc/mapping-messages.md).

`CCmdTarget` bir kum saati imleç görüntüsünü işlemek üye işlevleri içerir. Bir komut yürütmek için bir fark zaman aralığı gerçekleştirilecek beklediğiniz şekilde kum saati imleç görüntüleyin.

OLE Otomasyonu nesnesi etkin kullanıma sunmak için kullanılan, gönderme eşlemeleri, ileti eşlemeleri benzer `IDispatch` işlevselliği. Bu arabirim göstererek, diğer uygulamalar (örneğin, Visual Basic) uygulamanıza çağırabilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CCmdTarget`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="beginwaitcursor"></a>  CCmdTarget::BeginWaitCursor

Bir komut yürütmek için bir fark zaman aralığı gerçekleştirilecek beklediğiniz imleç kum saati olarak görüntülemek için bu işlevi çağırın.

```
void BeginWaitCursor();
```

### <a name="remarks"></a>Açıklamalar

Framework gibi ne zaman meşgul olduğunu kullanıcıya göstermek için bu işlevi çağıran bir `CDocument` nesne yükler veya kendisi bir dosyaya kaydeder.

Eylemleri `BeginWaitCursor` her zaman diğer eylemler gibi bir tek ileti işleyicisi dışında etkili değildir `OnSetCursor` işleme, imleç değiştirebilirsiniz.

Çağrı `EndWaitCursor` önceki imleci geri yüklemek için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="ccmdtarget"></a>  CCmdTarget::CCmdTarget

Oluşturur bir `CCmdTarget` nesne.

```
CCmdTarget();
```

##  <a name="dooleverb"></a>  CCmdTarget::DoOleVerb

Gerçekleştirilecek bir OLE fiili belirtilen eylem neden olur.

```
BOOL DoOleVerb(
    LONG iVerb,
    LPMSG lpMsg,
    HWND hWndParent,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*iVerb*<br/>
Fiili sayısal tanımlayıcısı.

*lpMsg*<br/>
İşaretçi [MSG](/windows/desktop/api/winuser/ns-winuser-msg) yapısını açıklayan fiili çağrılan olay (örneğin, bir çift tıklatın).

*hWndParent*<br/>
Nesne içeren belge penceresi tanıtıcısı.

*lpRect*<br/>
İşaretçi [RECT](/previous-versions/dd162897\(v=vs.85\)) içeren nesneyi tanımlayan piksel koordinatları yapısı dikdörtgende çevreleyen *hwndParent*.

### <a name="return-value"></a>Dönüş Değeri

Başarılı, aksi takdirde FALSE ise TRUE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi temelde uygulamasıdır [Rpc_e_serverfault](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb). Olası eylemler tarafından numaralandırılır [CCmdTarget::EnumOleVerbs](#enumoleverbs).

##  <a name="enableautomation"></a>  CCmdTarget::EnableAutomation

OLE Otomasyonu nesnesi etkin bir nesne için etkinleştirmek için bu işlevi çağırın.

```
void EnableAutomation();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, nesnenizin oluşturucudan tipik olarak adlandırılır ve yalnızca bir dağıtım eşlemesi için sınıf bildirilmişlerse çağrılmalıdır. Otomasyon hakkında daha fazla bilgi için makalelere göz atın [Otomasyon istemcileri](../../mfc/automation-clients.md) ve [otomasyon sunucuları](../../mfc/automation-servers.md).

##  <a name="enableconnections"></a>  CCmdTarget::EnableConnections

Olay tetikleyicisinin tetikleme bağlantı noktaları sağlar.

```
void EnableConnections();
```

### <a name="remarks"></a>Açıklamalar

Bağlantı noktaları etkinleştirmek için türetilmiş sınıfın oluşturucusunda bu üye işlevini çağırın.

##  <a name="enabletypelib"></a>  CCmdTarget::EnableTypeLib

Bir nesnenin tür kitaplığı sağlar.

```
void EnableTypeLib();
```

### <a name="remarks"></a>Açıklamalar

Oluşturucusunun içinde bu üye işlevini çağırın, `CCmdTarget`-tür bilgiler sağlıyorsa, nesne türetilmiş.

##  <a name="endwaitcursor"></a>  CCmdTarget::EndWaitCursor

Bu işlev çağrısı yapmanız sonrasında çağrı `BeginWaitCursor` Kum Saati İmleci önceki imleci döndürülecek üye işlevi.

```
void EndWaitCursor();
```

### <a name="remarks"></a>Açıklamalar

Kum Saati imleç çağırdı sonra framework Ayrıca bu üye işlevini çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="enumoleverbs"></a>  CCmdTarget::EnumOleVerbs

Bir nesnenin OLE fiilleri numaralandırır.

```
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```

### <a name="parameters"></a>Parametreler

*ppenumOleVerb*<br/>
Bir işaretçi işaretçisi bir [IEnumOLEVERB](/windows/desktop/api/oleidl/nn-oleidl-ienumoleverb) arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin en az bir OLE fiili destekliyorsa TRUE (Bu durumda \* *ppenumOleVerb* işaret eden bir `IEnumOLEVERB` Numaralandırıcı arabirimi), aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi temelde uygulamasıdır [IOleObject::EnumVerbs](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-enumverbs).

##  <a name="fromidispatch"></a>  CCmdTarget::FromIDispatch

Eşlemek için bu işlevi çağırın bir `IDispatch` işaretçi, bir sınıfın üye işlevleri Otomasyon içine alınan `CCmdTarget` arabirimleri uygulayan nesne `IDispatch` nesne.

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
Bir işaretçi bir `IDispatch` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `CCmdTarget` ilişkili nesne *lpDispatch*. Bu işlev NULL döndürür `IDispatch` nesne bir Microsoft Foundation Class tanınmıyor `IDispatch` nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlevin sonucu üye işlevine bir çağrı gibidir `GetIDispatch`.

##  <a name="getdispatchiid"></a>  CCmdTarget::GetDispatchIID

Birincil dağıtım arabirimi kimliği alır.

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>Parametreler

*pIID*<br/>
Bir arabirim kimliği için bir işaretçi (bir [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931)).

### <a name="return-value"></a>Dönüş Değeri

Başarılı, aksi takdirde FALSE ise TRUE. Başarılı olursa, \* *pIID* birincil dağıtım arabirimi kimliğine ayarlayın

### <a name="remarks"></a>Açıklamalar

Türetilen sınıfların bu üye işlevini geçersiz kılmalıdır (kılınmazsa, `GetDispatchIID` false değerini döndürür). Bkz: [COleControl](../../mfc/reference/colecontrol-class.md).

##  <a name="getidispatch"></a>  CCmdTarget::GetIDispatch

Almak için bu üye işlevi çağrısı `IDispatch` işaretçisi, herhangi bir Otomasyon yönteminden döndürülüyor bir `IDispatch` işaretçi veya alır bir `IDispatch` işaretçi başvurusu tarafından.

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>Parametreler

*bAddRef*<br/>
Nesnenin başvuru sayısının artırılmasına belirtir.

### <a name="return-value"></a>Dönüş Değeri

`IDispatch` Nesnesiyle ilişkili bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu çağrı nesneleri için `EnableAutomation` etkin, Otomasyon yönetilmelerini kendi oluşturucularda bu işlev Foundation sınıf uygulamasına yönelik bir işaretçi döndürür `IDispatch` üzerinden iletişim kurmasına istemciler tarafından kullanılan `IDispatch` arabirimi. Bu işlevi çağırmak, otomatik olarak ekler fare işaretçisini bir başvuru bir çağrı yapmak gerekli değildir [IUnknown::AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref).

##  <a name="gettypeinfocount"></a>  CCmdTarget::GetTypeInfoCount

Bir nesnenin sağladığı tür bilgisi arabirimlerinin sayısını alır.

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tür bilgisi arabirimlerinin sayısını.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi temelde uygulayan [IDispatch::GetTypeInfoCount](/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount).

Türetilen sınıflar (0 veya 1) sağlanan türü bilgisi arabirimlerinin sayısını döndürmek için bu işlevi geçersiz kılmalıdır. Kılınmazsa, `GetTypeInfoCount` 0 döndürür. Geçersiz kılmak için kullanın [ımplement_oletypelıb](../../mfc/reference/type-library-access.md#implement_oletypelib) ayrıca uygulayan makrosu `GetTypeLib` ve `GetTypeLibCache`.

##  <a name="gettypeinfoofguid"></a>  CCmdTarget::GetTypeInfoOfGuid

Belirtilen GUID için karşılık gelen türü açıklaması alır.

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>Parametreler

*lcid*<br/>
Bir yerel ayar tanımlayıcı ( `LCID`).

*GUID*<br/>
[GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931) türü açıklaması.

*ppTypeInfo*<br/>
Bir işaretçi işaretçisi `ITypeInfo` arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya başarısız çağrının belirten bir HRESULT. Başarılı olursa, \* *ppTypeInfo* işaret türü bilgileri arabirimi.

##  <a name="gettypelib"></a>  CCmdTarget::GetTypeLib

Bir tür kitaplığı için bir işaretçi alır.

```
virtual HRESULT GetTypeLib(
    LCID lcid,
    LPTYPELIB* ppTypeLib);
```

### <a name="parameters"></a>Parametreler

*lcid*<br/>
Bir yerel ayar kimliği (LCID).

*ppTypeLib*<br/>
Bir işaretçi işaretçisi `ITypeLib` arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya başarısız çağrının belirten bir HRESULT. Başarılı olursa, \* *ppTypeLib* tür kitaplığı arabirimi işaret eder.

### <a name="remarks"></a>Açıklamalar

Türetilen sınıfların bu üye işlevini geçersiz kılmalıdır (kılınmazsa, `GetTypeLib` TYPE_E_CANTLOADLIBRARY döndürür). Kullanım [ımplement_oletypelıb](../../mfc/reference/type-library-access.md#implement_oletypelib) ayrıca uygulayan makrosu `GetTypeInfoCount` ve `GetTypeLibCache`.

##  <a name="gettypelibcache"></a>  CCmdTarget::GetTypeLibCache

Tür kitaplığı önbelleğe alır.

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CTypeLibCache` nesne.

### <a name="remarks"></a>Açıklamalar

Türetilen sınıfların bu üye işlevini geçersiz kılmalıdır (kılınmazsa, `GetTypeLibCache` NULL döndürür). Kullanım [ımplement_oletypelıb](../../mfc/reference/type-library-access.md#implement_oletypelib) ayrıca uygulayan makrosu `GetTypeInfoCount` ve `GetTypeLib`.

##  <a name="isinvokeallowed"></a>  CCmdTarget::IsInvokeAllowed

Bu işlev MFC'nin uygulaması tarafından çağrılır `IDispatch::Invoke` belirli Otomasyon yöntemi olup olmadığını belirlemek (tarafından tanımlanan *DISPID*) çağrılabilir.

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>Parametreler

*DISPID*<br/>
Bir dağıtım kimliği

### <a name="return-value"></a>Dönüş Değeri

Bir yöntem olabilir, çağrılan, aksi durumda FALSE TRUE.

### <a name="remarks"></a>Açıklamalar

Varsa `IsInvokeAllowed` TRUE döndürür `Invoke` ; yöntem çağırmaya devam eder. Aksi takdirde `Invoke` , E_UNEXPECTED döndürür ve başarısız olur.

Türetilen sınıfların uygun değer döndürmek için bu işlevi geçersiz kılma (kılınmazsa, `IsInvokeAllowed` TRUE döndürür). Özellikle bkz [COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).

##  <a name="isresultexpected"></a>  CCmdTarget::IsResultExpected

Kullanım `IsResultExpected` bir istemci bir Otomasyon işlevi için yaptığı çağrıdan dönüş değeri Bekliyor olup olmadığını belirlemek için.

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>Dönüş Değeri

Bir Otomasyon işlevi bir değer döndürmelidir olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İstemci kullanarak veya diğer bir işlev çağrısının sonucu yoksayılıyor olup olmadığı hakkında bilgi MFC OLE arabirimi sağlayan ve MFC sırayla kullanır bu bilgileri bir çağrı sonucunu belirlemek için `IsResultExpected`. Saati - veya kaynak yoğunluklu, dönüş değerinin üretim ise, dönüş değeri bilgi işlem önce bu işlevi çağrılarak verimliliği artırabilir.

Bu işlev, böylece bunları Otomasyon işlevden, Eğer diğer Otomasyon işlevlerden geçerli dönüş değerlerini alırsınız. istemci yalnızca çağırdı sonra 0 döndürür.

`IsResultExpected` bir Otomasyon işlev çağrısı sürüyor olmadığında çağrılırsa sıfır olmayan bir değer döndürür.

##  <a name="oncmdmsg"></a>  CCmdTarget::OnCmdMsg

Komut kullanıcı arabirimi nesnelerini güncelleştirme işlenecek ve yönlendirmek ve komut iletilerini dağıtmak için framework tarafından çağırılır.

```
virtual BOOL OnCmdMsg(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Komut kimliğini içerir.

*nCode*<br/>
Komut bildirim kodu tanımlar. Bkz: **açıklamalar** değerleri hakkında daha fazla bilgi için *nCode*.

*pExtra*<br/>
Değerini göre kullanılan *nCode*. Bkz: **açıklamalar** hakkında daha fazla bilgi için *pExtra*.

*pHandlerInfo*<br/>
BOŞ değilse `OnCmdMsg` doldurur *pTarget* ve *pmf* üyeleri *pHandlerInfo* yapısı yerine komut gönderme. Genellikle, bu parametre NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

İleti ele olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Ana uygulama yordamı framework komut mimarisinin budur.

Çalışma zamanında `OnCmdMsg` diğer nesneler için bir komut gönderir veya komutun kendisindeki kök sınıfı çağırarak işler `CCmdTarget::OnCmdMsg`, gerçek ileti eşlemesi arama yapar. Varsayılan komut yönlendirme tam açıklaması için bkz. [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).

Nadir durumlarda, framework'ün genişletmek için bu üye işlevini geçersiz kılmak isteyebilirsiniz standart komut yönlendirmeyi. Başvurmak [Teknik Not 21](../../mfc/tn021-command-and-message-routing.md) komut yönlendirme mimarisi hakkında gelişmiş Ayrıntılar için.

Kılarsanız `OnCmdMsg`, uygun değeri sağlamalısınız *nCode*, komut bildirim kodu ve *pExtra*, bağımlı olduğu değerini temel *nCode* . Aşağıdaki tabloda, bunlara karşılık gelen değerler listelenmektedir:

|*nCode* değeri|*pExtra* değeri|
|-------------------|--------------------|
|CN_COMMAND|[Ccmduı](../../mfc/reference/ccmdui-class.md)\*|
|CN_EVENT|AFX_EVENT\*|
|CN_UPDATE_COMMAND_UI|Ccmduı\*|
|CN_OLECOMMAND|[Colecmduı](../../mfc/reference/colecmdui-class.md)\*|
|CN_OLE_UNREGISTER|NULL|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]

##  <a name="onfinalrelease"></a>  CCmdTarget::OnFinalRelease

Ya da nesneden son OLE referansı bırakıldığında framework tarafından çağırılır.

```
virtual void OnFinalRelease();
```

### <a name="remarks"></a>Açıklamalar

Bu durum için özel işleme sağlamak için bu işlevi geçersiz kılar. Varsayılan Uygulama nesnesini siler.

##  <a name="restorewaitcursor"></a>  CCmdTarget::RestoreWaitCursor

(Örneğin, bir ileti kutusu açılır ve uzun bir işlemin sırada kapatılan sonra) sistemi imleci değiştirildikten sonra uygun Kum Saati İmleci geri yüklemek için bu işlevi çağırın.

```
void RestoreWaitCursor();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[ACDUAL örneği](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdUI Sınıfı](../../mfc/reference/ccmdui-class.md)<br/>
[CDocument Sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CWinApp Sınıfı](../../mfc/reference/cwinapp-class.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[COleDispatchDriver Sınıfı](../../mfc/reference/coledispatchdriver-class.md)
