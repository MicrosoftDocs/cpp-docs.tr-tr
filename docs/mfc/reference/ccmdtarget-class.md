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
ms.openlocfilehash: e1b02da9914263017d637cb07b0f3b9f56cd6aa9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507714"
---
# <a name="ccmdtarget-class"></a>CCmdTarget sınıfı

Microsoft Foundation Class Kitaplığı ileti eşleme mimarisine yönelik temel sınıf.

## <a name="syntax"></a>Sözdizimi

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
|[CCmdTarget:: EnableAutomation](#enableautomation)|`CCmdTarget` Nesne için OLE otomasyonuna izin verir.|
|[CCmdTarget:: EnableConnections](#enableconnections)|Bağlantı noktaları üzerinde olay tetiklemenize izin vermez.|
|[CCmdTarget:: EnableTypeLib](#enabletypelib)|Bir nesnenin tür kitaplığını etkinleştirilir.|
|[CCmdTarget:: EndWaitCursor](#endwaitcursor)|Önceki imlece döner.|
|[CCmdTarget:: EnumOleVerbs](#enumoleverbs)|Bir nesnenin OLE fiillerini numaralandırır.|
|[CCmdTarget:: FromIDispatch](#fromidispatch)|İşaretçiyle ilişkili `CCmdTarget` nesneye bir işaretçi döndürür. `IDispatch`|
|[CCmdTarget:: GetDispatchIID](#getdispatchiid)|Birincil dağıtım arabirim KIMLIĞINI alır.|
|[CCmdTarget:: GetIDispatch](#getidispatch)|Nesneyle`CCmdTarget` ilişkili `IDispatch` nesneye bir işaretçi döndürür.|
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

[CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), `CCmdTarget` [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md)ve [CFrameWnd](../../mfc/reference/cframewnd-class.md)dahil öğesinden türetilmiş anahtar çerçevesi sınıfları. İletileri işlemek için yeni bir sınıf istiyorsanız, bu `CCmdTarget`türetilmiş sınıflardan birindeki sınıfı türetirsiniz. Genellikle `CCmdTarget` doğrudan bir sınıf türetirsiniz.

Komut `OnCmdMsg` hedefleri ve yönlendirmeye genel bir bakış için bkz. [komut hedefleri](../../mfc/command-targets.md), [komut yönlendirme](../../mfc/command-routing.md)ve [eşleme iletileri](../../mfc/mapping-messages.md).

`CCmdTarget`kum saati imlecinin görüntülenmesini işleyen üye işlevlerini içerir. Bir komutun yürütülmesi için dikkat çekici bir zaman aralığı almayı düşünüyorsanız kum saati imlecini görüntüleyin.

İleti eşlemleriyle benzer olan dağıtım haritaları, OLE Otomasyonu `IDispatch` işlevlerini göstermek için kullanılır. Bu arabirimi kullanıma sunarak diğer uygulamalar (örneğin, Visual Basic) uygulamanıza çağırabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

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

Framework, bir `CDocument` nesnenin kendisini bir dosyaya yüklediğinde veya kaydettiğinde olduğu gibi, meşgul olduğunu kullanıcıya göstermek için bu işlevi çağırır.

Eylemleri `BeginWaitCursor` , `OnSetCursor` işleme gibi diğer eylemler, imleci değiştiremediğinden, her zaman tek bir ileti işleyicisinin dışında etkili değildir.

Önceki `EndWaitCursor` imleci geri yüklemek için çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="ccmdtarget"></a>CCmdTarget:: CCmdTarget

Bir `CCmdTarget` nesnesi oluşturur.

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

### <a name="return-value"></a>Dönüş Değeri

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

Tür bilgilerini sağlıyorsa türetilmiş nesnenizin oluşturucusunda `CCmdTarget`Bu üye işlevini çağırın.

##  <a name="endwaitcursor"></a>CCmdTarget:: EndWaitCursor

Bu işlevi, kum saati imlecini önceki imlece döndürmek için `BeginWaitCursor` üye işlevini çağırdıktan sonra çağırın.

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

### <a name="return-value"></a>Dönüş Değeri

Nesne en az bir OLE fiilini destekliyorsa (Bu durumda \* *ppenumOleVerb* bir `IEnumOLEVERB` Numaralandırıcı arabirimine işaret ediyorsa), aksi takdirde yanlış olur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi temelde bir [IOleObject:: EnumVerbs](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs)uygulamasıdır.

##  <a name="fromidispatch"></a>CCmdTarget:: FromIDispatch

Bir sınıfın `IDispatch` `IDispatch` Otomasyon üye işlevlerinden alınan bir işaretçiyi nesnenin arabirimlerini uygulayan nesneyeeşlemekiçinbuişleviçağırın.`CCmdTarget`

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>Parametreler

*lpDispatch*<br/>
Bir `IDispatch` nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

*LpDispatch*ile ilişkili `CCmdTarget` nesneye yönelik bir işaretçi. Bu işlev, `IDispatch` nesne Microsoft Foundation Class `IDispatch` nesnesi olarak tanınmıyorsa null değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlevin sonucu, üye işlevine `GetIDispatch`yapılan çağrının tersidir.

##  <a name="getdispatchiid"></a>CCmdTarget:: GetDispatchIID

Birincil dağıtım arabirim KIMLIĞINI alır.

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>Parametreler

*Piıd*<br/>
Arabirim KIMLIĞI ( [GUID](/previous-versions/aa373931\(v=vs.80\))) işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE, aksi durumda FALSE. Başarılı olursa, \* *pIID* birincil dağıtım arabirimi kimliği olarak ayarlanır.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflar bu üye işlevini geçersiz kılmalıdır (geçersiz kılınmamışsa `GetDispatchIID` , false döndürür). Bkz. [Coelcontrol](../../mfc/reference/colecontrol-class.md).

##  <a name="getidispatch"></a>CCmdTarget:: GetIDispatch

Bir `IDispatch` `IDispatch` işaretçi`IDispatch` döndüren veya başvuruya göre işaretçi alan bir Otomasyon yönteminden işaretçiyi almak için bu üye işlevini çağırın.

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>Parametreler

*bAddRef*<br/>
Nesnenin başvuru sayısının arttırılıp artırılmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesneyle `IDispatch` ilişkili işaretçi.

### <a name="remarks"></a>Açıklamalar

Oluşturucularını çağıran `EnableAutomation` nesneler için, Otomasyonu etkin hale getirerek bu işlev, `IDispatch` arabirimi aracılığıyla iletişim kuran istemciler tarafından kullanılan temel sınıf `IDispatch` uygulamasına bir işaretçi döndürür. Bu işlevi çağırmak işaretçiye otomatik olarak bir başvuru ekler, bu nedenle [IUnknown:: AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)çağrısı yapmak gerekli değildir.

##  <a name="gettypeinfocount"></a>CCmdTarget:: GetTypeInfoCount

Bir nesnenin sağladığı tür bilgisi arabirimlerinin sayısını alır.

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tür bilgisi arabirimlerinin sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, temel olarak [IDispatch:: GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount)uygular.

Türetilmiş sınıflar, sunulan tür bilgisi arabirimlerinin sayısını (0 veya 1) döndürmek için bu işlevi geçersiz kılmalıdır. Geçersiz kılınmamışsa `GetTypeInfoCount` 0 döndürür. Geçersiz kılmak için, `GetTypeLibCache`ve [](../../mfc/reference/type-library-access.md#implement_oletypelib) de uygulayan `GetTypeLib` IMPLEMENT_OLETYPELIB makrosunu kullanın.

##  <a name="gettypeinfoofguid"></a>CCmdTarget:: GetTypeInfoOfGuid

Belirtilen GUID 'ye karşılık gelen tür açıklamasını alır.

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>Parametreler

*lcid*<br/>
Yerel ayar tanımlayıcısı ( `LCID`).

*guid*<br/>
Tür açıklamasının [GUID 'i](/previous-versions/aa373931\(v=vs.80\)) .

*ppTypeInfo*<br/>
`ITypeInfo` Arabirim işaretçisinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Çağrının başarısını veya başarısızlığını gösteren bir HRESULT. Başarılı olursa, \* *ppTypeInfo* tür bilgisi arabirimine işaret eder.

##  <a name="gettypelib"></a>CCmdTarget:: GetTypeLib

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
`ITypeLib` Arabirim işaretçisinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Çağrının başarısını veya başarısızlığını gösteren bir HRESULT. Başarılı olursa, \* *ppTypeLib* tür kitaplığı arabirimine işaret eder.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflar bu üye işlevini geçersiz kılmalıdır (geçersiz kılınmamışsa `GetTypeLib` , TYPE_E_CANTLOADLIBRARY döndürür). Ve `GetTypeInfoCount` [](../../mfc/reference/type-library-access.md#implement_oletypelib) deuygulayanIMPLEMENT_OLETYPELIBmakrosunu`GetTypeLibCache`kullanın.

##  <a name="gettypelibcache"></a>CCmdTarget:: GetTypeLibCache

Tür kitaplığı önbelleğini alır.

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CTypeLibCache` nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflar bu üye işlevini geçersiz kılmalıdır (geçersiz kılınmamışsa `GetTypeLibCache` , null döndürür). Ve `GetTypeInfoCount` [](../../mfc/reference/type-library-access.md#implement_oletypelib) deuygulayanIMPLEMENT_OLETYPELIBmakrosunu`GetTypeLib`kullanın.

##  <a name="isinvokeallowed"></a>CCmdTarget:: IsInvokeAllowed

Bu işlev, belirli bir Otomasyon yönteminin ( `IDispatch::Invoke` *DISPID*tarafından tanımlanan) çağrılabilir olup olmadığını anlamak için MFC 'nin uygulamasının uygulamasına göre çağrılır.

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
Bir dağıtım KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Yöntem çağrlanacaksa TRUE, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

TRUE değerini döndürürse yöntemi çağırmaya `Invoke` devameder;Aksitakdirde,e_unexpecteddöndürenbaşarısızolur.`Invoke` `IsInvokeAllowed`

Türetilmiş sınıflar, uygun değerleri döndürmek için bu işlevi geçersiz kılabilir (geçersiz kılınmamışsa `IsInvokeAllowed` , true döndürür). Bkz. belirli [Coelcontrol:: IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).

##  <a name="isresultexpected"></a>CCmdTarget:: ısresultexyted

Bir `IsResultExpected` istemcinin bir Otomasyon işlevine çağrısından bir dönüş değeri bekleip bekmeyeceğini belirlemek için kullanın.

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>Dönüş Değeri

Bir Otomasyon işlevinin bir değer döndürmesi gerekiyorsa sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

OLE arabirimi, istemcinin bir işlev çağrısının sonucunu kullanıp kullanmadığını ya da yok saymadığını, MFC 'ye bilgi sağlar ve sırasıyla MFC bu bilgileri bir çağrının `IsResultExpected`sonucunu belirlemede kullanır. Dönüş değerinin üretimi zaman veya Kaynak yoğunluklu ise, dönüş değerini hesaplamadan önce bu işlevi çağırarak verimliliği artırabilirsiniz.

Bu işlev yalnızca bir kez 0 döndürür, bu sayede diğer otomasyon işlevlerindeki geçerli dönüş değerlerini istemcinin çağırdığı Otomasyon işlevinden çağırabilirsiniz.

`IsResultExpected`bir Otomasyon işlevi çağrısı devam ederken çağrılırsa sıfır dışında bir değer döndürür.

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
NULL değilse `OnCmdMsg` , komutu dağıtmadan *pHandlerInfo* yapısının *pTarget* ve *PMF* üyelerini doldurur. Genellikle, bu parametre NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu, Framework komut mimarisinin ana uygulama yordamlamasıdır.

Çalışma zamanında, `OnCmdMsg` diğer nesnelere bir komut gönderir veya asıl ileti eşleme aramasını yapan kök sınıfını `CCmdTarget::OnCmdMsg`çağırarak komutun kendisini işler. Varsayılan komut yönlendirmesinin tamamen açıklaması için bkz. [Ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).

Nadir durumlarda, çerçevenin standart komut yönlendirmesini genişletmek için bu üye işlevini geçersiz kılmak isteyebilirsiniz. Komut yönlendirme mimarisinin gelişmiş ayrıntıları için bkz. [teknik notta 21](../../mfc/tn021-command-and-message-routing.md) .

Geçersiz kıldıysanız `OnCmdMsg` *nCode*, komut bildirim kodu ve *nCode*değerine bağlı olan *pExtra*için uygun değeri sağlamanız gerekir. Aşağıdaki tabloda karşılık gelen değerleri listelenmektedir:

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
