---
title: "Normal MFC DLL'lerde veritabanı, OLE ve yuva MFC uzantı DLL'leri kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0042dd5dc6049447868cf5ca5ea1112b3695f3a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>Normal MFC DLL'lerde veritabanı, OLE ve yuva MFC uzantı DLL'leri kullanma
MFC uzantı DLL içine bağlı değilse, MFC uzantı DLL normal bir MFC DLL dosyasından kullanırken **CDynLinkLibrary** nesne zinciri Normal MFC DLL bir veya daha fazla ilgili sorunların bir dizi çalışabilir. MFC veritabanı, OLE ve yuva hata ayıklama sürümleri desteklemediğinden DLL'leri MFC uzantı DLL'leri uygulanan, açıkça kendi MFC uzantı DLL'leri hiçbirini kullanmadığınız olsa bile bu MFC kullanıyorsanız benzer sorunlar özelliklerini görebilirsiniz. Bazı Belirtiler şunlardır:  
  
-   Ne zaman sınıfının bir türdeki bir nesne seri durumdan çalışılıyor izin ver tanımlanan MFC uzantı DLL'si, ileti "Uyarı: CYourClass arşivden yüklenemiyor. Sınıf tanımlı değil." İzleme hata ayıklama penceresi ve nesneyi serileştirmek için başarısız görünür.  
  
-   Kötü sınıfı gösteren bir özel durum.  
  
-   MFC uzantı DLL'si saklanan kaynaklar başarısız oluştuğundan `AfxFindResourceHandle` döndürür **NULL** veya yanlış kaynak işleyicisi.  
  
-   `DllGetClassObject`, `DllCanUnloadNow`ve `UpdateRegistry`, `Revoke`, `RevokeAll`, ve `RegisterAll` üye işlevlerini `COleObjectFactory` MFC uzantı DLL'si tanımlı bir sınıf fabrikası bulmak başarısız.  
  
-   `AfxDoForAllClasses`MFC uzantı DLL'si her sınıf için çalışmaz.  
  
-   Standart MFC veritabanı, yuva veya OLE kaynakları yüklenemedi. Örneğin, **AfxLoadString**(**AFX_IDP_SQL_CONNECT_FAIL**) Normal MFC DLL MFC veritabanı sınıfları düzgün kullanılırken boş bir dize döndürür.  
  
 Bu soruna çözüm oluşturmak ve MFC uzantı oluşturur DLL başlatma işlevinde vermek için olan bir **CDynLinkLibrary** nesnesi. Tam olarak MFC uzantı DLL'si kullanan her Normal MFC DLL sonra bu başlatma işlevini çağırın.  
  
## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>MFC OLE, MFC veritabanı (veya DAO), veya MFC yuva desteği  
 Her MFC OLE, MFC veritabanı (veya DAO) kullanarak veya MFC yuva Normal MFC DLL dosyanızda, sırasıyla desteği, MFC hata ayıklama MFC uzantı DLL'leri MFCOxxD.dll, MFCDxxD.dll ve MFCNxxD.dll (xx sürüm numarasıdır) otomatik olarak bağlanır. Önceden tanımlanmış başlatma işlevini her kullanmakta olduğunuz bu DLL'ler için çağırmanız gerekir.  
  
 Veritabanı desteği için bir çağrı ekleyin `AfxDbInitModule` Normal MFC DLL için `CWinApp::InitInstance` işlevi. Bu çağrı önce herhangi bir temel sınıf çağrısına oluşur veya MFCDxxD.dll erişen kodu eklenen tüm emin olun. Bu işlev, parametre almayan ve void döndürür.  
  
 OLE desteği için bir çağrı ekleyin `AfxOleInitModule` Normal MFC DLL için `CWinApp::InitInstance`. Unutmayın **COleControlModule InitInstance** işlev çağrıları `AfxOleInitModule` zaten, bunu bir OLE denetimi oluşturuyorsanız ve kullanıyorsanız `COleControlModule`, bu çağrıyı eklememelisiniz `AfxOleInitModule`.  
  
 Yuvalar desteği için bir çağrı ekleyin `AfxNetInitModule` Normal MFC DLL için `CWinApp::InitInstance`.  
  
 MFC DLL sürüm oluşturur ve uygulamaları yuvaları, veritabanı için ayrı DLL'leri kullanmayın veya OLE desteği unutmayın. Ancak, yayın modunda bu başlatma işlevleri çağırmak güvenlidir.  
  
## <a name="cdynlinklibrary-objects"></a>CDynLinkLibrary Nesneleri  
 İstenen değeri veya nesne için arama her bu konunun başında bahsedilen işlemleri sırasında MFC gerekir. Örneğin, seri durumdan çıkarma sırasında MFC nesneleri arşivindeki kendi uygun çalışma zamanı sınıfı ile eşleşmesi için tüm şu anda çalışma zamanı sınıflarıyla arama gerekir.  
  
 Bu aramalar bir parçası olarak MFC kullanımdaki tüm MFC uzantı DLL'leri zinciri adım adım ilerlemenizi sağlayarak arar **CDynLinkLibrary** nesneleri. **CDynLinkLibrary** nesneleri bir zinciri kendi oluşturma sırasında otomatik olarak ekleyin ve her MFC uzantı DLL'si sırayla başlatma sırasında oluşturulur. Ayrıca, her modül (uygulama veya Normal MFC DLL) kendi zincirine sahip **CDynLinkLibrary** nesneleri.  
  
 MFC uzantı DLL'si içine kablolu için bir **CDynLinkLibrary** zinciri, onu oluşturmalısınız bir **CDynLinkLibrary** MFC uzantı DLL'si kullanan her bir modüle bağlamda nesnesi. MFC uzantı, Normal MFC DLL'den kullanılacak DLL olacaksa, bu nedenle, onu oluşturan bir dışarı aktarılan başlatma işlevi sağlamanız gerekir bir **CDynLinkLibrary** nesnesi. MFC uzantı kullanan her Normal MFC DLL DLL dışarı aktarılmış bir başlangıç işlevini çağırmanız gerekir.  
  
 MFC uzantı DLL yalnızca bir MFC uygulamasından (.exe) ve hiçbir zaman normal DLL'den MFC kullanılacak geçiyor sonra oluşturmak yeterli **CDynLinkLibrary** MFC uzantının DLL nesnesinde `DllMain`. MFC DLL Sihirbazı MFC uzantı DLL kodunun yaptığı budur. MFC uzantı DLL'si dolaylı olarak yüklerken, `DllMain` yükler ve uygulama başlamadan önce yürütülür. Tüm **CDynLinkLibrary** oluşturmaları kablolu varsayılan zincire MFC DLL bir MFC uygulaması için ayırır.  
  
 Birden çok sağlamak için kötü bir fikir olduğuna dikkat edin **CDynLinkLibrary** nesneleri bir MFC uzantı DLL herhangi bir zincirde özellikle MFC uzantı DLL'si dinamik olarak bellekten olarak olacaksa. Başlatma işlevi herhangi bir modülden birden çok kez çağırmayın.  
  
## <a name="sample-code"></a>Örnek kod  
 Bu örnek kod, Normal MFC DLL MFC uzantı DLL'si örtük olarak bağlama varsayar. Bu, Normal MFC DLL oluşturulurken MFC uzantı DLL içeri aktarma kitaplığına (.lib) kurularak gerçekleştirilir.  
  
 Aşağıdaki satırları MFC uzantı DLL'si kaynağında olması gerekir:  
  
```  
// YourExtDLL.cpp:  
  
// standard MFC extension DLL routines  
#include "afxdllx.h"  
  
static AFX_EXTENSION_MODULE NEAR extensionDLL = { NULL, NULL };  
  
extern "C" int APIENTRY  
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)  
{  
    if (dwReason == DLL_PROCESS_ATTACH)  
    {  
        // MFC extension DLL one-time initialization  
        if (!AfxInitExtensionModule(extensionDLL, hInstance))  
           return 0;  
    }  
    return 1;   // ok  
}  
  
// Exported DLL initialization is run in context of  
// application or regular MFC DLL  
extern "C" void WINAPI InitYourExtDLL()  
{  
    // create a new CDynLinkLibrary for this app  
    new CDynLinkLibrary(extensionDLL);  
  
    // add other initialization here  
}  
```  
  
 Dışarı aktardığınızdan emin olun **InitYourExtDLL** işlevi. Bu yapılabilir kullanarak **__declspec(dllexport)** veya şekilde DLL .def dosyası:  
  
```  
// YourExtDLL.Def:  
LIBRARY      YOUREXTDLL  
CODE         PRELOAD MOVEABLE DISCARDABLE  
DATA         PRELOAD SINGLE  
EXPORTS  
    InitYourExtDLL  
```  
  
 Bir çağrı ekleyin `InitInstance` üyesi `CWinApp`-normal her MFC DLL MFC uzantı DLL'si kullananlar nesnesinde türetilmiş:  
  
```  
// YourRegularDLL.cpp:  
  
class CYourRegularDLL : public CWinApp  
{  
public:  
    virtual BOOL InitInstance(); // Initialization  
    virtual int ExitInstance();  // Termination  
  
    // nothing special for the constructor  
    CYourRegularDLL(LPCTSTR pszAppName) : CWinApp(pszAppName) { }  
};  
  
BOOL CYourRegularDLL::InitInstance()  
{  
    // any DLL initialization goes here  
    TRACE0("YOUR regular MFC DLL initializing\n");  
  
    // wire any MFC extension DLLs into CDynLinkLibrary chain  
    InitYourExtDLL();  
  
    return TRUE;  
}  
```  
  
### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [MFC uzantı DLL başlatma](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
-   [Normal MFC DLL'leri başlatma](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [MFC uzantısı DLL’leri](../build/extension-dlls.md)  
  
-   [Statik Olarak MFC'ye Bağlı Normal MFC DLL'leri](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Dinamik Olarak MFC'ye Bağlı Normal MFC DLL'leri](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Bir DLL'in bir parçası MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [MFC'nin DLL sürümü](../mfc/tn033-dll-version-of-mfc.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC uzantısı DLL’leri](../build/extension-dlls.md)