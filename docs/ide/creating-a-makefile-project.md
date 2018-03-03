---
title: "Derleme görevleri dosyası projesi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5e86bedbf83cd417cfc41317e5887304cda7ee76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-makefile-project"></a>Derleme Görevleri Dosyası Projesi Oluşturma
Makefile (derleme görevleri dosyası) ile komut satırından derlediğiniz bir projeniz varsa, Visual Studio geliştirme ortamı bu projenizi tanımaz. Açıp kullanarak projesi oluşturmak için [!INCLUDE[vsUltShort](../ide/includes/vsultshort_md.md)], Visual Studio Professional ya da Visual Studio Express için Windows Masaüstü, önce bir boş proje oluşturma MakeFile proje şablonu seçerek. Daha sonra bu projeyi kullanarak Visual Studio geliştirme ortamından projenizi derleyebilirsiniz.  
  
 Proje, Çözüm Gezgini'nde hiçbir dosya göstermez. Proje, projeye ait özellik sayfasına yansıyan derleme ayarlarını belirtir.  
  
 Projede belirttiğiniz çıktı dosyasının, derleme komut dosyasının oluşturduğu ad üzerinde hiçbir etkisi yoktur; yalnızca bir amaç belirtir.  
  
### <a name="to-create-a-makefile-project"></a>Makefile projesi oluşturmak için  
  
1.  Yardım konusundaki yönergeleri izleyerek [proje bir Visual C++ Uygulama Sihirbazı oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  İçinde **yeni proje** iletişim kutusunda **derleme görevleri dosyası projesi** Sihirbazı'nı açmak için Şablonlar bölmesinde.  
  
3.  İçinde [uygulama ayarları](../ide/application-settings-makefile-project-wizard.md) sayfasında, komut sağlamak, çıktı, temizleyin ve bilgileri yeniden derleyin.  
  
4.  Tıklatın **son** Sihirbazı kapatmak ve yeni oluşturulan projede açmak için **Çözüm Gezgini**.  
  
 Özellik sayfasında projenin özelliklerini görüntüleyebilir ve düzenleyebilirsiniz. Bkz: [Visual C++ proje özelliklerini ayarlama](../ide/working-with-project-properties.md) özellik sayfası görüntüleme hakkında bilgi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme görevleri dosyası projesi Sihirbazı](../ide/makefile-project-wizard.md)   
 [Derleme görevleri dosyasındaki özel karakterler](../build/special-characters-in-a-makefile.md)   
 [Derleme Görevleri Dosyası İçeriği](../build/contents-of-a-makefile.md)