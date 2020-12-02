---
title: Normal MFC DLL 'Lerinde Database, OLE ve Sockets MFC uzantı dll 'Lerini kullanma
description: Normal MFC DLL 'Lerinde Database, OLE ve Sockets MFC uzantı dll 'Lerinin nasıl kullanılacağını gösterir.
ms.date: 11/30/2020
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.openlocfilehash: a28e80c4d554a86f45f708e661382ee4a54eca9e
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440275"
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>Normal MFC DLL 'Lerinde Database, OLE ve Sockets MFC uzantı dll 'Lerini kullanma

Normal bir MFC DLL 'den MFC uzantı DLL 'si kullanılırken, MFC uzantı DLL 'SI `CDynLinkLibrary` normal MFC DLL 'nin nesne zincirine kablolu değilse, bir veya daha fazla ilgili sorun ile karşılaşabilirsiniz. MFC veritabanı, OLE ve yuva desteği dll 'lerinin hata ayıklama sürümleri MFC uzantı dll 'leri olarak uygulandığından, kendi MFC uzantı dll 'lerinizi açıkça kullanmadığınız halde bu MFC özelliklerini kullanıyorsanız benzer sorunlar görebilirsiniz. Bazı belirtiler şunlardır:

- MFC uzantı DLL 'sinde tanımlı bir sınıf türünün bir nesnesinin serisini kaldırmaya çalışırken, "Uyarı: CYourClass from Arşiv ' e yüklenemez. Sınıf tanımlı değil. " Izleme hata ayıklama penceresinde görünür ve nesne seri hale getirilemez.

- Hatalı sınıfı gösteren bir özel durum ortaya çıkabilir.

- MFC uzantı DLL 'sinde depolanan kaynaklar, `AfxFindResourceHandle` döndürdüğü `NULL` veya hatalı bir kaynak tanıtıcısı nedeniyle yüklenemedi.

- `DllGetClassObject`, `DllCanUnloadNow` , ve,, `UpdateRegistry` ve ' nin,,, `Revoke` `RevokeAll` ve `RegisterAll` üye işlevleri, `COleObjectFactory` MFC uzantı dll 'de tanımlanan bir sınıf fabrikasını bulamıyor.

- `AfxDoForAllClasses` MFC uzantı DLL dosyasındaki hiçbir sınıf için çalışmaz.

- Standart MFC veritabanı, yuvalar veya OLE kaynakları yüklemede başarısız olur. Örneğin, `AfxLoadString(AFX_IDP_SQL_CONNECT_FAIL)` normal MFC DLL MFC veritabanı sınıflarını düzgün şekilde kullanırken bile boş bir dize döndürür.

Bu sorunlara yönelik çözüm, MFC uzantı DLL 'sinde bir nesne oluşturan bir başlatma işlevi oluşturmaktır ve dışarı aktarmasıdır `CDynLinkLibrary` . Bu başlatma işlevini MFC uzantısı DLL kullanan her normal MFC DLL 'den tam olarak bir kez çağırın.

## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>MFC OLE, MFC veritabanı (veya DAO) veya MFC Yuvaları desteği

MFC OLE, MFC veritabanı (veya DAO) veya normal MFC DLL 'inizdeki MFC Yuvaları desteğini kullanıyorsanız, MFC hata ayıklama MFC uzantı dll 'Leri, *`MFCOxxD.dll`* *`MFCDxxD.dll`* ve *`MFCNxxD.dll`* ( *xx* sürüm numarasıdır) otomatik olarak bağlanır. Kullanmakta olduğunuz dll 'lerin her biri için önceden tanımlanmış bir başlatma işlevi çağırın:

- Veritabanı desteği için, `AfxDbInitModule` kendi işlevinde normal MFC DLL 'nize bir çağrı ekleyin `CWinApp::InitInstance` . Bu çağrının herhangi bir temel sınıf çağrısından veya öğesine erişen eklenen bir koddan önce olduğundan emin olun *`MFCDxxD.dll`* . Bu işlev hiçbir parametre alıp döndürmez `void` .

- OLE desteği için, `AfxOleInitModule` normal MFC DLL 'nize bu işleve bir çağrı ekleyin `CWinApp::InitInstance` . `COleControlModule::InitInstance`İşlevi zaten çağırır `AfxOleInitModule` , bu nedenle bir OLE denetimi oluşturuyorsanız ve kullanıyorsanız `COleControlModule` , bu çağrıyı öğesine eklememelisiniz `AfxOleInitModule` .

- Yuva desteği için, `AfxNetInitModule` içinde normal MFC DLL 'nize bir çağrı ekleyin `CWinApp::InitInstance` .

MFC DLL 'Leri ve uygulamaları yayın derlemeleri veritabanı, yuvalar veya OLE desteği için ayrı dll kullanmaz. Ancak, bu başlatma işlevlerini yayın modunda çağırmak güvenlidir.

## <a name="cdynlinklibrary-objects"></a>CDynLinkLibrary nesneleri

Bu makalenin başlangıcında bahsedilen her işlem sırasında, MFC 'nin belirli bir değeri veya nesneyi araması gerekir. Örneğin, seri durumdan çıkarma sırasında, arşivdeki nesneleri uygun çalışma zamanı sınıfıyla eşleştirmek için MFC 'nin şu anda kullanılabilir olan tüm çalışma zamanı sınıflarını aramasını gerekir.

Bu aramaların bir parçası olarak MFC, bir nesne zinciri yürüyerek kullanılan tüm MFC uzantı dll 'Lerini tarar `CDynLinkLibrary` . `CDynLinkLibrary` nesneler, oluşturma sırasında bir zincire otomatik olarak eklenir ve başlatma sırasında sırayla her MFC uzantı DLL tarafından oluşturulur. Her modülün (uygulama veya normal MFC DLL) kendi nesne zinciri vardır `CDynLinkLibrary` .

Bir MFC uzantısı DLL 'inin bir zincirine kablolu olması için `CDynLinkLibrary` `CDynLinkLibrary` MFC uzantı dll 'sini kullanan her modülün bağlamında bir nesne oluşturması gerekir. MFC uzantı DLL 'sini normal MFC DLL 'Lerinde kullanmak için uzantı DLL, bir nesne oluşturan bir içe aktarılmış başlatma işlevi sağlamalıdır `CDynLinkLibrary` . MFC uzantısı DLL kullanan her normal MFC DLL 'nin, aktarılmış başlatma işlevini çağırması gerekir.

Bir MFC uygulamasından yalnızca bir MFC uzantı DLL 'SI kullanacaksanız ve normal bir MFC DLL 'den hiç kullanabileceksiniz, `CDynLinkLibrary` NESNEYI MFC UZANTıSı dll işlevinde oluşturmak yeterlidir `DllMain` . MFC DLL Sihirbazı MFC uzantı DLL kodunun yaptığı şeydir. MFC uzantı DLL 'sini örtülü olarak yüklerken `DllMain` uygulama başlamadan önce yükler ve yürütülür. Her `CDynLinkLibrary` oluşturma, MFC DLL 'sinin BIR MFC uygulaması için ayırdığından bir varsayılan zincire bağlanır.

Tek bir `CDynLinkLibrary` zincirde tek BIR MFC UZANTıSı dll 'sinden birden fazla nesnenin olması kötü bir fikirdir. MFC uzantı DLL 'SI bellekten dinamik olarak kaldırılabiliyorsa, bu durum özellikle doğrudur. Başlatma işlevini herhangi bir modülden birden çok kez çağırmayın.

## <a name="sample-code"></a>Örnek Kod

Bu örnek kod, normal MFC DLL 'nin MFC uzantı DLL 'sine örtük olarak bağlantı aldığını varsayar. Örtük olarak bağlamak için, normal MFC DLL 'yi oluştururken MFC uzantı DLL 'inin içeri aktarma kitaplığına (LIB dosyası) bağlanın.

Aşağıdaki satırlar, MFC uzantı DLL 'sinin kaynağında olmalıdır:

```cpp
// YourExtDLL.cpp:

// standard MFC extension DLL routines
#include "afxdllx.h"

static AFX_EXTENSION_MODULE extensionDLL;

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

**InitYourExtDLL** işlevini dışarı aktardığınızdan emin olun. **`__declspec(dllexport)`** Burada gösterildiği gibi, dll 'niz IÇIN Def dosyasında kullanabilirsiniz veya dışarı aktarabilirsiniz:

```def
// YourExtDLL.Def:
LIBRARY      YOUREXTDLL
CODE         PRELOAD MOVEABLE DISCARDABLE
DATA         PRELOAD SINGLE
EXPORTS
    InitYourExtDLL
```

`InitInstance` `CWinApp` MFC uzantı dll 'ini kullanarak her normal MFC DLL 'de türetilen nesnenin üyesine bir çağrı ekleyin:

```cpp
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

- [MFC uzantı DLL 'sini başlatma](run-time-library-behavior.md#initializing-extension-dlls)

- [Normal MFC DLL 'Leri başlatma](run-time-library-behavior.md#initializing-regular-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC uzantısı DLL’leri](extension-dlls.md)

- [MFC 'ye statik olarak bağlı normal MFC DLL 'Leri](regular-dlls-statically-linked-to-mfc.md)

- [MFC 'ye dinamik olarak bağlı normal MFC DLL 'Leri](regular-dlls-dynamically-linked-to-mfc.md)

- [DLL 'nin bir parçası olarak MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [MFC 'nin DLL sürümü](../mfc/tn033-dll-version-of-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC uzantısı DLL’leri](extension-dlls.md)
