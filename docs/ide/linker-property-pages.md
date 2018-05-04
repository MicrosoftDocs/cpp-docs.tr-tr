---
title: Bağlayıcı özellik sayfaları | Microsoft Docs
ms.custom: ''
ms.date: 11/21/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-ide
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.RegisterOutput
- VC.Project.VCLinkerTool.OVERWRITEImportLibrary
- VC.Project.VCLinkerTool.UseLibraryDependencyInputs
- VC.Project.VCLinkerTool.LinkLibraryDependencies
dev_langs:
- C++
helpviewer_keywords:
- per-user redirection
- Linker property pages
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 31b44b6711153d29ab6a9c542a6e5677e6279432
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="linker-property-pages"></a>Bağlayıcı Özellik Sayfaları

Bu konu, üzerinde aşağıdaki özellikleri açıklar. **genel** bağlayıcı özellik sayfası. Bu sayfayı Linux sürümü için bkz: [bağlayıcı Özellikleri (Linux C++)](../linux/prop-pages/linker-linux.md).

## <a name="general-page-properties"></a>Genel sayfa özellikleri

### <a name="ignore-import-library"></a>İçeri aktarma kitaplığını yoksay

Bu özellik bu yapıdan tüm bağımlı projesine oluşturulan herhangi bir .lib çıktı bağlamayan için bağlayıcı söyler. Bu yapılandırıldığında .lib dosyası üretmez .dll dosyalarını işlemek proje sistemi sağlar. Bir proje DLL üreten başka bir projeye bağlıdır, proje sistemi o alt projesi tarafından üretilen .lib dosyası otomatik olarak bağlar. Bu COM DLL veya yalnızca kaynak DLL'ler oluşturan projeleri göre gerekli olmayabilir; Bu DLL'ler herhangi anlamlı dışarı gerekmez. DLL hiçbir dışarı aktarma varsa, bağlayıcı .lib dosyası oluşturmaz. Hiçbir dışa aktarma .lib dosyasının disk üzerinde mevcut olduğundan ve bu (eksik) DLL ile bağlamak için bağlayıcı proje sistemi söyler, bağlantı başarısız olur. Kullanım **yoksay içeri aktarma kitaplığını** bu sorunu gidermek için özellik. Ayarlandığında **Evet**, proje sistemi varlığının veya yokluğunun .lib dosyanın yoksayar ve bu proje varolmayan .lib dosyasıyla bağlamayan bağımlı herhangi bir projeye neden olur.

Program aracılığıyla bu özelliğe erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>.

### <a name="register-output"></a>YAZMAÇ çıktı

Çalıştırır `regsvr32.exe /s $(TargetPath)` yapı Çıkışta olduğu yalnızca .dll projelerde geçerli. .Exe projeleri için bu özellik yoksayılır. Bir .exe çıktı kaydetmek için her zaman kayıtlı .exe dosyaları için gerekli olan özel kaydını yapmak için yapılandırma postbuild olay ayarlayın.

Program aracılığıyla bu özelliğe erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>.

### <a name="per-user-redirection"></a>Kullanıcı başına yeniden yönlendirme

Visual Studio'da kayıt HKEY_CLASSES_ROOT (HKCR) geleneksel yapmıştır. HKCR erişmek için Windows Vista ve sonraki işletim sistemleri ile Visual Studio yükseltilmiş modda çalıştırmanız gerekir. Geliştiriciler, her zaman yükseltilmiş modda çalıştırın istemediğiniz ancak hala kaydı çalışmanız gerekir. Kullanıcı başına yeniden yönlendirme, bu modda çalıştırmak zorunda kalmadan kaydetmenize olanak sağlar.

Kullanıcı başına yeniden yönlendirme için HKEY yönlendirilecek HKCR herhangi yazma zorlar\_geçerli\_kullanıcı (HKCU). Kullanıcı başına yeniden yönlendirme kapalıysa, neden olabilir [proje derleme hatası PRJ0050](../error-messages/tool-errors/project-build-error-prj0050.md) program HKCR için yazma çalıştığında.

### <a name="link-library-dependencies"></a>Bağlantı kitaplık bağımlılıkları

Bağımlı projeler tarafından üretilen .lib dosyaları bağlamak belirtir. Genellikle, .lib dosyaları bağlamak istediğiniz, ancak bu durumda belirli DLL'ler için geçerli olmayabilir.

Örneğin, göreli yol ve dosya adını sağlayarak .obj dosya belirtebilirsiniz ".. \\.. \MyLibProject\MyObjFile.obj". .Obj dosyası için kaynak kodunu # örneğin pch.h, önceden derlenmiş üst bilgi includes pch.obj dosyası MyObjFile.obj ile aynı klasörde bulunur ve pch.obj ek bir bağımlılık olarak da eklemelisiniz.

### <a name="use-library-dependency-inputs"></a>Kitaplık bağımlılık girişleri kullanın

Bağımlı bir proje .lib dosyası vermediğinde büyük bir projede artımlı bağlantılandırma devre dışı bırakılır. .Lib dosyaları üretmek birçok bağımlı projeler varsa, uygulama oluşturma uzun zaman alabilir. Bu özellik ayarlandığında **Evet**, .libs .obj dosyaları proje sistem bağlantıları böylece artımlı bağlantılandırma etkinleştirme bağımlı projeler tarafından üretilen.

Nasıl erişileceği hakkında bilgi için **genel** bağlayıcı özellik sayfası, bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).

## <a name="see-also"></a>Ayrıca bkz.

[VC ++ proje ayarları, projeler ve çözümler, Seçenekler iletişim kutusu](/visualstudio/ide/reference/vcpp-project-settings-projects-and-solutions-options-dialog-box)  
[Özellik Sayfaları](../ide/property-pages-visual-cpp.md)  