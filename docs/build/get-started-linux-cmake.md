---
title: Visual Studio’da platformlar arası C++ projeleri oluşturma
description: Visual Studio'da hem Linux hem de Windows'u hedefleyen bir C++ açık kaynak CMake projesinin nasıl kurulması, derlemesi ve hata ayıklamasıdır.
ms.topic: tutorial
ms.date: 01/08/2020
ms.openlocfilehash: aac536f488cf22adf5aa835c9fe5b884fc5d7298
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328753"
---
# <a name="tutorial-create-c-cross-platform-projects-in-visual-studio"></a>Öğretici: Visual Studio'da C++ platform ötesi projeler oluşturun

Visual Studio C ve C++ geliştirmeartık sadece Windows için değil. Bu öğretici, Windows ve Linux'ta C++ çapraz platform geliştirme için Visual Studio'nun nasıl kullanılacağını gösterir. CMake'e dayalıdır, böylece Visual Studio projeleri oluşturmak veya oluşturmak zorunda kalmamanız gerekir. CMakeLists.txt dosyası içeren bir klasörü açtığınızda, Visual Studio IntelliSense'i yapılandırır ve ayarları otomatik olarak oluşturur. Windows'da kodunuzu yerel olarak düzenlemeye, oluşturmaya ve hata ayıklamaya hızla başlayabilirsiniz. Ardından, visual studio içinden linux'ta da aynı şeyi yapmak için yapılandırmanızı değiştirin.

Bu öğreticide şunların nasıl yapıldığını öğrenirsiniz:

> [!div class="checklist"]
>
> * GitHub'dan bir açık kaynak CMake projesi klonlamak
> * Visual Studio'da projeyi açın
> * Windows'da yürütülebilir bir hedef oluşturma ve hata ayıklama
> * Linux makinesine bağlantı ekleme
> * Linux'ta aynı hedefi oluşturma ve hata ayıklama

## <a name="prerequisites"></a>Ön koşullar

* Cross Platform C++ Geliştirme için Visual Studio'u kur
  * İlk olarak [Visual Studio'yu yükleyin](https://visualstudio.microsoft.com/vs/) ve **C++ iş yükleriyle**C++ ve Linux geliştirme ile **Masaüstü geliştirmeyi** seçin. Bu minimum yükleme sadece 3 GB'dır. İndirme hızınıza bağlı olarak yükleme 10 dakikadan fazla sürmemelidir.

* Çapraz Platform C++ Geliştirme için bir Linux makinesi ayarlama
  * Visual Studio Linux'un belirli bir dağıtımını gerektirmez. İşletim sistemi fiziksel bir makinede, VM'de veya bulutta çalışıyor olabilir. Linux için Windows Alt Sistemi'ni (WSL) de kullanabilirsiniz. Ancak, bu öğretici için bir grafik ortamı gereklidir. WSL burada önerilmez, çünkü öncelikle komut satırı işlemleri için tasarlanmıştır.
  * Visual Studio Linux makinesinde bu araçları gerektirir: C++ derleyicileri, gdb, ssh, rsync, ninja ve zip. Debian tabanlı sistemlerde, bu bağımlılıkları yüklemek için bu komutu kullanabilirsiniz:

    ```cmd
    sudo apt install -y openssh-server build-essential gdb rsync ninja-build zip
    ```

  * Visual Studio sunucu modu etkin (en az 3.8) olan Linux makinecmake yeni bir sürümünü gerektirir. Microsoft, herhangi bir Linux dağıtım ına yükleyebileceğiniz evrensel bir CMake yapısı üretir. En son özelliklere sahip olduğundan emin olmak için bu yapıyı kullanmanızı öneririz. CMake ikililerini GitHub'daki [CMake repo'nun Microsoft çatalından](https://github.com/Microsoft/CMake/releases) alabilirsiniz. Bu sayfaya gidin ve Linux makinenizde sistem mimarisiyle eşleşen sürümü indirin, ardından çalıştırılabilir olarak işaretleyin:

    ```cmd
    wget <path to binary>
    chmod +x cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh
    ```

  * Komut dosyasını `-–help`'ile çalıştırmak için seçenekleri görebilirsiniz. **/usr/bin** `–prefix` Visual Studio'nun CMake'i aradığı varsayılan konum olduğundan, **/usr** yolunda yüklemeyi belirtme seçeneğini kullanmanızı öneririz. Aşağıdaki örnek, Linux x86_64 komut dosyasını gösterir. Farklı bir hedef platform kullanıyorsanız gerektiği gibi değiştirin.

    ```cmd
    sudo ./cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh --skip-license --prefix=/usr
    ```

* Windows makinenizde yüklü pencereler için Git.
* GitHub hesabı.

## <a name="clone-an-open-source-cmake-project-from-github"></a>GitHub'dan açık kaynak kodlu bir CMake projesini klonla

Bu öğretici GitHub'daki Bullet Physics SDK'yı kullanır. Birçok uygulama için çarpışma algılama ve fizik simülasyonları sağlar. SDK, ek kod yazmak zorunda kalmadan derleyen ve çalıştırılabilen örnek yürütülebilir programlar içerir. Bu öğretici, kaynak kodun hiçbirini değiştirmez veya komut dosyaları oluşturmaz. Başlamak için, Visual Studio'nun yüklü olduğu makinede GitHub'daki *bullet3* deposunu kopyalayın.

```cmd
git clone https://github.com/bulletphysics/bullet3.git
```

1. Visual Studio ana menüsünde, **Dosya > Açık > CMake'i**seçin. Az önce indirdiğiniz bullet3 repo'nun kökündeki CMakeLists.txt dosyasına gidin.

    ![Dosya > Açık > CMake için Visual Studio menüsü](media/cmake-open-cmake.png)

    Klasörü açar açmaz klasör ünüz Çözüm **Gezgini'nde**görünür hale gelir.

    ![Visual Studio Solution Explorer Klasör Görünümü](media/cmake-bullet3-solution-explorer.png)

    Bu görünüm, mantıksal veya filtreuygulanmış bir görünüm değil, diskte tam olarak ne olduğunu gösterir. Varsayılan olarak, gizli dosyaları göstermez.

1. Klasördeki tüm dosyaları görmek için **tüm dosyaları göster** düğmesini seçin.

    ![Visual Studio Solution Explorer Tüm Dosyaları Göster düğmesi](media/cmake-bullet3-show-all-files.png)

## <a name="switch-to-targets-view"></a>Hedefler görünümüne geçiş

CMake kullanan bir klasörü açtığınızda, Visual Studio otomatik olarak CMake önbelleğini oluşturur. Bu işlem, projenizin boyutuna bağlı olarak birkaç dakika sürebilir.

1. Çıktı **Penceresinde,** önbellek oluşturma işleminin durumunu izlemek için **çıktıyı göster'i** seçin ve ardından **CMake'i** seçin. İşlem tamamlandığında, "Hedef bilgi ayıklama yapılır" diyor.

   ![CMake'den çıktı gösteren Visual Studio Output penceresi](media/cmake-bullet3-output-window.png)

   Bu işlem tamamlandıktan sonra IntelliSense yapılandırılır. Projeyi oluşturabilir ve uygulamayı hata ayıklayabilirsiniz. Visual Studio artık CMakeLists dosyalarında belirtilen hedeflere dayalı olarak çözümün mantıksal bir görünümünü gösterir.

1. CMake Targets View'a geçmek için **Çözüm Gezgini'ndeki** **Çözümler ve Klasörler** düğmesini kullanın.

   ![CMake hedefleri görünümünü göstermek için Çözüm Gezgini'ndeki Çözümler ve Klasörler düğmesi](media/cmake-bullet3-show-targets.png)

   Bullet SDK için bu görünüm şu şekilde görünür:

   ![Çözüm Explorer CMake hedefleri görünümü](media/cmake-bullet3-targets-view.png)

   Hedef görünümü, bu kaynak tabanında ne olduğunu daha sezgisel bir görünüm sağlar. Bazı hedeflerin kitaplıklar, bazılarının ise yürütülebilir olduğunu görebilirsiniz.

1. Kaynak kod dosyalarını görmek için CMake Targets View'daki bir düğümü genişletin, bu dosyalar diskte nerede bulunabilirse.

## <a name="add-an-explicit-windows-x64-debug-configuration"></a>Açık bir Windows x64-Hata Ayıklama yapılandırması ekleme

Visual Studio, Windows için varsayılan **bir x64-Hata Ayıklama** yapılandırması oluşturur. Yapılandırmalar Visual Studio'nun CMake için hangi platform hedefini kullanacağını nasıl anladığıdır. Varsayılan yapılandırma diskte temsil edilmiyor. Açıkça bir yapılandırma eklediğinizde, Visual Studio *CMakeSettings.json*adlı bir dosya oluşturur. Belirttiğiniz tüm yapılandırmaların ayarlarıyla doldurulur.

1. Yeni bir yapılandırma ekleyin. Araç çubuğunda **Yapılandırma** açılır dosyasını açın ve **Yapılandırmaları Yönet'i**seçin.

   ![Yapılandırma açılır düşüşünü yönetme](media/cmake-bullet3-manage-configurations.png)

   [CMake Ayarları Düzenleyicisi](customize-cmake-settings.md) açılır. Yeni bir yapılandırma eklemek için editörün sol tarafındaki yeşil artı işaretini seçin. **CMakeSettings'e Yapılandırma Ekle** iletişim kutusu görüntülenir.

   ![CMakeSettings iletişim kutusuna Yapılandırma ekleme](media/cmake-bullet3-add-configuration-x64-debug.png)

   Bu iletişim kutusu, Visual Studio ile birlikte verilen tüm yapılandırmaları ve oluşturduğunuz özel yapılandırmaları gösterir. **X64-Hata Ayıklama** yapılandırmasını kullanmaya devam etmek istiyorsanız, ilk eklediğiniz yapılandırma olmalıdır. **x64-Hata Ayıklama'yı**seçin ve ardından **Seç** düğmesini seçin. Visual Studio **x64-Debug**için bir yapılandırma ile CMakeSettings.json dosyasını oluşturur ve diske kaydeder. Ad parametresini doğrudan CMakeSettings.json'da değiştirerek yapılandırmalarınız için istediğiniz adları kullanabilirsiniz.

## <a name="set-a-breakpoint-build-and-run-on-windows"></a>Windows'da bir kesme noktası ayarlama, oluşturma ve çalıştırma

Bu adımda, Bullet Physics kitaplığını gösteren örnek bir programı hata ayıklayacağız.
  
1. **Solution Explorer'da**AppBasicExampleGui'yi seçin ve genişletin.

1. `BasicExample.cpp` dosyasını açın.

1. Çalışan uygulamayı tıklattığınızda vurulan bir kesme noktası ayarlayın. Tıklama olayı, yardımcı sınıf içindeki bir yöntemle işlenir. Hızlı bir şekilde oraya ulaşmak için:

   1. Yapının `CommonRigidBodyBase` türetilmiş `BasicExample` olduğunu seçin. 30. hatta.

   1. Sağ tıklatın ve **Tanıma Git'i**seçin. Şimdi başlık CommonRigidBodyBase.h konum.

   1. Kaynağınızın üzerindeki tarayıcı görünümünde, `CommonRigidBodyBase`'de olduğunuzu görmeniz gerekir. Sağda, incelemek için üyeleri seçebilirsiniz. Açılır açılır dosyayı `mouseButtonCallback` açın ve üstbilgideki bu işlevin tanımına gitmeyi seçin.

      ![Visual Studio üye listesi araç çubuğu](media/cmake-bullet3-member-list-toolbar.png)

1. Bu işlev in ilk satırına bir kesme noktası yerleştirin. Uygulama penceresindeki fare düğmesini tıklattığınızda, Visual Studio hata ayıklama nın altında çalıştırıldığında vurulur.

1. Uygulamayı başlatmak için araç çubuğundaki başlatma açılır masını seçin. "Başlangıç Öğesini Seç" yazan yeşil oyun simgesine sahip olan dır. Açılan açılır durumda AppBasicExampleGui.exe'yi seçin. Çalıştırılabilir ad artık başlat düğmesinde görüntülenir:

   ![Select Başlangıç Öğesi için Visual Studio araç çubuğu başlatma açılır](media/cmake-bullet3-launch-button.png)

1. Uygulamayı ve gerekli bağımlılıkları oluşturmak için başlatma düğmesini seçin ve ardından Visual Studio hata ayıklama ekli olarak başlatın. Birkaç dakika sonra çalışan uygulama görüntülenir:

   ![Visual Studio bir Windows uygulamasını hata ayıklama](media/cmake-bullet3-launched.png)

1. Farenizi uygulama penceresine taşıyın ve kesme noktasını tetiklemek için bir düğmeye tıklayın. Kesme noktası Visual Studio'yu tekrar ön plana çıkarır ve düzenleyici yürütmenin duraklatılmış olduğu satırı gösterir. Uygulama değişkenlerini, nesneleri, iş parçacıklarını ve belleği inceleyebilir veya kodunuzda etkileşimli olarak adım atabilirsiniz. Uygulamanın devam etmesine izin vermek için **Devam** et'i seçin ve ardından normal şekilde çıkın. Veya durdurma düğmesini kullanarak Visual Studio'daki yürütmeyi durdurun.

## <a name="add-a-linux-configuration-and-connect-to-the-remote-machine"></a>Linux yapılandırması ekleyin ve uzak makineye bağlanın

1. Bir Linux yapılandırması ekleyin. **Solution Explorer** görünümünde CMakeSettings.json dosyasına sağ tıklayın ve **Yapılandırma Ekle'yi**seçin. CMakeSettings iletişim kutusunda daha önce olduğu gibi yapılandırma ekle iletişim kutusunu da görürsünüz. Bu sefer **Linux Hata Ayıklama'yı** seçin ve CMakeSettings.json dosyasını (ctrl + s) kaydedin.

1. Yapılandırma açılır durumda **Linux-Hata** Ayıklama'yı seçin.

   ![X64-Hata Ayıklama ve Linux Hata Ayıklama seçenekleriyle yapılandırma açılır başlatma](media/cmake-bullet3-linux-configuration-item.png)

   Bir Linux sistemine ilk kez bağlanDığınızda, **Uzak Sisteme Bağlan** iletişim kutusu görüntülenir.

   ![Visual Studio Uzak Sisteme Bağlan iletişim kutusu](media/cmake-bullet3-connection-manager.png)

   Zaten uzak bir bağlantı eklediyseniz, **Araçlar > Seçenekleri > Çapraz Platform > Bağlantı Yöneticisi'ne**yön vererek bu pencereyi açabilirsiniz.

1. Linux [makinenize bağlantı bilgilerini](/cpp/linux/connect-to-your-remote-linux-computer) sağlayın ve **Bağlan'ı**seçin. Visual Studio **Linux-Debug**için varsayılan bağlantı olarak CMakeSettings.json olarak bu makine ekler. Ayrıca uzak makineden başlıkları aşağı çeker, böylece [IntelliSense bu uzak bağlantı ya](/cpp/linux/configure-a-linux-project?view=vs-2019#remote_intellisense)da özel olsun. Ardından, Visual Studio dosyalarınızı uzak makineye gönderir ve uzak sistemdeki CMake önbelleğini oluşturur. Bu adımlar, ağınızın hızına ve uzak makinenizin gücüne bağlı olarak biraz zaman alabilir. CMake çıkış penceresinde "Hedef bilgi ayıklama tamamlandı" iletisi göründüğünde bunun tamam olduğunu anlarsınız.

## <a name="set-a-breakpoint-build-and-run-on-linux"></a>Bir kesme noktası ayarlayın, Linux'ta oluşturun ve çalıştırın

Masaüstü uygulaması olduğundan, hata ayıklama yapılandırmasına bazı ek yapılandırma bilgileri sağlamanız gerekir.

1. CMake Targets görünümünde, AppBasicExampleGui'yi sağ tıklatın ve gizli **.vs** alt klasöründe bulunan launch.vs.json dosyasını açmak için **Hata Ayıklama ve Başlatma Ayarlarını** seçin. Bu dosya geliştirme ortamınız için yereldir. Check-in yapmak ve ekibinizle birlikte kaydetmek isterseniz projenizin köküne taşıyabilirsiniz. Bu dosyada, AppBasicExampleGui için bir yapılandırma eklendi. Bu varsayılan ayarlar çoğu durumda çalışır, ancak burada çalışmaz. Bu bir masaüstü uygulaması olduğundan, programı Linux makinenizde görebilmeniz için programı başlatmak için bazı ek bilgiler sağlamanız gerekir.

1. Linux makinenizde ortam değişkeninin `DISPLAY` değerini bulmak için şu komutu çalıştırın:

   ```cmd
   echo $DISPLAY
   ```

   AppBasicExampleGui için yapılandırmada, bir parametre dizisi var, "pipeArgs". Bir satır içerir: "${debuggerCommand}". Uzak makinede GDB'yi fırlatan komut. Visual Studio, bu komut çalıştırmadan önce ekranı bu bağlama aktarmalıdır. Örneğin, görüntünuzun değeri `:1`aşağıdaki gibi bu satırı değiştirin:

   ```cmd
   "export DISPLAY=:1;${debuggerCommand}",
   ```

1. Uygulamanızı başlatın ve hata ayıkla. Araç çubuğunda **Başlangıç Öğesini Seç** açılır'ı açın ve **AppBasicExampleGui'yi**seçin. Ardından, araç çubuğundaki yeşil oynatma simgesini seçin veya **F5 tuşuna**basın. Uygulama ve bağımlılıkları uzak Linux makinesi üzerine inşa edilmiştir, daha sonra Visual Studio hata ayıklama bağlı ile başlatılan. Uzak Linux makinenizde bir uygulama penceresinin göründüğünü görmeniz gerekir.

1. Farenizi uygulama penceresine taşıyın ve bir düğmeye tıklayın. Kırılma noktası vuruldu. Program yürütme duraklar, Visual Studio ön plana geri geliyor, ve sizin kırılma noktası bakın. Visual Studio'da bir Linux Konsol Penceresi de görünmelisiniz. Pencere, uzak Linux makinesinden çıktı sağlar ve aynı `stdin`zamanda . Herhangi bir Visual Studio penceresi gibi, görmek istediğiniz yere sabitleyebilirsiniz. Konumu gelecek oturumlarda devam etmektedir.

   ![Visual Studio Linux Konsol Penceresi](media/cmake-bullet3-linux-console.png)

1. Visual Studio'yu kullanarak uygulama değişkenlerini, nesneleri, iş parçacıklarını, belleği inceleyebilir ve kodunuzda etkileşimli olarak adım atabilirsiniz. Ancak bu sefer, tüm bunları yerel Windows ortamınız yerine uzak bir Linux makinesinde yapıyorsunuz. Uygulamanın devam **etmesine** ve normal şekilde çıkmasına izin ver'i seçebilir veya yerel yürütmede olduğu gibi durdurma düğmesini seçebilirsiniz.

1. Çağrı Yığını penceresine bakın ve `x11OpenGLWindow` Visual Studio'nun uygulamayı Linux'ta başlatmasından bu yana Aramaları görüntüleyin.

   ![Linux çağrı yığınını gösteren Yığın arama penceresi](media/cmake-bullet3-linux-callstack.png)

## <a name="what-you-learned"></a>Öğrendikleriniz

Bu eğitimde, doğrudan GitHub'dan bir kod tabanı klonladınız. Windows'da değişiklik yapmadan inşa ettiniz, çalıştırdın ve debugged. Daha sonra, uzak bir Linux makinesinde oluşturmak, çalıştırmak ve hata ayıklamak için küçük yapılandırma değişiklikleriyle aynı kod tabanını kullandınız.

## <a name="next-steps"></a>Sonraki adımlar

Visual Studio'da CMake projelerini yapılandırma ve hata ayıklama hakkında daha fazla bilgi edinin:

> [!div class="nextstepaction"]
> [Visual Studio'da CMake Projeleri](cmake-projects-in-visual-studio.md)<br/><br/>
> [Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)<br/><br/>
> [Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)<br/><br/>
> [CMake derleme ayarlarını özelleştirme](customize-cmake-settings.md)<br/><br/>
> [CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)<br/><br/>
> [Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](../linux/deploy-run-and-debug-your-linux-project.md)<br/><br/>
> [CMake önceden tanımlanmış yapılandırma başvurusu](cmake-predefined-configuration-reference.md)
>
