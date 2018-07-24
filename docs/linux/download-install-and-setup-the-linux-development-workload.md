---
title: Visual Studio'da C++ Linux iş yükünü yükleyin | Microsoft Docs
description: İndirme, yükleme ve Linux iş yükünü Visual Studio'da C++ için Kurulum açıklar.
ms.custom: ''
ms.date: 07/20/2018
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
ms.openlocfilehash: e33b9ac72ca7691ccbb80a9a30349d3a1e31e194
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207565"
---
# <a name="download-install-and-setup-the-linux-workload"></a>İndirme, yükleme ve Linux iş yükünü Kurulumu

Visual Studio IDE oluşturmak ve Linux C++ projelerinde hata ayıklamak üzere kullanmak için yüklemelisiniz **C++ ile Linux geliştirme** iş yükü.

## <a name="visual-studio-setup"></a>Visual Studio Kurulumu
1. Visual Studio Yükleyicisi'ni başlatın ve seçin **C++ ile Linux geliştirme** iş yükü.

   ![Linux geliştirme uzantısı için Visual C++](media/linuxworkload.png)

2. Tıklayın **yükleme** yüklemeye devam etmek için.

## <a name="linux-setup"></a>Linux Kurulumu
Hedef Linux bilgisayarda olmalıdır **openssh-server**, **g ++**, **gdb**, ve **gdbserver** yüklü ve ssh arka plan programı çalışıyor olması gerekir.  Bunlar zaten mevcut değilse, şu şekilde yükleyebilirsiniz:
 
1. Linux bilgisayarınızda bir kabuk isteminde çalıştırın:

   `sudo apt-get install openssh-server g++ gdb gdbserver`

   Sudo komutu nedeniyle, kök parolası istenebilir.  Bu durumda, girin ve devam edin.  İşlem tamamlandıktan sonra bu hizmetlerin ve araçların yüklenir.

1. Olun ssh, Linux bilgisayarınızda çalıştırarak çalışmıyor:

   `sudo service ssh start`
   
   Bu hizmeti başlatın ve arka planda, bağlantıları kabul etmeye hazır çalıştırın.
