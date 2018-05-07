---
title: NMake özellik sayfası (Windows C++) | Microsoft Docs
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
ms.openlocfilehash: f156d69467f00c4c4a62ec84d3b870e2999d7115
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-property-page"></a>NMake Özellik Sayfaları
**NMake** özellik sayfası NMake projeleri için yapılandırma ayarlarını belirtmenize olanak sağlar.  
  
 NMake projeler hakkında daha fazla bilgi için bkz: [derleme görevleri dosyası projesi oluşturma](../ide/creating-a-makefile-project.md). Non_Windows derleme görevleri dosyası projeleri için bkz: [derleme görevleri dosyası proje özellikleri (Linux C++)](../linux/prop-pages/makefile-linux.md), [genel proje özellikleri (Android C++ derleme görevleri dosyası)](/visualstudio/cross-platform/general-makefile-android-prop-page) veya [NMake özellikleri (Android C++)](/visualstudio/cross-platform/nmake-android-prop-page).
  
 **NMake** özellik sayfası, aşağıdaki özellikleri içerir.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Komut satırı derleme**  
 Ne zaman çalıştırılması için komutu belirler **yapı** üzerinde tıkladığınız **yapı** menüsü.  
  
 **Tüm komut satırı yeniden oluşturma**  
 Ne zaman çalıştırılması için komutu belirler **yeniden tüm** üzerinde tıkladığınız **yapı** menüsü.  
  
 **Komut satırı Temizle**  
 Ne zaman çalıştırılması için komutu belirler **temiz** üzerinde tıkladığınız **yapı** menüsü.  
  
 **Output**  
 Komut satırı için çıktı içeren dosyanın adını belirtir. Varsayılan olarak, bu dosya adı proje adına göre temel alır.  
  
 **Önişlemci tanımları**  
 Kaynak kullanım dosyalar herhangi önişlemci tanımları belirtir. Varsayılan değer geçerli platform ve yapılandırması tarafından belirlenir.  
  
 **Arama Yolu Ekle**  
 Burada derleyici için dosyaları Ekle arar dizinleri belirtir.  
  
 **Zorlanan içerir**  
 Proje dosyaları dahil edilmeyen olsa bile önişlemci otomatik olarak işler dosyalarını belirtir.  
  
 **Derleme arama yolu**  
 Burada .NET Framework araması ne zaman dizinleri belirtir, .NET derlemelerini çözümlemek için trys.  
  
 **Derlemeler kullanma zorla**  
 .NET Framework otomatik olarak işler derlemeleri belirtir.  
  
 **Ek Seçenekler**  
 C++ dosyalarını ayrıştırırken kullanılacak IntelliSense için hiçbir ek derleyici anahtarları belirtir.  
  
 Nasıl erişileceği hakkında bilgi için **NMake** özellik sayfası, bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).  
  
 Program aracılığıyla erişim üyeleri bu nesne için hakkında daha fazla bilgi için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../ide/property-pages-visual-cpp.md)   
 [Nasıl Yapılır: Derleme Görevleri Dosyası Projeleri için IntelliSense'i Etkinleştirme](../ide/how-to-enable-intellisense-for-makefile-projects.md)