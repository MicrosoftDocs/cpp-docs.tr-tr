---
title: Normal MFC DLL'lerinde veritabanı, OLE ve yuva MFC uzantısı DLL'leri kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b8fe2c57991ffd15f135fab39c185b6a68f2e9c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701999"
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>Normal MFC DLL'lerinde veritabanı, OLE ve yuva MFC uzantısı DLL'leri kullanma

MFC uzantısı DLL içine bağlı değilse, bir MFC uzantılı DLL dosyasından Normal MFC DLL'SİNİN kullanırken **CDynLinkLibrary** nesne zinciri Normal MFC DLL'SİNİN, bir veya daha fazla ilgili sorunlarını bir dizi çalışabilir. MFC veritabanı, OLE ve yuva hata ayıklama sürümleri desteklediğinden DLL'leri MFC uzantısı DLL'leri olarak uygulanır, açıkça herhangi birini kendi MFC uzantısı DLL'leri kullanmadığınız olsa bile bu MFC kullanıyorsanız benzer sorunlara özelliklerini görebilirsiniz. Bazı Belirtiler şunlardır:

- Ne zaman sınıf türünde bir nesnenin serisini kaldırma girişimi izin ver tanımlanan MFC uzantısı DLL, ileti "Uyarı: arşivden CYourClass yüklenemiyor. Sınıf tanımlı değil." İzleme hata ayıklama penceresine ve nesneyi serileştirmek için başarısız görünür.

- Hatalı sınıfı gösteren bir özel durum.

- MFC uzantısı DLL depolanan kaynakları başarısız olduğundan `AfxFindResourceHandle` döndürür **NULL** veya yanlış kaynak işleyicisi.

- `DllGetClassObject`, `DllCanUnloadNow`ve `UpdateRegistry`, `Revoke`, `RevokeAll`, ve `RegisterAll` üye işlevleri `COleObjectFactory` MFC uzantısı DLL içinde tanımlanan bir sınıf üreteci bulmada başarısız olur.

- `AfxDoForAllClasses` MFC uzantısı DLL içindeki tüm sınıflar için geçerli değildir.

- Standart MFC veritabanı, yuva veya OLE kaynakları yüklenemedi. Örneğin, **AfxLoadString**(**AFX_IDP_SQL_CONNECT_FAIL**) Normal MFC DLL'SİNİN MFC veritabanı sınıfları düzgün bir şekilde kullanırken boş bir dize döndürür.

Bu soruna çözüm oluşturmak ve bir MFC uzantısı oluşturur DLL başlatma işlevinde vermek için olan bir **CDynLinkLibrary** nesne. Tam olarak MFC uzantısı DLL kullanan normal her MFC DLL sonra bu başlatma işlevi çağırın.

## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>MFC OLE, MFC veritabanı (veya DAO), veya MFC yuva desteği

Bir MFC OLE, MFC veritabanı (veya DAO) kullanarak ya da MFC yuva Normal MFC DLL içinde sırasıyla desteği, MFC hata ayıklama MFC uzantısı DLL'leri MFCOxxD.dll MFCDxxD.dll ve (xx sürüm numarasıdır) MFCNxxD.dll otomatik olarak bağlanır. Önceden tanımlanmış başlatma işlevinin her kullanmakta olduğunuz bu DLL'ler için çağırmanız gerekir.

Veritabanı desteği için bir çağrı ekleyin `AfxDbInitModule` Normal MFC DLL için `CWinApp::InitInstance` işlevi. Bu çağrı herhangi bir temel sınıf çağrısından önce oluşur veya MFCDxxD.dll erişir kod eklenen tüm emin olun. Bu işlev, parametre almayan ve void döndürür.

OLE desteği için bir çağrı ekleyin `AfxOleInitModule` Normal MFC DLL için `CWinApp::InitInstance`. Unutmayın **COleControlModule InitInstance** işlev çağrılarında `AfxOleInitModule` zaten, bunu bir OLE denetim oluşturma ve kullanıyorsanız `COleControlModule`, bu çağrıyı eklememelisiniz `AfxOleInitModule`.

Yuva desteği için bir çağrı ekleyin `AfxNetInitModule` Normal MFC DLL için `CWinApp::InitInstance`.

MFC DLL yayın oluşturur ve uygulamaları Yuvalar, veritabanı için ayrı DLL'leri kullanmayın veya OLE desteği unutmayın. Ancak, yayın modunda bu başlatma işlevleri çağırmak güvenlidir.

## <a name="cdynlinklibrary-objects"></a>CDynLinkLibrary Nesneleri

MFC her konunun başında belirtildiği işlemleri sırasında istenen değer veya nesne için arama yapmak gerekir. Örneğin, seri durumundan çıkarma sırasında MFC uygun kendi çalışma zamanı sınıf ile arşiv nesneleri eşleştirmek için tüm kullanılabilir çalışma zamanı sınıflar arama yapmanız gerekir.

Bu arama bir parçası olarak MFC kullanımda tüm MFC uzantısı DLL'leri zinciri walking tarafından arar **CDynLinkLibrary** nesneleri. **CDynLinkLibrary** nesneler bir zincirine yapım sırasında otomatik olarak ekler ve her MFC uzantısı DLL başlatma sırasında sırayla oluşturulur. Ayrıca, her bir modüle (uygulama veya Normal MFC DLL'SİNİN) kendi zincirine sahip **CDynLinkLibrary** nesneleri.

Bir MFC uzantılı DLL içine kablolu için bir **CDynLinkLibrary** zinciri gerekir oluşturma bir **CDynLinkLibrary** MFC uzantısı DLL kullanan her bir modüle bağlamında nesne. Bu nedenle, bir MFC uzantılı DLL normal MFC DLL'leri kullanılacak hedefleyecekse, onu oluşturan dışarı aktarılan başlatma işlev sağlamalısınız bir **CDynLinkLibrary** nesne. MFC uzantısı kullanan her Normal MFC DLL'SİNİN DLL dışarı aktarılan başlatma işlevi çağırmanız gerekir.

Bir MFC uzantılı DLL yalnızca bir MFC uygulaması (.exe) ve hiçbir zaman Normal MFC DLL'SİNİN kullanılacak sonra oluşturmak için yeterli **CDynLinkLibrary** MFC uzantı DLL nesnesinde `DllMain`. MFC DLL Sihirbazı MFC uzantısı DLL kodun ne yaptığını budur. Bir MFC uzantılı DLL örtülü olarak yüklenirken `DllMain` yükler ve uygulama başlamadan önce yürütülür. Tüm **CDynLinkLibrary** oluşturma kablolu bir varsayılan zincirine MFC DLL için bir MFC uygulaması ayırır.

Birden çok sağlamak için kötü bir fikir olduğunu unutmayın **CDynLinkLibrary** nesnenin bir MFC uzantısı DLL, herhangi bir zincirde MFC uzantısı DLL özellikle dinamik olarak bellekten olacaksa. Başlatma işlevinin herhangi bir modülden birden çok kez çağırmanız gerekmez.

## <a name="sample-code"></a>Örnek kod

Bu örnek kod, Normal MFC DLL, MFC uzantısı DLL örtük olarak bağlama varsayar. Bu, Normal MFC DLL'yi oluştururken MFC uzantısı DLL içeri aktarma kitaplığına (.lib) bağlantı kurularak gerçekleştirilir.

Aşağıdaki satırları MFC uzantısı DLL kaynakta olmalıdır:

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

Dışarı aktardığınızdan emin olun **InitYourExtDLL** işlevi. Bu yapılabilir kullanarak **__declspec(dllexport)** ya da gösterildiği gibi DLL'nin .def dosyasında:

```
// YourExtDLL.Def:
LIBRARY      YOUREXTDLL
CODE         PRELOAD MOVEABLE DISCARDABLE
DATA         PRELOAD SINGLE
EXPORTS
    InitYourExtDLL
```

Bir çağrı ekleyin `InitInstance` üyesi `CWinApp`-türetilmiş MFC uzantısı DLL kullanarak her bir Normal MFC DLL'SİNİN nesnesinde:

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

- [Bir MFC uzantılı DLL başlatma](../build/run-time-library-behavior.md#initializing-extension-dlls)

- [Normal MFC DLL'leri Başlat](../build/run-time-library-behavior.md#initializing-regular-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC uzantısı DLL’leri](../build/extension-dlls.md)

- [Statik Olarak MFC'ye Bağlı Normal MFC DLL'leri](../build/regular-dlls-statically-linked-to-mfc.md)

- [Dinamik Olarak MFC'ye Bağlı Normal MFC DLL'leri](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [Bir DLL'in bir parçası MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [MFC'nin DLL sürümü](../mfc/tn033-dll-version-of-mfc.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC uzantısı DLL’leri](../build/extension-dlls.md)