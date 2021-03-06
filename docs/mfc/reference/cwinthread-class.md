---
description: 'Daha fazla bilgi edinin: CWinThread sınıfı'
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
ms.openlocfilehash: f9f89aa6397f44c95e8958d077fe18258e3c17f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342614"
---
# <a name="cwinthread-class"></a>CWinThread sınıfı

Bir uygulama içindeki yürütmenin iş parçacığını temsil eder.

## <a name="syntax"></a>Syntax

```
class CWinThread : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWinThread:: CWinThread](#cwinthread)|Bir `CWinThread` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinThread:: CreateThread](#createthread)|Bir nesnenin yürütülmesini başlatır `CWinThread` .|
|[CWinThread:: ExitInstance](#exitinstance)|İş parçacığınızdan sona erene kadar temizlemek için geçersiz kılın.|
|[CWinThread:: GetMainWnd](#getmainwnd)|İş parçacığının ana penceresine bir işaretçi alır.|
|[CWinThread:: GetThreadPriority](#getthreadpriority)|Geçerli iş parçacığının önceliğini alır.|
|[CWinThread:: InitInstance](#initinstance)|İş parçacığı örneğini başlatmayı gerçekleştirmek için geçersiz kılın.|
|[CWinThread:: Isıdeboşta Iletisi](#isidlemessage)|Özel iletileri denetler.|
|[CWinThread:: OnIdle](#onidle)|İş parçacığına özgü boşta kalma süresi işlemini gerçekleştirmek için geçersiz kılın.|
|[CWinThread::P ostThreadMessage](#postthreadmessage)|Başka bir nesneye ileti gönderir `CWinThread` .|
|[CWinThread::P reTranslateMessage](#pretranslatemessage)|İletileri, [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage)Windows işlevlerine dağıtılmadan önce filtreler.|
|[CWinThread::P rocessMessageFilter](#processmessagefilter)|Uygulamaya ulaşmadan önce belirli iletileri keser.|
|[CWinThread::P rocessWndProcException](#processwndprocexception)|İş parçacığının iletisi ve komut işleyicileri tarafından oluşturulan işlenmemiş özel durumları karşılar.|
|[CWinThread::P öncelik Iletisi](#pumpmessage)|İş parçacığının ileti döngüsünü içerir.|
|[CWinThread:: ResumeThread](#resumethread)|Bir iş parçacığının askıya alma sayısını azaltır.|
|[CWinThread:: Run](#run)|İleti göndericisi olan iş parçacıkları için işlev denetleniyor. Varsayılan ileti döngüsünü özelleştirmek için geçersiz kılın.|
|[CWinThread:: SetThreadPriority](#setthreadpriority)|Geçerli iş parçacığının önceliğini ayarlar.|
|[CWinThread:: SuspendThread](#suspendthread)|Bir iş parçacığının askıya alma sayısını artırır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CWinThread:: operator işleci](#operator_handle)|Nesnesinin tanıtıcısını alır `CWinThread` .|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CWinThread:: m_bAutoDelete](#m_bautodelete)|İş parçacığı sonlandırmada nesnenin yok edilip edilmeyeceğini belirtir.|
|[CWinThread:: m_hThread](#m_hthread)|Geçerli iş parçacığının tanıtıcısı.|
|[CWinThread:: m_nThreadID](#m_nthreadid)|Geçerli iş parçacığının KIMLIĞI.|
|[CWinThread:: m_pActiveWnd](#m_pactivewnd)|Bir OLE sunucusu yerinde etkin olduğunda kapsayıcı uygulamasının ana penceresine yönelik işaretçi.|
|[CWinThread:: m_pMainWnd](#m_pmainwnd)|Uygulamanın ana penceresine bir işaretçi tutar.|

## <a name="remarks"></a>Açıklamalar

Yürütmenin ana iş parçacığı genellikle kaynağından türetilmiş bir nesne tarafından sağlanır `CWinApp` `CWinApp` `CWinThread` . Ek `CWinThread` nesneler, belirli bir uygulama içinde birden çok iş parçacığına izin verir.

Tarafından desteklenen iki genel iş parçacığı türü vardır `CWinThread` : çalışan iş parçacıkları ve Kullanıcı arabirimi iş parçacıkları. Çalışan iş parçacıklarında ileti göndericisi yok: Örneğin, bir elektronik tablo uygulamasında arka plan hesaplamaları gerçekleştiren bir iş parçacığı. Kullanıcı arabirimi iş parçacıklarının bir ileti göndericisi ve sistemden alınan işlem iletileri vardır. [CWinApp](../../mfc/reference/cwinapp-class.md) ve sınıfından türetilmiş sınıflar, Kullanıcı arabirimi iş parçacıklarının örnekleridir. Diğer Kullanıcı arabirimi iş parçacıkları da doğrudan öğesinden türetilebilir `CWinThread` .

Sınıf nesneleri `CWinThread` genellikle iş parçacığı süresince mevcuttur. Bu davranışı değiştirmek istiyorsanız, [M_BAUTODELETE](#m_bautodelete) false olarak ayarlayın.

`CWinThread`Sınıfı, kodunuzu ve MFC 'yi tamamen iş parçacığı açısından güvenli hale getirmek için gereklidir. İş parçacığına özgü bilgileri korumak için çerçeve tarafından kullanılan iş parçacığı yerel verileri, nesneleri tarafından yönetilir `CWinThread` . `CWinThread`İş parçacığı yerel verilerini işlemek için bu bağımlıdan dolayı, MFC kullanan herhangi bir iş PARÇACıĞıNıN MFC tarafından oluşturulması gerekir. Örneğin, çalışma zamanı işlevi tarafından oluşturulan bir iş parçacığı [_beginthread _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) HERHANGI bir MFC API 'sini kullanamaz.

Bir iş parçacığı oluşturmak için [AfxBeginThread](application-information-and-management.md#afxbeginthread)çağırın. Çalışan veya Kullanıcı arabirimi iş parçacığı istediğinize bağlı olarak iki form vardır. Bir kullanıcı arabirimi iş parçacığı istiyorsanız, `AfxBeginThread` türetilmiş sınıfınızın bir işaretçisine geçin `CRuntimeClass` `CWinThread` . Bir çalışan iş parçacığı oluşturmak istiyorsanız `AfxBeginThread` Denetim işlevine bir işaretçiye geçirin ve denetim işlevine parametresi koyun. Hem çalışan iş parçacıkları hem de Kullanıcı arabirimi iş parçacıkları için öncelik, yığın boyutu, oluşturma bayraklarını ve güvenlik özniteliklerini değiştiren isteğe bağlı parametreler belirtebilirsiniz. `AfxBeginThread` , yeni nesneniz için bir işaretçi döndürür `CWinThread` .

Çağırmak yerine `AfxBeginThread` , bir `CWinThread` türetilmiş nesne oluşturabilir ve sonra öğesini çağırabilirsiniz `CreateThread` . Bu iki aşamalı oluşturma yöntemi, `CWinThread` nesneyi, iş parçacığı yürütmelerinin art arda oluşturulması ve sonlandırmaları arasında yeniden kullanmak istiyorsanız yararlıdır.

Hakkında daha fazla bilgi için `CWinThread` bkz. [C++ ve MFC ile çoklu](../../parallel/multithreading-with-cpp-and-mfc.md)iş parçacıklı makaleler, çoklu Iş parçacığı [User-Interface oluşturma](../../parallel/multithreading-creating-user-interface-threads.md), Iş parçacığı oluşturma: [çalışan iş parçacıkları oluşturma](../../parallel/multithreading-creating-worker-threads.md)ve [Çoklu iş parçacığı oluşturma: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CWinThread`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cwinthreadcreatethread"></a><a name="createthread"></a> CWinThread:: CreateThread

Çağıran işlemin adres alanı içinde yürütülecek bir iş parçacığı oluşturur.

```
BOOL CreateThread(
    DWORD dwCreateFlags = 0,
    UINT nStackSize = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>Parametreler

*dwCreateFlags*<br/>
İş parçacığının oluşturulmasını denetleyen ek bir bayrak belirtir. Bu bayrak iki değerden birini içerebilir:

- CREATE_SUSPENDED askıya alma sayısı bir tane olan iş parçacığını başlatın. `CWinThread`İş parçacığı çalışmaya başlamadan önce, nesnenin [m_bAutoDelete](#m_bautodelete) veya türetilmiş sınıfınızın herhangi bir üyesi gibi herhangi bir üye verisi başlatmak istiyorsanız CREATE_SUSPENDED kullanın. Başlatma işlemi tamamlandıktan sonra, çalıştıran iş parçacığını başlatmak için [CWinThread:: ResumeThread iş parçacığını](#resumethread) kullanın. İş parçacığı çağrılana kadar yürütülmez `CWinThread::ResumeThread` .

- **0** oluşturulduktan hemen sonra iş parçacığını başlatın.

*nStackSize*<br/>
Yeni iş parçacığı için yığının bayt cinsinden boyutunu belirtir. **0** ise, yığın boyutu işlemin birincil iş parçacığıyla aynı boyutta olur.

*lpSecurityAttrs*<br/>
İş parçacığının güvenlik özniteliklerini belirten [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`AfxBeginThread`Bir iş parçacığı nesnesi oluşturmak ve tek bir adımda yürütmek için kullanın. İş parçacığı `CreateThread` yürütmelerinin art arda oluşturulması ve sonlandırılması arasında iş parçacığı nesnesini yeniden kullanmak istiyorsanız kullanın.

## <a name="cwinthreadcwinthread"></a><a name="cwinthread"></a> CWinThread:: CWinThread

Bir `CWinThread` nesnesi oluşturur.

```
CWinThread();
```

### <a name="remarks"></a>Açıklamalar

İş parçacığının yürütmeye başlamak için [CreateThread](#createthread) üye işlevini çağırın. Genellikle bu oluşturucuyu ve bu oluşturucuyu çağıran [AfxBeginThread](application-information-and-management.md#afxbeginthread)öğesini çağırarak iş parçacıkları oluşturacaksınız `CreateThread` .

## <a name="cwinthreadexitinstance"></a><a name="exitinstance"></a> CWinThread:: ExitInstance

Bu iş parçacığının örneğinden çıkmak için nadiren geçersiz kılınan bir [Run](#run) member işlevinin içinden çerçeve tarafından çağırılır veya [InitInstance](#initinstance) çağrısı başarısız olursa.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığının çıkış kodu; 0 hata olmadığını ve 0 ' dan büyük değerlerin bir hata olduğunu gösterir. Bu değer, [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)çağırarak alınabilir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi herhangi bir yerde, ancak member işlevinin içinde çağırmayın `Run` . Bu üye işlevi yalnızca kullanıcı arabirimi iş parçacıklarında kullanılır.

Bu işlevin varsayılan uygulanması, `CWinThread` [m_bAutoDelete](#m_bautodelete) true ise nesneyi siler. İş parçacığlarınız sonlandırıldığında ek temizleme işlemleri gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın. Uygulamanız, `ExitInstance` kodunuz yürütüldükten sonra temel sınıfın sürümünü çağırmalıdır.

## <a name="cwinthreadgetmainwnd"></a><a name="getmainwnd"></a> CWinThread:: GetMainWnd

Uygulamanız bir OLE sunucusu ise, uygulama nesnesinin üyesine doğrudan başvurmak yerine uygulamanın etkin ana penceresine bir işaretçi almak için bu işlevi çağırın `m_pMainWnd` .

```
virtual CWnd* GetMainWnd();
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlev, iki tür Windows türünden birine bir işaretçi döndürür. İş parçacığınızda bir OLE sunucusunun parçası varsa ve etkin bir kapsayıcı içinde etkin bir nesne varsa, bu işlev nesnenin [CWinApp:: m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) veri üyesini döndürür `CWinThread` .

Bir kapsayıcı içinde yerinde etkin bir nesne yoksa veya uygulamanız OLE sunucusu değilse, bu işlev iş parçacığı nesnenizin [m_pMainWnd](#m_pmainwnd) veri üyesini döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı arabirimi iş parçacıkları için, bu, uygulama nesnenizin üyesine doğrudan başvuru ile eşdeğerdir `m_pActiveWnd` .

Uygulamanız bir OLE sunucusu değilse, bu işlevi çağırmak, uygulama nesnenizin üyesine doğrudan başvuran ile eşdeğerdir `m_pMainWnd` .

Varsayılan davranışı değiştirmek için bu işlevi geçersiz kılın.

## <a name="cwinthreadgetthreadpriority"></a><a name="getthreadpriority"></a> CWinThread:: GetThreadPriority

Bu iş parçacığının geçerli iş parçacığı öncelik düzeyini alır.

```
int GetThreadPriority();
```

### <a name="return-value"></a>Dönüş Değeri

Öncelik sınıfı içindeki geçerli iş parçacığı öncelik düzeyi. Döndürülen değer aşağıdakilerden biri olacaktır, en yüksek öncelikten en düşüğe listelenmiştir:

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

Bu öncelikler hakkında daha fazla bilgi için bkz. Windows SDK [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) .

## <a name="cwinthreadinitinstance"></a><a name="initinstance"></a> CWinThread:: InitInstance

`InitInstance` Kullanıcı arabirimi iş parçacığının her yeni örneğini başlatmak için geçersiz kılınmalıdır.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Genellikle, `InitInstance` bir iş parçacığı ilk oluşturulduğunda tamamlanması gereken görevleri gerçekleştirmek için geçersiz kılmalısınız.

Bu üye işlevi yalnızca kullanıcı arabirimi iş parçacıklarında kullanılır. [AfxBeginThread](application-information-and-management.md#afxbeginthread)'e geçirilen denetim işlevindeki çalışan iş parçacıklarının başlatma işlemini gerçekleştirin.

## <a name="cwinthreadisidlemessage"></a><a name="isidlemessage"></a> CWinThread:: Isıdeboşta Iletisi

`OnIdle`Belirli iletiler oluşturulduktan sonra çağrılması için bu işlevi geçersiz kılın.

```
virtual BOOL IsIdleMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
İşlenmekte olan geçerli iletiyi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

`OnIdle`İleti işlendikten sonra çağrılmalıdır; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, `OnIdle` gereksiz Evcil hayvan tarafından oluşturulan gereksiz fare iletileri ve iletilerden sonra çağrı yapmaz.

Bir uygulama kısa bir Zamanlayıcı oluşturup, `OnIdle` performans sorunlarına neden olacak şekilde sık olarak çağrılır. Bu tür bir uygulamanın performansını geliştirmek için, `IsIdleMessage` uygulamanın `CWinApp` türetilmiş sınıfında aşağıdaki gibi WM_TIMER iletileri denetlemek için geçersiz kılın:

[!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]

Bu şekilde WM_TIMER işleme, kısa süreli zamanlayıcılar kullanan uygulamaların performansını iyileştirir.

## <a name="cwinthreadm_bautodelete"></a><a name="m_bautodelete"></a> CWinThread:: m_bAutoDelete

`CWinThread`Nesnenin iş parçacığı sonlandırmada otomatik olarak silinip silinmeyeceğini belirtir.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>Açıklamalar

`m_bAutoDelete`Veri ÜYESI bool türünde ortak bir değişkendir.

Değeri, `m_bAutoDelete` temeldeki iş parçacığı tanıtıcısının nasıl kapatıldığını etkilemez, ancak tanıtıcıyı kapatma zamanlamasını etkiler. Nesne yok edildiğinde iş parçacığı tutamacı her zaman kapalıdır `CWinThread` .

## <a name="cwinthreadm_hthread"></a><a name="m_hthread"></a> CWinThread:: m_hThread

Bu öğesine eklenen iş parçacığına yönelik tanıtıcı `CWinThread` .

```
HANDLE m_hThread;
```

### <a name="remarks"></a>Açıklamalar

`m_hThread`Veri üyesi, tür tanıtıcısının ortak değişkenidir. Yalnızca temeldeki çekirdek iş parçacığı nesnesi varsa ve tanıtıcı henüz kapanmamışsa geçerlidir.

CWinThread yıkıcısı üzerinde CloseHandle 'ı çağırır `m_hThread` . İş parçacığı sonlandırıldığında [M_BAUTODELETE](#m_bautodelete) true Ise, CWinThread nesnesi yok edilir ve bu, CWinThread nesnesi ve onun üye değişkenleri için herhangi bir işaretçiyi geçersiz kılar. `m_hThread`İş parçacığı çıkış değerini denetlemek için üyeye veya bir sinyal beklemeniz gerekebilir. `m_hThread`İş parçacığı yürütme sırasında, ve bittikten sonra, iş parçacığı yürütmesinin devam etmesine izin vermeden önce, CWinThread nesnesini ve üyesini tutmak IÇIN `m_bAutoDelete` false olarak ayarlayın. Aksi takdirde, iş parçacığı sonlandırılabilir, CWinThread nesnesini yok edebilir ve kullanmayı denemeden önce tanıtıcıyı kapatabilirsiniz. Bu tekniği kullanırsanız, CWinThread nesnesinin silinmesinden siz sorumlusunuz.

## <a name="cwinthreadm_nthreadid"></a><a name="m_nthreadid"></a> CWinThread:: m_nThreadID

Bu öğesine eklenen iş parçacığının KIMLIĞI `CWinThread` .

```
DWORD m_nThreadID;
```

### <a name="remarks"></a>Açıklamalar

`m_nThreadID`Veri ÜYESI dword türünde ortak bir değişkendir. Yalnızca temeldeki çekirdek iş parçacığı nesnesi varsa geçerlidir.
Ayrıca [m_hThread](#m_hthread) ömür hakkında açıklamalara bakın.

### <a name="example"></a>Örnek

  [AfxGetThread](application-information-and-management.md#afxgetthread)örneğine bakın.

## <a name="cwinthreadm_pactivewnd"></a><a name="m_pactivewnd"></a> CWinThread:: m_pActiveWnd

İş parçacığınızın etkin pencere nesnesine bir işaretçi depolamak için bu veri üyesini kullanın.

```
CWnd* m_pActiveWnd;
```

### <a name="remarks"></a>Açıklamalar

Tarafından başvurulan pencere kapatıldığında Microsoft Foundation Class Kitaplığı iş parçacığlarınızı otomatik olarak sonlandırır `m_pActiveWnd` . Bu iş parçacığı bir uygulama için birincil iş parçacığıdır, uygulama da sonlandırılır. Bu veri üyesi NULL ise, uygulamanın nesnesi için etkin pencere `CWinApp` devralınır. `m_pActiveWnd` , türünde ortak bir değişkendir `CWnd*` .

Genellikle, geçersiz kıldığınızda Bu üye değişkenini ayarlarsınız `InitInstance` . Bir çalışan iş parçacığında, bu veri üyesinin değeri üst iş parçacığından devralınır.

## <a name="cwinthreadm_pmainwnd"></a><a name="m_pmainwnd"></a> CWinThread:: m_pMainWnd

İş parçacığınızın ana pencere nesnesine bir işaretçi depolamak için bu veri üyesini kullanın.

```
CWnd* m_pMainWnd;
```

### <a name="remarks"></a>Açıklamalar

Tarafından başvurulan pencere kapatıldığında Microsoft Foundation Class Kitaplığı iş parçacığlarınızı otomatik olarak sonlandırır `m_pMainWnd` . Bu iş parçacığı bir uygulama için birincil iş parçacığıdır, uygulama da sonlandırılır. Bu veri üyesi NULL ise, uygulamanın nesnesinin ana penceresi, `CWinApp` iş parçacığının ne zaman sonlanılacağını belirlemede kullanılacaktır. `m_pMainWnd` , türünde ortak bir değişkendir `CWnd*` .

Genellikle, geçersiz kıldığınızda Bu üye değişkenini ayarlarsınız `InitInstance` . Bir çalışan iş parçacığında, bu veri üyesinin değeri üst iş parçacığından devralınır.

## <a name="cwinthreadonidle"></a><a name="onidle"></a> CWinThread:: OnIdle

Boş zamanlı işleme gerçekleştirmek için bu üye işlevini geçersiz kılın.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Parametreler

*lCount*<br/>
`OnIdle`İş parçacığının ileti kuyruğu boş olduğunda her seferinde arttırılan bir sayaç. Bu sayı, her yeni ileti işlendiğinde 0 ' a sıfırlanır. İş parçacığının bir iletiyi işlemeden boşta kaldığı sürenin göreli uzunluğunu öğrenmek için *lCount* parametresini kullanabilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Daha fazla boş işlem süresi almak için sıfır dışında; daha fazla boş işlem süresi gerekmiyorsa 0.

### <a name="remarks"></a>Açıklamalar

`OnIdle` , iş parçacığının ileti sırası boş olduğunda varsayılan ileti döngüsünde çağrılır. Kendi arka plan boşta işleyici görevlerinizi çağırmak için geçersiz kılmanızı kullanın.

`OnIdle` ek bir boş işlem süresi gerekmediğini belirtmek için 0 döndürmelidir. Her  seferinde bir `OnIdle` ileti sırası boş olduğunda ve her yeni ileti işlendiğinde 0 olarak sıfırlandığında lCount parametresi artırılır. Bu sayıya göre farklı boşta yordamlarınızı çağırabilirsiniz.

Bu üye işlevi için varsayılan uygulama, geçici nesneleri ve kullanılmayan dinamik bağlantı kitaplıklarını bellekten serbest bırakır.

Bu üye işlevi yalnızca kullanıcı arabirimi iş parçacıklarında kullanılır.

Uygulama, dönüşene kadar mesajları işleyemediği için `OnIdle` , bu işlevde uzun görevler gerçekleştirmeyin.

## <a name="cwinthreadoperator-handle"></a><a name="operator_handle"></a> CWinThread:: operator işleci

Nesnesinin tanıtıcısını alır `CWinThread` .

```
operator HANDLE() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, iş parçacığı nesnesinin tanıtıcısı; Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Windows API 'Lerini doğrudan çağırmak için tanıtıcıyı kullanın.

## <a name="cwinthreadpostthreadmessage"></a><a name="postthreadmessage"></a> CWinThread::P ostThreadMessage

Kullanıcı tanımlı bir iletiyi başka bir nesneye göndermek için çağırılır `CWinThread` .

```
BOOL PostThreadMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*İleti*<br/>
Kullanıcı tanımlı iletinin KIMLIĞI.

*wParam*<br/>
İlk ileti parametresi.

*lParam*<br/>
İkinci ileti parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Postalanan ileti, ileti eşleme makrosu ON_THREAD_MESSAGE uygun ileti işleyicisine eşlenir.

> [!NOTE]
> [PostThreadMessage](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)' ı çağırdığınızda ileti, iş parçacığının ileti kuyruğuna yerleştirilir. Ancak, bu şekilde gönderilen iletiler bir pencereyle ilişkili olmadığından, MFC bunları ileti veya komut işleyicilerine göndermez. Bu iletileri işlemek için, `PreTranslateMessage()` CWinApp türetilmiş sınıfınızın işlevini geçersiz kılın ve iletileri el ile işleyin.

## <a name="cwinthreadpretranslatemessage"></a><a name="pretranslatemessage"></a> CWinThread::P reTranslateMessage

Pencere iletilerini [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage)Windows işlevlerine dağıtılmadan önce filtrelemek için bu işlevi geçersiz kılın.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
İşlenecek iletiyi içeren bir [msg yapısına](/windows/win32/api/winuser/ns-winuser-msg) işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İleti içinde tam olarak işlendiyse `PreTranslateMessage` ve daha fazla işlenmemelidir. İleti normal şekilde işlenirse sıfır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca kullanıcı arabirimi iş parçacıklarında kullanılır.

## <a name="cwinthreadprocessmessagefilter"></a><a name="processmessagefilter"></a> CWinThread::P rocessMessageFilter

Framework 'ün kanca işlevi, belirli Windows iletilerini filtrelemek ve bunlara yanıt vermek için bu üye işlevini çağırır.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parametreler

*kodudur*<br/>
Bir kanca kodu belirtir. Bu üye işlevi, *lpMsg* 'in nasıl işleyeceğini anlamak için kodu kullanır.

*lpMsg*<br/>
Windows [msg yapısına](/windows/win32/api/winuser/ns-winuser-msg)yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kanca işlevi, olayları uygulamanın normal ileti işlemeye gönderilmeden önce işler.

Bu gelişmiş özelliği geçersiz kılarsınız, Framework 'ün kanca işlemesini sürdürmek için temel sınıf sürümü çağırdığınızdan emin olun.

## <a name="cwinthreadprocesswndprocexception"></a><a name="processwndprocexception"></a> CWinThread::P rocessWndProcException

Bu üye işlevi, işleyicinin iş parçacığınızın iletisi veya komut işleyicilerinden birinde oluşturulan bir özel durum yakaiçermediği zaman bu üye işlevini çağırır.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*a*<br/>
İşlenmeyen bir özel durumu işaret eder.

*pMsg*<br/>
Framework 'ün özel durum oluşturmasını sağlayan Windows iletisi hakkında bilgi içeren bir [msg yapısına](/windows/win32/api/winuser/ns-winuser-msg) işaret eder.

### <a name="return-value"></a>Dönüş Değeri

WM_CREATE bir özel durum oluşturulursa-1; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini doğrudan çağırmayın.

Bu üye işlevin varsayılan uygulanması yalnızca aşağıdaki iletilerden oluşturulan özel durumları işler:

|Komut|Eylem|
|-------------|------------|
|WM_CREATE|Neden.|
|WM_PAINT|Etkilenen pencereyi doğrulayın ve bu nedenle başka bir WM_PAINT iletisinin oluşturulmasını önler.|

Özel durumlarınızın genel işlemesini sağlamak için bu üye işlevini geçersiz kılın. Yalnızca varsayılan davranışı göstermek istiyorsanız temel işlevi çağırın.

Bu üye işlevi yalnızca ileti göndericisi olan iş parçacıklarında kullanılır.

## <a name="cwinthreadpumpmessage"></a><a name="pumpmessage"></a> CWinThread::P öncelik Iletisi

İş parçacığının ileti döngüsünü içerir.

```
virtual BOOL PumpMessage();
```

### <a name="remarks"></a>Açıklamalar

`PumpMessage` iş parçacığının ileti döngüsünü içerir. `PumpMessage` , tarafından `CWinThread` iş parçacığının iletilerini aktarmak için çağrılır. `PumpMessage`İletileri işlenmek üzere zorlamak için doğrudan çağrı yapabilir veya `PumpMessage` varsayılan davranışını değiştirmek için geçersiz kılabilirsiniz.

`PumpMessage`Doğrudan çağırmak ve varsayılan davranışını geçersiz kılmak yalnızca gelişmiş kullanıcılar için önerilir.

## <a name="cwinthreadresumethread"></a><a name="resumethread"></a> CWinThread:: ResumeThread

[SuspendThread](#suspendthread) üye işlevi tarafından askıya alınan bir iş parçacığının yürütülmesini veya CREATE_SUSPENDED bayrağıyla oluşturulmuş bir iş parçacığını yeniden başlatmak için çağırılır.

```
DWORD ResumeThread();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa iş parçacığının önceki askıya alma sayısı; `0xFFFFFFFF` Aksi takdirde. Dönüş değeri sıfırsa, geçerli iş parçacığı askıya alınmaz. Dönüş değeri bir ise, iş parçacığı askıya alındı, ancak şimdi yeniden başlatıldı. Birden büyük dönüş değeri, iş parçacığının askıda kaldığı anlamına gelir.

### <a name="remarks"></a>Açıklamalar

Geçerli iş parçacığının askıya alma sayısı bir tane azaltılır. Askıya alma sayısı sıfıra düşürüldüğünde iş parçacığı yürütmeyi sürdürür; Aksi takdirde iş parçacığı askıda kalır.

## <a name="cwinthreadrun"></a><a name="run"></a> CWinThread:: Run

Kullanıcı arabirimi iş parçacıkları için varsayılan bir ileti döngüsü sağlar.

```
virtual int Run();
```

### <a name="return-value"></a>Dönüş Değeri

**`int`** İş parçacığı tarafından döndürülen bir değer. Bu değer, [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)çağırarak alınabilir.

### <a name="remarks"></a>Açıklamalar

`Run` uygulama [WM_QUIT](/windows/win32/winmsg/wm-quit) bir ileti alana kadar Windows iletilerini alır ve gönderir. İş parçacığında ileti sırası şu anda hiçbir ileti içermiyorsa, `Run` `OnIdle` boşta kalma süresi işleme çağrısı yapın. Gelen iletiler, özel işleme için [PreTranslateMessage](#pretranslatemessage) üye işlevine ve ardından standart klavye çevirisi için Windows Işlevi [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) öğesine gider. Son olarak, [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevi çağırılır.

`Run` nadiren geçersiz kılındı, ancak özel davranış uygulamak için geçersiz kılabilirsiniz.

Bu üye işlevi yalnızca kullanıcı arabirimi iş parçacıklarında kullanılır.

## <a name="cwinthreadsetthreadpriority"></a><a name="setthreadpriority"></a> CWinThread:: SetThreadPriority

Bu işlev, geçerli iş parçacığının öncelik düzeyini öncelik sınıfı içinde ayarlar.

```
BOOL SetThreadPriority(int nPriority);
```

### <a name="parameters"></a>Parametreler

*Nöncelik*<br/>
Öncelik sınıfında yeni iş parçacığı öncelik düzeyini belirtir. Bu parametre, en yüksek öncelikten en düşüğe doğru listelenen aşağıdaki değerlerden biri olmalıdır:

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

Bu öncelikler hakkında daha fazla bilgi için bkz. Windows SDK [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) .

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yalnızca, [CreateThread](#createthread) başarıyla döndüğünde çağrılabilir.

## <a name="cwinthreadsuspendthread"></a><a name="suspendthread"></a> CWinThread:: SuspendThread

Geçerli iş parçacığının askıya alma sayısını artırır.

```
DWORD SuspendThread();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa iş parçacığının önceki askıya alma sayısı; `0xFFFFFFFF` Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Herhangi bir iş parçacığının sıfırdan bir askıya alma sayısı varsa, bu iş parçacığı yürütülmez. İş parçacığı, [ResumeThread](#resumethread) üye işlevi çağırarak devam edebilir.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWinApp sınıfı](../../mfc/reference/cwinapp-class.md)<br/>
[CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)
