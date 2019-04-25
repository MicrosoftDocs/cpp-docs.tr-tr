---
title: Bildirim aracı C++ giriş ve çıkış özellikleri
ms.date: 08/27/2018
f1_keywords:
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.DependencyInformationFile
- VC.Project.VCManifestTool.OutputResourceManifest
- VC.Project.VCManifestTool.GenerateCatalogFiles
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
ms.openlocfilehash: 1731665ffa6117896490115028b4744e195beae2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291062"
---
# <a name="input-and-output-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Girdi ve çıktı, bildirim aracı, yapılandırma özellikleri, &lt;Projectname&gt; özellik sayfaları iletişim kutusu

Girdi ve çıktı seçeneklerini belirtmek için bu iletişim kutusunu kullanın [Mt.exe](/windows/desktop/SbsCs/mt-exe).

Bu özellik sayfası iletişim kutusu erişmek için projenizi veya, özellik sayfası için özellik sayfalarını açın. Genişletin **bildirim aracında** düğümünde **yapılandırma özellikleri**ve ardından **giriş ve çıkış**.

## <a name="uielement-list"></a>UIElement Listesi

**Ek bildirim dosyaları**<br/>
Kullanan **/MANIFEST** bildirim aracı işleyecek ek bildirim dosyaları ya da birleştirme tam yollarını belirtmek için seçeneği. Tam yolları, noktalı virgülle ayrılır.

**Giriş kaynağı bildirimleri**<br/>
Kullanan **/inputresource** türü bildirim aracına giriş rt_manıfest, tam yolunu belirtmek için seçeneği. Yol belirtilen kaynak kimliği ile izlenebilir Örneğin:

`dll_with_manifest.dll;#1`

Kaynak Kimliği isteğe bağlıdır ve içinde winuser.h CREATEPROCESS_MANIFEST_RESOURCE_ID için varsayılan.

**Bildirim katıştırma**<br/>
- **Evet** proje sistemi uygulama bildirim dosyasına derlemesine gömmek olduğunu belirtir.

- **Hayır** proje sistemi uygulama bildirim dosyasına bir tek başına dosya olarak oluşturacağını belirtir.

**Çıkış bildirimi dosyası**<br/>
Çıkış bildirimi dosyası adını belirtir. Yalnızca bir bildirim dosyası bildirim aracı tarafından üzerinde çalıştırılır, bu özellik isteğe bağlıdır.

**Bildirim kaynağı dosyası**<br/>
Kaynak dosyaları bildirimi proje çıkışına katıştırmak için kullanılan çıkış belirtir.

**Katalog dosyaları oluştur**<br/>
Kullanan **/makecdfs** seçeneği katalogları yapmak için kullanılan katalog tanımı dosyaları (.cdf dosyaları), bildirim aracı oluşturacağını belirtin.

**ManagedAssembly öğesinden bildirim oluştur**<br/>
Yönetilen derlemeden bir bildirim oluşturur. (**- managedassemblyname:**<em>dosya</em>).

**Bağımlılık öğesini engelle**<br/>
İle kullanılan **- managedassembly** seçeneği. Bu etiket, son bildirimde bağımlılık öğelerini oluşturmayı engeller.

**Kategori etiketlerini oluştur**<br/>
İle kullanılan **- managedassembly** seçeneği. Bu etiket Kategori etiketlerinin oluşturulmasını sağlar.

**DPI tanıma etkinleştir**<br/>
Uygulamanın DPI kullanan olup olmadığını belirtir. Varsayılan ayardır **Evet** MFC projeleri için ve **Hayır** yalnızca MFC projeleri DPI tanıma geliştirdim çünkü aksi takdirde. Ayarı geçersiz kılabilirsiniz **Evet** farklı DPI ayarları işlemek için kod ekler. Uygulamanız belirsiz veya olmadığında DPI kullanan ayarlarsanız küçük görünebilir.

## <a name="see-also"></a>Ayrıca bkz.

[ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)<br/>
[Bildirim Aracı özellik sayfaları](manifest-tool-property-pages.md)<br/>
[Visual Studio’da C++ derleyicisi ve derleme özelliklerini ayarlama](../working-with-project-properties.md)<br/>
