---
title: VC++ Dizinleri Özellik Sayfası
ms.date: 07/17/2019
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
helpviewer_keywords:
- VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
ms.openlocfilehash: 9b005a89156db48615ec6ea8dfc4f07a7414fc3b
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299782"
---
# <a name="vc-directories-property-page-windows"></a>VC + + dizinleri Özellik sayfası (Windows)

Visual Studio 'ya Şu anda seçili olan projeyi oluştururken hangi dizinlerin kullanılacağını bildirmek için bu özellik sayfasını kullanın. Bir çözümdeki birden çok projenin dizinini ayarlamak için, [Visual Studio C++ proje ayarlarını paylaşma veya yeniden kullanma](../create-reusable-property-configurations.md)bölümünde açıklandığı gibi özel bir özellik sayfası kullanın.

Bu sayfanın Linux sürümü için bkz. [VC + + dizinleri (Linux C++)](../../linux/prop-pages/directories-linux.md).

**VC + + dizinleri** Özellik sayfasına erişmek için:

1. **Çözüm Gezgini** pencere görünür değilse, ana menüden **Görünüm** > **Çözüm Gezgini**' i seçin.
1. Proje düğümüne (en üst düzey çözümü değil) sağ tıklayın ve **Özellikler**' i seçin.
1. **Özellik sayfaları** iletişim kutusunun sol bölmesinde **yapılandırma özellikleri** > **VC + + dizinleri**' ni seçin.

VC + + dizinleri özellikleri, en üst düzey çözüm düğümüne değil, bir proje için geçerlidir. **Yapılandırma özellikleri**altında C++ **VC + + dizinleri** ' ni görmüyorsanız, **Çözüm Gezgini** penceresinde bir proje düğümü seçin:

![Proje düğümünü seçin](../media/vcppdir.png "VC + + dizinleri özelliklerini görmek için proje düğümünü seçin")

Platformlar arası projeler için **VC + + dizinleri** Özellik sayfasının farklı göründüğünü unutmayın. Linux C++ projelerine özgü bilgiler için bkz. [VC + + dizinleri (Linux C++)](../../linux/prop-pages/directories-linux.md).

Visual Studio 'da *Proje özellikleri* hakkında bilgi sahibi değilseniz, [Visual Studio 'Da ilk olarak C++ set derleyicisini ve derleme özelliklerini](../working-with-project-properties.md)okumayı yararlı bulabilirsiniz.

**VC + + dizinleri** özellikleri için varsayılan ayarlar proje türüne bağlıdır. Masaüstü projeleri için, C++ belirli bir platform araç takımı ve Windows SDK konumu için Araçlar konumlarını içerirler. **Platform araç takımını** ve **Windows SDK sürümünü** , **yapılandırma özellikleri** > **genel** sayfasında değiştirebilirsiniz.

Dizinlerden herhangi birine ait değerleri görüntülemek için:

1. **VC + + dizinleri** sayfasındaki özelliklerden birini seçin. Örneğin, **kitaplık dizinleri**' ni seçin.
1. Özellik değeri alanının sonundaki aşağı ok düğmesini seçin.
1. Açılan menüde **Düzenle**' yi seçin.

![Kitaplık dizinlerini Düzenle](../media/vcppdir_libdir_edit.png "Kitaplık yollarını düzenleme Iletişim kutusu")

Şimdi şöyle bir iletişim kutusu görürsünüz:

![Kitaplık dizinlerini göster](../media/vcppdir_libdir.png "Kitaplık yollarını ekleme veya kaldırma Iletişim kutusu")

Geçerli dizinleri görüntülemek için bu iletişim kutusunu kullanın. Ancak, bir dizini değiştirmek veya eklemek istiyorsanız, bir özellik sayfası oluşturmak veya varsayılan kullanıcı özellik sayfasını değiştirmek için **Özellik Yöneticisi** kullanmak daha iyidir. Daha fazla bilgi için bkz. [Visual Studio C++ proje ayarlarını paylaşma veya yeniden kullanma](../create-reusable-property-configurations.md).

Yukarıda gösterildiği gibi, devralınan yolların çoğu makro olarak verilir.  Bir makronun geçerli değerini incelemek için iletişim kutusunun sağ alt köşesindeki **makrolar** düğmesini seçin. Birçok makronun yapılandırma türüne bağlı olduğunu unutmayın. Bir hata ayıklama derlemesi içindeki bir makro, bir yayın derlemesi içindeki aynı makrodan farklı bir yol olarak değerlendirilemeyebilir.

Düzenleme kutusunda kısmi veya tamamlanmış eşleşmelerin aranmasını sağlayabilirsiniz. Aşağıdaki çizimde "WindowsSDK" dizesini içeren tüm makrolar gösterilmektedir ve ayrıca makronun değerlendirdiği geçerli yol gösterilmektedir:

![Makro değerlerini gör](../media/vcppdir_libdir_macros.png "Makroları düzenlemek Için Iletişim kutusu")

Not: Liste siz yazarken doldurulur. **ENTER**tuşuna basmayın.

Makrolar hakkında daha fazla bilgi edinmek ve mümkün olan her durumda sabit kodlanmış yollar yerine bunları nasıl kullanmanız gerektiği hakkında daha fazla bilgi için bkz. [Visual Studio 'da derleyici ve derleme özelliklerini ayarlama C++ ](../working-with-project-properties.md).

Yaygın olarak kullanılan makroların listesi için bkz. [derleme komutları ve özellikleri Için ortak makrolar](common-macros-for-build-commands-and-properties.md).

Kendi makrolarınızı iki şekilde tanımlayabilirsiniz:

- Bir geliştirici komut isteminde ortam değişkenlerini ayarlayın. Tüm ortam değişkenleri MSBuild özellikleri/makrolar olarak değerlendirilir.

- Kullanıcı makrolarını bir. props dosyasında tanımlayın. Daha fazla bilgi için bkz. [özellik sayfası makroları](../working-with-project-properties.md).

Daha fazla bilgi için şu blog gönderilerine bakın: [VC + + dizinleri](https://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [devralınan özellikler ve özellik sayfaları](https://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx)ve [Visual Studio 2010 C++ proje yükseltme Kılavuzu](https://devblogs.microsoft.com/cppblog/visual-studio-2010-c-project-upgrade-guide/).

## <a name="directory-types"></a>Dizin Türleri

Ayrıca, aşağıdaki gibi diğer dizinleri de belirtebilirsiniz.

**Yürütülebilir dizinler**<br/>
Yürütülebilir dosyaların aranacağı dizinler. **Path** ortam değişkenine karşılık gelir.

**Ekleme kodu dizinleri**<br/>
Kaynak kodda başvurulan ekleme kodu dosyalarının aranacağı dizinler. **Include** ortam değişkenine karşılık gelir.

**Başvuru dizinleri**<br/>
[#Using](../../preprocessor/hash-using-directive-cpp.md) yönergesi tarafından kaynak kodunda başvurulan derleme ve modül (meta veri) dosyalarının aranacağı dizinler. **LIBPATH** ortam değişkenine karşılık gelir.

**Kitaplık dizinleri**<br/>
Kitaplık (.lib) dosyalarının aranacağı dizinler; çalışma zamanı kitaplıkları da buna dahildir. **LIB** ortam değişkenine karşılık gelir. Bu ayar. obj dosyaları için geçerlidir; bir. obj dosyasına bağlantı sağlamak için, **yapılandırma özellikleri** > **bağlayıcı** > **genel** Özellik sayfasında, **Ek kitaplık bağımlılıkları** ' nı seçin ve sonra dosyanın göreli yolunu belirtin. Daha fazla bilgi için bkz. [bağlayıcı özellik sayfaları](linker-property-pages.md).

**Kitaplık WinRT dizinleri**<br/>
Evrensel Windows Platformu (UWP) uygulamalarında kullanılmak üzere WinRT kitaplığı dosyalarını aramak için dizinler.

**Kaynak dizinler**<br/>
IntelliSense için kullanılacak kaynak dosyaların aranacağı dizinler.

**Dizinleri dışla**<br/>
Her derlemeden önce, Visual Studio önceki derlemeden bu yana herhangi bir değişiklik yapılıp yapılmayacağını anlamak için tüm dosyalardaki zaman damgasını sorgular. Projenizin büyük kararlı kitaplıkları varsa, bu dizinleri zaman damgası denetiminden çıkararak derleme sürelerini hızlandırabilirsiniz.

## <a name="sharing-the-settings"></a>Ayarları Paylaşma

Proje özelliklerini diğer kullanıcılarla veya birden çok bilgisayar arasında paylaşabilirsiniz. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).
