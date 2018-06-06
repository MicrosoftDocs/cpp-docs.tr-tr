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
ms.openlocfilehash: 3acaccff2e2764f4fd7f6f4815f5721f0ba845a3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33336088"
---
# <a name="vc-directories-property-page-windows"></a>VC ++ dizinleri özellik sayfası (Windows)

Visual Studio şu anda seçili proje oluşturulurken kullanılacak hangi dizinleri bildirmek için bu özellik sayfasını kullanın. Bir çözümde birden çok proje için dizin kümesi için bir özel özellik sayfası açıklandığı gibi kullanın [yeniden kullanılabilir özellik yapılandırmaları oluşturma](working-with-project-properties.md#bkmkPropertySheets).

Bu sayfayı Linux sürümü için bkz: [VC ++ dizinleri (Linux C++)](../linux/prop-pages/directories-linux.md).   

Erişim için **VC ++ dizinleri** özellik sayfası:

1. Varsa **Çözüm Gezgini** pencere görünür değil, ana menüde seçin **Görünüm** > **Çözüm Gezgini**.
1. Bir proje düğümüne (üst düzey çözümü değil) sağ tıklatın ve seçin **özellikleri**.
1. Sol bölmesinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri** > **VC ++ dizinleri**.  

VC ++ dizinleri özellikleri üst düzey çözüm düğümüne bir proje için geçerlidir. Görmüyorsanız, **VC ++ dizinleri** altında **yapılandırma özellikleri**, C++ projesi düğümü seçin **Çözüm Gezgini** penceresi: 

![Proje düğümünü seçin](media/vcppdir.png "VC ++ dizinleri özellik görmek için proje düğümünü seçin")

Unutmayın **VC ++ dizinleri** farklı platformlar arası projeleri için özellik sayfası görünür. Linux C++ projelerine özel bilgi için bkz: [VC ++ dizinleri (Linux C++)](../linux/prop-pages/directories-linux.md). 
 
Alışık değilseniz *proje özellikleri* Visual Studio'da ilk okuma için yararlı [proje özellikleriyle çalışma](working-with-project-properties.md). 
 
Varsayılan ayarları **VC ++ dizinleri** özellikleri proje türüne bağlıdır. Masaüstü projeleri için belirli bir Platform araç takımı C++ Araçları konumlarını ve Windows SDK'sı konumu içerirler. Değiştirebileceğiniz **Platform araç takımı** ve **Windows SDK sürümü** üzerinde **yapılandırma özellikleri** > **genel** Sayfa. 

Herhangi bir dizin için değerleri görüntülemek için:

1. Özelliklerden birini **VC ++ dizinleri** sayfası. Örneğin, tercih **kitaplık dizinleri**.
1. Özellik değeri alanı sonunda aşağı ok düğmesini seçin.
1. Açılan menüde seçin **Düzenle**.

![Kitaplık dizinleri Düzenle](media/vcppdir_libdir_edit.png "kitaplık yolları Düzenle iletişim kutusu")

Artık bu gibi bir iletişim kutusu görürsünüz: 

![Kitaplık dizinleri Göster](media/vcppdir_libdir.png "eklemek veya kitaplık yolları kaldırmak için iletişim")

Geçerli dizin görüntülemek için bu iletişim kutusunu kullanın. Değiştirme veya bir dizin eklemek istiyorsanız, ancak bunu kullanmak en iyisidir **özellik Yöneticisi** bir özellik sayfası oluşturmak veya varsayılan kullanıcı özellik sayfası değiştirmek için. Daha fazla bilgi için bkz: [yeniden kullanılabilir özellik yapılandırmaları oluşturma](working-with-project-properties.md#bkmkPropertySheets).

Yukarıda gösterildiği gibi birçok devralınan yolları makroları olarak verilir.  Geçerli bir makro değerini incelemek için tercih **makroları** iletişim kutusunun sağ alt köşesindeki düğmesini. Not birçok makroları yapılandırma türüne bağlıdır. Yayın derlemesi içinde aynı makrosu daha farklı bir yol için bir hata ayıklama derlemesi makro değerlendirebilir. 

Düzenleme kutusuna kısmi veya tam eşleşme arayabilirsiniz. Aşağıdaki çizimde "WindowsSDK" dizesini içeren tüm makroları gösterir ve ayrıca makrosu değerlendiren geçerli yolunu gösterir:

![Makro değerlerini görmek](media/vcppdir_libdir_macros.png "makroları Düzenle iletişim kutusu")

Not: liste yazarken doldurulur. Basın yok **Enter**.

Makrolar ve bunları neden sabit kodlanmış yolları mümkün olduğunda yerine kullanmanız hakkında daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md#bkmkPropertiesVersusMacros). 

Yaygın olarak kullanılan makroları listesi için bkz: [derleme komutları ve özellikler için ortak makrolar](https://docs.microsoft.com/en-us/cpp/ide/common-macros-for-build-commands-and-properties).

İki yolla kendi makroları tanımlayabilirsiniz:
-   Bir geliştirici Komut İstemi'nde ortam değişkenlerini ayarlama. Tüm ortam değişkenlerini MSBuild özellikleri/makroları olarak kabul edilir.
-   Kullanıcı makroları .props dosyasında tanımlayın. Daha fazla bilgi için bkz: [özellik sayfası makroları](working-with-project-properties.md#bkmkPropertiesVersusMacros). 

Bu Web günlüğü postaları daha fazla bilgi için bkz: [VC ++ dizinleri](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [devralınan özellikler ve özellik sayfaları](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx), ve [Visual Studio 2010 C++ projesi Yükseltme Kılavuzu](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx).  
  
## <a name="directory-types"></a>Dizin Türleri

Ayrıca, aşağıdaki gibi diğer dizinleri de belirtebilirsiniz.  
  
**Yürütülebilir dosya dizinleri**<br/>
Yürütülebilir dosyaların aranacağı dizinler. Karşılık gelen **yolu** ortam değişkeni.

**Yönergeleri dahil etme**<br/>
Kaynak kodda başvurulan ekleme kodu dosyalarının aranacağı dizinler. Karşılık gelen **INCLUDE** ortam değişkeni.

**Başvuru dizinleri**<br/>
 Derleme ve kaynak kodu tarafından başvurulan modül (meta verileri) dosyaları için aranacak dizinlerde [#using](../preprocessor/hash-using-directive-cpp.md) yönergesi. Karşılık gelen **LIBPATH** ortam değişkeni.

**Kitaplık dizinleri**<br/>
Kitaplık (.lib) dosyalarının aranacağı dizinler; çalışma zamanı kitaplıkları da buna dahildir. Karşılık gelen **LIB** ortam değişkeni. Bu ayar .obj dosyaları için geçerli değildir; üzerinde bir .obj dosyasına bağlanmak için **yapılandırma özellikleri** > **bağlayıcı** > **genel** özellik sayfasında,  **Ek Kitaplık bağımlılıkları** ve ardından dosyanın göreli yolunu belirtin. Daha fazla bilgi için bkz: [bağlayıcı özellik sayfaları](../ide/linker-property-pages.md).

**Kitaplık WinRT dizinleri**<br/>
Evrensel Windows Platformu (UWP) uygulamaları için WinRT kitaplık dosyalarını aramak için dizinler kullanır. 

**Kaynak dizinler**<br/>
IntelliSense için kullanılacak kaynak dosyaların aranacağı dizinler.

**Dizinleri dışta tut**<br/>
Her derleme önce Visual Studio herhangi önceki derleme beri değiştirilmiş olup olmadığını belirlemek için tüm dosyaları zaman damgasını sorgular. Projenizi büyük kararlı kitaplıkları varsa, bu dizinlerin zaman damgası denetimden hariç tutarak, yapı süreleri olası hızlandırabilir.

## <a name="sharing-the-settings"></a>Ayarları Paylaşma

Proje özelliklerini diğer kullanıcılarla veya birden çok bilgisayar arasında paylaşabilirsiniz. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).
