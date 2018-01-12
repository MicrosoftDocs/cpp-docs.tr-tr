---
title: "Nasıl yapılır: derleme görevleri dosyası projeleri için IntelliSense'i etkinleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCNMakeTool.IntelliSense
dev_langs: C++
helpviewer_keywords:
- Makefile projects, IntelliSense
- IntelliSense, Makefile projects
ms.assetid: 9443f453-f18f-4f12-a9a1-ef9dbf8b188f
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fae3ec35259250f71ad672d9468b991033608ae4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-enable-intellisense-for-makefile-projects"></a>Nasıl Yapılır: Derleme Görevleri Dosyası Projeleri için IntelliSense'i Etkinleştirme
Visual C++ derleme görevleri dosyası projeleri için IDE'de belirli ayarları veya derleyici seçenekleri, projenizin çalışması için IntelliSense başarısız yanlış ayarlanır. Derleme görevleri dosyası projeleri Visual Studio geliştirme ortamında açık olduğunda IntelliSense çalışmasını Visual C++ derleme görevleri dosyası projeleri yapılandırmak için bu yordamı kullanın.  
  
### <a name="to-enable-intellisense-for-makefile-projects-in-the-ide"></a>IDE içinde derleme görevleri dosyası projeleri için IntelliSense'i etkinleştirme için  
  
1.  Açık **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Seçin **NMake** özellik sayfasında ve Özellikler altında değiştirme **IntelliSense** uygun şekilde.  
  
    -   Ayarlama **önişlemci tanımları** önişlemci semboller derleme görevleri dosyası projenizi tanımlamak için özellik. Bkz: [/D (önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md), daha fazla bilgi için.  
  
    -   Ayarlama **arama yolu Ekle** özelliği derleyici derleme görevleri dosyası projenizdeki önişlemci yönergeleri için geçirilen dosya başvuruları çözümlemek için arayacağı dizinlerin listesini belirtin. Bkz: [/ı (ek içeren dizinler)](../build/reference/i-additional-include-directories.md), daha fazla bilgi için.  
  
         CL kullanılarak oluşturulan projeleri için. Bir komut penceresinde EXE ayarlamak **INCLUDE** derleyici derleme görevleri dosyası projenizdeki önişlemci yönergeleri için geçirilen dosya başvuruları çözümlemek için arayacağı dizinleri belirtmek için ortam değişkeni.  
  
    -   Ayarlama **zorunlu içeren** derleme görevleri dosyası projesi oluştururken işlemi için hangi başlık dosyaları belirtmek için özellik. Bkz: [/FI (zorla dahil dosyasını Adlandır)](../build/reference/fi-name-forced-include-file.md), daha fazla bilgi için.  
  
    -   Ayarlama **derleme arama yolu** özelliği derleyici .NET derlemelerini projenizdeki başvuruları çözümlemek için arayacağı dizinlerin listesini belirtin. Bkz: [/AI (meta veri dizinlerini belirtin)](../build/reference/ai-specify-metadata-directories.md), daha fazla bilgi için.  
  
    -   Ayarlayın **kullanarak derlemeler zorunlu** özelliği, derleme görevleri dosyası projesi oluştururken işlemek için hangi .NET derlemelerini belirtin. Bkz: [/FU (zorlanan adı #using)](../build/reference/fu-name-forced-hash-using-file.md), daha fazla bilgi için.  
  
    -   Ayarlama **ek seçenekler** özelliği C++ dosyalarını ayrıştırırken IntelliSense tarafından kullanılacak ek derleyici anahtarları belirtin.  
  
4.  Tıklatın **Tamam** özellik sayfalarını kapatmak için.  
  
5.  Kullanım **Tümünü Kaydet** değiştirilmiş proje ayarlarını kaydetmek için komutu.  
  
 Sonraki açışınızda, derleme görevleri dosyası projesi çalıştırma Visual Studio geliştirme ortamında **temiz çözüm** komutu ve ardından **yapı çözümü** derleme görevleri dosyası projenizi komutu. IntelliSense IDE içinde düzgün çalışması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IntelliSense kullanma](/visualstudio/ide/using-intellisense)   
 [NMAKE başvurusu](../build/nmake-reference.md)   
 [Nasıl Yapılır: Varolan Koddan C++ Projesi Oluşturma](../ide/how-to-create-a-cpp-project-from-existing-code.md)