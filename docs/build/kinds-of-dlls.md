---
title: "DLL türleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC DLLs [C++], types
- DLLs [C++], types
- DLLs [C++], MFC
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47ce4a9264a59f88f22cd40bc3b6d6620c9702c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="kinds-of-dlls"></a>DLL Türleri
Bu konu, DLL derleme türünü belirlemenize yardımcı olacak bilgiler sağlar.  
  
##  <a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a>Farklı türdeki kullanılabilir DLL'ler  
 Visual C++ kullanarak, Win32 DLL'leri C veya C++ Microsoft Foundation Class (MFC) kitaplığı kullanmayan oluşturabilirsiniz. Win32 Uygulama Sihirbazı'ndaki bir MFC DLL projesi oluşturabilirsiniz.  
  
 MFC Kitaplığı ya da statik bağlantı kitaplıkları veya DLL'ler, MFC DLL Sihirbazı'nı kullanarak bir dizi, kullanılabilir. MFC DLL kullanıyorsanız, Visual C++ üç farklı DLL geliştirme senaryolarını destekler:  
  
-   Statik olarak Normal MFC DLL oluşturma  
  
-   MFC bağlantıları dinamik olarak Normal MFC DLL oluşturma  
  
-   MFC uzantı DLL'si oluşturma, her zaman dinamik olarak MFC'ye  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [MFC Dışı DLL'ler: Genel Bakış](../build/non-mfc-dlls-overview.md)  
  
-   [Statik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC uzantı DLL'leri: Genel Bakış](../build/extension-dlls-overview.md)  
  
-   [Hangi tür DLL kullanmak için](#_core_which_kind_of_dll_to_use)  
  
##  <a name="_core_which_kind_of_dll_to_use"></a>Hangi tür DLL kullanmaya karar verme  
 MFC DLL kullanmıyorsa, Visual C++ dışı MFC Win32 DLL oluşturmak için kullanın. (Statik veya dinamik olarak), DLL MFC'ye bağlantılandırma önemli disk alanı ve bellek alır. MFC DLL gerçekte kullanmadığı sürece MFC'ye bağlantı yapmamanız gerekir.  
  
 DLL MFC kullanma ve MFC veya MFC olmayan uygulamaları tarafından kullanılan, dinamik olarak MFC'ye bağlı normal MFC DLL ya da MFC'ye normal bir MFC DLL oluşturmanız gerekir. Çoğu durumda, muhtemelen dinamik olarak MFC'ye DLL dosyasının boyutu çok küçük olmaz ve MFC paylaşılan sürümünü kullanarak bellekte tasarrufları önemli olabilir çünkü bağlanan normal bir MFC DLL kullanmak istiyorsunuz. Statik olarak MFC'ye bağlantı varsa, DLL dosyası boyutunu daha büyük olabilir ve kendi özel MFC kitaplık kodu kopyasını yüklediğinden ek bellek büyük olasılıkla alabilir.  
  
 Dinamik olarak MFC'ye bağlanan bir DLL oluşturma MFC'nin bağlamak gerekli olmadığından, MFC'ye bir DLL oluşturmaktan daha hızlıdır. Bu bağlayıcı hata ayıklama bilgileri nerede sıkıştırmasının gerektiği hata ayıklama derlemelerinde özellikle doğrudur. Hata ayıklama bilgilerini içeren bir DLL ile bağlayarak, DLL sıkıştırmak için daha az hata ayıklama bilgisi yoktur.  
  
 Dinamik olarak MFC'ye bağlantılandırma bir dezavantajı, paylaşılan DLL'leri Mfcx0.dll ve Msvcrxx.dll (veya benzer dosyaları) DLL ile dağıtmanız gerektiğidir. MFC DLL'leri ücretsiz olarak yeniden dağıtılabilir, ancak hala Kurulum programınıza DLL'leri yüklemeniz gerekir. Ayrıca, hem programınız ve MFC DLL'leri tarafından kullanılan C çalışma zamanı kitaplığı içeren Msvcrxx.dll hazırlamalısınız.  
  
 DLL yalnızca MFC yürütülebilir dosyaları tarafından kullanılacaksa, normal bir MFC DLL veya MFC uzantı DLL oluşturma arasında seçim sahip. DLL varolan MFC sınıflarından türetilmiş yeniden kullanılabilir sınıfları uygulayan veya uygulama ve DLL arasında MFC'den türetilen nesneleri geçirmek gerekirse, MFC uzantı DLL'si yapılandırmanız gerekir.  
  
 DLL dinamik olarak MFC'ye bağlanıyorsa, MFC DLL'leri DLL ile dağıtılabilir. Bu mimari, disk alanından tasarruf ve bellek kullanımını en aza indirmek için birden fazla yürütülebilir dosyalar arasında sınıf kitaplığı paylaşımı için özellikle yararlıdır.  
  
 Sürüm 4.0, MFC kullanılan DLL'leri Visual C++ yalnızca desteklenen iki tür önce: USRDLL ve AFXDLL. Statik olarak MFC'ye bağlı normal MFC DLL'leri önceki USRDLL ile aynı özelliklere sahip. MFC uzantı DLL'leri eski AFXDLL aynı özelliklere sahip.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [MFC Dışı DLL'ler: Genel Bakış](../build/non-mfc-dlls-overview.md)  
  
-   [Statik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC uzantı DLL'leri: Genel Bakış](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)