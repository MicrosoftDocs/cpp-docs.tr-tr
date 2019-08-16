---
title: Uygulama bilgileri ve yönetimi
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: 934e89d928104c33f0c2038f136b5ad0ca48cbd4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507779"
---
# <a name="application-information-and-management"></a>Uygulama bilgileri ve yönetimi

Bir uygulama yazdığınızda, tek bir [CWinApp](../../mfc/reference/cwinapp-class.md)türetilen nesne oluşturursunuz. Her zaman, türetilmiş nesnenin dışından `CWinApp`bu nesne hakkında bilgi almak isteyebilirsiniz. Ya da diğer genel "mananger" nesnelerine erişmeniz gerekebilir.

Microsoft Foundation Class Kitaplığı, bu görevleri gerçekleştirmenize yardımcı olmak için aşağıdaki genel işlevleri sağlar:

### <a name="application-information-and-management-functions"></a>Uygulama bilgileri ve yönetim Işlevleri

|||
|-|-|
|[AfxBeginThread](#afxbeginthread)|Yeni bir iş parçacığı oluşturur.|
|[AfxContextMenuManager](#afxcontextmenumanager)|Genel [bağlam menü Yöneticisi](ccontextmenumanager-class.md)işaretçisi.|
|[AfxEndThread](#afxendthread)|Geçerli iş parçacığını sonlandırır.|
|[AfxFindResourceHandle](#afxfindresourcehandle)|Kaynak zincirine ve kaynak KIMLIĞI ve kaynak türüne göre belirli bir kaynağı bulur. |
|[AfxFreeLibrary](#afxfreelibrary)|Yüklenen dinamik bağlantı kitaplığı (DLL) modülünün başvuru sayısını azaltır; başvuru sayısı sıfıra ulaştığında, modül eşlenmemiş olur.|
|[AfxGetApp](#afxgetapp)|Uygulamanın tek `CWinApp` nesnesine bir işaretçi döndürür.|
|[AfxGetAppName](#afxgetappname)|Uygulamanın adını içeren bir dize döndürür.|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|Uygulamanın bu örneğini temsil eden bir HıNSTANCE döndürür.|
|[AfxGetMainWnd](#afxgetmainwnd)|OLE olmayan bir uygulamanın geçerli "Main" penceresine veya bir sunucu uygulamasının yerinde çerçeve penceresine bir işaretçi döndürür.|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Uygulamanın, kayıt defteri erişimini **HKEY_CURRENT_USER** ( **HKCU**) düğümüne yeniden yönlendirip yönlendirmediğini öğrenmek için bu işlevi kullanın.|
|[AfxGetResourceHandle](#afxgetresourcehandle)|Uygulamanın varsayılan kaynaklarının kaynağına bir HıNSTANCE döndürür. Uygulamanın kaynaklarına doğrudan erişmek için bunu kullanın.|
|[AfxGetThread](#afxgetthread)|Geçerli [CWinThread](../../mfc/reference/cwinthread-class.md) nesnesine bir işaretçi alır.|
|[AfxInitRichEdit](#afxinitrichedit)|Uygulama için sürüm 1,0 zengin düzenleme denetimini başlatır.|
|[Afxınitrichedit2](#afxinitrichedit2)|Uygulama için sürüm 2,0 ve üzeri zengin düzenleme denetimini başlatır.|
|[Afxısextendedframeclass](#afxisextendedframeclass)|Verilen pencerenin genişletilmiş bir çerçeve nesnesi olup olmadığını belirler.|
|[Afxısmfctoolbar](#afxismfctoolbar)|Verilen pencerenin bir araç çubuğu nesnesi olup olmadığını belirler.|
|[AfxKeyboardManager](#afxkeyboardmanager)|Genel [klavye Yöneticisi](ckeyboardmanager-class.md)işaretçisi.|
|[AfxLoadLibrary](#afxloadlibrary)|Bir DLL modülünü eşleştirir ve bir DLL işlevinin adresini elde etmek için kullanılabilecek bir tanıtıcı döndürür.|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|Genel [etiket menü Yöneticisi](cmenutearoffmanager-class.md)işaretçisi.|
|[AfxMouseManager](#afxmousemanager)|Genel [Fare Yöneticisi](cmousemanager-class.md)işaretçisi.|
|[AfxRegisterClass](#afxregisterclass)|MFC kullanan bir DLL 'ye bir pencere sınıfı kaydeder.|
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC tarafından otomatik olarak kaydedilen kayıtları tamamlamak için bir Windows pencere sınıfını kaydeder.|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Uygulamanın, kayıt defteri erişimini **HKEY_CURRENT_USER** ( **HKCU**) düğümüne yeniden yönlendirip yönlendirmeyeceğini ayarlar.|
|[AfxSetResourceHandle](#afxsetresourcehandle)|Uygulamanın varsayılan kaynaklarının yüklendiği HıNSTANCE tanıtıcısını ayarlar.|
|[AfxShellManager](#afxshellmanager)|Genel [Kabuk Yöneticisi](cshellmanager-class.md)işaretçisi. |
|[AfxSocketInit](#afxsocketinit)|Windows yuvaları başlatmak `CWinApp::InitInstance` için bir geçersiz kılma içinde çağırılır.|
|[Afxuseraraçları Yöneticisi](#afxusertoolsmanager)|Genel [Kullanıcı araçları Yöneticisi](cusertoolsmanager-class.md)işaretçisi.|
|[AfxWinInit](#afxwininit)|MFC 'yi başlatmak için GUI tabanlı `WinMain` bir uygulamanın [CWinApp](../../mfc/reference/cwinapp-class.md) başlatması kapsamında MFC tarafından sağlanan işlev tarafından çağırılır. MFC kullanan konsol uygulamaları için doğrudan çağrılmalıdır.|

##  <a name="afxbeginthread"></a>AfxBeginThread

Yeni bir iş parçacığı oluşturmak için bu işlevi çağırın.

```
CWinThread* AfxBeginThread(
    AFX_THREADPROC pfnThreadProc,
    LPVOID pParam,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);

CWinThread* AfxBeginThread(
    CRuntimeClass* pThreadClass,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>Parametreler

*pfnThreadProc*<br/>
Çalışan iş parçacığı için denetim işlevine işaret eder. NULL olamaz. Bu işlev şu şekilde bildirilmelidir:

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThreadClass*<br/>
[CWinThread](../../mfc/reference/cwinthread-class.md)öğesinden türetilen BIR nesnenin RUNTIME_CLASS.

*pParam*<br/>
*PfnThreadProc*içindeki işlev bildirimine parametre olarak gösterildiği gibi, Denetim işlevine geçirilecek parametre.

*Nöncelik*<br/>
İş parçacığının istenen önceliği. Kullanılabilir önceliklerin tam listesi ve açıklaması için bkz. Windows SDK [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) .

*nStackSize*<br/>
Yeni iş parçacığı için yığının bayt cinsinden boyutunu belirtir. 0 ise yığın boyutu, oluşturma iş parçacığıyla varsayılan olarak aynı boyut yığınına göre yapılır.

*dwCreateFlags*<br/>
İş parçacığının oluşturulmasını denetleyen ek bir bayrak belirtir. Bu bayrak iki değerden birini içerebilir:

- CREATE_SUSPENDED bir iş parçacığını askıya alma sayısı ile başlatır. Create_suspended `CWinThread` kullanın; örneğin, [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) veya türetilmiş sınıfınızın herhangi bir üyesi gibi, iş parçacığı çalışmaya başlamadan önce nesne. Başlatma işlemi tamamlandıktan sonra, çalıştıran iş parçacığını başlatmak için [CWinThread:: ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) ' i kullanın. İş parçacığı çağrılana kadar `CWinThread::ResumeThread` yürütülmez.

- **0** oluşturulduktan hemen sonra iş parçacığını başlatın.

*lpSecurityAttrs*<br/>
İş parçacığının güvenlik özniteliklerini belirten bir [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) yapısına işaret eder. NULL ise, oluşturma iş parçacığıyla aynı güvenlik öznitelikleri kullanılacaktır. Bu yapı hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan iş parçacığı nesnesine işaretçi veya bir hata oluşursa NULL.

### <a name="remarks"></a>Açıklamalar

İlk formu `AfxBeginThread` bir çalışan iş parçacığı oluşturur. İkinci form, Kullanıcı arabirimi iş parçacığı veya çalışan iş parçacığı olarak görev yapabilecek bir iş parçacığı oluşturur.

`AfxBeginThread`Yeni `CWinThread` bir nesne oluşturur, iş parçacığını yürütmeye başlamak için [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) işlevini çağırır ve iş parçacığına bir işaretçi döndürür. Tüm nesnelerin düzgün şekilde serbest bırakıldığından emin olmak için, oluşturma yordamının tamamında denetimler yapılır İş parçacığını sonlandırmak için, iş parçacığının içinden [AfxEndThread](#afxendthread) çağrısı yapın veya çalışan iş parçacığının denetim işlevinden geri dönün.

Çoklu iş parçacığı uygulama tarafından etkinleştirilmelidir; Aksi takdirde, bu işlev başarısız olur. Çoklu iş parçacığı kullanımı hakkında daha fazla bilgi için bkz. [/MD,/MT,/LD (çalışma zamanı kitaplığını kullanın)](../../build/reference/md-mt-ld-use-run-time-library.md) , *Visual C++ derleyicisi seçenekleri*altında.

Hakkında `AfxBeginThread`daha fazla bilgi için bkz. çoklu [iş parçacıklı makaleler: Çalışan iş parçacıkları](../../parallel/multithreading-creating-worker-threads.md) ve [çoklu iş parçacığı oluşturma: Kullanıcı arabirimi Iş parçacıkları](../../parallel/multithreading-creating-user-interface-threads.md)oluşturma.

### <a name="example"></a>Örnek

[CSocket:: Attach](../../mfc/reference/csocket-class.md#attach)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxcontextmenumanager"></a>AfxContextMenuManager

Genel [bağlam menü Yöneticisi](ccontextmenumanager-class.md)işaretçisi.

### <a name="syntax"></a>Sözdizimi

```
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcontextmenumanager. h

##  <a name="afxendthread"></a>AfxEndThread

Yürütülmekte olan iş parçacığını sonlandırmak için bu işlevi çağırın.

```
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>Parametreler

*nExitCode*<br/>
İş parçacığının çıkış kodunu belirtir.

*bDelete*<br/>
İş parçacığı nesnesini bellekten siler.

### <a name="remarks"></a>Açıklamalar

Sonlandırılacak iş parçacığının içinden çağrılmalıdır.

Hakkında `AfxEndThread`daha fazla bilgi için çoklu iş parçacığı [oluşturma makalesine bakın: Iş parçacıkları](../../parallel/multithreading-terminating-threads.md)sonlandırılıyor.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

  ## <a name="afxfindresourcehandle"></a>AfxFindResourceHandle
Kaynak `AfxFindResourceHandle` zincirini incelemek ve kaynak kimliğine ve kaynak türüne göre belirli bir kaynağı bulmak için kullanın.

### <a name="syntax"></a>Sözdizimi

```
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Kaynak KIMLIĞINI içeren bir dize işaretçisi.
*lpszType*<br/>
Kaynak türüne yönelik bir işaretçi. Kaynak türlerinin listesi için bkz. Windows SDK [FindResource](/windows/win32/api/winbase/nf-winbase-findresourcew) .

### <a name="return-value"></a>Dönüş Değeri

Kaynağı içeren modülün tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

`AfxFindResourceHandle`belirli kaynağı bulur ve kaynağı içeren modüle bir tanıtıcı döndürür. Kaynak, yüklemiş olduğunuz herhangi bir MFC uzantı DLL dosyasında olabilir. `AfxFindResourceHandle`size kaynağı olduğunu söyler.

Modüller şu sırayla aranır:

1. Ana modül (MFC uzantısı DLL ise).

1. Sistem dışı modüller.

1. Dile özgü modüller.

1. Ana modül (bir sistem DLL 'si ise).

1. Sistem modülleri.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="afxfreelibrary"></a>AfxFreeLibrary

Her `AfxFreeLibrary` ikisi `AfxLoadLibrary` de, yüklenen her kitaplık modülü için bir başvuru sayısı saklayın.

```
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>Parametreler

*Hınstlib*<br/>
Yüklenen kitaplık modülünün tanıtıcısı. [AfxLoadLibrary](#afxloadlibrary) bu tanıtıcıyı döndürür.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

`AfxFreeLibrary`yüklenen dinamik bağlantı kitaplığı (DLL) modülünün başvuru sayısını azaltır. Başvuru sayısı sıfıra ulaştığında, modül çağıran işlemin adres alanından eşlenmemiş ve tanıtıcı artık geçerli değildir. Bu başvuru sayısı her `AfxLoadLibrary` çağrıldığında artırılır.

Bir kitaplık modülünün eşlemesini kaldırmadan önce, sistem DLL 'yi kullanarak işlemlerden ayrılabilmesini sağlar. Bunun yapılması DLL 'ye geçerli işlem adına ayrılan kaynakları temizleme fırsatı verir. Giriş noktası işlevi döndüğünde, kitaplık modülü geçerli işlemin adres alanından kaldırılır.

Bir `AfxLoadLibrary` dll modülünü eşlemek için kullanın.

Uygulamanız birden çok iş `AfxFreeLibrary` parçacığı `AfxLoadLibrary` kullanıyorsa, ve ' ı ( `FreeLibrary` Win32 `LoadLibrary`işlevleri yerine) kullandığınızdan emin olun. Kullanarak `AfxLoadLibrary` ,`AfxFreeLibrary` MFC uzantı dll 'si yüklendiğinde ve kaldırıldığında çalıştırılan başlatma ve başlatma kodunun genel MFC durumunu bozmamasını sağlar.

### <a name="example"></a>Örnek

[AfxLoadLibrary](#afxloadlibrary)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdll_. h

##  <a name="afxgetapp"></a>AfxGetApp

Bu işlevin döndürdüğü işaretçi, ana ileti gönderme kodu veya en üstteki pencere gibi uygulama bilgilerine erişmek için kullanılabilir.

```
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın tek `CWinApp` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem NULL döndürürse, uygulama ana penceresinin henüz tam olarak başlatılmamış olduğunu gösteriyor olabilir. Bir sorunu da gösterebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

##  <a name="afxgetappname"></a>AfxGetAppName

Bu işlev tarafından döndürülen dize, tanılama iletileri veya geçici dize adları için bir kök olarak kullanılabilir.

```
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın adını içeren, null ile sonlandırılmış bir dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

##  <a name="afxgetinstancehandle"></a>AfxGetInstanceHandle

Bu işlev, geçerli uygulamanın örnek tanıtıcısını almanızı sağlar.

```
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın geçerli örneğine bir HıNSTANCE. MFC 'nin USRDLL sürümü ile bağlantılı bir DLL içinden çağrılırsa, DLL 'ye bir HıNSTANCE döndürülür.

### <a name="remarks"></a>Açıklamalar

`AfxGetInstanceHandle`her zaman yürütülebilir dosyanızın HıNSTANCE değerini döndürür (. EXE), MFC 'nin USRDLL sürümüyle bağlantılı DLL içinden çağrılmadığı müddetçe. Bu durumda, DLL 'ye bir HıNSTANCE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

##  <a name="afxgetmainwnd"></a>AfxGetMainWnd

Uygulamanız bir OLE sunucusu ise, uygulama nesnesinin [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) üyesine doğrudan başvurmak yerine uygulamanın etkin ana penceresine bir işaretçi almak için bu işlevi çağırın.

```
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>Dönüş Değeri

Sunucuda bir kapsayıcı içinde etkin olan bir nesne varsa ve bu kapsayıcı etkin ise, bu işlev, yerinde etkin belgeyi içeren çerçeve pencere nesnesine bir işaretçi döndürür.

Bir kapsayıcı içinde yerinde etkin bir nesne yoksa veya uygulamanız bir OLE sunucusu değilse, bu işlev yalnızca uygulama nesnenizin *m_pMainWnd* döndürür.

`AfxGetMainWnd` Uygulamanın birincil iş parçacığından çağrılırsa, yukarıdaki kurallara göre uygulamanın ana penceresini döndürür. İşlev uygulamadaki bir ikincil iş parçacığından çağrılırsa, işlev, çağrıyı yapan iş parçacığıyla ilişkili ana pencereyi döndürür.

### <a name="remarks"></a>Açıklamalar

Uygulamanız bir OLE sunucusu değilse, bu işlevi çağırmak, uygulama nesnenizin *m_pMainWnd* üyesine doğrudan başvuran ile eşdeğerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

##  <a name="afxgetperuserregistration"></a>AfxGetPerUserRegistration

Uygulamanın, kayıt defteri erişimini **HKEY_CURRENT_USER** ( **HKCU**) düğümüne yeniden yönlendirip yönlendirmediğini öğrenmek için bu işlevi kullanın.

```
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>Dönüş Değeri

DOĞRU, kayıt defteri bilgilerinin HKCU düğümüne yönlendirildiğini gösterir; FALSE, uygulamanın kayıt defteri bilgilerini varsayılan düğüme yazdığını gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** ( **HKCR**).

### <a name="remarks"></a>Açıklamalar

Kayıt defteri yönlendirmesini etkinleştirirseniz Framework, **HKCR** 'den **HKEY_CURRENT_USER\Software\Classes**'e erişimi yeniden yönlendirir. Yalnızca MFC ve ATL çerçeveleri yeniden yönlendirmeden etkilenir.

Uygulamanın kayıt defteri erişimini yeniden yönlendirip yönlendirmediğini değiştirmek için [AfxSetPerUserRegistration](#afxsetperuserregistration)kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxstat_. h

##  <a name="afxgetresourcehandle"></a>AfxGetResourceHandle

Uygulamanın kaynaklarına doğrudan erişmek için bu işlev tarafından döndürülen HıNSTANCE tutamacını kullanın, örneğin, Windows işlevine `FindResource`yapılan çağrılar.

```
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın varsayılan kaynaklarının yüklendiği bir HıNSTANCE tanıtıcısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

##  <a name="afxgetthread"></a>AfxGetThread

Şu anda yürütülmekte olan iş parçacığını temsil eden [CWinThread](../../mfc/reference/cwinthread-class.md) nesnesine bir işaretçi almak için bu işlevi çağırın.

```
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda yürütülmekte olan iş parçacığına yönelik işaretçi; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

, İstenen iş parçacığı içinden çağrılmalıdır.

> [!NOTE]
>  4,2, 5,0 veya `AfxGetThread` 6,0 görsel C++ sürümlerinden çağıran bir MFC projesi oluşturuyorsanız, hiçbir iş parçacığı bulunmazsa `AfxGetThread` [AfxGetApp](#afxgetapp) ' i çağırır. Derleyicinin daha yeni sürümlerinde, `AfxGetThread` hiçbir iş parçacığı bulunmazsa null değeri döndürür. Uygulama iş parçacığını istiyorsanız, öğesini çağırmanız `AfxGetApp`gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

##  <a name="afxinitrichedit"></a>AfxInitRichEdit

Uygulamanın zengin düzenleme denetimini (sürüm 1,0) başlatmak için bu işlevi çağırın.

```
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev geriye dönük uyumluluk için sağlanır. Yeni uygulamalar [AfxInitRichEdit2](#afxinitrichedit2)kullanmalıdır.

`AfxInitRichEdit`RICHED32 yükler. Zengin düzenleme denetiminin 1,0 sürümünü başlatmak için DLL. Zengin düzenleme denetiminin 2,0 ve 3,0 sürümünü kullanmak için, RICHED20. DLL 'nin yüklenmesi gerekiyor. Bu, [AfxInitRichEdit2](#afxinitrichedit2)çağrısıyla gerçekleştirilir.

Mevcut görsel C++ uygulamalardaki zengin düzenleme denetimlerini sürüm 2,0 ' ye güncelleştirmek için öğesini açın. RC dosyası metin olarak, her zengin düzenleme denetiminin sınıf adını "RICHEDIT" yerine "RichEdit20a" olarak değiştirin. Ardından çağrısını `AfxInitRichEdit` ile `AfxInitRichEdit2`değiştirin.

Bu işlev, kitaplık zaten işlem için başlatılmamışsa ortak denetimler kitaplığını da başlatır. Zengin düzenleme denetimini doğrudan MFC uygulamanızdan kullanırsanız, MFC 'nin zengin düzenleme denetimi çalışma zamanını düzgün bir şekilde başlattığını güvence altına almak için bu işlevi çağırmanız gerekir. [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md)veya [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)oluşturma yöntemini çağırırsanız, genellikle bu işlevi çağırmanız gerekmez, ancak bazı durumlarda gerekli olabilir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

##  <a name="afxinitrichedit2"></a>Afxınitrichedit2

Uygulamanın zengin düzenleme denetimini (sürüm 2,0 ve üzeri) başlatmak için bu işlevi çağırın.

```
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>Açıklamalar

RICHED20 yüklemek için bu işlevi çağırın. DLL ve zengin düzenleme denetiminin 2,0 sürümünü başlatın. [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md)veya [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)oluşturma yöntemini çağırırsanız, genellikle bu işlevi çağırmanız gerekmez, ancak bazı durumlarda gerekli olabilir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

  ## <a name="afxisextendedframeclass"></a>Afxısextendedframeclass
Verilen pencerenin genişletilmiş bir çerçeve nesnesi olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Öğesinden `CWnd`türetilmiş bir nesne için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen pencere bir genişletilmiş çerçeve nesneliyse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, *pWnd* aşağıdaki sınıflardan birini TÜRETILIYOR true değerini döndürür:

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

Bu yöntem, bir işlev veya yöntem parametresinin genişletilmiş çerçeve penceresi olduğunu doğrulamanız gerektiğinde faydalıdır.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** AFXPRIV. h

## <a name="afxismfctoolbar"></a>Afxısmfctoolbar

Verilen pencerenin bir araç çubuğu nesnesi olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Öğesinden `CWnd`türetilmiş bir nesne için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen pencere bir araç çubuğu nesneliyse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `TRUE` *pWnd* öğesinden `CMFCToolBar`türetilse döndürür. Bu yöntem, bir işlev veya yöntem parametresinin bir `CMFCToolBar` nesne olduğunu doğrulamanız gerektiğinde faydalıdır.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** AFXPRIV. h

## <a name="afxkeyboardmanager"></a>AfxKeyboardManager

Genel [klavye Yöneticisi](ckeyboardmanager-class.md)işaretçisi.

### <a name="syntax"></a>Sözdizimi

```
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxkeyboardmanager. h

##  <a name="afxloadlibrary"></a>AfxLoadLibrary

Bir `AfxLoadLibrary` dll modülünü eşlemek için kullanın.

```
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>Parametreler

*lpszModuleName*<br/>
Modülün adını içeren, null ile sonlandırılmış bir dizeye işaret eder (bir. DLL veya. EXE dosyası). Belirtilen ad modülün dosya adıdır.

Dize bir yol belirtiyorsa ancak dosya belirtilen dizinde yoksa, işlev başarısız olur.

Bir yol belirtilmemişse ve dosya adı uzantısı atlanırsa, varsayılan uzantı. DLL eklenir. Ancak, dosya adı dizesi, modül adının uzantıya sahip olmadığını göstermek için sondaki nokta karakterini (.) içerebilir. Hiçbir yol belirtilmediğinde, işlev dosyayı aşağıdaki sırayla arar:

- Uygulamanın yüklendiği dizin.

- Geçerli dizin.

- **Windows 95/98:** Windows sistem dizini. **Windows NT:** 32 bitlik Windows sistem dizini. Bu dizinin adı SYSTEM32 ' dir.

- **Yalnızca Windows NT:** 16 bit Windows sistem dizini. Bu dizinin yolunu alan Win32 işlevi yoktur, ancak arama yapılır. Bu dizinin adı SISTEM.

- Windows dizini.

- PATH ortam değişkeninde listelenen dizinler.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri modülün bir tanıtıcıdır. İşlev başarısız olursa, dönüş değeri NULL olur.

### <a name="remarks"></a>Açıklamalar

Bir DLL işlevinin adresini almak için [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) içinde kullanılabilecek bir tanıtıcı döndürür. `AfxLoadLibrary`, diğer yürütülebilir modülleri eşlemek için de kullanılabilir.

Her işlem, yüklenen her kitaplık modülü için bir başvuru sayısı tutar. Her çağrılışında `AfxLoadLibrary` bu başvuru sayısı artırılır ve `AfxFreeLibrary` her çağrıldığında azaltılır. Başvuru sayısı sıfıra ulaştığında, modül çağıran işlemin adres alanından eşlenmemiş ve tanıtıcı artık geçerli değildir.

Uygulamanız birden çok iş `AfxLoadLibrary` parçacığı `AfxFreeLibrary` kullanıyorsa ve dinamik olarak bir mfc uzantısı `FreeLibrary`dll yüklerse, ve ' ı (Win32 işlevleri `LoadLibrary` yerine) kullandığınızdan emin olun. `AfxLoadLibrary` Ve`AfxFreeLibrary` yöntem kullanarak, MFC uzantı dll 'si yüklendiğinde ve kaldırıldığında çalıştırılan başlangıç ve kapalı kodu genel MFC durumunu bozmaz.

Bir `AfxLoadLibrary` uygulamada kullanmak için MFC 'nin dll sürümüne dinamik olarak bağlantı oluşturmanız gerekir; örneğin, Afxdll_. h için `AfxLoadLibrary`üst bilgi dosyası, yalnızca MFC bir dll olarak uygulamaya bağlanmışsa dahil edilir. MFC uzantı dll 'Leri kullanmak veya oluşturmak için MFC 'nin DLL sürümüne bağlamanız gerektiğinden, bu tasarıma göre yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdll_. h

## <a name="afxmenutearoffmanager"></a>AfxMenuTearOffManager

Genel [etiket menü Yöneticisi](cmenutearoffmanager-class.md)işaretçisi.

### <a name="syntax"></a>Sözdizimi

```
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmenutearoffmanager. h

## <a name="afxmousemanager"></a>AfxMouseManager

Genel [Fare Yöneticisi](cmousemanager-class.md)işaretçisi.

### <a name="syntax"></a>Sözdizimi

```
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmousemanager. h

##  <a name="afxregisterclass"></a>AfxRegisterClass

MFC kullanan bir DLL 'ye pencere sınıflarını kaydetmek için bu işlevi kullanın.

```
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>Parametreler

*lpWndClass*<br/>
Kaydedilecek pencere sınıfıyla ilgili bilgileri içeren bir [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısına yönelik işaretçi. Bu yapı hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="return-value"></a>Dönüş Değeri

Sınıf başarıyla kaydedilmişse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullanırsanız, DLL kaldırıldığında sınıf otomatik olarak kaydı kaldırılır.

DLL olmayan derlemelerde, `AfxRegisterClass` bir uygulamaya kayıtlı sınıfların otomatik olarak kaydı olduğundan, tanımlayıcı, Windows işleviyle `RegisterClass`eşlenen bir makro olarak tanımlanır. `AfxRegisterClass` Yerinekullanıyorsanız,kodunuzhemuygulamadahemdedll`RegisterClass`'de değişiklik yapılmadan kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

##  <a name="afxregisterwndclass"></a>AfxRegisterWndClass

Kendi pencere sınıflarınızı kaydetmenizi sağlar.

```
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>Parametreler

*nClassStyle*<br/>
Pencere sınıfı için bit düzeyinde OR ( **&#124;** ) işleci kullanılarak oluşturulan Windows sınıf stilini veya stil bileşimini belirtir. Sınıf stillerinin listesi için Windows SDK [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısına bakın. NULL ise varsayılanlar aşağıdaki gibi ayarlanır:

- Fare stilini, kullanıcı fareyle çift tıkladığında pencere yordamına çift tıklama iletileri gönderen CS_DBLCLKS olarak ayarlar.

- Ok imleç stilini Windows standart IDC_ARROW olarak ayarlar.

- Arka plan fırçasını NULL olarak ayarlar, bu nedenle pencere arka planını silmez.

- Simgeyi standart, geri dönen bayrak Windows logosu simgesine ayarlar.

*hCursor*<br/>
Pencere sınıfından oluşturulan her bir pencerede yüklenecek imleç kaynağına yönelik bir tanıtıcı belirtir. Varsayılan değer olan **0**' ı kullanırsanız, standart IDC_ARROW imlecini alırsınız.

*hbrBackground*<br/>
Pencere sınıfından oluşturulan her bir pencerede yüklenecek fırça kaynağı için bir tanıtıcı belirtir. Varsayılan değer olan **0**' ı kullanırsanız, bir arka plan fırçanızı görürsünüz ve varsayılan olarak, [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd)işlerken arka planını silmez.

*HICON*<br/>
Pencere sınıfından oluşturulan her bir pencerede yüklenecek simge kaynağına yönelik bir tanıtıcı belirtir. Varsayılan değer olan **0**' ı kullanırsanız, standart, geri alma işareti Windows logosu simgesini görürsünüz.

### <a name="return-value"></a>Dönüş Değeri

Sınıf adını içeren, null ile sonlandırılmış bir dize. Bu sınıf adını `Create` , bir pencere oluşturmak için `CWnd` veya diğer **CWnd-** türetilmiş sınıflarda üye işlevine geçirebilirsiniz. Ad, Microsoft Foundation Class Kitaplığı tarafından oluşturulur.

> [!NOTE]
>  Dönüş değeri, statik arabelleğin bir işaretçisidir. Bu dizeyi kaydetmek için bir `CString` değişkene atayın.

### <a name="remarks"></a>Açıklamalar

Microsoft Foundation Class Kitaplığı, sizin için birkaç standart pencere sınıfını otomatik olarak kaydeder. Kendi pencere sınıflarınızı kaydetmek istiyorsanız bu işlevi çağırın.

Bir sınıf `AfxRegisterWndClass` için kaydedilen ad yalnızca parametrelere bağlıdır. Aynı parametrelerle birden `AfxRegisterWndClass` çok kez çağrı yaparsanız, ilk çağrıda yalnızca bir sınıf kaydedilir. Özdeş parametrelerle yapılan `AfxRegisterWndClass` sonraki çağrılar yalnızca zaten kayıtlı ClassName döndürür.

Aynı parametrelerle birden `AfxRegisterWndClass` çok CWnd ile türetilmiş sınıf için çağrı yaparsanız, her sınıf için ayrı bir pencere sınıfı almak yerine, her bir sınıf aynı pencere sınıfını paylaşır. Bu, CS_CLASSDC sınıf stili kullanıldığında sorunlara neden olabilir. Birden çok CS_CLASSDC pencere sınıfı yerine, tek bir CS_CLASSDC Window sınıfı ile sona erdir ve bu sınıfı C++ kullanan tüm pencereler aynı DC 'yi paylaşır. Bu sorundan kaçınmak için, sınıfı kaydetmek üzere [AfxRegisterClass](#afxregisterclass) ' ı çağırın.

Teknik notTN001 [başvurun: Pencere sınıfı kaydı](../../mfc/tn001-window-class-registration.md) `AfxRegisterWndClass` ve işlev hakkında daha fazla bilgi için pencere sınıfı kaydı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

##  <a name="afxsetperuserregistration"></a>AfxSetPerUserRegistration

Uygulamanın, kayıt defteri erişimini **HKEY_CURRENT_USER** ( **HKCU**) düğümüne yeniden yönlendirip yönlendirmeyeceğini ayarlar.

```
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki DOĞRU, kayıt defteri bilgilerinin HKCU düğümüne yönlendirildiğini gösterir; FALSE, uygulamanın kayıt defteri bilgilerini varsayılan düğüme yazdığını gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** ( **HKCR**).

### <a name="remarks"></a>Açıklamalar

Windows Vista 'Dan önce, kayıt defterine erişen uygulamalar, genellikle **HKEY_CLASSES_ROOT** düğümünü kullanır. Bununla birlikte, Windows Vista veya sonraki işletim sistemlerinde, bir uygulamayı Yükseltilmiş modda çalıştırıp HKCR 'ye yazmanız gerekir.

Bu yöntem, uygulamanızda kayıt defteri erişimini HKCR 'den HKCU 'a yönlendirerek, uygulamanızın, yükseltilmiş modda çalıştırmadan kayıt defterine okumasını ve yazmasına olanak sağlar. Daha fazla bilgi için bkz. [bağlayıcı özellik sayfaları](../../build/reference/linker-property-pages.md).

Kayıt defteri yönlendirmesini etkinleştirirseniz Framework, HKCR 'den **HKEY_CURRENT_USER\Software\Classes**'e erişimi yeniden yönlendirir. Yalnızca MFC ve ATL çerçeveleri yeniden yönlendirmeden etkilenir.

Varsayılan uygulama, HKCR altında kayıt defterine erişir.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxstat_. h

##  <a name="afxsetresourcehandle"></a>AfxSetResourceHandle

Uygulamanın varsayılan kaynaklarının nereye yükleneceğini belirleyen HıNSTANCE tanıtıcısını ayarlamak için bu işlevi kullanın.

```
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>Parametreler

*Hınstresource*<br/>
Örneği veya modülü bir olarak işleme. Uygulama kaynaklarının yüklendiği EXE veya DLL dosyası.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxshellmanager"></a>AfxShellManager

Genel [Kabuk Yöneticisi](cshellmanager-class.md)işaretçisi.

### <a name="syntax"></a>Sözdizimi

```
CShellManager* afxShellManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxshellmanager. h

##  <a name="afxsocketinit"></a>AfxSocketInit

Windows yuvaları başlatmak için bu `CWinApp::InitInstance` işlevi geçersiz kılmada çağırın.

```
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>Parametreler

*Lpwsaverileri*<br/>
Bir [Wsaveri](/windows/win32/api/winsock2/ns-winsock2-wsadata) yapısına yönelik işaretçi. *Lpwsaverileri* null değerine eşit değilse, `WSADATA` yapının adresi öğesine `WSAStartup`çağrısıyla doldurulur. Bu işlev, uygulama sonlanmadan önce sizin için de çağırılmasını sağlar `WSACleanup` .

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Statik olarak bağlı bir MFC uygulamasında ikincil iş parçacıklarında MFC Yuvaları kullanırken, yuva kitaplıklarını başlatmak `AfxSocketInit` için yuva kullanan her bir iş parçacığında çağrı yapmanız gerekir. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığında çağırılır.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxsock. h

## <a name="afxusertoolsmanager"></a>Afxuseraraçları Yöneticisi

Genel [Kullanıcı araçları Yöneticisi](cusertoolsmanager-class.md)işaretçisi.

### <a name="syntax"></a>Sözdizimi

```
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxuseraraçları Yöneticisi. h

##  <a name="afxwininit"></a>AfxWinInit

Bu işlev, MFC 'yi başlatmak için GUI tabanlı `WinMain` bir uygulamanın [CWinApp](../../mfc/reference/cwinapp-class.md) başlatması kapsamında MFC tarafından sağlanan işlev tarafından çağrılır.

```
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
Çalışmakta olan modülün tanıtıcısı.

*hPrevInstance*<br/>
Uygulamanın önceki bir örneğine yönelik bir tanıtıcı. Win32 tabanlı bir uygulama için, bu parametre her zaman **null**olur.

*lpCmdLine*<br/>
Uygulamanın komut satırını belirten, null ile sonlandırılmış bir dizeye işaret eder.

*nCmdShow*<br/>
GUI uygulamasının ana penceresinin nasıl gösterileceğini belirtir.

### <a name="remarks"></a>Açıklamalar

MFC tarafından sağlanan `WinMain` işlevi kullanmayan bir konsol uygulaması için doğrudan MFC 'yi başlatmak için çağırmanız `AfxWinInit` gerekir.

Kendi kendinize çağrı `AfxWinInit` yaparsanız bir `CWinApp` sınıfın örneğini bildirmeniz gerekir. Bir konsol uygulaması için, ' dan kendi sınıfınızı türetmekten `CWinApp` ve bunun yerine `CWinApp` doğrudan bir örneğini kullanmanıza tercih edebilirsiniz. **Main**uygulamanızda uygulamanız için tüm işlevleri bırakmaya karar verirseniz bu teknik uygundur.

> [!NOTE]
>  Bir derleme için bir etkinleştirme bağlamı oluşturduğunda, MFC kullanıcı modülü tarafından sağlanmış bir bildirim kaynağı kullanır. Etkinleştirme bağlamı ' de `AfxWinInit`oluşturulur. Daha fazla bilgi için bkz. [MFC modül durumunda etkinleştirme bağlamları Için destek](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
[CWinApp Sınıfı](cwinapp-class.md)<br/>
[CContextMenuManager Sınıfı](ccontextmenumanager-class.md)<br/>
[CWnd Sınıfı](cwnd-class.md)<br/>
[CFrameWndEx Sınıfı](cframewndex-class.md)<br/>
[CMFCToolBar Sınıfı](cmfctoolbar-class.md)<br/>
[CKeyboardManager Sınıfı](ckeyboardmanager-class.md)<br/>
[CMenuTearOffManager Sınıfı](cmenutearoffmanager-class.md)<br/>
[CMouseManager Sınıfı](cmousemanager-class.md)<br/>
[CShellManager Sınıfı](cshellmanager-class.md)<br/>
[CUserToolsManager Sınıfı](cusertoolsmanager-class.md)
