---
title: Başvuru Bilgileri ve Yönetimi
description: Microsoft Foundation Class kitaplığı (MFC) uygulama bilgileri ve yönetim işlevlerine başvuru.
ms.date: 01/27/2020
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: fc0b4b09f6c48da68bebe4a2825f49bcf6ab7e23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372495"
---
# <a name="application-information-and-management"></a>Başvuru Bilgileri ve Yönetimi

Bir uygulama yazarken, tek bir [CWinApp](../../mfc/reference/cwinapp-class.md)türetilmiş nesne oluşturursunuz. Bazen, bu nesne hakkında türetilmiş nesnenin `CWinApp`dışından bilgi almak isteyebilirsiniz. Veya diğer genel "yönetici" nesnelere erişmeniz gerekebilir.

Microsoft Hazırlık Sınıf Kitaplığı, aşağıdaki görevleri gerçekleştirmenize yardımcı olmak için aşağıdaki genel işlevleri sağlar:

## <a name="application-information-and-management-functions"></a>Uygulama Bilgileri ve Yönetim Fonksiyonları

|||
|-|-|
|[AfxBeginThread](#afxbeginthread)|Yeni bir iş parçacığı oluşturur.|
|[AfxContextMenuManager](#afxcontextmenumanager)|Genel bağlam [menü yöneticisiiçin](ccontextmenumanager-class.md)işaretçi.|
|[AfxEndThread](#afxendthread)|Geçerli iş parçacığı sonlandırır.|
|[AfxFindResourceHandle](#afxfindresourcehandle)|Kaynak zincirini yürütür ve kaynak kimliğine ve kaynak türüne göre belirli bir kaynağı bulur. |
|[Afxfreelibrary](#afxfreelibrary)|Yüklenen dinamik bağlantı kitaplığı (DLL) modülünün başvuru sayısını eriter. Başvuru sayısı sıfıra ulaştığında, modül eşlenen değil.|
|[Afxgetapp](#afxgetapp)|Bir işaretçiyi uygulamanın `CWinApp` tek nesnesine döndürür.|
|[AfxGetAppName](#afxgetappname)|Uygulamanın adını içeren bir dize döndürür.|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|Uygulamanın bu örneğini temsil eden bir HINSTANCE döndürür.|
|[AfxGetMainWnd](#afxgetmainwnd)|Bir işaretçiyi OLE olmayan bir uygulamanın geçerli "ana" penceresine veya sunucu uygulamasının yerinde çerçeve penceresine döndürür.|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** **(HKCU)** düğümüne yönlendirip yönlendirmediğini belirlemek için bu işlevi kullanın.|
|[AfxGetResourceHandle](#afxgetresourcehandle)|Bir HINSTANCE'ı uygulamanın varsayılan kaynaklarının kaynağına döndürür. Uygulamanın kaynaklarına doğrudan erişmek için kullanın.|
|[AfxGetThread](#afxgetthread)|Geçerli [CWinThread](../../mfc/reference/cwinthread-class.md) nesnesine bir işaretçi alır.|
|[AfxInitRichEdit](#afxinitrichedit)|Sürüm 1.0'ı uygulama için zengin bir şekilde edit denetimi ne kadar önemli hale sağlar.|
|[AfxInitRichEdit2](#afxinitrichedit2)|Sürüm 2.0'ı başlatır ve daha sonra uygulama için zengin bir edit denetimi sağlar.|
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|Verilen pencerenin genişletilmiş bir çerçeve nesnesi olup olmadığını belirler.|
|[AfxIsMFCToolBar](#afxismfctoolbar)|Verilen pencerenin araç çubuğu nesnesi olup olmadığını belirler.|
|[AfxKeyboardManager](#afxkeyboardmanager)|Genel klavye [yöneticisiiçin](ckeyboardmanager-class.md)işaretçi.|
|[Afxloadlibrary](#afxloadlibrary)|Bir DLL modülünün eşlerini eşler ve Bir DLL işlevinin adresini elde etmek için kullanılabilecek bir tutamaç döndürür.|
|[AfxLoadLibraryEx](#afxloadlibraryex)|Belirtilen seçenekleri kullanarak bir DLL modüleşler ve bir DLL işlevinin adresini elde etmek için kullanılabilecek bir tutamaç döndürür.|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|Genel [yırtılma menü yöneticisiiçin](cmenutearoffmanager-class.md)işaretçi.|
|[AfxMouseManager](#afxmousemanager)|Genel fare [yöneticisiiçin](cmousemanager-class.md)işaretçi.|
|[AfxRegisterClass](#afxregisterclass)|MFC kullanan bir DLL'de bir pencere sınıfını kaydeder.|
|[Afxregisterwndclass](#afxregisterwndclass)|MFC tarafından otomatik olarak kaydedilmiş olanları tamamlamak için bir Windows penceresi sınıfı kaydeder.|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** **(HKCU)** düğümüne yönlendirip yönlendirmediğini ayarlar.|
|[AfxSetResourceHandle](#afxsetresourcehandle)|Uygulamanın varsayılan kaynaklarının yüklendiği HINSTANCE tanıtıcısını ayarlar.|
|[AfxShellManager](#afxshellmanager)|Genel kabuk [yöneticisi](cshellmanager-class.md)için işaretçi . |
|[AfxSocketInit](#afxsocketinit)|Windows Soketlerini başlatmayı denetlemek için geçersiz `CWinApp::InitInstance` kılma olarak adlandırılır.|
|[AfxUserToolsManager](#afxusertoolsmanager)|Genel kullanıcı [araçları yöneticisiiçin](cusertoolsmanager-class.md)işaretçi.|
|[AfxWinInit](#afxwininit)|MFC tabanlı bir uygulamanın `WinMain` [CWinApp](../../mfc/reference/cwinapp-class.md) başlatılmasının bir parçası olarak, MFC tarafından sağlanan işlev tarafından çağrılan, MFC başlatılması. MFC kullanan konsol uygulamaları için doğrudan çağrılmalıdır.|

## <a name="afxbeginthread"></a><a name="afxbeginthread"></a>AfxBeginThread

Yeni bir iş parçacığı oluşturmak için bu işlevi arayın.

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
Alt iş parçacığı için kontrol işlevine işaret eder. İşaretçi NULL olamaz. Bu işlev aşağıdaki gibi bildirilmelidir:

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThreadClass*\
[CWinThread'ten](../../mfc/reference/cwinthread-class.md)türetilen bir nesnenin RUNTIME_CLASS.

*pParam*\
Parametre kontrol işlevine geçmek için.

*nÖncelikli*\
İş parçacığı için ayarlanan öncelik. Kullanılabilir önceliklerin tam listesi ve açıklaması için Windows SDK'daki [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) bölümüne bakın.

*nStackSize*\
Yeni iş parçacığı için yığının baytboyutu belirtir. 0 ise, yığın boyutu oluşturma iş parçacığı olarak aynı boyut yığını varsayılan.

*dwCreateFlags*\
İş parçacığının oluşturulmasını denetleyen ek bir bayrak belirtir. Bu bayrak iki değerden birini içerebilir:

- CREATE_SUSPENDED İş parçacığıbir askıya alma sayısı ile başlatın. Iş parçacığı çalışmaya başlamadan `CWinThread` [önce, nesnenin m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) veya türemiş sınıfınızın herhangi bir üyesi gibi herhangi bir üye verisini başlatmayı istiyorsanız CREATE_SUSPENDED kullanın. Başlatma işleminiz tamamlandıktan sonra, iş parçacığının çalışmasını başlatmak için [CWinThread::ResumeThread'i](../../mfc/reference/cwinthread-class.md#resumethread) kullanın. İş parçacığı çağrılana `CWinThread::ResumeThread` kadar yürütülmez.

- **0** Oluşturmaişleminden hemen sonra iş parçacığı başlatın.

*lpSecurityAttrs*\
İş parçacığı için güvenlik özniteliklerini belirten [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bir yapıya işaret eder. NULL ise, oluşturma iş parçacığı ile aynı güvenlik öznitelikleri kullanılır. Bu yapı hakkında daha fazla bilgi için Windows SDK'ya bakın.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan iş parçacığı nesnesine işaretçi veya bir hata oluşursa NULL.

### <a name="remarks"></a>Açıklamalar

İlk form `AfxBeginThread` bir alt iş parçacığı oluşturur. İkinci form, kullanıcı arabirimi iş parçacığı veya alt iş parçacığı olarak hizmet verebilir bir iş parçacığı oluşturur.

`AfxBeginThread`yeni `CWinThread` bir nesne oluşturur, iş parçacığı yürütmeye başlamak için [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) işlevini çağırır ve iş parçacığına bir işaretçi döndürür. Oluşturmanın herhangi bir bölümü başarısız olursa, tüm nesnelerin düzgün bir şekilde ayrılmasını sağlamak için yordam boyunca denetimler yapılır. İş parçacığı sona erdirmek için, iş parçacığı içinden [AfxEndThread'i](#afxendthread) arayın veya alt iş parçacığının kontrol işlevinden dönün.

Çoklu iş parçacığı uygulama tarafından etkinleştirilmelidir; aksi takdirde, bu işlev başarısız olur. Çoklu iş parçacığı etkinleştirme hakkında daha fazla bilgi için bkz: [/MD, /MT, /LD (Çalışma zamanı kitaplığını kullanın)](../../build/reference/md-mt-ld-use-run-time-library.md).

Hakkında daha `AfxBeginThread`fazla bilgi için, makaleler [Multithreading bakınız: İşçi İş parçacığı oluşturma](../../parallel/multithreading-creating-worker-threads.md) ve [Multithreading: Kullanıcı-Arayüz Konuları oluşturma](../../parallel/multithreading-creating-user-interface-threads.md).

### <a name="example"></a>Örnek

CSocket örneğine [bakın:Ekle.](../../mfc/reference/csocket-class.md#attach)

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxcontextmenumanager"></a><a name="afxcontextmenumanager"></a>AfxContextMenuManager

Genel bağlam [menü yöneticisiiçin](ccontextmenumanager-class.md)işaretçi.

### <a name="syntax"></a>Sözdizimi

```cpp
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcontextmenumanager.h

## <a name="afxendthread"></a><a name="afxendthread"></a>AfxEndThread

Şu anda çalıştırılamakta olan iş parçacığı sonlandırmak için bu işlevi arayın.

```cpp
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>Parametreler

*nExitCode*\
İş parçacığının çıkış kodunu belirtir.

*bSilin*\
İş parçacığı nesnesini bellekten siler.

### <a name="remarks"></a>Açıklamalar

Sonlandırılmak için iş parçacığı nın içinden çağrılmalıdır.

Hakkında daha `AfxEndThread`fazla bilgi için, makale [Multithreading bakın: Sonlandırma Konuları](../../parallel/multithreading-terminating-threads.md).

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxfindresourcehandle"></a><a name="afxfindresourcehandle"></a>AfxFindResourceHandle

Kaynak `AfxFindResourceHandle` zincirini yürümek ve kaynak kimliğine ve kaynak türüne göre belirli bir kaynağı bulmak için kullanın.

### <a name="syntax"></a>Sözdizimi

```cpp
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>Parametreler

*Lpszname*\
Kaynak kimliğini içeren bir dize için işaretçi.
*lpszType*\
Kaynak türüne işaretçi. Kaynak türlerinin listesi için Windows SDK'daki [Kaynak Bul'a](/windows/win32/api/winbase/nf-winbase-findresourcea) bakın.

### <a name="return-value"></a>Dönüş Değeri

Kaynağı içeren modüle bir tutamaç.

### <a name="remarks"></a>Açıklamalar

`AfxFindResourceHandle`belirli kaynağı bulur ve kaynağı içeren modüle bir tutamaç döndürür. Kaynak yüklenen herhangi bir MFC uzantısı DLL olabilir. `AfxFindResourceHandle`hangisinin kaynağına sahip olduğunu söyler.

Modüller bu sırada aranır:

1. Ana modül, bir MFC uzantısı DLL ise.

1. Sistem dışı modüller.

1. Dile özel modüller.

1. Ana modül, eğer bir sistemse DLL.

1. Sistem modülleri.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="afxfreelibrary"></a><a name="afxfreelibrary"></a>Afxfreelibrary

Her `AfxFreeLibrary` `AfxLoadLibrary` ikisi de ve her yüklenen kitaplık modülü için bir başvuru sayısı koruyun.

```cpp
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>Parametreler

*hInstLib*\
Yüklenen kitaplık modülünün tutamacı. [AfxLoadLibrary](#afxloadlibrary) bu tutamacı döndürür.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

`AfxFreeLibrary`yüklenen dinamik bağlantı kitaplığı (DLL) modülünün başvuru sayısını erteler. Başvuru sayısı sıfıra ulaştığında, modül arama işleminin adres alanından eşlenir ve tutamaç artık geçerli değildir. Bu başvuru sayısı her seferinde `AfxLoadLibrary` artışla çağrılır.

Bir kitaplık modülünün eşizinden çıkarmadan önce, sistem DLL'nin onu kullanarak işlemlerden ayrılmasını sağlar. Bunu yapmak, DLL'ye geçerli işlem için ayrılan kaynakları temizleme fırsatı verir. Giriş noktası işlevi döndükten sonra, kitaplık modülü geçerli işlemin adres alanından kaldırılır.

Bir `AfxLoadLibrary` DLL modüleşlemek için kullanın.

Uygulamanız birden `AfxFreeLibrary` `AfxLoadLibrary` çok iş parçacığı kullanıyorsa ve (Win32 işlevleri `FreeLibrary` yerine) `LoadLibrary`kullandığınızdan emin olun. MFC uzantısı DLL yüklendiğinde ve boşaltıldığında çalıştıran başlatma ve kapatma kodunun kullanılması `AfxLoadLibrary` ve `AfxFreeLibrary` genel MFC durumunun bozulmamasını sağlar.

### <a name="example"></a>Örnek

[AfxLoadLibrary](#afxloadlibrary)örneğine bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdll_.h

## <a name="afxgetapp"></a><a name="afxgetapp"></a>Afxgetapp

Bu işlev tarafından döndürülen işaretçi, ana ileti gönderme kodu veya en üstteki pencere gibi uygulama bilgilerine erişmek için kullanılabilir.

```cpp
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama için tek `CWinApp` bir nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem NULL döndürürse, uygulama ana penceresinin henüz tam olarak başlatılmasıolmadığını gösterebilir. Ayrıca bir sorun gösterebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxgetappname"></a><a name="afxgetappname"></a>AfxGetAppName

Döndürülen dize tanılama iletileri için veya geçici dize adları için bir kök olarak kullanılabilir.

```cpp
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın adını içeren null-sonlandırılan dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxgetinstancehandle"></a><a name="afxgetinstancehandle"></a>AfxGetInstanceHandle

Bu işlev, geçerli uygulamanın örnek tutamacını almanızı sağlar.

```cpp
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın geçerli örneğine bir HINSTANCE. MFC'nin USRDLL sürümüyle bağlantılı bir DLL içinden çağrılırsa, DLL'ye bir HINSTANCE döndürülür.

### <a name="remarks"></a>Açıklamalar

`AfxGetInstanceHandle`her zaman çalıştırılabilir dosyanızın HINSTANCE döndürür (. EXE) MFC USRDLL sürümü ile bağlantılı bir DLL içinden çağrılmadığı sürece. Bu durumda, DLL bir HINSTANCE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxgetmainwnd"></a><a name="afxgetmainwnd"></a>AfxGetMainWnd

Uygulamanız bir OLE sunucusuysa, uygulamanın etkin ana penceresine bir işaretçi almak için bu işlevi arayın. Uygulama nesnesinin [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) üyesine doğrudan atıfta bulunarak bu sonucu kullanın.

```cpp
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>Dönüş Değeri

Sunucuda etkin bir kapsayıcının içinde etkin bir nesne varsa, yerinde etkin belgeyi içeren çerçeve penceresi nesnesine bir işaretçi döndürür.

Bir kapsayıcının içinde etkin olan bir nesne yoksa veya uygulamanız Bir OLE sunucusu değilse, bu işlev uygulama nesnenizin *m_pMainWnd* döndürür.

Uygulamanın birincil iş parçacığından `AfxGetMainWnd` çağrılırsa, yukarıdaki kurallara göre uygulamanın ana penceresini döndürür. İşlev uygulamada ikincil bir iş parçacığı ndan çağrılırsa, işlev aramayı yapan iş parçacığıyla ilişkili ana pencereyi döndürür.

### <a name="remarks"></a>Açıklamalar

Uygulamanız bir OLE sunucusu değilse, bu işlevi aramak doğrudan uygulama nesnenizin *m_pMainWnd* üyesine atıfta bulunmaya eşdeğerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxgetperuserregistration"></a><a name="afxgetperuserregistration"></a>AfxGetPerUserRegistration

Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** **(HKCU)** düğümüne yönlendirip yönlendirmediğini belirlemek için bu işlevi kullanın.

```cpp
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, kayıt defteri bilgilerinin HKCU düğümüne yönlendirilmediğini gösterir. FALSE, uygulamanın kayıt defteri bilgilerini varsayılan düğüme yazdığını gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** **(HKCR)** idi.

### <a name="remarks"></a>Açıklamalar

Kayıt defteri yeniden yönlendirmesini etkinleştiriseniz, çerçeve **HKCR'dan** **HKEY_CURRENT_USER\Software\Classes'a**erişimi yeniden yönlendirir. Yeniden yönlendirmeden yalnızca MFC ve ATL çerçeveleri etkilenir.

Uygulamanın kayıt defteri erişimini yönlendirip yönlendirmediğini değiştirmek için [AfxSetPerUserRegistration 'ı](#afxsetperuserregistration)kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxstat_.h

## <a name="afxgetresourcehandle"></a><a name="afxgetresourcehandle"></a>AfxGetResourceHandle

Uygulamanın kaynaklarına doğrudan erişmek için bu işlev tarafından döndürülen HINSTANCE tutamacını `FindResource`kullanın, örneğin Windows işlevine yapılan çağrılarda.

```cpp
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın varsayılan kaynaklarının yüklendiği bir HINSTANCE işlemi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxgetthread"></a><a name="afxgetthread"></a>AfxGetThread

Şu anda çalıştırılamakta olan iş parçacığı temsil eden [CWinThread](../../mfc/reference/cwinthread-class.md) nesnesine bir işaretçi almak için bu işlevi arayın.

```cpp
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda çalıştırılamakta olan iş parçacığıiçin işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Iş parçacığı içinden çağrılmalıdır.

> [!NOTE]
> Visual C++ 4.2, `AfxGetThread` 5.0 veya 6.0 sürümlerinden arama lar yapıyorsunuz, `AfxGetThread` iş parçacığı bulunamazsa [AfxGetApp'ı](#afxgetapp) arar. Derleyicinin daha yeni sürümlerinde, `AfxGetThread` iş parçacığı bulunamadıysa NULL döndürür. Uygulama iş parçacığı istiyorsanız, `AfxGetApp`aramanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxinitrichedit"></a><a name="afxinitrichedit"></a>AfxInitRichEdit

Uygulama için zengin edit denetimini (sürüm 1.0) başlatmak için bu işlevi arayın.

```cpp
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev geriye dönük uyumluluk için sağlanır. Yeni uygulamalar [AfxInitRichEdit2](#afxinitrichedit2)kullanmalısınız.

`AfxInitRichEdit`yükler RICHED32. DLL, zengin edit denetiminin sürüm 1.0'ını başlatmaya. Zengin edit denetiminin 2.0 ve 3.0 sürümünü kullanmak için, RICHED20. DLL'nin yüklenmesi gerekiyor. [AfxInitRichEdit2'yi](#afxinitrichedit2)arayarak yüklenir.

Varolan Visual C++ uygulamalarındaki zengin edit denetimlerini sürüm 2.0'a güncelleştirmek için . RC dosyası metin olarak, her zengin edit denetiminin sınıf adını "RICHEDIT" den "RichEdit20a" olarak değiştirin. Daha sonra aramayı `AfxInitRichEdit` `AfxInitRichEdit2`' ile değiştirin.

Bu işlev, kitaplık işlem için zaten başharfe edilmemişse, ortak denetimkitaplığını da başlatılmasını sağlar. Zengin edit denetimini doğrudan MFC uygulamanızdan kullanıyorsanız, MFC'nin zengin edit denetimi çalışma süresini düzgün bir şekilde başlattığınızdan emin olmak için bu işlevi arayın. `Create` [CRichEditCtrl,](../../mfc/reference/cricheditctrl-class.md) [CRichEditView](../../mfc/reference/cricheditview-class.md)veya [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)yöntemini çağırırsanız, genellikle bu işlevi aramanız gerekmez, ancak bazı durumlarda gerekli olabilir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxinitrichedit2"></a><a name="afxinitrichedit2"></a>AfxInitRichEdit2

Uygulama için zengin edit denetimini (sürüm 2.0 ve sonrası) başlatması için bu işlevi arayın.

```cpp
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>Açıklamalar

RICHED20'yi yüklemek için bu işlevi arayın. DLL ve zengin edit denetimi sürüm 2.0 başlattı. `Create` [CRichEditCtrl,](../../mfc/reference/cricheditctrl-class.md) [CRichEditView](../../mfc/reference/cricheditview-class.md)veya [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)yöntemini çağırırsanız, genellikle bu işlevi aramanız gerekmez, ancak bazı durumlarda gerekli olabilir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxisextendedframeclass"></a><a name="afxisextendedframeclass"></a>AfxIsExtendedFrameClass

Verilen pencerenin genişletilmiş bir çerçeve nesnesi olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>Parametreler

*Pwnd*\
[içinde] `CWnd`Türetilen bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sağlanan pencere genişletilmiş bir çerçeve nesnesiyse TRUE; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

*PWnd* aşağıdaki sınıflardan birinden türetilmişse, bu yöntem TRUE döndürür:

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

Bu yöntem, bir işlev veya yöntem parametresi genişletilmiş bir çerçeve penceresi olduğunu doğrulamak zorunda yararlıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpriv.h

## <a name="afxismfctoolbar"></a><a name="afxismfctoolbar"></a>AfxIsMFCToolBar

Verilen pencerenin araç çubuğu nesnesi olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*\
[içinde] `CWnd`Türetilen bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sağlanan pencere bir araç çubuğu nesnesiyse TRUE; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

`TRUE` *PWnd'den* `CMFCToolBar`türetilmişse bu yöntem döndürür. Bu yöntem, bir işlev veya yöntem parametresi bir `CMFCToolBar` nesne olduğunu doğrulamak zorunda yararlıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpriv.h

## <a name="afxkeyboardmanager"></a><a name="afxkeyboardmanager"></a>AfxKeyboardManager

Genel klavye [yöneticisiiçin](ckeyboardmanager-class.md)işaretçi.

### <a name="syntax"></a>Sözdizimi

```cpp
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxkeyboardmanager.h

## <a name="afxloadlibrary"></a><a name="afxloadlibrary"></a>Afxloadlibrary

Bir `AfxLoadLibrary` DLL modüleşlemek için kullanın.

```cpp
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>Parametreler

*lpszModuleName*\
Modülün adını içeren null-terminatedli dize işaret (ya . DLL veya . EXE dosyası). Belirtilen ad modülün dosya adıdır.

Dize bir yol belirtir, ancak dosya belirtilen dizinde yoksa, işlev başarısız olur.

Bir yol belirtilmemişse ve dosya adı uzantısı atlanırsa, varsayılan uzantı . DLL eklenir. Ancak, dosya adı dizesi, modül adının uzantısı olmadığını belirtmek için bir son nokta karakteri (.) içerebilir. Yol belirtilmediğinde, işlev [Masaüstü Uygulamaları için Arama Sırası'nı](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)kullanır.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, geri dönüş değeri modülün bir tutamacıdır. Hatada, iade değeri NULL'dur.

### <a name="remarks"></a>Açıklamalar

Bir DLL işlevinin adresini almak için [GetProcAddress'te](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) kullanılabilecek bir tutamacı döndürür. `AfxLoadLibrary`diğer çalıştırılabilir modüllerin haritasını çıkarmak için de kullanılabilir.

Her işlem, yüklenen her kitaplık modülü için bir başvuru sayısı tutar. Bu başvuru sayısı her çağrıldı `AfxLoadLibrary` ve her zaman `AfxFreeLibrary` çağrılır kararnameye artımlı. Başvuru sayısı sıfıra ulaştığında, modül arama işleminin adres alanından eşlenir ve tutamaç artık geçerli değildir.

Uygulamanız birden `AfxLoadLibrary` `AfxFreeLibrary` çok iş parçacığı kullanıyorsa ve dinamik olarak bir MFC uzantısı DLL yüklerse ve (Win32 işlevleri `LoadLibrary` yerine) `FreeLibrary`kullandığınızdan emin olun. MFC uzantısı DLL yüklendiğinde ve boşaltıldığında çalıştıran başlatma ve kapatma kodunun genel MFC durumunu bozmadığını kullanmak `AfxLoadLibrary` ve `AfxFreeLibrary` sigortalamak.

Bir `AfxLoadLibrary` uygulamada kullanmak, MFC'nin DLL sürümüne dinamik olarak bağlanmanızı gerektirir. `AfxLoadLibrary`MFC uygulamaya DLL olarak bağlıysa, Afxdll_.h için üstbilgi dosyası yalnızca dahil edilir. MFC uzantılı DL'leri kullanmak veya oluşturmak için MFC'nin DLL sürümüne bağlanmanız gerekir, çünkü bu gereksinim tasarım gereğidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdll_.h

## <a name="afxloadlibraryex"></a><a name="afxloadlibraryex"></a>AfxLoadLibraryEx

Bir `AfxLoadLibraryEx` DLL modüleşlemek için kullanın.

```cpp
HINSTANCE AFXAPI AfxLoadLibraryEx(LPCTSTR lpFileName, HANDLE hFile, DWORD dwFlags);
```

### <a name="parameters"></a>Parametreler

*lpFileName*\
Modülün adını içeren null-terminatedli dize işaret (ya . DLL veya . EXE dosyası). Belirtilen ad modülün dosya adıdır.

Dize bir yol belirtir, ancak dosya belirtilen dizinde yoksa, işlev başarısız olur.

Bir yol belirtilmemişse ve dosya adı uzantısı atlanırsa, varsayılan uzantı . DLL eklenir. Ancak, dosya adı dizesi, modül adının uzantısı olmadığını belirtmek için bir son nokta karakteri (.) içerebilir. Yol belirtilmediğinde, işlev [Masaüstü Uygulamaları için Arama Sırası'nı](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)kullanır.

*hFile*\
Bu parametre ileride kullanılmak üzere ayrılmıştır. NULL olmalı.

*Dwflags*\
Modülü yüklerken yapılması gereken eylem. Bayrak belirtilmemişse, bu işlevin davranışı `AfxLoadLibrary` işlek ile aynıdır. Bu parametrenin olası değerleri [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) belgelerinde açıklanmıştır.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, geri dönüş değeri modülün bir tutamacıdır. Hatada, iade değeri NULL'dur.

### <a name="remarks"></a>Açıklamalar

`AfxLoadLibraryEx`Bir DLL işlevinin adresini almak için [GetProcAddress'te](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) kullanılabilecek bir tutamacı döndürür. `AfxLoadLibraryEx`diğer çalıştırılabilir modüllerin haritasını çıkarmak için de kullanılabilir.

Her işlem, yüklenen her kitaplık modülü için bir başvuru sayısı tutar. Bu başvuru sayısı her çağrıldı `AfxLoadLibraryEx` ve her zaman `AfxFreeLibrary` çağrılır kararnameye artımlı. Başvuru sayısı sıfıra ulaştığında, modül arama işleminin adres alanından eşlenir ve tutamaç artık geçerli değildir.

Uygulamanız birden `AfxLoadLibraryEx` `AfxFreeLibrary` çok iş parçacığı kullanıyorsa ve dinamik olarak bir MFC uzantısı DLL yüklerse ve (Win32 işlevleri `LoadLibraryEx` yerine) `FreeLibrary`kullandığınızdan emin olun. MFC uzantısı DLL yüklendiğinde ve boşaltıldığında çalıştıran başlatma ve kapatma kodunun kullanılması `AfxLoadLibraryEx` ve `AfxFreeLibrary` genel MFC durumunun bozulmamasını sağlar.

Bir `AfxLoadLibraryEx` uygulamada kullanmak, MFC'nin DLL sürümüne dinamik olarak bağlanmanızı gerektirir. `AfxLoadLibraryEx`MFC uygulamaya DLL olarak bağlıysa, Afxdll_.h için üstbilgi dosyası yalnızca dahil edilir. MFC uzantılı DL'leri kullanmak veya oluşturmak için MFC'nin DLL sürümüne bağlanmanız gerekir, çünkü bu gereksinim tasarım gereğidir.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdll_.h

## <a name="afxmenutearoffmanager"></a><a name="afxmenutearoffmanager"></a>AfxMenuTearOffManager

Genel [yırtılma menü yöneticisiiçin](cmenutearoffmanager-class.md)işaretçi.

### <a name="syntax"></a>Sözdizimi

```cpp
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxmenutearoffmanager.h

## <a name="afxmousemanager"></a><a name="afxmousemanager"></a>AfxMouseManager

Genel fare [yöneticisiiçin](cmousemanager-class.md)işaretçi.

### <a name="syntax"></a>Sözdizimi

```cpp
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmousemanager.h

## <a name="afxregisterclass"></a><a name="afxregisterclass"></a>AfxRegisterClass

MFC kullanan bir DLL pencere sınıfları kaydetmek için bu işlevi kullanın.

```cpp
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>Parametreler

*lpWndClass*\
Kaydedilecek pencere sınıfı hakkında bilgi içeren bir [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısıiçin işaretçi. Bu yapı hakkında daha fazla bilgi için Windows SDK'ya bakın.

### <a name="return-value"></a>Dönüş Değeri

Sınıf başarıyla kaydedilmişse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullanırsanız, DLL boşaltıldığında sınıf otomatik olarak kayıtsız kalmaktadır.

DLL olmayan yapılarda tanımlayıcı, `AfxRegisterClass` uygulamada kayıtlı sınıflar otomatik olarak kayıtdışı olduğundan, Windows işleviyle `RegisterClass`eşleyen bir makro olarak tanımlanır. Bunun yerine `AfxRegisterClass` `RegisterClass`kullanıyorsanız, kodunuz hem uygulamada hem de DLL'de değişiklik olmadan kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxregisterwndclass"></a><a name="afxregisterwndclass"></a>Afxregisterwndclass

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
Pencere sınıfı için bitwise-OR** (&#124;**) işleci kullanılarak oluşturulan Windows sınıf stilini veya stil kombinasyonunu belirtir. Sınıf stilleri listesi için Windows SDK'daki [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısına bakın. NULL ise, varsayılanlar aşağıdaki gibi ayarlanır:

- Fare stilini CS_DBLCLKS ayarlar ve kullanıcı fareyi çift tıklattığında pencere yordamına çift tıklatma iletileri gönderir.

- Ok imleç stilini Windows standart IDC_ARROW ayarlar.

- Arka plan fırçasını NULL olarak ayarlar, böylece pencere arka planını silmez.

- Simgeyi standart, sallanan Windows logosu simgesine ayarlar.

*hCursor*\
Pencere sınıfından oluşturulan her pencereye yüklenecek imleç kaynağına bir tanıtıcı belirtir. **Varsayılan 0'ı**kullanırsanız, standart IDC_ARROW imleci alırsınız.

*hbrArka Plan*\
Pencere sınıfından oluşturulan her pencereye yüklenecek fırça kaynağına bir tanıtıcı belirtir. **Varsayılan olarak 0**kullanıyorsanız, NULL arka plan fırçanız olur ve varsayılan olarak pencereniz [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd)işlerken arka planını silemez.

*Hıcon*\
Pencere sınıfından oluşturulan her pencereye yüklenecek simge kaynağına bir tanıtıcı belirtir. **Varsayılan 0'ı**kullanırsanız, standart, sallanan Windows logosu simgesini alırsınız.

### <a name="return-value"></a>Dönüş Değeri

Sınıf adını içeren null-sonlandırılan dize. Bir pencere oluşturmak için `Create` bu sınıf `CWnd` adını üye işlevine veya diğer **CWnd**türetilmiş sınıflara geçirebilirsiniz. Ad, Microsoft Hazırlık Sınıfı Kitaplığı tarafından oluşturulur.

> [!NOTE]
> İade değeri statik arabellek için bir işaretçidir. Bu dizeyi kaydetmek için `CString` bir değişkene atayın.

### <a name="remarks"></a>Açıklamalar

Microsoft Hazırlık Sınıf Kitaplığı sizin için otomatik olarak birkaç standart pencere sınıfları kaydeder. Kendi pencere sınıflarınızı kaydetmek istiyorsanız bu işlevi arayın.

Bir sınıfa göre `AfxRegisterWndClass` kayıtlı ad yalnızca parametrelere bağlıdır. Aynı parametrelere sahip birden çok kez ararsanız, `AfxRegisterWndClass` yalnızca ilk çağrıda bir sınıf kaydeder. Aynı parametrelere `AfxRegisterWndClass` sahip daha sonraki aramalar zaten kayıtlı sınıf adını döndürer.

Her sınıf `AfxRegisterWndClass` için ayrı bir pencere sınıfı almak yerine, aynı parametrelere sahip birden çok CWnd türetilmiş sınıf için çağrıda bulunuyorsanız, her sınıf aynı pencere sınıfını paylaşır. CS_CLASSDC sınıf stili kullanılırsa, bu paylaşım sorunlara neden olabilir. Birden çok CS_CLASSDC pencere sınıfı yerine, yalnızca bir CS_CLASSDC pencere sınıfı ile sona erer. Bu sınıfı kullanan tüm C++ pencereleri aynı DC'yi paylaşır. Bu sorunu önlemek için, sınıfı kaydetmek için [AfxRegisterClass'ı](#afxregisterclass) arayın.

Teknik Not [TN001 bakın: Pencere sınıfı](../../mfc/tn001-window-class-registration.md) kaydı ve `AfxRegisterWndClass` işlevi hakkında daha fazla bilgi için Pencere Sınıf Kaydı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxsetperuserregistration"></a><a name="afxsetperuserregistration"></a>AfxSetPerUserRegistration

Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** **(HKCU)** düğümüne yönlendirip yönlendirmediğini ayarlar.

```cpp
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*\
[içinde] TRUE, kayıt defteri bilgilerinin HKCU düğümüne yönlendirilmediğini gösterir. FALSE, uygulamanın kayıt defteri bilgilerini varsayılan düğüme yazdığını gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** **(HKCR)** idi.

### <a name="remarks"></a>Açıklamalar

Windows Vista'dan önce, kayıt defterine erişen uygulamalar genellikle **HKEY_CLASSES_ROOT** düğümlerini kullanırdı. Ancak, Windows Vista veya daha sonraki işletim sistemleri ile, HKCR yazmak için yükseltilmiş modda bir uygulama çalıştırmalısınız.

Bu yöntem, uygulamanızın yüksek modda çalışmadan kayıt defterine okuma ve yazma olanağı sağlar. Kayıt defteri erişimini HKCR'dan HKCU'ya yönlendirerek çalışır. Daha fazla bilgi için [Linker Özellik Sayfaları'na](../../build/reference/linker-property-pages.md)bakın.

Kayıt defteri yeniden yönlendirmesini etkinleştiriseniz, çerçeve HKCR'dan **HKEY_CURRENT_USER\Software\Classes'a**erişimi yönlendirir. Yeniden yönlendirmeden yalnızca MFC ve ATL çerçeveleri etkilenir.

Varsayılan uygulama HKCR altında kayıt defterine erişer.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxstat_.h

## <a name="afxsetresourcehandle"></a><a name="afxsetresourcehandle"></a>AfxSetResourceHandle

Uygulamanın varsayılan kaynaklarının nerede yüklendiğini belirleyen HINSTANCE tanıtıcısını ayarlamak için bu işlevi kullanın.

```cpp
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>Parametreler

*hInstResource*\
Örnek veya modül tutamacı. Uygulama kaynaklarının yüklendiği EXE veya DLL dosyası.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxshellmanager"></a><a name="afxshellmanager"></a>AfxShellManager

Genel kabuk [yöneticisi](cshellmanager-class.md)için işaretçi .

### <a name="syntax"></a>Sözdizimi

```cpp
CShellManager* afxShellManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxshellmanager.h

## <a name="afxsocketinit"></a><a name="afxsocketinit"></a>AfxSocketInit

Windows Soketlerini `CWinApp::InitInstance` başlatmayı sağlamak için geçersiz kılma işlevinizde bu işlevi arayın.

```cpp
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>Parametreler

*lpwsaData*\
[WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata) yapısına işaretçi. *LpwsaData* NULL eşit değilse, o zaman yapının `WSADATA` adresi için çağrı `WSAStartup`ile doldurulur . Bu işlev, uygulama `WSACleanup` sona ermeden önce sizin için çağrılmasını da sağlar.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Statik olarak bağlı bir MFC uygulamasında ikincil iş parçacıklarında MFC `AfxSocketInit` soketleri kullanırken, soket kitaplıklarını başlatmak için soket kullanan her iş parçacığı çağırmanız gerekir. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığı denir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxsock.h

## <a name="afxusertoolsmanager"></a><a name="afxusertoolsmanager"></a>AfxUserToolsManager

Genel kullanıcı [araçları yöneticisiiçin](cusertoolsmanager-class.md)işaretçi.

### <a name="syntax"></a>Sözdizimi

```cpp
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxusertoolsmanager.h

## <a name="afxwininit"></a><a name="afxwininit"></a>AfxWinInit

Bu işlev, MFC'yi başlatmak için GUI tabanlı bir uygulamanın `WinMain` [CWinApp](../../mfc/reference/cwinapp-class.md) başlatılmasının bir parçası olarak MFC tarafından sağlanan işlev tarafından çağrılır.

```cpp
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>Parametreler

*Hınstance*\
Şu anda çalışan modülün tutamacı.

*hPrevInstance*\
Uygulamanın önceki bir örneğine bir tanıtıcı. Win32 tabanlı bir uygulama için bu **NULL**parametre her zaman NULL'dur.

*lpCmdLine*\
Uygulama için komut satırını belirten null-sonlandırılmış dize işaret ediyor.

*nCmdShow*\
GUI uygulamasının ana penceresinin nasıl gösterileceğini belirtir.

### <a name="remarks"></a>Açıklamalar

MFC tarafından sağlanan `WinMain` işlevi kullanmayan bir konsol uygulaması için, `AfxWinInit` MFC'yi başlatmanız için doğrudan aramanız gerekir.

Kendinizi ararsanız, `AfxWinInit` bir `CWinApp` sınıfın örneğini bildirmelisiniz. Bir konsol uygulaması için, kendi sınıfınızı türetmemeyi `CWinApp` seçebilir ve `CWinApp` bunun yerine doğrudan bir örnek kullanabilirsiniz. Bu **teknik, ana**uygulamanızda uygulamanız için tüm işlevselliği bırakmaya karar verirseniz uygundur.

> [!NOTE]
> Bir derleme için etkinleştirme bağlamı oluşturduğunda, MFC kullanıcı modülü tarafından sağlanan bir bildirim kaynağı kullanır. Etkinleştirme bağlamı `AfxWinInit`' nda oluşturulur. Daha fazla bilgi [için, MFC Modülü Durumunda etkinleştirme bağlamları için Destek'e](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](mfc-macros-and-globals.md)\
[Cwinapp Sınıfı](cwinapp-class.md)\
[CContextMenuManager Sınıfı](ccontextmenumanager-class.md)\
[CWnd Sınıfı](cwnd-class.md)\
[CFrameWndEx Sınıfı](cframewndex-class.md)\
[CMFCToolBar Sınıfı](cmfctoolbar-class.md)\
[CKeyboardManager Sınıfı](ckeyboardmanager-class.md)\
[CmenuTearOffManager Sınıfı](cmenutearoffmanager-class.md)\
[CMouseManager Sınıfı](cmousemanager-class.md)\
[CShellManager Sınıfı](cshellmanager-class.md)\
[CusertoolsManager Sınıfı](cusertoolsmanager-class.md)
