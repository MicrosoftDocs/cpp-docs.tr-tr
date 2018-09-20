---
title: Yeni proje oluşturma Varolan kod dosyaları sihirbazından proje ayarlarını belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.appsettings
dev_langs:
- C++
helpviewer_keywords:
- Create New Project From Existing Code Files Wizard, project settings
ms.assetid: 9b8860c9-d35f-4f18-9565-2934d3d7f569
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f86361bf947a5a6117c53ce2c92c40ef1abb7117
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387828"
---
# <a name="specify-project-settings-create-new-project-from-existing-code-files-wizard"></a>Proje Ayarlarını Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı

Oluşturma yeni proje varolan kod dosyalarından sihirbazın bu sayfası belirtmek için kullanın:

- Yeni proje için yapı ortamı

- Yeni proje oluşturmak için belirli bir tür eşleştirmek için ayarları oluşturun

## <a name="task-list"></a>Görev Listesi

[Nasıl Yapılır: Varolan Koddan C++ Projesi Oluşturma](../ide/how-to-create-a-cpp-project-from-existing-code.md)

## <a name="uielement-list"></a>UIElement Listesi

- **Visual Studio'yu kullanın.**

   Visual Studio'da yeni proje oluşturmak için dahil edilen derleme araçları kullanılacağını belirtir. Bu seçenek varsayılan olarak seçilidir.

- **Proje türü**

   Sihirbaz oluşturacağı projenin türünü belirtir.

- **Windows uygulama projesi**

   Sihirbaz yürütülebilir bir Windows uygulaması projesi oluşturacak gösterir. Bu seçenek kullanılabilir **proje türü** aşağı açılan liste kutusu.

- **Konsol uygulama projesi**

   Sihirbazın bir konsol uygulaması projesi oluşturacak gösterir. Bu seçenek kullanılabilir **proje türü** aşağı açılan liste kutusu.

- **Dinamik olarak bağlı bir kitaplığı (DLL) projesi**

   Sihirbazın bir boş dinamik bağlantı kitaplığı uygulaması projesi oluşturacak gösterir. Bu seçenek kullanılabilir **proje türü** aşağı açılan liste kutusu.

- **Statik kitaplık (LIB) projesi**

   Sihirbazın bir statik kitaplık uygulaması projesi oluşturacak gösterir. Bu seçenek kullanılabilir **proje türü** aşağı açılan liste kutusu.

- **ATL için destek eklendi**

   Yeni projeye ATL desteği ekler.

- **MFC için destek eklendi**

   MFC desteği için yeni proje ekler.

- **Ortak dil çalışma zamanı desteği eklendi**

   CLR programlamada yeni proje için destek ekler.

- **Ortak dil çalışma zamanı**

   CLR özellikleri ile uyumlu olması için yeni proje belirtir.

- **Ortak dil çalışma zamanı (eski sözdizimi)**

   CLR programlama sözdizimi önce Visual C++ 2005 ' C++ sözdizimi için Yönetilen Uzantılar'ile uyumlu olması için yeni proje belirtir.

- **Dış yapı ortamı kullanın**

   Visual Studio'da yeni proje oluştururken bulunmayan yapı araçlarını kullanmayı belirtir. Bu seçenek belirlendiğinde, derleme komut satırları belirtebilirsiniz **hata ayıklama yapılandırma ayarlarını belirt** ve **sürüm yapılandırma ayarlarını belirt** sayfaları.

   > [!NOTE]
   > Zaman **kullanım dış yapı sistemi** seçeneği, IDE yeni projeyi oluşturmak değil böylece /D, / ı, /FI, /AI veya /FU seçenekleri derleme için gerekli değildir. Ancak, bu seçenekler sırada düzgün çalışması IntelliSense doğru şekilde ayarlanmalıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılandırma Ayarlarında Hata Ayıklamayı Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı](../ide/specify-debug-configuration-settings.md)<br>
[Yayın Yapılandırma Ayarlarını Belirtme, Varolan Kod Dosyalarından Yeni Proje Oluşturma Sihirbazı](../ide/specify-release-configuration.md)