---
title: Visual Studio'da C++ Linux iş yükünü yükleyin
description: İndirme, yükleme ve Linux iş yükünü Visual Studio'da C++ için Kurulum açıklar.
ms.date: 06/11/2019
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: d5c099794f781fa9e6217f3796d24d1a63fd7b53
ms.sourcegitcommit: fde637f823494532314790602c2819f889706ff6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67042750"
---
# <a name="download-install-and-set-up-the-linux-workload"></a>İndirme, yükleme ve Linux iş yükü ayarlayın

::: moniker range="vs-2015"

Linux projeleri, Visual Studio 2017 ve sonraki sürümlerde desteklenir.

::: moniker-end

::: moniker range=">=vs-2017"

Visual Studio IDE içinde Windows oluşturmak, düzenlemek ve bir Linux fiziksel, sanal makine yürütülmesine C++ projelerinde hata ayıklama için kullanabileceğiniz veya [Linux için Windows alt sistemi](/windows/wsl/about). 

Visual Studio projesine dönüştürmek zorunda kalmadan CMake veya başka bir derleme sistemini kullanan mevcut kod tabanınız üzerinde çalışabilirsiniz. Kod tabanınız platformlar arası ise, hem Windows hem de Visual Studio içinden Linux'u hedefleyebilirsiniz. Örneğin, düzenleme, hata ayıklama ve profil kodunuzu Visual Studio kullanarak Windows üzerinde sonra hızlı bir şekilde yapmak Linux için projeyi yeniden hedefle başka testler yapmak. Linux üst bilgi dosyaları burada Visual Studio kullanan bunları tam IntelliSense sağlamak için yerel makinenize otomatik olarak kopyalanır desteği (deyim tamamlama, Git tanımı vb.). 
 
Bu senaryolardan herhangi biri için **C++ ile Linux geliştirme** iş yükü gereklidir. 

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 derleme ve hata ayıklama için ayrı hedefleri belirtebilirsiniz. WSL hedeflenirken artık uzak bağlantı eklemek veya SSH'ı yapılandırmak gereklidir.

Destek [AddressSanitizer (IsObject)](https://github.com/google/sanitizers/wiki/AddressSanitizer) Linux projeleri için Visual Studio'da tümleşiktir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="visual-studio-setup"></a>Visual Studio Kurulumu

1. "Visual Studio yükleyicisi" Windows Arama kutusuna yazın:

   ![Windows Arama kutusuna](media/visual-studio-installer-search.png)

2. Yükleyici altında arayın **uygulamaları** sonuçlanır ve çift tıklayın. Yükleyici açıldığında seçin **Değiştir**ve ardından **iş yükleri** sekmesi. Ekranı aşağı kaydırarak **diğer araç takımları** seçip **C++ ile Linux geliştirme** iş yükü.

   ![Linux geliştirme iş yükü için Visual C++](media/linuxworkload.png)

1. IOT veya katıştırılmış platformları hedefliyorsanız, Git **Yükleme ayrıntıları** sağ bölmede altında **ile Linux geliştirme C++** , genişletme **isteğe bağlı bileşenler**ve gereksinim duyduğunuz bileşenleri seçin. Linux CMake desteği, varsayılan olarak seçilidir.

1. Tıklayın **Değiştir** yüklemeye devam etmek için.

## <a name="options-for-creating-a-linux-environment"></a>Bir Linux ortamı oluşturma seçenekleri

Linux makinesi zaten yoksa, Azure'da bir Linux sanal makinesi oluşturabilirsiniz. Daha fazla bilgi için [hızlı başlangıç: Azure portalında bir Linux sanal makinesi oluşturma](/azure/virtual-machines/linux/quick-create-portal).

Windows 10'da yükleyebilir ve Linux (WSL) için Windows alt sisteminde, sık kullandığınız Linux distro hedefleyin. Daha fazla bilgi için [Linux Yükleme Kılavuzu için Windows 10 için Windows alt sistemi](/windows/wsl/install-win10). WSL kullanışlı Konsolu ortamını olsa da grafik uygulamaları için önerilmez. 

::: moniker-end

::: moniker range="vs-2019"

## <a name="linux-setup-ubuntu-on-wsl"></a>Linux Kurulumu: Ubuntu'da WSL

WSL hedeflenirken uzak bir bağlantı ekleyin veya derleme ve hata ayıklama için SSH yapılandırmak için gerek yoktur. **zip** ve **rsync** otomatik IntelliSense desteği için Linux üstbilgileri Visual Studio ile eşitlenmesi için gereklidir. Gerekli uygulamaları henüz mevcut değilse şu şekilde yükleyebilirsiniz:

```bash
sudo apt-get install g++ gdb make rsync zip
```
::: moniker-end

::: moniker range=">=vs-2017"

## <a name="ubuntu-on-remote-linux-systems"></a>Uzak Linux sistemlerinde ubuntu

' % S'hedefi Linux sistem olmalıdır **openssh-server**, **g ++** , **gdb**, ve **gdbserver** yüklü ve ssh arka plan programı çalışıyor olması gerekir. **zip** otomatik uzak üst bilgiler yerel makineniz için IntelliSense desteği ile eşitlenmesi için gereklidir. Bu uygulamalar zaten mevcut değilse şu şekilde yükleyebilirsiniz:

1. Linux bilgisayarınızda bir kabuk isteminde çalıştırın:

   ```bash
   sudo apt-get install openssh-server g++ gdb gdbserver zip
   ```

   Sudo komutu nedeniyle, kök parolası istenebilir.  Bu durumda, girin ve devam edin. İşlem tamamlandıktan sonra gerekli hizmetler ve Araçlar yüklenir.

1. Olun ssh, Linux bilgisayarınızda çalıştırarak çalışmıyor:

   ```bash
   sudo service ssh start
   ```
   Bu hizmeti başlatılır ve arka planda, bağlantıları kabul etmeye hazır çalıştırır.

::: moniker-end

::: moniker range="vs-2019"

## <a name="fedora-on-wsl"></a>Fedora WSL üzerinde

Fedora kullanan **dnf** Yükleyici paketi. İndirmek için **g ++** , **gdb**, **rsync** ve **zip**çalıştırın:

   ```bash
   sudo dnf install gcc-g++ gdb rsync zip
   ```

**zip** ve **rsync** otomatik IntelliSense desteği için Linux üstbilgileri Visual Studio ile eşitlenmesi için gereklidir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="fedora-on-remote-linux-systems"></a>Uzak Linux sistemlerinde fedora

Fedora çalıştıran hedef makine **dnf** Yükleyici paketi. İndirmek için **openssh-server**, **g ++** , **gdb**, **gdbserver** ve **zip**ve yeniden ssh arka plan programı, bu yönergeleri izleyin:

1. Linux bilgisayarınızda bir kabuk isteminde çalıştırın:

   ```bash
   sudo dnf install openssh-server gcc-g++ gdb gdb-gdbserver zip
   ```
   Sudo komutu nedeniyle, kök parolası istenebilir.  Bu durumda, girin ve devam edin. İşlem tamamlandıktan sonra gerekli hizmetler ve Araçlar yüklenir.

1. Olun ssh, Linux bilgisayarınızda çalıştırarak çalışmıyor:

   ```bash
   sudo systemctl start sshd
   ```

   Bu hizmeti başlatılır ve arka planda, bağlantıları kabul etmeye hazır çalıştırır.

::: moniker-end

::: moniker range="vs-2015"

Linux desteği C++ geliştirme ve sonrasında Visual Studio 2017'de kullanılabilir.

::: moniker-end

## <a name="next-steps"></a>Sonraki Adımlar

Şimdi oluşturun veya Linux projesi açın ve hedef sistem üzerinde çalışacak şekilde yapılandırmak hazır olursunuz. Daha fazla bilgi için bkz.:

- [Yeni Linux projesi oluşturma](create-a-new-linux-project.md)
- [Linux CMake projesi yapılandırma](cmake-linux-project.md)
