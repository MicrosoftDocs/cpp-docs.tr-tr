---
title: Uygulama bilgileri ve Yönetimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41b6aa602956c6dcdeda8f6b8c24c1be48c58ce2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358488"
---
# <a name="application-information-and-management"></a>Uygulama Bilgileri ve Yönetimi
Bir uygulama yazdığınızda, tek bir oluşturma [CWinApp](../../mfc/reference/cwinapp-class.md)-türetilmiş bir nesne içermelidir. Bazen bu nesneden dışında hakkında bilgi edinmek isteyebilirsiniz `CWinApp`-türetilmiş bir nesne içermelidir. Veya diğer genel "mananger'a" nesnelere erişimi gerekebilir.
  
 Microsoft Foundation Class Kitaplığı bu görevleri gerçekleştirmenize yardımcı olması için aşağıdaki genel işlevleri sağlar:  
  
### <a name="application-information-and-management-functions"></a>Uygulama bilgileri ve Yönetimi işlevleri  
  
|||  
|-|-|  
|[AfxBeginThread](#afxbeginthread)|Yeni bir iş parçacığı oluşturur.|  
|[AfxContextMenuManager](#afxcontextmenumanager)|İşaretçi genel [bağlam menüsü Yöneticisi](ccontextmenumanager-class.md).|
|[AfxEndThread](#afxendthread)|Geçerli iş parçacığının sonlandırır.|  
|[AfxFindResourceHandle](#afxfindresourcehandle)|Kaynak zinciri anlatılmaktadır ve bir özel kaynak tarafından kaynak kimliği ve kaynak türünü bulun. |
|[AfxFreeLibrary](#afxfreelibrary)|Başvuru sayım yüklenen dinamik bağlantı kitaplığı (DLL) modülünü azaltır; başvuru sayısı sıfır ulaştığında eşlenmemiş bir modüldür.|  
|[AfxGetApp](#afxgetapp)|Uygulama için bir işaretçi tek döndürür `CWinApp` nesnesi.|  
|[AfxGetAppName](#afxgetappname)|Uygulamanın adını içeren bir dize döndürür.|  
|[Afxgetınstancehandle](#afxgetinstancehandle)|Döndürür bir `HINSTANCE` uygulama'nın bu örneği temsil eden.|  
|[AfxGetMainWnd](#afxgetmainwnd)|OLE dışı uygulama geçerli "ana" penceresinde ya da bir sunucu uygulaması yerinde çerçeve penceresi için bir işaretçi döndürür.|  
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Uygulama kayıt erişimi yönlendiren olup olmadığını belirlemek için bu işlevi kullanın **HKEY_CURRENT_USER** ( **HKCU**) düğüm.|  
|[AfxGetResourceHandle](#afxgetresourcehandle)|Döndürür bir `HINSTANCE` kaynağına uygulamanın varsayılan kaynaklar. Uygulamanın kaynaklarına doğrudan erişim için bunu kullanın.|  
|[AfxGetThread](#afxgetthread)|Geçerli bir işaretçi alır [CWinThread](../../mfc/reference/cwinthread-class.md) nesnesi.|  
|[Afxınitrichedit](#afxinitrichedit)|1.0 zengin düzenleme denetiminden uygulama için sürüm başlatır.|  
|[Afxınitrichedit2](#afxinitrichedit2)|2.0 ve daha zengin düzenleme denetiminden uygulama için sürüm başlatır.| 
|[Afxısextendedframeclass](#afxisextendedframeclass)|Belirtilen pencere genişletilmiş çerçeve nesne olup olmadığını belirler.|
|[Afxısmfctoolbar](#afxismfctoolbar)|Belirtilen pencere bir araç çubuğu nesnesi olup olmadığını belirler.|
|[AfxKeyboardManager](#afxkeyboardmanager)|İşaretçi genel [klavye Yöneticisi](ckeyboardmanager-class.md).|
|[AfxLoadLibrary](#afxloadlibrary)|DLL modülü eşler ve DLL işlevini adresini elde etmek için kullanılan bir işleyici döner.|  
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|İşaretçi genel [bölme menü Yöneticisi](cmenutearoffmanager-class.md).|
|[AfxMouseManager](#afxmousemanager)|İşaretçi genel [fare Yöneticisi](cmousemanager-class.md).|
|[AfxRegisterClass](#afxregisterclass)|Pencere sınıfı MFC kullanan DLL'de kaydeder.|  
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC tarafından otomatik olarak kaydedilmiş tamamlamak için bir Windows pencere sınıfı kaydeder.|  
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Uygulama kayıt erişimi yönlendiren olup olmadığını ayarlar **HKEY_CURRENT_USER** ( **HKCU**) düğüm.|  
|[AfxSetResourceHandle](#afxsetresourcehandle)|Ayarlar `HINSTANCE` tanıtıcı uygulamanın varsayılan kaynaklar burada yüklenir.|  
|[AfxShellManager](#afxshellmanager)|İşaretçi genel [Kabuk Yöneticisi](cshellmanager-class.md). |
|[Afxsocketınit](#afxsocketinit)|Adlı bir `CWinApp::InitInstance` Windows Sockets başlatmak için geçersiz kılın.|  
|[AfxUserToolsManager](#afxusertoolsmanager)|İşaretçi genel [kullanıcı araçları Yöneticisi](cusertoolsmanager-class.md).|
|[Afxwinınit](#afxwininit)|MFC tarafından sağlanan tarafından adlı `WinMain` parçası olarak işlevi [CWinApp](../../mfc/reference/cwinapp-class.md) MFC başlatmak için bir GUI tabanlı bir uygulama başlatma. MFC kullanan doğrudan konsol uygulamaları için çağrılmalıdır.|  
  

  
##  <a name="afxbeginthread"></a>  AfxBeginThread  
 Yeni bir iş parçacığı oluşturmak için bu işlevini çağırın.  
  
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
 `pfnThreadProc`  
 Çalışan iş parçacığı için denetleme işlevi noktalarına. Olamaz **NULL**. Bu işlevi aşağıdaki gibi bildirilmesi gerekir:  
  
 `UINT __cdecl MyControllingFunction( LPVOID pParam );`  
  
 *pThreadClass*  
 Bir nesnenin RUNTIME_CLASS türetilen [CWinThread](../../mfc/reference/cwinthread-class.md).  
  
 *pParam*  
 İşlevi bildiriminde parametresi gösterildiği gibi denetleyen işlev iletilecek parametre `pfnThreadProc`.  
  
 `nPriority`  
 İş parçacığı istenen önceliği. Tam listesi ve kullanılabilir öncelikleri açıklaması için bkz: [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) Windows SDK'sındaki.  
  
 `nStackSize`  
 Yeni bir iş parçacığı yığınının bayt cinsinden boyutu belirtir. 0 ise, yığın boyutu aynı boyutu yığın oluşturma iş parçacığı olarak varsayılan olarak ayarlanır.  
  
 `dwCreateFlags`  
 İş parçacığı oluşturma denetimleri ek bir bayrak belirtir. Bu bayrak iki değerden birini içerir:  
  
- **AfxBeginThread'e** bir askıya alma sayısına ile iş parçacığı başlatılamıyor. Kullanım **AfxBeginThread'e** , herhangi bir üye veri başlatmak istiyorsanız `CWinThread` gibi nesne [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) veya tüm üyeleri çalışan iş parçacığı başlamadan önce türetilmiş sınıf. Başlatma tamamlandıktan sonra kullanmak [CWinThread::ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) için çalışan iş parçacığı başlatılamıyor. İş parçacığı kadar yürütmez `CWinThread::ResumeThread` olarak adlandırılır.  
  
- **0** hemen oluşturulduktan sonra iş parçacığı başlatılamıyor.  
  
 `lpSecurityAttrs`  
 İşaret eden bir [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) iş parçacığı için güvenlik özniteliklerini belirtir yapısı. Varsa **NULL**, aynı güvenlik nitelikler oluşturma iş parçacığı kullanılır. Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan iş parçacığı nesnesine işaretçi veya **NULL** bir hata oluşursa.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk biçimini `AfxBeginThread` bir çalışan iş parçacığı oluşturur. İkinci form, bir kullanıcı arabirimi iş parçacığı veya bir çalışan iş parçacığı olarak hizmet iş parçacığı oluşturur.  
  
 `AfxBeginThread` Yeni bir `CWinThread` nesnesi, çağrıları kendi [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) iş parçacığının başlatmak için işlev ve iş parçacığına bir işaretçi döndürür. Denetimleri prosedür boyunca tüm nesneleri düzgün herhangi bir kısmını oluşturma başarısız olması kaldırıldığından emin olmak için yapılır. İş parçacığı sona erdirmek için arama [AfxEndThread](#afxendthread) gelen iş parçacığı ya da çalışan iş parçacığı denetleme işlevinin dönüş içinde.  
  
 Çoklu iş parçacığı kullanımı uygulama tarafından etkinleştirilmiş olması gerekir; Aksi takdirde, bu işlev başarısız olur. Çoklu iş parçacığı kullanımı etkinleştirme hakkında daha fazla bilgi için bkz [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md) altında *Visual C++ Derleyici Seçenekleri*.  
  
 Daha fazla bilgi için `AfxBeginThread`, makalelerine bakın [çoklu iş parçacığı kullanımı: çalışan iş parçacığı oluşturma](../../parallel/multithreading-creating-worker-threads.md) ve [çoklu iş parçacığı kullanımı: kullanıcı arabirimi iş parçacıkları oluşturma](../../parallel/multithreading-creating-user-interface-threads.md).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CSocket::Attach](../../mfc/reference/csocket-class.md#attach).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  

## <a name="afxcontextmenumanager"></a> AfxContextMenuManager
İşaretçi genel [bağlam menüsü Yöneticisi](ccontextmenumanager-class.md).  
   
### <a name="syntax"></a>Sözdizimi    
```  
CContextMenuManager* afxContextMenuManager;  
```     
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcontextmenumanager.h     

### <a name="see-also"></a>Ayrıca Bkz.   
 [CContextMenuManager Sınıfı](ccontextmenumanager-class.md)

  
##  <a name="afxendthread"></a>  AfxEndThread  
 Şu anda yürütülen iş parçacığı sonlandırmak için bu işlevini çağırın.  
  
```   
void AFXAPI AfxEndThread(
    UINT nExitCode,  
    BOOL bDelete  = TRUE); 
```  
  
### <a name="parameters"></a>Parametreler  
 *nExitCode*  
 İş parçacığı çıkış kodu belirtir.  
  
 *bSil*  
 İş parçacığı nesnesi bellekten siler.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonlandırılacak iş parçacığı içinde çağrılmalıdır.  
  
 Daha fazla bilgi için `AfxEndThread`, makaleye bakın [çoklu iş parçacığı kullanımı: iş parçacıklarını sonlandırma](../../parallel/multithreading-terminating-threads.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  

  ## <a name="afxfindresourcehandle"></a>AfxFindResourceHandle
Kullanım `AfxFindResourceHandle` kaynak zinciri yol ve belirli bir kaynak tarafından kaynak kimliği ve kaynak türünü bulun.  
   
### <a name="syntax"></a>Sözdizimi    
```
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );  
```
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Kaynak kimliği içeren bir dize için bir işaretçi    
 *lpszType*  
 Kaynak türü için bir işaretçi. Kaynak türleri listesi için bkz: [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) Windows SDK'sındaki.  
   
### <a name="return-value"></a>Dönüş Değeri  
 Kaynak içeren modülü için bir tanıtıcı.  
   
### <a name="remarks"></a>Açıklamalar  
 `AfxFindResourceHandle` belirli kaynak bulur ve kaynak içeren modülü için bir işleyici döner. Kaynak herhangi MFC uzantı DLL'si yüklü olabilir. `AfxFindResourceHandle` kaynağın hangisinin sahip söyler.  
  
 Modüller, bu sırada aranır:  
  
1.  Ana Modülü (MFC uzantı DLL'si ise).  
  
2.  Sistem dışı modüller.  
  
3.  Dile özgü modüller.  
  
4.  Ana Modülü (bir sistem DLL'i ise).  
  
5.  Sistem modüller.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
  
##  <a name="afxfreelibrary"></a>  AfxFreeLibrary  
 Her ikisi de `AfxFreeLibrary` ve `AfxLoadLibrary` her yüklü olan kitaplık modül için bir başvuru sayımı korumak.  
  
```   
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib); 
```  
  
### <a name="parameters"></a>Parametreler  
 *hInstLib*  
 Yüklü olan kitaplık modülü tanıtıcısı. [AfxLoadLibrary](#afxloadlibrary) bu işleyicisini döndürür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** işlevi başarılı olursa; Aksi halde, **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 `AfxFreeLibrary` azaltır yüklenen dinamik bağlantı kitaplığı (DLL) modül, başvuru sayısı. Başvuru sayısı sıfır ulaştığında modülü çağırma işlemi adres alanından eşlenmemiş ve tanıtıcı artık geçerli değil. Bu başvuru sayısı her zaman artırılır `AfxLoadLibrary` olarak adlandırılır.  
  
 Bir kitaplık modülü eşleme önce sistem kullanmadan işlemlerini ayırmak DLL sağlar. Bunun yapılması DLL geçerli işlem adına ayrılmış kaynakları temizlemek için fırsatı sunar. Giriş noktası işlevi döndükten sonra kitaplık modülü geçerli işlem adres alanından kaldırılır.  
  
 Kullanım `AfxLoadLibrary` DLL modülü eşlemek için.  
  
 Kullandığınızdan emin olun `AfxFreeLibrary` ve `AfxLoadLibrary` (Win32 işlevleri yerine **FreeLibrary** ve **LoadLibrary**) uygulamanız birden çok iş parçacığı kullanıyorsa. Kullanarak `AfxLoadLibrary` ve `AfxFreeLibrary` MFC uzantı DLL yüklendiğinde ve kaldırıldığında genel MFC durumunu bozuk olmayan yürütülen başlatma ve kapatma kodunun sağlar.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [AfxLoadLibrary](#afxloadlibrary).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdll_.h  
  
##  <a name="afxgetapp"></a>  AfxGetApp  
 Bu işlev tarafından döndürülen işaretçi ana ileti gönderme kodunu veya en üstteki pencere gibi uygulama bilgilerine erişmek için kullanılabilir.  
  
```   
CWinApp* AFXAPI AfxGetApp(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek bir işaretçi `CWinApp` uygulama nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem NULL değeri döndürülürse, uygulamanın ana pencereyi tam henüz başlatılmadı olduğunu gösteriyor olabilir. Ayrıca bir sorun olduğunu gösterebilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxgetappname"></a>  AfxGetAppName  
 Bu işlev tarafından döndürülen dize tanılama iletileri için veya bir kök olarak geçici dize adları için kullanılabilir.  
  
```   
LPCTSTR AFXAPI AfxGetAppName(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulamanın adını içeren null ile sonlandırılmış bir dize.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxgetinstancehandle"></a>  Afxgetınstancehandle  
 Bu işlev geçerli uygulama örneğinin tanıtıcısını almanıza olanak tanır.  
  
```   
HINSTANCE  AFXAPI AfxGetInstanceHandle(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `HINSTANCE` uygulamanın geçerli örneği. MFC, USRDLL sürümüyle bağlı DLL ve adlı varsa bir `HINSTANCE` DLL'e döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 `AfxGetInstanceHandle` her zaman döndürür `HINSTANCE` yürütülebilir dosyasının (. EXE) içinden adlı sürece DLL MFC USRDLL sürümü ile bağlantılı. Bu durumda, döndüren bir `HINSTANCE` dll.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxgetmainwnd"></a>  AfxGetMainWnd  
 Uygulamanızı OLE sunucusu ise, doğrudan başvurma yerine uygulama etkin ana penceresinde bir işaretçi almak için bu işlevi çağırmak [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) uygulama nesnesi üyesi.  
  
```   
CWnd* AFXAPI AfxGetMainWnd(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerinde bir nesne sunucusu varsa, etkin bir kapsayıcı ve bu kapsayıcı içindeki etkin, bu işlev, yerinde etkin belge çerçeve penceresi nesnesine bir işaretçi döndürür.  
  
 Bir kapsayıcıdaki yerinde etkin nesnesi yok veya uygulamanızın OLE sunucusu değil ise, bu işlev yalnızca döndürür `m_pMainWnd` uygulama nesnesi.  
  
 Varsa `AfxGetMainWnd` çağrılır isteğe bağlı olarak uygulamanın birincil iş parçacığından uygulamanın ana penceresi yukarıdaki kurallara göre döndürür. Uygulamadaki ikincil akıştan işlevi çağrıldıysa, işlev çağrıyı yapan iş parçacığı ile ilişkili ana penceresi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızı bir OLE sunucusu değil sonra bu işlevi çağırmak için başvuran için eşdeğer `m_pMainWnd` , uygulama nesnesinin üyesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxgetperuserregistration"></a>  AfxGetPerUserRegistration  
 Uygulama kayıt erişimi yönlendiren olup olmadığını belirlemek için bu işlevi kullanın **HKEY_CURRENT_USER** ( **HKCU**) düğüm.  
  
```  
BOOL AFXAPI AfxGetPerUserRegistration();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` kayıt defteri bilgileri için yönlendirilir gösterir **HKCU** düğümü; `FALSE` uygulama varsayılan düğüme kayıt defteri bilgilerini yazar gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** ( **HKCR**).  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt defteri yeniden yönlendirmesini devre dışı bırakırsanız, framework erişimden yönlendiren **HKCR** için **HKEY_CURRENT_USER\Software\Classes**. Yalnızca MFC ve ATL çerçeveleri tarafından yeniden yönlendirme etkilenir.  
  
 Uygulama kayıt defteri erişimi yönlendiren olup olmadığını değiştirmek için kullanın [AfxSetPerUserRegistration](#afxsetperuserregistration).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxstat_.h    
  
##  <a name="afxgetresourcehandle"></a>  AfxGetResourceHandle  
 Kullanım `HINSTANCE` uygulamanın kaynaklarına doğrudan, örneğin, Windows işlev çağrıları erişmek için bu işlev tarafından döndürülen tanıtıcı **FindResource**.  
  
```   
extern HINSTANCE  AfxGetResourceHandle(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `HINSTANCE` tanıtıcı uygulamanın varsayılan kaynaklar burada yüklenir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxgetthread"></a>  AfxGetThread  
 Bir işaretçi almak için bu işlevi çağırmak [CWinThread](../../mfc/reference/cwinthread-class.md) şu anda yürütülen iş parçacığı temsil eden nesne.  
  
```   
CWinThread* AfxGetThread(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda yürütülen iş parçacığı işaretçi; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 İstenen iş parçacığının içinden çağrılmalıdır.  
  
> [!NOTE]
>  Bir MFC projesine arama bağlantı noktası oluşturma, `AfxGetThread` 4.2, 5.0 veya 6.0, Visual C++ sürümlerinden `AfxGetThread` çağrıları [AfxGetApp](#afxgetapp) hiçbir iş parçacığı bulunursa. Derleyici, daha yeni sürümlerinde `AfxGetThread` döndürür **NULL** hiçbir iş parçacığı bulunduysa. Uygulama iş parçacığı istiyorsanız çağırmalısınız `AfxGetApp`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxinitrichedit"></a>  Afxınitrichedit  
 Uygulama için zengin düzenleme denetimine (sürüm 1.0) başlatmak için bu işlevini çağırın.  
  
```   
BOOL AFXAPI AfxInitRichEdit(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, geriye dönük uyumluluk için sağlanır. Yeni uygulamalar kullanması gereken [Afxınitrichedit2](#afxinitrichedit2).  
  
 `AfxInitRichEdit` RICHED32 yükler. Zengin düzenleme denetimine 1.0 sürümünü başlatmak için DLL. Sürüm 2.0 ve 3.0 RICHED20 zengin düzenleme denetimi kullanmak için. DLL yüklü olması gerekir. Bu çağrısıyla yapılır [Afxınitrichedit2](#afxinitrichedit2).  
  
 Sürüm 2.0 varolan Visual C++ uygulamalarını zengin düzenleme denetimlerinde güncelleştirmek için açın. RC dosyasını bir metin olarak "RICHEDIT" her zengin düzenleme denetimine "RichEdit20a" sınıf adını değiştirin. Çağrı Değiştir `AfxInitRichEdit` ile `AfxInitRichEdit2`.  
  
 Kitaplık işlemi için zaten başlatılmamış ise bu işlev ortak denetimler kitaplığı da başlatır. Zengin düzenleme denetimine doğrudan MFC uygulamasından kullanıyorsanız, MFC zengin metin düzenleme denetimini çalışma zamanı düzgün başlatılmamış güvence altına almak için bu işlevi çağırmalıdır. Create yöntemini çağırırsanız [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), veya [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), genellikle bu işlevi çağırmak gerekmez, ancak bazı durumlarda olması olabilir gerekli.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxinitrichedit2"></a>  Afxınitrichedit2  
 Uygulama için zengin düzenleme denetimine (sürüm 2.0 ve üzeri) başlatmak için bu işlevini çağırın.  
  
```   
BOOL AFXAPI AfxInitRichEdit2(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 RICHED20 yüklemek için bu işlevini çağırın. DLL ve başlatma zengin 2.0 sürümünü denetim düzenleyin. Create yöntemini çağırırsanız [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), veya [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), genellikle bu işlevi çağırmak gerekmez, ancak bazı durumlarda olması olabilir gerekli.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  

  ## <a name="afxisextendedframeclass"></a>  Afxısextendedframeclass
Belirtilen pencere genişletilmiş çerçeve nesne olup olmadığını belirler.  
   
### <a name="syntax"></a>Sözdizimi    
```  
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );  
```
### <a name="parameters"></a>Parametreler  
 [in] `pWnd`  
 Türetilmiş bir nesne için bir işaretçi `CWnd`.  
   
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` sağlanan pencere genişletilmiş çerçeve nesneyi ise; Aksi takdirde `FALSE`.  
   
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem `TRUE` varsa `pWnd` aşağıdaki sınıflar birinden türetilen:  
  
-   `CFrameWndEx`  
  
-   `CMDIFrameWndEx`  
  
-   `COleIPFrameWndEx`  
  
-   `COleDocIPFrameWndEx`  
  
-   `CMDIChildWndEx`  
  
 Bir işlev veya yöntem parametresi bir genişletilmiş çerçeve penceresi olduğunu doğrulamak varsa, bu yöntem kullanışlıdır.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpriv.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](cwnd-class.md)   
 [CFrameWndEx Sınıfı](cframewndex-class.md)   

## <a name="afxismfctoolbar"></a> Afxısmfctoolbar
Belirtilen pencere bir araç çubuğu nesnesi olup olmadığını belirler.  
   
### <a name="syntax"></a>Sözdizimi    
```  
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);  
```
### <a name="parameters"></a>Parametreler  
 [in] `pWnd`  
 Türetilmiş bir nesne için bir işaretçi `CWnd`.  
   
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` sağlanan pencere bir araç nesneyse; Aksi takdirde `FALSE`.  
   
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem `TRUE` varsa `pWnd` türetilen `CMFCToolBar`. Bir işlev veya yöntem parametresi olduğunu doğrulamak varsa, bu yöntem kullanışlıdır bir `CMFCToolBar` nesnesi.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpriv.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](cwnd-class.md)   
 [CMFCToolBar Sınıfı](cmfctoolbar-class.md)

 
## <a name="afxkeyboardmanager"></a> AfxKeyboardManager
İşaretçi genel [klavye Yöneticisi](ckeyboardmanager-class.md).  
   
### <a name="syntax"></a>Sözdizimi    
```  
CKeyboardManager* afxKeyboardManager;  
```  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxkeyboardmanager.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  

 [Makrolar, genel işlevler ve genel değişkenler](mfc-macros-and-globals.md)   
 [CKeyboardManager Sınıfı](ckeyboardmanager-class.md)


##  <a name="afxloadlibrary"></a>  AfxLoadLibrary  
 Kullanım `AfxLoadLibrary` DLL modülü eşlemek için.  
  
```   
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName); 
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszModuleName*  
 İşaret modülünün adını içeren null ile sonlandırılmış bir dize (ya da bir. DLL veya. EXE dosyası). Belirtilen ad modülün dosya adıdır.  
  
 Dize yolunu belirtir, ancak belirtilen dizinde dosya yok, işlev başarısız olur.  
  
 Yol belirtilmedi ve dosya adı uzantısı atlanırsa, varsayılan uzantısı. DLL eklenir. Ancak, filename dize modül adı uzantısı olduğunu belirtmek için bir sondaki nokta karakteri (.) içerebilir. Yol belirtilmezse, işlevi dosyası aşağıdaki sırayla arar:  
  
-   Uygulama içinden yüklenen dizin.  
  
-   Geçerli dizin.  
  
- **Windows 95/98:** Windows Sistem dizini. **Windows NT:** 32-bit Windows Sistem dizini. Bu dizin SYSTEM32 adıdır.  
  
- **Yalnızca Windows NT:** 16 bit Windows Sistem dizini. Bu dizinin yolunu alır hiçbir Win32 işlevi yoktur, ancak bunu aranır. Bu dizinin adını sistemidir.  
  
-   Windows dizinidir.  
  
-   PATH ortam değişkeninde listelenen dizinleri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri modülüne işleyicisidir. İşlev başarısız olursa, dönüş değeri NULL olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanılabilir bir işleyici döner [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) DLL işlevini adresini almak için. `AfxLoadLibrary` Ayrıca diğer yürütülebilir modüller eşleştirmek için kullanılabilir.  
  
 Her işlem her yüklü olan kitaplık modül için bir başvuru sayımı tutar. Bu başvuru sayısı her zaman artırılır `AfxLoadLibrary` denir ve her zaman düşülür `AfxFreeLibrary` olarak adlandırılır. Başvuru sayısı sıfır ulaştığında modülü çağırma işlemi adres alanından eşlenmemiş ve tanıtıcı artık geçerli değil.  
  
 Kullandığınızdan emin olun `AfxLoadLibrary` ve `AfxFreeLibrary` (Win32 işlevleri yerine **LoadLibrary** ve **FreeLibrary**) uygulamanız birden çok iş parçacığı kullanıyorsa ve dinamik olarak bir MFC yüklüyorsa uzantı DLL. Kullanarak `AfxLoadLibrary` ve `AfxFreeLibrary` MFC uzantı DLL yüklendiğinde ve kaldırıldığında yürütülen başlatma ve kapatma kodunun genel MFC durumunu bozuk olmayan oluşturmasını sağlar.  
  
 Kullanarak `AfxLoadLibrary` MFC; DLL sürümü dinamik olarak bağlamak bir uygulamada gerektiren için üstbilgi dosyası `AfxLoadLibrary`, Afxdll_.h, yalnızca MFC DLL olarak uygulamaya bağlıysa dahil. MFC uzantı DLL'leri oluşturmak veya kullanmak üzere MFC'nin DLL sürümü bağlamak zorunda olduğundan bu tasarım gereğidir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]  
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]  
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdll_.h  
   
## <a name="afxmenutearoffmanager"></a> AfxMenuTearOffManager
İşaretçi genel [bölme menü Yöneticisi](cmenutearoffmanager-class.md).  
   
### <a name="syntax"></a>Sözdizimi    
```  
CMenuTearOffManager* g_pTearOffMenuManager;  
```  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmenutearoffmanager.h  
   
### <a name="see-also"></a>Ayrıca Bkz.     
 [CMenuTearOffManager Sınıfı](cmenutearoffmanager-class.md)
 
## <a name="afxmousemanager"></a>  AfxMouseManager
İşaretçi genel [fare Yöneticisi](cmousemanager-class.md).  
   
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
 *lpWndClass*  
 İşaretçi bir [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) kaydedilecek pencere sınıfı hakkında bilgi içeren yapısı. Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** sınıf başarıyla kayıtlı; Aksi takdirde ise **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevi kullanırsanız, DLL kaldırıldığında otomatik olarak kaydı sınıftır.  
  
 DLL olmayan derlemelerde `AfxRegisterClass` tanımlayıcısı Windows işlev eşlemeleri makrosu olarak tanımlanır **RegisterClass**, bir uygulamada kayıtlı sınıflarını otomatik olarak kaydı olduğundan. Kullanırsanız `AfxRegisterClass` yerine **RegisterClass**, kodunuzu bir uygulamada hem DLL değişiklik olmadan kullanılabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxregisterwndclass"></a>  AfxRegisterWndClass  
 Kendi pencere sınıfları kaydetmenizi sağlar.  
  
```  
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,  
    HCURSOR hCursor = 0,  
    HBRUSH hbrBackground = 0,  
    HICON hIcon = 0);  
```  
  
### <a name="parameters"></a>Parametreler  
 *nClassStyle*  
 Windows sınıfı stili veya Bitsel-OR kullanılarak oluşturulan stilleri bileşimini belirtir ( **&#124;**) pencere sınıfı için işleci. Sınıf stilleri listesi için bkz: [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Windows SDK'sındaki yapısı. Varsa **NULL**, varsayılan değerleri aşağıdaki gibi ayarlayın:  
  
-   Fare stilini ayarlar **CS_DBLCLKS**, kullanıcının fare tıklattığında hangi gönderir pencere yordamı iletileri çift tıklayın.  
  
-   Windows standart ok imleç stilini ayarlar **IDC_ARROW**.  
  
-   Arka plan Fırçası ayarlar **NULL**, pencerenin, arka plan silecek değil.  
  
-   Simge için standart, Sallayan sürekli bayrağı Windows logo simgesini ayarlar.  
  
 `hCursor`  
 Pencere sınıfından oluşturulan her penceresinde yüklenecek imleç kaynağı için tanıtıcı belirtir. Varsayılan değer olan kullanırsanız **0**, standart alırsınız **IDC_ARROW** imleç.  
  
 *hbrBackground*  
 Pencere sınıfından oluşturulan her penceresinde yüklenecek fırça kaynağı için tanıtıcı belirtir. Varsayılan değer olan kullanırsanız **0**, sahip olur bir **NULL** arka planı fırçasını ve varsayılan olarak, pencere değil, arka plan işleme sırasında silme [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055).  
  
 `hIcon`  
 Pencere sınıfından oluşturulan her penceresinde yüklenecek simgesi kaynağı için tanıtıcı belirtir. Varsayılan değer olan kullanırsanız **0**, standart, Sallayan sürekli bayrağı Windows logo simgesini alırsınız.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sınıf adı içeren null ile sonlandırılmış bir dize. Bu sınıf adı geçirebilirsiniz **oluşturma** üye işlevinde `CWnd` veya diğer **CWnd -** türetilmiş sınıfları bir pencere oluşturulamadı. Ad, Microsoft Foundation Class Kitaplığı tarafından oluşturulur.  
  
> [!NOTE]
>  Dönüş değeri arabellek için statik bir işaretçidir. Bu dize kaydetmek için kendisine atayın bir `CString` değişkeni.  
  
### <a name="remarks"></a>Açıklamalar  
 Microsoft Foundation Class Kitaplığı birkaç standart pencere sınıfları sizin için otomatik olarak kaydeder. Kendi pencere sınıfları kaydetmek istiyorsanız, bu işlevini çağırın.  
  
 Adı kayıtlı bir sınıf tarafından için `AfxRegisterWndClass` parametreleri yalnızca bağlıdır. Çağırırsanız `AfxRegisterWndClass` birden çok kez aynı parametrelerle bunu yalnızca bir sınıf ilk çağrıda kaydeder. Sonraki çağrılar `AfxRegisterWndClass` aynı parametrelere sahip basit zaten kayıtlı classname döndürür.  
  
 Çağırırsanız `AfxRegisterWndClass` her bir sınıf için ayrı bir pencerede sınıfı alma yerine aynı parametrelere sahip birden çok CWnd türetilmiş sınıflar için aynı pencere sınıfı her sınıf paylaşır. Bu sorunlar oluşabilir **CS_CLASSDC** sınıfı stili kullanılır. Birden çok yerine **CS_CLASSDC** pencere sınıfları, şunun biriyle **CS_CLASSDC** pencere sınıfı ve sınıf aynı DC paylaşmak kullanma tüm C++ windows. Bu sorunu önlemek için arama [AfxRegisterClass](#afxregisterclass) sınıfını.  
  
 Teknik Not bakın [TN001: pencere sınıfı kaydı](../../mfc/tn001-window-class-registration.md) pencere sınıfı kaydı hakkında daha fazla bilgi ve `AfxRegisterWndClass` işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxsetperuserregistration"></a>  AfxSetPerUserRegistration  
 Uygulama kayıt erişimi yönlendiren olup olmadığını ayarlar **HKEY_CURRENT_USER** ( **HKCU**) düğüm.  
  
```  
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bEnable`  
 `TRUE` kayıt defteri bilgileri için yönlendirilir gösterir **HKCU** düğümü; `FALSE` uygulama varsayılan düğüme kayıt defteri bilgilerini yazar gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** ( **HKCR**).  
  
### <a name="remarks"></a>Açıklamalar  

Windows Vista, genellikle kullanılan kayıt defteri erişilen uygulamalar önce **HKEY_CLASSES_ROOT** düğümü. Ancak, Windows Vista veya sonraki işletim sistemleri, bir uygulama yazmak için yükseltilmiş modda çalıştırmalısınız **HKCR**.  
  
 Bu yöntem, uygulamanızın Okuma ve kayıt defteri erişimden yönlendirerek yükseltilmiş modda çalıştırmadan kayıt defterine yazma sağlar **HKCR** için **HKCU**. Daha fazla bilgi için bkz: [bağlayıcı özellik sayfaları](../../ide/linker-property-pages.md).  
  
 Kayıt defteri yeniden yönlendirmesini devre dışı bırakırsanız, framework erişimden yönlendiren **HKCR** için **HKEY_CURRENT_USER\Software\Classes**. Yalnızca MFC ve ATL çerçeveleri tarafından yeniden yönlendirme etkilenir.  
  
 Varsayılan uygulama kayıt defterinde altına erişen **HKCR**.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxstat_.h    
  
##  <a name="afxsetresourcehandle"></a>  AfxSetResourceHandle  
 Ayarlamak için bu işlevi kullanın `HINSTANCE` uygulamanın varsayılan kaynaklar burada yüklenen belirler tanıtıcısı.  
  
```  
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);  
```  
  
### <a name="parameters"></a>Parametreler  
 `hInstResource`  
 Örneği veya modül tanıtıcısını bir. Uygulamanın kaynaklarına yüklü olan EXE ya da DLL dosyası.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  

## <a name="afxshellmanager"></a>  AfxShellManager
İşaretçi genel [Kabuk Yöneticisi](cshellmanager-class.md).  
   
### <a name="syntax"></a>Sözdizimi    
```  
CShellManager* afxShellManager;  
```  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxshellmanager.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [CShellManager Sınıfı](cshellmanager-class.md)
  
##  <a name="afxsocketinit"></a>  Afxsocketınit  
 Bu işlev çağrısı, `CWinApp::InitInstance` Windows Sockets başlatmak için geçersiz kılın.  
  
```  
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpwsaData`  
 Bir işaretçi bir [WSADATA](../../mfc/reference/wsadata-structure.md) yapısı. Varsa `lpwsaData` eşit değil `NULL`, ardından adresini `WSADATA` yapısı çağrısıyla dolduğunda `WSAStartup`. Bu işlevi de sağlar `WSACleanup` uygulama kapatılmadan önce sizin için çağrılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Statik olarak bağlantılı bir MFC uygulamasında İkincil iş parçacıklarındaki MFC yuva kullanırken çağırmalısınız `AfxSocketInit` yuva kitaplıklarını başlatma yuva kullanan her bir iş parçacığı. Varsayılan olarak, `AfxSocketInit` yalnızca birincil iş parçacığı denir.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxsock.h  

## <a name="afxusertoolsmanager"></a>  AfxUserToolsManager
İşaretçi genel [kullanıcı araçları Yöneticisi](cusertoolsmanager-class.md).  
   
### <a name="syntax"></a>Sözdizimi    
```  
CUserToolsManager* afxUserToolsManager;  
```  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxusertoolsmanager.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [CUserToolsManager Sınıfı](cusertoolsmanager-class.md)
 
  
##  <a name="afxwininit"></a>  Afxwinınit  
 MFC tarafından sağlanan tarafından bu işlev çağrılır `WinMain` parçası olarak işlevi [CWinApp](../../mfc/reference/cwinapp-class.md) MFC başlatmak için bir GUI tabanlı bir uygulama başlatma.  
  
```  
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,  
    HINSTANCE hPrevInstance,  
    LPTSTR lpCmdLine,  
    int nCmdShow);  
```  
  
### <a name="parameters"></a>Parametreler  
 `hInstance`  
 Şu anda çalışan modül işleyicisi.  
  
 *hPrevInstance*  
 Uygulamanın önceki bir örneği için bir tanıtıcı. Win32 tabanlı bir uygulama için bu parametreyi her zaman olduğu **NULL**.  
  
 `lpCmdLine`  
 Uygulama için komut satırı belirten bir null ile sonlandırılmış dize noktalarına.  
  
 `nCmdShow`  
 Nasıl bir GUI uygulaması ana penceresinde gösterilen belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir konsol uygulaması için hangi kullanmaz MFC tarafından sağlanan `WinMain` işlevini çağırmanız gerekir `AfxWinInit` MFC doğrudan başlatılamadı.  
  
 Çağırırsanız `AfxWinInit` kendiniz örneği bildirmelidir bir `CWinApp` sınıfı. Bir konsol uygulaması için kendi sınıfından türetilen değil seçebilir `CWinApp` ve bunun yerine bir örneğini kullanması `CWinApp` doğrudan. Bu, uygulamanız için tüm işlevselliği uygulamanızda bırakın karar verirseniz uygun bir tekniktir **ana**.  
  
> [!NOTE]
>  Bir derleme için bir etkinleştirme bağlamı oluşturduğunda, MFC kullanıcı modülü tarafından sağlanan bir bildirim kaynağı kullanır. Etkinleştirme bağlamı oluşturulan `AfxWinInit`. Daha fazla bilgi için bkz: [MFC modül durumunda etkinleştirme bağlamları desteği](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]  

### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)   
 [CWinApp Sınıfı](../../mfc/reference/cwinapp-class.md)
