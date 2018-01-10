---
title: "Windows mağazası uygulamaları, Windows çalışma zamanı ve C çalışma zamanı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c75d66fcbe9ef437980878e7789a82dc94b68573
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-store-apps-the-windows-runtime-and-the-c-run-time"></a>Windows Mağazası Uygulamaları, Windows Çalışma Zamanı ve C Çalışma Zamanı
[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]uygulamalar üzerinde yürütür Windows çalışma zamanı çalışan programlardır [!INCLUDE[win8](../build/reference/includes/win8_md.md)].  Windows çalışma zamanı işlevleri, değişkenleri ve kullanılabilir kaynaklar denetimleri güvenilir bir ortamdır bir [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] uygulama. Ancak, tasarım gereği, Windows çalışma zamanı kısıtlamaları özelliklerin çoğu C çalışma zamanı kitaplığı (CRT) kullanılmasını engellemek [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] uygulamalar.  
  
 Windows çalışma zamanı aşağıdaki CRT özellikleri desteklemez:  
  
-   Desteklenmeyen işlevsellik ilgili çoğu CRT işlevleri.  
  
     Örneğin, bir [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] uygulama kullanarak bir işlem oluşturamıyor `exec` ve `spawn` yordamları aileleri.  
  
     Ne zaman CRT işlevi desteklenmez bir [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] uygulama, olgu kendi başvurusu makalesinde belirtilir.  
  
-   En çok baytlı karakter ve dize işlevleri.  
  
     Ancak, Unicode ve ANSI text desteklenir.  
  
-   Konsol uygulamaları ve komut satırı bağımsız değişkenleri.  
  
     Ancak, geleneksel masaüstü uygulamaları hala konsol ve komut satırı bağımsız değişkenleri destekler.  
  
-   Ortam değişkenleri.  
  
-   Geçerli çalışma dizini kavramı.  
  
-   [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]uygulamalar ve statik olarak CRT bağlı ve kullanılarak oluşturulmuş DLL'leri [/MT](../build/reference/md-mt-ld-use-run-time-library.md) veya `/MTd` derleyici seçenekleri.  
  
     Diğer bir deyişle, CRT çoklu iş parçacığı, statik bir sürümünü kullanan bir uygulama.  
  
-   Kullanılarak oluşturulmuş bir uygulama [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) derleyici seçeneği.  
  
     Diğer bir deyişle, bir hata ayıklama, çoklu iş parçacığı kullanan ve CRT DLL özgü sürümü. Bu tür bir uygulama desteklenmiyor [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)].  
  
 Kullanılamayan CRT işlevleri tam bir listesi için bir [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] uygulama ve önerileri alternatif işlevleri için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uyumluluk](../c-runtime-library/compatibility.md)   
 [Windows çalışma zamanı desteklenmeyen CRT işlevleri](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)   
 [Kategorilere Göre Çalışma Zamanı Yordamları](../c-runtime-library/run-time-routines-by-category.md)