---
title: "Hata işleme ve bildirme | Microsoft Docs"
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
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 738721eb3fc37ba076157129cb88a22f2c90e464
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="error-handling-and-notification"></a>Hata İşleme ve Bildirme
Hata işleme ve bildirme hakkında daha fazla bilgi için bkz: [yardımcı işlevini anlama](understanding-the-helper-function.md).  
  
 Kanca işlevleri hakkında daha fazla bilgi için bkz: [yapı ve sabit tanımları](../../build/reference/structure-and-constant-definitions.md).  
  
 Gecikmeli yüklenen DLL'ler programınızı kullanıyorsa, program çalışırken oluşan hataları işlenmemiş özel durumlardan sonuçlanır bu yana, hataları yerine işlemelidir. Hata işleme iki bölümlerini oluşmaktadır:  
  
 Bir kanca aracılığıyla kurtarma.  
 Kodunuzu kurtarmak ya da bir alternatif kitaplığı ve/veya yordamı hatada sağlamak gerekirse, bir kanca sağladığınız veya bu durumu düzeltmek yardımcı işlevini sağlanabilir. Böylece işleme uygun bir değer döndürüleceğini kanca rutin gereksinimlerini (bir HINSTANCE veya FARPROC) devam edebilir veya bir özel durum olduğunu göstermek için 0. Ayrıca, kendi özel durum oluşturabilir veya **longjmp** kanca dışında. Bildirim kancaları ve hata kancaları vardır.  
  
 Bir özel durum raporlama.  
 Hata işleme için gerekli olan tüm yordamı iptal etmek için kullanıcı kodu özel durumu işleyebilecek sürece hiçbir kanca gereklidir.  
  
 Hata işleme ve bildirme aşağıdaki konular ele alınmıştır:  
  
-   [Bildirim Kancaları](../../build/reference/notification-hooks.md)  
  
-   [Hata Kancaları](../../build/reference/failure-hooks.md)  
  
-   [Özel Durumlar](../../build/reference/exceptions-c-cpp.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)