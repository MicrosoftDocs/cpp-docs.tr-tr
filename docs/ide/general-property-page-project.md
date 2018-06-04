---
title: Genel özellik sayfası (Proje) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.ConfigurationType
- VC.Project.VCConfiguration.ManagedExtensions
- VC.Project.VCConfiguration.BuildBrowserInformation
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.PlatformToolset
- VC.Project.VCConfiguration.TargetName
- VC.Project.VCConfiguration.
- VC.Project.VCConfiguration.TargetExt
- VC.Project.VCConfiguration.ATLMinimizesCRunTimeLibraryUsage
- VC.Project.VCConfiguration.ReferencesPath
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.useOfMfc
- VC.Project.VCConfiguration.CharacterSet
- VC.Project.VCGeneralMakefileSettings.ConfigurationType
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.AppSupport
- VC.Project.VCConfiguration.ToolFiles
- VC.Project.VCConfiguration.useOfATL
dev_langs:
- C++
helpviewer_keywords:
- Clean Build option
- output files, setting directory
- Unicode, creating C++ build configuration
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba98f7d9ed14df1e017f8b83e73cf5d318610f9f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33336498"
---
# <a name="general-property-page-project"></a>Genel Özellik Sayfası (Proje)

Ne zaman, Çözüm Gezgini'nde proje düğümüne sağ tıklatın ve seçin **özellikleri**, **genel** altında özellik sayfası **yapılandırma özellikleri** düğümünde Sol bölmede iki bölüm özellikleri görüntüler:

- Genel

- Proje Varsayılanları

Windows olmayan projeleri için bkz: [Linux C++ özellik sayfası başvurusu](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->.

## <a name="general"></a>Genel

Genel bölümünde özellikleri yapı işleminde oluşturulur ve ne zaman silineceğini dosyaları dosyalarının konumunu etkileyen **temiz** seçeneği (**yapı** menüsü) seçilidir.

**Hedef platformu**  
Proje üzerinde çalışacağı platformu belirtir. Örneğin, Windows, Android veya iOS. Değer **Windows 10** Proje hedefleri Evrensel Windows platformu anlamına gelir. Windows'un önceki sürümlerini hedefleyen, sürüm listelenmeyen ve bu alan değeri olarak yalnızca görünüyorsa **Windows**. Bu bir proje oluşturduğunuzda, ayarlanmış salt okunur bir alandır.

**Windows SDK sürümü**  
Windows hedef platformu için bu projenizin gerektirdiği Windows SDK sürümünü belirtir. Visual Studio Yükleyicisi'ni kullanarak bir C++ iş yükü yüklediğinizde Windows SDK'ın gerekli bölümleri de yüklenir. Diğer Windows SDK sürümü bilgisayarınızda yüklüyse, yüklediğiniz SDK Araçları her sürümü açılır listede görüntülenir.

Windows 7 veya Windows Vista'yı hedefleyecek şekilde değeri kullanmak **8.1**, Windows 8.1 SDK bu platformlar için geriye dönük olarak uyumlu olduğundan. Ayrıca, için uygun değer tanımlamanız gerekir **_WIN32_WINNT** targetver.h içinde. Windows 7, 0x0601'i olmasıdır. Bkz: [WINVER ve _WIN32_WINNT değiştirme](../porting/modifying-winver-and-win32-winnt.md).

Windows XP ve Windows Server 2003 projeler derlemek için kitaplıkları'nın geçerli sürümü kullanmak için Visual Studio'da bulunan Windows XP platform araç takımı yükleyebilirsiniz. Edinme ve bu platform araç takımı kullanma hakkında daha fazla bilgi için bkz: [yapılandırma programlar için Windows XP](../build/configuring-programs-for-windows-xp.md). Platform araç kümesini değiştirme hakkında ek bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

**Hedef Platform Min. Sürüm**  
Proje üzerinde çalışabilir platform en düşük sürümünü belirtir. Bu özellik yalnızca proje türü gibi Windows Evrensel projelerinde destekliyorsa, görüntülenir. Uygulamanızı özelliklerinin daha yeni bir Windows SDK sürümünde yararlanabilirsiniz, ancak yine de bu özellikler olmadan önceki sürümlerinde çalıştırılabilir, belki de işlevsellik, bazı kaybı sonra bu iki özellik değerini farklı olabilir. Bu nedenle, kodunuzu platform sürümü işaretlerseniz karşı çalışma zamanında çalışıyor ve eski platform sürümünde kullanılamaz özelliklerini kullanmaya çalışın değil.

Visual C++ bu seçenek zorlamaz unutmayın. Projenizi kullanan herkes için bir kılavuz olarak ve C# ve JavaScript gibi diğer dilleri ile tutarlılık için dahil edilmiştir. En düşük sürüm kullanılabilir olmayan bir özelliğini kullanırsanız, visual C++ hataya neden olmaz.

**Çıktı dizini**  
Bağlayıcı gibi araçlar oluşturma işlemi sırasında oluşturulan tüm son çıktı dosyaları nerede yerleştirir dizini belirtir. Genellikle, bu bağlayıcı, kitaplığı veya BSCMake gibi araçlar çıktısını içerir. Varsayılan olarak, bu özellik, belirtilen makroları (SolutionDir) $ tarafından (yapılandırma) dizindir \.

Program aracılığıyla bu özelliğe erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.OutputDirectory%2A>.

**Ara dizini**  
Derleyici gibi araçlar oluşturma işlemi sırasında oluşturulan tüm ara dosyaları nerede yerleştirir dizini belirtir. Genellikle, bu C/C++ derleyicisi, MIDL ve kaynak derleyicisi gibi araçları çıktısını içerir. Varsayılan olarak, bu özellik, belirtilen makrosu $(yapılandırma) göre dizindir \.

Program aracılığıyla bu özelliğe erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.IntermediateDirectory%2A>.

**Hedef adı**  
Bu proje oluşturur dosya adını belirtir. Varsayılan olarak, bu özellik makrosu $(ProjectName) tarafından belirtilen dosya adıdır.

**Hedef uzantısı**  
Bu proje oluşturur dosya adı uzantısını belirtir; Örneğin, .exe veya .dll.

**Temiz üzerinde silme uzantıları**  
**Temiz** seçeneği (**yapı** menüsü) bir projenin yapılandırma oluşturulan Burada Ara dizinden dosyaları siler. Bu özellik ile belirtilen uzantılara sahip dosyaları olacaktır ne zaman silinmiş **temiz** çalıştırıldığında veya bir yeniden oluşturma gerçekleştirdiğinizde. Bu uzantılar Ara dizindeki dosyaların yanı sıra, yapı sistem yapı (de dahil olmak üzere ara çıktıların .obj dosyaları gibi) bulunduğu bağımsız olarak bilinen herhangi bir çıktı de silinecek. Joker karakterler belirtebilirsiniz unutmayın.

Program aracılığıyla bu özelliğe erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A>.

**Günlük dosyası oluşturma**  
Bir projeyi derleme her oluşturulan günlük dosyası için bir varsayılan olmayan konum belirtmenize olanak tanır. Varsayılan konumu makroları (IntDir) $$ (MSBuildProjectName) .log tarafından belirtilir.

Proje makroları dizin konumunu değiştirmek için kullanabilirsiniz. Bkz: [derleme komutları ve özellikler için ortak makrolar](../ide/common-macros-for-build-commands-and-properties.md).

**Platform araç takımı**  
Visual C++ kitaplıkları ve derleyici farklı bir sürümünü hedeflemek için projeyi sağlar. Visual C++ projeleri, Visual Studio veya Visual Studio, Windowx XP'de çalıştırabilirsiniz yürütülebilir dosyalar oluşturma toolsets dahil olmak üzere birkaç önceki sürümlerini tarafından yüklenen toolsets biri tarafından yüklenen varsayılan toolset hedefleyebilirsiniz. Platform araç kümesini değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

**Yönetilen Artımlı derleme etkinleştir**  
Derlemeleri oluşturduğunuzda yönetilen projeleri için bu algılama dış görünürlüğü sağlar. Bir yönetilen projenin değişiklik diğer projelerine görünür durumda değilse, ardından bağımlı projeleri yeniden oluşturulur değil. Bu yönetilen projeleri dahil et çözümleri derleme sürelerini önemli ölçüde artırabilir.

## <a name="project-defaults"></a>Proje Varsayılanları

Proje varsayılan Bölümü özelliklerinde değiştirebileceğiniz varsayılan özelliklerini temsil eder. Bu özellikleri tanımı .props dosyalarında bulunabilir *yükleme dizini*\VC\VCProjectDefaults.

**Yapılandırma türü**  
Aralarından seçim yapabileceğiniz çeşitli yapılandırma türleri şunlardır:

- **Uygulama (.exe)**, bağlayıcı araç takımı (C/C++ derleyicisi MIDL, kaynak derleyici, bağlayıcı, BSCMake, XML Web Hizmeti Proxy üreticisi, özel derleme, prebuild, prelink, postbuild olayları) görüntüler.

- **Dinamik kitaplığı (.dll)**, bağlayıcı araç takımı görüntüler, / DLL bağlayıcı seçeneği belirtir ve _WINDLL tanımlamak için CL ekler.

- **Derleme görevleri dosyası**, derleme görevleri dosyası araç takımı (NMake) görüntüler.

- **Statik kitaplık (.lib)**, kitaplığı araç takımı (kitaplığı bağlayıcı için yedek ve XML Web Hizmeti Proxy Oluşturucu atlayın dışında bağlayıcı araç takımı ile aynı) görüntüler.

- **Yardımcı programı**, yardımcı programı araç takımı (MIDL, özel derleme, prebuild postbuild olaylar) görüntüler.

Program aracılığıyla bu özelliğe erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.ConfigurationType%2A>.

**MFC kullanımı**  
MFC projesine statik veya dinamik olarak MFC DLL bağlayacaksınız olup olmadığını belirtir. MFC olmayan projeleri seçebilirsiniz **kullanmak standart Windows kitaplıkları** MFC kullandığınızda dahil çeşitli Win32 kitaplıkları için bağlamak için.

Program aracılığıyla bu özelliğe erişmek için bkz: <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A>.

**ATL Kullanımı**  
ATL Proje statik veya dinamik olarak ATL bağlayacaksınız olup olmadığını belirtir. DLL. Herhangi bir şey dışında belirtirseniz, **değil kullanarak ATL**, tanımlayın derleyicinin eklenecek **komut satırı** özellik sayfası.

Program aracılığıyla bu özelliğe erişmek için bkz: <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfATL%2A>.

**Karakter kümesi**  
_UNICODE veya _MBCS ayarlanmış olup olmadığını tanımlar. Ayrıca bağlayıcı giriş noktası uygun olan yerlerde etkiler.

Program aracılığıyla bu özelliğe erişmek için bkz: <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A>.

**Ortak dil çalışma zamanı desteği**  
Neden [/CLR](../build/reference/clr-common-language-runtime-compilation.md) kullanılacak derleyici seçeneği.

Program aracılığıyla bu özelliğe erişmek için bkz: <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A>.

**.NET hedef Framework sürümü**  
Yönetilen projelerinde hedef .NET framework sürümünü belirtir.

**Bütün Program iyileştirmesi**  
Belirtir [/GL](../build/reference/gl-whole-program-optimization.md) derleyici seçeneği ve [/LTCG](../build/reference/ltcg-link-time-code-generation.md) bağlayıcı seçeneği. Varsayılan olarak, bu hata ayıklama yapılandırmaları için devre dışı ve perakende yapılandırmaları için etkinleştirilmiş.

**Windows mağazası uygulama desteği**  
Bu proje Windows çalışma zamanı (Evrensel Windows platformu) uygulamaları destekleyip desteklemediğini belirtir. Daha fazla bilgi için bkz: [/ZW (Windows çalışma zamanı derlemesi)](../build/reference/zw-windows-runtime-compilation.md)ve Windows Developer Center'da.

## <a name="see-also"></a>Ayrıca bkz.

[Özellik Sayfaları](../ide/property-pages-visual-cpp.md)  