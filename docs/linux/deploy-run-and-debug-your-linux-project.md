---
title: Dağıtma, çalıştırmak ve Linux projenizin hatalarını ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/06/2017
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: b3f3742f8a63bf93f5686143daeea23ba13255be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="deploy-run-and-debug-your-linux-project"></a>Dağıtma, çalıştırmak ve Linux projenizin hatalarını ayıklama

Bir Linux projesi oluşturduktan sonra proje kullanarak bağlandığınız [Linux Bağlantı Yöneticisi](../linux/connect-to-your-remote-linux-computer.md), çalıştırmak ve projenin hata ayıklamasını. Derleme, yürütme ve uzak hedefte kodda hata ayıklama.

Etkileşim ve Linux projenizin hatalarını ayıklamak üzere birkaç yolu vardır.

* Kesme noktaları, Gözcü pencerelerini ve bir değişkeni bekleyerek gibi geleneksel Visual Studio özellikleri kullanarak hata ayıklama. Diğer proje türleri için normalde yaptığınız gibi bu yöntemleri kullanarak hata ayıklama.
* Bir özel Linux konsol penceresinde hedef bilgisayardan çıktısını görüntüleyin. Hedef bilgisayara giriş göndermek için konsolunu da kullanabilirsiniz.

## <a name="debug-your-linux-project"></a>Linux projenizin hatalarını ayıklama

1. Hata ayıklama modu seçin **hata ayıklama** özellik sayfası.

    GDB Linux üzerinde çalışan uygulamalar hata ayıklamak için kullanılır.  Ancak, bu öğesinden seçilebilir iki farklı modda çalıştırabilirsiniz **hata ayıklama modu** seçeneğini projenin **hata ayıklama** özellik sayfası:

    ![GDB seçenekleri](media/settings_debugger.png)

    - İçinde **gdbserver** modu, GDB çalıştırılan yerel olarak hangi uzak sistemde çalışan gdbserver bağlanır.  Bu, Linux konsol penceresi destekleyen tek mod olduğuna dikkat edin.

    - İçinde **gdb** modu, Visual Studio hata ayıklayıcısı sürücüleri GDB GDB yerel sürümünü hedef bilgisayarda yüklü sürümü ile uyumlu değilse daha uyumlu uzak sistem üzerindeki. |

    > [!NOTE] 
    > Kesme noktaları gdbserver hata ayıklama modunda isabet gdb modu deneyin. GDB ilk olmalıdır [yüklü](../linux/download-install-and-setup-the-linux-development-workload.md) uzak hedefte.

2. Standart kullanarak uzak hedefe seçin **hata ayıklama** Visual Studio içinde araç.

    Uzak hedefe kullanılabilir olduğunda, ad veya IP adresine göre listelenen görürsünüz.

    ![Uzak hedef](media/remote_target.png)

    Uzak hedefe henüz bağlanmadıysanız kullanmak için bir yönerge görürsünüz [Linux Bağlantı Yöneticisi](../linux/connect-to-your-remote-linux-computer.md) uzak hedef bağlanmak için.

    ![Uzaktan mimarisi](media/architecture.png)

3. Bazı kod sol cilt tıklatarak bir kesme noktası bilmeniz kümesi çalıştırır.

    Kırmızı noktaya kesme ayarladığınız kod satırında görünür.

4. Tuşuna **F5** (veya **hata ayıklama > hata ayıklamayı Başlat**) hata ayıklama başlatılamıyor.

    Hata ayıklama başlattığınızda, uygulama başlatılmadan önce uzak hedefe derlenir. Derleme hataları görünür **hata listesi** penceresi.

    Herhangi bir hata varsa, uygulamayı başlatın ve hata ayıklayıcı kesme noktasında duraklatılır.

    ![Bir kesme noktası isabet](media/hit_breakpoint.png)  

    Şimdi, uygulama ile etkileşim kurabilir, geçerli durumu, görünüm değişkenleri ve kod aracılığıyla adım gibi komut tuşlarına basarak kullanımda **F10** veya **F11**.

4. Linux konsolu ile uygulamanızı, select etkileşim kurmak için kullanmak istiyorsanız, **hata ayıklama > Linux Konsolu**.

  ![Linux Konsolu menüsü](media/consolemenu.png)

  Bu konsolu tüm konsol çıktısı hedef bilgisayardan görüntüler yanı sıra giriş gerçekleştirin ve hedef bilgisayara gönderin.

  ![Linux konsol penceresi](media/consolewindow.png)

## <a name="configure-other-debugging-options"></a>Diğer hata ayıklama seçeneklerini yapılandırma

* Komut satırı bağımsız değişkenleri yürütülebilir kullanarak geçirilebilir **Program değişkenleri** öğesi projenin **hata ayıklama** özellik sayfası.
  
  ![Program değişkenleri](media/settings_programarguments.png)

* Belirli hata ayıklayıcısı seçeneklerini GDB için geçirilebilir kullanarak **ek hata ayıklayıcı komutlarını** girişi.  Örneğin, SIGILL (geçersiz yönerge) sinyalleri yoksay isteyebilirsiniz.  Kullanabileceğinizi **ele** Bunu başarmak için komutu.  Aşağıdakileri ekleyerek **ek hata ayıklayıcı komutlarını** yukarıda gösterildiği gibi girişi:

  ```handle SIGILL nostop noprint```

## <a name="next-steps"></a>Sonraki adımlar

* Bu blog gönderisi Linux ARM aygıtlarda hata ayıklamak için bkz: [katıştırılmış bir ARM aygıt Visual Studio'da hata ayıklama](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/debugging-an-embedded-arm-device-in-visual-studio/).

* İle hata ayıklama için **ekleme işlemi için** komutu, bu blog gönderisi bkz: [proje sistemi, Linux konsol penceresi, rsync ve işleme Ekle Linux C++ iş yükü geliştirmeleri](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/).

## <a name="see-also"></a>Ayrıca bkz.
[C++ hata ayıklama özellikleri (Linux C++)](../linux/prop-pages/debugging-linux.md).
