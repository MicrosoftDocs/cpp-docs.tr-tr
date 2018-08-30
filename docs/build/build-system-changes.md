---
title: Derleme sistemi değişiklikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- vc.msbuild.changes
dev_langs:
- C++
helpviewer_keywords:
- Build system changes, project file (.vcxprog)
- Build system changes, custom build rules
- Build system changes, MSBuild
- MSBuild, build system changes
- Build system changes, .vsprops
- Build system changes, $(Inherit)
- Build system changes, $(NoInherit)
ms.assetid: e564d95f-a6cc-4d97-b57e-1a71daf66f4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e29d664824a01c0e2a0c0e738368f8d025a239ee
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202163"
---
# <a name="build-system-changes"></a>Derleme Sistemi Değişiklikleri
Visual C++ projeleri derlemek için MSBuild sistemi kullanılır. Ancak, Visual Studio 2008 ve önceki sürümlerde, VCBuild sistemi kullanıldı. Belirli dosya türleri ve üzerinde VCBuild bağımlı kavramları yok veya geçerli sistemde farklı şekilde temsil edilir. Bu belgede, geçerli derleme sistemi farklılıkları açıklar.  
  
## <a name="vcproj-is-now-vcxproj"></a>.vcproj .vcxproj sunulmuştur  
 Proje dosyaları artık .vcproj dosya adı uzantısını kullanın. Visual Studio, Visual C++'ın önceki bir sürümünü geçerli sistemi tarafından kullanılan biçime tarafından oluşturulan proje dosyalarını otomatik olarak dönüştürür. Bir proje el ile yükseltme hakkında daha fazla bilgi için bkz. [Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe).  
  
 Geçerli sürümde, .vcxproj dosya adı uzantısı için bir proje dosyası var.  
  
## <a name="vsprops-is-now-props"></a>.vsprops .props sunulmuştur  
 Önceki sürümlerde bir *proje özellik sayfası* .vsprops dosya adı uzantısına sahip bir XML tabanlı bir dosya. Proje özellik sayfası için derleme araçları gibi derleyici veya bağlayıcı anahtarları belirtin ve kullanıcı tanımlı makrolar oluşturmanıza olanak sağlar.  
  
 Geçerli sürümde .props dosya adı uzantısı için bir proje özellik sayfası var.  
  
## <a name="custom-build-rules-and-rules-files"></a>Özel derleme kuralları ve .rules dosyaları  
 Önceki sürümlerde bir *kural dosyası* .rules dosya adı uzantısına sahip bir XML tabanlı bir dosya. Bir kural dosyası, özel derleme kuralları tanımlayın ve bunları birleştirmenizi Visual C++ projesi derleme işlemine olanak tanır. Daha fazla çıkış dosyalarını veya ilişkili bir veya daha fazla dosya adı uzantılarına sahip olabilir, bir özel derleme kuralının giriş dosyaları birini oluşturan bir araca geçirmek sağlar.  
  
 Bu sürümde, özel derleme kuralları üç dosya türleri, .xml, .props ve .targets, .rules dosyası tarafından temsil edilir. Visual C++'ın önceki bir sürümü kullanılarak oluşturulmuş bir .rules dosyası geçerli sürüme geçiş yaptığında eşdeğer .xml, .props ve .targets dosyaları oluşturulur ve özgün .rules dosyası ile birlikte, projenizdeki depolanır.  
  
> [!IMPORTANT]
>  Geçerli sürümde, IDE, yeni kurallar oluşturulmasını desteklemiyor. Bu nedenle, Visual C++'ın önceki bir sürümü kullanılarak oluşturulmuş bir projeden bir kuralı dosyasını kullanmak için en kolay yolu projeyi geçerli sürüme geçirmek olmaktır.  
  
## <a name="inheritance-macros"></a>Devralma makroları  
 Önceki sürümlerde, **$(ınherit)** makrosu proje sistemi tarafından oluşturulan komut satırında devralınan özellikler görünme sırasını belirtir. **$(Noınherit)** makrosu $(ınherit) sayılmasına tüm oluşumlarını neden olur ve devralınacak devralınacak değil, tüm özellikleri neden olur. Örneğin, varsayılan olarak $(ınherit) makrosu kullanılarak belirtilen dosyaları neden [/ı (ek içeren dizinler)](../build/reference/i-additional-include-directories.md) derleyici seçeneği, komut satırına eklenecek.  
  
 Geçerli sürümde, bir veya daha fazla değişmez değerler ve özelliği makroları birleşimi bir özelliğin değerini belirterek devralma desteklenir. **$(Inherit)** ve **$(noınherit)** makroları desteklenmez.  
  
 Aşağıdaki örnekte, noktalı virgül ile ayrılmış bir listeyi özellik sayfasında bir özelliğine atanır. Liste bitiştirilmiş halini oluşur  *\<değer >* je typu literal a değerini `MyProperty` makrosu gösterimi kullanılarak erişilen özelliği **$(**  <em>MyProperty</em>**)**.  
  
```  
Property=<value>;$(MyProperty)  
```  
  
## <a name="vcxprojuser-files"></a>.vcxproj.user Files  
 Bir kullanıcı dosyası (. vcxproj.user) kullanıcıya özgü özelliklerini, örneğin, hata ayıklama ve dağıtım ayarları depolar. Vcxproj.user dosyanın belirli bir kullanıcı için tüm projeler için geçerlidir.  
  
## <a name="vcxprojfilters-file"></a>.vcxproj.filters File  
 Zaman **Çözüm Gezgini** filtreler dosyası bir projeye bir dosya eklemek için kullanılır (. vcxproj.filters) nerede tanımlar **Çözüm Gezgini** ağaç görünümü, dosya adı uzantısına göre veya dosya eklenir.  
  
## <a name="vc-directories-settings"></a>VC ++ dizinleri ayarları  
 Visual C++ dizinleri ayarları belirtilir [VC ++ Directories Property Page](../ide/vcpp-directories-property-page.md). Visual Studio'nun önceki sürümlerinde, kullanıcı başına dizinleri ayarları uygulamak ve hariç tutulan dizinler listesini sysincl.dat dosyasında belirtilir.  
  
 Çalıştırırsanız, VC ++ dizinleri ayarlarını değiştiremezsiniz [devenv/resetsettings](/visualstudio/ide/reference/resetsettings-devenv-exe) komut satırına. Açarsanız ayarları da değiştiremezsiniz **Araçları** menüsünde tıklatın **içeri ve dışarı aktarma ayarları**ve ardından **tüm ayarları Sıfırla** seçeneği.  
  
 VC ++ dizinleri ayarları önceki bir Visual C++ sürümü tarafından oluşturulmuş bir .vssettings dosyası geçiş. Açık **Araçları** menüsünde tıklatın **içeri ve dışarı aktarma ayarları**seçin **seçili ortam ayarlarını içeri aktarma**ve ardından sihirbazdaki yönergeleri izleyin. Veya üzerinde ilk kez Visual Studio'yu başlattığınızda **varsayılan ortam ayarlarını Seç** iletişim kutusunda **uygun ayarlarımı önceki bir sürümünden geçirme ve bunları ek olarak varsayılan ayarları uygulamak Aşağıda seçili**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)