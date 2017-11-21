---
title: "Bağlayıcı özellik sayfaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.RegisterOutput
- VC.Project.VCLinkerTool.OVERWRITEImportLibrary
- VC.Project.VCLinkerTool.UseLibraryDependencyInputs
- VC.Project.VCLinkerTool.LinkLibraryDependencies
dev_langs: C++
helpviewer_keywords:
- per-user redirection
- Linker property pages
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c958b0bce27effc5362d107a3b6abe9fcc761d39
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-property-pages"></a>Bağlayıcı Özellik Sayfaları
Bu konu, üzerinde aşağıdaki özellikleri açıklar. **genel** bağlayıcı özellik sayfası:  
  
 **İçeri aktarma kitaplığını yoksay**  
 Bu yapı tüm bağımlı projesine üretilen herhangi bir .lib çıktı bağlantı kullanmaya bağlayıcı söyler. Bu yapılandırıldığında .lib dosyası üretmez .dll dosyalarını işlemek proje sistemi sağlar. Bir proje DLL üreten başka bir projeye bağlıdır, proje sistemi otomatik olarak o alt projesi tarafından üretilen .lib dosyası bağlayın. Bu COM DLL veya yalnızca kaynak DLL'ler oluşturan projeleri göre gerekli olmayabilir; Bu DLL'ler herhangi anlamlı dışarı gerekmez. DLL hiçbir dışarı aktarma varsa, bağlayıcı .lib dosyası oluşturmaz. Hiçbir dışa aktarma .lib dosyasının disk üzerinde mevcut olduğundan ve proje sistemi ile birlikte (eksik) bu DLL bağlamak için bağlayıcı söyler, bağlantı başarısız olur.  
  
 Kullanım **yoksay içeri aktarma kitaplığını** bu sorunu gidermek için. Ayarlandığında `Yes`, proje sistemi varlığının veya yokluğunun .lib dosyanın yoksay ve bu proje varolmayan .lib dosyasıyla bağlamayan bağımlı herhangi bir projeye neden.  
  
 Program aracılığıyla bu özelliğe erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>.  
  
 **YAZMAÇ çıktı**  
 Regsvr32.exe yalnızca .dll projelerde geçerli olan /s $(TargetPath) çalıştırın. .Exe projeleri için bu özellik yoksayılır. Bir .exe çıktı kaydetmek istiyorsanız, her zaman kayıtlı .exe dosyaları için gerekli olan özel kaydını yapmak için yapılandırma postbuild olay ayarlayın.  
  
 Program aracılığıyla bu özelliğe erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>.  
  
 **Kullanıcı başına yeniden yönlendirme**  
 Visual Studio'da kayıt HKEY_CLASSES_ROOT (HKCR) geleneksel yapmıştır. İle [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)], Visual Studio yükseltilmiş modda çalıştırmalı HKCR erişmek için. Geliştiriciler, her zaman yükseltilmiş modda çalıştırın istemediğiniz ancak hala kaydı çalışmanız gerekir. Kullanıcı başına yeniden yönlendirme, bu modda çalıştırmak zorunda kalmadan kaydetmenize olanak sağlar.  
  
 Kullanıcı başına yeniden yönlendirme HKCR HKEY_CURRENT_USER (HKCU) yeniden yönlendirilmesi için tüm yazma zorlar. Kullanıcı başına yeniden yönlendirme kapalıysa, neden olabilir [proje derleme hatası PRJ0050](../error-messages/tool-errors/project-build-error-prj0050.md) program HKCR için yazma çalıştığında.  
  
 **Bağlantı kitaplık bağımlılıkları**  
 Bağımlı projeler tarafından üretilen .lib dosyaları bağlama seçmenizi sağlar. Genellikle, .lib dosyasında bağlantı istersiniz.  
  
 Örneğin, göreli yol ve dosya adını sağlayarak .obj dosya belirtebilirsiniz **... \\.. \MyLibProject\MyObjFile.obj**. .Obj dosyası için kaynak kodunu # pch.obj dosyası ile aynı klasörde bulunur sonra Örneğin pch.h, önceden derlenmiş üst bilgi includes **MyObjFile.obj** ve ayrıca eklemelisiniz **pch.obj** ek olarak bağımlılığı.  
  
 **Kitaplık bağımlılık girişleri kullanın**  
 Bağımlı bir proje .lib dosyası vermediğinde büyük bir projede artımlı bağlantılandırma devre dışı bırakılır. .Lib dosyaları üretmek birçok bağımlı projeler varsa, uygulama oluşturma uzun zaman alabilir. Bu özellik ayarlandığında `Yes`, .libs .obj dosyaları proje sistem bağlantıları böylece artımlı bağlantılandırma etkinleştirme bağımlı projeler tarafından üretilen.  
  
 Nasıl erişileceği hakkında bilgi için **genel** bağlayıcı özellik sayfası, bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VC ++ dizinleri, projeler ve çözümler, Seçenekler iletişim kutusu](http://msdn.microsoft.com/en-us/e027448b-c811-4c3d-8531-4325ad3f6e02)   
 [Özellik sayfaları](../ide/property-pages-visual-cpp.md)