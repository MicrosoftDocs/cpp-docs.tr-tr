---
title: Bildirim Aracı Özellik Sayfaları
ms.date: 07/24/2019
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.SuppressStartupBanner
- VC.Project.VCManifestTool.VerboseOutput
- VC.Project.VCManifestTool.AssemblyIdentity
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.ResourceOutputFileName
- VC.Project.VCManifestTool.GenerateCatalogFiles
- VC.Project.VCManifestTool.ManifestFromManagedAssembly
- VC.Project.VCManifestTool.SuppressDependencyElement
- VC.Project.VCManifestTool.GenerateCategoryTags
- VC.Project.VCManifestTool.EnableDPIAwareness
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.ReplacementsFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- vc.project.AdditionalOptionsPage
ms.assetid: f33499c4-7733-42d9-80e3-8a5018786965
ms.openlocfilehash: e1d0f1ac889cb915216ceb70d48e36efe4ad21bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336305"
---
# <a name="manifest-tool-property-pages"></a>Bildirim Aracı Özellik Sayfaları

[Mt.exe](/windows/win32/sbscs/mt-exe)için genel seçenekleri belirtmek için bu sayfaları kullanın. Bu sayfalar **Proje** > **Özellikleri** > Yapılandırma**Özellikleri** > Bildirim**Aracı**altında bulunur.

## <a name="general-property-page"></a>Genel Özellik Sayfası

### <a name="suppress-startup-banner"></a>Başlangıç Banner'ı bastır

   **Evet (/nologo),** bildirim aracı başlatıldığında standart Microsoft telif hakkı verilerinin gizleneceğini belirtir. Mt.exe'yi bir yapı işleminin parçası olarak veya bir yapı ortamından çalıştırdığınızda, günlük dosyalarındaki istenmeyen çıktıyı bastırmak için bu seçeneği kullanın.

### <a name="verbose-output"></a>Verbose Çıkışı

   **Evet (/tambose)** ek yapı bilgilerinin bildirim oluşturma sırasında görüntüleneceğini belirtir.

### <a name="assembly-identity"></a>Montaj Kimliği

AssemblyIdentity> Öğesi özniteliklerini içeren bir kimlik dizesini belirtmek için /identity seçeneğini kullanır. [ \<](/visualstudio/deployment/assemblyidentity-element-clickonce-application) Kimlik dizesi öznitelik `name` değeriyle başlar ve ardından *öznitelik* = *değer* çiftleri tarafından izlenir. Kimlik dizesindeki öznitelikler virgülle sınırlandırılır.

Bu örnek bir kimlik dizesi:`Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`

## <a name="input-and-output-property-page"></a>Giriş ve Çıkış Özelliği Sayfası

### <a name="additional-manifest-files"></a>Ek Manifesto Dosyaları

Bildirim aracının işleyecek veya birleştireceği ek bildirim dosyalarının tam yollarını belirtmek için **/manifest** seçeneğini kullanır. Tam yollar bir yarı kolon ile sınırlandırılır. (-manifest [manifest1] [manifest2] ...)

### <a name="input-resource-manifests"></a>Giriş Kaynak Bildirimleri

Manifesto aracına giriş yapmak için RT_MANIFEST türünden bir kaynağın tam yolunu belirtmek için **/inputresource** seçeneğini kullanır. Yol, belirtilen kaynak kimliği tarafından izlenebilir. Örneğin:

`dll_with_manifest.dll;#1`

### <a name="embed-manifest"></a>Bildirimi Gömme

- **Evet,** proje sisteminin uygulama bildirimi dosyasını derlemeye gömeceğini belirtir.

- **Proje** sisteminin uygulama bildirimi dosyasını tek başına bir dosya olarak oluşturacağını belirtyoktur.

### <a name="output-manifest-file"></a>Çıktı Bildirimi Dosyası

Çıktı bildirimi dosyasının adını belirtir. Bu özellik, bildirim aracı tarafından yalnızca bir bildirim dosyası işletildiğinde isteğe bağlıdır. (-out:[dosya];#[kaynak kimliği])

### <a name="manifest-resource-file"></a>Manifest Kaynak Dosyası

Bildirimi proje çıktısına yerleştirmek için kullanılan çıktı kaynakları dosyasını belirtir.

### <a name="generate-catalog-files"></a>Katalog Dosyaları Oluşturma

Katalog yapmak için kullanılan katalog tanım dosyaları (.cdf dosyaları) oluşturacağını belirtmek için **/makecdfs** seçeneğini kullanır. (/makecdfs)

### <a name="generate-manifest-from-managedassembly"></a>Yönetilen Montaj'dan Bildirim Oluşturma

Yönetilen bir derlemeden bir bildirim oluşturur. (-yönetilen assemblyname:\[dosya])

### <a name="suppress-dependency-element"></a>Bağımlılık Öğesini Bastırma

-managedassembly ile kullanılır. son bildirimde bağımlılık öğelerinin oluşumunu bastırır. (-nodependency)

### <a name="generate-category-tags"></a>Kategori Etiketleri Oluştur

-managedassembly ile kullanılır. -kategori, kategori etiketlerinin oluşturulmasına neden olur. (-kategori)

### <a name="dpi-awareness"></a>DPI Farkındalık

Uygulamanın DPI farkında olup olmadığını belirtir. Varsayılan olarak, ayar MFC projeleri için **Evet** **ve** aksi takdirde yalnızca MFC projeleri DPI bilinirliği yerleşik olduğundan. Farklı DPI ayarlarını işlemek için kod eklerseniz, ayarı **Evet** olarak geçersiz kılabilirsiniz. Uygulamanız, dpi farkında olarak ayarlarsanız bulanık veya küçük görünebilir.

**Seçenekler**

- **Yok**
- **Yüksek DPI Farkında**
- **Monitör Başına Yüksek DPI Farkında**

## <a name="isolated-com-property-page"></a>Yalıtılmış COM Özellik Sayfası

Yalıtılmış COM hakkında daha fazla bilgi için, [Yalıtılmış Uygulamalar](/windows/win32/SbsCs/isolated-applications) ve [Nasıl Yapılır: COM Bileşenlerini Tüketmek Için Yalıtılmış Uygulamalar Oluşturma](../how-to-build-isolated-applications-to-consume-com-components.md).

### <a name="type-library-file"></a>Tür Kitaplığı Dosyası

Regfree COM bildirim desteği için kullanılacak tür kitaplığını belirtir. (-tlb:[dosya])

### <a name="registrar-script-file"></a>Kayıt Defteri Dosyası Dosyası

Regfree COM bildirim desteği için kullanılacak kayıt defteri dosyasını belirtir. (-rgs:[dosya])

### <a name="component-file-name"></a>Bileşen Dosya Adı

.tlb veya .rgs belirtileninden oluşturulmuş bileşenin dosya adını belirtir. (-dll:[dosya])

### <a name="replacements-file"></a>Değiştirmeler Dosyası

RGS dosyasında değiştirilebilir dizeleri için değerler içeren dosyayı belirtir. (değiştirmeler:[dosya])

## <a name="advanced-property-page"></a>Gelişmiş Özellik Sayfası

### <a name="update-file-hashes"></a>Dosya Hehes'i Güncelleştir

Dosya öğelerinde belirtilen dosyaların karmasını oluşturur ve karma özniteliği bu değerle güncelleştirir. (hashupdate:[yol])

### <a name="update-file-hashes-search-path"></a>Dosya Hashes Arama Yolunu Güncelleştir

Dosya işlemelerini güncellerken kullanılacak arama yolunu belirtir.

### <a name="additional-options"></a>Ek Seçenekler

Ek Seçenekler

## <a name="see-also"></a>Ayrıca bkz.

[C++ proje özelliği sayfası başvurusu](property-pages-visual-cpp.md)
