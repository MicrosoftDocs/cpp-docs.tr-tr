---
title: Gelişmiş özellik sayfası (proje)
ms.date: 07/19/2019
f1_keywords:
- VC.Project.VCConfiguration.VCToolsVersion
ms.description: Use the Advanced property page in Visual Studio 2019 to set various properties for C++ projects.
ms.openlocfilehash: fae3c76d4a62e3b0409664b3630ad76ab601c52b
ms.sourcegitcommit: 610751254a01cba6ad15fb1e1764ecb2e71f66bf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2019
ms.locfileid: "68315521"
---
# <a name="advanced-property-page"></a>Gelişmiş özellik sayfası

Gelişmiş özellik sayfası, Visual Studio 2019 ve üzeri sürümlerde kullanılabilir.

::: moniker range="vs-2019"

## <a name="advanced-properties"></a>Gelişmiş Özellikler

- **Hedef dosya uzantısı**

   Derleme çıkışı için kullanılacak dosya uzantısını belirtir. Uygulamalar için varsayılan olarak **. exe** , statik kitaplıklar için **. lib** ve DLL 'ler için. **DLL** .

- **Temizlemede Silinecek Uzantılar**

   **Temizleme** seçeneği (**derleme** menüsü), bir projenin yapılandırmasının oluşturulduğu ara dizindeki dosyaları siler. Bu özellik ile belirtilen uzantılara sahip dosyalar, **Temizleme** çalıştırıldığında veya yeniden derleme gerçekleştirdiğinizde silinir. Ara dizindeki bu uzantılara ait dosyaların yanı sıra, yapı sistemi, bulunduğu yere bakılmaksızın (. obj dosyaları gibi ara çıktılar dahil olmak üzere) her türlü bilinen çıktıyı da siler. Joker karakterler belirtebilirsiniz.

   Bu özelliğe programlı bir şekilde erişmek için <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A>bkz.

- **Derleme günlüğü dosyası**

   Her proje oluşturduğunuzda oluşturulan günlük dosyası için varsayılan olmayan bir konum belirtmenizi sağlar. Varsayılan konum, makrolar $ (IntDir) $ (MSBuildProjectName). log tarafından belirtilir.

   Dizin konumunu değiştirmek için proje makroları kullanabilirsiniz. Bkz. [derleme komutları ve özellikleri Için ortak makrolar](common-macros-for-build-commands-and-properties.md).

- **Tercih edilen derleme aracı mimarisi**

   X86 veya x64 derleme araçlarının kullanılıp kullanılmayacağını belirtir.

- **Hata ayıklama kitaplıklarını kullan**

   Bir hata ayıklama veya sürüm derlemesi oluşturulup oluşturulmayacağını belirtir.

- **Unity (JUMBO) derlemesini etkinleştir**

   Derleme performansını artırmak üzere derlemeden önce C++ , birçok kaynak dosyanın bir veya daha fazla "Unity" dosyasına birleştirileceği bir yapı işlemini sağlar. Unity oyun altyapısıyla ilgisi yoktur.

- **MFC kullanımı**

   MFC projesinin MFC DLL 'sine statik olarak mı yoksa dinamik olarak mı bağlantı yapıp olmayacağını belirtir. MFC olmayan projeler, MFC kullandığınızda dahil edilen çeşitli Win32 kitaplıklarına bağlantı sağlamak için **Standart Windows kitaplıklarını kullan** ' ı seçebilir.

   Bu özelliğe programlı bir şekilde erişmek için <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A>bkz.

- **Karakter kümesi**

   _UNıCODE veya _MBCS 'nin ayarlanması gerekip gerekmediğini tanımlar. Ayrıca uygun yerlerde bağlayıcı giriş noktasını da etkiler.

   Bu özelliğe programlı bir şekilde erişmek için <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A>bkz.

- **Tüm program Iyileştirmesi**

   [/GL](gl-whole-program-optimization.md) derleyici seçeneğini ve [/LTCG](ltcg-link-time-code-generation.md) bağlayıcı seçeneğini belirtir. Bu, varsayılan olarak hata ayıklama yapılandırmalarında devre dışıdır ve perakende yapılandırmalarda etkinleştirilir.

- **MSVC araç takımı sürümü**

   Projeyi derlemek için kullanılacak MSVC araç takımının tam sürümünü belirtir. Yüklü bir araç takımının çeşitli güncelleştirme ve önizleme sürümlerine sahipseniz, buradan hangisini kullanacağınızı belirtebilirsiniz.

## <a name="ccli-properties"></a>C++/CLı özellikleri

- **Ortak dil çalışma zamanı desteği**

   [/Clr](clr-common-language-runtime-compilation.md) derleyici seçeneğinin kullanılmasına neden olur.

   Bu özelliğe programlı bir şekilde erişmek için <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A>bkz.

- **.NET hedef Framework sürümü**

   Yönetilen projelerde, hedeflenen .NET Framework sürümünü belirtir.

- **Yönetilen artımlı derlemeyi etkinleştir**

   Yönetilen projeler için, bu, derlemeleri oluştururken dış görünürlüğü algılamayı mümkün bir şekilde sunar. Yönetilen bir projede yapılan bir değişiklik diğer projelere görünür değilse, bağımlı projeler yeniden oluşturulamaz. Bu, yönetilen projeler içeren çözümlerde derleme sürelerini önemli ölçüde iyileştirebilir.

::: moniker-end
