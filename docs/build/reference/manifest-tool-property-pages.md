---
title: Bildirim Aracı Özellik Sayfaları
ms.date: 7/24/2019
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
ms.openlocfilehash: c8413a28024361db82ca74858453202393987e60
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492697"
---
# <a name="manifest-tool-property-pages"></a>Bildirim Aracı Özellik Sayfaları

Bu sayfaları, [mt. exe](/windows/win32/sbscs/mt-exe)için genel seçenekleri belirtmek üzere kullanın. Bu sayfalar **Proje** > **özellikleri** > **yapılandırma**özellikleribildirim > **Aracı**altında bulunur.

## <a name="general-property-page"></a>Genel özellik sayfası

### <a name="suppress-startup-banner"></a>Başlangıç başlığını gösterme

   **Evet (/nologo)** bildirim aracı başlatıldığında standart Microsoft telif hakkı verilerinin yeniden açılıp başlatılmadığını belirtir. Bu seçeneği, bir yapı işleminin parçası olarak mt. exe ' yi veya bir yapı ortamını çalıştırdığınızda günlük dosyalarında istenmeyen çıktıyı bastırmak için kullanın.

### <a name="verbose-output"></a>Ayrıntılı çıkış

   **Evet (/verbose)** bildirim oluşturma sırasında ek derleme bilgilerinin gösterileceğini belirtir.

### <a name="assembly-identity"></a>Derleme kimliği * *

AssemblyIdentity > öğesi için [ \<](/visualstudio/deployment/assemblyidentity-element-clickonce-application)öznitelikleri içeren bir kimlik dizesi belirtmek için/Identity seçeneğini kullanır. Bir kimlik `name` dizesi, öznitelik değeri ile başlar ve ardından *öznitelik* = *değeri* çiftleri gelir. Bir kimlik dizesindeki öznitelikler virgülle ayrılır.

Bu örnek bir kimlik dizesidir:`Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`

## <a name="input-and-output-property-page"></a>Giriş ve çıkış Özellik sayfası     

###  <a name="additional-manifest-files"></a>Ek bildirim dosyaları

Bildirim Aracı tarafından işlenecek veya birleştirilecek ek bildirim dosyalarının tam yollarını belirtmek için **/MANIFEST** seçeneğini kullanır. Tam yollar noktalı virgülle ayrılır. (-manifest [manifest1] [manifest2]...)

###  <a name="input-resource-manifests"></a>Giriş kaynağı bildirimleri

, Bildirim aracına girmek için RT_MANIFEST türünde bir kaynağın tam yolunu belirtmek için **/ınputresource** seçeneğini kullanır. Yolun ardından belirtilen kaynak KIMLIĞI gelebilir. Örneğin:

`dll_with_manifest.dll;#1`

###  <a name="embed-manifest"></a>Ekleme bildirimi

- **Evet** , proje sisteminin uygulama bildirim dosyasını derlemeye katıştırabelirtir.

- **Hayır** , proje sisteminin uygulama bildirim dosyasını tek başına bir dosya olarak oluşturulacağını belirtir.

###  <a name="output-manifest-file"></a>Çıkış bildirimi dosyası

Çıkış bildirimi dosyasının adını belirtir. Bildirim Aracı tarafından üzerinde yalnızca bir bildirim dosyası çalıştırıldığında, bu özellik isteğe bağlıdır. (-out: [dosya]; # [kaynak KIMLIĞI])

###  <a name="manifest-resource-file"></a>Bildirim kaynak dosyası

Bildirimi proje çıkışına katıştırmak için kullanılan çıkış kaynakları dosyasını belirtir.

###  <a name="generate-catalog-files"></a>Katalog dosyaları oluştur

Bildirim aracının, katalog oluşturmak için kullanılan Katalog tanım dosyalarını (. CDF dosyaları) üretkullanacağını belirtmek için **/makecdfs** seçeneğini kullanır. /makecdfs

###  <a name="generate-manifest-from-managedassembly"></a>ManagedAssembly öğesinden bildirim oluştur

Yönetilen bir derlemeden bir bildirim oluşturur. (-managedassemblyname: [dosya])

###  <a name="suppress-dependency-element"></a>Bağımlılık öğesini gizle

-Managedassembly ile kullanılır. Son bildirimdeki bağımlılık öğelerinin oluşturulmasını engeller. (-nodependency)

###  <a name="generate-category-tags"></a>Kategori Etiketleri Oluştur

-Managedassembly ile kullanılır. -Kategori, kategori etiketlerinin oluşturulmasına neden olur. (-kategori)

###  <a name="dpi-awareness"></a>DPı tanıma

Uygulamanın DPı duyarlı olup olmadığını belirtir. Varsayılan olarak, bu ayar MFC projeleri için **Evet** ' tir , aksi takdırde yalnızca MFC projeleri DPI tanıma göre oluşturulmuştur. Farklı DPı ayarlarını işleyecek kod eklerseniz, ayarı **Evet** olarak geçersiz kılabilirsiniz. Uygulamanız, değilse, bir belirsiz veya küçük görünebilir.

**Yapabileceği**

- **Yok.**
- **Yüksek DPı kullanan**
- **Monitör başına yüksek DPı kullanan**

## <a name="isolated-com-property-page"></a>Yalıtılmış COM özellik sayfası

Yalıtılmış com hakkında daha fazla bilgi için bkz. [Yalıtılmış uygulamalar](/windows/win32/SbsCs/isolated-applications) ve [nasıl yapılır: COM bileşenlerini](../how-to-build-isolated-applications-to-consume-com-components.md)tüketmek için yalıtılmış uygulamalar oluşturun.

###  <a name="type-library-file"></a>Tür kitaplığı dosyası

RegFree COM bildirim desteği için kullanılacak tür kitaplığını belirtir. (-tlb: [dosya])

###  <a name="registrar-script-file"></a>Kaydedici betik dosyası

RegFree COM bildirim desteği için kullanılacak kaydedici betik dosyasını belirtir. (-RGS: [dosya])

###  <a name="component-file-name"></a>Bileşen dosyası adı

Belirtilen. tlb veya. RGS tarafından oluşturulan bileşenin dosya adını belirtir. (-dll: [dosya])

###  <a name="replacements-file"></a>Değişiklik dosyası

RGS dosyasındaki değiştirilebilen dizelerin değerlerini içeren dosyayı belirtir. (değişiklikler: [dosya])

## <a name="advanced-property-page"></a>Gelişmiş özellik sayfası

###  <a name="update-file-hashes"></a>Dosya karmalarını güncelleştirme

Dosya öğelerinde belirtilen dosyaların karmasını hesaplar ve karma özniteliğini bu değerle güncelleştirir. (hashupdate: [yol])

###  <a name="update-file-hashes-search-path"></a>Dosya karma arama yolunu Güncelleştir

Dosya karmalarını güncelleştirirken kullanılacak arama yolunu belirtir.

###  <a name="additional-options"></a>Ek seçenekler

Ek seçenekler


## <a name="see-also"></a>Ayrıca bkz.

[C++Proje özellik sayfası başvurusu](property-pages-visual-cpp.md)
