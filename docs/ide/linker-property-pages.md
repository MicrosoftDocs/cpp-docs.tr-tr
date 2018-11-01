---
title: Bağlayıcı Özellik Sayfaları
ms.date: 11/21/2017
f1_keywords:
- VC.Project.VCLinkerTool.RegisterOutput
- VC.Project.VCLinkerTool.OVERWRITEImportLibrary
- VC.Project.VCLinkerTool.UseLibraryDependencyInputs
- VC.Project.VCLinkerTool.LinkLibraryDependencies
helpviewer_keywords:
- per-user redirection
- Linker property pages
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
ms.openlocfilehash: 1ac499d11b1e806a046d7ff9105da43cebcee1af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561596"
---
# <a name="linker-property-pages"></a>Bağlayıcı Özellik Sayfaları

Bu konuda, üzerinde aşağıdaki özellikleri anlatılmaktadır **genel** bağlayıcı özellik sayfası. Bu sayfa Linux sürümü için bkz: [bağlayıcı Özellikleri (Linux C++)](../linux/prop-pages/linker-linux.md).

## <a name="general-page-properties"></a>Genel sayfa özellikleri

### <a name="ignore-import-library"></a>İçeri aktarma kitaplığını yoksay

Bu özellik bu yapının bağımlı bir proje içinde oluşturulan herhangi bir .lib çıktı bağlamayan söyler. Bu, oluşturulduğunda bir .lib dosyası üretmez .dll dosyalarını işlemek proje sistemi sağlar. Bir DLL üreten başka bir projeye bir proje bağlıdır, proje sistemi bu alt proje tarafından üretilen .lib dosyası otomatik olarak bağlar. Bu COM DLL'leri veya yalnızca kaynak DLL'lerine üretme projeleri tarafından gerekmeyebilir; Bu DLL'leri herhangi anlamlı dışarı aktarma yok. Bağlayıcı, DLL hiçbir dışarı varsa, bir .lib dosyası oluşturmaz. Hiçbir dışarı aktarma .lib dosyası disk üzerinde mevcut olduğundan ve proje sistemi ile (eksik) bu DLL'yi bağlamak için söyler, bağlantı başarısız olur. Kullanım **içeri aktarma kitaplığını Yoksay** bu sorunu çözmek için özellik. Ayarlandığında **Evet**, proje sistemi varlığı veya yokluğu bu .lib dosyası yoksayar ve bu proje ile varolmayan .lib dosyası bağlamayan bağımlı projeler neden olur.

Bu özelliğe program aracılığıyla erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>.

### <a name="register-output"></a>Çıkışı Kaydet

Çalıştırmaları `regsvr32.exe /s $(TargetPath)` yapı çıktı, geçerli .dll projelerde. .Exe projeleri için bu özellik yoksayılır. Bir .exe çıkış kaydetmek için postbuild olay her zaman kayıtlı .exe dosyaları için gerekli olan özel bir kayıt yapmak için yapılandırma ayarlayın.

Bu özelliğe program aracılığıyla erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>.

### <a name="per-user-redirection"></a>Bağımsız kullanıcı yönlendirmesi

Visual Studio'da kayıt geleneksel HKEY_CLASSES_ROOT (HKCR) yapılmıştır. Windows Vista ve sonraki işletim sistemleri ile HKCR erişmek için Visual Studio'nun yükseltilmiş modda çalıştırmanız gerekir. Geliştiriciler her zaman yükseltilmiş modda çalıştırmak istemiyorsanız, ancak hala kayıt ile çalışması gerekir. Bağımsız kullanıcı yönlendirmesi, bu modda çalıştırmak zorunda kalmadan kaydetmenize olanak sağlar.

Bağımsız kullanıcı yönlendirmesi için HKEY yönlendirilmesi HKCR herhangi bir yazma zorlar\_geçerli\_kullanıcı (HKCU). Bağımsız kullanıcı yönlendirmesi devre dışı bırakılırsa, neden olabilir [proje derleme hatası PRJ0050](../error-messages/tool-errors/project-build-error-prj0050.md) program için HKCR yazma çalıştığında.

### <a name="link-library-dependencies"></a>Bağlantı kitaplığı bağımlılıkları

Bağımlı projeleri tarafından üretilen .lib dosyaları bağlamak belirtir. Genellikle, .lib dosyaları bağlamak istediğiniz, ancak bu durum belirli DLL'ler için geçerli olmayabilir.

Göreli yol ve dosya adı örneğin sağlayarak bir .obj dosyası da belirtebilirsiniz ".. \\.. \MyLibProject\MyObjFile.obj". .Obj dosyası için kaynak kodu # örneğin pch.h, önceden derlenmiş üst bilgi pch.obj dosyası MyObjFile.obj aynı klasörde bulunur ve pch.obj ek bir bağımlılık olarak da eklemelisiniz includes.

### <a name="use-library-dependency-inputs"></a>Kitaplık bağımlılığı girişlerini kullan

Bağımlı bir proje bir .lib dosyasına oluşturursa, büyük bir projenin artımlı bağlamayı devre dışı bırakıldı. .Lib dosyaları oluşturan birçok bağımlı projeler varsa, uygulama oluşturma, uzun zaman alabilir. Bu özelliği ayarlandığında **Evet**, proje sistemi bağlantıları .libs .obj dosyaları böylece artımlı bağlamasına olanak bağımlı projeleri tarafından üretilen.

Nasıl erişileceği hakkında daha fazla bilgi için **genel** bağlayıcı özellik sayfasında bakın [Working with Project Properties](../ide/working-with-project-properties.md).

## <a name="see-also"></a>Ayrıca bkz.

[VC++ Proje Ayarları, Projeler ve Çözümler, Seçenekler İletişim Kutusu](/visualstudio/ide/reference/vcpp-project-settings-projects-and-solutions-options-dialog-box)<br>
[Özellik Sayfaları](../ide/property-pages-visual-cpp.md)