---
title: "İndirme, yükleme ve Linux iş yükü Kurulumu | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d2e19ee03483dce82846e7e7bbb0ab103e01203f
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="download-install-and-setup-the-linux-workload"></a>İndirme, yükleme ve Linux iş yükü Kurulumu

## <a name="visual-studio-setup"></a>Visual Studio Kurulumu
1. Visual Studio Yükleyicisi'ni başlatın ve seçin **C++ ile Linux geliştirme** iş yükü.

   ![Visual C++ Linux geliştirmesi uzantısı](media/linuxworkload.png)

2. Tıklatın **yükleme** yüklemeye devam etmek için.

## <a name="linux-setup"></a>Linux Kurulumu
Hedef Linux bilgisayarda olmalıdır **openssh server**, **g ++**, **gdb**, ve **gdbserver** yüklü ve ssh arka plan programı çalışıyor olmalıdır.  Bunlar zaten mevcut değilse, aşağıdaki gibi yükleyebilirsiniz:
 
1. Linux bilgisayarınızda bir kabuk isteminde çalıştırın:

   `sudo apt-get install openssh-server g++ gdb gdbserver`

   Kök parolanızı sudo komutu nedeniyle istenebilir.  Bu durumda, girin ve devam edin.  Tamamlandıktan sonra bu hizmetler ve Araçlar yüklenir.

1. Olun ssh Linux bilgisayarınızda çalıştırarak çalışmıyor:

   `sudo service ssh start`
   
   Bu hizmeti başlatın ve arka planda, bağlantı kabul etmeye hazır çalıştırın.
