---
title: Genel Özellik Sayfası (Proje)
ms.date: 07/17/2019
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
ms.openlocfilehash: eaaa2c7428809c05532642b0f9ac53146c6f01a9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924291"
---
# <a name="general-property-page-project"></a>Genel Özellik Sayfası (Proje)

::: moniker range=">=msvc-160"

Bu konu, Windows için Visual Studio projelerine yöneliktir. Linux projeleri için bkz. [Linux C++ Özellik sayfası başvurusu](../../linux/prop-pages-linux.md). CMake projeleri için bkz. [Visual Studio 'Da CMake projeleri](../cmake-projects-in-visual-studio.md). Android projeleri için bkz. [genel proje özellikleri (Android C++)](../../cross-platform/general-android-prop-page.md). Android derleme görevleri dosyası projeleri için bkz. [genel proje özellikleri (Android C++ Makefile)](../../cross-platform/general-makefile-android-prop-page.md)

Çözüm Gezgini ' de bir proje düğümüne sağ tıklayıp **Özellikler** ' i seçtiğinizde, sol bölmedeki **yapılandırma özellikleri** düğümü altındaki **genel** Özellik sayfası şu özellikleri görüntüler:

- **Çıkış dizini**

   Bağlayıcı gibi araçların derleme işlemi sırasında oluşturulan tüm son çıktı dosyalarını yerleşen dizini belirtir. Genellikle, bu, bağlayıcı, kütüphaneian veya BSCMake gibi araçların çıktısını içerir. Varsayılan olarak, bu özellik makrolar $ (SolutionDir) $ (yapılandırma) ile belirtilen dizindir.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.OutputDirectory%2A> ..

- **Ara Dizin**

   Derleyici gibi araçların derleme işlemi sırasında oluşturulan tüm ara dosyaları yerleştireceğinizi belirten dizini belirtir. Genellikle, bu, C/C++ derleyicisi, MıDL ve kaynak derleyicisi gibi araçların çıktısını içerir. Varsayılan olarak, bu özellik, $ (yapılandırma) \ makrosu tarafından belirtilen dizindir.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.IntermediateDirectory%2A> ..

- **Hedef Adı**

   Bu projenin oluşturduğu dosya adını belirtir. Varsayılan olarak bu özellik, Macro $ (ProjectName) tarafından belirtilen dosya adıdır.

- **Yapılandırma türü**

  Aralarından seçim yapabileceğiniz birkaç yapılandırma türü vardır:

  - **Uygulama (. exe)**

     Bağlayıcı araç takımını (C/C++ derleyicisi, MıDL, kaynak derleyicisi, bağlayıcı, BSCMake, XML Web hizmeti proxy Oluşturucusu, özel derleme, ön derleme, ön bağlantı, postbuild olayları) görüntüler.

  - **Dinamik kitaplık (. dll)**

     Bağlayıcı araç takımını görüntüler,/DLL bağlayıcı seçeneğini belirtir ve _WINDLL tanımlar öğesini CL 'ye ekler.

  - **Makefile**

     Makefile araç takımını (NMake) görüntüler.

  - **Statik kitaplık (. lib)**

     Kütüphaneian araç takımını (bağlayıcı araç takımı ile aynı ve XML Web hizmeti proxy oluşturucusunu atla hariç) görüntüler.

  - **Yardımcı Program**

     Utility araç takımını (MıDL, özel derleme, prebuild, postbuild olayları) görüntüler.

  Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.ConfigurationType%2A> ..

- **Windows SDK sürümü**

   Windows hedef platformu için, bu, projenizin gerektirdiği Windows SDK sürümünü belirtir. Visual Studio yükleyicisini kullanarak bir C++ Iş yükü yüklediğinizde Windows SDK gerekli bölümleri de yüklenir. Bilgisayarınızda başka Windows SDK sürümleriniz varsa, yüklediğiniz SDK araçlarının her sürümü açılan menüde görünür.

   Windows 7 veya Windows Vista 'Yı hedeflemek için **8,1** değerini kullanın, çünkü Windows SDK 8,1 Bu platformlarla geriye dönük olarak uyumludur. Ayrıca, targetver. h içinde **_WIN32_WINNT** için uygun değeri tanımlamanız gerekir. Windows 7 için, bu 0x0601 ' dir. Bkz. [WINVER ve _WIN32_WINNT değiştirme](../../porting/modifying-winver-and-win32-winnt.md).

   Windows XP ve Windows 2003 Server projelerini derlemek için, kitaplıkların güncel sürümünü kullanmak üzere Visual Studio 'ya dahil edilen Windows XP platformu araç takımını yükleyebilirsiniz. Bu platform araç takımını edinme ve kullanma hakkında daha fazla bilgi için bkz. [WINDOWS XP Için programları yapılandırma](../configuring-programs-for-windows-xp.md). Platform araç takımını değiştirme hakkında daha fazla bilgi için bkz. [nasıl yapılır: hedef Framework ve platform araç takımını değiştirme](../how-to-modify-the-target-framework-and-platform-toolset.md).

- **Platform araç takımı**

   Projenin Visual C++ kitaplıklarının ve derleyicinin farklı bir sürümünü hedeflemesini sağlar. Visual Studio C++ projeleri, Visual Studio tarafından yüklenen varsayılan araç takımını veya Visual Studio 'nun Windows XP 'de çalışabilen araç kümeleri de dahil olmak üzere birkaç önceki sürümü tarafından yüklenen araç kümelerinden birini hedefleyebilir. Platform araç takımını değiştirme hakkında daha fazla bilgi için bkz. [nasıl yapılır: hedef Framework ve platform araç takımını değiştirme](../how-to-modify-the-target-framework-and-platform-toolset.md).

- **C++ dil standardı**

   Hangi dil standardının kullanılacağını belirtir. Varsayılan değer/std: c++ 14 ' dir. C++ 17 özelliklerini kullanmak için/std: c++ 17 veya C++ 20 veya diğer deneysel özellikleri kullanmak için/std: c++ + latest ' ı belirtin. Daha fazla bilgi için bkz. [/std (dil standart sürümünü belirt)](std-specify-language-standard-version.md)

::: moniker-end

::: moniker range="<=msvc-150"

Visual Studio 2015 ve Visual Studio 2017 ' de, **Çözüm Gezgini** ' de bir proje düğümüne sağ tıklayıp **Özellikler** ' i seçtiğinizde, sol bölmedeki **yapılandırma özellikleri** düğümü altındaki **genel** Özellik sayfası özelliklerin iki bölümünü görüntüler:

- Genel

- Proje Varsayılanları

## <a name="general"></a>Genel

- **Hedef platform**

   Projenin çalışacağı platformu belirtir. Örneğin, Windows, Android veya iOS. **Windows 10** değeri, projenin Evrensel Windows platformu hedeflediği anlamına gelir. Windows 'un önceki sürümlerini hedefliyorsanız, sürüm listelenmez ve bu alandaki değer yalnızca **Windows** olarak görünür. Bu, bir proje oluşturduğunuzda ayarlanmış bir salt okunurdur.

- **Hedef platform sürümü (Visual Studio 2015)**

   Projenin üzerinde çalışacağı platformun en düşük sürümünü belirtir. Bu özellik yalnızca proje türü destekliyorsa görüntülenir. Uygulamanız daha yeni bir Windows SDK sürümündeki özelliklerden yararlanabilir, ancak bu özellikler olmadan önceki sürümlerde çalışmaya devam edebilir, belki de bazı işlevsellik kaybı ile, bu iki özelliğin değeri farklı olabilir. Bu durumda, kodunuz çalışma zamanında çalıştığı platformun sürümünü denetlemelidir ve eski platform sürümünde kullanılamayan özellikleri kullanmayı denemez.

   C++ proje sistemi bu seçeneği zorlamaz. C# ve JavaScript gibi diğer dillerle tutarlılığa ve projenizi kullanan herkese yönelik bir kılavuz olarak dahil edilmiştir. En düşük sürümde kullanılamayan bir özelliği kullanıyorsanız Visual C++ bir hata oluşturmaz.

- **Windows SDK sürümü (Visual Studio 2017)**

   Windows hedef platformu için, bu, projenizin gerektirdiği Windows SDK sürümünü belirtir. Visual Studio yükleyicisini kullanarak bir C++ Iş yükü yüklediğinizde Windows SDK gerekli bölümleri de yüklenir. Bilgisayarınızda başka Windows SDK sürümleriniz varsa, yüklediğiniz SDK araçlarının her sürümü açılan menüde görünür.

   Windows 7 veya Windows Vista 'Yı hedeflemek için **8,1** değerini kullanın, çünkü Windows SDK 8,1 Bu platformlarla geriye dönük olarak uyumludur. Ayrıca, targetver. h içinde **_WIN32_WINNT** için uygun değeri tanımlamanız gerekir. Windows 7 için, bu 0x0601 ' dir. Bkz. [WINVER ve _WIN32_WINNT değiştirme](../../porting/modifying-winver-and-win32-winnt.md).

   Windows XP ve Windows 2003 Server projelerini derlemek için, kitaplıkların güncel sürümünü kullanmak üzere Visual Studio 'ya dahil edilen Windows XP platformu araç takımını yükleyebilirsiniz. Bu platform araç takımını edinme ve kullanma hakkında daha fazla bilgi için bkz. [WINDOWS XP Için programları yapılandırma](../configuring-programs-for-windows-xp.md). Platform araç takımını değiştirme hakkında daha fazla bilgi için bkz. [nasıl yapılır: hedef Framework ve platform araç takımını değiştirme](../how-to-modify-the-target-framework-and-platform-toolset.md).

- **Çıkış dizini**

   Bağlayıcı gibi araçların derleme işlemi sırasında oluşturulan tüm son çıktı dosyalarını yerleşen dizini belirtir. Genellikle, bu, bağlayıcı, kütüphaneian veya BSCMake gibi araçların çıktısını içerir. Varsayılan olarak, bu özellik makrolar $ (SolutionDir) $ (yapılandırma) ile belirtilen dizindir.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.OutputDirectory%2A> ..

- **Ara Dizin**

   Derleyici gibi araçların derleme işlemi sırasında oluşturulan tüm ara dosyaları yerleştireceğinizi belirten dizini belirtir. Genellikle, bu, C/C++ derleyicisi, MıDL ve kaynak derleyicisi gibi araçların çıktısını içerir. Varsayılan olarak, bu özellik, $ (yapılandırma) \ makrosu tarafından belirtilen dizindir.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.IntermediateDirectory%2A> ..

- **Hedef Adı**

   Bu projenin oluşturduğu dosya adını belirtir. Varsayılan olarak bu özellik, Macro $ (ProjectName) tarafından belirtilen dosya adıdır.

- **Hedef uzantısı**

   Bu projenin oluşturduğu dosya adı uzantısını belirtir; Örneğin,. exe veya. dll.

- **Temizlemede Silinecek Uzantılar**

   **Temizleme** seçeneği ( **derleme** menüsü), bir projenin yapılandırmasının oluşturulduğu ara dizindeki dosyaları siler. Bu özellik ile belirtilen uzantılara sahip dosyalar, **Temizleme** çalıştırıldığında veya yeniden derleme gerçekleştirdiğinizde silinir. Ara dizindeki bu uzantılara ait dosyaların yanı sıra, yapı sistemi, bulunduğu yere bakılmaksızın (. obj dosyaları gibi ara çıktılar dahil olmak üzere) her türlü bilinen çıktıyı da siler. Joker karakterler belirtebilirsiniz.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A> ..

- **Derleme günlüğü dosyası**

   Her proje oluşturduğunuzda oluşturulan günlük dosyası için varsayılan olmayan bir konum belirtmenizi sağlar. Varsayılan konum, makrolar $ (IntDir) $ (MSBuildProjectName). log tarafından belirtilir.

   Dizin konumunu değiştirmek için proje makroları kullanabilirsiniz. Bkz. [derleme komutları ve özellikleri Için ortak makrolar](common-macros-for-build-commands-and-properties.md).

- **Platform araç takımı**

   Projenin Visual C++ kitaplıklarının ve derleyicinin farklı bir sürümünü hedeflemesini sağlar. Visual Studio C++ projeleri, Visual Studio tarafından yüklenen varsayılan araç takımını veya Visual Studio 'nun Windows XP 'de çalışabilen araç kümeleri de dahil olmak üzere birkaç önceki sürümü tarafından yüklenen araç kümelerinden birini hedefleyebilir. Platform araç takımını değiştirme hakkında daha fazla bilgi için bkz. [nasıl yapılır: hedef Framework ve platform araç takımını değiştirme](../how-to-modify-the-target-framework-and-platform-toolset.md).

- **Yönetilen artımlı derlemeyi etkinleştir**

   Yönetilen projeler için, bu, derlemeleri oluştururken dış görünürlüğü algılamayı mümkün bir şekilde sunar. Yönetilen bir projede yapılan bir değişiklik diğer projelere görünür değilse, bağımlı projeler yeniden oluşturulamaz. Bu, yönetilen projeler içeren çözümlerde derleme sürelerini önemli ölçüde iyileştirebilir.

## <a name="project-defaults"></a>Proje Varsayılanları

Proje varsayılan bölümündeki özellikler, değiştirebileceğiniz varsayılan özellikleri temsil eder. Bu özelliklerin tanımı, \Vc\vcprojectdefaults. *yükleme dizinindeki* . props dosyalarında bulunabilir.

- **Yapılandırma türü**

  Aralarından seçim yapabileceğiniz birkaç yapılandırma türü vardır:

  - **Uygulama (. exe)**

     Bağlayıcı araç takımını (C/C++ derleyicisi, MıDL, kaynak derleyicisi, bağlayıcı, BSCMake, XML Web hizmeti proxy Oluşturucusu, özel derleme, ön derleme, ön bağlantı, postbuild olayları) görüntüler.

  - **Dinamik kitaplık (. dll)**

     Bağlayıcı araç takımını görüntüler,/DLL bağlayıcı seçeneğini belirtir ve _WINDLL tanımlar öğesini CL 'ye ekler.

  - **Makefile**

     Makefile araç takımını (NMake) görüntüler.

  - **Statik kitaplık (. lib)**

     Kütüphaneian araç takımını (bağlayıcı araç takımı ile aynı ve XML Web hizmeti proxy oluşturucusunu atla hariç) görüntüler.

  - **Yardımcı Program**

     Utility araç takımını (MıDL, özel derleme, prebuild, postbuild olayları) görüntüler.

  Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.ConfigurationType%2A> ..

- **MFC kullanımı**

   MFC projesinin MFC DLL 'sine statik olarak mı yoksa dinamik olarak mı bağlantı yapıp olmayacağını belirtir. MFC olmayan projeler, MFC kullandığınızda dahil edilen çeşitli Win32 kitaplıklarına bağlantı sağlamak için **Standart Windows kitaplıklarını kullan** ' ı seçebilir.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A> ..

- **Karakter kümesi**

   _UNICODE veya _MBCS ayarlanması gerekip gerekmediğini tanımlar. Ayrıca uygun yerlerde bağlayıcı giriş noktasını da etkiler.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A> ..

- **Ortak dil çalışma zamanı desteği**

   [/Clr](clr-common-language-runtime-compilation.md) derleyici seçeneğinin kullanılmasına neden olur.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A> ..

- **.NET hedef Framework sürümü**

   Yönetilen projelerde, hedeflenen .NET Framework sürümünü belirtir.

- **Tüm program Iyileştirmesi**

   [/GL](gl-whole-program-optimization.md) derleyici seçeneğini ve [/LTCG](ltcg-link-time-code-generation.md) bağlayıcı seçeneğini belirtir. Bu, varsayılan olarak hata ayıklama yapılandırmalarında devre dışıdır ve perakende yapılandırmalarda etkinleştirilir.

- **Windows Mağazası uygulama desteği**

   Bu projenin Windows Çalışma Zamanı (Evrensel Windows Platformu) uygulamalarını destekleyip desteklemediğini belirtir. Daha fazla bilgi için bkz. [/ZW (Windows çalışma zamanı derlemesi)](zw-windows-runtime-compilation.md)ve Windows Geliştirici Merkezi.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[C++ proje özellik sayfası başvurusu](property-pages-visual-cpp.md)
