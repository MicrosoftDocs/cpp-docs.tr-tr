---
title: Genel Özellik Sayfası (Proje)
ms.date: 11/04/2016
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
helpviewer_keywords:
- Clean Build option
- output files, setting directory
- Unicode, creating C++ build configuration
ms.openlocfilehash: 5479b892a2cb97fb645dba4ffac70dd9ac4aeffe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594525"
---
# <a name="general-property-page-project"></a>Genel Özellik Sayfası (Proje)

Ne zaman, Çözüm Gezgini'nde bir proje düğümünü sağ tıklatın ve seçin **özellikleri**, **genel** altında özellik sayfası **yapılandırma özellikleri** düğümü sol bölmesinde, özelliklerin iki bölümü görüntülenir:

- Genel

- Proje Varsayılanları

Windows olmayan projeler için bkz: [Linux C++ özellik Sayfa başvurusu](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->.

## <a name="general"></a>Genel

Genel bölümündeki özellikler yapı işlemi sırasında oluşturulan ve hangi dosyaların silineceğini dosyalarının konumunu etkileyen **temiz** seçeneği (**derleme** menüsü) seçilir.

- **Hedef Platform**

   Projenin çalışacağını platformu belirtir. Örneğin, Windows, Android veya iOS. Değer **Windows 10** Evrensel Windows platformu projenizin hedeflediği anlamına gelir. Önceki Windows sürümlerinde hedefleniyorsa, sürüm listelenmeyen ve bu alandaki değer olarak yalnızca görünür **Windows**. Bu, bir proje oluşturduğunuzda, ayarlanan salt okunur bir alandır.

- **Windows SDK sürümü**

   Windows hedef platformu için bu, projenizin gerektirdiği Windows SDK sürümünü belirtir. Visual Studio Yükleyicisi'ni kullanarak bir C++ iş yükünü yüklediğinizde Windows SDK'sı gerekli bölümlerini de yüklenir. Bilgisayarınızda başka Windows SDK sürümleri varsa, her bir sürümünü yüklemiş olduğunuz SDK Araçları açılır listede görüntülenir.

   Windows 7 veya Windows Vista'yı hedeflemek için değerini kullanın. **8.1**, Windows 8.1 SDK'sı, o platformlar için geriye dönük uyumlu olduğundan. Ayrıca, uygun değeri tanımlamalıdır **_WIN32_WINNT** targetver.h içinde. Windows 7 için 0x0601'i olmasıdır. Bkz: [WINVER ve _WIN32_WINNT'de değişiklik yapma](../porting/modifying-winver-and-win32-winnt.md).

   Windows XP ve Windows 2003 Server projeleri derlemek için kitaplıkları'nın geçerli sürümü kullanmak için Visual Studio içinde Windows XP platform araç takımını yükleyebilirsiniz. Edinmek ve bu platform araç takımını kullanmanız konusunda daha fazla bilgi için bkz: [yapılandırma programlar için Windows XP](../build/configuring-programs-for-windows-xp.md). Platform araç kümesini değiştirme hakkında ek bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

- **Hedef Platform Min. Sürüm**

   Projeyi çalıştırmak platformun en düşük sürümünü belirtir. Bu özellik yalnızca proje türü gibi Evrensel Windows projeleri destekliyorsa görünür. Uygulamanızı özelliklerinin daha yeni bir Windows SDK sürümünde yararlanabilirsiniz, ancak yine de bu özellikler olmadan önceki sürümlere çalıştırabilirsiniz, belki de işlevsellik kaybı ile daha sonra bu iki özellik değerini farklı olabilir. Bu nedenle, kodunuzu platformun sürümü onay çalışma zamanında karşı çalışan ve eski platform sürümünde kullanılamayan özelliklerini kullanmayı deneyin değil.

   Visual C++ bu seçeneği zorlamaz unutmayın. Diğer diller, C# ve JavaScript gibi ve projenizi kullanan herkes için bir kılavuz olarak tutarlılık dahildir. En düşük sürümde değil bir özellik kullanırsanız visual C++ hataya neden olmaz.

- **Çıkış dizini**

   Bağlayıcı gibi araçların derleme işlemi sırasında oluşturulan tüm son çıktı dosyalarını koyacağı dizini belirtir. Genellikle bu bağlayıcı, kitaplıkçı veya BSCMake gibi araçların çıktısını içerir. Varsayılan olarak, bu özellik, belirtilen makroları (SolutionDir) $$ (yapılandırma) dizindir \.

   Bu özelliğe program aracılığıyla erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.OutputDirectory%2A>.

- **Ara dizin**

   Derleyici gibi araçların derleme işlemi sırasında oluşturulan tüm ara dosyaları koyacağı dizini belirtir. Genellikle bu C/C++ Derleyici, MIDL ve kaynak derleyicisi gibi araçların çıktısını içerir. Varsayılan olarak, bu özellik, belirtilen makro $(yapılandırma) dizindir \.

   Bu özelliğe program aracılığıyla erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.IntermediateDirectory%2A>.

- **Hedef adı**

   Bu projenin oluşturduğu dosya adını belirtir. Varsayılan olarak, bu özellik makrosu $(ProjectName) tarafından belirtilen dosya adıdır.

- **Hedef uzantısı**

   Bu projenin oluşturduğu dosya adı uzantısını belirtir; Örneğin, .exe veya .dll.

- **Temizlemede silinecek uzantılar**

   **Temiz** seçeneği (**derleme** menüsü) bir projenin yapılandırmasının oluşturulan Burada Ara dizinden dosya siler. Bu özellik ile belirtilmiş uzantılara sahip dosyalar olacaktır ne zaman silinmiş **temiz** çalıştırıldığında veya yeniden derleme yaptığınızda. Ara dizindeki bu uzantılara ait dosyaların yanı sıra, derleme sistemi de (dahil .obj dosyaları gibi ara çıkışlar) bulunduğu yeri bağımsız olarak yapının bilinen çıkışlarını siler. Joker karakterleri belirtebileceğinizi unutmayın.

   Bu özelliğe program aracılığıyla erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A>.

- **Derleme günlüğü dosyası**

   Bir proje oluşturduğunuzda oluşturulan günlük dosyası için bir varsayılan olmayan konum belirtmenizi sağlar. Varsayılan konumu makroları $(IntDir) $(MSBuildProjectName) .log tarafından belirtilir.

   Proje makrolarını, dizin konumunu değiştirmek için kullanabilirsiniz. Bkz: [genel derleme komutları ve Özellikler makroları](../ide/common-macros-for-build-commands-and-properties.md).

- **Platform araç takımı**

   Visual C++ kitaplıklarının ve derleyicinin farklı bir sürümü hedeflemek projeye izin verir. Visual C++ projelerini Visual Studio veya Windowx XP'de çalışabilen yürütülebilir dosyalar oluşturan araç takımları dahil olmak üzere Visual Studio birkaç önceki sürümü yüklüdür araç takımları biri tarafından yüklenen varsayılan araç hedefleyebilirsiniz. Platform araç kümesini değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

- **Yönetilen Artımlı derlemeyi etkinleştir**

   Derlemeleri oluştururken yönetilen projelerde, bu algılama dış görünürlüğü sağlar. Yönetilen bir projeye bir değişiklik diğer projeleri görünür değilse, ardından bağımlı projeleri yeniden oluşturulur değil. Bu, yönetilen projeleri içeren çözümler derleme sürelerini önemli ölçüde artırabilir.

## <a name="project-defaults"></a>Proje Varsayılanları

Proje varsayılanı bölümündeki özellikler değiştirebileceğiniz varsayılan özellikleri temsil eder. Bu özelliklerin tanımı .props dosyalarında bulunabilir *yükleme dizini*\VC\VCProjectDefaults.

- **Yapılandırma türü**

   Aralarından seçim yapılabilecek birkaç yapılandırma türü vardır:

   - **Uygulama (.exe)**

      Bağlayıcı araç takımını (C/C++ Derleyici, MIDL, kaynak derleyici, bağlayıcı, BSCMake, XML Web Hizmeti Proxy üreticisi, özel yapı, prebuild, prelink, postbuild olayları) görüntüler.

   - **Dinamik kitaplık (.dll)**

      Bağlayıcı araç takımını görüntüler, / DLL bağlayıcı seçeneğini belirtir ve _wındll öğesini CL öğesine ekler.

   - **Derleme görevleri dosyası**

      Makefile araç takımını (NMake) görüntüler.

   - **Statik kitaplık (.lib)**

      Kitaplıkçı araç kümesini (bağlayıcı araç takımını, kitaplıkçı bağlayıcı için yedek ve XML Web Hizmeti Proxy üreticisi çıkarın dışında aynı) görüntüler.

   - **yardımcı programı**

      Yardımcı araç takımını (MIDL, özel yapı, prebuild, postbuild olayları) görüntüler.

   Bu özelliğe program aracılığıyla erişmek için bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.ConfigurationType%2A>.

- **MFC'nin kullanımı**

   MFC projesinin statik veya dinamik olarak MFC DLL'sine mı bağlanacağını belirtir. MFC olmayan projeler seçebilirsiniz **standart Windows kitaplıkları kullanın** MFC kullandığınızda, içerdiği çeşitli Win32 kitaplıklarına bağlanması için.

   Bu özelliğe program aracılığıyla erişmek için bkz: <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A>.

- **ATL'nin kullanımı**

   ATL projesini statik veya dinamik olarak için ATL mı bağlanacağını belirtir. DLL. Dışında herhangi bir şey belirtirseniz, **ATL kullanılmıyor**, tanımlama derleyicinin eklenecek **komut satırı** özellik sayfası.

   Bu özelliğe program aracılığıyla erişmek için bkz: <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfATL%2A>.

- **Karakter kümesi**

   _UNICODE veya _MBCS öğesinin ayarlanmış olup olmadığını tanımlar. Ayrıca uygun yerlerde bağlayıcı giriş noktasını etkiler.

   Bu özelliğe program aracılığıyla erişmek için bkz: <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A>.

- **Ortak dil çalışma zamanı desteği**

   Neden [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği kullanılacak.

   Bu özelliğe program aracılığıyla erişmek için bkz: <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A>.

- **.NET hedef Framework sürümü**

   Yönetilen projelerde, hedef .NET framework sürümünü belirtir.

- **Bütün Program iyileştirmesi**

   Belirtir [/GL](../build/reference/gl-whole-program-optimization.md) derleyici seçeneği ve [/LTCG](../build/reference/ltcg-link-time-code-generation.md) bağlayıcı seçeneği. Varsayılan olarak, bu hata ayıklama yapılandırmaları için devre dışı ve perakende yapılandırmaları için etkin.

- **Windows Store uygulaması desteği**

   Bu projenin Windows çalışma zamanı (Evrensel Windows platformu) uygulamalarını destekleyip desteklemediğini belirtir. Daha fazla bilgi için [/ZW (Windows çalışma zamanı derlemesi)](../build/reference/zw-windows-runtime-compilation.md)ve Windows Geliştirici Merkezi.

## <a name="see-also"></a>Ayrıca bkz.

[Özellik Sayfaları](../ide/property-pages-visual-cpp.md)