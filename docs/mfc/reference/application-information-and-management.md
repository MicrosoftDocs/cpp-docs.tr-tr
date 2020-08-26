---
title: Uygulama bilgileri ve yönetimi
description: Microsoft Foundation Class Library (MFC) uygulama bilgileri ve yönetim işlevlerine başvuru.
ms.date: 01/27/2020
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: 3412ed3f02e93d3e8c947d4f730355c219493a77
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832314"
---
# <a name="application-information-and-management"></a>Uygulama bilgileri ve yönetimi

Bir uygulama yazdığınızda, tek bir [CWinApp](../../mfc/reference/cwinapp-class.md)türetilen nesne oluşturursunuz. Her zaman, türetilmiş nesnenin dışından bu nesne hakkında bilgi almak isteyebilirsiniz `CWinApp` . Ya da diğer genel "Manager" nesnelerine erişmeniz gerekebilir.

Microsoft Foundation Class Kitaplığı, bu görevleri gerçekleştirmenize yardımcı olmak için aşağıdaki genel işlevleri sağlar:

## <a name="application-information-and-management-functions"></a>Uygulama bilgileri ve yönetim Işlevleri

| Ad | Açıklama |
|-|-|
|[AfxBeginThread](#afxbeginthread)|Yeni bir iş parçacığı oluşturur.|
|[AfxContextMenuManager](#afxcontextmenumanager)|Genel [bağlam menü Yöneticisi](ccontextmenumanager-class.md)işaretçisi.|
|[AfxEndThread](#afxendthread)|Geçerli iş parçacığını sonlandırır.|
|[AfxFindResourceHandle](#afxfindresourcehandle)|Kaynak zincirine ve kaynak KIMLIĞI ve kaynak türüne göre belirli bir kaynağı bulur. |
|[AfxFreeLibrary](#afxfreelibrary)|Yüklenen dinamik bağlantı kitaplığı (DLL) modülünün başvuru sayısını azaltır. Başvuru sayısı sıfıra ulaştığında, modül eşlenmemiş olur.|
|[AfxGetApp](#afxgetapp)|Uygulamanın tek nesnesine bir işaretçi döndürür `CWinApp` .|
|[AfxGetAppName](#afxgetappname)|Uygulamanın adını içeren bir dize döndürür.|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|Uygulamanın bu örneğini temsil eden bir HıNSTANCE döndürür.|
|[AfxGetMainWnd](#afxgetmainwnd)|OLE olmayan bir uygulamanın geçerli "Main" penceresine veya bir sunucu uygulamasının yerinde çerçeve penceresine bir işaretçi döndürür.|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** (**HKCU**) düğümüne yeniden yönlendirip yönlendirmediğini öğrenmek için bu işlevi kullanın.|
|[AfxGetResourceHandle](#afxgetresourcehandle)|Uygulamanın varsayılan kaynaklarının kaynağına bir HıNSTANCE döndürür. Uygulamanın kaynaklarına doğrudan erişmek için kullanın.|
|[AfxGetThread](#afxgetthread)|Geçerli [CWinThread](../../mfc/reference/cwinthread-class.md) nesnesine bir işaretçi alır.|
|[AfxInitRichEdit](#afxinitrichedit)|Uygulama için sürüm 1,0 zengin düzenleme denetimini başlatır.|
|[Afxınitrichedit2](#afxinitrichedit2)|Uygulama için sürüm 2,0 ve üzeri zengin düzenleme denetimini başlatır.|
|[Afxısextendedframeclass](#afxisextendedframeclass)|Verilen pencerenin genişletilmiş bir çerçeve nesnesi olup olmadığını belirler.|
|[Afxısmfctoolbar](#afxismfctoolbar)|Verilen pencerenin bir araç çubuğu nesnesi olup olmadığını belirler.|
|[AfxKeyboardManager](#afxkeyboardmanager)|Genel [klavye Yöneticisi](ckeyboardmanager-class.md)işaretçisi.|
|[AfxLoadLibrary](#afxloadlibrary)|Bir DLL modülünü eşleştirir ve bir DLL işlevinin adresini elde etmek için kullanılabilecek bir tanıtıcı döndürür.|
|[AfxLoadLibraryEx](#afxloadlibraryex)|Belirtilen seçenekleri kullanarak bir DLL modülünü eşleştirir ve bir DLL işlevinin adresini elde etmek için kullanılabilecek bir tanıtıcı döndürür.|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|Küresel [yırma menü Yöneticisi](cmenutearoffmanager-class.md)işaretçisi.|
|[AfxMouseManager](#afxmousemanager)|Genel [Fare Yöneticisi](cmousemanager-class.md)işaretçisi.|
|[AfxRegisterClass](#afxregisterclass)|MFC kullanan bir DLL 'ye bir pencere sınıfı kaydeder.|
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC tarafından otomatik olarak kaydedilmiş olanları tamamlamak için bir Windows pencere sınıfı kaydeder.|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** (**HKCU**) düğümüne yeniden yönlendirip yönlendirmeyeceğini ayarlar.|
|[AfxSetResourceHandle](#afxsetresourcehandle)|Uygulamanın varsayılan kaynaklarının yüklendiği HıNSTANCE tanıtıcısını ayarlar.|
|[AfxShellManager](#afxshellmanager)|Genel [Kabuk Yöneticisi](cshellmanager-class.md)işaretçisi. |
|[AfxSocketInit](#afxsocketinit)|`CWinApp::InitInstance`Windows yuvaları başlatmak için bir geçersiz kılma içinde çağırılır.|
|[Afxuseraraçları Yöneticisi](#afxusertoolsmanager)|Genel [Kullanıcı araçları Yöneticisi](cusertoolsmanager-class.md)işaretçisi.|
|[AfxWinInit](#afxwininit)|MFC 'yi `WinMain` başlatmak IÇIN GUI tabanlı bir uygulamanın [CWinApp](../../mfc/reference/cwinapp-class.md) başlatması kapsamında MFC tarafından sağlanan işlev tarafından çağırılır. MFC kullanan konsol uygulamaları için doğrudan çağrılmalıdır.|

## <a name="afxbeginthread"></a><a name="afxbeginthread"></a> AfxBeginThread

Yeni bir iş parçacığı oluşturmak için bu işlevi çağırın.

```cpp
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

*pfnThreadProc*\
Çalışan iş parçacığı için denetim işlevine işaret eder. İşaretçi NULL olamaz. Bu işlev şu şekilde bildirilmelidir:

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThreadClass*\
[CWinThread](../../mfc/reference/cwinthread-class.md)öğesinden türetilen bir nesnenin RUNTIME_CLASS.

*pParam*\
Denetim işlevine geçirilecek parametre.

*Nöncelik*\
İş parçacığı için ayarlanacak öncelik. Kullanılabilir önceliklerin tam listesi ve açıklaması için bkz. Windows SDK [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) .

*nStackSize*\
Yeni iş parçacığı için yığının bayt cinsinden boyutunu belirtir. 0 ise yığın boyutu, oluşturma iş parçacığıyla varsayılan olarak aynı boyut yığınına göre yapılır.

*dwCreateFlags*\
İş parçacığının oluşturulmasını denetleyen ek bir bayrak belirtir. Bu bayrak iki değerden birini içerebilir:

- CREATE_SUSPENDED askıya alma sayısı bir tane olan iş parçacığını başlatın. `CWinThread`İş parçacığı çalışmaya başlamadan önce, nesnenin [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) veya türetilmiş sınıfınızın herhangi bir üyesi gibi herhangi bir üye verisi başlatmak istiyorsanız CREATE_SUSPENDED kullanın. Başlatma işlemi tamamlandıktan sonra, çalıştıran iş parçacığını başlatmak için [CWinThread:: ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) ' i kullanın. İş parçacığı `CWinThread::ResumeThread` çağrılana kadar yürütülmez.

- **0** oluşturulduktan hemen sonra iş parçacığını başlatın.

*lpSecurityAttrs*\
İş parçacığının güvenlik özniteliklerini belirten [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) yapısına işaret eder. NULL ise, oluşturma iş parçacığıyla aynı güvenlik öznitelikleri kullanılır. Bu yapı hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan iş parçacığı nesnesine işaretçi veya bir hata oluşursa NULL.

### <a name="remarks"></a>Açıklamalar

İlk formu `AfxBeginThread` bir çalışan iş parçacığı oluşturur. İkinci form, Kullanıcı arabirimi iş parçacığı veya çalışan iş parçacığı olarak görev yapabilecek bir iş parçacığı oluşturur.

`AfxBeginThread` Yeni bir `CWinThread` nesne oluşturur, iş parçacığını yürütmeye başlamak Için [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) işlevini çağırır ve iş parçacığına bir işaretçi döndürür. Tüm nesnelerin düzgün şekilde serbest bırakıldığından emin olmak için, oluşturma yordamının tamamında denetimler yapılır İş parçacığını sonlandırmak için, iş parçacığının içinden [AfxEndThread](#afxendthread) çağrısı yapın veya çalışan iş parçacığının denetim işlevinden geri dönün.

Çoklu iş parçacığı uygulama tarafından etkinleştirilmelidir; Aksi takdirde, bu işlev başarısız olur. Çoklu iş parçacığı sağlama hakkında daha fazla bilgi için bkz. [/MD,/MT,/LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md).

Hakkında daha fazla bilgi için `AfxBeginThread` bkz. [Çoklu iş parçacıkları: çalışan iş parçacıkları](../../parallel/multithreading-creating-worker-threads.md) ve çoklu iş parçacığı oluşturma [: Kullanıcı arabirimi iş parçacıkları oluşturma](../../parallel/multithreading-creating-user-interface-threads.md).

### <a name="example"></a>Örnek

[CSocket:: Attach](../../mfc/reference/csocket-class.md#attach)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxcontextmenumanager"></a><a name="afxcontextmenumanager"></a> AfxContextMenuManager

Genel [bağlam menü Yöneticisi](ccontextmenumanager-class.md)işaretçisi.

### <a name="syntax"></a>Syntax

```cpp
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcontextmenumanager. h

## <a name="afxendthread"></a><a name="afxendthread"></a> AfxEndThread

Yürütülmekte olan iş parçacığını sonlandırmak için bu işlevi çağırın.

```cpp
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>Parametreler

*nExitCode*\
İş parçacığının çıkış kodunu belirtir.

*bDelete*\
İş parçacığı nesnesini bellekten siler.

### <a name="remarks"></a>Açıklamalar

Sonlandırılacak iş parçacığının içinden çağrılmalıdır.

Hakkında daha fazla bilgi için `AfxEndThread` bkz. [Çoklu iş parçacığı oluşturma: Iş parçacıkları sonlandırılıyor](../../parallel/multithreading-terminating-threads.md).

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxfindresourcehandle"></a><a name="afxfindresourcehandle"></a> AfxFindResourceHandle

Kaynak `AfxFindResourceHandle` zincirini incelemek ve kaynak kimliğine ve kaynak türüne göre belirli bir kaynağı bulmak için kullanın.

### <a name="syntax"></a>Söz dizimi

```cpp
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>Parametreler

*lpszName*\
Kaynak KIMLIĞINI içeren bir dize işaretçisi.
*lpszType*\
Kaynak türüne yönelik bir işaretçi. Kaynak türlerinin listesi için bkz. Windows SDK [FindResource](/windows/win32/api/winbase/nf-winbase-findresourcea) .

### <a name="return-value"></a>Dönüş Değeri

Kaynağı içeren modülün tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

`AfxFindResourceHandle` belirli kaynağı bulur ve kaynağı içeren modüle bir tanıtıcı döndürür. Kaynak, yüklenmiş herhangi bir MFC uzantı DLL dosyasında olabilir. `AfxFindResourceHandle` size kaynağı olduğunu söyler.

Modüller şu sırayla aranır:

1. Bir MFC uzantısı DLL ise, ana modül.

1. Sistem dışı modüller.

1. Dile özgü modüller.

1. Bir sistem DLL 'SI ise ana modül.

1. Sistem modülleri.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="afxfreelibrary"></a><a name="afxfreelibrary"></a> AfxFreeLibrary

Her ikisi de `AfxFreeLibrary` , `AfxLoadLibrary` yüklenen her kitaplık modülü için bir başvuru sayısı saklayın.

```cpp
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>Parametreler

*Hınstlib*\
Yüklenen kitaplık modülünün tanıtıcısı. [AfxLoadLibrary](#afxloadlibrary) bu tanıtıcıyı döndürür.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

`AfxFreeLibrary` yüklenen dinamik bağlantı kitaplığı (DLL) modülünün başvuru sayısını azaltır. Başvuru sayısı sıfıra ulaştığında, modül çağıran işlemin adres alanından eşlenmemiş ve tanıtıcı artık geçerli değildir. Bu başvuru sayısı her `AfxLoadLibrary` çağrıldığında artırılır.

Bir kitaplık modülünün eşlemesini kaldırmadan önce, sistem DLL 'yi kullanarak işlemlerden ayrılabilmesini sağlar. Bunun yapılması DLL 'ye geçerli işlem için ayrılan kaynakları temizleme fırsatı verir. Giriş noktası işlevi döndüğünde, kitaplık modülü geçerli işlemin adres alanından kaldırılır.

`AfxLoadLibrary`BIR dll modülünü eşlemek için kullanın.

`AfxFreeLibrary` `AfxLoadLibrary` `FreeLibrary` `LoadLibrary` Uygulamanız birden çok iş parçacığı kullanıyorsa, ve ' ı (Win32 işlevleri yerine) kullandığınızdan emin olun. Kullanarak `AfxLoadLibrary` , `AfxFreeLibrary` MFC uzantı dll 'si yüklendiğinde ve bellekten kaldırıldığında çalıştırılan başlatma ve başlatma kodunun genel MFC durumunu bozmamasını sağlar.

### <a name="example"></a>Örnek

[AfxLoadLibrary](#afxloadlibrary)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdll_. h

## <a name="afxgetapp"></a><a name="afxgetapp"></a> AfxGetApp

Bu işlevin döndürdüğü işaretçi, ana ileti gönderme kodu veya en üstteki pencere gibi uygulama bilgilerine erişmek için kullanılabilir.

```cpp
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın tek nesnesine yönelik bir işaretçi `CWinApp` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem NULL döndürürse, uygulama ana penceresinin henüz tam olarak başlatılmamış olabileceğini gösterebilir. Bir sorunu da gösterebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxgetappname"></a><a name="afxgetappname"></a> AfxGetAppName

Döndürülen dize, tanılama iletileri veya geçici dize adları için bir kök olarak kullanılabilir.

```cpp
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın adını içeren, null ile sonlandırılmış bir dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxgetinstancehandle"></a><a name="afxgetinstancehandle"></a> AfxGetInstanceHandle

Bu işlev, geçerli uygulamanın örnek tanıtıcısını almanızı sağlar.

```cpp
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın geçerli örneğine bir HıNSTANCE. MFC 'nin USRDLL sürümü ile bağlantılı bir DLL içinden çağrılırsa, DLL 'ye bir HıNSTANCE döndürülür.

### <a name="remarks"></a>Açıklamalar

`AfxGetInstanceHandle` her zaman yürütülebilir dosyanızın HıNSTANCE değerini döndürür (. EXE), MFC 'nin USRDLL sürümü ile bağlantılı bir DLL içinden çağrılmamışsa. Bu durumda, DLL 'ye bir HıNSTANCE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxgetmainwnd"></a><a name="afxgetmainwnd"></a> AfxGetMainWnd

Uygulamanız bir OLE sunucusu ise, uygulamanın etkin ana penceresine bir işaretçi almak için bu işlevi çağırın. Uygulama nesnesinin [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) üyesine doğrudan başvurmak yerine bu sonucu kullanın.

```cpp
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>Dönüş Değeri

Sunucu etkin bir kapsayıcı içinde yerinde etkin olan bir nesne varsa, yerinde etkin belgeyi içeren çerçeve pencere nesnesine bir işaretçi döndürür.

Bir kapsayıcı içinde yerinde etkin bir nesne yoksa veya uygulamanız OLE sunucusu değilse, bu işlev uygulama nesnenizin *m_pMainWnd* döndürür.

`AfxGetMainWnd`Uygulamanın birincil iş parçacığından çağrılırsa, yukarıdaki kurallara göre uygulamanın ana penceresini döndürür. İşlev uygulamadaki bir ikincil iş parçacığından çağrılırsa, işlev, çağrıyı yapan iş parçacığıyla ilişkili ana pencereyi döndürür.

### <a name="remarks"></a>Açıklamalar

Uygulamanız bir OLE sunucusu değilse, bu işlevi çağırmak, uygulama nesnenizin *m_pMainWnd* üyesine doğrudan başvuru ile eşdeğerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxgetperuserregistration"></a><a name="afxgetperuserregistration"></a> AfxGetPerUserRegistration

Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** (**HKCU**) düğümüne yeniden yönlendirip yönlendirmediğini öğrenmek için bu işlevi kullanın.

```cpp
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, kayıt defteri bilgilerinin HKCU düğümüne yönlendirildiğini gösterir. FALSE, uygulamanın kayıt defteri bilgilerini varsayılan düğüme yazdığını gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="remarks"></a>Açıklamalar

Kayıt defteri yeniden yönlendirmeyi etkinleştirirseniz Framework, **HKCR** 'den **HKEY_CURRENT_USER \software\classes**'a erişimi yeniden yönlendirir. Yalnızca MFC ve ATL çerçeveleri yeniden yönlendirmeden etkilenir.

Uygulamanın kayıt defteri erişimini yeniden yönlendirip yönlendirmediğini değiştirmek için [AfxSetPerUserRegistration](#afxsetperuserregistration)kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxstat_. h

## <a name="afxgetresourcehandle"></a><a name="afxgetresourcehandle"></a> AfxGetResourceHandle

Uygulamanın kaynaklarına doğrudan erişmek için bu işlev tarafından döndürülen HıNSTANCE tutamacını kullanın, örneğin, Windows işlevine yapılan çağrılar `FindResource` .

```cpp
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın varsayılan kaynaklarının yüklendiği bir HıNSTANCE tanıtıcısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxgetthread"></a><a name="afxgetthread"></a> AfxGetThread

Şu anda yürütülmekte olan iş parçacığını temsil eden [CWinThread](../../mfc/reference/cwinthread-class.md) nesnesine bir işaretçi almak için bu işlevi çağırın.

```cpp
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda yürütülmekte olan iş parçacığına yönelik işaretçi; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

İş parçacığı içinden çağrılmalıdır.

> [!NOTE]
> `AfxGetThread`4,2, 5,0 veya 6,0 Visual C++ sürümlerinden BIR MFC projesi oluşturuyorsanız, `AfxGetThread` iş parçacığı bulunmazsa [AfxGetApp](#afxgetapp) ' i çağırır. Derleyicinin daha yeni sürümlerinde, `AfxGetThread` hiçbir iş parçacığı bulunmazsa NULL değeri döndürür. Uygulama iş parçacığını istiyorsanız, öğesini çağırmanız gerekir `AfxGetApp` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxinitrichedit"></a><a name="afxinitrichedit"></a> AfxInitRichEdit

Uygulamanın zengin düzenleme denetimini (sürüm 1,0) başlatmak için bu işlevi çağırın.

```cpp
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev geriye dönük uyumluluk için sağlanır. Yeni uygulamalar [AfxInitRichEdit2](#afxinitrichedit2)kullanmalıdır.

`AfxInitRichEdit` zengin düzenleme denetiminin 1,0 sürümünü başlatmak için RICHED32.DLL yükler. Zengin düzenleme denetiminin 2,0 ve 3,0 sürümünü kullanmak için RICHED20.DLL yüklenmesi gerekir. Bu, [AfxInitRichEdit2](#afxinitrichedit2)için bir çağrı yapılarak yüklenir.

Mevcut Visual C++ uygulamalarında zengin düzenleme denetimlerini sürüm 2,0 ' ye güncelleştirmek için öğesini açın. RC dosyası metin olarak, her zengin düzenleme denetiminin sınıf adını "RICHEDIT" yerine "RichEdit20a" olarak değiştirin. Ardından çağrısını `AfxInitRichEdit` ile değiştirin `AfxInitRichEdit2` .

Bu işlev, kitaplık zaten işlem için başlatılmamışsa ortak denetimler kitaplığını da başlatır. Zengin düzenleme denetimini doğrudan MFC uygulamanızdan kullanırsanız, MFC 'nin zengin düzenleme denetimi çalışma zamanını düzgün bir şekilde başlattığını garantilemek için bu işlevi çağırın. `Create` [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md)veya [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)yöntemini çağırırsanız, genellikle bu işlevi çağırmanız gerekmez, ancak bazı durumlarda gerekli olabilir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxinitrichedit2"></a><a name="afxinitrichedit2"></a> Afxınitrichedit2

Uygulamanın zengin düzenleme denetimini (sürüm 2,0 ve üzeri) başlatmak için bu işlevi çağırın.

```cpp
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>Açıklamalar

RICHED20.DLL yüklemek ve zengin düzenleme denetiminin 2,0 sürümünü başlatmak için bu işlevi çağırın. `Create` [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md)veya [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)yöntemini çağırırsanız, genellikle bu işlevi çağırmanız gerekmez, ancak bazı durumlarda gerekli olabilir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxisextendedframeclass"></a><a name="afxisextendedframeclass"></a> Afxısextendedframeclass

Verilen pencerenin genişletilmiş bir çerçeve nesnesi olup olmadığını belirler.

### <a name="syntax"></a>Söz dizimi

```cpp
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>Parametreler

*pWnd*\
'ndaki Öğesinden türetilmiş bir nesne için bir işaretçi `CWnd` .

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

## <a name="afxismfctoolbar"></a><a name="afxismfctoolbar"></a> Afxısmfctoolbar

Verilen pencerenin bir araç çubuğu nesnesi olup olmadığını belirler.

### <a name="syntax"></a>Söz dizimi

```cpp
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*\
'ndaki Öğesinden türetilmiş bir nesne için bir işaretçi `CWnd` .

### <a name="return-value"></a>Dönüş Değeri

Belirtilen pencere bir araç çubuğu nesneliyse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `TRUE` , *pWnd* öğesinden türetilse döndürür `CMFCToolBar` . Bu yöntem, bir işlev veya yöntem parametresinin bir nesne olduğunu doğrulamanız gerektiğinde faydalıdır `CMFCToolBar` .

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** AFXPRIV. h

## <a name="afxkeyboardmanager"></a><a name="afxkeyboardmanager"></a> AfxKeyboardManager

Genel [klavye Yöneticisi](ckeyboardmanager-class.md)işaretçisi.

### <a name="syntax"></a>Syntax

```cpp
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxkeyboardmanager. h

## <a name="afxloadlibrary"></a><a name="afxloadlibrary"></a> AfxLoadLibrary

`AfxLoadLibrary`BIR dll modülünü eşlemek için kullanın.

```cpp
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>Parametreler

*lpszModuleName*\
Modülün adını içeren, null ile sonlandırılmış bir dizeye işaret eder (bir. DLL veya. EXE dosyası). Belirtilen ad modülün dosya adıdır.

Dize bir yol belirtiyorsa ancak dosya belirtilen dizinde yoksa, işlev başarısız olur.

Bir yol belirtilmemişse ve dosya adı uzantısı atlanırsa, varsayılan uzantı. DLL eklenir. Ancak, dosya adı dizesi, modül adının uzantıya sahip olmadığını göstermek için sondaki nokta karakterini (.) içerebilir. Hiçbir yol belirtilmediğinde, işlev [Masaüstü uygulamaları Için arama sırasını](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)kullanır.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri modülün bir tanıtıcıdır. Hatada, dönüş değeri NULL olur.

### <a name="remarks"></a>Açıklamalar

Bir DLL işlevinin adresini almak için [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) içinde kullanılabilecek bir tanıtıcı döndürür. `AfxLoadLibrary` , diğer yürütülebilir modülleri eşlemek için de kullanılabilir.

Her işlem, yüklenen her kitaplık modülü için bir başvuru sayısı tutar. Her çağrılışında bu başvuru sayısı artırılır `AfxLoadLibrary` ve her `AfxFreeLibrary` çağrıldığında azaltılır. Başvuru sayısı sıfıra ulaştığında, modül çağıran işlemin adres alanından eşlenmemiş ve tanıtıcı artık geçerli değildir.

`AfxLoadLibrary` `AfxFreeLibrary` `LoadLibrary` `FreeLibrary` Uygulamanız birden çok iş parçacığı kullanıyorsa ve dinamik olarak bir MFC uzantı dll yüklerse, ve ' ı (Win32 işlevleri yerine) kullandığınızdan emin olun. `AfxLoadLibrary`Ve `AfxFreeLibrary` Yöntem kullanarak, MFC uzantı dll 'si yüklendiğinde ve kaldırıldığında çalıştırılan başlatma ve kapatılma kodu genel MFC durumunu bozmaz.

`AfxLoadLibrary`Bir uygulamada kullanmak IÇIN MFC 'nın dll sürümüne dinamik olarak bağlantı oluşturmanız gerekir. Afxdll_. h için üst bilgi dosyası, `AfxLoadLibrary` yalnızca MFC BIR DLL olarak uygulamaya bağlanmışsa dahil edilir. MFC uzantı dll 'Leri kullanmak veya oluşturmak için MFC 'nin DLL sürümüne bağlamanız gerektiğinden, bu gereksinim tasarım tarafından yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdll_. h

## <a name="afxloadlibraryex"></a><a name="afxloadlibraryex"></a> AfxLoadLibraryEx

`AfxLoadLibraryEx`BIR dll modülünü eşlemek için kullanın.

```cpp
HINSTANCE AFXAPI AfxLoadLibraryEx(LPCTSTR lpFileName, HANDLE hFile, DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*lpFileName*\
Modülün adını içeren, null ile sonlandırılmış bir dizeye işaret eder (bir. DLL veya. EXE dosyası). Belirtilen ad modülün dosya adıdır.

Dize bir yol belirtiyorsa ancak dosya belirtilen dizinde yoksa, işlev başarısız olur.

Bir yol belirtilmemişse ve dosya adı uzantısı atlanırsa, varsayılan uzantı. DLL eklenir. Ancak, dosya adı dizesi, modül adının uzantıya sahip olmadığını göstermek için sondaki nokta karakterini (.) içerebilir. Hiçbir yol belirtilmediğinde, işlev [Masaüstü uygulamaları Için arama sırasını](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)kullanır.

*hFile*\
Bu parametre gelecekte kullanılmak üzere ayrılmıştır. NULL olmalıdır.

*dwFlags*\
Modül yüklenirken gerçekleştirilecek eylem. Hiçbir bayrak belirtilmemişse, bu işlevin davranışı `AfxLoadLibrary` işlevle aynıdır. Bu parametrenin olası değerleri [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) belgelerinde açıklanmıştır.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri modülün bir tanıtıcıdır. Hatada, dönüş değeri NULL olur.

### <a name="remarks"></a>Açıklamalar

`AfxLoadLibraryEx` DLL işlevinin adresini almak için [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) içinde kullanılabilecek bir tanıtıcı döndürür. `AfxLoadLibraryEx` , diğer yürütülebilir modülleri eşlemek için de kullanılabilir.

Her işlem, yüklenen her kitaplık modülü için bir başvuru sayısı tutar. Her çağrılışında bu başvuru sayısı artırılır `AfxLoadLibraryEx` ve her `AfxFreeLibrary` çağrıldığında azaltılır. Başvuru sayısı sıfıra ulaştığında, modül çağıran işlemin adres alanından eşlenmemiş ve tanıtıcı artık geçerli değildir.

`AfxLoadLibraryEx` `AfxFreeLibrary` `LoadLibraryEx` `FreeLibrary` Uygulamanız birden çok iş parçacığı kullanıyorsa ve dinamik olarak bir mfc uzantısı DLL yüklerse, ve ' ı (Win32 işlevleri yerine) kullandığınızdan emin olun. Kullanarak `AfxLoadLibraryEx` , `AfxFreeLibrary` MFC uzantı dll 'si yüklendiğinde ve bellekten kaldırıldığında çalıştırılan başlatma ve başlatma kodunun genel MFC durumunu bozmamasını sağlar.

`AfxLoadLibraryEx`Bir uygulamada kullanmak IÇIN MFC 'nın dll sürümüne dinamik olarak bağlantı oluşturmanız gerekir. Afxdll_. h için üst bilgi dosyası, `AfxLoadLibraryEx` yalnızca MFC BIR DLL olarak uygulamaya bağlanmışsa dahil edilir. MFC uzantı dll 'Leri kullanmak veya oluşturmak için MFC 'nin DLL sürümüne bağlamanız gerektiğinden, bu gereksinim tasarım tarafından yapılır.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdll_. h

## <a name="afxmenutearoffmanager"></a><a name="afxmenutearoffmanager"></a> AfxMenuTearOffManager

Küresel [yırma menü Yöneticisi](cmenutearoffmanager-class.md)işaretçisi.

### <a name="syntax"></a>Syntax

```cpp
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmenutearoffmanager. h

## <a name="afxmousemanager"></a><a name="afxmousemanager"></a> AfxMouseManager

Genel [Fare Yöneticisi](cmousemanager-class.md)işaretçisi.

### <a name="syntax"></a>Syntax

```cpp
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmousemanager. h

## <a name="afxregisterclass"></a><a name="afxregisterclass"></a> AfxRegisterClass

MFC kullanan bir DLL 'ye pencere sınıflarını kaydetmek için bu işlevi kullanın.

```cpp
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>Parametreler

*lpWndClass*\
Kaydedilecek pencere sınıfıyla ilgili bilgileri içeren bir [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısına yönelik işaretçi. Bu yapı hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="return-value"></a>Dönüş Değeri

Sınıf başarıyla kaydedilmişse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullanırsanız, DLL kaldırıldığında sınıf otomatik olarak kaydı kaldırılır.

DLL olmayan derlemelerde, `AfxRegisterClass` `RegisterClass` bir uygulamaya kayıtlı sınıfların otomatik olarak kaydı olduğundan, tanımlayıcı, Windows işleviyle eşlenen bir makro olarak tanımlanır. `AfxRegisterClass`Yerine kullanıyorsanız `RegisterClass` , kodunuz hem uygulamada hem de dll 'de değişiklik yapılmadan kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxregisterwndclass"></a><a name="afxregisterwndclass"></a> AfxRegisterWndClass

Kendi pencere sınıflarınızı kaydetmenizi sağlar.

```cpp
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>Parametreler

*nClassStyle*\
Pencere sınıfı için bit düzeyinde OR (**&#124;**) işleci kullanılarak oluşturulan Windows sınıf stilini veya stil bileşimini belirtir. Sınıf stillerinin listesi için Windows SDK [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısına bakın. NULL ise varsayılanlar aşağıdaki gibi ayarlanır:

- Fare stilini, kullanıcı fareyle çift tıkladığında pencere yordamına çift tıklama iletileri gönderen CS_DBLCLKS olarak ayarlar.

- Ok imleç stilini Windows standart IDC_ARROW olarak ayarlar.

- Arka plan fırçasını NULL olarak ayarlar, bu nedenle pencere arka planını silmez.

- Simgeyi standart, geri dönen bayrak Windows logosu simgesine ayarlar.

*hCursor*\
Pencere sınıfından oluşturulan her bir pencerede yüklenecek imleç kaynağına yönelik bir tanıtıcı belirtir. Varsayılan değer olan **0**' ı kullanırsanız, standart IDC_ARROW imlecini alırsınız.

*hbrBackground*\
Pencere sınıfından oluşturulan her bir pencerede yüklenecek fırça kaynağı için bir tanıtıcı belirtir. Varsayılan değer olan **0**' ı kullanırsanız, bir arka plan fırçanızı ve varsayılan olarak, [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd)işlerken pencere arka planını silmez.

*HICON*\
Pencere sınıfından oluşturulan her bir pencerede yüklenecek simge kaynağına yönelik bir tanıtıcı belirtir. Varsayılan değer olan **0**' ı kullanırsanız, standart, geri dönen bayrak Windows logosu simgesini alırsınız.

### <a name="return-value"></a>Dönüş Değeri

Sınıf adını içeren, null ile sonlandırılmış bir dize. Bu sınıf adını, `Create` `CWnd` bir pencere oluşturmak için veya diğer **CWnd-** türetilmiş sınıflarda üye işlevine geçirebilirsiniz. Ad, Microsoft Foundation Class Kitaplığı tarafından oluşturulur.

> [!NOTE]
> Dönüş değeri, statik arabelleğin bir işaretçisidir. Bu dizeyi kaydetmek için bir `CString` değişkene atayın.

### <a name="remarks"></a>Açıklamalar

Microsoft Foundation Class Kitaplığı, sizin için birkaç standart pencere sınıfını otomatik olarak kaydeder. Kendi pencere sınıflarınızı kaydetmek istiyorsanız bu işlevi çağırın.

Bir sınıf için kaydedilen ad `AfxRegisterWndClass` yalnızca parametrelere bağlıdır. `AfxRegisterWndClass`Aynı parametrelerle birden çok kez çağrı yaparsanız, ilk çağrıda yalnızca bir sınıf kaydedilir. Aynı parametrelerle daha sonra yapılan çağrılar `AfxRegisterWndClass` , zaten kayıtlı ClassName döndürür.

`AfxRegisterWndClass`Aynı parametrelerle birden çok CWnd ile türetilmiş sınıf için çağrı yaparsanız, her sınıf için ayrı bir pencere sınıfı almak yerine, her bir sınıf aynı pencere sınıfını paylaşır. CS_CLASSDC sınıfı stili kullanılırsa bu paylaşım sorunlara yol açabilir. Birden çok CS_CLASSDC pencere sınıfı yerine yalnızca bir CS_CLASSDC pencere sınıfıyla bitolursunuz. Bu sınıfı kullanan tüm C++ pencereleri aynı DC 'yi paylaşır. Bu sorundan kaçınmak için, sınıfı kaydetmek üzere [AfxRegisterClass](#afxregisterclass) ' ı çağırın.

Pencere sınıfı kaydı ve işlevi hakkında daha fazla bilgi için bkz. Teknik [NotTN001: pencere sınıfı kaydı](../../mfc/tn001-window-class-registration.md) `AfxRegisterWndClass` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxsetperuserregistration"></a><a name="afxsetperuserregistration"></a> AfxSetPerUserRegistration

Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** (**HKCU**) düğümüne yeniden yönlendirip yönlendirmeyeceğini ayarlar.

```cpp
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEnable*\
'ndaki TRUE, kayıt defteri bilgilerinin HKCU düğümüne yönlendirildiğini gösterir. FALSE, uygulamanın kayıt defteri bilgilerini varsayılan düğüme yazdığını gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="remarks"></a>Açıklamalar

Windows Vista 'Dan önce, kayıt defterine erişen uygulamalar **HKEY_CLASSES_ROOT** düğümünü sık kullanılır. Bununla birlikte, Windows Vista veya sonraki işletim sistemlerinde, bir uygulamayı Yükseltilmiş modda çalıştırıp HKCR 'ye yazmanız gerekir.

Bu yöntem, uygulamanızın, yükseltilmiş modda çalıştırmadan kayıt defterine okuyup yazmasını sağlar. Bu, kayıt defteri erişimini HKCR 'den HKCU 'a yönlendirerek işe yarar. Daha fazla bilgi için bkz. [bağlayıcı özellik sayfaları](../../build/reference/linker-property-pages.md).

Kayıt defteri yeniden yönlendirmeyi etkinleştirirseniz Framework, HKCR 'den **HKEY_CURRENT_USER \Software\Classes**'a erişimi yeniden yönlendirir. Yalnızca MFC ve ATL çerçeveleri yeniden yönlendirmeden etkilenir.

Varsayılan uygulama, HKCR altında kayıt defterine erişir.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxstat_. h

## <a name="afxsetresourcehandle"></a><a name="afxsetresourcehandle"></a> AfxSetResourceHandle

Uygulamanın varsayılan kaynaklarının nereye yükleneceğini belirleyen HıNSTANCE tanıtıcısını ayarlamak için bu işlevi kullanın.

```cpp
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>Parametreler

*Hınstresource*\
Örneği veya modülü bir olarak işleme. Uygulama kaynaklarının yüklendiği EXE veya DLL dosyası.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxshellmanager"></a><a name="afxshellmanager"></a> AfxShellManager

Genel [Kabuk Yöneticisi](cshellmanager-class.md)işaretçisi.

### <a name="syntax"></a>Syntax

```cpp
CShellManager* afxShellManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxshellmanager. h

## <a name="afxsocketinit"></a><a name="afxsocketinit"></a> AfxSocketInit

`CWinApp::InitInstance`Windows yuvaları başlatmak için bu işlevi geçersiz kılmada çağırın.

```cpp
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>Parametreler

*Lpwsaverileri*\
Bir [Wsaveri](/windows/win32/api/winsock2/ns-winsock2-wsadata) yapısına yönelik işaretçi. *Lpwsaverileri* null değerine eşit değilse, `WSADATA` yapının adresi öğesine çağrısıyla doldurulur `WSAStartup` . Bu işlev, `WSACleanup` uygulama sonlanmadan önce sizin için de çağırılmasını sağlar.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Statik olarak bağlı bir MFC uygulamasında ikincil iş parçacıklarında MFC Yuvaları kullanırken, `AfxSocketInit` yuva kitaplıklarını başlatmak için yuva kullanan her bir iş parçacığında çağrı yapmanız gerekir. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığında çağırılır.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxsock. h

## <a name="afxusertoolsmanager"></a><a name="afxusertoolsmanager"></a> Afxuseraraçları Yöneticisi

Genel [Kullanıcı araçları Yöneticisi](cusertoolsmanager-class.md)işaretçisi.

### <a name="syntax"></a>Syntax

```cpp
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxuseraraçları Yöneticisi. h

## <a name="afxwininit"></a><a name="afxwininit"></a> AfxWinInit

Bu işlev, MFC 'yi `WinMain` başlatmak IÇIN GUI tabanlı bir uygulamanın [CWinApp](../../mfc/reference/cwinapp-class.md) başlatması kapsamında MFC tarafından sağlanan işlev tarafından çağrılır.

```cpp
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*\
Çalışmakta olan modülün tanıtıcısı.

*hPrevInstance*\
Uygulamanın önceki bir örneğine yönelik bir tanıtıcı. Win32 tabanlı bir uygulama için, bu parametre her zaman **null**olur.

*lpCmdLine*\
Uygulamanın komut satırını belirten, null ile sonlandırılmış bir dizeye işaret eder.

*nCmdShow*\
GUI uygulamasının ana penceresinin nasıl gösterileceğini belirtir.

### <a name="remarks"></a>Açıklamalar

MFC tarafından sağlanan işlevi kullanmayan bir konsol uygulaması için `WinMain` `AfxWinInit` doğrudan MFC 'yi başlatmak için çağırmanız gerekir.

`AfxWinInit`Kendi kendinize çağrı yaparsanız bir sınıfın örneğini bildirmeniz gerekir `CWinApp` . Bir konsol uygulaması için, ' dan kendi sınıfınızı türetmekten `CWinApp` ve bunun yerine doğrudan bir örneğini kullanmanıza tercih edebilirsiniz `CWinApp` . **Main**uygulamanızda uygulamanız için tüm işlevleri bırakmaya karar verirseniz bu teknik uygundur.

> [!NOTE]
> Bir derleme için bir etkinleştirme bağlamı oluşturduğunda, MFC kullanıcı modülü tarafından sağlanmış bir bildirim kaynağı kullanır. Etkinleştirme bağlamı ' de oluşturulur `AfxWinInit` . Daha fazla bilgi için bkz. [MFC modül durumunda etkinleştirme bağlamları Için destek](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)\
[CWinApp sınıfı](cwinapp-class.md)\
[CContextMenuManager sınıfı](ccontextmenumanager-class.md)\
[CWnd sınıfı](cwnd-class.md)\
[CFrameWndEx sınıfı](cframewndex-class.md)\
[CMFCToolBar sınıfı](cmfctoolbar-class.md)\
[CKeyboardManager sınıfı](ckeyboardmanager-class.md)\
[CMenuTearOffManager sınıfı](cmenutearoffmanager-class.md)\
[CMouseManager sınıfı](cmousemanager-class.md)\
[CShellManager sınıfı](cshellmanager-class.md)\
[Cuser, yönetici sınıfı](cusertoolsmanager-class.md)
