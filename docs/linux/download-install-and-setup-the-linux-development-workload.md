---
title: C++ Linux Iş yükünü Visual Studio 'ya yükler
description: Visual Studio 'da için C++ Linux iş yükünün nasıl indirileceği, yükleneceği ve kurulacağı açıklanmaktadır.
ms.date: 06/11/2019
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: 719fb9a04c3b0090a1ae5442f881ba6b7d2136c5
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077634"
---
# <a name="download-install-and-set-up-the-linux-workload"></a>Linux iş yükünü indirme, yükleme ve ayarlama

::: moniker range="vs-2015"

Linux projeleri Visual Studio 2017 ve üzeri sürümlerde desteklenir.

::: moniker-end

::: moniker range=">=vs-2017"

Windows üzerinde Visual Studio IDE 'yi kullanarak, uzak bir Linux sisteminde, sanal makinede C++ veya [Linux Için Windows alt sisteminde](/windows/wsl/about)yürütülen projeleri oluşturabilir, düzenleyebilir ve hata ayıklaması yapabilirsiniz.

Visual Studio projesine dönüştürmek zorunda kalmadan CMake kullanan mevcut kod tabanınız üzerinde çalışabilirsiniz. Kod tabanınız platformlar arası ise, Visual Studio içinden hem Windows hem de Linux 'u hedefleyebilirsiniz. Örneğin, Visual Studio kullanarak Windows 'da kodunuzu düzenleyebilir, oluşturabilir ve hata ayıklamanıza ve Linux ortamında derleyip hata ayıklamanın ardından Linux için projeyi hızla yeniden hedefleyebilirsiniz. Linux üst bilgi dosyaları, Visual Studio 'Nun tam IntelliSense desteği sağlamak için bunları kullandığı yerel makinenize otomatik olarak kopyalanır (deyimin tamamlanması, tanıma git vb.).

Bu senaryoların herhangi biri için iş yüküyle **Linux geliştirme C++**  gereklidir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="visual-studio-setup"></a>Visual Studio Kurulumu

1. Windows Arama kutusuna "Visual Studio Yükleyicisi" yazın:

   ![Windows arama kutusu](media/visual-studio-installer-search.png)

2. **Uygulama** sonuçları altında yükleyiciyi bulun ve çift tıklatın. Yükleyici açıldığında, **Değiştir**' i seçin ve sonra **iş yükleri** sekmesine tıklayın. **diğer araç kümelerine** gidin ve iş yüküyle **Linux geliştirmeyi C++**  seçin.

   ![Linux C++ geliştirme iş yükü için Visual](media/linuxworkload.png)

1. IoT veya katıştırılmış platformları hedefliyorsanız, sağdaki **Yükleme ayrıntıları** bölmesine gidin. **Linux ile geliştirme altında C++** , **isteğe bağlı bileşenler**' i genişletin ve ihtiyacınız olan bileşenleri seçin. Linux için CMake desteği varsayılan olarak seçilidir.

1. Yüklemeye devam etmek için **Değiştir** 'e tıklayın.

## <a name="options-for-creating-a-linux-environment"></a>Linux ortamı oluşturma seçenekleri

Henüz bir Linux makineniz yoksa Azure 'da bir Linux sanal makinesi oluşturabilirsiniz. Daha fazla bilgi için bkz. [hızlı başlangıç: Azure Portal Linux sanal makinesi oluşturma](/azure/virtual-machines/linux/quick-create-portal).

Windows 10 ' da, Linux (WSL) için Windows alt sistemine sahip en sevdiğiniz Linux 'u yükleyebilir ve hedefleyebilirsiniz. Daha fazla bilgi için bkz. [Windows 10 Için Linux Için Windows alt sistemi yükleme kılavuzu](/windows/wsl/install-win10). Windows Mağazası 'na erişemiyorsanız, [WSL 'nin geçmiş paketlerini el ile indirebilirsiniz](/windows/wsl/install-manual). WSL, uygun bir konsol ortamıdır, ancak grafik uygulamalar için önerilmez.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 'da Linux projeleri, uzak Linux sisteminize veya WSL 'ye aşağıdaki bağımlılıkların yüklenmesini gerektirir:

- **Derleyici** -Visual Studio 2019, GCC ve [Clang](/cpp/build/clang-support-cmake?view=vs-2019)için kullanıma hazır destek içerir.
- **gdb** -Visual Studio, Linux sisteminde otomatik olarak gdb 'yi başlatır ve Linux üzerinde tam uygunlukta hata ayıklama deneyimi sağlamak Için Visual Studio hata ayıklayıcısının ön ucu kullanır.
- **rsync** ve **ZIP** -rsync ve zip dahil, Visual Studio 'nun IntelliSense tarafından kullanılmak üzere Linux sisteminizden Windows dosya sistemine üst bilgi dosyalarını ayıklamasına olanak tanır.
- **yapabilir**
- **OpenSSH-Server** (yalnızca uzak Linux sistemleri)-Visual Studio, GÜVENLI bir SSH bağlantısı üzerinden uzak Linux sistemlerine bağlanır.
- **CMake** (yalnızca CMake projeleri)- [Linux için Microsoft 'un statik bağlantılı CMake İkililerini](https://github.com/microsoft/CMake/releases)yükleyebilirsiniz.

Aşağıdaki komutlar Clang yerine g + + kullandığınızı varsayar.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 'da Linux projeleri, uzak Linux sisteminize veya WSL 'ye aşağıdaki bağımlılıkların yüklenmesini gerektirir:

- **GCC** -Visual Studio 2017, gcc için kullanıma hazır destek içerir.
- **gdb** -Visual Studio, Linux sisteminde otomatik olarak gdb 'yi başlatır ve Linux üzerinde tam uygunlukta hata ayıklama deneyimi sağlamak Için Visual Studio hata ayıklayıcısının ön ucu kullanır.
- **rsync** ve **ZIP** -rsync ve zip dahil, Visual Studio 'Nun IntelliSense için kullanılacak Windows dosya sistemine Linux sisteminizden başlık dosyalarını ayıklamasına olanak tanır.
- **yapabilir**
- **OpenSSH-Server** -Visual Studio, GÜVENLI bir SSH bağlantısı üzerinden uzak Linux sistemlerine bağlanır.
- **CMake** (yalnızca CMake projeleri)- [Linux için Microsoft 'un statik bağlantılı CMake İkililerini](https://github.com/microsoft/CMake/releases)yükleyebilirsiniz.

::: moniker-end

::: moniker range="vs-2019"

## <a name="linux-setup-ubuntu-on-wsl"></a>Linux Kurulumu: WSL üzerinde Ubuntu

WSL 'yi hedeflerken, derlemek ve hata ayıklamak için uzak bir bağlantı eklemeye ya da SSH 'yi yapılandırmaya gerek yoktur. IntelliSense desteği için Visual Studio ile Linux üstbilgilerinin otomatik eşitlenmesi için **zip** ve **rsync** gereklidir. Gerekli uygulamalar henüz yoksa, bunları aşağıdaki şekilde yükleyebilirsiniz:

```bash
sudo apt-get install g++ gdb make rsync zip
```

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="ubuntu-on-remote-linux-systems"></a>Uzak Linux sistemlerinde Ubuntu

Hedef Linux sisteminin **OpenSSH-Server**, **g + +** , **gdb** **ve yüklü olması gerekir ve SSH** arka plan programının çalışıyor olması gerekir. IntelliSense desteği için yerel makineli uzak üst bilgilerin otomatik eşitlenmesi için **zip** ve **rsync** gereklidir. Bu uygulamalar henüz yoksa, bunları aşağıdaki şekilde yükleyebilirsiniz:

1. Linux bilgisayarınızda bir kabuk isteminde şunu çalıştırın:

   ```bash
   sudo apt-get install openssh-server g++ gdb make rsync zip
   ```

   Sudo komutu nedeniyle kök parolanız istenebilir.  Bu durumda, girin ve devam edin. Tamamlandıktan sonra gerekli hizmetler ve araçlar yüklenir.

1. Çalıştıran SSH hizmetinin Linux bilgisayarınızda çalıştığından emin olun:

   ```bash
   sudo service ssh start
   ```

   Bu, hizmeti başlatır ve bağlantıları kabul etmeye, arka planda çalıştırır.

::: moniker-end

::: moniker range="vs-2019"

## <a name="fedora-on-wsl"></a>WSL üzerinde Fedora

Fedora **DNF** paket yükleyicisini kullanır. **G + +** , **gdb**, **Make**, **rsync** ve **zip**indirmek için şunu çalıştırın:

   ```bash
   sudo dnf install gcc-g++ gdb rsync make zip
   ```

IntelliSense desteği için Visual Studio ile Linux üstbilgilerinin otomatik eşitlenmesi için **zip** ve **rsync** gereklidir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="fedora-on-remote-linux-systems"></a>Uzak Linux sistemlerinde Fedora 'lar

Fedora çalıştıran hedef makine **DNF** paket yükleyicisini kullanır. **OpenSSH-Server**, **g + +** , **gdb**, **Make**, **rsync**ve **zip**indirmek ve ssh daemon 'u yeniden başlatmak için aşağıdaki yönergeleri izleyin:

1. Linux bilgisayarınızda bir kabuk isteminde şunu çalıştırın:

   ```bash
   sudo dnf install openssh-server gcc-g++ gdb make rsync zip
   ```

   Sudo komutu nedeniyle kök parolanız istenebilir.  Bu durumda, girin ve devam edin. Tamamlandıktan sonra gerekli hizmetler ve araçlar yüklenir.

1. Çalıştıran SSH hizmetinin Linux bilgisayarınızda çalıştığından emin olun:

   ```bash
   sudo systemctl start sshd
   ```

   Bu, hizmeti başlatır ve bağlantıları kabul etmeye, arka planda çalıştırır.

::: moniker-end

::: moniker range="vs-2015"

Linux C++ geliştirmeye yönelik destek, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

## <a name="next-steps"></a>Sonraki Adımlar

Artık bir Linux projesi oluşturmaya veya açmaya ve hedef sistemde çalışacak şekilde yapılandırmaya hazırsınız. Daha fazla bilgi için bkz.

- [Yeni Linux projesi oluşturma](create-a-new-linux-project.md)
- [Linux CMake projesi yapılandırma](cmake-linux-project.md)
