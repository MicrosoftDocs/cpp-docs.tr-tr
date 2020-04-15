---
title: Visual Studio'da C++ Linux iş yükünü yükleyin
description: Visual Studio'da C++ için Linux iş yükünü niçin indirecek, yükleyip kuracağız.
ms.date: 06/11/2019
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: 8e10521ab35f3d85ced8bffd771b4e101d4d4fe6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364337"
---
# <a name="download-install-and-set-up-the-linux-workload"></a>Linux iş yükünü indirin, kurun ve ayarlayın

::: moniker range="vs-2015"

Linux projeleri Visual Studio 2017 ve sonrası desteklenir.

::: moniker-end

::: moniker range=">=vs-2017"

Uzak bir Linux sistemi, sanal makine veya [Linux için Windows Alt Sistemi](/windows/wsl/about)üzerinde yürüten C++ projeleri oluşturmak, bunları gerçekleştirmek ve hata ayıklamak için Windows'daki Visual Studio IDE'yi kullanabilirsiniz.

Bir Visual Studio projesine dönüştürmek zorunda kalmadan CMake kullanan varolan kod tabanı üzerinde çalışabilirsiniz. Kod tabanınız çapraz platformsa, Visual Studio içinden hem Windows'u hem de Linux'u hedefleyebilirsiniz. Örneğin, Visual Studio'yu kullanarak Windows'da kodunuzu dikileyebilir, oluşturabilir ve hata ayıklayabilir, ardından Linux'un Linux ortamında oluşturması ve hata ayıklama sını sağlamak için projeyi hızla yeniden hedefleyebilirsiniz. Linux başlık dosyaları otomatik olarak yerel makinenize kopyalanır ve Visual Studio bunları tam IntelliSense desteği sağlamak için kullanır (Bildirim Tamamlama, Tanıma Git vb.).

Bu senaryolardan herhangi biri için C++ iş **yüküne sahip Linux geliştirme** gereklidir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="visual-studio-setup"></a>Visual Studio kurulumu

1. Windows arama kutusuna "Visual Studio Installer" yazın:

   ![Windows arama kutusu](media/visual-studio-installer-search.png)

1. **Apps** sonuçlarının altındaki yükleyiciyi arayın ve çift tıklatın. Yükleyici **açıldığında, Değiştir'i**seçin ve ardından **İş Yükleri** **sekmesine** tıklayın. **Linux development with C++**

   ![Linux Geliştirme iş yükü için Visual C++](media/linuxworkload.png)

1. IoT veya gömülü platformları hedefliyorsanız, sağdaki **Yükleme ayrıntıları** bölmesine gidin. **C++ ile Linux geliştirme**altında, **İsteğe Bağlı Bileşenleri**genişletin ve ihtiyacınız olan bileşenleri seçin. Linux için CMake desteği varsayılan olarak seçilir.

1. Yüklemeye devam etmek için **Değiştir'i** tıklatın.

## <a name="options-for-creating-a-linux-environment"></a>Linux ortamı oluşturma seçenekleri

Zaten bir Linux makineniz yoksa, Azure'da bir Linux Sanal Makinesi oluşturabilirsiniz. Daha fazla bilgi için [Bkz. Quickstart: Azure portalında bir Linux sanal makinesi oluşturun.](/azure/virtual-machines/linux/quick-create-portal)

Windows 10'da, en sevdiğiniz Linux dağıtımını Linux için Windows Alt Sistemi'ne (WSL) yükleyebilir ve hedefleyebilirsiniz. Daha fazla bilgi için, [Windows 10 için Linux Yükleme Kılavuzu için Windows Alt Sistemi'ne](/windows/wsl/install-win10)bakın. Windows Mağazası'na erişemiyorsanız, [WSL dağıtım paketlerini el ile indirebilirsiniz.](/windows/wsl/install-manual) WSL kullanışlı bir konsol ortamıdır, ancak grafik uygulamalar için önerilmez.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio'daki Linux projeleri, uzak Linux sisteminize veya WSL'nize aşağıdaki bağımlılıkların yüklenmesini gerektirir:

- **Bir derleyici** - Visual Studio 2019 GCC ve [Clang](/cpp/build/clang-support-cmake?view=vs-2019)için out-of-the-box desteği vardır.
- **gdb** - Visual Studio otomatik olarak Linux sisteminde gdb başlattı ve Linux üzerinde tam sadakat hata ayıklama deneyimi sağlamak için Visual Studio hata ayıklama ön ucunu kullanır.
- **rsync** ve **zip** - rsync ve zip dahil Visual Studio IntelliSense tarafından kullanılmak üzere Windows dosya sistemine Linux sisteminden başlık dosyaları ayıklamak için izin verir.
- **yapmak**
- **openssh-server** (yalnızca uzak Linux sistemleri) - Visual Studio güvenli bir SSH bağlantısı üzerinden uzak Linux sistemlerine bağlanır.
- **CMake** (Yalnızca CMake projeleri) - [Microsoft'un statik olarak bağlı CMake ikililerini Linux için](https://github.com/microsoft/CMake/releases)yükleyebilirsiniz.
- **ninja-build** (Yalnızca CMake projeleri)- [Ninja](https://ninja-build.org/) Visual Studio 2019 sürüm 16.6 veya daha sonra Linux ve WSL yapılandırmaları için varsayılan jeneratördür.

Aşağıdaki komutlar clang yerine g++ kullandığınızı varsayar.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio'daki Linux projeleri, uzak Linux sisteminize veya WSL'nize aşağıdaki bağımlılıkların yüklenmesini gerektirir:

- **gcc** - Visual Studio 2017, GCC için hazır destek tespin.
- **gdb** - Visual Studio otomatik olarak Linux sisteminde gdb başlattı ve Linux üzerinde tam sadakat hata ayıklama deneyimi sağlamak için Visual Studio hata ayıklama ön ucunu kullanır.
- **rsync** ve **zip** - rsync ve zip dahil Visual Studio IntelliSense için kullanmak için Windows dosya sistemine Linux sisteminden başlık dosyaları ayıklamak için izin verir.
- **yapmak**
- **openssh-server** - Visual Studio güvenli bir SSH bağlantısı üzerinden uzak Linux sistemlerine bağlanır.
- **CMake** (Yalnızca CMake projeleri) - [Microsoft'un statik olarak bağlı CMake ikililerini Linux için](https://github.com/microsoft/CMake/releases)yükleyebilirsiniz.

::: moniker-end

::: moniker range="vs-2019"

## <a name="linux-setup-ubuntu-on-wsl"></a>Linux kurulumu: Ubuntu WSL üzerinde

WSL'yi hedefliyorsanız, oluşturmak ve hata ayıklamak için uzak bağlantı eklemenize veya SSH'yi yapılandırmaya gerek yoktur. **zip** ve **rsync** Intellisense desteği için Visual Studio ile Linux başlıkları otomatik senkronizasyon için gereklidir. Gerekli uygulamalar zaten yoksa, bunları aşağıdaki gibi yükleyebilirsiniz. **ninja-build** sadece CMake projeleri için gereklidir.

```bash
sudo apt-get install g++ gdb make ninja-build rsync zip
```

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="ubuntu-on-remote-linux-systems"></a>Uzak Linux sistemleri üzerinde Ubuntu

Hedef Linux sistemi **openssh-server,** **g++**, **gdb**, **ninja-build** (CMake projeleri sadece) olmalı ve yüklü **yapmak** ve ssh daemon çalışıyor olmalıdır. **zip** ve **rsync** Intellisense desteği için yerel makine ile uzak başlıkları otomatik senkronize için gereklidir. Bu uygulamalar zaten mevcut değilse, bunları aşağıdaki gibi yükleyebilirsiniz:

1. Linux bilgisayarınızdaki bir kabuk isteminde çalıştırın:

   ```bash
   sudo apt-get install openssh-server g++ gdb make ninja-build rsync zip
   ```

   Sudo komutu nedeniyle kök parolanız istenebilir.  Eğer öyleyse, girin ve devam edin. Tamamlandıktan sonra, gerekli hizmetler ve araçlar yüklenir.

1. Ssh hizmetinin Linux bilgisayarınızda çalıştırılarak çalıştırdığından emin olun:

   ```bash
   sudo service ssh start
   ```

   Bu hizmet başlar ve bağlantıları kabul etmeye hazır, arka planda çalışır.

::: moniker-end

::: moniker range="vs-2019"

## <a name="fedora-on-wsl"></a>Fedora WSL üzerinde

Fedora **dnf** paket yükleyici kullanır. **g++** indirmek için , **gdb**, **yapmak**, **rsync**, **ninja-build**, ve **zip**, çalıştır:

   ```bash
   sudo dnf install gcc-g++ gdb rsync ninja-build make zip
   ```

**zip** ve **rsync** Intellisense desteği için Visual Studio ile Linux başlıkları otomatik senkronizasyon için gereklidir. **ninja-build** sadece CMake projeleri için gereklidir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="fedora-on-remote-linux-systems"></a>Uzak Linux sistemlerinde Fedora

Fedora'yı çalıştıran hedef makine **dnf** paket yükleyicisini kullanır. **Openssh-server**indirmek için , **g++**, **gdb**, **yapmak**, **ninja-build**, **rsync**, ve **zip**, ve ssh daemon yeniden, bu talimatları izleyin. **ninja-build** sadece CMake projeleri için gereklidir.

1. Linux bilgisayarınızdaki bir kabuk isteminde çalıştırın:

   ```bash
   sudo dnf install openssh-server gcc-g++ gdb ninja-build make rsync zip
   ```

   Sudo komutu nedeniyle kök parolanız istenebilir.  Eğer öyleyse, girin ve devam edin. Tamamlandıktan sonra, gerekli hizmetler ve araçlar yüklenir.

1. Ssh hizmetinin Linux bilgisayarınızda çalıştırılarak çalıştırdığından emin olun:

   ```bash
   sudo systemctl start sshd
   ```

   Bu hizmet başlar ve bağlantıları kabul etmeye hazır, arka planda çalışır.

::: moniker-end

::: moniker range="vs-2015"

Linux C++ geliştirme desteği Visual Studio 2017 ve sonraki sürümlerinde kullanılabilir.

::: moniker-end

## <a name="next-steps"></a>Sonraki Adımlar

Artık bir Linux projesi oluşturmaya veya açmaya ve hedef sistemde çalışacak şekilde yapılandırmaya hazırsınız. Daha fazla bilgi için bkz.

- [Yeni bir Linux projesi oluşturun](create-a-new-linux-project.md)
- [Linux CMake projesi yapılandırma](cmake-linux-project.md)
