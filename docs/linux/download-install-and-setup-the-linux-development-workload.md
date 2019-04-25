---
title: Visual Studio'da C++ Linux iş yükünü yükleyin
description: İndirme, yükleme ve Linux iş yükünü Visual Studio'da C++ için Kurulum açıklar.
ms.date: 03/05/2019
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: 74155724abb3a0e02cc27dd8a8d144f142ee4b6f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262859"
---
# <a name="download-install-and-set-up-the-linux-workload"></a>İndirme, yükleme ve Linux iş yükü ayarlayın

Visual Studio 2017 IDE içinde Windows oluşturmak, düzenlemek ve bir Linux fiziksel, sanal makine yürütülmesine C++ projelerinde hata ayıklama için kullanabileceğiniz veya [Linux için Windows alt sistemi](/windows/wsl/about). 

Visual Studio projesine dönüştürmek zorunda kalmadan CMake veya başka bir derleme sistemini kullanan mevcut kod tabanınız üzerinde çalışabilirsiniz. Kod tabanınız platformlar arası ise, hem Windows hem de Visual Studio içinden Linux'u hedefleyebilirsiniz. Örneğin, düzenleme, hata ayıklama ve profil kodunuzu Visual Studio kullanarak Windows üzerinde sonra hızlı bir şekilde yapmak Linux için projeyi yeniden hedefle başka testler yapmak. Linux üst bilgi dosyaları burada Visual Studio kullanan bunları tam IntelliSense sağlamak için yerel makinenize otomatik olarak kopyalanır desteği (deyim tamamlama, Git tanımı vb.).
 
Bu senaryolardan herhangi biri için **C++ ile Linux geliştirme** iş yükü gereklidir. 

## <a name="visual-studio-setup"></a>Visual Studio Kurulumu

1. "Visual Studio yükleyicisi" Windows Arama kutusuna yazın: ![Windows Arama kutusuna](media/visual-studio-installer-search.png)
2. Yükleyici altında arayın **uygulamaları** sonuçlanır ve çift tıklayın. Yükleyici açıldığında seçin **Değiştir**ve ardından **iş yükleri** sekmesi. Ekranı aşağı kaydırarak **diğer araç takımları** seçip **C++ ile Linux geliştirme** iş yükü.

   ![Linux geliştirme iş yükü için Visual C++](media/linuxworkload.png)

1. CMake kullanın veya IOT veya katıştırılmış platformları hedefleyen, Git **Yükleme ayrıntıları** sağ bölmede altında **C++ ile Linux geliştirme**, genişletme **isteğebağlıbileşenler** ve gereksinim duyduğunuz bileşenleri seçin.

    **Visual Studio 2017 sürüm 15.4 ve üzeri**<br/>: Linux CMake desteği, Visual Studio için Linux C++ iş yükünü yüklediğinizde varsayılan olarak seçilidir.

1. Tıklayın **Değiştir** yüklemeye devam etmek için.

## <a name="options-for-creating-a-linux-environment"></a>Bir Linux ortamı oluşturma seçenekleri

Linux makinesi zaten yoksa, Azure'da bir Linux sanal makinesi oluşturabilirsiniz. Daha fazla bilgi için [hızlı başlangıç: Azure portalında bir Linux sanal makinesi oluşturma](/azure/virtual-machines/linux/quick-create-portal).

Windows 10, başka bir seçeneği, Linux için Windows alt sistemi etkinleştirmektir. Daha fazla bilgi için [Windows 10 Yükleme Kılavuzu](/windows/wsl/install-win10).

## <a name="linux-setup-ubuntu"></a>Linux Kurulumu: Ubuntu

Hedef Linux bilgisayarda olmalıdır **openssh-server**, **g ++**, **gdb**, ve **gdbserver** yüklü ve ssh arka plan programı çalışıyor olması gerekir. **zip** otomatik uzak üst bilgiler yerel makineniz için IntelliSense desteği ile eşitlenmesi için gereklidir. Bu uygulamalar zaten mevcut değilse şu şekilde yükleyebilirsiniz:

1. Linux bilgisayarınızda bir kabuk isteminde çalıştırın:

   `sudo apt-get install openssh-server g++ gdb gdbserver zip`

   Sudo komutu nedeniyle, kök parolası istenebilir.  Bu durumda, girin ve devam edin. İşlem tamamlandıktan sonra gerekli hizmetler ve Araçlar yüklenir.

1. Olun ssh, Linux bilgisayarınızda çalıştırarak çalışmıyor:

   `sudo service ssh start`

   Bu hizmeti başlatılır ve arka planda, bağlantıları kabul etmeye hazır çalıştırır.

## <a name="linux-setup-fedora"></a>Linux Kurulumu: Fedora

Fedora çalıştıran hedef makine **dnf** Yükleyici paketi. İndirmek için **openssh-server**, **g ++**, **gdb**, **gdbserver** ve **zip**ve yeniden ssh arka plan programı, bu yönergeleri izleyin:

1. Linux bilgisayarınızda bir kabuk isteminde çalıştırın:

   `sudo dnf install openssh-server gcc-g++ gdb gdb-gdbserver zip`

   Sudo komutu nedeniyle, kök parolası istenebilir.  Bu durumda, girin ve devam edin. İşlem tamamlandıktan sonra gerekli hizmetler ve Araçlar yüklenir.

1. Olun ssh, Linux bilgisayarınızda çalıştırarak çalışmıyor:

   `sudo systemctl start sshd`

   Bu hizmeti başlatılır ve arka planda, bağlantıları kabul etmeye hazır çalıştırır.

## <a name="ensure-you-have-cmake-38-on-the-remote-linux-machine"></a>Uzak Linux makinesinde CMake 3.8 sahip olduğunuzdan emin olun

Kendi Linux distro CMake daha eski bir sürümü olabilir. Visual Studio'da CMake desteği, CMake 3.8 içinde sunulan sunucu modu desteği gerektirir. Bir Microsoft tarafından sağlanan CMake değişken için Linux makinenize en son önceden oluşturulmuş ikilileri indirmek [ https://github.com/Microsoft/CMake/releases ](https://github.com/Microsoft/CMake/releases).
