---
title: "Aracı yapılandırma özellikleri (Visual C++) bildirim | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.MergeRulesFile
- VC.Project.VCManifestTool.UseUnicodeResponseFiles
- VC.Project.VCManifestTool.SuppressStartupBanner
- VC.Project.VCManifestTool.UseFAT32Workaround
- VC.Project.VCManifestTool.VerboseOutput
- VC.Project.VCManifestTool.AssemblyIdentity
dev_langs: C++
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e5e56c823a7a30850e24e393a545f0df6a6637a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="general-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Genel, bildirim aracı, yapılandırma özellikleri &lt;Projectname&gt; özellik sayfaları iletişim kutusu
Genel seçeneklerini belirtmek için bu iletişim kutusunu kullanın [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Bu özellik sayfası iletişim kutusu erişmek için özellik sayfaları projenizi veya özellik sayfasını açın. Genişletme **bildirim aracı** düğümü altında **yapılandırma özellikleri**ve ardından **genel**.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Başlangıç başlığını gösterme**  
 **Evet (/ nologo)** bildirim aracı başlatıldığında standart Microsoft telif hakkı verileri gizlenir belirtir. Mt.exe parçası olarak bir yapı işlemi veya bir yapı ortamından çalıştırdığınızda, günlük dosyaları, istenmeyen çıktısında gizlemek için bu seçeneği kullanın.  
  
 **Ayrıntılı çıktı**  
 **Evet (/ verbose)** ek yapı bilgileri bildirim oluşturma sırasında görüntüleneceğini belirtir.  
  
 **Derleme kimliği**  
 Bir kimlik dizesi belirtmek için /identity seçeneğini kullanan hangi oluşturur özniteliklerini [ \<assemblyIdentity > öğesi](/visualstudio/deployment/assemblyidentity-element-clickonce-application). Bir kimlik dizesi değeri ile başlayan `name` özniteliği ve tarafından izlenen *özniteliği* = *değeri* çiftleri. Bir kimlik dizesi özniteliklerin virgülle ayrılır.  
  
 Örnek kimlik dizesi aşağıdadır:  
  
 `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)   
 [Bildirim aracı özellik sayfaları](../ide/manifest-tool-property-pages.md)   
 [Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)   