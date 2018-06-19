---
title: Hata işleme ve bildirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2edec23da89766a45545566b0a689001d3ca75f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373224"
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