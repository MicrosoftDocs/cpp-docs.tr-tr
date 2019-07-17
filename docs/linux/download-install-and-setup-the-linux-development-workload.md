---
title: C++ Linux Iş yükünü Visual Studio 'ya yükler
description: Visual Studio 'da için C++ Linux iş yükünün nasıl indirileceği, yükleneceği ve kurulacağı açıklanmaktadır.
ms.date: 06/11/2019
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: 5df7b323d202f398059e92abaeeeedbf73439fa4
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299800"
---
# <a name="download-install-and-set-up-the-linux-workload"></a>Linux iş yükünü indirme, yükleme ve ayarlama

::: moniker range="vs-2015"

Linux projeleri Visual Studio 2017 ve üzeri sürümlerde desteklenir.

::: moniker-end

::: moniker range=">=vs-2017"

Linux fiziksel bilgisayarında, sanal makinede veya [Linux Için Windows alt sisteminde](/windows/wsl/about)yürütülen projeleri oluşturmak C++ , düzenlemek ve hatalarını ayıklamak Için WINDOWS 'ta Visual Studio IDE 'yi kullanabilirsiniz. 

Visual Studio projesine dönüştürmek zorunda kalmadan CMake veya diğer herhangi bir yapı sistemini kullanan mevcut kod tabanınız üzerinde çalışabilirsiniz. Kod tabanınız platformlar arası ise, Visual Studio içinden hem Windows hem de Linux 'u hedefleyebilirsiniz. Örneğin, Visual Studio kullanarak Windows 'da kodunuzu düzenleyebilir, hata ayıklayın ve profil oluşturabilir, daha sonra daha fazla test yapmak üzere Linux için projeyi hızlıca yeniden hedefleyebilirsiniz. Linux üst bilgi dosyaları, tam IntelliSense desteği sağlamak için Visual Studio tarafından kullanılan yerel makinenize otomatik olarak kopyalanır (deyimin tamamlanması, tanıma git vb.). 
 
Bu senaryoların herhangi biri için iş yüküyle **Linux geliştirme C++**  gereklidir. 

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 ' de, oluşturma ve hata ayıklama için ayrı hedefler belirtebilirsiniz. WSL 'yi hedeflerken, uzak bir bağlantı eklemek veya SSH 'yi yapılandırmak artık gerekli değildir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="visual-studio-setup"></a>Visual Studio Kurulumu

1. Windows Arama kutusuna "Visual Studio Yükleyicisi" yazın:

   ![Windows arama kutusu](media/visual-studio-installer-search.png)

2. **Uygulama** sonuçları altında yükleyiciyi bulun ve çift tıklatın. Yükleyici açıldığında, **Değiştir**' i seçin ve sonra **iş yükleri** sekmesine tıklayın. **Diğer araç kümelerine** gidin ve iş yüküyle  **C++ Linux geliştirmeyi** seçin.

   ![Linux C++ geliştirme iş yükü için Visual](media/linuxworkload.png)

1. IoT veya katıştırılmış platformları hedefliyorsanız, sağdaki **Yükleme ayrıntıları** bölmesine gidin ve **Linux ile geliştirme C++** altında, **isteğe bağlı bileşenler** ' i genişletin ve ihtiyacınız olan bileşenleri seçin. Linux için CMake desteği varsayılan olarak seçilidir.

1. Yüklemeye devam etmek için **Değiştir** 'e tıklayın.

## <a name="options-for-creating-a-linux-environment"></a>Linux ortamı oluşturma seçenekleri

Henüz bir Linux makineniz yoksa Azure 'da bir Linux sanal makinesi oluşturabilirsiniz. Daha fazla bilgi için bkz [. hızlı başlangıç: Azure portal](/azure/virtual-machines/linux/quick-create-portal)bir Linux sanal makinesi oluşturun.

Windows 10 ' da, Linux (WSL) için Windows alt sistemine sahip en sevdiğiniz Linux 'u yükleyebilir ve hedefleyebilirsiniz. Daha fazla bilgi için bkz. [Windows 10 Için Linux Için Windows alt sistemi yükleme kılavuzu](/windows/wsl/install-win10). WSL, uygun bir konsol ortamıdır, ancak grafik uygulamalar için önerilmez. 

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

Hedef Linux sisteminde **OpenSSH-Server**, **g + +** , **gdb**ve **gdbserver** yüklü olmalıdır ve SSH arka plan programının çalışıyor olması gerekir. IntelliSense desteği için yerel makineli uzak üst bilgilerin otomatik eşitlenmesi için **zip** gerekir. Bu uygulamalar henüz yoksa, bunları aşağıdaki şekilde yükleyebilirsiniz:

1. Linux bilgisayarınızda bir kabuk isteminde şunu çalıştırın:

   ```bash
   sudo apt-get install openssh-server g++ gdb gdbserver zip
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

Fedora **DNF** paket yükleyicisini kullanır. **G + +** , **gdb**, **rsync** ve **zip**indirmek için şunu çalıştırın:

   ```bash
   sudo dnf install gcc-g++ gdb rsync zip
   ```

IntelliSense desteği için Visual Studio ile Linux üstbilgilerinin otomatik eşitlenmesi için **zip** ve **rsync** gereklidir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="fedora-on-remote-linux-systems"></a>Uzak Linux sistemlerinde Fedora 'lar

Fedora çalıştıran hedef makine **DNF** paket yükleyicisini kullanır. **OpenSSH-Server**, **g + +** , **gdb**, **gdbserver** ve **zip**'i indirmek ve ssh daemon 'u yeniden başlatmak için aşağıdaki yönergeleri izleyin:

1. Linux bilgisayarınızda bir kabuk isteminde şunu çalıştırın:

   ```bash
   sudo dnf install openssh-server gcc-g++ gdb gdb-gdbserver zip
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

Artık bir Linux projesi oluşturmaya veya açmaya ve hedef sistemde çalışacak şekilde yapılandırmaya hazırsınız. Daha fazla bilgi için bkz.:

- [Yeni Linux projesi oluşturma](create-a-new-linux-project.md)
- [Linux CMake projesi yapılandırma](cmake-linux-project.md)
