---
title: Visual Studio C++ 'da Linux projesi yapılandırma
ms.date: 06/11/2019
ms.assetid: 4d7c6adf-54b9-4b23-bd23-5de0c825b768
ms.openlocfilehash: 5d42ca587946d3b5adcbd3b6fe35a6c1e1bb9ae8
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419387"
---
# <a name="configure-a-linux-project"></a>Linux projesi yapılandırma

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

Bu konu başlığında [, Visual Studio 'da yeni C++ bir Linux projesi oluşturma](create-a-new-linux-project.md)bölümünde açıklandığı gibi bir C++ Linux projesinin nasıl yapılandırılacağı açıklanmaktadır. CMake Linux projeleri için bkz. [Linux CMake projesini yapılandırma ](cmake-linux-project.md). 

Bir Linux projesini fiziksel bir Linux makinesini, sanal makineyi veya [Linux Için Windows alt sistemini](/windows/wsl/about) (WSL) hedeflemek üzere yapılandırabilirsiniz. 

::: moniker range="vs-2019"

**Visual Studio 2019 sürüm 16,1**:

- WSL 'yi hedeflerken, uzak Linux sistemlerini hedeflerken oluşturma ve IntelliSense için gerekli olan kopyalama işlemlerini önleyebilirsiniz.

- Oluşturma ve hata ayıklama için ayrı Linux hedefleri belirtebilirsiniz.

::: moniker-end

## <a name="general-settings"></a>Genel ayarlar

Yapılandırma seçeneklerini görüntülemek için **proje > Özellikler** menüsünü seçin ya da **Çözüm Gezgini** ' de projeye sağ tıklayıp bağlam menüsünden **Özellikler** ' i seçin. **Genel** ayarlar görüntülenir.

![Genel yapılandırma](media/settings_general.png)

Varsayılan olarak, bir yürütülebilir (. out) oluşturulur. Statik veya dinamik bir kitaplık oluşturmak veya var olan bir derleme görevleri dosyasını kullanmak için **yapılandırma türü** ayarını kullanın.

Özellik sayfalarındaki ayarlar hakkında daha fazla bilgi için bkz. [Linux proje özellik sayfası başvurusu](prop-pages-linux.md).

## <a name="remote-settings"></a>Uzak ayarlar

Uzak Linux bilgisayarıyla ilgili ayarları değiştirmek için, [genel](prop-pages/general-linux.md)altında görüntülenen uzak ayarları yapılandırın.

- Uzak hedef Linux bilgisayarı belirtmek için, **uzak derleme makinesi** girişini kullanın. Bu, daha önce oluşturulan bağlantılardan birini seçmenizi sağlar. Yeni bir giriş oluşturmak için, [uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md) bölümüne bakın.

   ![Yapı makinesi](media/remote-build-machine-vs2019.png)

   ::: moniker range="vs-2019"

   **Visual Studio 2019 sürüm 16,1**: Linux Için Windows alt sistemi hedeflemek üzere **platform araç takımı** için aşağı oka tıklayın ve **WSL_1_0**' yi seçin. Diğer uzak Seçenekler kaybolur ve varsayılan WSL kabuğu yolu kendi yerine görünür:

   ![WSL derleme makinesi](media/wsl-remote-vs2019.png)

   Yan yana WSL yüklemelerine sahipseniz, burada farklı bir yol belirtebilirsiniz. Birden çok distros yönetme hakkında daha fazla bilgi için bkz. [Linux Için Windows alt sistemini yönetme ve yapılandırma](/windows/wsl/wsl-config#set-a-default-distribution).

   **Yapılandırma özellikleri** > **hata ayıklama** sayfasında, hata ayıklama için farklı bir hedef belirtebilirsiniz.

   ::: moniker-end

- **Uzak derleme kök dizini** , projenin uzak Linux bilgisayarda oluşturulduğu kök konumunu belirler. Bu, varsayılan olarak **~/Projects** olarak değiştirilmediği durumlar olur.

- **Uzak derleme proje dizini** , bu söz konusu projenin uzak Linux bilgisayarda oluşturulacağı yerdir. Bu, varsayılan olarak **$ (Remoterootdir)/$ (ProjectName)** olarak ayarlanır ve bu, yukarıda kök dizin kümesinin altında geçerli projeden sonra adlı bir dizine genişletilir.

> [!NOTE]
> Varsayılan c ve C++ derleyicileri veya projeyi oluşturmak için kullanılan bağlayıcı ve arşivleyicide değiştirmek için **cC++ /> Genel** bölümünde uygun girişleri ve **bağlayıcı > Genel** bölümünü kullanın. Örneğin, belirli bir GCC veya Clang sürümü belirtebilirsiniz. Daha fazla bilgi için bkz. [CC++ /Properties C++(Linux)](prop-pages/c-cpp-linux.md) ve [bağlayıcı özellikleri C++(Linux)](prop-pages/linker-linux.md).

## <a name="copy-sources-remote-systems-only"></a>Kaynakları Kopyala (yalnızca uzak sistemler)

::: moniker range="vs-2019"

Bu bölüm, WSL hedeflenirken uygulanmaz.

::: moniker-end

Uzak sistemlerde derlerken, geliştirme BILGISAYARıNıZDAKI kaynak dosyaları Linux bilgisayara kopyalanır ve burada derlenir. Varsayılan olarak, Visual Studio projesindeki tüm kaynaklar yukarıdaki ayarlarda ayarlanan konumlara kopyalanır. Ancak, ek kaynaklar da listeye eklenebilir veya kaynakları kopyalama işlemi, derleme görevleri dosyası projesi için varsayılan olan tamamen kapatılabilir.

- **Kopyalanacak kaynaklar** , uzak bilgisayara hangi kaynakların kopyalanacağını belirler. Varsayılan olarak, **\@(Sourcestocopyuzaktan)** projedeki tüm kaynak kod dosyalarını varsayılan olarak alır, ancak resimler gibi herhangi bir varlık/kaynak dosyası içermez.

- Kaynak dosyaların uzak bilgisayara kopyalanmasını etkinleştirmek ve devre dışı bırakmak için **kaynakları Kopyala** özelliği açık ve kapalı olabilir.

- **Kopyalanacak ek kaynaklar** , uzak sisteme kopyalanacak ek kaynak dosyaları eklemenize olanak tanır. Noktalı virgülle ayrılmış bir liste belirtebilir veya kullanılacak yerel ve uzak bir ad belirtmek için **: =** sözdizimini kullanabilirsiniz:

`C:\Projects\ConsoleApplication1\MyFile.cpp:=~/projects/ConsoleApplication1/ADifferentName.cpp;C:\Projects\ConsoleApplication1\MyFile2.cpp:=~/projects/ConsoleApplication1/ADifferentName2.cpp;`

## <a name="build-events"></a>Derleme olayları

Tüm derleme uzak bir bilgisayarda (veya WSL) bulunduğundan, proje özelliklerindeki derleme olayları bölümüne birkaç ek derleme olayı eklenmiştir. Bunlar, uzaktan **oluşturma öncesi olay**, **uzak bağlama öncesi olay**ve **uzak derleme sonrası**olaylardır ve bu işlem, uzak bilgisayarda işlemdeki adımlardan önce veya sonra gerçekleşir.

![Derleme olayları](media/settings_buildevents.png)

## <a name="remote_intellisense"></a>Uzak sistemlerde üst bilgiler için IntelliSense

**Bağlantı Yöneticisi**'nde yeni bir bağlantı eklediğinizde, Visual Studio, uzak sistemdeki derleyicinin ekleme dizinlerini otomatik olarak algılar. Daha sonra Visual Studio, bu dosyaları yerel Windows makinenizde bir dizine kopyalar. Bundan sonra, bu bağlantıyı bir Visual Studio veya CMake projesinde kullandığınızda, bu dizinteki üstbilgiler IntelliSense sağlamak için kullanılır.

> [!NOTE]
> Visual Studio 2019 sürüm 16,5 ve sonrasında, uzak üst bilgi kopyası iyileştirilmiştir. Artık üstbilgiler bir Linux projesi açılırken veya bir Linux hedefi için CMake yapılandırılırken isteğe bağlı olarak kopyalanır. Kopya, projenin belirtilen derleyicileri temelinde proje başına temelinde arka planda gerçekleşir. Daha fazla bilgi için bkz. [Linux IntelliSense 'In doğruluğu ve performansına yönelik iyileştirmeler](https://devblogs.microsoft.com/cppblog/improvements-to-accuracy-and-performance-of-linux-intellisense/).

Bu işlevsellik, zip 'in yüklü olduğu Linux makinesine bağlıdır. Bu apt-get komutunu kullanarak zip 'i yükleyebilirsiniz:

```cmd
sudo apt install zip
```

Üst bilgi önbelleğinizi yönetmek için **araçlar > seçenekler, platformlar arası > bağlantı yöneticisi > uzak üstbilgiler IntelliSense Yöneticisi**' ne gidin. Linux makinenizde değişiklik yaptıktan sonra üst bilgi önbelleğini güncelleştirmek için, uzak bağlantıyı seçin ve ardından **Güncelleştir**' i seçin. Bağlantıyı silmeden üstbilgileri kaldırmak için **Sil** ' i seçin. **Dosya Gezgini**'nde yerel dizini açmak için **keşfet** ' i seçin. Bu klasörü salt okunurdur olarak değerlendirin. Visual Studio 2017 sürüm 15,3 ' den önce oluşturulmuş mevcut bir bağlantının üst bilgilerini indirmek için bağlantıyı seçin ve ardından **İndir**' i seçin.

::: moniker range="vs-2017"

![Uzak üst bilgi IntelliSense](media/remote-header-intellisense.png)

::: moniker-end

::: moniker range="vs-2019"

![Uzak üst bilgi IntelliSense](media/connection-manager-vs2019.png)

Sorunları gidermeye yardımcı olmak için günlüğü etkinleştirebilirsiniz:

![Uzaktan günlüğe kaydetme](media/remote-logging-vs2019.png)

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici ve derleme özelliklerini ayarlama](../build/working-with-project-properties.md)<br/>
[C++Genel Özellikler (Linux C++)](../linux/prop-pages/general-linux.md)<br/>
[VC + + dizinleri (Linux C++)](../linux/prop-pages/directories-linux.md)<br/>
[Kaynakları kopyalama proje özellikleri (Linux C++)](../linux/prop-pages/copy-sources-project.md)<br/>
[Derleme olayı özellikleri (Linux C++)](../linux/prop-pages/build-events-linux.md)
