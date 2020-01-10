---
title: Visual Studio’da platformlar arası C++ projeleri oluşturma
description: Hem Linux hem de Windows 'u hedefleyen Visual Studio 'da C++ açık kaynaklı bir CMake projesini ayarlama, derleme ve hata ayıklama.
ms.topic: tutorial
ms.date: 01/08/2020
ms.openlocfilehash: 83d71d3078e892a51aef159b225fecec2b581f20
ms.sourcegitcommit: 5f276064779d90a4cfda758f89e0c0f1e4d1a188
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75791769"
---
# <a name="tutorial-create-c-cross-platform-projects-in-visual-studio"></a>Öğretici: Visual C++ Studio 'da platformlar arası projeler oluşturma

Visual Studio C ve C++ geliştirme artık yalnızca Windows için değildir. Bu öğreticide, Windows ve Linux 'ta platformlar C++ arası geliştirme Için Visual Studio 'nun nasıl kullanılacağı gösterilmektedir. CMake tabanlıdır, bu nedenle Visual Studio projeleri oluşturmanız veya oluşturmanız gerekmez. CMakeLists. txt dosyasını içeren bir klasörü açtığınızda, Visual Studio IntelliSense ve derleme ayarlarını otomatik olarak yapılandırır. Kodunuzu Windows 'da yerel olarak düzenleyebilir, oluşturabilir ve hata ayıklamaya başlayabilirsiniz. Ardından, yapılandırmanızı Linux üzerinde aynı olacak şekilde değiştirin, hepsi Visual Studio içinden.

Bu öğreticide şunların nasıl yapıladığını öğreneceksiniz:

> [!div class="checklist"]
> * GitHub 'dan açık kaynaklı bir CMake projesini kopyalama
> * Projeyi Visual Studio 'da aç
> * Windows üzerinde yürütülebilir bir hedef oluşturma ve hata ayıklama
> * Linux makinesine bağlantı ekleme
> * Linux 'ta aynı hedefte derleme ve hata ayıklama

## <a name="prerequisites"></a>Prerequisites

* Platformlar arası C++ geliştirme Için Visual Studio 'yu ayarlama
  * İlk olarak, [Visual Studio 'yu yükledikten](https://visualstudio.microsoft.com/vs/) sonra ve **iş C++ yükleriyle Linux ile geliştirme** **ile C++ masaüstü geliştirmeyi** seçin. Bu minimum yüklemesi yalnızca 3 GB 'dir. Yükleme hızınıza bağlı olarak, yükleme 10 dakikadan uzun sürmemelidir.

* Platformlar arası C++ geliştirme Için bir Linux makinesi ayarlama
  * Visual Studio, Linux 'un belirli bir dağıtımına gerek yoktur. İşletim sistemi bir fiziksel makinede, bir VM 'de veya bulutta çalışıyor olabilir. Linux için Windows alt sistemini (WSL) de kullanabilirsiniz. Ancak, bu öğreticide grafik ortamı gereklidir. Birincil olarak komut satırı işlemleri için tasarlanan için WSL burada önerilmez.
  * Visual Studio, Linux makinesinde bu araçları gerektirir: C++ derleyiciler, gdb, SSH, rsync ve zip. BT tabanlı sistemlerde bu bağımlılıkları yüklemek için şu komutu kullanabilirsiniz:

    ```cmd
    sudo apt install -y openssh-server build-essential gdb rsync zip
    ```

  * Visual Studio, Linux makinesinde sunucu modunun etkinleştirildiği yeni bir CMake sürümü gerektirir (en az 3,8). Microsoft, herhangi bir Linux 'ta yükleyebileceğiniz bir evrensel CMake derlemesi oluşturur. En son özelliklere sahip olduğunuzdan emin olmak için bu derlemeyi kullanmanızı öneririz. GitHub 'daki [CMake deposunun Microsoft çatalından](https://github.com/Microsoft/CMake/releases) CMake ikili dosyalarını alabilirsiniz. Bu sayfaya gidin ve Linux makinenizde sistem mimarisine uyan sürümü indirin, sonra yürütülebilir olarak işaretleyin:

    ```cmd
    wget <path to binary>
    chmod +x cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh
    ```

  * Betiği `-–help`ile çalıştırmaya yönelik seçenekleri görebilirsiniz. **/Usr/bin** , Visual Studio 'Nun CMake 'e baktığı varsayılan konum olduğundan, **/usr** yolunda yüklemeyi belirtmek için `–prefix` seçeneğini kullanmanızı öneririz. Aşağıdaki örnekte, Linux-x86_64 betiği gösterilmektedir. Farklı bir hedef platform kullanıyorsanız bunu gerektiği gibi değiştirin.

    ```cmd
    sudo ./cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh --skip-license --prefix=/usr
    ```

* Windows makinenizde yüklü olan Windows için git.
* GitHub hesabı.

## <a name="clone-an-open-source-cmake-project-from-github"></a>GitHub 'dan açık kaynaklı bir CMake projesini kopyalama

Bu öğreticide, GitHub üzerinde fizik SDK madde Işareti kullanılmaktadır. Birçok uygulama için çakışma algılama ve fizik benzetimleri sağlar. SDK, ek kod yazmak zorunda kalmadan derlemek ve çalıştırmak için örnek yürütülebilir programlar içerir. Bu öğretici, kaynak kodların veya derleme betiklerinin hiçbirini değiştirmez. Başlamak için, Visual Studio 'Nun yüklü olduğu makinede *bullet3* deposunu GitHub 'dan klonlayın.

```cmd
git clone https://github.com/bulletphysics/bullet3.git
```

1. Visual Studio ana menüsünde **dosya > > CMake aç**' ı seçin. Az önce indirdiğiniz bullet3 deposunun kökündeki CMakeLists. txt dosyasına gidin.

    ![Dosya > açık > CMake için Visual Studio menüsü](media/cmake-open-cmake.png)

    Klasörü açtığınızda, klasör yapınız **Çözüm Gezgini**görünür hale gelir.

    ![Visual Studio Çözüm Gezgini klasör görünümü](media/cmake-bullet3-solution-explorer.png)

    Bu görünüm, mantıksal veya filtrelenmiş bir görünüm değil diskte tam olarak neler olduğunu gösterir. Varsayılan olarak, gizli dosyaları göstermez.

1. Klasördeki tüm dosyaları görmek için **tüm dosyaları göster** düğmesini seçin.

    ![Visual Studio Çözüm Gezgini tüm dosyaları göster düğmesi](media/cmake-bullet3-show-all-files.png)

## <a name="switch-to-targets-view"></a>Hedefler görünümüne geç

CMake kullanan bir klasörü açtığınızda, Visual Studio otomatik olarak CMake önbelleğini oluşturur. Bu işlem, projenizin boyutuna bağlı olarak birkaç dakika sürebilir.

1. **Çıkış penceresi**, **çıktıyı göster** ' i seçin ve ardından önbellek oluşturma Işleminin durumunu izlemek için **CMake** ' i seçin. İşlem tamamlandığında, "hedef bilgileri ayıklama tamamlandı" ifadesini belirtir.

   ![CMake çıkışının gösterildiği Visual Studio çıkış penceresi](media/cmake-bullet3-output-window.png)

   Bu işlem tamamlandıktan sonra, IntelliSense yapılandırılır. Projeyi oluşturabilir ve uygulamada hata ayıklayabilirsiniz. Visual Studio artık, CMakeLists dosyalarında belirtilen hedeflere bağlı olarak çözümün mantıksal bir görünümünü gösterir.

1. CMake hedefleri görünümüne geçmek için **Çözüm Gezgini** **çözüm ve klasörler** düğmesini kullanın.

   ![CMake hedeflerini göstermek için Çözüm Gezgini çözüm ve klasörler düğmesi](media/cmake-bullet3-show-targets.png)

   Bu görünüm, madde Işareti SDK 'Sı için şöyle görünür:

   ![CMake hedeflerini Çözüm Gezgini görünümü](media/cmake-bullet3-targets-view.png)

   Hedefler görünümü bu kaynak tabanında nelerin daha sezgisel bir görünümünü sağlar. Bazı hedeflerin kitaplıkların olduğunu ve başkalarının yürütülebilir olduğunu görebilirsiniz.

1. Bu dosyaların diskte bulunduğu her yerde kaynak kodu dosyalarını görmek için CMake hedefleri görünümündeki bir düğümü genişletin.

## <a name="add-an-explicit-windows-x64-debug-configuration"></a>Açık bir Windows x64-hata ayıklama yapılandırması ekleme

Visual Studio, Windows için varsayılan bir **x64-hata ayıklama** yapılandırması oluşturur. Yapılandırma, Visual Studio 'nun CMake için hangi platform hedefini kullandığını öğrendiği bir şeydir. Varsayılan yapılandırma diskte temsil değildir. Açıkça bir yapılandırma eklediğinizde, Visual Studio *Cmakesettings. JSON*adlı bir dosya oluşturur. Belirttiğiniz tüm yapılandırmaların ayarlarıyla doldurulur.

1. Yeni bir yapılandırma ekleyin. Araç çubuğunda **yapılandırma** açılan kutusu ' nu açın ve **yapılandırmaları Yönet**' i seçin.

   ![Yapılandırma açılan eklentisini yönetme](media/cmake-bullet3-manage-configurations.png)

   [CMake ayarları Düzenleyicisi](customize-cmake-settings.md) açılır. Yeni bir yapılandırma eklemek için düzenleyicinin sol tarafındaki yeşil artı işaretini seçin. **CMakeSettings 'e yapılandırma Ekle** iletişim kutusu görünür.

   ![CMakeSettings iletişim kutusuna yapılandırma Ekle](media/cmake-bullet3-add-configuration-x64-debug.png)

   Bu iletişim kutusunda, Visual Studio 'Ya dahil edilen tüm yapılandırmaların yanı sıra, oluşturduğunuz tüm özel konfigürasyonlar gösterilir. **X64-hata ayıklama** yapılandırmasını kullanmaya devam etmek istiyorsanız, bu, ilk eklediğiniz ilk olmalıdır. **X64-Debug**' ı seçin ve ardından **Seç** düğmesini seçin. Visual Studio, bir **x64-Debug**yapılandırması Ile CMakeSettings. json dosyasını oluşturur ve diske kaydeder. Ad parametresini doğrudan CMakeSettings. JSON içinde değiştirerek, yapılandırlarınız için istediğiniz adları kullanabilirsiniz.

## <a name="set-a-breakpoint-build-and-run-on-windows"></a>Windows üzerinde kesme noktası ayarlama, derleme ve çalıştırma

Bu adımda, madde Işareti fizik kitaplığını gösteren örnek bir programda hata ayıklaması yapacağız.
  
1. **Çözüm Gezgini**' de AppBasicExampleGui ' ı seçin ve genişletin.

1. `BasicExample.cpp` dosyasını açın.

1. Çalışan uygulamaya tıkladığınızda isabet alan bir kesme noktası ayarlayın. Click olayı bir yardımcı sınıf içindeki bir yöntemde işlenir. Hızlıca almak için:

   1. Yapı `BasicExample` türetildiği `CommonRigidBodyBase` seçin. 30. satırın etrafında.

   1. Sağ tıklayın ve **Tanıma Git**' i seçin. Artık CommonRigidBodyBase. h üst bilgisinde olduğunuzu görürsünüz.

   1. Kaynağınızın üzerindeki tarayıcı görünümünde, `CommonRigidBodyBase`olduğunuzu görmeniz gerekir. Sağ tarafta, incelemek üzere üyeleri seçebilirsiniz. Açılan eklentiyi açın ve `mouseButtonCallback` ' yi seçerek başlıktaki bu işlevin tanımına gidin.

      ![Visual Studio üye listesi araç çubuğu](media/cmake-bullet3-member-list-toolbar.png)

1. Bu işlevin içindeki ilk satıra bir kesme noktası koyun. Visual Studio hata ayıklayıcısı altında çalıştırıldığında, uygulamanın penceresinde bir fare düğmesine tıkladığınızda bu, isabet alır.

1. Uygulamayı başlatmak için araç çubuğunda Başlat açılan kutusu ' nu seçin. Bu, "başlangıç öğesi Seç" diyen yeşil yürütme simgesiyle aynıdır. Açılan kutuda AppBasicExampleGui. exe ' yi seçin. Yürütülebilir dosya adı Şimdi Başlat düğmesinde görüntülenir:

   ![Başlangıç öğesi seç için Visual Studio araç çubuğu başlatma açılan menüsü](media/cmake-bullet3-launch-button.png)

1. Uygulamayı ve gerekli bağımlılıkları oluşturmak için Başlat düğmesini seçin ve ardından Visual Studio hata ayıklayıcısı ekli olarak başlatın. Birkaç dakika sonra, çalışan uygulama görünür:

   ![Visual Studio bir Windows uygulamasında hata ayıklama](media/cmake-bullet3-launched.png)

1. Farenizi uygulama penceresine taşıyın ve ardından bir düğmeye tıklayarak kesme noktasını tetikleyin. Kesme noktası, Visual Studio 'Yu ön plana geri getirir ve düzenleyici yürütmenin duraklatıldığı satırı gösterir. Uygulama değişkenlerini, nesneleri, iş parçacıklarını ve belleği inceleyebilir veya kodunuzda etkileşimli olarak adım adım izleyebilirsiniz. Uygulamanın sürdürülmesine izin vermek için **devam** ' ı seçin ve ardından normal bir şekilde çıkın. Ya da Durdur düğmesini kullanarak Visual Studio içinde yürütmeyi durdurabilirsiniz.

## <a name="add-a-linux-configuration-and-connect-to-the-remote-machine"></a>Linux yapılandırması ekleme ve uzak makineye bağlanma

1. Bir Linux yapılandırması ekleyin. **Çözüm Gezgini** görünümünde CMakeSettings. JSON dosyasına sağ tıklayın ve **yapılandırma Ekle**' yi seçin. Daha önce olduğu gibi CMakeSettings iletişim kutusunda aynı yapılandırma Ekle ' ye bakabilirsiniz. Linux ' u seçin-bu kez **hata ayıklayın** , sonra CMakeSettings. json dosyasını kaydedin (Ctrl + s).

1. Yapılandırma açılır penceresinde **Linux-Debug** ' ı seçin.

   ![X64-hata ayıklama ve Linux-hata ayıklama seçenekleri ile yapılandırma açılan eklentisini başlatma](media/cmake-bullet3-linux-configuration-item.png)

   Bir Linux sistemine ilk kez bağlanıyorsanız, **uzak sistem 'e Bağlan** iletişim kutusu görüntülenir.

   ![Visual Studio uzak sisteme Bağlan iletişim kutusu](media/cmake-bullet3-connection-manager.png)

   Zaten bir uzak bağlantı eklediyseniz, **araçlar > seçenekler > platformlar arası > bağlantı Yöneticisi**' ne giderek bu pencereyi açabilirsiniz.

1. [Linux makinenize bağlantı bilgilerini](/cpp/linux/connect-to-your-remote-linux-computer) girin ve **Bağlan**' ı seçin. Visual Studio, bu makineyi **Linux-Debug**için varsayılan bağlantınız olarak CMakeSettings. JSON öğesine ekler. Ayrıca, uzak makinenize ait üst bilgileri alıp [Bu uzak bağlantıya özel IntelliSense](/cpp/linux/configure-a-linux-project?view=vs-2019#remote_intellisense)'i edinirsiniz. Ardından, Visual Studio dosyalarınızı uzak makineye gönderir ve uzak sistemde CMake önbelleğini oluşturur. Bu adımlar, ağınızın hızına ve uzak makinenizin gücüne bağlı olarak biraz zaman alabilir. CMake çıkış penceresinde "hedef bilgi ayıklama işlemi bitti" iletisi göründüğünde bunun tamamlandığını bilirsiniz.

## <a name="set-a-breakpoint-build-and-run-on-linux"></a>Linux 'ta kesme noktası ayarlama, derleme ve çalıştırma

Bir masaüstü uygulaması olduğundan, hata ayıklama yapılandırmasına bazı ek yapılandırma bilgileri sağlamanız gerekir.

1. CMake hedefleri görünümünde AppBasicExampleGui öğesine sağ tıklayın ve **Hata Ayıkla ve Başlat ayarları** ' nı seçerek Hidden **. vs** alt klasöründeki Launch. vs. json dosyasını açın. Bu dosya, geliştirme ortamınız için yereldir. İade etmek ve ekibinizle kaydetmek istiyorsanız, bunu projenizin köküne taşıyabilirsiniz. Bu dosyada AppBasicExampleGui için bir yapılandırma eklenmiştir. Bu varsayılan ayarlar çoğu durumda çalışır, ancak burada değildir. Bir masaüstü uygulaması olduğundan, Linux makinenizde görebilmeniz için programı başlatmak üzere bazı ek bilgiler sağlamanız gerekir.

1. `DISPLAY` ortam değişkeninin değerini Linux makinenizde bulmak için şu komutu çalıştırın:

   ```cmd
   echo $DISPLAY
   ```

   AppBasicExampleGui yapılandırmasında, "pipeArgs" parametre dizisi vardır. "$ {DebuggerCommand}" satırı içeriyor. Bu, uzak makinede gdb 'yi Başlatan komuttur. Bu komut çalıştırılmadan önce Visual Studio 'Nun ekranı bu içeriğe dışarı aktarmanız gerekir. Örneğin, görüntülerinizin değeri `:1`, bu satırı aşağıdaki gibi değiştirin:

   ```cmd
   "export DISPLAY=:1;${debuggerCommand}",
   ```

1. Uygulamanızı başlatın ve hata ayıklayın. Araç çubuğunda **Başlangıç öğesi Seç** açılan penceresini açın ve **Appbasicexamplegui**' ı seçin. Sonra, araç çubuğunda yeşil yürütme simgesini seçin veya **F5**tuşuna basın. Uygulama ve bağımlılıkları, uzak Linux makinesinde oluşturulmuştur ve ardından Visual Studio hata ayıklayıcısı ekli olarak başlatılır. Uzak Linux makinenizde bir uygulama penceresi göründüğünü görmeniz gerekir.

1. Farenizi uygulama penceresine taşıyın ve bir düğmeye tıklayın. Kesme noktası isabet edilir. Program yürütme duraklatılır, Visual Studio ön plana geri gelir ve kesme noktasını görürsünüz. Ayrıca, Visual Studio 'da bir Linux konsol penceresi göründüğünü görmeniz gerekir. Pencere, uzak Linux makinesinden çıkış sağlar ve ayrıca `stdin`girişi kabul edebilir. Tüm Visual Studio pencereleri gibi, onu görmeyi tercih ettiğiniz yere yerleştirebilirsiniz. Konumu gelecekteki oturumlarda kalıcı hale getirilir.

   ![Visual Studio Linux konsol penceresi](media/cmake-bullet3-linux-console.png)

1. Visual Studio kullanarak uygulama değişkenlerini, nesneleri, iş parçacıklarını, belleği ve kodunuzu etkileşimli olarak inceleyebilirsiniz. Ancak, bu kez, bunu yerel Windows ortamınız yerine bir uzak Linux makinesinde gerçekleşiyoruz. Uygulamanın çalışmaya devam etmesine izin vermek ve normal bir şekilde çıkmak için **devam** ' ı seçebilir veya yerel yürütmede olduğu gibi Durdur düğmesini de seçebilirsiniz.

1. Çağrı yığını penceresine bakın ve Visual Studio 'Nun uygulamayı Linux üzerinde başlatmasından bu yana `x11OpenGLWindow` çağrıları görüntüleyin.

   ![Linux çağrı yığınını gösteren çağrı yığını penceresi](media/cmake-bullet3-linux-callstack.png)

## <a name="what-you-learned"></a>Öğrendikleriniz

Bu öğreticide, doğrudan GitHub 'dan bir kod tabanı Klonladığınız. Windows üzerinde değişiklik yapmadan oluşturduğunuz, çalıştırdınız ve hata ayıklaması gerçekleştirdik. Ardından, uzak bir Linux makinesinde derlemek, çalıştırmak ve hata ayıklamak için, küçük yapılandırma değişiklikleriyle aynı kod tabanını kullandınız.

## <a name="next-steps"></a>Sonraki adımlar

Visual Studio 'da CMake projelerini yapılandırma ve hata ayıklama hakkında daha fazla bilgi edinin:

> [!div class="nextstepaction"]
> [Visual Studio 'da CMake projeleri](cmake-projects-in-visual-studio.md)<br/><br/>
> [Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)<br/><br/>
> [Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)<br/><br/>
> [CMake derleme ayarlarını özelleştirme](customize-cmake-settings.md)<br/><br/>
> [CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)<br/><br/>
> [Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](../linux/deploy-run-and-debug-your-linux-project.md)<br/><br/>
> [CMake önceden tanımlanmış yapılandırma başvurusu](cmake-predefined-configuration-reference.md)
>
