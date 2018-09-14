---
title: Visual Studio'da C++ Linux iş yükünü yükleyin | Microsoft Docs
description: İndirme, yükleme ve Linux iş yükünü Visual Studio'da C++ için Kurulum açıklar.
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 403f1bcd8634c3f471f34ff1266501de5bf05d52
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601398"
---
# <a name="download-install-and-setup-the-linux-workload"></a>İndirme, yükleme ve Linux iş yükünü Kurulumu

Visual Studio IDE içinde Windows oluşturmak, düzenlemek ve bir Linux fiziksel, sanal makine yürütülmesine C++ projelerinde hata ayıklama için kullanabileceğiniz veya [Linux için Windows alt sistemi](/windows/wsl/about). Bu senaryolardan herhangi biri için önce yükleme **C++ ile Linux geliştirme** iş yükü.

## <a name="visual-studio-setup"></a>Visual Studio Kurulumu

1. Windows arama menüsünde "Visual Studio yükleyicisi" yazın. Bunun altında arayın **uygulamaları** sonuçlanır ve çift tıklayın. Yükleyici açıldığında seçin **Değiştir**ve ardından **iş yükleri** sekmesi. Ekranı aşağı kaydırarak **diğer araç takımları** seçip **C++ ile Linux geliştirme** iş yükü.

   ![Linux geliştirme iş yükü için Visual C++](media/linuxworkload.png)

1. CMake kullanın veya IOT veya katıştırılmış platformları hedefleyen, Git **Yükleme ayrıntıları** sağ bölmede altında **C++ ile Linux geliştirme**, genişletme **isteğebağlıbileşenler** ve gereksinim duyduğunuz bileşenleri seçin. 

1. Tıklayın **Değiştir** yüklemeye devam etmek için.


## <a name="options-for-creating-a-linux-environment"></a>Bir Linux ortamı oluşturma seçenekleri

Linux makinesi zaten yoksa, Azure'da bir Linux sanal makinesi oluşturabilirsiniz. Daha fazla bilgi için [hızlı başlangıç: Azure portalında bir Linux sanal makinesi oluşturma](/azure/virtual-machines/linux/quick-create-portal).

Windows 10, başka bir seçeneği, Linux için Windows alt sistemi etkinleştirmektir. Daha fazla bilgi için [Windows 10 Yükleme Kılavuzu](/windows/wsl/install-win10).

## <a name="linux-setup"></a>Linux Kurulumu

Hedef Linux bilgisayarda olmalıdır **openssh-server**, **g ++**, **gdb**, ve **gdbserver** yüklü ve ssh arka plan programı çalışıyor olması gerekir. **zip** otomatik uzak üst bilgiler yerel makineniz için IntelliSense desteği ile eşitlenmesi için gereklidir. Bu uygulamalar zaten mevcut değilse şu şekilde yükleyebilirsiniz:

1. Linux bilgisayarınızda bir kabuk isteminde çalıştırın:

   `sudo apt-get install openssh-server g++ gdb gdbserver zip`

   Sudo komutu nedeniyle, kök parolası istenebilir.  Bu durumda, girin ve devam edin.  İşlem tamamlandıktan sonra bu hizmetlerin ve araçların yüklenir.

1. Olun ssh, Linux bilgisayarınızda çalıştırarak çalışmıyor:

   `sudo service ssh start`

   Bu hizmeti başlatın ve arka planda, bağlantıları kabul etmeye hazır çalıştırın.
