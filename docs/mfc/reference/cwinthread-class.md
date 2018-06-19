---
title: CWinThread sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7cbdcc1c5534d8dd9ba5d4f895af70a8ec16ac5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376972"
---
# <a name="cwinthread-class"></a>CWinThread sınıfı
Bir uygulama içinde yürütme iş parçacığı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinThread::CWinThread](#cwinthread)|Oluşturan bir `CWinThread` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinThread::CreateThread](#createthread)|Başlayan yürütme işlemi bir `CWinThread` nesnesi.|  
|[CWinThread::ExitInstance](#exitinstance)|İş parçacığı sonlandırıldığında temizlemek için geçersiz kılın.|  
|[CWinThread::GetMainWnd](#getmainwnd)|İş parçacığı için ana penceresi için bir işaretçi alır.|  
|[CWinThread::GetThreadPriority](#getthreadpriority)|Geçerli iş parçacığı önceliği alır.|  
|[CWinThread::InitInstance](#initinstance)|İş parçacığı örneği başlatma gerçekleştirmek için geçersiz kılın.|  
|[CWinThread::IsIdleMessage](#isidlemessage)|Özel ileti denetler.|  
|[CWinThread::OnIdle](#onidle)|İş parçacığına özgü boşta kalma süresi işlemini gerçekleştirmek için geçersiz kılın.|  
|[CWinThread::PostThreadMessage](#postthreadmessage)|Başka bir iletiye yazılarını `CWinThread` nesnesi.|  
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Windows işlevleri gönderilir önce iletileri filtreler [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|Uygulama düşmeden önce belirli iletileri kesintiye uğratır.|  
|[CWinThread::ProcessWndProcException](#processwndprocexception)|İş parçacığının ileti ve komut işleyicileri tarafından oluşturulan tüm işlenmeyen özel durumları yakalar.|  
|[CWinThread::PumpMessage](#pumpmessage)|İş parçacığının ileti döngüsü içerir.|  
|[CWinThread::ResumeThread](#resumethread)|Bir iş parçacığının azaltır sayısı askıya alın.|  
|[CWinThread::Run](#run)|İş parçacığı için işlevi ile bir ileti Pompalama denetleme. Varsayılan ileti döngüsü özelleştirmek için geçersiz kılın.|  
|[CWinThread::SetThreadPriority](#setthreadpriority)|Geçerli iş parçacığı önceliği ayarlar.|  
|[CWinThread::SuspendThread](#suspendthread)|İş parçacığının bir artış sayısı askıya alın.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinThread::operator TANITICISI](#operator_handle)|İşleyicisini alır `CWinThread` nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinThread::m_bAutoDelete](#m_bautodelete)|İş parçacığı sonlandırma nesnede destroy belirtir.|  
|[CWinThread::m_hThread](#m_hthread)|Geçerli iş parçacığına işleyin.|  
|[CWinThread::m_nThreadID](#m_nthreadid)|Geçerli iş parçacığı kimliği.|  
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|OLE sunucu yerinde etkin olduğunda kapsayıcı uygulamanın ana penceresi işaretçi.|  
|[CWinThread::m_pMainWnd](#m_pmainwnd)|Bir işaretçi uygulamanın ana penceresine tutar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ana yürütme iş parçacığı genellikle türetilmiş bir nesne tarafından sağlanan `CWinApp`; `CWinApp` türetildiği `CWinThread`. Ek `CWinThread` nesneler belirli bir uygulama içinde birden çok iş parçacığı sağlar.  
  
 İş parçacığı iki genel tür vardır, `CWinThread` destekler: çalışan iş parçacıkları ve kullanıcı arabirimi iş parçacıkları. Çalışan iş parçacığı sahip hiçbir ileti Pompalama: Örneğin, elektronik tablo uygulamasında arka plan hesaplamaları gerçekleştiren bir iş parçacığı. Kullanıcı arabirimi iş parçacıkları ileti Pompalama sahip ve işlem sistemden alınan iletileri. [CWinApp](../../mfc/reference/cwinapp-class.md) ve ondan türetilmiş sınıfları kullanıcı arabirimi iş parçacıkları bir örnekleridir. Başka bir kullanıcı arabirimi iş parçacığı de doğrudan türetilebilir `CWinThread`.  
  
 Sınıfının nesneleri `CWinThread` genellikle iş parçacığı süresince mevcut. Bu davranışı değiştirmek istiyorsanız, Ayarla [m_bAutoDelete](#m_bautodelete) için **FALSE**.  
  
 `CWinThread` Sınıftır kodu ve MFC tam olarak iş parçacığı güvenli hale getirmek gerekli. İş parçacığına özgü bilgileri korumak için çerçevesi tarafından kullanılan iş parçacığı yerel veri tarafından yönetilen `CWinThread` nesneleri. Bu bağımlılığı nedeniyle `CWinThread` iş parçacığı yerel verileri işlemek için MFC kullanan tüm iş parçacığı tarafından MFC ile oluşturulması gerekir. Örneğin, çalışma zamanı işlevi tarafından oluşturulan iş parçacığı [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) herhangi MFC API'leri kullanamazsınız.  
  
 Bir iş parçacığı oluşturma çağrısı [AfxBeginThread](application-information-and-management.md#afxbeginthread). Çalışan ya da kullanıcı arabirimi iş parçacığı mi istediğinize bağlı olarak iki tür vardır. Bir kullanıcı arabirimi iş parçacığı istiyorsanız, geçişi için `AfxBeginThread` gösteren bir işaretçi `CRuntimeClass` biri, `CWinThread`-türetilmiş sınıf. Bir çalışan iş parçacığı oluşturmak istiyorsanız, geçişi için `AfxBeginThread` denetleyen işlev ve denetleyen işlev parametresi için bir işaretçi. Çalışan iş parçacıkları ve kullanıcı arabirimi iş parçacıkları için öncelik, yığın boyutu, oluşturma bayrakları ve güvenlik özniteliklerini değiştirme isteğe bağlı parametreleri belirtebilirsiniz. `AfxBeginThread` bir işaretçi yeni döndürülecek `CWinThread` nesnesi.  
  
 Çağırmak yerine `AfxBeginThread`, oluşturmak bir `CWinThread`-türetilen nesne ve ardından arama `CreateThread`. Bu iki aşamalı yapımı yöntem yeniden kullanmak istiyorsanız yararlıdır `CWinThread` art arda oluşturma ve iş parçacığı yürütmeleri sonlandırmalar arasında nesne.  
  
 Daha fazla bilgi için `CWinThread`, makalelerine bakın [C++ ve MCF ile çoklu iş parçacığı kullanımı](../../parallel/multithreading-with-cpp-and-mfc.md), [çoklu iş parçacığı kullanımı: kullanıcı arabirimi iş parçacıkları oluşturma](../../parallel/multithreading-creating-user-interface-threads.md), [çoklu iş parçacığı kullanımı: çalışan oluşturma İş parçacığı](../../parallel/multithreading-creating-worker-threads.md), ve [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="createthread"></a>  CWinThread::CreateThread  
 Arama işlemi adres alanı içinde çalıştırmak için bir iş parçacığı oluşturur.  
  
```  
BOOL CreateThread(
    DWORD dwCreateFlags = 0,  
    UINT nStackSize = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwCreateFlags`  
 İş parçacığı oluşturma denetimleri ek bir bayrak belirtir. Bu bayrak iki değerden birini içerir:  
  
- **AfxBeginThread'e** bir askıya alma sayısına ile iş parçacığı başlatılamıyor. Kullanım **AfxBeginThread'e** , herhangi bir üye veri başlatmak istiyorsanız `CWinThread` gibi nesne [m_bAutoDelete](#m_bautodelete) veya tüm üyeleri çalışan iş parçacığı başlamadan önce türetilmiş sınıf. Başlatma tamamlandıktan sonra kullanmak [CWinThread::ResumeThread](#resumethread) için çalışan iş parçacığı başlatılamıyor. İş parçacığı kadar yürütmez `CWinThread::ResumeThread` olarak adlandırılır.  
  
- **0** hemen oluşturulduktan sonra iş parçacığı başlatılamıyor.  
  
 `nStackSize`  
 Yeni bir iş parçacığı yığınının bayt cinsinden boyutu belirtir. Varsa **0**, işlemin birincil iş parçacığının aynı boyutta Varsayılanları yığın boyutu.  
  
 `lpSecurityAttrs`  
 İşaret eden bir [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) iş parçacığı için güvenlik özniteliklerini belirtir yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İş parçacığı başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `AfxBeginThread` bir iş parçacığı nesnesi oluşturun ve tek bir adımda yürütün. Kullanım `CreateThread` art arda oluşturma ve iş parçacığı yürütmeleri sonlandırılması arasında iş parçacığı nesnesi yeniden kullanmak istiyorsanız.  
  
##  <a name="cwinthread"></a>  CWinThread::CWinThread  
 Oluşturan bir `CWinThread` nesnesi.  
  
```  
CWinThread();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İş parçacığının yürütme başlamak için arama [CreateThread](#createthread) üye işlevi. Genellikle iş parçacığı çağırarak oluşturacağınız [AfxBeginThread](application-information-and-management.md#afxbeginthread), bu oluşturucuyu çağıracaktır ve `CreateThread`.  
  
##  <a name="exitinstance"></a>  CWinThread::ExitInstance  
 Bir nadiren geçersiz kılınan içinde çerçevesinden tarafından çağrılan [çalıştırmak](#run) iş parçacığı'nın bu örneğinin çıkmak için üye işlevi veya çağrı [InitInstance](#initinstance) başarısız olur.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İş parçacığının çıkış kodu; 0 hata olmadığını gösterir ve değerler 0'dan büyük bir hata gösterir. Bu değer çağırarak alınabilir [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi ancak içinde herhangi bir yerden çağırmayın **çalıştırmak** üye işlevi. Bu üye işlevi yalnızca kullanıcı arabirimi iş parçacıkları kullanılır.  
  
 Bu işlev varsayılan uygulaması siler `CWinThread` , nesne [m_bAutoDelete](#m_bautodelete) olan **doğru**. Ek temizlemenin, iş parçacığı sonlandırıldığında gerçekleştirmek isterseniz, bu işlev geçersiz kılar. Uygulamanıza `ExitInstance` kodunuzu yürütüldükten sonra temel sınıfın sürüm çağırmalıdır.  
  
##  <a name="getmainwnd"></a>  CWinThread::GetMainWnd  
 Uygulamanızı OLE sunucusu ise, doğrudan başvurma yerine uygulama etkin ana penceresinde bir işaretçi almak için bu işlevi çağırmak `m_pMainWnd` uygulama nesnesi üyesi.  
  
```  
virtual CWnd* GetMainWnd();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu işlev, Windows'un iki türden biri için bir işaretçi döndürür. Bu işlev, iş parçacığı OLE sunucusu parçası olan ve etkin bir kapsayıcı içinde yerinde etkin olduğu bir nesnenin varsa, döndürür [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) veri üyesi `CWinThread` nesnesi.  
  
 Bir kapsayıcıdaki yerinde etkin nesnesi yok veya uygulamanızın OLE sunucusu değil, bu işlevi döndürür [m_pMainWnd](#m_pmainwnd) iş parçacığı nesnenizin veri üyesi.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin kullanıcı arabirimi iş parçacıkları, bu için başvuran için eşdeğerdir `m_pActiveWnd` , uygulama nesnesinin üyesi.  
  
 Uygulamanızı bir OLE sunucusu değil sonra bu işlevi çağırmak için başvuran için eşdeğer `m_pMainWnd` , uygulama nesnesinin üyesi.  
  
 Bu işlev varsayılan davranışı değiştirmek için geçersiz kılar.  
  
##  <a name="getthreadpriority"></a>  CWinThread::GetThreadPriority  
 Bu iş parçacığı geçerli iş parçacığı öncelik düzeyini alır.  
  
```  
int GetThreadPriority();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öncelik sınıfı içinde geçerli iş parçacığının öncelik düzeyi. Döndürülen değer aşağıdaki olacaktır en yüksek öncelikli olandan en düşük için listelenen:  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **THREAD_PRIORITY_LOWEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 Bu öncelikleri hakkında daha fazla bilgi için bkz: [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) Windows SDK'sındaki.  
  
##  <a name="initinstance"></a>  CWinThread::InitInstance  
 `InitInstance` Her bir kullanıcı arabirimi iş parçacığı yeni bir örneğini başlatmak için geçersiz kılınmalıdır.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlatma başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, kılmanız `InitInstance` bir iş parçacığı ilk oluşturulduğunda tamamlanması gereken görevler gerçekleştirmek için.  
  
 Bu üye işlevi yalnızca kullanıcı arabirimi iş parçacıkları kullanılır. İş parçacıklarını başlatma geçirilen denetleyen işlev gerçekleştirmek [AfxBeginThread](application-information-and-management.md#afxbeginthread).  
  
##  <a name="isidlemessage"></a>  CWinThread::IsIdleMessage  
 Tutmak için bu işlevi geçersiz **ONIDLE** belirli iletileri üretildikten sonra çağrılan gelen.  
  
```  
virtual BOOL IsIdleMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 `pMsg`  
 İşlenen geçerli ileti noktalarına.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `OnIdle` işlendikten sonra çağrılmalıdır ileti; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama çağrılmayan **ONIDLE** yedek fare iletileri ve belirliyorsanız düzeltme işaretleri yanıp sönen tarafından üretilen iletileri sonra.  
  
 Uygulamanın kısa bir süreölçer oluşturduysanız **ONIDLE** sık performans sorunlarına neden olarak adlandırılır. Bu tür bir uygulamanın performansını artırmak için geçersiz kılma `IsIdleMessage` uygulamanın içinde `CWinApp`-türetilmiş sınıf denetlemek için `WM_TIMER` gibi iletileri:  
  
 [!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]  
  
 İşleme `WM_TIMER` bu şekilde kısa zamanlayıcılar kullanan uygulamaların performansını artırır.  
  
##  <a name="m_bautodelete"></a>  CWinThread::m_bAutoDelete  
 Belirtir olup olmadığını `CWinThread` nesne otomatik olarak silinmesi iş parçacığı sonlandırmanın.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_bAutoDelete` Veri üyesi olan bir ortak değişken türü **BOOL**.  
  
 Değeri `m_bAutoDelete` temel alınan iş parçacığı tutamacı nasıl kapalı etkilemez. İş parçacığı tutamacı her zaman zaman kapalı `CWinThread` nesne yok.  
  
##  <a name="m_hthread"></a>  CWinThread::m_hThread  
 İşlemek için bağlı iş parçacığına `CWinThread`.  
  
```  
HANDLE m_hThread;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_hThread` Veri üyesi olan bir ortak değişken türü `HANDLE`. İş parçacığı şu anda arka plandaki varsa, yalnızca geçerli değil.  
  
##  <a name="m_nthreadid"></a>  CWinThread::m_nThreadID  
 İş parçacığı kimliği için bağlı `CWinThread`.  
  
```  
DWORD m_nThreadID;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 **M_nThreadID** veri üyesi olan bir ortak değişken türü `DWORD`. İş parçacığı şu anda arka plandaki varsa, yalnızca geçerli değil.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [AfxGetThread](application-information-and-management.md#afxgetthread).  
  
##  <a name="m_pactivewnd"></a>  CWinThread::m_pActiveWnd  
 Bu veri üyesi, iş parçacığının etkin pencereyi nesnesine bir işaretçi depolamak için kullanın.  
  
```  
CWnd* m_pActiveWnd;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Pencerenin başvurulan Microsoft Foundation Class Kitaplığı otomatik olarak, iş parçacığı sonlandırılır `m_pActiveWnd` kapalı. Bu iş parçacığı bir uygulama için birincil iş parçacığı ise, uygulama de sonlandırılacak. Bu veri üyesi ise **NULL**, uygulamanın etkin pencereyi `CWinApp` nesne devralmış. `m_pActiveWnd` tür genel bir değişkendir **CWnd\***.  
  
 Geçersiz kıldığınızda genellikle, bu üye değişkeni ayarlanabilir `InitInstance`. Bir çalışan iş parçacığı, bu veri üyesinin değerini kendi üst iş parçacığından devralınır.  
  
##  <a name="m_pmainwnd"></a>  CWinThread::m_pMainWnd  
 Bu veri üyesi, iş parçacığının ana pencere nesnesi için bir işaretçi depolamak için kullanın.  
  
```  
CWnd* m_pMainWnd;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Pencerenin başvurulan Microsoft Foundation Class Kitaplığı otomatik olarak, iş parçacığı sonlandırılır `m_pMainWnd` kapalı. Bu iş parçacığı bir uygulama için birincil iş parçacığı ise, uygulama de sonlandırılacak. Bu veri üyesi ise **NULL**, uygulamanın ana penceresi `CWinApp` nesnesi, iş parçacığı sonlandırma zamanı belirlemek için kullanılır. `m_pMainWnd` tür genel bir değişkendir **CWnd\***.  
  
 Geçersiz kıldığınızda genellikle, bu üye değişkeni ayarlanabilir `InitInstance`. Bir çalışan iş parçacığı, bu veri üyesinin değerini kendi üst iş parçacığından devralınır.  
  
##  <a name="onidle"></a>  CWinThread::OnIdle  
 Boşta kalma süresi işlemini gerçekleştirmek için bu üye işlevi geçersiz kılar.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Parametreler  
 `lCount`  
 Bir sayaç artırılır her zaman `OnIdle` iş parçacığının ileti sırası boş olduğunda çağrılır. Bu sayı, yeni bir ileti işlenen her zaman 0 olarak sıfırlanır. Kullanabileceğiniz `lCount` göreli iş parçacığı işlenirken boşta bir ileti olmadan süreyi belirlemek için parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha fazla boşta işleme süresi almak için sıfır olmayan; Daha fazla boşta işleme süresi gerekirse 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `OnIdle` iş parçacığının ileti sırası boş olduğunda varsayılan ileti döngüde adı verilir. Boşta işleyici görevler kendi arka plan çağırmak için geçersiz kılma kullanın.  
  
 `OnIdle` hiçbir ek boşta işleme süresi gerekli olduğunu göstermek için 0 değerini döndürmelidir. `lCount` Parametresi, her zaman artırılır `OnIdle` ileti sırası boş ve yeni bir ileti işlenir her zaman 0 olarak sıfırlanır olduğunda çağrılır. Bu sayısına göre farklı boşta yordamları çağırabilirsiniz.  
  
 Bu üye işlevi varsayılan uygulamasını geçici nesneler ve bellek kullanılmayan dinamik bağlantı kitaplıklarından boşaltır.  
  
 Bu üye işlevi yalnızca kullanıcı arabirimi iş parçacıkları kullanılır.  
  
 Uygulama kadar iletileri işleyemez çünkü `OnIdle` döndürür, bu işlevde uzun görevler gerçekleştirmeyin.  
  
##  <a name="operator_handle"></a>  CWinThread::operator TANITICISI  
 İşleyicisini alır `CWinThread` nesnesi.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, iş parçacığı nesnesi; tanıtıcısı Aksi takdirde, **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows API'larını doğrudan çağırmak için tanıtıcı kullanın.  
  
##  <a name="postthreadmessage"></a>  CWinThread::PostThreadMessage  
 Başka bir kullanıcı tanımlı bir ileti göndermek için çağrılan `CWinThread` nesnesi.  
  
```  
BOOL PostThreadMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 `message`  
 Kullanıcı tanımlı iletinin kimliği.  
  
 `wParam`  
 İlk ileti parametresi.  
  
 `lParam`  
 İkinci ileti parametresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Gönderilen ileti için uygun ileti işleyicisi tarafından ileti eşlemesi makrosu eşlendi `ON_THREAD_MESSAGE`.  
  
> [!NOTE]
>  Windows çağrılırken [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946) işlevi bir MFC uygulamasından işleyicileri çağrılmaz MFC ileti. Daha fazla bilgi için Bilgi Bankası makalesi, "Sorun: MFC ileti işleyicisi yok adlı ile PostThreadMessage()" (Q142415) bakın.  
  
##  <a name="pretranslatemessage"></a>  CWinThread::PreTranslateMessage  
 Windows işlevleri gönderilir önce penceresi iletilerine filtre uygulamak için bu işlevi geçersiz kılma [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 `pMsg`  
 İşaret eden bir [MSG yapısı](../../mfc/reference/msg-structure1.md) işlemek için ileti içeren.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti tam işlenmiş, sıfır olmayan `PreTranslateMessage` ve daha fazla işlenmesi gerektiğini değil. İleti normal şekilde işlenmesi, sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi yalnızca kullanıcı arabirimi iş parçacıkları kullanılır.  
  
##  <a name="processmessagefilter"></a>  CWinThread::ProcessMessageFilter  
 Framework'ün kanca işlevini filtre ve belirli Windows iletilerini yanıtlamak için bu üye işlevi çağırır.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 `code`  
 Kanca kod belirtir. Bu üye işlev kodunu nasıl işleneceğini belirlemek üzere kullanır. `lpMsg.`  
  
 `lpMsg`  
 Windows için bir işaretçi [MSG yapısı](../../mfc/reference/msg-structure1.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti işleniyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanın normal ileti gönderilmeden önce olayları kanca işlevini işler işleniyor.  
  
 Bu gelişmiş özellik geçersiz kılarsanız framework'ün korumak için temel sınıf sürüm çağırdığınızdan emin olun işleme bağlayın.  
  
##  <a name="processwndprocexception"></a>  CWinThread::ProcessWndProcException  
 İşleyici, iş parçacığının iletisi ya da komut işleyicileri birinde oluşturulan bir özel yakalamaz her framework bu üye işlevi çağırır.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 *e*  
 İşlenmeyen bir özel durum noktalarına.  
  
 `pMsg`  
 İşaret eden bir [MSG yapısı](../../mfc/reference/msg-structure1.md) framework bir özel durum nedeniyle windows iletisi hakkında bilgi içeren.  
  
### <a name="return-value"></a>Dönüş Değeri  
 -1 olursa bir `WM_CREATE` özel durum oluşturulur; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi doğrudan çağırmayın.  
  
 Bu üye işlevi varsayılan uygulaması yalnızca şu iletilerden oluşturulan özel durumları işler:  
  
|Komut|Eylem|  
|-------------|------------|  
|`WM_CREATE`|Başarısız.|  
|`WM_PAINT`|Bu nedenle başka önleme etkilenen penceresinde, doğrula `WM_PAINT` oluşturulmasını ileti.|  
  
 Bu üye işlevi, özel durumların genel işleme sağlamak için geçersiz kılar. Yalnızca varsayılan davranışı görüntülemek istiyorsanız temel işlevselliğini çağırın.  
  
 Bu üye işlevine sahip bir ileti Pompalama parçacıklarında kullanılır.  
  
##  <a name="pumpmessage"></a>  CWinThread::PumpMessage  
 İş parçacığının ileti döngüsü içerir.  
  
```  
virtual BOOL PumpMessage();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `PumpMessage` İş parçacığının ileti döngüsü içerir. **PumpMessage** tarafından çağrılır `CWinThread` iş parçacığının iletileri pompa için. Çağırabilirsiniz `PumpMessage` geçersiz kılabilir veya zorlamak için iletileri işlenmek üzere doğrudan `PumpMessage` varsayılan davranışını değiştirmek için.  
  
 Çağırma `PumpMessage` doğrudan ve kendi varsayılan davranışı geçersiz kılma yalnızca ileri düzey kullanıcıların yapması önerilir.  
  
##  <a name="resumethread"></a>  CWinThread::ResumeThread  
 Tarafından askıya alındı bir iş parçacığı yürütülmesini sürdürmek için çağrılan [SuspendThread](#suspendthread) üye işlevini veya ile oluşturulan bir iş parçacığı **AfxBeginThread'e** bayrağı.  
  
```  
DWORD ResumeThread();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İş parçacığı önceki count başarılı olursa; askıya alma `0xFFFFFFFF` Aksi takdirde. Dönüş değeri sıfır ise, geçerli iş parçacığının askıya değil. Dönüş değeri ise, iş parçacığı askıya alındı, ancak şimdi yeniden. Herhangi bir yol iş parçacığı büyük dönüş değeri askıda kalır.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli iş parçacığının askıya alma sayısı tarafından azalır. Askıya alma sayısı azaltıldığında sıfır olarak iş parçacığı yürütme; sürdürür. Aksi takdirde iş parçacığı askıda kalır.  
  
##  <a name="run"></a>  CWinThread::Run  
 Varsayılan ileti döngüsü için kullanıcı arabirimi iş parçacıkları sağlar.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `int` iş parçacığı tarafından döndürülen değer. Bu değer çağırarak alınabilir [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Açıklamalar  
 **Çalıştırma** edinme ve uygulama alıncaya kadar Windows iletileri gönderir bir [WM_QUIT](http://msdn.microsoft.com/library/windows/desktop/ms632641) ileti. İş parçacığının ileti sırası şu anda hiçbir ileti içeriyorsa **çalıştırmak** çağrıları `OnIdle` boşta kalma süresi işlemini gerçekleştirmek için. Gelen iletileri Git [PreTranslateMessage](#pretranslatemessage) üye işlevi özel işleme ve ardından Windows işlevi için [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) standart klavye çeviri için. Son olarak, [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows işlevi çağrılır.  
  
 **Çalıştırma** nadiren geçersiz kılınır, ancak özel davranışı uygulamak için geçersiz kılabilirsiniz.  
  
 Bu üye işlevi yalnızca kullanıcı arabirimi iş parçacıkları kullanılır.  
  
##  <a name="setthreadpriority"></a>  CWinThread::SetThreadPriority  
 Bu işlev geçerli iş parçacığının kendi öncelik sınıfı içinde öncelik düzeyi ayarlar.  
  
```  
BOOL SetThreadPriority(int nPriority);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPriority`  
 Öncelik sınıfı içinde yeni iş parçacığı öncelik düzeyini belirtir. Bu parametre, en yüksek öncelikli olandan en düşük için listelenen aşağıdaki değerlerden biri olmalıdır:  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **THREAD_PRIORITY_LOWEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 Bu öncelikleri hakkında daha fazla bilgi için bkz: [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonra yalnızca çağrılabilir [CreateThread](#createthread) başarıyla döndürür.  
  
##  <a name="suspendthread"></a>  CWinThread::SuspendThread  
 Geçerli artırır iş parçacığının askıya alma sayısı.  
  
```  
DWORD SuspendThread();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İş parçacığı önceki count başarılı olursa; askıya alma `0xFFFFFFFF` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir iş parçacığı bir askıya alma sayısı sıfır yukarıda varsa, bu iş parçacığını yürütmek değil. İş parçacığı çağırarak ettirilebilir [ResumeThread'i](#resumethread) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWinApp sınıfı](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)
