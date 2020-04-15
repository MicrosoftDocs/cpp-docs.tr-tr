---
title: CWinThread Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CWinThread
- AFXWIN/CWinThread
- AFXWIN/CWinThread::CWinThread
- AFXWIN/CWinThread::CreateThread
- AFXWIN/CWinThread::ExitInstance
- AFXWIN/CWinThread::GetMainWnd
- AFXWIN/CWinThread::GetThreadPriority
- AFXWIN/CWinThread::InitInstance
- AFXWIN/CWinThread::IsIdleMessage
- AFXWIN/CWinThread::OnIdle
- AFXWIN/CWinThread::PostThreadMessage
- AFXWIN/CWinThread::PreTranslateMessage
- AFXWIN/CWinThread::ProcessMessageFilter
- AFXWIN/CWinThread::ProcessWndProcException
- AFXWIN/CWinThread::PumpMessage
- AFXWIN/CWinThread::ResumeThread
- AFXWIN/CWinThread::Run
- AFXWIN/CWinThread::SetThreadPriority
- AFXWIN/CWinThread::SuspendThread
- AFXWIN/CWinThread::m_bAutoDelete
- AFXWIN/CWinThread::m_hThread
- AFXWIN/CWinThread::m_nThreadID
- AFXWIN/CWinThread::m_pActiveWnd
- AFXWIN/CWinThread::m_pMainWnd
helpviewer_keywords:
- CWinThread [MFC], CWinThread
- CWinThread [MFC], CreateThread
- CWinThread [MFC], ExitInstance
- CWinThread [MFC], GetMainWnd
- CWinThread [MFC], GetThreadPriority
- CWinThread [MFC], InitInstance
- CWinThread [MFC], IsIdleMessage
- CWinThread [MFC], OnIdle
- CWinThread [MFC], PostThreadMessage
- CWinThread [MFC], PreTranslateMessage
- CWinThread [MFC], ProcessMessageFilter
- CWinThread [MFC], ProcessWndProcException
- CWinThread [MFC], PumpMessage
- CWinThread [MFC], ResumeThread
- CWinThread [MFC], Run
- CWinThread [MFC], SetThreadPriority
- CWinThread [MFC], SuspendThread
- CWinThread [MFC], m_bAutoDelete
- CWinThread [MFC], m_hThread
- CWinThread [MFC], m_nThreadID
- CWinThread [MFC], m_pActiveWnd
- CWinThread [MFC], m_pMainWnd
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
ms.openlocfilehash: f2e95dd3ba8be31633590e37d95dedc8749ebdd8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367415"
---
# <a name="cwinthread-class"></a>CWinThread Sınıfı

Bir uygulama içinde yürütme iş parçacığı temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CWinThread : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CWinThread::CWinThread](#cwinthread)|Bir `CWinThread` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CWinThread::CreateThread](#createthread)|Bir `CWinThread` nesnenin yürütülmesini başlatır.|
|[CWinThread::ExitInstance](#exitinstance)|İş parçacığısona erdiğinde temizlemek için geçersiz kılın.|
|[CWinThread::GetMainWnd](#getmainwnd)|İş parçacığı için ana pencereye bir işaretçi alır.|
|[CWinThread::GetThreadPriority](#getthreadpriority)|Geçerli iş parçacığının önceliğini alır.|
|[CWinThread::InitInstance](#initinstance)|İş parçacığı örneği başlatma gerçekleştirmek için geçersiz kılma.|
|[CWinThread::IsidleMessage](#isidlemessage)|Özel iletileri denetler.|
|[CwinThread::Onidle](#onidle)|İş parçacığına özgü boşta zaman işlemegerçekleştirmek için geçersiz kılın.|
|[CWinThread::PostThreadMessage](#postthreadmessage)|Başka `CWinThread` bir nesneye ileti gönderir.|
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|İletileri Windows işlevlerine gönderilmeden önce filtreler [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage).|
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|Uygulamaya ulaşmadan önce belirli iletileri yakalar.|
|[CWinThread::ProcessWndProcException](#processwndprocexception)|İş parçacığının iletisi ve komut işleyicileri tarafından atılan tüm işlenmemiş özel durumları yakalar.|
|[CWinThread::PumpMessage](#pumpmessage)|İş parçacığının ileti döngüsüiçerir.|
|[CWinThread::ResumeThread](#resumethread)|İş parçacığının askıya alma sayısını eriter.|
|[CWinThread::Çalıştır](#run)|İleti pompası ile iş parçacıkları için kontrol işlevi. Varsayılan ileti döngüsüözelleştirmek için geçersiz kılma.|
|[CWinThread::SetThreadPriority](#setthreadpriority)|Geçerli iş parçacığının önceliğini ayarlar.|
|[CWinThread::SuspendThread](#suspendthread)|İş parçacığının askıya alma sayısını artımlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CWinThread::operatör HANDLE](#operator_handle)|Nesnenin tutamacını `CWinThread` alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CWinThread::m_bAutoDelete](#m_bautodelete)|İş parçacığı sonlandırma nesnesini yok etmek için olup olmadığını belirtir.|
|[CWinThread::m_hThread](#m_hthread)|Geçerli iş parçacığına işle.|
|[CWinThread::m_nThreadID](#m_nthreadid)|Geçerli iş parçacığının kimliği.|
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|OLE sunucusu yerinde etkin olduğunda kapsayıcı uygulamasının ana penceresini işaretleyin.|
|[CWinThread::m_pMainWnd](#m_pmainwnd)|Uygulamanın ana penceresi için bir işaretçi tutar.|

## <a name="remarks"></a>Açıklamalar

Yürütme ana iş parçacığı genellikle türetilen `CWinApp`bir nesne tarafından sağlanır; `CWinApp` `CWinThread`türetilmiştir. Ek `CWinThread` nesneler, belirli bir uygulama içinde birden çok iş parçacığı sağlar.

Destekleyen iki genel iş parçacığı `CWinThread` türü vardır: alt iş parçacıkları ve kullanıcı arabirimi iş parçacıkları. Alt iş parçacıklarının ileti pompası yoktur: örneğin, elektronik tablo uygulamasında arka plan hesaplamaları gerçekleştiren bir iş parçacığı. Kullanıcı arabirimi iş parçacıkları, sistemden alınan bir ileti pompasına ve işlem iletilerine sahiptir. [CWinApp](../../mfc/reference/cwinapp-class.md) ve ondan türetilen sınıflar kullanıcı arabirimi iş parçacıkları örnekleridir. Diğer kullanıcı arabirimi iş parçacıkları da `CWinThread`doğrudan türetilebilir.

Sınıf `CWinThread` nesneleri genellikle iş parçacığı süresince vardır. Bu davranışı değiştirmek istiyorsanız, [m_bAutoDelete](#m_bautodelete) FALSE olarak ayarlayın.

Sınıf, `CWinThread` kodunuzu ve MFC'yi tamamen iş parçacığı için güvenli hale getirmek için gereklidir. İş parçacığına özgü bilgileri korumak için çerçeve tarafından `CWinThread` kullanılan iş parçacığı yerel verileri nesneler tarafından yönetilir. İş parçacığı yerel `CWinThread` verileri işlemek için bu bağımlılık nedeniyle, MFC kullanan herhangi bir iş parçacığı MFC tarafından oluşturulmalıdır. Örneğin, çalışma zamanı işlevi tarafından oluşturulan bir iş parçacığı [_beginthread _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) herhangi bir MFC API's kullanamazsınız.

Bir iş parçacığı oluşturmak için [AfxBeginThread'i](application-information-and-management.md#afxbeginthread)arayın. Bir alt veya kullanıcı arabirimi iş parçacığı isteyip istemediğiniz bağlı olarak iki form vardır. Kullanıcı arabirimi iş parçacığı istiyorsanız, `AfxBeginThread` türetilmiş `CRuntimeClass` sınıfınızın `CWinThread`işaretçisine geçirin. Bir alt iş parçacığı oluşturmak istiyorsanız, bir işaretçiye `AfxBeginThread` denetleme işlevine ve parametreye denetleme işlevine geçirin. Hem alt iş parçacıkları hem de kullanıcı arabirimi iş parçacıkları için, önceliği, yığın boyutunu, oluşturma bayraklarını ve güvenlik özniteliklerini değiştiren isteğe bağlı parametreler belirtebilirsiniz. `AfxBeginThread`yeni `CWinThread` nesnenize bir işaretçi döndürecektir.

Çağırmak `AfxBeginThread`yerine, türetilmiş `CWinThread`bir nesne oluşturup sonra arayabilirsiniz. `CreateThread` Bu iki aşamalı yapı yöntemi, ardışık oluşturma `CWinThread` ve iş parçacığı yürütmeleri sonlandırma arasındaki nesneyi yeniden kullanmak istiyorsanız yararlıdır.

Hakkında daha `CWinThread`fazla bilgi için, [C++ ve MFC ile Multithreading, Multithreading:](../../parallel/multithreading-with-cpp-and-mfc.md) [Kullanıcı Arabirimi İş parçacığı oluşturma,](../../parallel/multithreading-creating-user-interface-threads.md) [Multithreading: İşçi İş parçacığı oluşturma](../../parallel/multithreading-creating-worker-threads.md)ve Çoklu İş [Parçacığı: Senkronizasyon Sınıfları Nasıl Kullanılır](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`CWinThread`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cwinthreadcreatethread"></a><a name="createthread"></a>CWinThread::CreateThread

Arama işleminin adres alanı içinde yürütülecek bir iş parçacığı oluşturur.

```
BOOL CreateThread(
    DWORD dwCreateFlags = 0,
    UINT nStackSize = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>Parametreler

*dwCreateFlags*<br/>
İş parçacığının oluşturulmasını denetleyen ek bir bayrak belirtir. Bu bayrak iki değerden birini içerebilir:

- CREATE_SUSPENDED İş parçacığıbir askıya alma sayısı ile başlatın. Iş parçacığı çalışmaya başlamadan `CWinThread` [önce, nesnenin m_bAutoDelete](#m_bautodelete) veya türemiş sınıfınızın herhangi bir üyesi gibi herhangi bir üye verisini başlatmayı istiyorsanız CREATE_SUSPENDED kullanın. Başlatma işleminiz tamamlandıktan sonra, iş parçacığı nın çalışmasını başlatmak için [CWinThread::ResumeThread'i](#resumethread) kullanın. İş parçacığı çağrılana `CWinThread::ResumeThread` kadar yürütülmez.

- **0** Oluşturmaişleminden hemen sonra iş parçacığı başlatın.

*nStackSize*<br/>
Yeni iş parçacığı için yığının baytboyutu belirtir. **0**ise, yığın boyutu işlemin birincil iş parçacığı ile aynı boyutta varsayılan.

*lpSecurityAttrs*<br/>
İş parçacığı için güvenlik özniteliklerini belirten [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bir yapıya işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı başarıyla oluşturulursa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir `AfxBeginThread` iş parçacığı nesnesi oluşturmak ve tek bir adımda yürütmek için kullanın. İş `CreateThread` parçacığı yürütmeleri ardışık oluşturma ve sonlandırma arasında iş parçacığı nesnesini yeniden kullanmak istiyorsanız kullanın.

## <a name="cwinthreadcwinthread"></a><a name="cwinthread"></a>CWinThread::CWinThread

Bir `CWinThread` nesne inşa eder.

```
CWinThread();
```

### <a name="remarks"></a>Açıklamalar

İş parçacığının yürütülmesini başlatmak için [CreateThread](#createthread) üye işlevini arayın. Genellikle [AfxBeginThread](application-information-and-management.md#afxbeginthread)çağırarak iş parçacığı oluşturacak , bu `CreateThread`yapıcı ve çağıracak .

## <a name="cwinthreadexitinstance"></a><a name="exitinstance"></a>CWinThread::ExitInstance

İş parçacığının bu örneğinden çıkmak için nadiren geçersiz kılınan [Run](#run) üye işlevi içinden veya [InitInstance'a](#initinstance) yapılan bir çağrı başarısız olursa, çerçeve tarafından çağrılır.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığının çıkış kodu; 0 hata olmadığını gösterir ve 0'dan büyük değerler hata gösterir. Bu değer [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)çağırarak alınabilir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini üye işlevin `Run` içinde değil, herhangi bir yerden aramayın. Bu üye işlev yalnızca kullanıcı arabirimi iş parçacıklarında kullanılır.

Bu işlevin varsayılan `CWinThread` [uygulaması, m_bAutoDelete](#m_bautodelete) DOĞRU ise nesneyi siler. İş parçacığınız sonlandığında ek temizleme gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Uygulamanız, `ExitInstance` kodunuz yürütüldükten sonra taban sınıfın sürümünü aramalıdır.

## <a name="cwinthreadgetmainwnd"></a><a name="getmainwnd"></a>CWinThread::GetMainWnd

Uygulamanız bir OLE sunucusuysa, uygulama nesnesinin `m_pMainWnd` üyesine doğrudan atıfta bulunarak olmak yerine uygulamanın etkin ana penceresine bir işaretçi almak için bu işlevi arayın.

```
virtual CWnd* GetMainWnd();
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlev, iki tür pencereden birine bir işaretçiyi döndürür. İş parçacığınız bir OLE sunucusunun parçasıysa ve etkin bir kapsayıcının içinde etkin olan bir nesne varsa, bu `CWinThread` işlev [CWinApp:m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) nesnenin veri üyesini döndürür.

Bir kapsayıcı içinde etkin olan bir nesne yoksa veya uygulamanız bir OLE sunucusu değilse, bu işlev iş parçacığı nesnenizin [m_pMainWnd](#m_pmainwnd) veri üyesini döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı arabirimi iş parçacıkları için bu, doğrudan `m_pActiveWnd` uygulama nesnenizin üyesine atıfta bulunmaya eşdeğerdir.

Uygulamanız bir OLE sunucusu değilse, bu işlevi aramak doğrudan uygulama `m_pMainWnd` nesnenizin üyesine atıfta bulunmaya eşdeğerdir.

Varsayılan davranışı değiştirmek için bu işlevi geçersiz kılın.

## <a name="cwinthreadgetthreadpriority"></a><a name="getthreadpriority"></a>CWinThread::GetThreadPriority

Bu iş parçacığının geçerli iş parçacığı öncelik düzeyini alır.

```
int GetThreadPriority();
```

### <a name="return-value"></a>Dönüş Değeri

Öncelik sınıfı içindeki geçerli iş parçacığı öncelik düzeyi. Döndürülen değer, en yüksek öncelikten en düşük değere listelenen aşağıdakilerden biri olacaktır:

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

Bu öncelikler hakkında daha fazla bilgi için Windows SDK'daki [SetThreadPriority'e](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) bakın.

## <a name="cwinthreadinitinstance"></a><a name="initinstance"></a>CWinThread::InitInstance

`InitInstance`kullanıcı arabirimi iş parçacığının her yeni örneğini başlatmak için geçersiz kılınması gerekir.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Genellikle, iş parçacığı `InitInstance` ilk oluşturulduğunda tamamlanması gereken görevleri gerçekleştirmek için geçersiz kılarsınız.

Bu üye işlev yalnızca kullanıcı arabirimi iş parçacıklarında kullanılır. [AfxBeginThread'e](application-information-and-management.md#afxbeginthread)geçen kontrol işlevinde alt iş parçacıklarının başlatılmasını gerçekleştirin.

## <a name="cwinthreadisidlemessage"></a><a name="isidlemessage"></a>CWinThread::IsidleMessage

Belirli iletiler oluşturulduktan sonra çağrılmasını engellemek `OnIdle` için bu işlevi geçersiz kılın.

```
virtual BOOL IsIdleMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
İşlenen geçerli iletiyi işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

İleti işledikten sonra `OnIdle` çağrılması gerekiyorsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, göz `OnIdle` kırpan bakıcılar tarafından oluşturulan gereksiz fare iletileri ve iletileri sonra aramaz.

Bir uygulama kısa bir zamanlayıcı `OnIdle` oluşturduysa, sık sık çağrılacak ve performans sorunlarına neden olur. Böyle bir uygulamanın performansını artırmak `IsIdleMessage` için, aşağıdaki `CWinApp`gibi WM_TIMER iletileri denetlemek için uygulamanın türetilmiş sınıfında geçersiz kılma:

[!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]

Bu şekilde WM_TIMER taşıma kısa zamanlayıcılar kullanan uygulamaların performansını artıracaktır.

## <a name="cwinthreadm_bautodelete"></a><a name="m_bautodelete"></a>CWinThread::m_bAutoDelete

İş parçacığı sonlandırma sırasında nesnenin `CWinThread` otomatik olarak silinip silinmeyeceğini belirtir.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>Açıklamalar

Veri `m_bAutoDelete` üyesi BOOL türünün ortak değişkenidir.

Değeri, `m_bAutoDelete` alttaki iş parçacığı tanıtıcısının nasıl kapatılacağını etkilemez, ancak tutamacı kapatma zamanlamasını etkiler. `CWinThread` Nesne yok edildiğinde iş parçacığı tutamacı her zaman kapatılır.

## <a name="cwinthreadm_hthread"></a><a name="m_hthread"></a>CWinThread::m_hThread

Buna `CWinThread`bağlı iş parçacığına tut.

```
HANDLE m_hThread;
```

### <a name="remarks"></a>Açıklamalar

Veri `m_hThread` üyesi, HANDLE türünde ortak bir değişkendir. Yalnızca temel çekirdek iş parçacığı nesnesi şu anda varsa ve tutamaç henüz kapatılmadıysa geçerlidir.

CWinThread yıkıcı CloseHandle çağırır. `m_hThread` Iş parçacığı sona erdiğinde [m_bAutoDelete](#m_bautodelete) DOĞRU ise, CWinThread nesnesi yok edilir, bu da CWinThread nesnesine ve üye değişkenlerine yönelik işaretçileri geçersiz kılamaz. Üyenin `m_hThread` iş parçacığı çıkış değerini denetlemesi veya bir sinyal beklemesi gerekebilir. Iş parçacığı yürütme sırasında ve `m_hThread` sona erdikten sonra CWinThread `m_bAutoDelete` nesnesi ve üyesi tutmak için, iş parçacığı yürütme devam etmesine izin vermeden önce FALSE olarak ayarlayın. Aksi takdirde, iş parçacığı sonlandırabilir, CWinThread nesnesini yok edebilir ve kullanmaya çalışmadan önce tutamacı kapatabilir. Bu tekniği kullanırsanız, CWinThread nesnesinin silinmesorumlusundan siz sorumlusunuz.

## <a name="cwinthreadm_nthreadid"></a><a name="m_nthreadid"></a>CWinThread::m_nThreadID

Buna `CWinThread`bağlı iş parçacığının kimliği.

```
DWORD m_nThreadID;
```

### <a name="remarks"></a>Açıklamalar

Veri `m_nThreadID` üyesi DWORD türünün ortak değişkenidir. Yalnızca temel çekirdek iş parçacığı nesnesi şu anda varsa geçerlidir.
Ayrıca [m_hThread](#m_hthread) yaşam süresi yle ilgili açıklamalara bakın.

### <a name="example"></a>Örnek

  [AfxGetThread](application-information-and-management.md#afxgetthread)örneğine bakın.

## <a name="cwinthreadm_pactivewnd"></a><a name="m_pactivewnd"></a>CWinThread::m_pActiveWnd

İş parçacığınızın etkin pencere nesnesine bir işaretçi depolamak için bu veri üyesini kullanın.

```
CWnd* m_pActiveWnd;
```

### <a name="remarks"></a>Açıklamalar

Microsoft Hazırlık Sınıfı Kitaplığı, atıfta bulunulan pencere `m_pActiveWnd` kapatıldığında iş parçacığınızı otomatik olarak sonlandırır. Bu iş parçacığı bir uygulama için birincil iş parçacığı ise, uygulama da sonlandırılır. Bu veri üyesi NULL ise, uygulamanın `CWinApp` nesnesinin etkin penceresi devralınacaktır. `m_pActiveWnd`türünde `CWnd*`ortak bir değişkendir.

Genellikle, geçersiz kılarken bu üye `InitInstance`değişkeni ayarlarsınız. Bir alt iş parçacığında, bu veri üyesinin değeri üst iş parçacığından devralır.

## <a name="cwinthreadm_pmainwnd"></a><a name="m_pmainwnd"></a>CWinThread::m_pMainWnd

İş parçacığınızın ana pencere nesnesine bir işaretçi depolamak için bu veri üyesini kullanın.

```
CWnd* m_pMainWnd;
```

### <a name="remarks"></a>Açıklamalar

Microsoft Hazırlık Sınıfı Kitaplığı, atıfta bulunulan pencere `m_pMainWnd` kapatıldığında iş parçacığınızı otomatik olarak sonlandırır. Bu iş parçacığı bir uygulama için birincil iş parçacığı ise, uygulama da sonlandırılır. Bu veri üyesi NULL ise, uygulamanın `CWinApp` nesnesinin ana penceresi iş parçacığının ne zaman sonlandırılacağını belirlemek için kullanılır. `m_pMainWnd`türünde `CWnd*`ortak bir değişkendir.

Genellikle, geçersiz kılarken bu üye `InitInstance`değişkeni ayarlarsınız. Bir alt iş parçacığında, bu veri üyesinin değeri üst iş parçacığından devralır.

## <a name="cwinthreadonidle"></a><a name="onidle"></a>CwinThread::Onidle

Boşta zamanlı işleme gerçekleştirmek için bu üye işlevi geçersiz kılın.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Parametreler

*lSay*<br/>
İş parçacığının ileti kuyruğu `OnIdle` boş olduğunda her seferinde artıya artan sayaç çağrılır. Bu sayı, yeni bir ileti her işlenirken 0'a sıfırlanır. İletiyi işlemeden iş parçacığının boşta kalma süresini göreli olarak belirlemek için *lCount* parametresini kullanabilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Daha fazla boşta işlem süresi almak için sıfır olmayan; Daha fazla boşta işlem süresi gerekiyorsa 0.

### <a name="remarks"></a>Açıklamalar

`OnIdle`iş parçacığının ileti kuyruğu boş olduğunda varsayılan ileti döngüsünde çağrılır. Kendi arka plan boşta işleyici görevlerinizi çağırmak için geçersiz kılmanızı kullanın.

`OnIdle`ek boşta işlem süresi gerekmediğini belirtmek için 0 döndürmelidir. İleti sırası boşolduğunda ve yeni bir `OnIdle` ileti her işlendiğinde sıfırlandığında *lCount* parametresi her seferinde çağrılır. Bu sayıya göre farklı boşta yordamlarınızı arayabilirsiniz.

Bu üye işlevin varsayılan uygulaması geçici nesneleri ve kullanılmayan dinamik bağlantı kitaplıklarını bellekten serbest hale getirir.

Bu üye işlev yalnızca kullanıcı arabirimi iş parçacıklarında kullanılır.

Uygulama dönene kadar `OnIdle` iletileri işleyemediğinden, bu işlevde uzun görevler gerçekleştirmeyin.

## <a name="cwinthreadoperator-handle"></a><a name="operator_handle"></a>CWinThread::operatör HANDLE

Nesnenin tutamacını `CWinThread` alır.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, iş parçacığı nesnesinin tutamacı; aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Doğrudan Windows API'lerini aramak için tutamacı kullanın.

## <a name="cwinthreadpostthreadmessage"></a><a name="postthreadmessage"></a>CWinThread::PostThreadMessage

Kullanıcı tanımlı bir iletiyi `CWinThread` başka bir nesneye göndermek için çağrılır.

```
BOOL PostThreadMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*İleti*<br/>
Kullanıcı tanımlı iletinin kimliği.

*Wparam*<br/>
İlk ileti parametresi.

*Lparam*<br/>
İkinci ileti parametresi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İletilen ileti, ileti haritası makrosu ON_THREAD_MESSAGE tarafından uygun ileti işleyicisine eşlenir.

> [!NOTE]
> [PostThreadMessage'ı](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)aradiğinizde, ileti iş parçacığının ileti kuyruğuna yerleştirilir. Ancak, bu şekilde gönderilen iletiler bir pencereyle ilişkili olmadığından, MFC bunları ileti veya komut işleyicilerine göndermez. Bu iletileri işlemek için, CWinApp türetilmiş sınıfınızın `PreTranslateMessage()` işlevini geçersiz kılın ve iletileri el ile işleyin.

## <a name="cwinthreadpretranslatemessage"></a><a name="pretranslatemessage"></a>CWinThread::PreTranslateMessage

Windows işlevleri [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage)gönderilmeden önce pencere iletileri filtrelemek için bu işlevi geçersiz kılın.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
İşleme iletiyi içeren bir [MSG yapısına](/windows/win32/api/winuser/ns-winuser-msg) işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İleti tam olarak `PreTranslateMessage` işlenmişse ve daha fazla işlenmemeliyse sıfıra inmez. İleti normal şekilde işlenirse sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev yalnızca kullanıcı arabirimi iş parçacıklarında kullanılır.

## <a name="cwinthreadprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinThread::ProcessMessageFilter

Framework'ün kanca işlevi, belirli Windows iletilerini filtrelemek ve bunlara yanıt vermek için bu üye işlevi çağırır.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*Kod*<br/>
Bir kanca kodu belirtir. Bu üye işlev *lpMsg* nasıl işlenir belirlemek için kodu kullanır.

*lpMsg*<br/>
Windows [MSG yapısına](/windows/win32/api/winuser/ns-winuser-msg)işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kanca işlevi, uygulamanın normal ileti işlemesine gönderilmeden önce olayları işler.

Bu gelişmiş özelliği geçersiz kılarsanız, çerçevenin kanca işlemesini sürdürmek için taban sınıf sürümünü aradığından emin olun.

## <a name="cwinthreadprocesswndprocexception"></a><a name="processwndprocexception"></a>CWinThread::ProcessWndProcException

Çerçeve, işleyici işparçacığınızın iletisinizin veya komut işleyicilerinden birine atılan bir özel durum yakalamadığında bu üye işlevi çağırır.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*E*<br/>
Işlenmemiş bir özel durum işaret.

*pMsg*<br/>
Çerçevenin özel durum atmasına neden olan windows iletisi hakkında bilgi içeren bir [MSG yapısına](/windows/win32/api/winuser/ns-winuser-msg) işaret eder.

### <a name="return-value"></a>Dönüş Değeri

-1 WM_CREATE bir özel durum oluşturulursa; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi doğrudan aramayın.

Bu üye işlevin varsayılan uygulaması yalnızca aşağıdaki iletilerden oluşturulan özel durumları işler:

|Komut|Eylem|
|-------------|------------|
|Wm_create|Başarısız.|
|Wm_paınt|Etkilenen pencereyi doğrulayarak başka bir WM_PAINT iletisinin oluşturulmasını önleyin.|

Özel durumlarınızın genel olarak işlenmesini sağlamak için bu üye işlevini geçersiz kılın. Yalnızca varsayılan davranışı görüntülemek istiyorsanız temel işlevselliği arayın.

Bu üye işlev yalnızca ileti pompası olan iş parçacıklarında kullanılır.

## <a name="cwinthreadpumpmessage"></a><a name="pumpmessage"></a>CWinThread::PumpMessage

İş parçacığının ileti döngüsüiçerir.

```
virtual BOOL PumpMessage();
```

### <a name="remarks"></a>Açıklamalar

`PumpMessage`iş parçacığının ileti döngüsü içerir. `PumpMessage`iş parçacığının iletilerini `CWinThread` pompalamak için çağrılır. İletilerin `PumpMessage` işlenmesini zorlamak için doğrudan arayabilirsiniz veya varsayılan `PumpMessage` davranışını değiştirmek için geçersiz kılınabilirsiniz.

Doğrudan `PumpMessage` arama ve varsayılan davranış geçersiz kılma yalnızca gelişmiş kullanıcılar için önerilir.

## <a name="cwinthreadresumethread"></a><a name="resumethread"></a>CWinThread::ResumeThread

[AskThread](#suspendthread) üye işlevi veya CREATE_SUSPENDED bayrağı ile oluşturulan bir iş parçacığı tarafından askıya alınan bir iş parçacığı yürütme devam etmek için çağırdı.

```
DWORD ResumeThread();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığının önceki askıya alma sayısı başarılı olursa; `0xFFFFFFFF` aksi takdirde. İade değeri sıfırise, geçerli iş parçacığı askıya alınmadı. İade değeri birse, iş parçacığı askıya alındı, ancak şimdi yeniden başlatıldı. Birden büyük herhangi bir dönüş değeri iş parçacığının askıya alınması anlamına gelir.

### <a name="remarks"></a>Açıklamalar

Geçerli iş parçacığının askıya alma sayısı bir azaltılır. Askıya alma sayısı sıfıra düşürülürse, iş parçacığı yürütmeye devam eder; aksi takdirde iş parçacığı askıya kalır.

## <a name="cwinthreadrun"></a><a name="run"></a>CWinThread::Çalıştır

Kullanıcı arabirimi iş parçacıkları için varsayılan ileti döngüsü sağlar.

```
virtual int Run();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı tarafından döndürülen **bir int** değeri. Bu değer [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)çağırarak alınabilir.

### <a name="remarks"></a>Açıklamalar

`Run`uygulama [WM_QUIT](/windows/win32/winmsg/wm-quit) iletisi alana kadar Windows iletilerini alır ve gönderir. İş parçacığının ileti kuyruğu şu anda `Run` `OnIdle` ileti içermiyorsa, boşta zaman işleme yapmak için çağrılar. Gelen iletiler özel işleme için [PreTranslateMessage](#pretranslatemessage) üye işlevine ve standart klavye çevirisi için Windows işlevi [TranslateMessage'a](/windows/win32/api/winuser/nf-winuser-translatemessage) gider. Son olarak, [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevi çağrılır.

`Run`nadiren geçersiz kılınmıştır, ancak özel davranış uygulamak için geçersiz kılınabilirsiniz.

Bu üye işlev yalnızca kullanıcı arabirimi iş parçacıklarında kullanılır.

## <a name="cwinthreadsetthreadpriority"></a><a name="setthreadpriority"></a>CWinThread::SetThreadPriority

Bu işlev, öncelik sınıfı içindeki geçerli iş parçacığının öncelik düzeyini ayarlar.

```
BOOL SetThreadPriority(int nPriority);
```

### <a name="parameters"></a>Parametreler

*nÖncelikli*<br/>
Yeni iş parçacığı öncelik düzeyini öncelik sınıfı içinde belirtir. Bu parametre, en yüksek öncelikten en düşük değere listelenen aşağıdaki değerlerden biri olmalıdır:

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

Bu öncelikler hakkında daha fazla bilgi için Windows SDK'daki [SetThreadPriority'e](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) bakın.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yalnızca CreateThread başarıyla [döndükten](#createthread) sonra çağrılabilir.

## <a name="cwinthreadsuspendthread"></a><a name="suspendthread"></a>CWinThread::SuspendThread

Geçerli iş parçacığının askıya alma sayısını dalaştırır.

```
DWORD SuspendThread();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığının önceki askıya alma sayısı başarılı olursa; `0xFFFFFFFF` aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Herhangi bir iş parçacığı sıfırın üzerinde bir askıya alma sayısı varsa, bu iş parçacığı yürütülmez. Konu, [ResumeThread](#resumethread) üye işlevini çağırarak devam ettirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWinApp Sınıfı](../../mfc/reference/cwinapp-class.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)
