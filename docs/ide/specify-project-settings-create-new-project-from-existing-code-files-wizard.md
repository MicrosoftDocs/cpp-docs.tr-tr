---
title: "Proje ayarlarını belirtme yeni proje varolan kod dosyalarından Oluşturma Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.importwiz.appsettings
dev_langs: C++
helpviewer_keywords: Create New Project From Existing Code Files Wizard, project settings
ms.assetid: 9b8860c9-d35f-4f18-9565-2934d3d7f569
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2cf1e8eba11063f7f2e46f836cd2ef84cc70dfe8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="specify-project-settings-create-new-project-from-existing-code-files-wizard"></a>Proje Ayarlarını Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı
Oluşturma yeni proje varolan kod dosyaları sihirbazın bu sayfası belirtmek için kullanın:  
  
-   Yeni proje için yapı ortamı  
  
-   Yapı oluşturmak için yeni proje belirli bir türdeki eşleştirmek için ayarları  
  
## <a name="task-list"></a>Görev Listesi  
 [Nasıl Yapılır: Varolan Koddan C++ Projesi Oluşturma](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Visual Studio'yu kullanma**  
 Visual Studio'da yeni proje oluşturmak için dahil edilen derleme araçları kullanılacağını belirtir. Bu seçenek varsayılan olarak seçilidir.  
  
 **Proje türü**  
 Sihirbaz oluşturacaktır proje türünü belirtir.  
  
 **Windows uygulama projesi**  
 Sihirbaz yürütülebilir bir Windows uygulaması için bir proje oluşturur gösterir. Bu seçenek kullanılabilir **proje türü** aşağı açılan liste kutusu.  
  
 **Konsol uygulama projesi**  
 Sihirbazın bir konsol uygulaması için bir proje oluşturur gösterir. Bu seçenek kullanılabilir **proje türü** aşağı açılan liste kutusu.  
  
 **Dinamik olarak bağlı kitaplığı (DLL) projesi**  
 Sihirbazın bir boş dinamik bağlantı kitaplık uygulaması için bir proje oluşturur gösterir. Bu seçenek kullanılabilir **proje türü** aşağı açılan liste kutusu.  
  
 **Statik kitaplık (LIB) proje**  
 Sihirbazın bir statik kitaplık uygulaması için bir proje oluşturur gösterir. Bu seçenek kullanılabilir **proje türü** aşağı açılan liste kutusu.  
  
 **ATL desteği ekleme**  
 ATL desteği yeni projeye ekler.  
  
 **MFC desteği ekleme**  
 MFC desteği yeni projeye ekler.  
  
 **Ortak dil çalışma zamanı desteği ekleme**  
 CLR programlama yeni proje için destek ekler.  
  
 **Ortak dil çalışma zamanı**  
 CLR özellikleri ile uyumlu olması için yeni proje belirtir.  
  
 **Ortak dil çalışma zamanı (eski sözdizimi)**  
 Visual C++ 2005 önce CLR programlama sözdizimi C++ sözdizimi için Yönetilen Uzantılar'ile uyumlu olması için yeni proje belirtir.  
  
 **Dış yapı sistem kullanın**  
 Visual Studio'da yeni proje oluşturmak için bulunmayan derleme araçları kullanılacağını belirtir. Bu seçenek belirlendiğinde, üzerinde derleme komut satırları belirtebilirsiniz **hata ayıklama yapılandırma ayarlarını belirt** ve **yayın yapılandırma ayarlarını belirt** sayfaları.  
  
> [!NOTE]
>  Zaman **kullanım dış yapı sistem** seçeneği seçiliyse, yeni proje IDE oluşmuyor böylece /D, / t, /FI, /AI veya /FU seçenekleri derleme için gerekli değildir. Ancak, bu seçenekler düzgün çalışması IntelliSense sırayla doğru şekilde ayarlanmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılandırma ayarlarında hata ayıklamayı belirtme, varolan kod dosyaları Sihirbazı'ndan yeni proje oluşturma](../ide/specify-debug-configuration-settings.md)   
 [Yayın Yapılandırma Ayarlarını Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı](../ide/specify-release-configuration.md)