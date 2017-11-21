---
title: "Dinamik olarak MFC'ye bağlı normal MFC DLL'leri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- AFX_MANAGE_STATE macro
- DLLs [C++], regular
- shared DLL versions [C++]
- dynamically linked DLLs [C++]
ms.assetid: b4f7ab92-8723-42a5-890e-214f4e29dcd0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9c1835ad660c9dbb9f8e4b43dbf697ea960f82ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="regular-mfc-dlls-dynamically-linked-to-mfc"></a>Dinamik olarak MFC'ye bağlı normal MFC DLL'leri
MFC DLL dinamik olarak MFC'ye bağlı normal MFC'yi dahili olarak kullanan DLL'dir ve MFC veya MFC dışı çalıştırılabilirler tarafından DLL dışarı aktarılan işlevler çağrılabilir. Adı açıklandığı gibi bu tür DLL MFC (olarak da bilinen MFC paylaşılan sürüm) dinamik bağlantı kitaplığı sürümü kullanılarak oluşturulmuştur. İşlevler, genellikle bir normal standart C arabirimi kullanan MFC DLL dışarı aktarılır.  
  
 Eklemelisiniz `AFX_MANAGE_STATE` makrosu geçerli modül durumunu DLL için ayarlamak amacıyla MFC'ye dinamik olarak bağlantı Normal MFC DLL'leri dışarı aktarılan işlevler başındaki. Bu, aşağıdaki kod satırını DLL'den dışarı aktarılan işlevlerin başına ekleyerek yapılır:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 Dinamik olarak MFC'ye bağlı bir Normal MFC DLL, aşağıdaki özelliklere sahiptir:  
  
-   Yeni bir Visual C++ 4.0 tarafından sunulan DLL türü budur.  
  
-   İstemci yürütülebilir DLL'lerin (C, C++, Pascal, Visual Basic vb.); kullanımını destekleyen herhangi bir dilde yazılabilir MFC uygulaması olarak yok.  
  
-   Statik olarak bağlı normal MFC DLL, bu tür DLL MFC DLL (paylaşılan MFC DLL olarak da bilinir) dinamik olarak bağlanır.  
  
-   Bu tür DLL'ye bağlı MFC içeri aktarma kitaplığını MFC uzantı DLL'leri ya MFC DLL kullanan uygulamalar için kullanılanla aynıdır: MFCxx (D) .lib.  
  
 Normal MFC DLL, dinamik olarak MFC'ye bağlı aşağıdaki gereksinimlere sahiptir:  
  
-   Bu DLL'ler ile derlenir **_AFXDLL** tanımlanan, olduğu gibi MFC DLL dinamik olarak bağlı çalıştırılabilir. Ancak **_USRDLL** Ayrıca, statik olarak MFC'ye bağlı normal bir MFC DLL gibi tanımlanır.  
  
-   Bu tür DLL oluşturmalıdır bir `CWinApp`-türetilmiş sınıf.  
  
-   Bu tür DLL kullanır `DllMain` MFC tarafından sağlanan. Tüm DLL özgü başlatma kodda yerleştirin `InitInstance` üye işlevine ve sonlandırma kodunu `ExitInstance` normal bir MFC uygulaması olduğu gibi.  
  
 Bu tür DLL MFC dinamik bağlantı kitaplığı sürümünü kullandığından, geçerli modül durumunu DLL için olana açıkça ayarlamanız gerekir. Bunu yapmak için kullanın [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) makrosu her işlev başındaki DLL'den dışarı.  
  
 Normal MFC DLL'leri olmalıdır bir `CWinApp`-türetilmiş sınıf ve o uygulama sınıfın tek bir nesne bir MFC uygulamalarında olduğu gibi. Ancak, `CWinApp` DLL nesnesinin yaptığı gibi bir ana ileti Pompalama yok `CWinApp` bir uygulama nesnesi.  
  
 Unutmayın `CWinApp::Run` mekanizması uygulamanın ana ileti göndericisi olduğundan bir DLL için uygulanmaz. DLL kalıcı olmayan iletişim ya da kendi ana penceresi varsa, uygulamanızın ana ileti göndericisi çağıran DLL dışarı aktarılan bir yordam çağırmalıdır `CWinApp::PreTranslateMessage`.  
  
 Tüm DLL özgü başlatma yerleştirin `CWinApp::InitInstance` normal bir MFC uygulaması olduğu gibi üye işlevi. `CWinApp::ExitInstance` Üye işlevini, `CWinApp` sağlanan MFC'den türetilmiş bir sınıf olarak adlandırılan `DllMain` DLL kaldırılmadan önce işlev.  
  
 Paylaşılan dll MFCx0.dll ve Msvcr*0.dll (veya benzer dosyalar) uygulamanızla birlikte dağıtmanız gerekir.  
  
 Dinamik olarak MFC'ye bağlı bir DLL de statik olarak MFC'ye bağlayamazsınız. Uygulamaları bağlantı Normal MFC DLL'leri MFC'ye dinamik olarak, diğer DLL gibi bağlı.  
  
 Simgeler genellikle bir normal standart C arabirimi kullanan MFC DLL dışarı aktarılır. Normal bir MFC DLL'den dışarı aktarılan bir işlevin bildirimi şuna benzer:  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 Normal bir MFC DLL içindeki tüm bellek ayırmaları DLL kalmalı; DLL için geçirin veya arama yürütülebilir dosyadan aşağıdakilerden herhangi birini almak gerekir:  
  
-   MFC nesnelerine işaretçiler  
  
-   MFC tarafından ayrılan bellek işaretçiler  
  
 Yukarıdakilerin tümü gerçekleştirmeniz gereken ya da MFC türetilmiş nesneler arama yürütülebilir ve DLL arasında geçirmek gerekiyorsa, MFC uzantı DLL'si yapılandırmanız gerekir.  
  
 Yalnızca verilerin bir kopyasını yaparsanız işaretçileri ayrılan bellek C çalışma zamanı kitaplıkları tarafından bir uygulama ve DLL arasında geçirmek güvenlidir. Değil silmeli veya bu işaretçileri yeniden boyutlandırmak veya bellek kopyasını yapmadan kullanın.  
  
 MFC'ye dinamik olarak normal bir MFC DLL oluşturma bağlar, makrosu kullanmanıza gerek [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) MFC modül durumu doğru biçimde geçmek için. Bu, aşağıdaki kod satırını DLL'den dışarı aktarılan işlevlerin başına ekleyerek yapılır:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 **AFX_MANAGE_STATE** statik olarak MFC'ye Normal MFC DLL'leri veya MFC uzantı DLL'leri makrosu kullanılmamalıdır. Daha fazla bilgi için bkz: [MFC modüllerinin Durum verilerini yönetme](../mfc/managing-the-state-data-of-mfc-modules.md).  
  
 Örnek örneği nasıl yazma, yapı ve normal bir MFC DLL kullanmak için bkz: [ile ilgili](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap). Dinamik olarak MFC'ye Normal MFC DLL'leri hakkında daha fazla bilgi için örnek soyut "Dönüştürme ile ilgili için dinamik olarak bağlantı ile MFC DLL" başlıklı bölüme bakın.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [Normal MFC DLL'leri başlatma](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Normal MFC DLL'nin Modül durumları dinamik olarak MFC'ye bağlı](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
  
-   [MFC modüllerinin durum verisini yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [Normal MFC DLL'lerde veritabanı, OLE ve yuva MFC uzantı DLL'leri kullanma](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [Bir DLL'in bir parçası MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL türleri](../build/kinds-of-dlls.md)