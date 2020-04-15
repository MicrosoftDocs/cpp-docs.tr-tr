---
title: Gelişmiş Özellik Sayfası (Proje)
ms.date: 07/19/2019
f1_keywords:
- VC.Project.VCConfiguration.VCToolsVersion
ms.description: Use the Advanced property page in Visual Studio 2019 to set various properties for C++ projects.
ms.openlocfilehash: 8ce62b768f5cda30501e791bcd040a40b18bfb23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328420"
---
# <a name="advanced-property-page"></a>Gelişmiş Özellik Sayfası

Advanced özellik sayfası Visual Studio 2019 ve sonraki yıllarda kullanılabilir.

::: moniker range="vs-2019"

## <a name="advanced-properties"></a>Gelişmiş Özellikler

- **Hedef Dosya Uzantısı**

   Yapı çıktısı için kullanılacak dosya uzantısını belirtir. Uygulamalar için **.exe,** statik kitaplıklar için **.lib** ve DL'ler için **.dll** varsayılanları.

- **Temizle'de Silinecek Uzantılar**

   **Temizle** seçeneği **(Ekle** menüsü) dosyaları projenin yapılandırmasının oluşturulduğu ara dizinden siler. Bu özellik ile belirtilen uzantıları olan dosyalar **Temiz** çalıştırıldığında veya yeniden oluşturma gerçekleştirdiğinizde silinir. Yapı sistemi, ara dizindeki bu uzantıların dosyalarına ek olarak, bulunduğu yere bakılmaksızın (.obj dosyaları gibi ara çıktılar dahil) yapının bilinen tüm çıktılarını da siler. Joker karakter belirtebileceğinizi unutmayın.

   Bu özelliğe programlı olarak <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A>erişmek için bkz.

- **Günlük Dosyası Oluştur**

   Bir proje oluşturduğunuzda oluşturulan günlük dosyası için varsayılan olmayan bir konum belirtmenizi sağlar. Varsayılan konum makrolar tarafından belirtilir $(IntDir)$(MSBuildProjectName).log.

   Dizin konumunu değiştirmek için proje makrolarını kullanabilirsiniz. [Yapı komutları ve özellikleri için ortak makrolara](common-macros-for-build-commands-and-properties.md)bakın.

- **Tercih Edilen Yapı Aracı Mimarisi**

   X86 veya x64 yapı araçlarının kullanılıp kullanılmayacağını belirtir.

- **Hata Ayıklama Kitaplıklarını Kullanma**

   Bir HATA VEYA RELEASE yapı oluşturmak için olup olmadığını belirtir.

- **Birlik (JUMBO) oluşturmayı etkinleştirin**

   Yapı performansını artırmak için derlemeden önce birçok C++ kaynak dosyasının bir veya daha fazla "birlik" dosyasında biraraya geldiği bir yapı işlemini sağlar. Unity oyun motoru ile ilgisi yok.

- **MFC kullanımı**

   MFC projesinin MFC DLL'ye statik veya dinamik olarak bağlanıp bağlanmayacağını belirtir. MFC olmayan projeler, MFC'yi kullandığınızda dahil edilen çeşitli Win32 kitaplıklarına bağlanmak için **Standart Windows Kitaplıklarını Kullan'ı** seçebilir.

   Bu özelliğe programlı olarak <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A>erişmek için bkz.

- **Karakter Seti**

   _UNICODE veya _MBCS ayarlanıp ayarlanmayacağını tanımlar. Ayrıca, uygun olduğu durumlarda bağlayıcı giriş noktasını da etkiler.

   Bu özelliğe programlı olarak <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A>erişmek için bkz.

- **Tüm Program Optimizasyonu**

   [/GL](gl-whole-program-optimization.md) derleyici seçeneğini ve [/LTCG](ltcg-link-time-code-generation.md) bağlayıcı seçeneğini belirtir. Varsayılan olarak, bu Hata Ayıklama yapılandırmaları için devre dışı bırakılır ve Perakende yapılandırmaları için etkinleştirilir.

- **MSVC Araç Seti Sürümü**

   Projeyi oluşturmak için kullanılacak MSVC araç kümesinin tam sürümünü belirtir. Bir araç setinin çeşitli güncelleştirme ve önizleme sürümleri yüklüyse, burada hangisini kullanacağınızı belirtebilirsiniz.

## <a name="ccli-properties"></a>C++/CLI Özellikleri

- **Ortak Dil Runtime desteği**

   [/clr](clr-common-language-runtime-compilation.md) derleyici seçeneğinin kullanılmasına neden olur.

   Bu özelliğe programlı olarak <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A>erişmek için bkz.

- **.NET Hedef Çerçeve Sürümü**

   Yönetilen projelerde, .NET çerçeve sürümünü hedeflemek için belirtir.

- **Yönetilen Artımlı Yapıyı Etkinleştir**

   Yönetilen projeler için bu, derlemeler oluşturduğunuzda dış görünürlüğün algılanmasını sağlar. Yönetilen bir projede yapılan bir değişiklik diğer projeler tarafından görülemezse, bağımlı projeler yeniden oluşturulmaz. Bu, yönetilen projeleri içeren çözümlerde yapı sürelerini önemli ölçüde artırabilir.

::: moniker-end
