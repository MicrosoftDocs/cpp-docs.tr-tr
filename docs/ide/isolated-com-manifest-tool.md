---
title: Bildirim aracı yalıtılmış COM özellikleri (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.ReplacementsFile
dev_langs:
- C++
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c425a71f8bb8a7972ade29fb0d18cf3eab7debb5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="isolated-com-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>COM, bildirim aracı, yapılandırma özellikleri yalıtılmış &lt;Projectname&gt; özellik sayfaları iletişim kutusu
Belirtmek için bu iletişim kutusunu kullanın **yalıtılmış COM** seçenekleri [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Bu özellik sayfası iletişim kutusu erişmek için özellik sayfaları projenizi veya özellik sayfasını açın. Genişletme **bildirim aracı** düğümü altında **ortak özellikleri**ve ardından **yalıtılmış COM**.  
  
## <a name="task-list"></a>Görev Listesi  
  
-   [Nasıl Yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Tür kitaplığı dosyası**  
 Bildirim aracı bildirim dosyası oluşturmak için kullanacağı türü kitaplık dosyası (.tlb dosyası) adını belirtmek için TLB seçeneğini kullanır.  
  
 **Kaydedici betik dosyası**  
 Bildirim aracı bildirim dosyası oluşturmak için kullanacağı kayıt komut dosyasını (.rgs dosyası) adını belirtmek için /rgs seçeneğini kullanır.  
  
 **Bileşen dosya adı**  
 Bildirim aracı oluşturacak kaynağın adını belirtmek için / dll seçeneğini kullanır. Bu özellik için bir değer girmelisiniz olduğunda ya da değerleri **türü kitaplık dosyası** veya **Kaydedici betik dosyası** belirtilir.  
  
 **Değişiklik dosyası**  
 .Rgs dosyasındaki değiştirilebilir dizeleri değerlerini içeren dosyanın tam yolunu belirtmek için /replacements seçeneğini kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış uygulamalar](http://msdn.microsoft.com/library/aa375190)   
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)   
 [Bildirim aracı özellik sayfaları](../ide/manifest-tool-property-pages.md)   
 [Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)   