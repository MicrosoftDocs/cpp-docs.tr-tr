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
ms.openlocfilehash: 583b685295bf77910ef134776c1c4fa39baf93ad
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816348"
---
# <a name="ccmdtarget-class"></a>CCmdTarget sınıfı

Microsoft Foundation Class Kitaplığı ileti eşleme mimarisine yönelik temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CCmdTarget : public CObject
```

## <a name="members"></a>Üyeleri

### <a name="public-constructors"></a>Ortak oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CCmdTarget:: CCmdTarget](#ccmdtarget)|@No__t-0 nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CCmdTarget:: BeginWaitCursor](#beginwaitcursor)|İmleci bir kum saati imleci olarak görüntüler.|
|[CCmdTarget::D Ootaverb](#dooleverb)|OLE fiili tarafından belirtilen bir eylemin gerçekleştirilmesine neden olur.|
|[CCmdTarget:: EnableAutomation](#enableautomation)|@No__t-0 nesnesi için OLE otomasyonuna izin verir.|
|[CCmdTarget:: EnableConnections](#enableconnections)|Bağlantı noktaları üzerinde olay tetiklemenize izin vermez.|
|[CCmdTarget:: EnableTypeLib](#enabletypelib)|Bir nesnenin tür kitaplığını etkinleştirilir.|
|[CCmdTarget:: EndWaitCursor](#endwaitcursor)|Önceki imlece döner.|
|[CCmdTarget:: EnumOleVerbs](#enumoleverbs)|Bir nesnenin OLE fiillerini numaralandırır.|
|[CCmdTarget:: FromIDispatch](#fromidispatch)|@No__t-1 işaretçiyle ilişkili `CCmdTarget` nesnesine bir işaretçi döndürür.|
|[CCmdTarget:: GetDispatchIID](#getdispatchiid)|Birincil dağıtım arabirim KIMLIĞINI alır.|
|[CCmdTarget:: GetIDispatch](#getidispatch)|@No__t-1 nesnesiyle ilişkili `IDispatch` nesnesine bir işaretçi döndürür.|
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

@No__t 'den türetilmiş anahtar Framework sınıfları [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md)ve [CFrameWnd](../../mfc/reference/cframewnd-class.md)dahil. İletileri işlemek için yeni bir sınıf istiyorsanız bu @no__t -0-türetilmiş sınıflardan birini sınıfından türetebilirsiniz. @No__t-0 ' dan nadiren bir sınıf türetecaksınız.

Komut hedefleri ve `OnCmdMsg` yönlendirmeye genel bir bakış için bkz. [komut hedefleri](../../mfc/command-targets.md), [komut yönlendirme](../../mfc/command-routing.md)ve [eşleme iletileri](../../mfc/mapping-messages.md).

`CCmdTarget`, kum saati imlecini görüntülemeyi işleyen üye işlevlerini içerir. Bir komutun yürütülmesi için dikkat çekici bir zaman aralığı almayı düşünüyorsanız kum saati imlecini görüntüleyin.

İleti eşlemleriyle benzer olan dağıtım haritaları, OLE Otomasyonu `IDispatch` işlevselliğini göstermek için kullanılır. Bu arabirimi kullanıma sunarak diğer uygulamalar (örneğin, Visual Basic) uygulamanıza çağırabilir.

## <a name="inheritance-hierarchy"></a>Devralma hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CCmdTarget`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="beginwaitcursor"></a>CCmdTarget:: BeginWaitCursor

Komutun yürütülmesi için dikkat çekici bir zaman aralığı almayı beklemeniz durumunda imleci bir kum saati olarak göstermek için bu işlevi çağırın.

```
void BeginWaitCursor();
```

### <a name="remarks"></a>Açıklamalar

Framework, `CDocument` nesnesinin kendisini bir dosyaya yükleme veya kaydetme gibi bir kullanıcının meşgul olduğunu göstermek için bu işlevi çağırır.

@No__t-0 ' ın eylemleri, `OnSetCursor` işleme gibi diğer eylemler her zaman tek bir ileti işleyicisinin dışında etkili değildir.

Önceki imleci geri yüklemek için `EndWaitCursor` çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="ccmdtarget"></a>CCmdTarget:: CCmdTarget

@No__t-0 nesnesi oluşturur.

```
CCmdTarget();
```

##  <a name="dooleverb"></a>CCmdTarget::D Ootaverb

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
*HwndParent*içinde bir nesnenin sınırlayıcı dikdörtgenini tanımlayan koordinatları içeren [dikdörtgen](/previous-versions/dd162897\(v=vs.85\)) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş değeri

Başarılı olursa TRUE, aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi temel olarak bir [IOleObject uygulamasıdır::D oVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb). Olası eylemler [CCmdTarget:: EnumOleVerbs](#enumoleverbs)tarafından numaralandırılır.

##  <a name="enableautomation"></a>CCmdTarget:: EnableAutomation

Bir nesne için OLE Otomasyonu 'nu etkinleştirmek için bu işlevi çağırın.

```
void EnableAutomation();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle nesnenizin oluşturucusundan çağrılır ve yalnızca sınıf için bir dağıtım eşlemesi bildirilirse çağrılmalıdır. Otomasyon hakkında daha fazla bilgi için bkz. Makale [Otomasyonu istemcileri](../../mfc/automation-clients.md) ve [Otomasyon sunucuları](../../mfc/automation-servers.md).

##  <a name="enableconnections"></a>CCmdTarget:: EnableConnections

Bağlantı noktaları üzerinde olay tetiklemenize izin vermez.

```
void EnableConnections();
```

### <a name="remarks"></a>Açıklamalar

Bağlantı noktalarını etkinleştirmek için, türetilmiş sınıfınızın oluşturucusunda Bu üye işlevini çağırın.

##  <a name="enabletypelib"></a>CCmdTarget:: EnableTypeLib

Bir nesnenin tür kitaplığını etkinleştirilir.

```
void EnableTypeLib();
```

### <a name="remarks"></a>Açıklamalar

Tür bilgisi sağlıyorsa, bu üye işlevini @no__t -0-türetilmiş nesnenizin oluşturucusunda çağırın.

##  <a name="endwaitcursor"></a>CCmdTarget:: EndWaitCursor

Kum saati imlecini önceki imlece döndürmek için `BeginWaitCursor` üye işlevini çağırdıktan sonra bu işlevi çağırın.

```
void EndWaitCursor();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, bu üye işlevini, kum saati imlecini çağırdıktan sonra da çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="enumoleverbs"></a>CCmdTarget:: EnumOleVerbs

Bir nesnenin OLE fiillerini numaralandırır.

```
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```

### <a name="parameters"></a>Parametreler

*ppenumOleVerb*<br/>
[IEnumOLEVERB](/windows/win32/api/oleidl/nn-oleidl-ienumoleverb) arabirimine yönelik işaretçiye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş değeri

Nesne en az bir OLE fiilini destekliyorsa (Bu durumda \* *ppenumOleVerb* `IEnumOLEVERB` Numaralandırıcı arabirimine işaret ediyorsa), aksı takdirde yanlış olur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi temelde bir [IOleObject:: EnumVerbs](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs)uygulamasıdır.

##  <a name="fromidispatch"></a>CCmdTarget:: FromIDispatch

Bir sınıfın Otomasyon üye işlevlerinden alınan `IDispatch` işaretçisini `IDispatch` nesnesinin arabirimlerini uygulayan `CCmdTarget` nesnesine eşlemek için bu işlevi çağırın.

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
@No__t-0 nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş değeri

*LpDispatch*ile ilişkili `CCmdTarget` nesnesine yönelik bir işaretçi. Bu işlev, `IDispatch` nesnesi Microsoft Foundation Class `IDispatch` nesnesi olarak tanınmıyorsa NULL değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlevin sonucu `GetIDispatch` üye işlevine yapılan çağrının tersidir.

##  <a name="getdispatchiid"></a>CCmdTarget:: GetDispatchIID

Birincil dağıtım arabirim KIMLIĞINI alır.

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>Parametreler

*Piıd*<br/>
Arabirim KIMLIĞI ( [GUID](/previous-versions/cc317743(v%3dmsdn.10))) işaretçisi.

### <a name="return-value"></a>Dönüş değeri

Başarılı olursa TRUE, aksi durumda FALSE. Başarılı olursa, \* *Piıd* , birincil DAĞıTıM arabirimi kimliği olarak ayarlanır.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflar bu üye işlevini geçersiz kılmalıdır (geçersiz kılınmamışsa, `GetDispatchIID` FALSE döndürür). Bkz. [Coelcontrol](../../mfc/reference/colecontrol-class.md).

##  <a name="getidispatch"></a>CCmdTarget:: GetIDispatch

@No__t-1 işaretçisi döndüren veya başvuruya göre @no__t 2 işaretçisi alan bir Otomasyon yönteminden `IDispatch` işaretçisini almak için bu üye işlevini çağırın.

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>Parametreler

*bAddRef*<br/>
Nesnenin başvuru sayısının arttırılıp artırılmayacağını belirtir.

### <a name="return-value"></a>Dönüş değeri

Nesneyle ilişkili `IDispatch` işaretçisi.

### <a name="remarks"></a>Açıklamalar

Kurucularında `EnableAutomation` çağıran nesneler için, bu işlev `IDispatch` arabirimi aracılığıyla iletişim kuran istemciler tarafından kullanılan `IDispatch` ' in temel sınıf uygulamasına bir işaretçi döndürür. Bu işlevi çağırmak işaretçiye otomatik olarak bir başvuru ekler, bu nedenle [IUnknown:: AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)çağrısı yapmak gerekli değildir.

##  <a name="gettypeinfocount"></a>CCmdTarget:: GetTypeInfoCount

Bir nesnenin sağladığı tür bilgisi arabirimlerinin sayısını alır.

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>Dönüş değeri

Tür bilgisi arabirimlerinin sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, temel olarak [IDispatch:: GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount)uygular.

Türetilmiş sınıflar, sunulan tür bilgisi arabirimlerinin sayısını (0 veya 1) döndürmek için bu işlevi geçersiz kılmalıdır. Geçersiz kılınmamışsa, `GetTypeInfoCount` 0 döndürür. Geçersiz kılmak için, `GetTypeLib` ve `GetTypeLibCache` ' yi de uygulayan [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) makrosunu kullanın.

##  <a name="gettypeinfoofguid"></a>CCmdTarget:: GetTypeInfoOfGuid

Belirtilen GUID 'ye karşılık gelen tür açıklamasını alır.

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>Parametreler

*IC*<br/>
Yerel ayar tanımlayıcısı (`LCID`).

*'ini*<br/>
Tür açıklamasının [GUID 'i](/previous-versions/cc317743(v%3dmsdn.10)) .

*ppTypeInfo*<br/>
@No__t-0 arabirimine bir işaretçiye yönelik işaretçi.

### <a name="return-value"></a>Dönüş değeri

Çağrının başarısını veya başarısızlığını gösteren bir HRESULT. Başarılı olursa, \* *ppTypeInfo* tür bilgisi arabirimine işaret eder.

##  <a name="gettypelib"></a>CCmdTarget:: GetTypeLib

Bir tür kitaplığına yönelik bir işaretçi alır.

```
virtual HRESULT GetTypeLib(
    LCID lcid,
    LPTYPELIB* ppTypeLib);
```

### <a name="parameters"></a>Parametreler

*IC*<br/>
Bir yerel ayar tanıtıcısı (LCıD).

*ppTypeLib*<br/>
@No__t-0 arabirimine bir işaretçiye yönelik işaretçi.

### <a name="return-value"></a>Dönüş değeri

Çağrının başarısını veya başarısızlığını gösteren bir HRESULT. Başarılı olursa, \* *ppTypeLib* tür kitaplığı arabirimine işaret eder.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflar bu üye işlevini geçersiz kılmalıdır (geçersiz kılınmamışsa, `GetTypeLib`, TYPE_E_CANTLOADLIBRARY döndürür). @No__t-1 ve `GetTypeLibCache` ' yi de uygulayan [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) makrosunu kullanın.

##  <a name="gettypelibcache"></a>CCmdTarget:: GetTypeLibCache

Tür kitaplığı önbelleğini alır.

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>Dönüş değeri

@No__t-0 nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflar bu üye işlevini geçersiz kılmalıdır (geçersiz kılınmamışsa `GetTypeLibCache`, NULL döndürür). @No__t-1 ve `GetTypeLib` ' yi de uygulayan [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) makrosunu kullanın.

##  <a name="isinvokeallowed"></a>CCmdTarget:: IsInvokeAllowed

Bu işlev, belirli bir Otomasyon yönteminin ( *DISPID*tarafından tanımlanan) çağrılabilir olup olmadığını anlamak için MFC 'nin `IDispatch::Invoke` ' a uygulanması tarafından çağrılır.

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
Bir dağıtım KIMLIĞI.

### <a name="return-value"></a>Dönüş değeri

Yöntem çağrlanacaksa TRUE, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

@No__t-0 TRUE değerini döndürürse, `Invoke` yöntemi çağırmak için devam eder; Aksi takdirde, `Invoke` başarısız olur, E_UNEXPECTED döndürülüyor.

Türetilmiş sınıflar, uygun değerleri döndürmek için bu işlevi geçersiz kılabilir (geçersiz kılınmamışsa, `IsInvokeAllowed` TRUE döndürür). Bkz. belirli [Coelcontrol:: IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).

##  <a name="isresultexpected"></a>CCmdTarget:: ısresultexyted

Bir istemcinin bir Otomasyon işlevine çağrısından bir dönüş değeri bekleip bekmeyeceğini belirlemek için `IsResultExpected` kullanın.

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>Dönüş değeri

Bir Otomasyon işlevinin bir değer döndürmesi gerekiyorsa sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

OLE arabirimi, istemcinin bir işlev çağrısının sonucunu kullanıp kullanmadığını ya da yok saymadığını, MFC 'ye bilgi sağlar ve sırasıyla MFC bu bilgileri `IsResultExpected` ' a yapılan çağrının sonucunu belirlemede kullanır. Dönüş değerinin üretimi zaman veya Kaynak yoğunluklu ise, dönüş değerini hesaplamadan önce bu işlevi çağırarak verimliliği artırabilirsiniz.

Bu işlev yalnızca bir kez 0 döndürür, bu sayede diğer otomasyon işlevlerindeki geçerli dönüş değerlerini istemcinin çağırdığı Otomasyon işlevinden çağırabilirsiniz.

`IsResultExpected`, bir Otomasyon işlevi çağrısı devam ederken çağrılırsa sıfır dışında bir değer döndürür.

##  <a name="oncmdmsg"></a>CCmdTarget:: OnCmdMsg

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
Komut bildirim kodunu tanımlar. *NCode*değerleri hakkında daha fazla bilgi için bkz. **açıklamalar** .

*pExtra*<br/>
*NCode*değerine göre kullanılır. *PExtra*hakkında daha fazla bilgi için bkz. **açıklamalar** .

*pHandlerInfo*<br/>
NULL değilse, `OnCmdMsg`, komutu dağıtma yerine *pHandlerInfo* yapısının *pTarget* ve *PMF* üyelerini doldurur. Genellikle, bu parametre NULL olmalıdır.

### <a name="return-value"></a>Dönüş değeri

İleti işlenirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu, Framework komut mimarisinin ana uygulama yordamlamasıdır.

Çalışma zamanında, `OnCmdMsg` diğer nesnelere bir komut gönderir veya gerçek ileti eşleme aramasını yapan `CCmdTarget::OnCmdMsg` kök sınıfını çağırarak komutun kendisini işler. Varsayılan komut yönlendirmesinin tamamen açıklaması için bkz. [Ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).

Nadir durumlarda, çerçevenin standart komut yönlendirmesini genişletmek için bu üye işlevini geçersiz kılmak isteyebilirsiniz. Komut yönlendirme mimarisinin gelişmiş ayrıntıları için bkz. [teknik notta 21](../../mfc/tn021-command-and-message-routing.md) .

@No__t-0 ' ı geçersiz kılarsınız *, nCode*değerine bağlı olarak *nCode*, komut bildirim kodu ve *pExtra*için uygun değeri sağlamanız gerekir. Aşağıdaki tabloda karşılık gelen değerleri listelenmektedir:

|*nCode* değeri|*pExtra* değeri|
|-------------------|--------------------|
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)\*|
|CN_EVENT|AFX_EVENT @ no__t-0|
|CN_UPDATE_COMMAND_UI|CCmdUI @ no__t-0|
|CN_OLECOMMAND|[Cotacmduı](../../mfc/reference/colecmdui-class.md)\*|
|CN_OLE_UNREGISTER|NULL|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]

##  <a name="onfinalrelease"></a>CCmdTarget:: OnFinalRelease

Nesnesine veya nesnesinden son OLE başvurusu serbest bırakıldığında Framework tarafından çağırılır.

```
virtual void OnFinalRelease();
```

### <a name="remarks"></a>Açıklamalar

Bu durum için özel işleme sağlamak üzere bu işlevi geçersiz kılın. Varsayılan uygulama, nesneyi siler.

##  <a name="restorewaitcursor"></a>CCmdTarget:: RestoreWaitCursor

Sistem imleci değiştirildikten sonra uygun kum saati imlecini geri yüklemek için bu işlevi çağırın (örneğin, bir ileti kutusu açıldıktan sonra ve uzun bir işlemin ortasında kapatıldıktan sonra).

```
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
