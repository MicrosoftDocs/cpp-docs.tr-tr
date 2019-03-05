---
title: CWinThread sınıfı
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
ms.openlocfilehash: 0e02f123580696519e59d828ec590456cbd2a81c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270143"
---
# <a name="cwinthread-class"></a>CWinThread sınıfı

Uygulamadaki bir iş parçacığını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CWinThread : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWinThread::CWinThread](#cwinthread)|Oluşturur bir `CWinThread` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinThread::CreateThread](#createthread)|Yürütülmesini başlatan bir `CWinThread` nesne.|
|[CWinThread::ExitInstance](#exitinstance)|İş parçacığı sonlandığında temizlemek için geçersiz kılın.|
|[CWinThread::GetMainWnd](#getmainwnd)|İş parçacığı için ana penceresine bir işaretçi alır.|
|[CWinThread::GetThreadPriority](#getthreadpriority)|Geçerli iş parçacığının önceliğini alır.|
|[CWinThread::InitInstance](#initinstance)|İş parçacığı örneği başlatma gerçekleştirmek için geçersiz kılın.|
|[CWinThread::IsIdleMessage](#isidlemessage)|Özel iletiler denetler.|
|[CWinThread::OnIdle](#onidle)|İş parçacığına özgü boşta kalma süresi işleme gerçekleştirmek için geçersiz kılın.|
|[CWinThread::PostThreadMessage](#postthreadmessage)|Başka bir iletiyi gönderir `CWinThread` nesne.|
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Windows işlevleri için dağıtılmadan önce iletileri filtreler [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage).|
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|Uygulamaya ulaşmadan önce belirli iletileri kesintiye uğratır.|
|[CWinThread::ProcessWndProcException](#processwndprocexception)|İş parçacığının ileti ve komut işleyicileri tarafından oluşturulan tüm işlenmeyen özel durumları yakalar.|
|[CWinThread::PumpMessage](#pumpmessage)|iş parçacığının ileti döngüsü içerir.|
|[CWinThread::ResumeThread](#resumethread)|Bir iş parçacığının azaltır sayısı askıya alın.|
|[CWinThread::Run](#run)|Bir ileti pompası ile iş parçacığı için denetleme işlevine. Varsayılan mesaj döngüsünü özelleştirmek için geçersiz kılın.|
|[CWinThread::SetThreadPriority](#setthreadpriority)|Geçerli iş parçacığının önceliğini ayarlar.|
|[CWinThread::SuspendThread](#suspendthread)|Bir iş parçacığının artışlarla sayısı askıya alın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CWinThread::operator TANITICISI](#operator_handle)|Tanıtıcısını alır `CWinThread` nesne.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CWinThread::m_bAutoDelete](#m_bautodelete)|Yok edilecek iş parçacığı sonlandırma nesne belirtir.|
|[CWinThread::m_hThread](#m_hthread)|Geçerli iş parçacığına işleyin.|
|[CWinThread::m_nThreadID](#m_nthreadid)|Geçerli iş parçacığının kimliği.|
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|OLE sunucusu yerinde etkin olduğunda kapsayıcı uygulamanın ana pencere işaretçisi.|
|[CWinThread::m_pMainWnd](#m_pmainwnd)|Uygulamanın ana penceresine bir işaretçi tutar.|

## <a name="remarks"></a>Açıklamalar

Ana iş parçacığı yürütme genellikle türetilen bir nesne tarafından sağlanan `CWinApp`; `CWinApp` türetilir `CWinThread`. Ek `CWinThread` nesneler belirli bir uygulama içinde birden çok iş parçacığı sağlar.

İş parçacıklarının iki genel tür vardır, `CWinThread` destekler: çalışan iş parçacığı ve kullanıcı arabirimi iş parçacıkları. Çalışan iş parçacıkları sahip hiçbir ileti pompası: Örneğin, bir elektronik tablo uygulamasında arka plan hesaplamalar yapan bir iş parçacığı. Kullanıcı arabirimi iş parçacığı bir ileti pompası sahip ve sistemden alınan iletileri. [CWinApp](../../mfc/reference/cwinapp-class.md) ve ondan türetilen sınıflar, kullanıcı arabirimi iş parçacığı örnekleri verilmiştir. Diğer kullanıcı arabirimi iş parçacıkları de doğrudan türetilebilir `CWinThread`.

Sınıfın nesneleri `CWinThread` genellikle iş parçacığı süresi boyunca mevcut. Bu davranışı değiştirmek isterseniz, [m_bAutoDelete](#m_bautodelete) false.

`CWinThread` Sınıfı, kod ve MFC tam iş parçacığı açısından güvenli hale getirmek için gerekli. İş parçacığına özgü bilgileri korumak için framework tarafından kullanılan iş parçacığı-yerel veri yönetilir `CWinThread` nesneleri. Bu bağımlılığa nedeniyle `CWinThread` iş parçacığı-yerel verileri işlemek için MFC kullanan herhangi bir iş parçacığı tarafından MFC ile oluşturulması gerekir. Örneğin, çalışma zamanı işlevi tarafından oluşturulan iş parçacığı [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) herhangi bir MFC API'sini kullanamazsınız.

Bir iş parçacığı oluşturmak için arama [AfxBeginThread](application-information-and-management.md#afxbeginthread). Bir çalışan veya kullanıcı arabirimi iş parçacığı istemenize bağlı olarak iki biçimi, vardır. Bir kullanıcı arabirimi iş parçacığı istiyorsanız geçirmek `AfxBeginThread` işaretçisi `CRuntimeClass` , `CWinThread`-türetilmiş sınıf. İş parçacığı oluşturmak istiyorsanız, geçirmek `AfxBeginThread` denetleme işlevine ve denetleyen işlev parametresi için bir işaretçi. Çalışan iş parçacığı ve kullanıcı arabirimi iş parçacıkları için öncelik, yığın boyutu, oluşturma bayrakları ve güvenlik öznitelikleri değiştiren isteğe bağlı parametreleri belirtebilirsiniz. `AfxBeginThread` Yeni bir işaretçi döndürür `CWinThread` nesne.

Çağırmak yerine `AfxBeginThread`, oluşturulabilir bir `CWinThread`-türetilmiş nesne ve sonra çağrı `CreateThread`. Bu iki aşamalı yapımı yöntemi yeniden kullanmak istiyorsanız yararlıdır `CWinThread` art arda gelen oluşturma ve yürütme iş parçacığı, sonlandırmalar arasında nesne.

Daha fazla bilgi için `CWinThread`, makalelere göz atın [çoklu iş parçacığı kullanımı C++ ve MFC ile](../../parallel/multithreading-with-cpp-and-mfc.md), [çoklu iş parçacığı kullanımı: Kullanıcı arabirimi iş parçacıkları oluşturma](../../parallel/multithreading-creating-user-interface-threads.md), [çoklu iş parçacığı kullanımı: Çalışan iş parçacıkları oluşturma](../../parallel/multithreading-creating-worker-threads.md), ve [çoklu iş parçacığı kullanımı: Eşitleme sınıflarının nasıl kullanılacağını](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CWinThread`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="createthread"></a>  CWinThread::CreateThread

Çağıran işlemin adres alanı içinde çalıştırmak için bir iş parçacığı oluşturur.

```
BOOL CreateThread(
    DWORD dwCreateFlags = 0,
    UINT nStackSize = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>Parametreler

*dwCreateFlags*<br/>
İş parçacığı oluşturmayı denetleyen ek bir bayrak belirtir. Bu bayrak, iki değerden birini içerebilir:

- CREATE_SUSPENDED iş parçacığı bir askıya alma sayımı Bir'den başlatın. Tüm üye verilerini başlatmak istiyorsanız CREATE_SUSPENDED kullanın `CWinThread` gibi nesne [m_bAutoDelete](#m_bautodelete) veya tüm üyeleri iş parçacığı çalışmaya başlamadan önce türetilmiş sınıf. Başlatma işleminiz tamamlandığında kullanın [CWinThread::ResumeThread](#resumethread) iş parçacığının çalışmasını başlatmak için. İş parçacığı kadar yürütülmez `CWinThread::ResumeThread` çağrılır.

- **0** oluşturduktan hemen sonra iş parçacığı başlatılamıyor.

*nStackSize*<br/>
Yeni iş parçacığı yığınının bayt cinsinden boyutunu belirtir. Varsa **0**, yığın boyutu varsayılan olarak, işlemin birincil iş parçacığının aynı boyutta için.

*lpSecurityAttrs*<br/>
İşaret eden bir [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) iş parçacığı için güvenlik özniteliklerini belirten yapısı.

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı başarıyla oluşturulursa, sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kullanım `AfxBeginThread` bir iş parçacığı nesnesi oluşturun ve tek bir adımda yürütmek için. Kullanım `CreateThread` art arda gelen oluşturma ve yürütme iş parçacığının sonlandırılması arasındaki iş parçacığı nesnesini yeniden kullanmak istiyorsanız.

##  <a name="cwinthread"></a>  CWinThread::CWinThread

Oluşturur bir `CWinThread` nesne.

```
CWinThread();
```

### <a name="remarks"></a>Açıklamalar

İş parçacığının yürütme başlamak için çağrı [CreateThread](#createthread) üye işlevi. Çağırarak iş parçacıkları genellikle oluşturacak [AfxBeginThread](application-information-and-management.md#afxbeginthread), bu oluşturucu çağıracaktır ve `CreateThread`.

##  <a name="exitinstance"></a>  CWinThread::ExitInstance

Bir nadiren geçersiz kılınan içinde framework tarafından çağırılır [çalıştırma](#run) üye işlevi, iş parçacığı'nın bu örneğinin çıkmak için veya bir çağrı, [InitInstance](#initinstance) başarısız olur.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığının çıkış kodu; 0 hata olduğunu gösterir ve değerleri 0'dan büyük bir hata gösterir. Bu değer, çağrılarak alınabilir [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread).

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi ancak içinde her yerden çağırmayın `Run` üye işlevi. Bu üye işlevi, yalnızca kullanıcı arabirimi iş parçacığı kullanılır.

Bu işlev varsayılan uygulamasını siler `CWinThread` , nesne [m_bAutoDelete](#m_bautodelete) true'dur. Bu işlev, iş parçacığı sonlandığında ek temizleme gerçekleştirmek istediğiniz geçersiz kılın. Uygulamanıza `ExitInstance` kodunuzu yürütüldükten sonra temel sınıfın sürüm çağırmalıdır.

##  <a name="getmainwnd"></a>  CWinThread::GetMainWnd

Uygulamanızı bir OLE sunucusu ise, yerine doğrudan söz konusu uygulamanın etkin ana penceresini bir işaretçi almak için bu işlevi çağırın `m_pMainWnd` üyesi uygulama nesnesi.

```
virtual CWnd* GetMainWnd();
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlev windows iki tür için bir işaretçi döndürür. Bu işlev, iş parçacığı OLE sunucusu bir parçasıdır ve etkin bir kapsayıcı içinde yerinde etkin bir nesnenin, döndürür [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) veri üyesi `CWinThread` nesne.

Bu işlev, bir kapsayıcıdaki yerinde etkin nesnesi yok veya uygulamanızı OLE sunucusu değil, döndürür [m_pMainWnd](#m_pmainwnd) veri üyesi, iş parçacığı nesnesi.

### <a name="remarks"></a>Açıklamalar

Kullanıcı arabirimi iş parçacıkları için bu için başvuran için eşdeğer `m_pActiveWnd` üyesi, uygulama nesnesi.

Uygulamanızı bir OLE sunucusu değil. sonra bu işlevi çağırmak için başvuran için eşdeğer `m_pMainWnd` üyesi, uygulama nesnesi.

Bu işlev varsayılan davranışı değiştirmek için geçersiz kılın.

##  <a name="getthreadpriority"></a>  CWinThread::GetThreadPriority

Bu iş parçacığının geçerli iş parçacığı öncelik düzeyi alır.

```
int GetThreadPriority();
```

### <a name="return-value"></a>Dönüş Değeri

Öncelik sınıfı içinde geçerli iş parçacığı öncelik düzeyi. Döndürülen değer, aşağıdakilerden birini olacaktır yüksek önceliğe düşüğe doğru listelenir:

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

Bu öncelikleri hakkında daha fazla bilgi için bkz. [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK.

##  <a name="initinstance"></a>  CWinThread::InitInstance

`InitInstance` kullanıcı arabirimi iş parçacığı her yeni örneği başlatmak için geçersiz kılınmalıdır.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Genellikle, geçersiz kılmanız `InitInstance` bir iş parçacığı ilk oluşturulduğunda, tamamlanması gereken görevleri gerçekleştirmek için.

Bu üye işlevi, yalnızca kullanıcı arabirimi iş parçacığı kullanılır. Denetleme işlevine geçirilen iş parçacıklarını başlatma gerçekleştirmek [AfxBeginThread](application-information-and-management.md#afxbeginthread).

##  <a name="isidlemessage"></a>  CWinThread::IsIdleMessage

Tutmak için bu işlevi geçersiz kılma `OnIdle` belirli iletileri oluşturulduktan sonra çağrılan öğesinden.

```
virtual BOOL IsIdleMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
İşlenen geçerli ileti işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Gösterimiyse `OnIdle` işlendikten sonra çağrılmalıdır ileti; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama arama `OnIdle` yedekli fare iletileri ve düzeltme işaretleri yanıp sönen tarafından oluşturulan iletileri.

Uygulamanın kısa bir zamanlayıcı oluşturduysa `OnIdle` sık, performans sorunlarına neden olmaktan çağrılır. Bu tür bir uygulamanın performansını artırmak için geçersiz kılma `IsIdleMessage` içinde uygulamanın `CWinApp`-türetilmiş sınıf WM_TIMER iletileri gibi denetlemek için:

[!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]

Bu şekilde WM_TIMER işleme kısa zamanlayıcılar kullanan uygulamaların performansını geliştirir.

##  <a name="m_bautodelete"></a>  CWinThread::m_bAutoDelete

Belirtir olup olmadığını `CWinThread` nesne iş parçacığı sonlandırma sırasında otomatik olarak da silinmelidir.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>Açıklamalar

`m_bAutoDelete` Veri üyesi BOOL türü genel değişkenidir.

Değerini `m_bAutoDelete` temel alınan iş parçacığı işleyicisini nasıl kapalı etkilemez. İş parçacığı işleyicisini daima kapatılır `CWinThread` nesnesi yok edildiğinde.

##  <a name="m_hthread"></a>  CWinThread::m_hThread

Şuna bağlı iş parçacığı tanıtıcı `CWinThread`.

```
HANDLE m_hThread;
```

### <a name="remarks"></a>Açıklamalar

`m_hThread` Veri üyesi tanıtıcı türü genel değişkenidir. Yalnızca şu anda iş parçacığı temelindeki varsa geçerlidir.

##  <a name="m_nthreadid"></a>  CWinThread::m_nThreadID

İş parçacığının kimliği için bağlı `CWinThread`.

```
DWORD m_nThreadID;
```

### <a name="remarks"></a>Açıklamalar

`m_nThreadID` Veri üyesi DWORD türü genel değişkenidir. Yalnızca şu anda iş parçacığı temelindeki varsa geçerlidir.

### <a name="example"></a>Örnek

  Örneğin bakın [AfxGetThread](application-information-and-management.md#afxgetthread).

##  <a name="m_pactivewnd"></a>  CWinThread::m_pActiveWnd

Bu veri üyesi, iş parçacığının etkin pencere nesnesine bir işaretçi depolamak için kullanın.

```
CWnd* m_pActiveWnd;
```

### <a name="remarks"></a>Açıklamalar

Pencere tarafından başvurulan, Microsoft Foundation Class Kitaplığı, iş parçacığı otomatik olarak sonlanacaktır `m_pActiveWnd` kapatılır. Bu iş parçacığı bir uygulama için birincil iş parçacığı ise, uygulama de sonlandırılacak. Bu veri üyesi NULL, uygulama için etkin pencere ise `CWinApp` nesne devralınır. `m_pActiveWnd` türü genel değişkenidir `CWnd*`.

Genellikle, geçersiz kılarken bu üye değişkeni ayarlamak `InitInstance`. Bir çalışan iş parçacığında bu veri üyesinin değerini ana iş parçacığından devralınır.

##  <a name="m_pmainwnd"></a>  CWinThread::m_pMainWnd

Bu veri üyesi, iş parçacığının ana pencere nesnesi için bir işaretçi depolamak için kullanın.

```
CWnd* m_pMainWnd;
```

### <a name="remarks"></a>Açıklamalar

Pencere tarafından başvurulan, Microsoft Foundation Class Kitaplığı, iş parçacığı otomatik olarak sonlanacaktır `m_pMainWnd` kapatılır. Bu iş parçacığı bir uygulama için birincil iş parçacığı ise, uygulama de sonlandırılacak. Bu veri üyesi NULL, uygulamanın ana penceresi ise `CWinApp` nesnesi, iş parçacığını sonlandırmak ne zaman belirlemek için kullanılır. `m_pMainWnd` türü genel değişkenidir `CWnd*`.

Genellikle, geçersiz kılarken bu üye değişkeni ayarlamak `InitInstance`. Bir çalışan iş parçacığında bu veri üyesinin değerini ana iş parçacığından devralınır.

##  <a name="onidle"></a>  CWinThread::OnIdle

Boşta kalma süresi işleme gerçekleştirmek için bu üye işlevini geçersiz kılar.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Parametreler

*lCount*<br/>
Her bir sayaç artırılır `OnIdle` iş parçacığının ileti kuyruğu boş olduğunda çağrılır. Bu sayı, yeni bir ileti işlendiği her zaman 0 olarak sıfırlanır. Kullanabileceğiniz *lCount* göreli iş parçacığı boş bir ileti işlemeden sürenin uzunluğunu belirlemek için parametre.

### <a name="return-value"></a>Dönüş Değeri

Daha fazla boşta işleme süresi almak için sıfır olmayan; Daha fazla boşta işleme süresi gerekliyse 0.

### <a name="remarks"></a>Açıklamalar

`OnIdle` iş parçacığının ileti kuyruğu boş olduğunda varsayılan mesaj döngüsünü çağrılır. Boşta işleyici görevler kendi arka plan çağırmak için geçersiz kılma kullanın.

`OnIdle` Ek boş kalma işleme süresi gerekli olduğunu belirtmek için 0 döndürmelidir. *LCount* parametresi her zaman artırılır `OnIdle` ileti kuyruğu boş ve 0 olarak yeni bir ileti işlendiği her erişimde sıfırlanacağını çağrılır. Bu sayısına göre farklı boşta yordamları çağırabilirsiniz.

Bu üye işlevinin varsayılan uygulama geçici nesneler ve kullanılmayan dinamik bağlantı kitaplıklarından bellek kazandırır.

Bu üye işlevi, yalnızca kullanıcı arabirimi iş parçacığı kullanılır.

Uygulama kadar iletileri işleyemediği `OnIdle` döndürür, bu işlevde harcanan verimsiz uzun görevlerden gerçekleştirmeyin.

##  <a name="operator_handle"></a>  CWinThread::operator TANITICISI

Tanıtıcısını alır `CWinThread` nesne.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, iş parçacığı nesnesi; tanıtıcısı Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Doğrudan Windows API çağırmak için bir tanıtıcı kullanın.

##  <a name="postthreadmessage"></a>  CWinThread::PostThreadMessage

Başka bir kullanıcı tanımlı bir ileti göndermek için çağrılan `CWinThread` nesne.

```
BOOL PostThreadMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*message*<br/>
Kullanıcı tanımlı iletinin kimliği.

*wParam*<br/>
İlk ileti parametresi.

*lParam*<br/>
İkinci ileti parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Postalanan ileti uygun ileti işleyicisi için ileti eşlemesi makronun ON_THREAD_MESSAGE eşlenir.

> [!NOTE]
> Çağırdığınızda [PostThreadMessage](/windows/desktop/api/winuser/nf-winuser-postthreadmessagea), ileti iş parçacığının ileti sırasına konur. Bu şekilde gönderilen iletiler pencere ile ilişkili olmadığından, ancak, MFC bunları ileti veya komut işleyicilerini dağıtacağı değil. Bu iletileri işlemek için geçersiz kılma `PreTranslateMessage()` işlevi CWinApp-türetilmiş sınıf ve iletileri el ile işleyin.

##  <a name="pretranslatemessage"></a>  CWinThread::PreTranslateMessage

Windows işlevleri için dağıtılmadan önce Filtre pencere iletileri için bu işlevi geçersiz kılma [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage).

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
İşaret eden bir [MSG yapısı](/windows/desktop/api/winuser/ns-winuser-tagmsg) işlemek için bir ileti içeren.

### <a name="return-value"></a>Dönüş Değeri

İleti tam olarak işlendiği olursa sıfır dışı `PreTranslateMessage` ve daha fazla işlenmemesi. İleti normal yolla işleneceğini olursa sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, yalnızca kullanıcı arabirimi iş parçacığı kullanılır.

##  <a name="processmessagefilter"></a>  CWinThread::ProcessMessageFilter

Bu üye işlevi, belirli Windows iletilere yanıt verir ve filtre framework'ün kanca işlevini çağırır.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*Kod*<br/>
Kanca kodu belirtir. Bu üye işlevi kod nasıl işleneceğini belirlemek için kullanır. *lpMsg.*

*lpMsg*<br/>
Bir Windows işaretçisi [MSG yapısı](/windows/desktop/api/winuser/ns-winuser-tagmsg).

### <a name="return-value"></a>Dönüş Değeri

İleti işleme olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulamanın normal ileti gönderilmeden önce olayları bir kanca işlevini işler işleme.

Bu gelişmiş özellik geçersiz kılarsanız, temel sınıf sürümü, framework'ün korumak için çağrılacak emin olun. işlem bağlama.

##  <a name="processwndprocexception"></a>  CWinThread::ProcessWndProcException

İşleyici, iş parçacığının ileti ya da komut işleyicileri birinde verilen bir özel durumu yakalamaz her framework bu üye işlevini çağırır.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*e*<br/>
İşlenmeyen bir özel durum işaret eder.

*pMsg*<br/>
İşaret eden bir [MSG yapısı](/windows/desktop/api/winuser/ns-winuser-tagmsg) bir özel durum için framework neden windows iletisi hakkındaki bilgileri içeren.

### <a name="return-value"></a>Dönüş Değeri

WM_CREATE özel durum oluşturulursa, -1; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini doğrudan çağırmanız gerekmez.

Bu üye işlevini varsayılan uygulaması yalnızca şu iletilerden oluşturulan özel durumları işler:

|Komut|Eylem|
|-------------|------------|
|WM_CREATE|Başarısız.|
|WM_PAINT|Bu nedenle başka bir WM_PAINT iletisini oluşturulmasını önleme etkilenen penceresinde doğrulayın.|

Bu üye işlevi, özel durumlar genel işlenmesini sağlamak için geçersiz kılın. Yalnızca varsayılan davranışı görüntülemek istiyorsanız, temel işlevlerini çağırın.

Bu üye işlevi bir ileti pompası sahip parçacıklarında kullanılır.

##  <a name="pumpmessage"></a>  CWinThread::PumpMessage

iş parçacığının ileti döngüsü içerir.

```
virtual BOOL PumpMessage();
```

### <a name="remarks"></a>Açıklamalar

`PumpMessage` iş parçacığının ileti döngüsü içerir. `PumpMessage` çağıran `CWinThread` iş parçacığının iletileri pompa için. Çağırabilirsiniz `PumpMessage` geçersiz kılabilir veya zorlamak için iletileri işlenecek doğrudan `PumpMessage` varsayılan davranışını değiştirmek için.

Çağırma `PumpMessage` doğrudan ve varsayılan davranışını geçersiz kılarak yalnızca ileri düzey kullanıcılar için önerilir.

##  <a name="resumethread"></a>  CWinThread::ResumeThread

Tarafından askıya alındı bir iş parçacığının yürütülmesini sürdürmek için adlı [SuspendThread](#suspendthread) CREATE_SUSPENDED bayrağı ile oluşturulan bir iş parçacığı veya üye işlevi.

```
DWORD ResumeThread();
```

### <a name="return-value"></a>Dönüş Değeri

Önceki iş parçacığı sayısı başarılıysa; askıya alma `0xFFFFFFFF` Aksi takdirde. Dönüş değeri sıfır ise, geçerli iş parçacığını askıya değil. Dönüş değeri ise, iş parçacığını askıya alındı, ancak şimdi yeniden başlatılır. Herhangi bir dönüş değeri bir anlamına iş parçacığı büyük askıda kalır.

### <a name="remarks"></a>Açıklamalar

Geçerli iş parçacığının askıya alma sayısı bir azaltılır. Askıya alma sayımı küçültülürse sıfır olarak iş parçacığı yürütmeyi devam ettirir. Aksi takdirde iş parçacığı askıda kalır.

##  <a name="run"></a>  CWinThread::Run

Kullanıcı arabirimi iş parçacıkları için bir varsayılan mesaj döngüsünü sağlar.

```
virtual int Run();
```

### <a name="return-value"></a>Dönüş Değeri

Bir **int** iş parçacığı tarafından döndürülen değer. Bu değer, çağrılarak alınabilir [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread).

### <a name="remarks"></a>Açıklamalar

`Run` Uygulama alıncaya kadar Windows iletileri gönderir ve alır bir [WM_QUIT](/windows/desktop/winmsg/wm-quit) ileti. İş parçacığının ileti kuyruğu şu anda hiçbir ileti içeriyorsa `Run` çağrıları `OnIdle` boşta kalma süresi işlemini gerçekleştirmek için. Gelen iletiler Git [PreTranslateMessage](#pretranslatemessage) üye işlevi özel işleme ve ardından Windows işleve [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) standart klavye çevirisi için. Son olarak, [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows işlevi çağrılır.

`Run` nadiren geçersiz kılınır, ancak özel davranışı uygulamak için geçersiz kılabilirsiniz.

Bu üye işlevi, yalnızca kullanıcı arabirimi iş parçacığı kullanılır.

##  <a name="setthreadpriority"></a>  CWinThread::SetThreadPriority

Bu işlev, öncelik sınıf içindeki geçerli iş parçacığı öncelik düzeyi ayarlar.

```
BOOL SetThreadPriority(int nPriority);
```

### <a name="parameters"></a>Parametreler

*nPriority*<br/>
Öncelik sınıfı içinde yeni iş parçacığı öncelik düzeyi belirtir. Bu parametre yüksek önceliğe düşüğe doğru listelenen şu değerlerden biri olmalıdır:

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

Bu öncelikleri hakkında daha fazla bilgi için bkz. [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Sonra yalnızca çağrılabilir [CreateThread](#createthread) başarıyla döndürür.

##  <a name="suspendthread"></a>  CWinThread::SuspendThread

Geçerli artırır iş parçacığının askıya alma sayısı.

```
DWORD SuspendThread();
```

### <a name="return-value"></a>Dönüş Değeri

Önceki iş parçacığı sayısı başarılıysa; askıya alma `0xFFFFFFFF` Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Herhangi bir iş parçacığı bir askıya alma sayısı sıfırdan küçük varsa, bu iş parçacığı yürütmez. İş parçacığı çağırarak sürdürülebilir [ResumeThread](#resumethread) üye işlevi.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWinApp Sınıfı](../../mfc/reference/cwinapp-class.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)
