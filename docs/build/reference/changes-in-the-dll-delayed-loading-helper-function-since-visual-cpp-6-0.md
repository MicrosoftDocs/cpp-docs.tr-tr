---
title: "DLL değişiklikleri Gecikmeli yardımcı işlevini Visual C++ 6.0 yükleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b3123a722e0e95119a4b04f5c060bd947b987cdf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Visual C++ 6.0 Sonrasındaki Gecikmeli Yükleme Yardımcısı İşlevi DLL Değişiklikleri
Bilgisayarınızda Visual C++ birden fazla sürümü varsa veya kendi yardımcı işlevinizi tanımlanmışsa tarafından etkilenebilir DLL'e yapılan değişiklikler Gecikmeli yardımcı işlevini yüklemesi. Örneğin:  
  
-   **__delayLoadHelper** artık **__delayLoadHelper2**  
  
-   **__pfnDliNotifyHook** artık **__pfnDliNotifyHook2**  
  
-   **__pfnDliFailureHook** artık **__pfnDliFailureHook2**  
  
-   **__FUnloadDelayLoadedDLL** artık **__FUnloadDelayLoadedDLL2**  
  
> [!NOTE]
>  Varsayılan yardımcı işlevini kullanıyorsanız, bu değişiklikler, etkilemez. Bağlayıcı çağırma nasıl ilgili değişiklik yoktur.  
  
## <a name="multiple-versions-of-visual-c"></a>Visual C++ birden çok sürümü  
 Bilgisayarınızda Visual C++ birden fazla sürümü varsa, bağlayıcı delayimp.lib eşleştiğinden emin olun. Bir uyuşmazlık varsa, ya da raporlama bir bağlayıcı hatası alırsınız `___delayLoadHelper2@8` veya `___delayLoadHelper@8` çözülmemiş bir dış simgesi olarak. Eski bir eski delayimp.lib ile yeni bir bağlayıcı anlamına gelir ve ikincisi yeni delayimp.lib ile eski bir bağlayıcı anlamına gelir.  
  
 Çözümlenmemiş bağlayıcı hata iletisi alırsanız, çalıştırmak [dumpbin /linkermember](../../build/reference/linkermember.md): hangi yardımcı işlevini yerine tanımlanan görmek için yardımcı işlevini içeren beklediğiniz delayimp.lib 1. Yardımcı işlevini de bir nesne dosyasında tanımlanmış olması; çalıştırma [dumpbin /symbols](../../build/reference/symbols.md) ve Ara `delayLoadHelper(2)`.  
  
 Visual C++ 6.0 bağlayıcı sonra olduğunu biliyorsanız:  
  
-   DUMPBIN tanımlar olup olmadığını belirlemek için gecikme yükü yardımcının .lib veya .obj dosyasını çalıştırma **__delayLoadHelper2**. Değilse, bağlantı başarısız olur.  
  
-   Tanımlamak **__delayLoadHelper** cinsinden gecikme yardımcının .lib veya .obj dosyası yüklenemiyor.  
  
## <a name="user-defined-helper-function"></a>Kullanıcı tanımlı yardımcı işlevi  
 Kendi yardımcı işlevinizi tanımlı ve Visual C++ geçerli sürümünü kullanıyorsanız, aşağıdakileri yapın:  
  
-   Yardımcı işlevi yeniden adlandırma **__delayLoadHelper2**.  
  
-   İşaretçileri (ImgDelayDescr delayimp.h içinde) gecikme tanımlayıcısındaki mutlak adreslerden (VAs) göreli adresleri (her iki 32 ve 64 bit program beklendiği şekilde çalışması için RVAs) için değiştirilmiş olduğundan, bu geri işaretçileri dönüştürmeniz gerekir. Yeni bir işlev sunulmuştur: PFromRva, delayhlp.cpp içinde bulunamadı. Her iki 32 veya 64 bit işaretçileri dönüştürmek için tanımlayıcısındaki alanların her biri üzerinde bu işlevi kullanabilirsiniz. Varsayılan Gecikmeli Yükleme Yardımcısı işlevi, örnek olarak kullanmak üzere iyi bir şablonu olmaya devam ediyor.  
  
## <a name="load-all-imports-for-a-delay-loaded-dll"></a>Gecikmeli yüklenen DLL için tüm içe aktarmaları yükleme  
 Bağlayıcı DLL'den yüklenen gecikme olması için belirttiğiniz tüm içe aktarmaları yükleyebilirsiniz. Bkz: [Delay-Loaded DLL için tüm almalar yüklenirken](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yardımcı İşlevini Anlama](understanding-the-helper-function.md)