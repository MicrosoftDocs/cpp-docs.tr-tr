---
title: NMake özellik sayfası (C++ Windows) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
dev_langs:
- C++
helpviewer_keywords:
- NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29d10b35b0855e34826c10b813a2df48cd84cfef
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711977"
---
# <a name="nmake-property-page"></a>NMake Özellik Sayfaları
**NMake** özellik sayfası NMake projeleri için derleme ayarları belirtmenize olanak sağlar.  
  
NMake projeleri hakkında daha fazla bilgi için bkz. [bir derleme görevleri dosyası projesi oluşturma](../ide/creating-a-makefile-project.md). Non_Windows derleme görevleri dosyası projeleri için bkz: [derleme görevleri dosyası proje özellikleri (Linux C++)](../linux/prop-pages/makefile-linux.md), [genel proje özellikleri (Android C++ derleme görevleri dosyası)](/visualstudio/cross-platform/general-makefile-android-prop-page) veya [NMake özellikleri (Android C++)](/visualstudio/cross-platform/nmake-android-prop-page).
  
**NMake** özellik sayfası, aşağıdaki özellikleri içerir.  
  
## <a name="uielement-list"></a>UIElement Listesi  

- **Komut satırı derleme**

   Ne zaman çalıştırılacak komutu belirtir **derleme** üzerinde tıklandığında **derleme** menüsü.  
  
- **Rebuild all komut satırı**

   Ne zaman çalıştırılacak komutu belirtir **Rebuild All** üzerinde tıklandığında **derleme** menüsü.  
  
- **Temizle komut satırı**

   Ne zaman çalıştırılacak komutu belirtir **temiz** üzerinde tıklandığında **derleme** menüsü.  
  
- **Output**

   Çıkış komut satırı içerecek dosyanın adını belirtir. Varsayılan olarak, bu dosya adı proje adı temel alır.  
  
- **Önişlemci tanımları**

   Kaynak kullanan dosyaları tüm önişlemci tanımlarını belirtir. Varsayılan değer, geçerli platform ve yapılandırma tarafından belirlenir.  
  
- **Arama Yolu Ekle**

   Derleyici için dahil etme dosyaları nerede arar dizinleri belirtir.  
  
- **Zorlanmış içerir**

   Proje dosyalarında bulunmayan olsa bile, önişlemci otomatik olarak işleyen dosyalarını belirtir.  
  
- **Bütünleştirilmiş kod arama yolu**

   Burada .NET Framework araması ne zaman dizinleri belirtir, .NET derlemelerini çözümlenecek trys.  
  
- **Zorlanarak kullanılan bütünleştirilmiş kodlar**

   .NET Framework otomatik olarak işler bütünleştirilmiş kodları belirtir.  
  
- **Ek Seçenekler**

   C++ dosyaları ayıklarken kullanılacak IntelliSense için herhangi bir ek derleyici anahtarlarını belirtir.  
  
Nasıl erişileceği hakkında daha fazla bilgi için **NMake** özellik sayfasında bakın [Working with Project Properties](../ide/working-with-project-properties.md).  
  
Bu nesne program aracılığıyla üyelerine erişim hakkında daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../ide/property-pages-visual-cpp.md)   
 [Nasıl Yapılır: Derleme Görevleri Dosyası Projeleri için IntelliSense'i Etkinleştirme](../ide/how-to-enable-intellisense-for-makefile-projects.md)