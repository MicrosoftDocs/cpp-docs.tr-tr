---
title: CCmdTarget sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b76e4a0c0533ceb0200757f86f332d77c3b39ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
|[CCmdTarget::CCmdTarget](#ccmdtarget)|Oluşturan bir `CCmdTarget` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|İmleç bir kum saati imleç olarak görüntüler.|  
|[CCmdTarget::DoOleVerb](#dooleverb)|Eylemin gerçekleştirilmesi için bir OLE fiil tarafından belirtilen neden olur.|  
|[CCmdTarget::EnableAutomation](#enableautomation)|OLE Otomasyon için verir `CCmdTarget` nesnesi.|  
|[CCmdTarget::EnableConnections](#enableconnections)|Olay tetikleme bağlantı noktaları sağlar.|  
|[CCmdTarget::EnableTypeLib](#enabletypelib)|Bir nesnenin tür kitaplığı sağlar.|  
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|Önceki imleci geri döner.|  
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|Bir nesnenin OLE fiillerini sıralar.|  
|[CCmdTarget::FromIDispatch](#fromidispatch)|Bir işaretçi döndürür `CCmdTarget` ilişkili nesne `IDispatch` işaretçi.|  
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|Birincil gönderme arabirimi kimliğini alır.|  
|[CCmdTarget::GetIDispatch](#getidispatch)|Bir işaretçi döndürür `IDispatch` ilişkili nesne `CCmdTarget` nesne.|  
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|Bir nesneyi sağlar türü bilgileri arabirimleri sayısını alır.|  
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|Belirtilen GUID'sine karşılık gelen tür açıklamasını alır.|  
|[CCmdTarget::GetTypeLib](#gettypelib)|Bir işaretçi bir tür kitaplığı alır.|  
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|Tür kitaplığı önbelleğe alır.|  
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|Otomasyon yöntemi çağırma sağlar.|  
|[CCmdTarget::IsResultExpected](#isresultexpected)|Döndürür bir Otomasyon işlevi, sıfır olmayan bir değer döndürmesi.|  
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|Yönlendirir ve komut iletileri gönderir.|  
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|Son OLE başvurusu yayımlandıktan sonra temizler.|  
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|Kum Saati İmleci geri yükler.|  
  
## <a name="remarks"></a>Açıklamalar  
 İleti eşlemesi komutları veya iletileri bunları işlemek için yazma üye işlevleri yönlendirir. (Bir menü öğesi, komut düğmesi veya kısayol tuşu iletiden komutudur.)  
  
 Anahtar framework sınıfları türetilen `CCmdTarget` dahil [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md), ve [ CFrameWnd](../../mfc/reference/cframewnd-class.md). Yeni bir sınıf iletileri işlemek istiyorsanız, bunlardan birini sınıf türetin `CCmdTarget`-türetilmiş sınıfları. Nadiren öğesinden bir sınıf türetin `CCmdTarget` doğrudan.  
  
 Komut hedefleri genel bakış ve `OnCmdMsg` yönlendirme, bkz: [komut hedefleri](../../mfc/command-targets.md), [komut yönlendirme](../../mfc/command-routing.md), ve [eşleme iletileri](../../mfc/mapping-messages.md).  
  
 `CCmdTarget` bir kum saati imleci görüntü işleme üye işlevlerini içerir. Bir komut yürütmek için bir fark zaman aralığı yapılacak beklediğiniz Kum Saati İmleci görüntüler.  
  
 Gönderme haritalar, ileti eşlemeleri benzer, OLE Otomasyon kullanıma sunmak için kullanılan `IDispatch` işlevselliği. Bu arabirim göstererek (Visual Basic gibi) diğer uygulamalar uygulamanıza çağırabilirsiniz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCmdTarget`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="beginwaitcursor"></a>  CCmdTarget::BeginWaitCursor  
 Bir komut yürütmek için bir fark zaman aralığı yapılacak beklediğiniz imleci bir kum saati görüntülemek için bu işlevini çağırın.  
  
```  
void BeginWaitCursor();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Framework'te kullanıcı gibi ne zaman meşgul olduğunu göstermek için bu işlevi çağıran bir **CDocument** nesne yükler veya kendisi bir dosyaya kaydeder.  
  
 Eylemleri `BeginWaitCursor` her zaman diğer eylemler olarak gibi tek bir ileti işleyicisi dışında etkin olmayan `OnSetCursor` işleme, imleci değiştirebilirsiniz.  
  
 Çağrı `EndWaitCursor` önceki imleci geri yüklemek için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="ccmdtarget"></a>  CCmdTarget::CCmdTarget  
 Oluşturan bir `CCmdTarget` nesnesi.  
  
```  
CCmdTarget();
```  
  
##  <a name="dooleverb"></a>  CCmdTarget::DoOleVerb  
 Eylemin gerçekleştirilmesi için bir OLE fiil tarafından belirtilen neden olur.  
  
```  
BOOL DoOleVerb(
    LONG iVerb,  
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 `iVerb`  
 Fiilin sayısal tanımlayıcı.  
  
 `lpMsg`  
 İşaretçi [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) fiili çağrılan olay (örneğin, bir çift tıklatın) açıklayan yapısı.  
  
 `hWndParent`  
 Nesne içeren belge penceresine tanıtıcısı.  
  
 `lpRect`  
 İşaretçi [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) içeren nesneyi tanımlayan piksel cinsinden koordinatları yapısını dikdörtgende çevreleyen *hwndParent*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE başarılı, aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi temelde uygulamasıdır [Rpc_e_serverfault](http://msdn.microsoft.com/library/windows/desktop/ms694508). Olası eylemler tarafından numaralandırılır [CCmdTarget::EnumOleVerbs](#enumoleverbs).  
  
##  <a name="enableautomation"></a>  CCmdTarget::EnableAutomation  
 OLE Otomasyon nesnesi için etkinleştirmek için bu işlevini çağırın.  
  
```  
void EnableAutomation();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, genellikle nesnenizin oluşturucusundan çağrılır ve gönderme harita sınıfı için tanımlanmış ise yalnızca çağrılmalıdır. Otomasyon hakkında daha fazla bilgi için makalelerine bakın [Otomasyon istemcileri](../../mfc/automation-clients.md) ve [otomasyon sunucuları](../../mfc/automation-servers.md).  
  
##  <a name="enableconnections"></a>  CCmdTarget::EnableConnections  
 Olay tetikleme bağlantı noktaları sağlar.  
  
```  
void EnableConnections();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlantı noktaları etkinleştirmek için türetilmiş sınıf oluşturucu bu üye işlevini çağırın.  
  
##  <a name="enabletypelib"></a>  CCmdTarget::EnableTypeLib  
 Bir nesnenin tür kitaplığı sağlar.  
  
```  
void EnableTypeLib();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevini çağırın oluşturucuda, `CCmdTarget`-türü bilgileri sağlıyorsa, nesne türetilmiş. Bilgi Bankası makalesi Q185720, daha fazla bilgi için bkz: "nasıl yapılır: bir MFC Otomasyon sunucusundan tür bilgiler sağlar." Bilgi Bankası makaleleri kullanılabilir [ http://support.microsoft.com ](http://support.microsoft.com/).  
  
##  <a name="endwaitcursor"></a>  CCmdTarget::EndWaitCursor  
 Adlı sonra bu işlevi çağırmak `BeginWaitCursor` önceki imleci Kum Saati İmleci döndürmek için üye işlevi.  
  
```  
void EndWaitCursor();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kum Saati İmleci çağırdı sonra framework de bu üye işlevi çağırır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="enumoleverbs"></a>  CCmdTarget::EnumOleVerbs  
 Bir nesnenin OLE fiillerini sıralar.  
  
```  
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppenumOleVerb`  
 Bir işaretçi bir işaretçi bir [IEnumOLEVERB](http://msdn.microsoft.com/library/windows/desktop/ms695084) arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne en az bir OLE fiil destekliyorsa TRUE (Bu durumda \* `ppenumOleVerb` işaret eden bir **IEnumOLEVERB** Numaralandırıcı arabirimi), aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi temelde uygulamasıdır [IOleObject::EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781).  
  
##  <a name="fromidispatch"></a>  CCmdTarget::FromIDispatch  
 Eşlemek için bu işlevi çağırmak bir `IDispatch` içine bir sınıf üyesi işlevleri Otomasyon alınan işaretçi `CCmdTarget` arabirimleri uygulayan nesne `IDispatch` nesne.  
  
```  
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDispatch`  
 Bir işaretçi bir `IDispatch` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `CCmdTarget` ilişkili nesne `lpDispatch`. Bu işlev, döndürür **NULL** varsa `IDispatch` nesne Microsoft Foundation Class tanınmıyor `IDispatch` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevin sonucu üye işlevi çağrısı tersidir `GetIDispatch`.  
  
##  <a name="getdispatchiid"></a>  CCmdTarget::GetDispatchIID  
 Birincil gönderme arabirimi kimliğini alır.  
  
```  
virtual BOOL GetDispatchIID(IID* pIID);
```  
  
### <a name="parameters"></a>Parametreler  
 *pIID*  
 Bir işaretçi bir arabirim kimliği (bir [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931)).  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE başarılı, aksi takdirde FALSE. Başarılı olursa, \* *pIID* birincil gönderme arabirimi kimliğine ayarlayın  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen sınıflar bu üye işlevi geçersiz kılma (geçersiz kılınmazsa, `GetDispatchIID` FALSE değerini döndürür). Bkz: [COleControl](../../mfc/reference/colecontrol-class.md).  
  
 Bilgi Bankası makalesi Q185720, daha fazla bilgi için bkz: "nasıl yapılır: bir MFC Otomasyon sunucusundan tür bilgiler sağlar." Bilgi Bankası makaleleri kullanılabilir [ http://support.microsoft.com ](http://support.microsoft.com/).  
  
##  <a name="getidispatch"></a>  CCmdTarget::GetIDispatch  
 Almak için bu üye işlevini çağırın `IDispatch` işaretçi bir Otomasyon yönteminden bu döndürür bir `IDispatch` işaretçi veya sürer bir `IDispatch` başvuruya işaretçi.  
  
```  
LPDISPATCH GetIDispatch(BOOL bAddRef);
```  
  
### <a name="parameters"></a>Parametreler  
 *bAddRef*  
 Nesne başvurusu sayısı artırılamıyor belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `IDispatch` Nesnesiyle ilişkili işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu çağrı nesneleri için `EnableAutomation` etkinse, Otomasyon yapmadan kendi kurucularda bu işlev bir işaretçi Foundation sınıf uygulamasını döndürür `IDispatch` üzerinden iletişim kurmasına istemcileri tarafından kullanılan `IDispatch` arabirimi. Bu işlevi çağırmak, otomatik olarak ekler işaretçi başvuru yapılan bir çağrı yapmak gerekli değildir [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379).  
  
##  <a name="gettypeinfocount"></a>  CCmdTarget::GetTypeInfoCount  
 Bir nesneyi sağlar türü bilgileri arabirimleri sayısını alır.  
  
```  
virtual UINT GetTypeInfoCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tür bilgileri arabirimleri sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi temelde uygulayan [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12).  
  
 Türetilen sınıflar (0 veya 1) sağlanan türü bilgileri arabirimleri sayısı döndürmek için bu işleve geçersiz kılmalısınız. Geçersiz kılınmazsa, **GetTypeInfoCount** 0 döndürür. Geçersiz kılmak için kullanın [ımplement_oletypelıb](../../mfc/reference/type-library-access.md#implement_oletypelib) de uygulayan makrosu `GetTypeLib` ve `GetTypeLibCache`.  
  
##  <a name="gettypeinfoofguid"></a>  CCmdTarget::GetTypeInfoOfGuid  
 Belirtilen GUID'sine karşılık gelen tür açıklamasını alır.  
  
```  
HRESULT GetTypeInfoOfGuid(
    LCID lcid,  
    const GUID& guid,  
    LPTYPEINFO* ppTypeInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `lcid`  
 Yerel ayar tanımlayıcısı ( `LCID`).  
  
 `guid`  
 [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931) türü açıklaması.  
  
 `ppTypeInfo`  
 Bir işaretçi işaretçi `ITypeInfo` arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı veya başarısızlık çağrının belirten bir HRESULT. Başarılı olursa, * `ppTypeInfo` işaret türü bilgileri arabirimi.  
  
##  <a name="gettypelib"></a>  CCmdTarget::GetTypeLib  
 Bir işaretçi bir tür kitaplığı alır.  
  
```  
virtual HRESULT GetTypeLib(
    LCID lcid,  
    LPTYPELIB* ppTypeLib);
```  
  
### <a name="parameters"></a>Parametreler  
 `lcid`  
 Yerel ayar tanımlayıcısı ( `LCID`).  
  
 `ppTypeLib`  
 Bir işaretçi bir işaretçi `ITypeLib` arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı veya başarısızlık çağrının belirten bir HRESULT. Başarılı olursa, * `ppTypeLib` noktaları için tür kitaplığı arabirim.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen sınıflar bu üye işlevi geçersiz kılma (geçersiz kılınmazsa, `GetTypeLib` TYPE_E_CANTLOADLIBRARY döndürür). Kullanım [ımplement_oletypelıb](../../mfc/reference/type-library-access.md#implement_oletypelib) de uygulayan makrosu `GetTypeInfoCount` ve `GetTypeLibCache`.  
  
##  <a name="gettypelibcache"></a>  CCmdTarget::GetTypeLibCache  
 Tür kitaplığı önbelleğe alır.  
  
```  
virtual CTypeLibCache* GetTypeLibCache();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir **CTypeLibCache** nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen sınıflar bu üye işlevi geçersiz kılma (geçersiz kılınmazsa, **GetTypeLibCache** NULL döndürür). Kullanım [ımplement_oletypelıb](../../mfc/reference/type-library-access.md#implement_oletypelib) de uygulayan makrosu `GetTypeInfoCount` ve `GetTypeLib`.  
  
##  <a name="isinvokeallowed"></a>  CCmdTarget::IsInvokeAllowed  
 Bu işlev MFC'nin uygulaması tarafından çağrılır **IDispatch::Invoke** verilen Otomasyon yöntemi olup olmadığı belirlenemiyor (tarafından tanımlanan `dispid`) çağrılabilir.  
  
```  
virtual BOOL IsInvokeAllowed(DISPID dispid);
```  
  
### <a name="parameters"></a>Parametreler  
 `dispid`  
 Bir dağıtım kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE yöntemi çağrılır, aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `IsInvokeAllowed` TRUE döndürür **Invoke** ; yöntemini çağırmak için geçer Aksi halde, `Invoke` , E_UNEXPECTED döndürme başarısız olur.  
  
 Türetilen sınıflar uygun değer döndürmek için bu işlevi geçersiz kılma (geçersiz kılınmazsa, `IsInvokeAllowed` TRUE değerini döndürür). Özellikle bkz [COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).  
  
##  <a name="isresultexpected"></a>  CCmdTarget::IsResultExpected  
 Kullanım `IsResultExpected` bir istemci kendi çağrısından bir Otomasyon işlevi için dönüş değeri bekler olup olmadığını belirlemek için.  
  
```  
BOOL IsResultExpected();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir Otomasyon işlevi bir değer döndürmesi, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İstemci kullanarak veya diğer bir işlev çağrısının sonucunu yoksayılıyor olup olmadığı hakkında bilgi MFC OLE arabirimi sağlar ve MFC sırayla bu bilgileri bir çağrı sonucunu belirlemek üzere kullanır `IsResultExpected`. Dönüş değeri üretimini zaman - veya -yoğun kaynak, ise dönüş değeri computing önce bu işlevini çağırarak verimliliğini artırabilir.  
  
 Bu işlev, böylece bunları Otomasyon işlevinden, çağırırsanız diğer Otomasyon işlevlerden geçerli dönüş değerleri alırsınız istemci yalnızca çağırdı sonra 0 döndürür.  
  
 `IsResultExpected` bir Otomasyon işlev çağrısı ediyor olmadığında çağrıldıklarında sıfır olmayan bir değer döndürür.  
  
##  <a name="oncmdmsg"></a>  CCmdTarget::OnCmdMsg  
 Rota ve komut iletileri gönderme ve komut kullanıcı arabirimi nesnelerini güncelleştirme işlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Komut kimliğini içerir.  
  
 `nCode`  
 Komut bildirim kodu tanımlar. Bkz: **açıklamalar** değerleri hakkında daha fazla bilgi için `nCode`.  
  
 `pExtra`  
 Değeri göre kullanılan `nCode`. Bkz: **açıklamalar** hakkında daha fazla bilgi için `pExtra`.  
  
 `pHandlerInfo`  
 Aksi takdirde **NULL**, `OnCmdMsg` doldurur **pTarget** ve **pmf** üyeleri `pHandlerInfo` komutu göndermeyi yerine yapısı. Genellikle, bu parametre olmalıdır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti işleniyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Ana uygulama yordamı framework komut mimarisinin budur.  
  
 Çalışma zamanında `OnCmdMsg` komut diğer nesnelere dağıtır ya da kök sınıfı çağırarak komutu işlediği `CCmdTarget::OnCmdMsg`, hangi gerçek ileti eşleme arama yapar. Varsayılan komut yönlendirme tam açıklama için bkz [ileti işleme ve eşleme konuları](../../mfc/message-handling-and-mapping.md).  
  
 Framework'ün genişletmek için bu üye işlevi geçersiz kılmak isteyebilirsiniz nadir durumlarda, standart komut yönlendirme. Başvurmak [Teknik Not 21](../../mfc/tn021-command-and-message-routing.md) komut yönlendirme mimarisinin Gelişmiş Ayrıntılar için.  
  
 Geçersiz kılarsanız `OnCmdMsg`, uygun değeri sağlamalısınız `nCode`, komut bildirim kodu ve `pExtra`, bağlı olan değerine göre `nCode`. Aşağıdaki tabloda, bunlara karşılık gelen değerler listelenmektedir:  
  
|`nCode` Değer|`pExtra` Değer|  
|-------------------|--------------------|  
|CN_COMMAND|[Ccmduı](../../mfc/reference/ccmdui-class.md)*|  
|CN_EVENT|AFX_EVENT *|  
|CN_UPDATE_COMMAND_UI|Ccmduı *|  
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)*|  
|CN_OLE_UNREGISTER|NULL|  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]  
  
##  <a name="onfinalrelease"></a>  CCmdTarget::OnFinalRelease  
 Son OLE başvurusu için veya nesnesinden yayımlandığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnFinalRelease();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu durumda özel işleme sağlamak için bu işlevi geçersiz kılar. Varsayılan uygulama nesneyi siler.  
  
##  <a name="restorewaitcursor"></a>  CCmdTarget::RestoreWaitCursor  
 (Örneğin, bir ileti kutusu açtığı ya da uzun bir işlem sırasında ortasında kapalı sonra) sistem imleci değiştikten sonra uygun Kum Saati İmleci geri yüklemek için bu işlevini çağırın.  
  
```  
void RestoreWaitCursor();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek ACDUAL](../../visual-cpp-samples.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Ccmduı sınıfı](../../mfc/reference/ccmdui-class.md)   
 [CDocument sınıfı](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)   
 [CWinApp sınıfı](../../mfc/reference/cwinapp-class.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CView sınıfı](../../mfc/reference/cview-class.md)   
 [CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)   
 [COleDispatchDriver Sınıfı](../../mfc/reference/coledispatchdriver-class.md)
