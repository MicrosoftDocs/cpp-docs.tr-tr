---
title: "Nasıl yapılır: derleme görevleri dosyası projeleri için IntelliSense'i etkinleştirme | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCNMakeTool.IntelliSense
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, IntelliSense
- IntelliSense, Makefile projects
ms.assetid: 9443f453-f18f-4f12-a9a1-ef9dbf8b188f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1dda7b485c5aef7b6277da3141f293e16ac7523b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433731"
---
# <a name="how-to-enable-intellisense-for-makefile-projects"></a>Nasıl Yapılır: Derleme Görevleri Dosyası Projeleri için IntelliSense'i Etkinleştirme

Visual C++ derleme görevleri dosyası projeleri için IDE içindeki bazı ayarları ya da derleyici seçenekleri, projenizin çalışılacak IntelliSense başarısız yanlış ayarlanır. Derleme görevleri dosyası projeleri Visual Studio geliştirme ortamında açıkken IntelliSense çalışır, böylece Visual C++ derleme görevleri dosyası projeleri yapılandırmak için bu yordamı kullanın.

### <a name="to-enable-intellisense-for-makefile-projects-in-the-ide"></a>IDE içinde derleme görevleri dosyası projeleri için IntelliSense'i etkinleştirme

1. Açık **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Seçin **NMake** özellik sayfa ve Özellikler altında değiştirin **IntelliSense** uygun şekilde.

   - Ayarlama **önişlemci tanımları** derleme görevleri dosyası projenize önişlemci simgeleri tanımlamak için özellik. Bkz: [/D (önişlemci tanımları)](../build/reference/d-preprocessor-definitions.md), daha fazla bilgi için.

   - Ayarlama **arama yolu Ekle** özelliği, derleme görevleri dosyası projesi ön işlemci yönergelerinde geçirilen dosya başvurularını çözümlemek için derleyicinin arama yapacağı dizinleri listesini belirtin. Bkz: [/ı (ek içeren dizinler)](../build/reference/i-additional-include-directories.md), daha fazla bilgi için.

         For projects that are built using CL.EXE from a Command Window, set the **INCLUDE** environment variable to specify directories that the compiler will search to resolve file references that are passed to preprocessor directives in your makefile project.

   - Ayarlama **zorunlu içerir** özelliği, derleme görevleri dosyası projesi oluşturma sırasında hangi başlığı işlenecek dosyaları belirtmek için. Bkz: [/FI (zorla dahil dosyasını Adlandır)](../build/reference/fi-name-forced-include-file.md), daha fazla bilgi için.

   - Ayarlama **bütünleştirilmiş kod arama yolu** özelliği, projenizdeki .NET derlemelerin başvurularını çözümlemek için derleyicinin arama yapacağı dizinleri listesini belirtin. Bkz: [/AI (meta veri dizinlerini belirtin)](../build/reference/ai-specify-metadata-directories.md), daha fazla bilgi için.

   - Ayarlama **kullanarak derlemeleri zorunlu** özelliği, derleme görevleri dosyası projesi oluşturma sırasında işlenecek hangi .NET derlemelerini belirtin. Bkz: [/FU (zorlanan adı #using)](../build/reference/fu-name-forced-hash-using-file.md), daha fazla bilgi için.

   - Ayarlama **ek seçenekler** özelliği C++ dosyaları ayrıştırılırken IntelliSense tarafından kullanılacak ek derleyici anahtarlarını belirtin.

1. Tıklayın **Tamam** özellik sayfalarını kapatmak için.

1. Kullanım **Tümünü Kaydet** değiştirilen proje ayarları kaydetmek için komutu.

Sonraki açışınızda, derleme görevleri dosyası projesi çalıştırma Visual Studio geliştirme ortamında **çözümü Temizle** komutunu ve ardından **Çözümü Derle** derleme görevleri dosyası projenize komutu. IntelliSense, IDE'de düzgün çalışması gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[IntelliSense Kullanma](/visualstudio/ide/using-intellisense)<br>
[NMAKE Başvurusu](../build/nmake-reference.md)<br>
[Nasıl Yapılır: Varolan Koddan C++ Projesi Oluşturma](../ide/how-to-create-a-cpp-project-from-existing-code.md)