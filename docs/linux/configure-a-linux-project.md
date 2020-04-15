---
title: Visual Studio'da C++ Linux projesini yapılandırma
ms.date: 06/11/2019
ms.assetid: 4d7c6adf-54b9-4b23-bd23-5de0c825b768
ms.openlocfilehash: 50d5df0e25e82238297458ec7fedb955654e525b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "80150972"
---
# <a name="configure-a-linux-project"></a>Linux projesi yapılandırma

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

Bu konu, Visual Studio'da yeni bir [C++ Linux projesi oluştur'da](create-a-new-linux-project.md)açıklandığı gibi bir C++ Linux projesinin nasıl yapılandırılabildiğini açıklar. CMake Linux projeleri için [bkz.](cmake-linux-project.md)

Bir Linux projesini fiziksel bir Linux makinesini, sanal makineyi veya [Linux için Windows Alt Sistemini](/windows/wsl/about) (WSL) hedefleyecek şekilde yapılandırabilirsiniz.

::: moniker range="vs-2019"

**Visual Studio 2019 sürüm 16.1**:

- WSL'yi hedefalırken, uzak Linux sistemlerini hedefalırken intelliSense oluşturmak ve IntelliSense oluşturmak için gerekli olan kopyalama işlemlerinden kaçınabilirsiniz.

- Oluşturma ve hata ayıklama için ayrı Linux hedefleri belirtebilirsiniz.

::: moniker-end

## <a name="general-settings"></a>Genel ayarlar

Yapılandırma seçeneklerini görüntülemek için **Project > Properties** menüsünü seçin veya Çözüm **Gezgini'ndeki** projeye sağ tıklayın ve bağlam menüsünden **Özellikler'i** seçin. **Genel** ayarlar görüntülenir.

![Genel yapılandırma](media/settings_general.png)

Varsayılan olarak, yürütülebilir (.out) oluşturulur. Statik veya dinamik bir kitaplık oluşturmak veya varolan bir Makefile kullanmak için **Yapılandırma Türü** ayarını kullanın.

Özellik sayfalarındaki ayarlar hakkında daha fazla bilgi için [Linux Project Property Page Reference](prop-pages-linux.md)sayfasına bakın.

## <a name="remote-settings"></a>Uzak ayarlar

Uzak Linux bilgisayarına ait ayarları değiştirmek için [Genel](prop-pages/general-linux.md)altında görünen uzak ayarları yapılandırın.

- Uzaktan hedef li Bir Linux bilgisayarı belirlemek için **Uzaktan Yapı Makinesi** girişini kullanın. Bu, daha önce oluşturulan bağlantılardan birini seçmenize olanak sağlar. Yeni bir giriş oluşturmak [için Uzaktan Linux Bilgisayarınıza Bağlanma bölümüne](connect-to-your-remote-linux-computer.md) bakın.

   ![Yapı Makinesi](media/remote-build-machine-vs2019.png)

   ::: moniker range="vs-2019"

   **Visual Studio 2019 sürüm 16.1**: Linux için Windows Alt Sistemi'ni hedeflemek için **Platform Toolset** için aşağı ok'u tıklayın ve **WSL_1_0**seçin. Diğer uzak seçenekler kaybolur ve varsayılan WSL kabuğuna giden yol onların yerine görünür:

   ![WSL yapı makinesi](media/wsl-remote-vs2019.png)

   Yan yana WSL yüklemeleriniz varsa, burada farklı bir yol belirtebilirsiniz. Birden çok dağıtımın yönetimi hakkında daha fazla bilgi için, [Linux için Windows Alt Sistemini Yönet ve yapılandırma](/windows/wsl/wsl-config#set-a-default-distribution)bilginle.

   **Yapılandırma Özellikleri** > **Hata Ayıklama** sayfasında hata ayıklama için farklı bir hedef belirtebilirsiniz.

   ::: moniker-end

- **Uzaktan Yapı Kök Dizini,** projenin uzak Linux bilgisayarında nerede kurulduğunu belirler. Bu, değiştirilmediği sürece **~/projeler** için varsayılan olacaktır.

- **Uzaktan Yapı Proje Dizini,** bu özel projenin uzak Linux bilgisayarında oluşturulacağı yerdir. Bu varsayılan **$(RemoteRootDir)/$(ProjectName)**, yukarıdaki kök dizini altında, geçerli proje adını bir dizine genişletecektir.

> [!NOTE]
> Varsayılan C ve C++ derleyicilerini veya projeyi oluşturmak için kullanılan Bağlayıcı ve Arşivleyici'yi değiştirmek için **C/C++ > Genel** bölümünde ve **Bağlayıcı genel** > bölümünde uygun girişleri kullanın. Örneğin, GCC veya Clang'ın belirli bir sürümünü belirtebilirsiniz. Daha fazla bilgi için [Bkz. C/C++ Özellikleri (Linux C++)](prop-pages/c-cpp-linux.md) ve [Linker Özellikleri (Linux C++)](prop-pages/linker-linux.md).

## <a name="copy-sources-remote-systems-only"></a>Kopyalama kaynakları (yalnızca uzak sistemler)

::: moniker range="vs-2019"

Bu bölüm WSL hedeflenirken geçerli değildir.

::: moniker-end

Uzak sistemler de inşa edilirken, geliştirme bilgisayarınızdaki kaynak dosyalar Linux bilgisayarına kopyalanır ve orada derlenir. Varsayılan olarak, Visual Studio projesindeki tüm kaynaklar yukarıdaki ayarlarda ayarlanan konumlara kopyalanır. Ancak, listeye ek kaynaklar da eklenebilir veya kopyalama kaynakları tamamen kapatılabilir ve bu da Makefile projesinin varsayılanıdır.

- **Kopyalanan kaynaklar,** hangi kaynakların uzak bilgisayara kopyalanabilen kaynaklar olduğunu belirler. Varsayılan olarak, ** \@(SourcesToCopyRemotely)** projedeki tüm kaynak kodu dosyaları için varsayılan, ancak görüntüler gibi herhangi bir varlık / kaynak dosyaları içermez.

- **Kaynak** dosyalarının uzak bilgisayara kopyalanmasını etkinleştirmek ve devre dışı etmek için kopyalama kaynakları açık ve kapalı olabilir.

- **Kopyalanacak ek kaynaklar,** uzak sisteme kopyalanacak ek kaynak dosyaları eklemenize olanak tanır. Yarı-iki nokta nokta lı sınırlı bir liste belirtebilirsiniz veya kullanmak için yerel ve uzak bir ad belirtmek için **:=** sözdizimini kullanabilirsiniz:

`C:\Projects\ConsoleApplication1\MyFile.cpp:=~/projects/ConsoleApplication1/ADifferentName.cpp;C:\Projects\ConsoleApplication1\MyFile2.cpp:=~/projects/ConsoleApplication1/ADifferentName2.cpp;`

## <a name="build-events"></a>Etkinlikler oluşturma

Tüm derleme uzak bir bilgisayarda (veya WSL) gerçekleştiğinden, Project Properties'deki Yapı Olayları bölümüne birkaç ek Yapı Olayı eklendi. Bunlar **Uzaktan Ön Yapı Olayı,** **Uzaktan Ön Bağlantı Olayı**ve Uzaktan **Post-Build Olayıdır**ve bu işlemdeki tek tek adımlardan önce veya sonra uzak bilgisayarda oluşur.

![Etkinlikler Oluşturun](media/settings_buildevents.png)

## <a name="intellisense-for-headers-on-remote-systems"></a><a name="remote_intellisense"></a>Uzak sistemlerde üstbilgi için IntelliSense

**Connection Manager'a**yeni bir bağlantı eklediğinizde, Visual Studio uzak sistemdeki derleyicinin dahil dizinlerini otomatik olarak algılar. Visual Studio daha sonra fermuarını kaplar ve bu dosyaları yerel Windows makinenizdeki bir dizine kopyalar. Bundan sonra, visual studio veya CMake projesinde bu bağlantıyı her kullandığınızda, bu dizinlerde üstbilgi IntelliSense sağlamak için kullanılır.

> [!NOTE]
> Visual Studio 2019 sürüm 16.5 ve sonraki sürümlerde, uzak üstbilgi kopyası optimize edilmiştir. Üstbilgi artık bir Linux projesi açarken veya Linux hedefi için CMake'i yapılandırırken isteğe bağlı olarak kopyalanır. Kopya, projenin belirtilen derleyicilerine dayalı olarak, proje başına olarak arka planda oluşur. Daha fazla bilgi için Linux [IntelliSense'in Doğruluk ve Performansında İyileştirmeler bölümüne](https://devblogs.microsoft.com/cppblog/improvements-to-accuracy-and-performance-of-linux-intellisense/)bakın.

Bu işlevsellik, Linux makinesinin zip yüklü olmasına bağlıdır. Bu apt-get komutunu kullanarak zip yükleyebilirsiniz:

```cmd
sudo apt install zip
```

Üstbilgi önbelleğinizi yönetmek için **Araçlar > Seçenekleri, Çapraz Platform > Bağlantı Yöneticisi > Uzak Üstler IntelliSense Yöneticisi'ne**gidin. Linux makinenizde değişiklik yaptıktan sonra üstbilgi önbelleğini güncelleştirmek için uzak bağlantıyı seçin ve ardından **Güncelleştir'i**seçin. Bağlantının kendisini silmeden üstbilgileri kaldırmak için **Sil'i** seçin. **Dosya Gezgini'nde**yerel dizini açmak için **Keşfet'i** seçin. Bu klasörü salt okunur olarak ele ayarı. Visual Studio 2017 sürüm 15.3'ten önce oluşturulmuş varolan bir bağlantı için üstbilgi indirmek için bağlantıyı seçin ve ardından **İndir'i**seçin.

::: moniker range="vs-2017"

![Uzaktan Başlık IntelliSense](media/remote-header-intellisense.png)

::: moniker-end

::: moniker range="vs-2019"

![Uzaktan Başlık IntelliSense](media/connection-manager-vs2019.png)

Sorunları gidermek için günlüğe kaydetmeyi etkinleştirebilirsiniz:

![Uzaktan Günlük](media/remote-logging-vs2019.png)

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici ve yapı özellikleri ayarlama](../build/working-with-project-properties.md)<br/>
[C++ Genel Özellikleri (Linux C++)](../linux/prop-pages/general-linux.md)<br/>
[VC++ Dizinleri (Linux C++)](../linux/prop-pages/directories-linux.md)<br/>
[Copy Sources Proje Özellikleri (Linux C++)](../linux/prop-pages/copy-sources-project.md)<br/>
[Etkinlik Özellikleri Oluşturma (Linux C++)](../linux/prop-pages/build-events-linux.md)
