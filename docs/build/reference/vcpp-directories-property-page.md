---
title: VC++ Dizinleri Özellik Sayfası
ms.date: 10/09/2018
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
ms.openlocfilehash: aff143fca47cb5958b90e4a3f4c7ec284f2129f5
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861054"
---
# <a name="vc-directories-property-page-windows"></a>VC ++ dizinleri özellik sayfası (Windows)

Visual Studio şu anda seçili proje oluşturma sırasında kullanmak için hangi dizinleri bildirmek için bu özellik sayfasını kullanın. Bir çözümde birden çok proje için dizinleri ayarlamak için bir özel özellik sayfası ölçeklendirmesini kullanacak [paylaşımını veya yeniden Visual Studio C++ proje ayarları](../create-reusable-property-configurations.md).

Bu sayfa Linux sürümü için bkz: [VC ++ dizinleri (Linux C++)](../../linux/prop-pages/directories-linux.md).

Erişim için **VC ++ dizinleri** özellik sayfası:

1. Varsa **Çözüm Gezgini** penceresi görünür değilse, ana menüden seçin **görünümü** > **Çözüm Gezgini**.
1. Bir proje düğümü (en üst düzey çözümü değil) sağ tıklatın ve seçin **özellikleri**.
1. Sol bölmesinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri** > **VC ++ dizinleri**.

VC ++ dizinleri özellikleri, üst düzey çözüm düğümüne bir proje için geçerlidir. Görmüyorsanız, **VC ++ dizinleri** altında **yapılandırma özellikleri**, bir C++ projesi düğümünde seçin **Çözüm Gezgini** penceresi:

![Proje düğümünü seçin](../media/vcppdir.png "VC ++ dizinleri özellikleri görmek için proje düğümünü seçin")

Unutmayın **VC ++ dizinleri** farklı platformlar arası projeler için özellik sayfası görünür. Linux C++ projelerine özgü bilgiler için bkz: [VC ++ dizinleri (Linux C++)](../../linux/prop-pages/directories-linux.md).

İle aşina değilseniz *proje özellikleri* Visual Studio'da ilk okuma için yararlı [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

İçin varsayılan ayarları **VC ++ dizinleri** özellikleri proje türüne bağlıdır. Masaüstü projeleri için C++ araçlarının konumları için belirli bir Platform araç takımını ve Windows SDK'sı konumu içerirler. Değiştirebileceğiniz **Platform araç takımını** ve **Windows SDK sürümü** üzerinde **yapılandırma özellikleri** > **genel** Sayfa.

Tüm dizinlerin değerlerini görüntülemek için:

1. Özelliklerinde birini **VC ++ dizinleri** sayfası. Örneğin, **kitaplık dizinleri**.
1. Özellik değeri alanı sonundaki aşağı ok düğmesini seçin.
1. Aşağı açılan menüsünde **Düzenle**.

![Kitaplık dizinleri Düzenle](../media/vcppdir_libdir_edit.png "kitaplık yollarını düzenlemek için iletişim kutusu")

Artık böyle bir iletişim kutusu görürsünüz:

![Kitaplık dizinleri Göster](../media/vcppdir_libdir.png "eklemek veya kitaplık yollarını kaldırmak için iletişim kutusu")

Geçerli dizinleri görüntülemek için bu iletişim kutusunu kullanın. Bir dizin eklemek veya değiştirmek istiyorsanız, ancak bunu kullanmak en iyisidir **özellik Yöneticisi** bir özellik sayfası oluşturma veya varsayılan kullanıcı özellik sayfası değiştirmek için. Daha fazla bilgi için [paylaşımını veya yeniden Visual Studio C++ proje ayarları](../create-reusable-property-configurations.md).

Yukarıda gösterildiği gibi devralınan yolların çoğu makro olarak verilir.  Bir makronun geçerli değerini incelemek için seçin **makroları** iletişim kutusunun sağ alt köşedeki düğmesi. Not birçok makroları yapılandırma türüne bağlıdır. Hata ayıklama derlemesinde makro için aynı makroyu derleme farklı bir yolda değerlendirebilir.

Düzenleme kutusuna kısmi veya tam eşleşme arayabilirsiniz. Aşağıdaki çizimde "WindowsSDK" dizesini içeren tüm makroları gösterir ve ayrıca makro değerlendiren geçerli yol gösterir:

![Makro değerleri görmek](../media/vcppdir_libdir_macros.png "makroları düzenlemek için iletişim kutusu")

Not: Siz yazarken liste doldurulur. Basın yoksa **Enter**.

Makrolar ve neden sabit kodlanmış yollar mümkün olduğunda yerine kullanmanız gerektiği hakkında daha fazla bilgi için bkz. [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

Yaygın olarak kullanılan makrolar bir listesi için bkz. [derleme komutları ve özellikler için ortak makroları](common-macros-for-build-commands-and-properties.md).

Kendi makroları iki yolla tanımlayabilirsiniz:

- Bir geliştirici Komut İstemi'nde ortam değişkenlerini ayarlayın. Tüm ortam değişkenlerini MSBuild özellikleri/makro kabul edilir.

- Bir .props dosyası içinde kullanıcı makroları tanımlar. Daha fazla bilgi için [özellik sayfası makroları](../working-with-project-properties.md).

Daha fazla bilgi için şu blog postalarına bakın: [VC ++ dizinleri](https://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [devralınan özellikler ve özellik sayfaları](https://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx), ve [Visual Studio 2010 C++ proje Yükseltme Kılavuzu](https://devblogs.microsoft.com/cppblog/visual-studio-2010-c-project-upgrade-guide/).

## <a name="directory-types"></a>Dizin Türleri

Ayrıca, aşağıdaki gibi diğer dizinleri de belirtebilirsiniz.

**Yürütülebilir dizinler**<br/>
Yürütülebilir dosyaların aranacağı dizinler. Karşılık gelen **yolu** ortam değişkeni.

**Ekleme kodu dizinleri**<br/>
Kaynak kodda başvurulan ekleme kodu dosyalarının aranacağı dizinler. Karşılık gelen **INCLUDE** ortam değişkeni.

**Başvuru dizinleri**<br/>
Derleme ve kaynak kod tarafından başvurulan modül (meta veriler) dosyalarının aranacağı dizinler [#using](../../preprocessor/hash-using-directive-cpp.md) yönergesi. Karşılık gelen **LIBPATH** ortam değişkeni.

**Kitaplık dizinleri**<br/>
Kitaplık (.lib) dosyalarının aranacağı dizinler; çalışma zamanı kitaplıkları da buna dahildir. Karşılık gelen **LIB** ortam değişkeni. Bu ayar .obj dosyaları için geçerli değildir; bir .obj dosyasına bağlantı vermek **yapılandırma özellikleri** > **bağlayıcı** > **genel** özellik sayfasında  **Ek Kitaplık bağımlılıkları** ve ardından dosyanın göreli yolunu belirtin. Daha fazla bilgi için [bağlayıcı özellik sayfaları](linker-property-pages.md).

**Kitaplık WinRT dizinleri**<br/>
WinRT kitaplığı dosyaları için aranacak dizinleri, Evrensel Windows Platformu (UWP) uygulamaları kullanın.

**Kaynak dizinleri**<br/>
IntelliSense için kullanılacak kaynak dosyaların aranacağı dizinler.

**Dışarıda tutulan dizinler**<br/>
Her derlemeden önce Visual Studio tüm önceki derleme beri değiştirilmiş olup olmadığını belirlemek için tüm dosyalarını zaman damgasını sorgular. Projeniz büyük kararlı kitaplıkları varsa, bu dizinlerin zaman damgası denetimden hariç tutarak oluşturma sürelerini potansiyel olarak hızlandırabilir.

## <a name="sharing-the-settings"></a>Ayarları Paylaşma

Proje özelliklerini diğer kullanıcılarla veya birden çok bilgisayar arasında paylaşabilirsiniz. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).
