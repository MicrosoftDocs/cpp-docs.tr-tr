---
title: Statik olarak MFC'ye bağlı normal MFC DLL'leri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular MFC DLLs [C++]
- DLLs [C++], regular
- USRDLLs
- USRDLLs, statically linked to MFC
- statically linked DLLs [C++]
- regular MFC DLLs [C++], statically linked to MFC
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c48fdfb0b10541c1643ec49038e29cfa60c633d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383754"
---
# <a name="regular-mfc-dlls-statically-linked-to-mfc"></a>Statik olarak MFC'ye bağlı normal MFC DLL'leri
MFC DLL statik olarak MFC'ye bağlı normal MFC'yi dahili olarak kullanan DLL'dir ve MFC veya MFC dışı çalıştırılabilirler tarafından DLL dışarı aktarılan işlevler çağrılabilir. Adı açıklandığı gibi bu tür DLL MFC statik bağlantı kitaplık sürümü kullanılarak oluşturulur. İşlevler, genellikle bir normal standart C arabirimi kullanan MFC DLL dışarı aktarılır. Örnek örneği nasıl yazma, yapı ve normal bir MFC DLL kullanmak için bkz: [ile ilgili](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap).  
  
 Visual C++ belgelerinde USRDLL terimi artık kullanılmayan unutmayın. Statik olarak MFC'ye bağlı normal bir MFC DLL önceki USRDLL ile aynı özelliklere sahiptir.  
  
 Statik olarak MFC'ye, bağlı normal bir MFC DLL, aşağıdaki özelliklere sahiptir:  
  
-   İstemci yürütülebilir DLL'lerin (C, C++, Pascal, Visual Basic vb.); kullanımını destekleyen herhangi bir dilde yazılabilir MFC uygulaması olarak yok.  
  
-   DLL uygulamaları tarafından kullanılan aynı MFC statik bağlantı kitaplıkları bağlayabilirsiniz. Artık statik bağlantı kitaplıkları DLL'ler için ayrı bir sürümü yok.  
  
-   MFC 4.0 sürümünden önce statik olarak MFC'ye bağlı normal MFC DLL işlevleri aynı türde USRDLL sağlanan. Visual C++ itibariyle sürüm 4.0 USRDLL terimi artık kullanılmıyor.  
  
 Statik olarak MFC'ye, bağlı normal MFC DLL aşağıdaki gereksinimlere sahiptir:  
  
-   Bu tür DLL türetilmiş bir sınıf örneği oluşturmalıdır `CWinApp`.  
  
-   Bu tür DLL kullanır `DllMain` MFC tarafından sağlanan. Tüm DLL özgü başlatma kodda yerleştirin `InitInstance` üye işlevine ve sonlandırma kodunu `ExitInstance` normal bir MFC uygulaması olduğu gibi.  
  
-   USRDLL'in artık kullanılmamasına rağmen hala tanımlamalısınız "**_USRDLL**" derleyici komut satırında. Bu tanım hangi bildirimlerin çekilmesini MFC başlık dosyalarından belirler.  
  
 Normal MFC DLL'leri olmalıdır bir `CWinApp`-türetilmiş sınıf ve o uygulama sınıfın tek bir nesne bir MFC uygulamalarında olduğu gibi. Ancak, `CWinApp` DLL nesnesinin yaptığı gibi bir ana ileti Pompalama yok `CWinApp` bir uygulama nesnesi.  
  
 Unutmayın `CWinApp::Run` mekanizması uygulamanın ana ileti göndericisi olduğundan bir DLL için uygulanmaz. DLL kalıcı olmayan iletişim kutuları açılır ya da kendi ana penceresi varsa, uygulamanın ana ileti göndericisi sırayla çağıran DLL'den dışarı aktarılmış bir yordam çağırmalıdır `CWinApp::PreTranslateMessage` üye işlevi DLL uygulama nesnesi.  
  
 Bu işlev bir örnek için ile ilgili örnek bakın.  
  
 Simgeler genellikle bir normal standart C arabirimi kullanan MFC DLL dışarı aktarılır. Normal bir MFC DLL'den dışarı aktarılan bir işlevin bildirimi şunun gibi görünür:  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 Normal bir MFC DLL içindeki tüm bellek ayırmaları DLL kalmalı; DLL için geçirin veya arama yürütülebilir dosyadan aşağıdakilerden herhangi birini almak gerekir:  
  
-   MFC nesnelerine işaretçiler  
  
-   MFC tarafından ayrılan bellek işaretçiler  
  
 Yukarıdakilerin tümü yapın veya arama yürütülebilir ve DLL arasında MFC'den türetilen nesneleri geçirmek gereken gerekiyorsa, MFC uzantı DLL'si yapılandırmanız gerekir.  
  
 Yalnızca verilerin bir kopyasını yaparsanız işaretçileri ayrılan bellek C çalışma zamanı kitaplıkları tarafından bir uygulama ve DLL arasında geçirmek güvenlidir. Değil silmeli veya bu işaretçileri yeniden boyutlandırmak veya bellek kopyasını yapmadan kullanın.  
  
 Statik olarak MFC'ye bağlı bir DLL da dinamik paylaşılan MFC DLL'leri bağlayamazsınız. Statik olarak MFC'ye bağlı bir DLL herhangi bir DLL gibi bir uygulama dinamik olarak bağlı; uygulamalar için diğer DLL gibi bağlayın.  
  
 Standart MFC statik bağlantı kitaplıkları açıklanan kurala göre adlandırılır [MFC DLL'leri için adlandırma kurallarını](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions). Ancak, MFC sürüm 3.0 ve üstü ile artık bağlayıcıya sonrasıyla istediğiniz MFC kitaplık sürümünü el ile belirtmek gerekli değildir. Bunun yerine, MFC başlık dosyaları otomatik olarak gibi temel alınarak önişlemci içinde bağlamak için MFC Kitaplığı doğru sürümü tanımlar belirlemek  **\_hata ayıklama** veya **_UNICODE**. MFC başlık dosyaları, belirli bir MFC kitaplık sürümünü bağlamak için DEFAULTLIB ekleyin.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [Normal MFC DLL'leri başlatma](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Bir DLL'in bir parçası MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [Normal MFC DLL'lerinde Veritabanı, OLE ve Yuva MFC uzantısı DLL'leri Kullanma](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [MFC DLL oluşturma](../mfc/reference/mfc-dll-wizard.md)  
  
-   [Dinamik Olarak MFC'ye Bağlı Normal MFC DLL'leri](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC uzantısı DLL’leri](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL Türleri](../build/kinds-of-dlls.md)