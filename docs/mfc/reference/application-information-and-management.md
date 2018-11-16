---
title: Uygulama Bilgileri ve Yönetimi
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: 9d5216cd399943cda67bc9387ea37c938e5cab48
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694341"
---
# <a name="application-information-and-management"></a>Uygulama Bilgileri ve Yönetimi

Tek bir uygulama yazdığınızda, oluşturduğunuz [CWinApp](../../mfc/reference/cwinapp-class.md)-türetilmiş bir nesneye. Bazen bu nesneden dışında hakkında bilgi edinmek isteyebilirsiniz `CWinApp`-türetilmiş bir nesneye. Veya diğer genel "mananger'a" nesnelere erişimi gerekebilir.

Microsoft Foundation Class Kitaplığı, bu görevleri gerçekleştirmenize yardımcı olması için aşağıdaki genel işlevleri sağlar:

### <a name="application-information-and-management-functions"></a>Uygulama bilgileri ve Yönetimi işlevleri

|||
|-|-|
|[AfxBeginThread](#afxbeginthread)|Yeni bir iş parçacığı oluşturur.|
|[AfxContextMenuManager](#afxcontextmenumanager)|Genel işaretçisine [bağlam menüsü manager](ccontextmenumanager-class.md).|
|[AfxEndThread](#afxendthread)|Geçerli iş parçacığı sonlanır.|
|[AfxFindResourceHandle](#afxfindresourcehandle)|Kaynak zincirini size yol gösterir ve belirli bir kaynak tarafından kaynak kimliği ve kaynak türünü bulun. |
|[AfxFreeLibrary](#afxfreelibrary)|Yüklenen dinamik bağlantı kitaplığı (DLL) modülün başvuru sayısını azaltır; başvuru sayısı sıfır ulaştığında eşlenmemiş bir modüldür.|
|[AfxGetApp](#afxgetapp)|Tek bir uygulama için bir işaretçi döndürür `CWinApp` nesne.|
|[AfxGetAppName](#afxgetappname)|Uygulamanın adını içeren bir dize döndürür.|
|[Afxgetınstancehandle](#afxgetinstancehandle)|Uygulamanın bu örneği temsil eden bir HINSTANCE döndürür.|
|[AfxGetMainWnd](#afxgetmainwnd)|OLE dışı uygulamanızın "ana" geçerli pencere ya da yerinde çerçeve penceresini bir sunucu uygulaması için bir işaretçi döndürür.|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Uygulama kayıt defteri erişimini yönlendiren olup olmadığını belirlemek için bu işlevi kullanın **HKEY_CURRENT_USER** ( **HKCU**) düğüm.|
|[AfxGetResourceHandle](#afxgetresourcehandle)|Uygulamanın varsayılan kaynaklar kaynağına bir HINSTANCE döndürür. Uygulamanın kaynaklarını doğrudan erişmek için bunu kullanın.|
|[AfxGetThread](#afxgetthread)|Geçerli bir işaretçi alır [CWinThread](../../mfc/reference/cwinthread-class.md) nesne.|
|[Afxınitrichedit](#afxinitrichedit)|Sürüm 1.0 zengin düzenleme denetiminden uygulama başlatır.|
|[Afxınitrichedit2](#afxinitrichedit2)|Sürüm 2.0 ve sonraki zengin düzenleme denetimi uygulamanın başlatır.|
|[Afxısextendedframeclass](#afxisextendedframeclass)|Verilen aralığında bir genişletilmiş çerçeve nesnesi olup olmadığını belirler.|
|[Afxısmfctoolbar](#afxismfctoolbar)|Belirtilen pencere bir araç çubuğu nesnesi olup olmadığını belirler.|
|[AfxKeyboardManager](#afxkeyboardmanager)|Genel işaretçisine [klavye manager](ckeyboardmanager-class.md).|
|[AfxLoadLibrary](#afxloadlibrary)|DLL modülü eşler ve bir DLL işlevinin adresini almak için kullanılan bir tanıtıcı döndürür.|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|Genel işaretçisine [bölme menü manager](cmenutearoffmanager-class.md).|
|[AfxMouseManager](#afxmousemanager)|Genel işaretçisine [fare manager](cmousemanager-class.md).|
|[AfxRegisterClass](#afxregisterclass)|MFC kullanan bir DLL içinde bir pencere sınıfını kaydeder.|
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC tarafından otomatik olarak kaydedilmiş desteklemek için Windows pencere sınıfını kaydeder.|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Uygulama kayıt defteri erişimini yönlendiren olup olmadığını ayarlar **HKEY_CURRENT_USER** ( **HKCU**) düğüm.|
|[AfxSetResourceHandle](#afxsetresourcehandle)|Uygulamanın varsayılan kaynakları burada yüklenen HINSTANCE tanıtıcı ayarlar.|
|[AfxShellManager](#afxshellmanager)|Genel işaretçisine [Kabuk yöneticisini](cshellmanager-class.md). |
|[Afxsocketınit](#afxsocketinit)|Adlı bir `CWinApp::InitInstance` Windows Sockets başlatmak için geçersiz kılın.|
|[AfxUserToolsManager](#afxusertoolsmanager)|Genel işaretçisine [kullanıcı araçları Yöneticisi](cusertoolsmanager-class.md).|
|[Afxwinınit](#afxwininit)|MFC tarafından sağlanan tarafından adlandırılan `WinMain` işlevi, bir parçası olarak [CWinApp](../../mfc/reference/cwinapp-class.md) MFC başlatmak için bir GUI tabanlı bir uygulama başlatma. MFC kullanan doğrudan konsol uygulamaları için çağrılmalıdır.|

##  <a name="afxbeginthread"></a>  AfxBeginThread

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
Çalışan iş parçacığı için denetleme işlevine işaret eder. NULL olamaz. Bu işlev şu şekilde bildirilmesi gerekir:

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThreadClass*<br/>
Bir nesnenin RUNTIME_CLASS türetilen [CWinThread](../../mfc/reference/cwinthread-class.md).

*pParam*<br/>
İçin işlev bildiriminde bulunan parametrede gösterildiği denetim işlevine iletilecek parametre *pfnThreadProc*.

*nPriority*<br/>
İş parçacığının istenen önceliği. Tam listesi ve kullanılabilir açıklaması için bkz. [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK.

*nStackSize*<br/>
Yeni iş parçacığı yığınının bayt cinsinden boyutunu belirtir. 0 ise, oluşturulan iş parçacığıyla aynı boyutta bir yığına için yığın boyutu varsayılan olarak ayarlanır.

*dwCreateFlags*<br/>
İş parçacığı oluşturmayı denetleyen ek bir bayrak belirtir. Bu bayrak, iki değerden birini içerebilir:

- CREATE_SUSPENDED iş parçacığı bir askıya alma sayımı Bir'den başlatın. Tüm üye verilerini başlatmak istiyorsanız CREATE_SUSPENDED kullanın `CWinThread` gibi nesne [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) veya tüm üyeleri iş parçacığı çalışmaya başlamadan önce türetilmiş sınıf. Başlatma işleminiz tamamlandığında kullanın [CWinThread::ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) iş parçacığının çalışmasını başlatmak için. İş parçacığı kadar yürütülmez `CWinThread::ResumeThread` çağrılır.

- **0** oluşturduktan hemen sonra iş parçacığı başlatılamıyor.

*lpSecurityAttrs*<br/>
İşaret eden bir [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) iş parçacığı için güvenlik özniteliklerini belirten yapısı. NULL ise, oluşturulan iş parçacığıyla aynı güvenlik öznitelikleri kullanılır. Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan iş parçacığı nesnesi veya bir hata oluşursa NULL işaretçisi.

### <a name="remarks"></a>Açıklamalar

İlk formu `AfxBeginThread` çalışan iş parçacığı oluşturur. İkinci form, bir kullanıcı arabirimi iş parçacığı veya bir iş parçacığı olarak yapabilen bir iş parçacığı oluşturur.

`AfxBeginThread` Yeni bir oluşturur `CWinThread` nesnesi, çağrılar kendi [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) iş parçacığını yürütmeye başlamak için işlev ve iş parçacığına bir işaretçi döndürür. Denetimleri, tüm nesnelerin düzgün bir şekilde oluşturmayı, herhangi bir bölümü başarısız olması serbest bırakıldığından emin olmak için yordam boyunca gerçekleştirilir. İş parçacığını sonlandırmak için çağrı [AfxEndThread](#afxendthread) gelen iş parçacığı veya çalışan iş parçacığının denetleme işlevinden dönüş içinde.

Çoklu iş parçacığı kullanımı, uygulama tarafından etkinleştirilmelidir; Aksi takdirde, bu işlev başarısız olur. Çoklu iş parçacığı kullanımı etkinleştirme hakkında daha fazla bilgi için [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md) altında *Visual C++ Derleyici Seçenekleri*.

Daha fazla bilgi için `AfxBeginThread`, makalelere göz atın [çoklu iş parçacığı kullanımı: çalışan iş parçacıkları oluşturma](../../parallel/multithreading-creating-worker-threads.md) ve [çoklu iş parçacığı kullanımı: kullanıcı arabirimi iş parçacıkları oluşturma](../../parallel/multithreading-creating-user-interface-threads.md).

### <a name="example"></a>Örnek

Örneğin bakın [CSocket::Attach](../../mfc/reference/csocket-class.md#attach).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

## <a name="afxcontextmenumanager"></a> AfxContextMenuManager

Genel işaretçisine [bağlam menüsü manager](ccontextmenumanager-class.md).

### <a name="syntax"></a>Sözdizimi

```
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxcontextmenumanager.h

### <a name="see-also"></a>Ayrıca Bkz.

[CContextMenuManager Sınıfı](ccontextmenumanager-class.md)

##  <a name="afxendthread"></a>  AfxEndThread

Yürütülmekte olan iş parçacığını sonlandırmak için bu işlevi çağırın.

```
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>Parametreler

*nExitCode*<br/>
İş parçacığı çıkış kodunu belirtir.

*bSil*<br/>
Bellekten iş parçacığı nesnesini siler.

### <a name="remarks"></a>Açıklamalar

Sonlandırılacak olan iş parçacığının içinden çağrılmalıdır.

Daha fazla bilgi için `AfxEndThread`, makaleye göz atın [çoklu iş parçacığı kullanımı: iş parçacıklarını sonlandırma](../../parallel/multithreading-terminating-threads.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

  ## <a name="afxfindresourcehandle"></a>AfxFindResourceHandle
Kullanım `AfxFindResourceHandle` kaynak zinciri yol ve belirli bir kaynak tarafından kaynak kimliği ve kaynak türünü bulun.

### <a name="syntax"></a>Sözdizimi

```
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Kaynak kimliğini içeren bir dize işaretçisi
*lpszType*<br/>
Kaynak türü için bir işaretçi. Kaynak türleri listesi için bkz. [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Kaynak içeren modül için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

`AfxFindResourceHandle` belirli kaynak bulur ve kaynak içeren modül için bir tanıtıcı döndürür. Kaynak herhangi MFC uzantısı DLL, yüklemiş olabilir. `AfxFindResourceHandle` size hangi kaynağın sahip bildirir.

Modüller, bu sırada aranır:

1. Ana Modülü (bir MFC uzantılı DLL ise).

1. Sistem dışı modüller.

1. Dile özgü modüller.

1. Ana Modülü (bir sistem DLL ise).

1. Sistem modüller.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

### <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](mfc-macros-and-globals.md)

##  <a name="afxfreelibrary"></a>  AfxFreeLibrary

Her ikisi de `AfxFreeLibrary` ve `AfxLoadLibrary` her yüklenen kitaplık modülü için bir başvuru sayısı Bakımı.

```
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>Parametreler

*hInstLib*<br/>
Yüklenen kitaplık modülü tanıtıcısı. [AfxLoadLibrary](#afxloadlibrary) bu tanıtıcısını döndürür.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

`AfxFreeLibrary` yüklenen dinamik bağlantı kitaplığı (DLL) modülün başvuru sayısını azaltır. Başvuru sayısı sıfır ulaştığında, çağıran işlemin adres alanından eşlenmemiş bir modüldür, tanıtıcı artık geçerli değil. Her zaman bu başvuru sayısının artırılması `AfxLoadLibrary` çağrılır.

Kitaplık modülü eşleme önce DLL kullanan işlemlerden ayırmak sistemi sağlar. Bunun yapılması DLL adına geçerli işlem için ayrılan kaynakları temizlemek için bir fırsat sağlar. Giriş noktası işlev döndürdükten sonra kitaplık modülü geçerli işlemin adres alanından kaldırılır.

Kullanım `AfxLoadLibrary` bir DLL modülü eşlemek için.

Kullandığınızdan emin olun `AfxFreeLibrary` ve `AfxLoadLibrary` (Win32 işlevlerini yerine `FreeLibrary` ve `LoadLibrary`) uygulamanız birden çok iş parçacığı kullanıyorsa. Kullanarak `AfxLoadLibrary` ve `AfxFreeLibrary` MFC uzantısı DLL yüklendiğinde ve kaldırıldığında genel MFC durumunun bozulmasına neden değil, yürütülen başlatma ve kapatma kod sağlar.

### <a name="example"></a>Örnek

Örneğin bakın [AfxLoadLibrary](#afxloadlibrary).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdll_.h

##  <a name="afxgetapp"></a>  AfxGetApp

Bu işlev tarafından döndürülen işaretçi ana ileti gönderme kodu veya en üstteki pencere gibi uygulama bilgilerine erişmek için kullanılabilir.

```
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>Dönüş Değeri

Tek bir işaretçiye `CWinApp` uygulama için nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem NULL döndürür, uygulamanın ana pencere tamamen henüz başlatılmadı olduğunu gösteriyor olabilir. Ayrıca bir sorun olduğunu gösterebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxgetappname"></a>  AfxGetAppName

Bu işlev tarafından döndürülen dize için tanılama iletileri veya bir kök olarak geçici dize adları için kullanılabilir.

```
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın adını içeren null ile sonlandırılmış bir dize.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxgetinstancehandle"></a>  Afxgetınstancehandle

Bu işlev, geçerli uygulamanın örnek tanıtıcısını almanıza olanak tanır.

```
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>Dönüş Değeri

Bir HINSTANCE uygulamanın geçerli örneği. MFC USRDLL sürümüyle bağlantılı bir DLL içinde çağrılır, DLL bir HINSTANCE döndürülür.

### <a name="remarks"></a>Açıklamalar

`AfxGetInstanceHandle` her zaman yürütülebilir dosyanızın HINSTANCE döndürür (. EXE) içinden çağrılmadıkça DLL MFC USRDLL sürümüyle bağlantılı. Bu durumda, bir HINSTANCE DLL'ye döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxgetmainwnd"></a>  AfxGetMainWnd

Uygulamanızı bir OLE sunucusu ise, yerine doğrudan söz konusu uygulamanın etkin ana penceresini bir işaretçi almak için bu işlevi çağırın [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) üyesi uygulama nesnesi.

```
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>Dönüş Değeri

Sunucu yerinde bir nesneye sahipse bir kapsayıcı ve bu kapsayıcı içinde etkin etkin, bu işlev, yerinde etkin belge çerçeve penceresi nesnesine bir işaretçi döndürür.

Bir kapsayıcıdaki yerinde etkin nesnesi yok veya uygulamanızın bir OLE sunucusu değil ise, bu işlev yalnızca döndürür *m_pMainWnd* , uygulama nesnesi.

Varsa `AfxGetMainWnd` çağrılır isteğe bağlı olarak uygulamanın birincil iş parçacığından uygulamanın ana pencere yukarıdaki kurallara göre döndürür. İkincil bir iş parçacığından uygulamada işlev çağrılırsa, işlev çağrısı yapan iş parçacığıyla ilişkilendirilmiş ana pencereyi döndürür.

### <a name="remarks"></a>Açıklamalar

Uygulamanızı bir OLE sunucusu değil. sonra bu işlevi çağırmak için başvuran için eşdeğer *m_pMainWnd* üyesi, uygulama nesnesi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxgetperuserregistration"></a>  AfxGetPerUserRegistration

Uygulama kayıt defteri erişimini yönlendiren olup olmadığını belirlemek için bu işlevi kullanın **HKEY_CURRENT_USER** ( **HKCU**) düğüm.

```
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>Dönüş Değeri

TRUE, kayıt defteri bilgilerini HKCU düğüme yönlendirilir gösterir; FALSE, uygulama varsayılan düğüme kayıt defteri bilgilerini yazar gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** ( **HKCR**).

### <a name="remarks"></a>Açıklamalar

Kayıt defteri yeniden yönlendirme etkinleştirirseniz, framework erişimden yönlendiren **HKCR** için **HKEY_CURRENT_USER\Software\Classes**. Yalnızca MFC ve ATL çerçeveleri yönlendirme tarafından etkilenir.

Uygulama kayıt defteri erişimini yönlendiren olmadığını değiştirmek için kullanın [AfxSetPerUserRegistration](#afxsetperuserregistration).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxstat_.h

##  <a name="afxgetresourcehandle"></a>  AfxGetResourceHandle

Uygulamanın kaynaklarını doğrudan erişmek için bu işlev tarafından döndürülen HINSTANCE işlemek kullanımı gibi Windows çağrıları işlevi `FindResource`.

```
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın varsayılan kaynakları burada yüklü olan bir HINSTANCE tanıtıcısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxgetthread"></a>  AfxGetThread

Bir işaretçi almak için bu işlevi çağırın [CWinThread](../../mfc/reference/cwinthread-class.md) yürütülmekte olan iş parçacığını temsil eden nesne.

```
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>Dönüş Değeri

Yürütülmekte olan iş parçacığını işaretçi; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

İstenen iş parçacığının içinden çağrılmalıdır.

> [!NOTE]
>  Bir MFC projesi arama bağlantı noktası oluşturma, `AfxGetThread` 4.2, 5.0 veya 6.0, Visual C++ sürümlerinden `AfxGetThread` çağrıları [AfxGetApp](#afxgetapp) hiçbir iş parçacığı bulunursa. Derleyici, daha yeni sürümlerinde `AfxGetThread` hiçbir iş parçacığı bulunmazsa NULL döndürür. Uygulama iş parçacığı istiyorsanız çağırmalısınız `AfxGetApp`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxinitrichedit"></a>  Afxınitrichedit

Uygulama için zengin düzenleme denetimi (sürüm 1.0) başlatmak için bu işlevi çağırın.

```
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, geriye dönük uyumluluk için sağlanır. Yeni uygulamalar kullanması gereken [Afxınitrichedit2](#afxinitrichedit2).

`AfxInitRichEdit` RICHED32 yükler. Zengin Düzenleme denetiminin sürüm 1.0 başlatmak için kullanılan DLL. Sürüm 2.0 ve 3.0 RICHED20 bir zengin düzenleme denetimini kullanmak için. DLL yüklenmesi gerekiyor. Bu çağrı ile gerçekleştirilir [Afxınitrichedit2](#afxinitrichedit2).

Zengin düzenleme denetimlerinde mevcut Visual C++ uygulamaları 2.0 sürümüne güncelleştirmek için açın. RC dosyası bir metin olarak "RICHEDIT" her zengin düzenleme denetimi "RichEdit20a" sınıf adını değiştirin. Ardından çağrısını değiştirin `AfxInitRichEdit` ile `AfxInitRichEdit2`.

Kitaplık zaten işlem için başlatılmamış ise bu işlev Ayrıca ortak denetimler kitaplığını başlatır. Zengin düzenleme denetimi doğrudan MFC uygulamasından kullanırsanız, MFC zengin düzenleme denetiminin çalışma zamanının düzgün bir şekilde başlatıldı güvence altına almak için bu işlevi çağırmanız gerekir. Oluşturma yöntemini çağırırsanız [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), veya [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)bu işlevi çağırmak genellikle gerekli değildir, ancak bazı durumlarda olabilir gerekli.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxinitrichedit2"></a>  Afxınitrichedit2

Uygulama için zengin düzenleme denetimi (sürüm 2.0 ve üzeri) başlatmak için bu işlevi çağırın.

```
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>Açıklamalar

RICHED20 yüklemek için bu işlevi çağırın. DLL ve başlatma 2.0 sürümünü zengin düzenleme denetimi. Oluşturma yöntemini çağırırsanız [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), veya [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)bu işlevi çağırmak genellikle gerekli değildir, ancak bazı durumlarda olabilir gerekli.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

  ## <a name="afxisextendedframeclass"></a>  Afxısextendedframeclass
Verilen aralığında bir genişletilmiş çerçeve nesnesi olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
[in] Türetilen bir nesneye bir işaretçi `CWnd`.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen pencere bir genişletilmiş çerçeve nesnesi ise TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, TRUE döndürür *pWnd* aşağıdaki sınıflarının birinden türetilir:

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

Bir işlev veya metot parametre bir genişletilmiş çerçeve penceresi olduğunu doğrulamak varsa, bu yöntem yararlı olur.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxpriv.h

### <a name="see-also"></a>Ayrıca Bkz.

[CWnd Sınıfı](cwnd-class.md)<br/>
[CFrameWndEx Sınıfı](cframewndex-class.md)

## <a name="afxismfctoolbar"></a> Afxısmfctoolbar

Belirtilen pencere bir araç çubuğu nesnesi olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
[in] Türetilen bir nesneye bir işaretçi `CWnd`.

### <a name="return-value"></a>Dönüş Değeri

Sağlanan penceresi araç çubuğu nesnesi ise TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem döndürür `TRUE` varsa *pWnd* türetildiği `CMFCToolBar`. İşlev veya metot bir parametre olduğunu doğrulamak varsa, bu yöntem kullanışlıdır bir `CMFCToolBar` nesne.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxpriv.h

### <a name="see-also"></a>Ayrıca Bkz.

[CWnd Sınıfı](cwnd-class.md)<br/>
[CMFCToolBar Sınıfı](cmfctoolbar-class.md)

## <a name="afxkeyboardmanager"></a> AfxKeyboardManager

Genel işaretçisine [klavye manager](ckeyboardmanager-class.md).

### <a name="syntax"></a>Sözdizimi

```
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxkeyboardmanager.h

### <a name="see-also"></a>Ayrıca Bkz.

[Makrolar, genel işlevler ve genel değişkenler](mfc-macros-and-globals.md)<br/>
[CKeyboardManager Sınıfı](ckeyboardmanager-class.md)

##  <a name="afxloadlibrary"></a>  AfxLoadLibrary

Kullanım `AfxLoadLibrary` bir DLL modülü eşlemek için.

```
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>Parametreler

*lpszModuleName*<br/>
Modül adını içeren bir null ile sonlandırılmış dizeye işaret (ya da bir. DLL veya. EXE dosyası). Belirtilen ad modülünün dosya adıdır.

Dizeyi bir yol belirtir, ancak dosyayı belirtilen dizinde mevcut değil, işlev başarısız olur.

Bir yol belirtilmezse ve dosya adı uzantısı atlanırsa, varsayılan uzantı. DLL eklenir. Ancak, dosya adı dizesi, modül adı uzantısı yoksa belirtmek için bir sondaki nokta karakteri (.) içerebilir. Yol belirtildiğinde, işlev dosya aşağıdaki sırayla arar:

- Uygulama içinden yüklenen dizin.

- Geçerli dizin.

- **Windows 95/98:** Windows Sistem dizini. **Windows NT:** 32-bit Windows Sistem dizini. Bu dizin SYSTEM32 adıdır.

- **Yalnızca Windows NT:** 16-bit Windows Sistem dizini. Bu dizinin yolunu alır hiçbir Win32 işlevi yoktur, ancak bunu aranır. Bu dizinin adını sistemidir.

- Windows dizini.

- PATH ortam değişkeninde listelenen dizinleri.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri modülüne işleyicisidir. İşlev başarısız olursa, dönüş değeri NULL olur.

### <a name="remarks"></a>Açıklamalar

Kullanılabilir bir tanıtıcı döndürür [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) DLL işlevin adresini almak için. `AfxLoadLibrary` Ayrıca diğer yürütülebilir modüllerin eşlemek için kullanılabilir.

Her işlem, her yüklenen kitaplık modülü için bir başvuru sayısını tutar. Her zaman bu başvuru sayısının artırılması `AfxLoadLibrary` çağrılır ve her zaman azaltılır `AfxFreeLibrary` çağrılır. Başvuru sayısı sıfır ulaştığında, çağıran işlemin adres alanından eşlenmemiş bir modüldür, tanıtıcı artık geçerli değil.

Kullandığınızdan emin olun `AfxLoadLibrary` ve `AfxFreeLibrary` (Win32 işlevlerini yerine `LoadLibrary` ve `FreeLibrary`) uygulamanız birden çok iş parçacığı kullanıyorsa ve dinamik olarak bir MFC uzantılı DLL yükler. Kullanarak `AfxLoadLibrary` ve `AfxFreeLibrary` MFC uzantısı DLL yüklendiğinde ve kaldırıldığında, yürütülen başlatma ve kapatma kod genel MFC durum bozuk değil oluşturmasını sağlar.

Kullanarak `AfxLoadLibrary` uygulamada gerektirir; MFC'nin DLL sürümü için dinamik olarak bağlanmak için üst bilgi dosyası `AfxLoadLibrary`, Afxdll_.h, yalnızca MFC uygulamasına bir DLL olarak bağlanırsa dahil. Kullanma veya MFC uzantısı DLL'leri oluşturmak için MFC'nin DLL sürümü için bağlamak sahip olduğunuz için bu tasarım gereğidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdll_.h

## <a name="afxmenutearoffmanager"></a> AfxMenuTearOffManager

Genel işaretçisine [bölme menü manager](cmenutearoffmanager-class.md).

### <a name="syntax"></a>Sözdizimi

```
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxmenutearoffmanager.h

### <a name="see-also"></a>Ayrıca Bkz.

[CMenuTearOffManager Sınıfı](cmenutearoffmanager-class.md)

## <a name="afxmousemanager"></a>  AfxMouseManager

Genel işaretçisine [fare manager](cmousemanager-class.md).

### <a name="syntax"></a>Sözdizimi

```
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxmousemanager.h

### <a name="see-also"></a>Ayrıca Bkz.

[CMouseManager Sınıfı](cmousemanager-class.md)

##  <a name="afxregisterclass"></a>  AfxRegisterClass

Pencere sınıfları kullanan MFC DLL içinde kaydetmek için bu işlevi kullanın.

```
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>Parametreler

*lpWndClass*<br/>
İşaretçi bir [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) kaydedilecek pencere sınıfı hakkında bilgi içeren yapıya. Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.

### <a name="return-value"></a>Dönüş Değeri

Sınıf başarıyla kaydettirildi TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işlev kullanırsanız, DLL kaldırıldığında otomatik kaydı sınıftır.

DLL olmayan yapılarda `AfxRegisterClass` tanımlayıcısı Windows işleve eşleyen bir makro olarak tanımlanmış olan `RegisterClass`, kayıtlı bir uygulamaya sınıfları otomatik olarak kaydı olduğundan. Kullanırsanız `AfxRegisterClass` yerine `RegisterClass`, kodunuzu hem uygulama hem de bir DLL değişiklik olmadan kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxregisterwndclass"></a>  AfxRegisterWndClass

Kendi pencere sınıflarını kaydetme sağlar.

```
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>Parametreler

*nClassStyle*<br/>
Windows sınıf stil veya stilleri, bit düzeyinde OR kullanılarak oluşturulan bir birleşimini belirtir ( **&#124;**) işleci, pencere sınıfı için. Sınıf stilleri bir listesi için bkz. [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) Windows SDK'sındaki yapısı. NULL ise, varsayılan değerleri şu şekilde ayarlanır:

- Kullanıcı fare çift tıkladığında hangi gönderimler pencere yordamını iletileri çift CS_DBLCLKS için fare stilini ayarlar.

- Windows standart IDC_ARROW ok imleç stilini ayarlar.

- Pencere arka planı silme değil için arka plan Fırçası NULL olarak ayarlar.

- Simge için standart, el Sallayan bayrağı Windows logosu simgesi ayarlar.

*hCursor*<br/>
İmleç kaynak penceresi sınıfından oluşturulan her pencere yüklenmesi için bir tanıtıcı belirtir. Varsayılan değerini kullanırsanız **0**, standart IDC_ARROW imleci alır.

*hbrBackground*<br/>
Fırça kaynağı penceresi sınıfından oluşturulan her pencere yüklenmesi için bir tanıtıcı belirtir. Varsayılan değerini kullanırsanız **0**NULL arkaplan Fırçası olacaktır ve pencerenizi varsayılan olarak, kendi arka plan işlenirken silecek değil [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd).

*hIcon*<br/>
Pencere sınıfından oluşturulan her penceresinde yüklenmesi için simge kaynağı için bir tanıtıcı belirtir. Varsayılan değerini kullanırsanız **0**, standart, el Sallayan bayrağı Windows logo simgesini alırsınız.

### <a name="return-value"></a>Dönüş Değeri

Sınıf adı içeren null ile sonlandırılmış bir dize. Bu sınıf adı için geçirdiğiniz `Create` üye işlevinde `CWnd` veya diğer **CWnd -** türetilmiş sınıfları bir pencere oluşturmak için. Ad, Microsoft Foundation Class Kitaplığı tarafından oluşturulur.

> [!NOTE]
>  Dönüş değeri, arabellek için statik bir işaretçisidir. Bu dize kaydetmek için kendisine atama bir `CString` değişkeni.

### <a name="remarks"></a>Açıklamalar

Microsoft Foundation Class Kitaplığı çeşitli standart pencere sınıfları sizin için otomatik olarak kaydeder. Kendi pencere sınıflarını kaydetmek istiyorsanız, bu işlevi çağırın.

Kayıtlı adı için bir sınıf tarafından `AfxRegisterWndClass` parametreleri yalnızca bağlıdır. Eğer `AfxRegisterWndClass` birden çok kez aynı parametrelerle, yalnızca ilk çağrıda bir sınıfı kaydeder. Yapılan sonraki çağrılar `AfxRegisterWndClass` ile aynı parametreleri yalnızca zaten kayıtlı classname döndürür.

Eğer `AfxRegisterWndClass` her sınıf için ayrı bir pencerede sınıfı yerine aynı parametrelere sahip birden çok CWnd'den türetilen sınıflar için her sınıf aynı pencere sınıfı paylaşır. CS_CLASSDC sınıfı stili kullanılıyorsa, bu sorunlara neden olabilir. Birden çok CS_CLASSDC pencere sınıfları yerine, bir CS_CLASSDC pencere sınıfını ve aynı etki alanı denetleyicisi sınıfı paylaşan kullanan tüm C++ windows edersiniz. Bu sorunu önlemek için çağrı [AfxRegisterClass](#afxregisterclass) sınıfı kaydedilecek.

Teknik Not başvuran [TN001: pencere sınıfı kaydı](../../mfc/tn001-window-class-registration.md) pencere sınıfı kaydı hakkında daha fazla bilgi ve `AfxRegisterWndClass` işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxsetperuserregistration"></a>  AfxSetPerUserRegistration

Uygulama kayıt defteri erişimini yönlendiren olup olmadığını ayarlar **HKEY_CURRENT_USER** ( **HKCU**) düğüm.

```
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] TRUE, kayıt defteri bilgilerini HKCU düğüme yönlendirilir gösterir; FALSE, uygulama varsayılan düğüme kayıt defteri bilgilerini yazar gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** ( **HKCR**).

### <a name="remarks"></a>Açıklamalar

Windows Vista, genellikle kullanılan kayıt defteri erişilen uygulamalar önce **HKEY_CLASSES_ROOT** düğümü. Ancak, Windows Vista veya sonraki işletim sistemleri ile bir uygulama için HKCR yazmak için yükseltilmiş modda çalıştırmanız gerekir.

Bu yöntem, okumak ve HKCU HKCR kayıt defteri erişim yönlendirerek yükseltilmiş modda çalıştırmadan kayıt defterine yazmak uygulamanızın sağlar. Daha fazla bilgi için [bağlayıcı özellik sayfaları](../../ide/linker-property-pages.md).

Kayıt defteri yeniden yönlendirme etkinleştirirseniz, framework için HKCR erişimden yönlendiren **HKEY_CURRENT_USER\Software\Classes**. Yalnızca MFC ve ATL çerçeveleri yönlendirme tarafından etkilenir.

Varsayılan uygulama HKCR altındaki kayıt defterine erişir.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxstat_.h

##  <a name="afxsetresourcehandle"></a>  AfxSetResourceHandle

Uygulamanın varsayılan kaynakları burada yüklenen belirler HINSTANCE tanıtıcı ayarlamak için bu işlevi kullanın.

```
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>Parametreler

*hInstResource*<br/>
Örneği veya modül tanıtıcısını bir. EXE veya DLL dosyası, uygulama kaynaklarının yüklenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

## <a name="afxshellmanager"></a>  AfxShellManager

Genel işaretçisine [Kabuk yöneticisini](cshellmanager-class.md).

### <a name="syntax"></a>Sözdizimi

```
CShellManager* afxShellManager;
```

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxshellmanager.h

### <a name="see-also"></a>Ayrıca Bkz.

[CShellManager Sınıfı](cshellmanager-class.md)

##  <a name="afxsocketinit"></a>  Afxsocketınit

Bu işlevi çağırmak, `CWinApp::InitInstance` Windows Sockets başlatmak için geçersiz kılın.

```
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>Parametreler

*lpwsaData*<br/>
Bir işaretçi bir [WSADATA](../../mfc/reference/wsadata-structure.md) yapısı. Varsa *lpwsaData* NULL, ardından adresini eşit değil `WSADATA` yapısı çağrısıyla dolduğunda `WSAStartup`. Bu işlev ayrıca sağlar `WSACleanup` uygulama sonlandırılmadan önce sizin için çağrılır.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Statik olarak bağlı bir MFC uygulamasında İkincil iş parçacıklarındaki MFC Yuvaları kullanılırken çağırmalısınız `AfxSocketInit` yuva kitaplıklarını başlatma yuva kullanan her bir iş parçacığı. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığında çağrılır.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxsock.h

## <a name="afxusertoolsmanager"></a>  AfxUserToolsManager

Genel işaretçisine [kullanıcı araçları Yöneticisi](cusertoolsmanager-class.md).

### <a name="syntax"></a>Sözdizimi

```
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxusertoolsmanager.h

### <a name="see-also"></a>Ayrıca Bkz.

[CUserToolsManager Sınıfı](cusertoolsmanager-class.md)

##  <a name="afxwininit"></a>  Afxwinınit

MFC tarafından sağlanan tarafından bu işlev çağrılır `WinMain` işlevi, bir parçası olarak [CWinApp](../../mfc/reference/cwinapp-class.md) MFC başlatmak için bir GUI tabanlı bir uygulama başlatma.

```
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
Şu anda çalışan modül tanıtıcısı.

*hPrevInstance*<br/>
Uygulamanın önceki bir örneği için bir tanıtıcı. Win32 tabanlı bir uygulama için bu parametreyi her zaman olduğu **NULL**.

*lpCmdLine*<br/>
Uygulama için komut satırı belirten bir boş sonlandırılmış dizeye işaret eder.

*nCmdShow*<br/>
Nasıl bir GUI uygulamanın ana pencere gösterilen belirtir.

### <a name="remarks"></a>Açıklamalar

Bir konsol uygulaması için hangi kullanmayan MFC tarafından sağlanan `WinMain` işlevini çağırmalıdır `AfxWinInit` doğrudan MFC başlatılamadı.

Eğer `AfxWinInit` kendiniz bir örneğini bildirmeniz gerekir bir `CWinApp` sınıfı. Bir konsol uygulaması için kendi sınıfından türetilir değil tercih edebileceğiniz `CWinApp` ve bunun yerine bir örneğini kullanması `CWinApp` doğrudan. Uygulamanız için tüm işlevselliği uygulamanızda bırakmak isterseniz bu tekniği uygundur **ana**.

> [!NOTE]
>  Bir derleme için bir etkinleştirme bağlamı oluşturur, MFC kullanıcı modülü tarafından sağlanan bir bildirim kaynağı kullanır. Etkinleştirme bağlamı oluşturulan `AfxWinInit`. Daha fazla bilgi için [MFC modül durumunda etkinleştirme bağlamları desteği](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CWinApp Sınıfı](../../mfc/reference/cwinapp-class.md)
