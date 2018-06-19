---
title: İndirme, yükleme ve Linux iş yükü Kurulumu | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
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
ms.openlocfilehash: 1d28f0db0ff91dbdb08c9ca88dfe197e8942a7f4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33329442"
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
