---
title: Dağıtma, çalıştırma ve C++ Linux projenizi Visual Studio'da hata ayıklama
description: Derleme, yürütün ve hata ayıklama kodu Visual Studio'da Linux C++ projesi içinde uzak hedefte açıklar.
ms.date: 09/12/2018
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
ms.openlocfilehash: cdafb064f8a6269c5ccae938e280b5f47bff3b00
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393391"
---
# <a name="deploy-run-and-debug-your-linux-project"></a>Dağıtma, çalıştırma ve Linux projenizin hatalarını ayıklama

Visual Studio'da Linux C++ projesi oluşturduktan sonra proje kullanarak bağlantı kurduğunuz [Linux Bağlantı Yöneticisi](connect-to-your-remote-linux-computer.md), çalıştırın ve proje hata ayıklama. Derleme, yürütün ve uzak hedef kodunda hata ayıklayın.

Linux projenizin hatalarını ayıklama ve etkileşim için birkaç yol vardır.

- Kesme noktaları, Gözcü pencerelerini ve bir değişkenin geldiğinizde gibi geleneksel Visual Studio özellikleri kullanarak hata ayıklama. Diğer proje türleri için normalde yaptığınız gibi bu yöntemleri kullanarak hata ayıklama.

- Özel bir Linux konsol penceresinde hedef bilgisayardan çıktısını görüntüleyin. Konsolu, hedef bilgisayara giriş göndermek için de kullanabilirsiniz.

## <a name="debug-your-linux-project"></a>Linux projenizin hatalarını ayıklama

1. Select hata ayıklama modunda **hata ayıklama** özellik sayfası.

   GDB, Linux üzerinde çalışan uygulamalarda hata ayıklama için kullanılır. GDB öğesinden seçilebilir iki farklı modda çalışabilir **mod hata ayıklaması** seçeneği projenin **hata ayıklama** özellik sayfası:

   ![GDB seçenekleri](media/settings_debugger.png)

   - İçinde **gdbserver** modunda, GDB çalıştırın yerel olarak uzak sistemdeki gdbserver bağlanır.  Bu Linux konsol penceresinde destekleyen tek mod olduğunu unutmayın.

   - İçinde **gdb** modu, Visual Studio hata ayıklayıcı, uzak sistemde GDB sürücüler. Bu, GDB yerel sürümünü hedef bilgisayarda yüklü sürümüyle uyumlu değilse, daha iyi bir seçenektir. |

   > [!NOTE]
   > İsabet kesme noktaları hata ayıklama gdbserver modunda, gdb modunda deneyin. GDB ilk olmalıdır [yüklü](download-install-and-setup-the-linux-development-workload.md) uzak hedef.

1. Standart kullanarak uzak hedef seçin **hata ayıklama** Visual Studio'da araç çubuğu.

   Uzak hedef kullanılabilir olduğunda, ad veya IP adresine göre listelenen görürsünüz.

   ![Uzak hedef](media/remote_target.png)

   Uzak hedef henüz bağlanmadıysanız, kullanılacak bir yönerge göreceğiniz [Linux Bağlantı Yöneticisi](connect-to-your-remote-linux-computer.md) uzak hedef bağlanmak için.

   ![Uzak mimarisi](media/architecture.png)

1. Bazı kod sol kanalda tıklatarak bir kesme noktası bilmeniz kümesi çalıştırır.

   Kırmızı nokta kod satırında Kesme noktasının ayarlandığı görünür.

1. Tuşuna **F5** (veya **hata ayıklama > hata ayıklamayı Başlat**) hata ayıklama başlatılamıyor.

   Hata ayıklaması başlattığınızda, uygulama başlamadan önce uzak hedef üzerinde derlenir. Derleme hataları görünür **hata listesi** penceresi.

   Herhangi bir hata varsa, uygulama başlatılır ve hata ayıklayıcı kesme noktasında duraklatılır.

   ![Bir kesme noktası isabet](media/hit_breakpoint.png)

   Artık, uygulamanın kendi geçerli durumunda, değişkenleri görüntüle ve kodu adımlayın gibi komut tuşlarına basarak etkileşim kurabileceğiniz **F10** veya **F11**.

1. Uygulamanızı, select etkileşim kurmak için Linux konsolu kullanmak istiyorsanız **hata ayıklama > Linux Konsolu**.

   ![Linux konsolu menü](media/consolemenu.png)

   Bu konsol hedef bilgisayarı tüm konsol çıktısı görüntüler yanı sıra gelenlerin ve hedef bilgisayara gönderin.

   ![Linux konsol penceresi](media/consolewindow.png)

## <a name="configure-other-debugging-options"></a>Diğer hata ayıklama seçeneklerini yapılandırma

- Komut satırı bağımsız değişkenleri yürütülebilir kullanarak geçirilebilir **Program bağımsız değişkenleri** projenin öğesi **hata ayıklama** özellik sayfası.

   ![Program bağımsız değişkenleri](media/settings_programarguments.png)

- Belirli hata ayıklayıcısı seçenekleri geçirilebilir için GDB kullanarak **ek hata ayıklayıcı komutları** girişi.  Örneğin, SIGILL (geçersiz yönerge) sinyalleri yoksaymak isteyebilirsiniz.  Kullanabileceğinizi **işlemek** Bunu başarmak için komutu.  Aşağıdaki ekleyerek **ek hata ayıklayıcı komutları** yukarıda da gösterildiği gibi giriş:

   `handle SIGILL nostop noprint`

## <a name="next-steps"></a>Sonraki adımlar

- ARM cihazları, Linux üzerinde hata ayıklamak için bu blog gönderisini inceleyin: [Katıştırılmış bir ARM cihazı Visual Studio'da hata ayıklama](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/debugging-an-embedded-arm-device-in-visual-studio/).

- Kullanarak hata ayıklama **iliştirme** komutu, bu blog gönderisini inceleyin: [Linux C++ proje sistemi, Linux konsol penceresi, rsync ve işleme İliştir iş yükünde geliştirmeler](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/).

## <a name="see-also"></a>Ayrıca bkz.

[C++ hata ayıklama özellikleri (Linux C++)](prop-pages/debugging-linux.md)
