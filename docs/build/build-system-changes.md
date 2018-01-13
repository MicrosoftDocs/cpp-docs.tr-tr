---
title: "Derleme sistemi değişiklikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.msbuild.changes
dev_langs: C++
helpviewer_keywords:
- Build system changes, project file (.vcxprog)
- Build system changes, custom build rules
- Build system changes, MSBuild
- MSBuild, build system changes
- Build system changes, .vsprops
- Build system changes, $(Inherit)
- Build system changes, $(NoInherit)
ms.assetid: e564d95f-a6cc-4d97-b57e-1a71daf66f4a
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59d30e2afd07c21cb42dbc2b9109d7547d6c5b9f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="build-system-changes"></a>Derleme Sistemi Değişiklikleri
MSBuild sistem Visual C++ projeleri oluşturmak üzere kullanılır. Ancak, Visual Studio 2008 ve önceki sürümleri, VCBuild sistem kullanıldı. Belirli dosya türleri ve üzerinde VCBuild bağımlı olduğu kavramları yok veya geçerli sistemde farklı şekilde gösterilir. Bu belge geçerli yapı sistemi farklılıkları açıklar.  
  
## <a name="vcproj-is-now-vcxproj"></a>.vcproj .vcxproj sunulmuştur  
 Proje dosyaları artık .vcproj dosya adı uzantısı kullanın. Visual Studio, Visual C++ daha önceki bir sürümünün geçerli sistem tarafından kullanılan biçime tarafından oluşturulan proje dosyalarını otomatik olarak dönüştürür. El ile bir projesinin nasıl yükseltileceği hakkında daha fazla bilgi için bkz: [Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe).  
  
 Geçerli sürümde bir proje dosyası için dosya adı uzantısı .vcxproj ' dir.  
  
## <a name="vsprops-is-now-props"></a>.vsprops .props sunulmuştur  
 Önceki sürümlerde bir *proje özellik sayfası* .vsprops dosya adı uzantısına sahip bir XML tabanlı bir dosya değil. Bir proje özellik sayfası derleme araçları derleyici veya bağlayıcı gibi anahtarları belirtin ve kullanıcı tanımlı makrolar oluşturmanıza olanak sağlar.  
  
 Geçerli sürümde, dosya adı uzantısı için bir proje özellik sayfası .props ' dir.  
  
## <a name="custom-build-rules-and-rules-files"></a>Özel derleme kuralları ve .rules dosyaları  
 Önceki sürümlerde bir *kural dosyasını* .rules dosya adı uzantısına sahip bir XML tabanlı bir dosya değil. Kural dosyasının özel derleme kuralları tanımlamak ve bir Visual C++ projesi oluşturma işlemine dahil olanak sağlar. Daha fazla çıkış dosyaları veya bir veya daha fazla dosya adı uzantıları ile ilişkili olabilir, bir özel derleme kural giriş dosyaları bir oluşturan bir aracı geçirmenize olanak sağlar.  
  
 Bu sürümde, özel derleme kuralları üç dosya türleri, .xml, .props ve .rules dosya yerine .targets gösterilir. Visual C++ önceki bir sürümü kullanılarak oluşturulmuş bir .rules dosyası geçerli sürüme geçirildiğinde eşdeğer .xml, .props ve .targets dosyaları oluşturulur ve projenizin özgün .rules dosyası ile birlikte depolanır.  
  
> [!IMPORTANT]
>  Geçerli sürümde, [!INCLUDE[TLA2#tla_ide](../build/includes/tla2sharptla_ide_md.md)] yeni kurallar oluşturulmasını desteklemiyor. Bu nedenle, Visual C++ önceki bir sürümü kullanılarak oluşturulmuş bir projeye ait bir kural dosyasını kullanmak için kolay proje geçerli sürüme geçirmek için yoludur.  
  
## <a name="inheritance-macros"></a>Devralma makroları  
 Önceki sürümlerde **$(ınherit)** makrosu Proje yapı sistem tarafından oluşturulan komut satırında devralınan özellikler görünme sırasını belirtir. **$(Noınherit)** makrosu $(ınherit) göz ardı tüm oluşumlarını neden olur ve devralınması devralınacak değil, tüm özellikleri neden olur. Örneğin, varsayılan olarak $(ınherit) makrosu kullanılarak belirtilen dosyaların neden olur [/ı (ek içeren dizinler)](../build/reference/i-additional-include-directories.md) komut satırına eklenecek derleyici seçeneği.  
  
 Geçerli sürümde, bir veya daha fazla değişmez değerler ve özelliği makroları birleşimini bir özelliğin değerini belirterek devralma desteklenir. **$(Inherit)** ve **$(noınherit)** makroları desteklenmez.  
  
 Aşağıdaki örnekte, noktalı virgülle ayrılmış listesini özellik sayfasında bir özelliğe atanır. Liste birleşimini oluşur  *\<değeri >* hazır değer ve değeri `MyProperty` makrosu gösterimini kullanarak tarafından erişilen özellik **$(**  *MyProperty***)**.  
  
```  
Property=<value>;$(MyProperty)  
```  
  
## <a name="vcxprojuser-files"></a>. vcxproj.user dosyaları  
 Bir kullanıcı dosyası (. vcxproj.user) Örneğin, hata ayıklama ve dağıtım ayarları için kullanıcıya özgü özellikleri depolar. Belirli bir kullanıcı için tüm projeleri vcxproj.user dosya uygular.  
  
## <a name="vcxprojfilters-file"></a>. vcxproj.filters dosyası  
 Zaman **Çözüm Gezgini** filtreleri dosyanın bir proje için bir dosya eklemek için kullanılan (. vcxproj.filters) where tanımlar **Çözüm Gezgini** ağaç görünümü, dosya adı uzantısına göre dosya eklenir.  
  
## <a name="vc-directories-settings"></a>VC ++ dizinleri ayarları  
 Visual C++ dizinleri ayarları üzerinde belirtilir [VC ++ dizinleri özellik sayfası](../ide/vcpp-directories-property-page.md). Visual Studio'nun önceki sürümlerinde, kullanıcı başına dizinleri ayarları uygulamak ve dışlanan dizinler listesinde sysincl.dat dosyasında belirtilir.  
  
 Çalıştırırsanız VC ++ dizinleri ayarlarını değiştiremez [devenv /resetsettings](/visualstudio/ide/reference/resetsettings-devenv-exe) komut satırında. Ayrıca açarsanız ayarlarını değiştiremezsiniz **Araçları** menüsünde tıklatın **içeri ve dışarı aktarma ayarları**ve ardından **tüm ayarlara** seçeneği.  
  
 Visual C++ önceki bir sürümü tarafından oluşturulmuş bir .vssettings dosyasından VC ++ dizinleri ayarlarını geçirme. Açık **Araçları** menüsünde tıklatın **içeri ve dışarı aktarma ayarları**seçin **seçili ortam ayarlarını**ve ardından sihirbazdaki yönergeleri izleyin. Veya üzerinde ilk kez, Visual Studio başlattığınızda **varsayılan ortam ayarlarını seçin** iletişim kutusunda **önceki bir sürümden uygun ayarlarımı geçirmek ve varsayılan ayarlarına ek uygulayın Aşağıda seçili**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)