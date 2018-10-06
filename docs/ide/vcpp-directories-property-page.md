---
title: VC ++ dizinleri özellik sayfası | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
dev_langs:
- C++
helpviewer_keywords:
- VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82aaa2dc43177963b9b38c398e74aaa0ffff11dd
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821224"
---
# <a name="vc-directories-property-page-windows"></a>VC ++ dizinleri özellik sayfası (Windows)

Visual Studio şu anda seçili proje oluşturma sırasında kullanmak için hangi dizinleri bildirmek için bu özellik sayfasını kullanın. Bir çözümde birden çok proje için dizinleri ayarlamak için bir özel özellik sayfası ölçeklendirmesini kullanacak [yeniden kullanılabilir özellik yapılandırmalarını oluşturma](working-with-project-properties.md#bkmkPropertySheets).

Bu sayfa Linux sürümü için bkz: [VC ++ dizinleri (Linux C++)](../linux/prop-pages/directories-linux.md).

Erişim için **VC ++ dizinleri** özellik sayfası:

1. Varsa **Çözüm Gezgini** penceresi görünür değilse, ana menüden seçin **görünümü** > **Çözüm Gezgini**.
1. Bir proje düğümü (en üst düzey çözümü değil) sağ tıklatın ve seçin **özellikleri**.
1. Sol bölmesinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri** > **VC ++ dizinleri**.

VC ++ dizinleri özellikleri, üst düzey çözüm düğümüne bir proje için geçerlidir. Görmüyorsanız, **VC ++ dizinleri** altında **yapılandırma özellikleri**, bir C++ projesi düğümünde seçin **Çözüm Gezgini** penceresi:

![Proje düğümünü seçin](media/vcppdir.png "VC ++ dizinleri özellikleri görmek için proje düğümünü seçin")

Unutmayın **VC ++ dizinleri** farklı platformlar arası projeler için özellik sayfası görünür. Linux C++ projelerine özgü bilgiler için bkz: [VC ++ dizinleri (Linux C++)](../linux/prop-pages/directories-linux.md).

İle aşina değilseniz *proje özellikleri* Visual Studio'da ilk okuma için yararlı [Working with project properties](working-with-project-properties.md).

İçin varsayılan ayarları **VC ++ dizinleri** özellikleri proje türüne bağlıdır. Masaüstü projeleri için C++ araçlarının konumları için belirli bir Platform araç takımını ve Windows SDK'sı konumu içerirler. Değiştirebileceğiniz **Platform araç takımını** ve **Windows SDK sürümü** üzerinde **yapılandırma özellikleri** > **genel** Sayfa.

Tüm dizinlerin değerlerini görüntülemek için:

1. Özelliklerinde birini **VC ++ dizinleri** sayfası. Örneğin, **kitaplık dizinleri**.
1. Özellik değeri alanı sonundaki aşağı ok düğmesini seçin.
1. Aşağı açılan menüsünde **Düzenle**.

![Kitaplık dizinleri Düzenle](media/vcppdir_libdir_edit.png "kitaplık yollarını düzenlemek için iletişim kutusu")

Artık böyle bir iletişim kutusu görürsünüz:

![Kitaplık dizinleri Göster](media/vcppdir_libdir.png "eklemek veya kitaplık yollarını kaldırmak için iletişim kutusu")

Geçerli dizinleri görüntülemek için bu iletişim kutusunu kullanın. Bir dizin eklemek veya değiştirmek istiyorsanız, ancak bunu kullanmak en iyisidir **özellik Yöneticisi** bir özellik sayfası oluşturma veya varsayılan kullanıcı özellik sayfası değiştirmek için. Daha fazla bilgi için [yeniden kullanılabilir özellik yapılandırmalarını oluşturma](working-with-project-properties.md#bkmkPropertySheets).

Yukarıda gösterildiği gibi devralınan yolların çoğu makro olarak verilir.  Bir makronun geçerli değerini incelemek için seçin **makroları** iletişim kutusunun sağ alt köşedeki düğmesi. Not birçok makroları yapılandırma türüne bağlıdır. Hata ayıklama derlemesinde makro için aynı makroyu derleme farklı bir yolda değerlendirebilir.

Düzenleme kutusuna kısmi veya tam eşleşme arayabilirsiniz. Aşağıdaki çizimde "WindowsSDK" dizesini içeren tüm makroları gösterir ve ayrıca makro değerlendiren geçerli yol gösterir:

![Makro değerleri görmek](media/vcppdir_libdir_macros.png "makroları düzenlemek için iletişim kutusu")

Not: siz yazarken liste doldurulur. Basın yoksa **Enter**.

Makrolar ve neden sabit kodlanmış yollar mümkün olduğunda yerine kullanmanız gerektiği hakkında daha fazla bilgi için bkz. [Working with Project Properties](../ide/working-with-project-properties.md#bkmkPropertiesVersusMacros).

Yaygın olarak kullanılan makrolar bir listesi için bkz. [genel derleme komutları ve Özellikler makroları](https://docs.microsoft.com/cpp/ide/common-macros-for-build-commands-and-properties).

Kendi makroları iki yolla tanımlayabilirsiniz:

- Bir geliştirici Komut İstemi'nde ortam değişkenlerini ayarlayın. Tüm ortam değişkenlerini MSBuild özellikleri/makro kabul edilir.

- Bir .props dosyası içinde kullanıcı makroları tanımlar. Daha fazla bilgi için [özellik sayfası makroları](working-with-project-properties.md#bkmkPropertiesVersusMacros).

Daha fazla bilgi için şu blog postalarına bakın: [VC ++ dizinleri](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [devralınan özellikler ve özellik sayfaları](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx), ve [Visual Studio 2010 C++ proje Yükseltme Kılavuzu](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx).

## <a name="directory-types"></a>Dizin Türleri

Ayrıca, aşağıdaki gibi diğer dizinleri de belirtebilirsiniz.

**Yürütülebilir dizinler**<br/>
Yürütülebilir dosyaların aranacağı dizinler. Karşılık gelen **yolu** ortam değişkeni.

**Ekleme kodu dizinleri**<br/>
Kaynak kodda başvurulan ekleme kodu dosyalarının aranacağı dizinler. Karşılık gelen **INCLUDE** ortam değişkeni.

**Başvuru dizinleri**<br/>
Derleme ve kaynak kod tarafından başvurulan modül (meta veriler) dosyalarının aranacağı dizinler [#using](../preprocessor/hash-using-directive-cpp.md) yönergesi. Karşılık gelen **LIBPATH** ortam değişkeni.

**Kitaplık dizinleri**<br/>
Kitaplık (.lib) dosyalarının aranacağı dizinler; çalışma zamanı kitaplıkları da buna dahildir. Karşılık gelen **LIB** ortam değişkeni. Bu ayar .obj dosyaları için geçerli değildir; bir .obj dosyasına bağlantı vermek **yapılandırma özellikleri** > **bağlayıcı** > **genel** özellik sayfasında  **Ek Kitaplık bağımlılıkları** ve ardından dosyanın göreli yolunu belirtin. Daha fazla bilgi için [bağlayıcı özellik sayfaları](../ide/linker-property-pages.md).

**Kitaplık WinRT dizinleri**<br/>
WinRT kitaplığı dosyaları için aranacak dizinleri, Evrensel Windows Platformu (UWP) uygulamaları kullanın.

**Kaynak dizinleri**<br/>
IntelliSense için kullanılacak kaynak dosyaların aranacağı dizinler.

**Dışarıda tutulan dizinler**<br/>
Her derlemeden önce Visual Studio tüm önceki derleme beri değiştirilmiş olup olmadığını belirlemek için tüm dosyalarını zaman damgasını sorgular. Projeniz büyük kararlı kitaplıkları varsa, bu dizinlerin zaman damgası denetimden hariç tutarak oluşturma sürelerini potansiyel olarak hızlandırabilir.

## <a name="sharing-the-settings"></a>Ayarları Paylaşma

Proje özelliklerini diğer kullanıcılarla veya birden çok bilgisayar arasında paylaşabilirsiniz. Daha fazla bilgi için [Working with Project Properties](../ide/working-with-project-properties.md).
