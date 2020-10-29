---
title: Visual Studio 'da C++ Linux iş yükünü yükler
description: Visual Studio 'da C++ için Linux iş yükünü indirme, yükleme ve ayarlama.
ms.date: 05/03/2020
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: 9d0c832ec383286b5f89b8ed1474e69d72b5cb98
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921613"
---
# <a name="download-install-and-set-up-the-linux-workload"></a>Linux iş yükünü indirme, yükleme ve ayarlama

::: moniker range="msvc-140"

Linux projeleri Visual Studio 2017 ve üzeri sürümlerde desteklenir. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end

::: moniker range=">=msvc-150"

Windows üzerinde Visual Studio IDE 'yi kullanarak, uzak bir Linux sisteminde, sanal makinede veya [Linux Için Windows alt sisteminde](/windows/wsl/about)yürütülen C++ projeleri oluşturabilir, düzenleyebilir ve hata ayıklaması yapabilirsiniz.

Visual Studio projesine dönüştürmek zorunda kalmadan CMake kullanan mevcut kod tabanınız üzerinde çalışabilirsiniz. Kod tabanınız platformlar arası ise, Visual Studio içinden hem Windows hem de Linux 'u hedefleyebilirsiniz. Örneğin, Visual Studio kullanarak Windows 'da kodunuzu düzenleyebilir, oluşturabilir ve hatalarını ayıklayabilirsiniz. Ardından bir Linux ortamında derlemek ve hata ayıklamak üzere Linux için projeyi hızlıca yeniden hedefleyin. Linux üst bilgi dosyaları yerel makinenize otomatik olarak kopyalanır. Visual Studio, tam IntelliSense desteği sağlamak için bunları kullanır (deyimin tamamlanması, tanıma git vb.).

Bu senaryolardan herhangi biri için, C++ iş yüküyle **Linux geliştirme** gereklidir.

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="visual-studio-setup"></a>Visual Studio Kurulumu

1. Windows Arama kutusuna "Visual Studio Yükleyicisi" yazın:

   ![Windows arama kutusu](media/visual-studio-installer-search.png)

1. **Uygulama** sonuçları altında yükleyiciyi bulun ve çift tıklatın. Yükleyici açıldığında, **Değiştir** ' i seçin ve sonra **iş yükleri** sekmesine tıklayın. **Diğer araç kümelerine** Ilerleyin ve C++ iş yüküyle **Linux geliştirmeyi** seçin.

   ![Linux'ta Geliştirme için Visual C++ iş yükü](media/linuxworkload.png)

1. IoT veya katıştırılmış platformları hedefliyorsanız, sağdaki **Yükleme ayrıntıları** bölmesine gidin. **C++ Ile Linux geliştirme** altında, **isteğe bağlı bileşenler** ' i genişletin ve ihtiyacınız olan bileşenleri seçin. Linux için CMake desteği varsayılan olarak seçilidir.

1. Yüklemeye devam etmek için **Değiştir** 'e tıklayın.

## <a name="options-for-creating-a-linux-environment"></a>Linux ortamı oluşturma seçenekleri

Henüz bir Linux makineniz yoksa Azure 'da bir Linux sanal makinesi oluşturabilirsiniz. Daha fazla bilgi için bkz. [hızlı başlangıç: Azure Portal Linux sanal makinesi oluşturma](/azure/virtual-machines/linux/quick-create-portal).

Windows 10 ' da, Linux (WSL) için Windows alt sistemine sahip en sevdiğiniz Linux 'u yükleyebilir ve hedefleyebilirsiniz. Daha fazla bilgi için bkz. [Windows 10 Için Linux Için Windows alt sistemi yükleme kılavuzu](/windows/wsl/install-win10). Windows Mağazası 'na erişemiyorsanız, [WSL 'nin geçmiş paketlerini el ile indirebilirsiniz](/windows/wsl/install-manual). WSL, uygun bir konsol ortamıdır, ancak grafik uygulamalar için önerilmez.

::: moniker-end

::: moniker range="msvc-160"

Visual Studio 'da Linux projeleri, uzak Linux sisteminize veya WSL 'ye aşağıdaki bağımlılıkların yüklenmesini gerektirir:

- **Derleyici** -Visual Studio 2019, GCC ve [Clang](../build/clang-support-cmake.md)için tam desteğe sahiptir.
- **gdb** -Visual Studio, Linux sisteminde otomatik olarak gdb 'yi başlatır ve Linux üzerinde tam uygunlukta hata ayıklama deneyimi sağlamak Için Visual Studio hata ayıklayıcının ön sonunu kullanır.
- **rsync** ve **ZIP** -rsync ve zip dahil, Visual Studio 'nun IntelliSense tarafından kullanılmak üzere Linux sisteminizden Windows dosya sistemine üst bilgi dosyalarını ayıklamasına olanak tanır.
- **make**
- **OpenSSH-Server** (yalnızca uzak Linux sistemleri)-Visual Studio, GÜVENLI bir SSH bağlantısı üzerinden uzak Linux sistemlerine bağlanır.
- **CMake** (yalnızca CMake projeleri)- [Linux için Microsoft 'un statik bağlantılı CMake İkililerini](https://github.com/microsoft/CMake/releases)yükleyebilirsiniz.
- **dokja-Build** (yalnızca CMake projeleri)- [Dokja](https://ninja-build.org/) , Visual Studio 2019 sürüm 16,6 veya sonraki sürümlerinde Linux ve WSL yapılandırmalarına yönelik varsayılan oluşturucu olur.

Aşağıdaki komutlar Clang yerine g + + kullandığınızı varsayar.

::: moniker-end

::: moniker range="msvc-150"

Visual Studio 'da Linux projeleri, uzak Linux sisteminize veya WSL 'ye aşağıdaki bağımlılıkların yüklenmesini gerektirir:

- **GCC** -Visual Studio 2017, gcc için tam desteğe sahiptir.
- **gdb** -Visual Studio, Linux sisteminde otomatik olarak gdb 'yi başlatır ve Linux üzerinde tam uygunlukta hata ayıklama deneyimi sağlamak Için Visual Studio hata ayıklayıcının ön sonunu kullanır.
- **rsync** ve **ZIP** -rsync ve zip dahil, Visual Studio 'Nun IntelliSense için kullanılacak Windows dosya sistemine Linux sisteminizden başlık dosyalarını ayıklamasına olanak tanır.
- **make**
- **OpenSSH-Server** -Visual Studio, GÜVENLI bir SSH bağlantısı üzerinden uzak Linux sistemlerine bağlanır.
- **CMake** (yalnızca CMake projeleri)- [Linux için Microsoft 'un statik bağlantılı CMake İkililerini](https://github.com/microsoft/CMake/releases)yükleyebilirsiniz.

::: moniker-end

::: moniker range="msvc-160"

## <a name="linux-setup-ubuntu-on-wsl"></a>Linux Kurulumu: WSL üzerinde Ubuntu

WSL 'yi hedeflemek istediğinizde, uzak bir bağlantı eklemeniz veya SSH 'yi derlemek ve hata ayıklaması için yapılandırmanız gerekmez. IntelliSense desteği için Visual Studio ile Linux üstbilgilerinin otomatik eşitlenmesi için **zip** ve **rsync** gereklidir. **dokja-derleme** yalnızca CMake projeleri için gereklidir. Gerekli uygulamalar henüz yoksa, bu komutu kullanarak yükleyebilirsiniz:

```bash
sudo apt-get install g++ gdb make ninja-build rsync zip
```

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="ubuntu-on-remote-linux-systems"></a>Uzak Linux sistemlerinde Ubuntu

Hedef Linux sisteminin **OpenSSH-Server** , **g + +** , **gdb** **ve yüklü olması** gerekir. **dokja-** yalnızca CMake projeleri için derleme gerekir. **SSH** arka plan programı çalışıyor olmalıdır. IntelliSense desteği için yerel makineli uzak üst bilgilerin otomatik eşitlenmesi için **zip** ve **rsync** gereklidir. Bu uygulamalar henüz yoksa, bunları aşağıdaki şekilde yükleyebilirsiniz:

1. Linux bilgisayarınızda bir kabuk isteminde şunu çalıştırın:

   ```bash
   sudo apt-get install openssh-server g++ gdb make ninja-build rsync zip
   ```

   Sudo komutunu çalıştırmak için kök parolanız istenebilir. Bu durumda, girin ve devam edin. Tamamlandıktan sonra gerekli hizmetler ve araçlar yüklenir.

1. Çalıştıran SSH hizmetinin Linux bilgisayarınızda çalıştığından emin olun:

   ```bash
   sudo service ssh start
   ```

   Bu komut, hizmeti başlatır ve bağlantıları kabul etmeye yönelik olarak arka planda çalıştırır.

::: moniker-end

::: moniker range="msvc-160"

## <a name="fedora-on-wsl"></a>WSL üzerinde Fedora

Fedora **DNF** paket yükleyicisini kullanır. **G + +** , **gdb** , **Make** , **rsync** , **dokja-Build** ve **zip** indirmek için şunu çalıştırın:

   ```bash
   sudo dnf install gcc-g++ gdb rsync ninja-build make zip
   ```

IntelliSense desteği için Visual Studio ile Linux üstbilgilerinin otomatik eşitlenmesi için **zip** ve **rsync** gereklidir. **dokja-derleme** yalnızca CMake projeleri için gereklidir.

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="fedora-on-remote-linux-systems"></a>Uzak Linux sistemlerinde Fedora 'lar

Fedora çalıştıran hedef makine **DNF** paket yükleyicisini kullanır. **OpenSSH-Server** , **g + +** , **gdb** , **Make** , **dokja-Build** , **rsync** ve **zip** indirmek ve ssh daemon 'u yeniden başlatmak için aşağıdaki yönergeleri izleyin. **dokja-derleme** yalnızca CMake projeleri için gereklidir.

1. Linux bilgisayarınızda bir kabuk isteminde şunu çalıştırın:

   ```bash
   sudo dnf install openssh-server gcc-g++ gdb ninja-build make rsync zip
   ```

   Sudo komutunu çalıştırmak için kök parolanız istenebilir. Bu durumda, girin ve devam edin. Tamamlandıktan sonra gerekli hizmetler ve araçlar yüklenir.

1. Çalıştıran SSH hizmetinin Linux bilgisayarınızda çalıştığından emin olun:

   ```bash
   sudo systemctl start sshd
   ```

   Bu komut, hizmeti başlatır ve bağlantıları kabul etmeye yönelik olarak arka planda çalıştırır.

## <a name="next-steps"></a>Sonraki Adımlar

Artık bir Linux projesi oluşturmaya veya açmaya ve hedef sistemde çalışacak şekilde yapılandırmaya hazırsınız. Daha fazla bilgi için bkz.

- [Yeni bir Linux MSBuild C++ projesi oluşturma](create-a-new-linux-project.md)
- [Linux CMake projesi yapılandırma](cmake-linux-project.md)

::: moniker-end
