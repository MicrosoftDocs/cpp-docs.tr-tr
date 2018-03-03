---
title: "Nasıl yapılır: Varolan koddan C++ projesi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C++, creating projects from existing code
ms.assetid: e328a938-395c-48ea-9e35-dd433de12b31
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d6781709c105c606f6ceb856654525385738c1ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-c-project-from-existing-code"></a>Nasıl Yapılır: Varolan Koddan C++ Projesi Oluşturma

Visual Studio'da, varolan kod dosyalarınızın bir Visual C++ projeye kullanarak bağlantı noktası **oluşturma yeni proje varolan kod dosyaları** Sihirbazı. Bu sihirbaz, Visual Studio'nun eski Express sürümlerinde kullanılamaz. Bu sihirbaz yeni bir çözüm ve kaynak dosyalarınızı yönetin ve yapılandırması oluşturmak için MSBuild sistem kullanır projesi oluşturur.  
  
Varolan kod dosyalarınızın bir Visual C++ projeye bağlantı noktası oluşturma, tüm IDE içinde yerleşik yerel MSBuild proje yönetimi özellikleri kullanmanızı sağlar. Nmake derleme görevleri dosyaları, CMake veya alternatifleri gibi mevcut Yapı sisteminizin kullanmayı tercih ederseniz, bunun yerine klasör Aç seçeneğini kullanabilirsiniz. Daha fazla bilgi için bkz: [Klasör Aç Visual C++ projelerinde](../ide/non-msbuild-projects.md). Her iki seçenek IDE özellikleri gibi kullanmanıza olanak tanır [IntelliSense](/visualstudio/ide/using-intellisense) ve [proje özelliklerini](../ide/working-with-project-properties.md).  
  
### <a name="to-create-a-c-project-from-existing-code"></a>Varolan koddan bir C++ projesi oluşturmak için  
  
1.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje ilk var olan kodu**.  
  
1.  İlk sayfasında **varolan kod dosyalarından yeni proje oluştur** seçin **Visual C++** içinde **ne tür bir proje oluşturmak istediğinizi** listesi. Seçin **sonraki** devam etmek için. 
  
1.  Proje konumunu ve kaynak dosyaların dizinini belirtin. Bu sayfada daha fazla bilgi için bkz [proje konumunu belirtin ve kaynak dosyaları, yeni projesi oluştur gelen varolan kod dosyaları Sihirbazı](../ide/specify-project-location-and-source-files.md). Seçin **sonraki** devam etmek için.  
  
1.  Kullanmak için proje ayarlarını belirtin. Bu sayfada daha fazla bilgi için bkz [proje ayarlarını belirtme, yeni projesi oluştur gelen varolan kod dosyaları Sihirbazı](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md). Seçin **sonraki** devam etmek için.  

1.  Hata ayıklama yapılandırma ayarlarını belirtin. Bu sayfada daha fazla bilgi için bkz [hata ayıklama yapılandırma ayarlarını belirtin, yeni projesi oluştur gelen varolan kod dosyaları Sihirbazı](../ide/specify-debug-configuration-settings.md). Seçin **sonraki** devam etmek için.  

1.  Yayın yapılandırma ayarlarını belirtin. Bu sayfada daha fazla bilgi için bkz [yayın yapılandırma ayarlarını belirtin, yeni projesi oluştur gelen varolan kod dosyaları Sihirbazı](../ide/specify-release-configuration.md). Seçin **son** yeni proje oluşturmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Proje belirtin konumunu ve kaynak dosyaları, yeni proje varolan kod dosyalarından Oluşturma Sihirbazı](../ide/specify-project-location-and-source-files.md)   
[Proje ayarlarını belirtme, varolan kod dosyaları Sihirbazı'ndan yeni proje oluşturma](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)   
[Yapılandırma ayarlarında hata ayıklamayı belirtme, varolan kod dosyaları Sihirbazı'ndan yeni proje oluşturma](../ide/specify-debug-configuration-settings.md)   
[Yayın Yapılandırma Ayarlarını Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı](../ide/specify-release-configuration.md)