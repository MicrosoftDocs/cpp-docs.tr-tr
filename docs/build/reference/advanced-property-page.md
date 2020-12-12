---
description: 'Daha fazla bilgi edinin: Gelişmiş özellik sayfası'
title: Gelişmiş özellik sayfası (proje)
ms.date: 08/10/2020
f1_keywords:
- VC.Project.VCConfiguration.VCToolsVersion
ms.description: Use the Advanced property page in Visual Studio 2019 to set various properties for C++ projects.
ms.openlocfilehash: 916c1f341d148a0f6b426ddf3c31e0d20c59a29c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187318"
---
# <a name="advanced-property-page"></a>Gelişmiş özellik sayfası

::: moniker range="<=msvc-150"

Gelişmiş özellik sayfası, Visual Studio 2019 ve üzeri sürümlerde kullanılabilir. Bu sürümün belgelerini görmek için bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end

::: moniker range="msvc-160"

Gelişmiş özellik sayfası, Visual Studio 2019 ve üzeri sürümlerde kullanılabilir.

## <a name="advanced-properties"></a>Gelişmiş Özellikler

- **Hedef dosya uzantısı**

   Derleme çıkışı için kullanılacak dosya uzantısını belirtir. Uygulamalar için varsayılan olarak *`.exe`* , *`.lib`* statik kitaplıklar ve *`.dll`* DLL 'ler içindir.

- **Temizlemede Silinecek Uzantılar**

   **Temizleme** seçeneği (**derleme** menüsü), bir projenin yapılandırmasının oluşturulduğu ara dizindeki dosyaları siler. Bu özellikte belirtilen uzantılara sahip dosyalar, **Temizleme** çalıştırıldığında veya yeniden oluşturduğunuzda silinir. Yapı sistemi, bu uzantılara sahip tüm dosyaları ara dizinde siler. Ayrıca, nerede bulunduğuna bakılmaksızın, derleme bilinen tüm çıkışlarını da siler. (Dosyalar gibi ara çıkışları da içerir *`.obj`* .) Bu özellikte joker karakter belirtebilirsiniz.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A> ..

- **Derleme günlüğü dosyası**

   Her proje oluşturduğunuzda oluşturulan günlük dosyası için varsayılan olmayan bir konum belirtmenizi sağlar. Varsayılan konum, makrolarla belirtilir `$(IntDir)$(MSBuildProjectName).log` .

   Dizin konumunu değiştirmek için proje makroları kullanabilirsiniz. Bkz. [derleme komutları ve özellikleri Için ortak makrolar](common-macros-for-build-commands-and-properties.md).

- **Tercih edilen derleme aracı mimarisi**

   X86 veya x64 derleme araçlarının kullanılıp kullanılmayacağını belirtir.

- **Hata ayıklama kitaplıklarını kullan**

   Bir hata ayıklama veya sürüm derlemesi oluşturulup oluşturulmayacağını belirtir.

- **Unity (JUMBO) derlemesini etkinleştir**

   Birden çok C++ kaynak dosyasını derlemeden önce bir veya daha fazla dosyada birleştiren daha hızlı bir yapı işlemi sağlar. Bu Birleşik dosyalar *Unity* dosyaları olarak bilinir. Unity oyun altyapısıyla ilgisi yoktur.

- **Içeriği OutDir öğesine Kopyala**

   Projede *içerik* olarak işaretlenen öğeleri projenin çıkış dizinine ( `$(OutDir)` ) kopyalayın. Bu ayar, dağıtımı basitleştirecek. Bu özellik Visual Studio 2019 sürüm 16,7 ' den başlayarak kullanılabilir.

- **Proje başvurularını OutDir öğesine Kopyala**

   Yürütülebilir (DLL ve EXE dosyası) proje başvuru öğelerini projenin çıkış dizinine ( `$(OutDir)` ) kopyalayın. C++/CLı ( [`/clr`](clr-common-language-runtime-compilation.md) ) projelerinde, bu özellik yok sayılır. Bunun yerine, her bir proje başvurusunun yereli **Kopyala** özelliği, çıkış dizinine kopyalanıp kopyalanmadığını denetler. Bu ayar, yerel dağıtımı basitleştirecek. Visual Studio 2019 sürüm 16,7 ' den itibaren kullanılabilir.

- **Proje başvurularını simgeleri OutDir öğesine Kopyala**

   Proje başvuru öğeleri için PDB dosyalarını proje başvuru yürütülebilir öğeleri ve projenin çıkış dizinine ( `$(OutDir)` ) kopyalayın. Bu özellik her zaman C++/CLı projeleri için etkinleştirilir. Bu ayar, hata ayıklama dağıtımını basitleştirecek. Visual Studio 2019 sürüm 16,7 ' den itibaren kullanılabilir.

- **C++ çalışma zamanını OutDir 'a Kopyala**

   Çalışma zamanı dll 'Lerini projenin çıkış dizinine ( `$(OutDir)` ) kopyalayın. Bu ayar, yerel dağıtımı basitleştirecek. Visual Studio 2019 sürüm 16,7 ' den itibaren kullanılabilir.

- **MFC kullanımı**

   MFC projesinin MFC DLL 'ye statik veya dinamik olarak bağlı olup olmadığını belirtir. MFC olmayan projelerde, MFC 'nin içerdiği Win32 kitaplıklarını bağlamak için **Standart Windows kitaplıklarını kullan** ' ı seçin.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A> ..

- **Karakter kümesi**

   Ayarlanmış olup olmadığını tanımlar `_UNICODE` `_MBCS` . Ayrıca uygun yerlerde bağlayıcı giriş noktasını da etkiler.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A> ..

- **Tüm program Iyileştirmesi**

   [`/GL`](gl-whole-program-optimization.md)Derleyici seçeneğini ve [`/LTCG`](ltcg-link-time-code-generation.md) bağlayıcı seçeneğini belirtir. Varsayılan olarak, tüm program iyileştirmesi hata ayıklama yapılandırmalarında devre dışıdır ve yayın yapılandırmalarına yönelik olarak etkinleştirilir.

- **MSVC araç takımı sürümü**

   Projeyi derlemek için kullanılan MSVC araç takımının tam sürümünü belirtir. Yüklü bir araç takımının çeşitli güncelleştirme ve önizleme sürümlerine sahip olabilirsiniz. Burada kullanmak istediğiniz birini belirtebilirsiniz.

## <a name="ccli-properties"></a>C++/CLı özellikleri

- **Ortak dil çalışma zamanı desteği**

   [`/clr`](clr-common-language-runtime-compilation.md)Derleyici seçeneğinin kullanılmasına neden olur.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A> ..

- **.NET hedef Framework sürümü**

   Yönetilen projelerde, hedeflenen .NET Framework sürümünü belirtir.

- **Yönetilen artımlı derlemeyi etkinleştir**

   Yönetilen projeler için bu seçenek, derlemeler oluştururken dış görünürlüğü algılamayı mümkün bir şekilde sunar. Yönetilen bir projede yapılan bir değişiklik diğer projelere görünür değilse, bağımlı projeler yeniden oluşturulamaz. Yönetilen artımlı derlemeler, yönetilen projeler içeren çözümlerde derleme sürelerini önemli ölçüde iyileştirebilir.

::: moniker-end
