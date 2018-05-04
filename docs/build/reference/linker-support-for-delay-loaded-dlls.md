---
title: Gecikmeli yüklenen DLL'ler için bağlayıcı desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aea4ca6d5391f71f27d59d0192fcf1f832dd6702
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği
Visual C++ bağlayıcı artık DLL'leri Gecikmeli yüklenmesini destekler. Bu gereksinim Windows SDK işlevleri kullanmak için hafifletir **LoadLibrary** ve **GetProcAddress** Gecikmeli yüklemesi DLL uygulamak için.  
  
 Visual C++ 6.0 önce çalışma zamanında DLL'i tek yolu kullanmaktı **LoadLibrary** ve **GetProcAddress**; işletim sistemi DLL'i olduğunda çalıştırılabilir veya onu yüklenen DLL kullanarak.  
  
 Statik olarak DLL ile bağlarken Visual C++ 6.0 ile başlayarak, programın bu DLL'deki işlevi çağırır kadar gecikme seçenekleri DLL'yi sağlar.  
  
 Bir uygulama geciktirebilir DLL kullanarak yük [/DELAYLOAD (Gecikmeli yükleme içe aktarma)](../../build/reference/delayload-delay-load-import.md) yardımcı işlevi (Visual C++ tarafından sağlanan varsayılan uygulaması) ile bağlayıcı seçeneği. Yardımcısı işlevi DLL çalışma zamanında çağırarak yükler **LoadLibrary** ve **GetProcAddress** sizin için.  
  
 DLL varsa Gecikmeli yükleme dikkate almanız gerekir:  
  
-   Programınızı bir işlev DLL'de aranmayacağını.  
  
-   DLL işlevinde geç yürütmesinde programınızın kadar çağrılmadığı değil.  
  
 Gecikmeli DLL yüklenmesini herhangi birinin derleme sırasında belirtilebilir bir. EXE veya. DLL projesi. A. Bir veya daha fazla DLL'leri yükleme gecikmeler DLL projesi kendisini Gecikmeli yüklenen giriş noktası Dllmain çağırmalıdır değil.  
  
 Aşağıdaki konularda Gecikmeli yükleme DLL'leri açıklanmaktadır:  
  
-   [Gecikme Yükü DLL'lerini Belirtme](../../build/reference/specifying-dlls-to-delay-load.md)  
  
-   [Gecikmeli Yüklenen DLL'i Açıkça Kaldırma](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
-   [Gecikmeli Yüklenen DLL için Tüm İçe Aktarmaları Yükleme](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)  
  
-   [İçeri Aktarılanları Bağlama](../../build/reference/binding-imports.md)  
  
-   [Hata İşleme ve Bildirme](../../build/reference/error-handling-and-notification.md)  
  
-   [Gecikmeli Yükleme İçe Aktarmalarını Dökme](../../build/reference/dumping-delay-loaded-imports.md)  
  
-   [DLL'leri Yüklemede Gecikme Kısıtlamaları](../../build/reference/constraints-of-delay-loading-dlls.md)  
  
-   [Yardımcı İşlevini Anlama](understanding-the-helper-function.md)  
  
-   [Kendi Yardımcı İşlevinizi Geliştirme](../../build/reference/developing-your-own-helper-function.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'leri](../../build/dlls-in-visual-cpp.md)   
 [Bağlama](../../build/reference/linking.md)