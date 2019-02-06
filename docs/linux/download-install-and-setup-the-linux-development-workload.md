---
title: Visual Studio'da C++ Linux iş yükünü yükleyin
description: İndirme, yükleme ve Linux iş yükünü Visual Studio'da C++ için Kurulum açıklar.
ms.date: 02/06/2019
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: c01c8ddeeb8439a7610c0f6c7c11b608ab3675d8
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55763898"
---
# <a name="download-install-and-setup-the-linux-workload"></a>İndirme, yükleme ve Linux iş yükünü Kurulumu

Visual Studio IDE içinde Windows oluşturmak, düzenlemek ve bir Linux fiziksel, sanal makine yürütülmesine C++ projelerinde hata ayıklama için kullanabileceğiniz veya [Linux için Windows alt sistemi](/windows/wsl/about). Bu senaryolardan herhangi biri için önce yükleme **C++ ile Linux geliştirme** iş yükü.

## <a name="visual-studio-setup"></a>Visual Studio Kurulumu

1. "Visual Studio yükleyicisi" Windows Arama kutusuna yazın: ![Windows Arama kutusuna](media/visual-studio-installer-search.png)
2. Yükleyici altında arayın **uygulamaları** sonuçlanır ve çift tıklayın. Yükleyici açıldığında seçin **Değiştir**ve ardından **iş yükleri** sekmesi. Ekranı aşağı kaydırarak **diğer araç takımları** seçip **C++ ile Linux geliştirme** iş yükü.

   ![Linux geliştirme iş yükü için Visual C++](media/linuxworkload.png)

1. CMake kullanın veya IOT veya katıştırılmış platformları hedefleyen, Git **Yükleme ayrıntıları** sağ bölmede altında **C++ ile Linux geliştirme**, genişletme **isteğebağlıbileşenler** ve gereksinim duyduğunuz bileşenleri seçin.

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

