---
title: Aracı giriş ve çıkış özellikleri (Visual C++) bildirim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.DependencyInformationFile
- VC.Project.VCManifestTool.OutputResourceManifest
- VC.Project.VCManifestTool.GenerateCatalogFiles
dev_langs:
- C++
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 15be7636188bb670febd7875974d683c1d78360f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33331564"
---
# <a name="input-and-output-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Giriş ve çıkış, bildirim aracı, yapılandırma özellikleri &lt;Projectname&gt; özellik sayfaları iletişim kutusu
Giriş ve çıkış seçeneklerini belirtmek için bu iletişim kutusunu kullanın [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Bu özellik sayfası iletişim kutusu erişmek için özellik sayfaları projenizi veya özellik sayfasını açın. Genişletme **bildirim aracı** düğümü altında **yapılandırma özellikleri**ve ardından **giriş ve çıkış**.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Ek bildirim dosyaları**  
 Kullanan **/bildirimi** seçeneği bildirim aracı işleyecek ek bildirim dosyası ya da birleştirme tam yolunu belirtin. Tam yollar noktalı virgülle ayrılır.  
  
 **Giriş kaynağı bildirimleri**  
 Kullanan **/inputresource** seçeneği bir kaynak türü bildirim aracına giriş RT_MANIFEST, tam yolunu belirtin. Belirtilen kaynak kimliğine göre yolu izlenebilir Örneğin:  
  
 `dll_with_manifest.dll;#1`  
  
 Kaynak Kimliği isteğe bağlıdır ve CREATEPROCESS_MANIFEST_RESOURCE_ID için winuser.h içinde varsayılan olarak.  
  
 **Bildirimi katıştırmak**  
 **Evet** proje sistemi derlemeye uygulama bildirim dosyasının katıştırmak belirtir.  
  
 **Hayır** proje sistemi bağımsız bir dosya olarak uygulama bildirim dosyasının oluşturacağını belirtir.  
  
 **Çıktı bildirim dosyası**  
 Çıktı bildirim dosyasının adını belirtir. Yalnızca bir bildirim dosyası üzerinde bildirim aracı tarafından çalıştırılır, bu özellik isteğe bağlıdır.  
  
 **Bildirim kaynak dosyası**  
 Proje çıktı bildirimi katıştırmak için kullanılan kaynak dosyalarını çıkış belirtir.  
  
 **Katalog dosyaları oluşturma**  
 Kullanan **/makecdfs** bildirim aracı da kataloglar yapmak için kullanılan katalog tanım dosyalarını (.cdf dosyaları) oluşturacak belirtmek için seçeneği.  
  
 **Bildirim ManagedAssembly oluşturmak**  
 Yönetilen bir derlemeden bir bildirim oluşturur. (**- managedassemblyname: *** dosya*).  
  
 **Dependency öğesi gösterme**  
 İle kullanılan **- managedassembly** seçeneği. Bu etiket dependency öğesi son bildiriminde nesil gizler.  
  
 **Kategori etiketleri oluştur**  
 İle kullanılan **- managedassembly** seçeneği. Bu etiket oluşturulacak kategori etiketleri neden olur.  
  
 **DPI tanıma etkinleştir**  
 Uygulama DPI olup olmadığını belirtir. Varsayılan olarak, ayardır **Evet** MFC projeleri için ve **Hayır** yalnızca MFC projeleri DPI tanıma yerleşik olduğundan Aksi takdirde. Ayarı geçersiz kılabilirsiniz **Evet** farklı DPI ayarları işlemek için kod eklerseniz. Uygulamanızı belirsiz veya olmadığında DPI ayarlarsanız küçük görünebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)   
 [Bildirim aracı özellik sayfaları](../ide/manifest-tool-property-pages.md)   
 [Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)   