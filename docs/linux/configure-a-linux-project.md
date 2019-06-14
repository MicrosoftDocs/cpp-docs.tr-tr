---
title: Visual Studio'da C++ Linux projesi yapılandırma
ms.date: 06/11/2019
ms.assetid: 4d7c6adf-54b9-4b23-bd23-5de0c825b768
ms.openlocfilehash: a4e20222cc0b04f496989bf2d51fc12c85f5d162
ms.sourcegitcommit: fde637f823494532314790602c2819f889706ff6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67042628"
---
# <a name="configure-a-linux-project"></a>Linux projesi yapılandırma

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ile kullanılabilir ve üzerinde desteklenir.

::: moniker-end

Bu konu nasıl yapılandırılacağını açıklar bir C++ açıklandığı gibi Linux projesi [yeni bir C++ Linux proje Visual Studio'da](create-a-new-linux-project.md). CMake Linux projeleri için bkz: [Linux CMake projesi yapılandırma ](cmake-linux-project.md). 

Hedef fiziksel Linux makine, bir sanal makine için Linux projesi yapılandırabilirsiniz ya da [Linux için Windows alt sistemi](/windows/wsl/about) (WSL). 

::: moniker range="vs-2019"

**Visual Studio 2019 sürüm 16.1**:

- WSL hedeflenirken uzak Linux sistemleri hedeflenirken IntelliSense ve oluşturmak için gerekli olan kopyalama işlemleri önleyebilirsiniz.

- Derleme ve hata ayıklama için ayrı Linux hedefleri belirtebilirsiniz.

::: moniker-end

## <a name="general-settings"></a>Genel ayarlar

Yapılandırma seçenekleri görüntülemek için seçin **Proje > Özellikleri** menüsü ya da projeye sağ tıklayarak **Çözüm Gezgini** seçip **özellikleri** bağlamından menüsü. **Genel** ayarları görüntülenir.

![Genel yapılandırma](media/settings_general.png)

Varsayılan olarak, bir yürütülebilir dosya (.out) oluşturulur. Bir statik veya dinamik kitaplığını oluşturmak veya mevcut bir derleme görevleri dosyası kullanmak için **yapılandırma türü** ayarı.

Özellik sayfaları ayarlar hakkında daha fazla bilgi için bkz. [Linux projesi özellik Sayfa başvurusu](prop-pages-linux.md).

## <a name="remote-settings"></a>Uzak bağlantı ayarları

Uzak Linux bilgisayara ilgili ayarları değiştirmek için altında görünen uzak ayarları yapılandırma [genel](prop-pages/general-linux.md).

- Bir uzak hedef Linux bilgisayarı belirtmek için kullanın **uzak derleme makinesi** girişi. Bu, daha önce oluşturduğunuz bağlantılardan birini seçmenize olanak sağlar. Yeni bir giriş oluşturmak için bkz: [için Uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md) bölümü.

   ![Derleme makinesi](media/remote-build-machine-vs2019.png)

   ::: moniker range="vs-2019"

   **Visual Studio 2019 sürüm 16.1**: Linux için Windows alt sistemi hedeflemek için için aşağı oka tıklayın **Platform araç takımını** ve **WSL_1_0**. Diğer uzak seçenekleri kaybolur ve bunun yerine varsayılan WSL Kabuk yolunu görünür:

   ![Derleme makinesi WSL](media/wsl-remote-vs2019.png)

   Yan yana WSL yüklemeleri varsa, burada farklı bir yol belirtebilirsiniz. Birden çok dağıtım paketlerini yönetme hakkında daha fazla bilgi için bkz. [yönetme ve Linux için Windows alt sistemi yapılandırma](/windows/wsl/wsl-config#set-a-default-distribution).

   Hata ayıklama için farklı bir hedef belirtebilirsiniz **yapılandırma özellikleri** > **hata ayıklama** sayfası.

   ::: moniker-end

- **Uzaktan derleme kök dizini** proje uzak Linux bilgisayarda nerede oluşturulan kök konumu belirler. Bu varsayılan **~/projects** değiştirmediğiniz sürece.

- **Uzaktan derleme proje dizini** burada uzak Linux bilgisayarda bu belirli proje oluşturulacak olan. Bu varsayılan **$(RemoteRootDir)/$(ProjectName)** , yukarıda kök dizininin altındaki şu anki proje sonra adlandırılmış bir dizine genişletin.

> [!NOTE]
> ' % S'varsayılan C ve C++ Derleyicileri, veya bağlayıcı ve projeyi derlemek için kullanılan Arşivleyicide değiştirmek için uygun girdileri kullanmak **C/C++ > Genel** bölümü ve **bağlayıcı > Genel** bölümü. Örneğin, belirli bir sürümü GCC, Clang veya belirtebilirsiniz. Daha fazla bilgi için [C/C++ özellikleri (Linux C++)](prop-pages/c-cpp-linux.md) ve [bağlayıcı Özellikleri (Linux C++)](prop-pages/linker-linux.md).

## <a name="copy-sources-remote-systems-only"></a>Kaynakları (yalnızca uzak sistemlere) kopyalayın

::: moniker range="vs-2019"

Bu bölümde WSL hedeflenirken geçerli değildir.

::: moniker-end

Uzak sistemlere oluştururken, kaynak dosyalarını geliştirme PC Linux bilgisayara kopyalar ve orada derlenir. Varsayılan olarak, tüm kaynakları Visual Studio projesini, yukarıdaki ayarlarında belirlenen konumlara kopyalanır. Ancak, ek kaynaklar listesine de eklenebilir veya kaynakları kopyalama bir derleme görevleri dosyası projesi için varsayılan seçenek tamamen devre dışı kapatılabilir.

- **Kopyalanacak kaynakları** hangi kaynakları uzak bilgisayara kopyalanır belirler. Varsayılan olarak,  **\@(SourcesToCopyRemotely)** projedeki tüm kaynak kodu dosyaları için varsayılan olarak, ancak resimler gibi herhangi bir varlık/kaynak dosyası içermiyor.

- **Kaynakları Kopyala** açılabilir ve etkinleştirmek ve uzak bilgisayarın kaynak dosyaların kopyalanmasını devre dışı bırakmak için kapalı.

- **Kopyalanacak ek kaynakları** uzak sisteme kopyalanacak ek kaynak dosyaları eklemenizi sağlar. Noktalı virgülle ayrılmış liste belirtebilir veya kullanabileceğiniz **: =** kullanılacak yerel ve uzak bir ad belirtmek için sözdizimi:

`C:\Projects\ConsoleApplication1\MyFile.cpp:=~/projects/ConsoleApplication1/ADifferentName.cpp;C:\Projects\ConsoleApplication1\MyFile2.cpp:=~/projects/ConsoleApplication1/ADifferentName2.cpp;`

## <a name="build-events"></a>Derleme olayları

Tüm derleme bir uzak bilgisayar (veya WSL) gerçekleştiği için birkaç ek derleme olayları proje özelliklerinde Build Events bölümüne eklenmiştir. Bunlar **uzaktan derleme öncesi olay**, **uzaktan bağlama öncesi olay**, ve **uzaktan derleme sonrası olay**ve uzak bilgisayarda önce veya sonra tek tek adımları meydana gelir işlemi.

![Derleme olayları](media/settings_buildevents.png)

## <a name="remote_intellisense"></a> Uzak sistemlerdeki üst bilgileri için IntelliSense

::: moniker range="vs-2019"

Bu bölümde WSL hedeflenirken geçerli değildir.

::: moniker-end

İçinde yeni bir bağlantı eklediğinizde **Bağlantı Yöneticisi**, Visual Studio uzak sistem üzerindeki derleyici için dizinleri otomatik olarak algılar. Visual Studio sonra zıps ve bu dosyaların yerel Windows makinenizde bir dizine kopyalar. Her bir Visual Studio ya da CMake proje bu bağlantının kullandığınızda bundan sonra bu dizinlerin üstbilgilerinde IntelliSense sağlamak için kullanılır.

Bu işlev, zip yüklü olan bir Linux makinesinde bağlıdır. Zip bu apt-get komutuyla yükleyebilirsiniz:

```cmd
sudo apt install zip
```

Üst bilgi önbelleği yönetmek için gidin **Araçlar > Seçenekler, Çoklu Platform > Bağlantı Yöneticisi > Uzak üst bilgiler IntelliSense Yöneticisi**. Linux makinenizde değişiklikleri yaptıktan sonra üst bilgi önbelleği güncelleştirmek için Uzak bağlantıyı seçin ve ardından **güncelleştirme**. Seçin **Sil** bağlantı silmeden üstbilgileri kaldırmak için. Seçin **Araştır** yerel dizinde açmak için **dosya Gezgini**. Bu klasör, salt okunur olarak kabul eder. Visual Studio 2017 sürüm 15.3 önce oluşturulmuş mevcut bir bağlantı için üst bilgileri indirmek için bağlantıyı seçin ve ardından **indirme**.

::: moniker range="vs-2017"

![Remote Header IntelliSense](media/remote-header-intellisense.png)

::: moniker-end

::: moniker range="vs-2019"

![Remote Header IntelliSense](media/connection-manager-vs2019.png)

Sorunlarını gidermenize yardımcı olmak için günlük kaydını etkinleştirebilirsiniz:

![Uzaktan günlüğe kaydetme](media/remote-logging-vs2019.png)

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici ayarlayın ve derleme özellikleri](../build/working-with-project-properties.md)<br/>
[C++ genel özellikleri (Linux C++)](../linux/prop-pages/general-linux.md)<br/>
[VC ++ dizinleri (Linux C++)](../linux/prop-pages/directories-linux.md)<br/>
[Kopyalama kaynakları proje özellikleri (Linux C++)](../linux/prop-pages/copy-sources-project.md)<br/>
[Derleme olay özellikleri (Linux C++)](../linux/prop-pages/build-events-linux.md)
