---
title: Visual Studio’da platformlar arası C++ projeleri oluşturma
description: Bu öğreticide, Visual Studio 'da hem Linux hem de Windows 'u C++ hedefleyen açık kaynaklı bir CMake projesini ayarlama, derleme ve hata ayıklama işlemlerinin nasıl yapılacağı gösterilmektedir.
author: mikeblome
ms.topic: tutorial
ms.date: 03/05/2019
ms.openlocfilehash: cd01d5e389bda46fbb05d297ece8e68ef2265725
ms.sourcegitcommit: c53a3efcc5d51fc55fa57ac83cca796b33ae888f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71960721"
---
# <a name="tutorial-create-c-cross-platform-projects-in-visual-studio"></a>Öğretici: Visual C++ Studio 'da platformlar arası projeler oluşturma 

Visual Studio C ve C++ geliştirme artık yalnızca Windows için değildir. Bu öğreticide, Visual Studio projeleri oluşturmaya veya C++ oluşturmaya gerek kalmadan CMake tabanlı platformlar arası geliştirme Için Visual Studio 'nun nasıl kullanılacağı gösterilmektedir. CMakeLists. txt dosyasını içeren bir klasörü açtığınızda, Visual Studio IntelliSense ve derleme ayarlarını otomatik olarak yapılandırır. Kodunuzu Windows üzerinde yerel olarak düzenleyebilir, oluşturabilir ve hata ayıklamanıza, sonra da yapılandırmanızı Linux 'ta aynı olacak şekilde, hepsi de Visual Studio içinden geçirebilirsiniz.

Bu öğreticide şunların nasıl yapıladığını öğreneceksiniz:

> [!div class="checklist"]
> * GitHub 'dan açık kaynaklı bir CMake projesini kopyalama
> * Projeyi Visual Studio 'da aç 
> * Windows üzerinde yürütülebilir bir hedef oluşturma ve hata ayıklama
> * Linux makinesine bağlantı ekleme
> * Linux 'ta aynı hedefte derleme ve hata ayıklama

## <a name="prerequisites"></a>Prerequisites

- Platformlar arası C++ geliştirme Için Visual Studio 'yu ayarlama
    - Önce [Visual Studio 'nun yüklü](https://visualstudio.microsoft.com/vs/)olması gerekir. Daha sonra, yüklü **iş yükleriyle C++**  **birlikte C++ masaüstü geliştirme** ve Linux geliştirme hakkında emin olun. Bu minimum yükleme, indirme hızı yüklemenize bağlı olarak 10 dakikadan uzun sürmemelidir.
- Platformlar arası C++ geliştirme Için bir Linux makinesi ayarlama
    - Visual Studio, Linux 'un belirli bir dağıtımına gerek yoktur. İşletim sistemi bir fiziksel makinede, bir VM 'de, bulutta veya Linux için Windows alt sisteminde (WSL) çalıştırılabilir. Bununla birlikte, bu öğreticide grafik ortamı gereklidir; Bu nedenle, öncelikli olarak komut satırı işlemleri için tasarlanan WSL önerilmez.
    - Visual Studio 'Nun Linux makinesinde gerektirdiği araçlar şunlardır: C++ derleyiciler, gdb, SSH, rsync ve zip. BT tabanlı sistemlerde, bu bağımlılıkları aşağıdaki şekilde yükleyebilirsiniz.
    
    ```cmd
        sudo apt install -y openssh-server build-essential gdb rsync zip
    ```
    - Visual Studio, Linux makinesinde sunucu modunun etkin olduğu bir CMake sürümünün (en az 3,8) olmasını gerektirir. Microsoft, herhangi bir Linux 'ta yükleyebileceğiniz bir evrensel CMake derlemesi oluşturur. En son özelliklere sahip olduğunuzdan emin olmak için bu derlemeyi kullanmanızı öneririz. GitHub 'daki [CMake deposunun Microsoft çatalından](https://github.com/Microsoft/CMake/releases) CMake ikili dosyalarını alabilirsiniz. Bu sayfaya gidin ve Linux makinenizde sistem mimarinizle eşleşen sürümü indirin, sonra yürütülebilir olarak işaretleyin:
    
    ```cmd
        wget <path to binary>
        chmod +x cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh
    ```
    - Betiği `-–help` ile çalıştırmaya yönelik seçenekleri görebilirsiniz. Visual Studio 'nun CMake 'e baktığı varsayılan konum olduğundan, **/usr/local** yoluna yüklemeyi belirtmek için `–prefix` seçeneğini kullanmanızı öneririz. Aşağıdaki örnekte, Linux-x86_64 betiği gösterilmektedir. Farklı bir hedef platform kullanıyorsanız, gereken şekilde değiştirin. 
    
    ```cmd
        sudo ./cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh --skip-license --prefix=/usr/local
    ```
- Windows makinenizde yüklü olan Windows için git.
- Bir GitHub hesabı.

## <a name="clone-an-open-source-cmake-project-from-github"></a>GitHub 'dan açık kaynaklı bir CMake projesini kopyalama

Bu öğreticide, GitHub üzerinde fizik SDK, çeşitli farklı uygulamalar için çakışma algılama ve fizik simülasyonu sağlayan bir madde Işareti kullanılmaktadır. Ek kod yazmak zorunda kalmadan derleyip çalıştıran örnek yürütülebilir programları içerir. Bu öğretici, kaynak kodların veya derleme betiklerinin hiçbirini değiştirmez. Başlamak için, Visual Studio 'Nun yüklü olduğu makinede bullet3 deposunu GitHub 'dan klonlayın. 

```cmd

git clone https://github.com/bulletphysics/bullet3.git

```

1. Visual Studio ana menüsünde **dosya > seçin > CMake** ' i açın ve az önce indirdiğiniz bullet3 deposunun kökündeki CMakeLists. txt dosyasına gidin.

    ![Dosya > açık > CMake için Visual Studio menüsü](media/cmake-open-cmake.png)

    Klasörü açtığınızda, klasör yapınız **Çözüm Gezgini**görünür olur.

    ![Visual Studio Çözüm Gezgini klasör görünümü](media/cmake-bullet3-solution-explorer.png)

    Bu görünüm, mantıksal veya filtrelenmiş bir görünüm değil diskte tam olarak neler olduğunu gösterir. Varsayılan olarak, gizli dosyaları göstermez. 

2. Klasördeki tüm dosyaları görmek için **tüm dosyaları göster** düğmesine basın.

    ![Visual Studio Çözüm Gezgini tüm dosyaları göster düğmesi](media/cmake-bullet3-show-all-files.png)

## <a name="switch-to-targets-view"></a>Hedefler görünümüne geç

CMake kullanan bir klasörü açtığınızda, Visual Studio otomatik olarak CMake önbelleğini oluşturur. Bu işlem, projenizin boyutuna bağlı olarak birkaç dakika sürebilir. 

1. **Çıkış penceresi**, **çıktıyı göster** ' i seçin ve ardından önbellek oluşturma Işleminin durumunu izlemek için **CMake** ' i seçin. İşlem tamamlandığında, "hedef bilgileri ayıklama tamamlandı" ifadesini belirtir.

    ![CMake çıkışının gösterildiği Visual Studio çıkış penceresi](media/cmake-bullet3-output-window.png)

    Bu işlem tamamlandıktan sonra, IntelliSense yapılandırılır, proje oluşturabilir ve uygulamada hata ayıklaması yapabilirsiniz. Visual Studio artık CMakeLists dosyalarında belirtilen hedeflere dayalı olarak çözümün mantıksal bir görünümünü sağlayabilir. 

2. CMake hedefleri görünümüne geçmek için **Çözüm Gezgini** **çözüm ve klasörler** düğmesini kullanın.

    ![CMake hedeflerini göstermek için Çözüm Gezgini çözüm ve klasörler düğmesi](media/cmake-bullet3-show-targets.png)

    Bu görünüm, madde Işareti SDK 'Sı için şöyle görünür:

    ![CMake hedeflerini Çözüm Gezgini görünümü](media/cmake-bullet3-targets-view.png)

    Hedefler görünümü bu kaynak tabanında nelerin daha sezgisel bir görünümünü sağlar. Bazı hedeflerin kitaplıkların olduğunu ve başkalarının yürütülebilir olduğunu görebilirsiniz. 

3. Bu dosyaların diskte bulunduğu her yerde kaynak kodu dosyalarını görmek için CMake hedefleri görünümündeki bir düğümü genişletin.

## <a name="add-an-explicit-windows-x64-debug-configuration"></a>Açık bir Windows x64-hata ayıklama yapılandırması ekleme

Visual Studio, Windows için varsayılan bir **x64-hata ayıklama** yapılandırması oluşturur. Yapılandırma, Visual Studio 'nun CMake için hangi platform hedefini kullandığını öğrendiği bir şeydir. Varsayılan yapılandırma diskte temsil değildir. Açıkça bir yapılandırma eklediğinizde, Visual Studio belirttiğiniz tüm yapılandırmaların ayarlarıyla doldurulan CMakeSettings. JSON adlı bir dosya oluşturur. 

1. Araç çubuğundaki yapılandırma açılır listesini tıklayıp **yapılandırmaları Yönet...** öğesini seçerek yeni bir yapılandırma ekleyin.

    ![Yapılandırma açılan eklentisini yönetme](media/cmake-bullet3-manage-configurations.png)

    Bu, [CMake ayarları düzenleyicisini](customize-cmake-settings.md)açar. Yeni bir yapılandırma eklemek için düzenleyicinin sol tarafındaki yeşil artı işaretini seçin. **CMakeSettings 'e yapılandırma Ekle** iletişim kutusu görünür.

    ![CMakeSettings iletişim kutusuna yapılandırma Ekle](media/cmake-bullet3-add-configuration-x64-debug.png)

    Bu iletişim kutusu, Visual Studio 'Ya dahil edilen tüm yapılandırmaların yanı sıra, oluşturabileceğiniz özel yapılandırmaların de gösterir. **X64-hata ayıklama** yapılandırmasını kullanmaya devam etmek istiyorsanız, bu, ilk eklediğiniz ilk olmalıdır. **X64-Debug** ' ı seçin ve **Seç**' e tıklayın. Bu, bir **x64-Debug** yapılandırması Ile CMakeSettings. json dosyasını oluşturur ve yapılandırmayı diske kaydeder. Ad parametresini doğrudan CMakeSettings. JSON içinde değiştirerek, yapılandırlarınız için istediğiniz adları kullanabilirsiniz.

## <a name="set-a-breakpoint-build-and-run-on-windows"></a>Windows üzerinde kesme noktası ayarlama, derleme ve çalıştırma 

Bu adımda, madde Işareti fizik kitaplığını gösteren örnek bir programda hata ayıklaması yapacağız.
  
1. **Çözüm Gezgini**' de AppBasicExampleGui ' ı seçin ve genişletin. 
1. Dosyayı açın `BasicExample.cpp`. 
1. Çalışan uygulamaya tıkladığınızda isabet edilecek bir kesme noktası ayarlayın. Click olayı bir yardımcı sınıf içindeki bir yöntemde işlenir. Hızlıca almak için:

    1. @No__t-1 @no__t yapısının, 30. satırın etrafında türetildiğinden önce 0 ' ı seçin.
    1. Sağ tıklayın ve **Tanıma Git**' i seçin. Artık CommonRigidBodyBase. h üst bilgisinde çalışıyorsunuz. 
    1. Yukarıdaki tarayıcı görünümünde, kaynağınız `CommonRigidBodyBase` ' da olduğunu görmeniz gerekir. Sağ tarafta, incelemek üzere üyeleri seçebilirsiniz. Başlıktaki bu işlevin tanımına gitmek için açılan aşağı tıklayın ve `mouseButtonCallback` ' ı seçin.

        ![Visual Studio üye listesi araç çubuğu](media/cmake-bullet3-member-list-toolbar.png)

1. Bu işlevin içindeki ilk satıra bir kesme noktası koyun. Bu, Visual Studio hata ayıklayıcısı altında başlatıldığında uygulamanın penceresinde bir fare düğmesine tıkladığınızda bu sonucu alırsınız.

1. Uygulamayı başlatmak için, araç çubuğunda "başlangıç öğesini seç" diyen Play simgesiyle Başlat açılan simgesini seçin. Açılan kutuda AppBasicExampleGui. exe ' yi seçin. Yürütülebilir dosya adı Şimdi Başlat düğmesinde görüntülenir:

    ![Başlangıç öğesi seç için Visual Studio araç çubuğu başlatma açılan menüsü](media/cmake-bullet3-launch-button.png)

5.  Uygulamayı ve gerekli bağımlılıkları oluşturmak için Başlat düğmesine basın, ardından Visual Studio hata ayıklayıcısı ekli olarak başlatın. Birkaç dakika sonra, çalışan uygulama görünür:

    ![Visual Studio bir Windows uygulamasında hata ayıklama](media/cmake-bullet3-launched.png)

6. Farenizi uygulama penceresine taşıyın ve ardından bir düğmeye tıklayarak kesme noktasını tetikleyin. Bu, Visual Studio 'Yu, yürütmenin duraklatıldığı çizgiyi gösteren düzenleyiciyle ön plana geri getirir. Uygulama değişkenlerini, nesneleri, iş parçacıklarını ve belleği inceleyebilirsiniz. Kodunuzda etkileşimli olarak gezinebilirsiniz. Uygulamanın çalışmaya devam etmesini sağlamak için **devam** ' a tıklayabilir veya Durdur düğmesini kullanarak Visual Studio içinde yürütmeyi durduramazsınız.

##  <a name="add-a-linux-configuration-and-connect-to-the-remote-machine"></a>Linux yapılandırması ekleme ve uzak makineye bağlanma

1. Şimdi bir Linux yapılandırması ekleyin. **Çözüm Gezgini** görünümünde CMakeSettings. JSON dosyasına sağ tıklayın ve **yapılandırma Ekle**' yi seçin. Daha önce olduğu gibi CMakeSettings iletişim kutusunda aynı yapılandırma Ekle ' ye bakabilirsiniz. Linux ' u seçin-bu kez **hata ayıklayın** , sonra CMakeSettings. json dosyasını kaydedin (Ctrl + s). 
2. Şimdi yapılandırma açılır penceresinde **Linux-Debug** ' ı seçin.

    ![X64-hata ayıklama ve Linux-hata ayıklama seçenekleri ile yapılandırma açılan eklentisini başlatma](media/cmake-bullet3-linux-configuration-item.png)

    Bir Linux sistemine ilk kez bağlanıyorsanız, **uzak sistem 'e Bağlan** iletişim kutusu görüntülenir.

    ![Visual Studio uzak sisteme Bağlan iletişim kutusu](media/cmake-bullet3-connection-manager.png)

    Zaten bir uzak bağlantı eklediyseniz, **araçlar > seçenekler > platformlar arası > bağlantı Yöneticisi**' ne giderek bu pencereyi açabilirsiniz.
 
3. [Linux makinenize bağlantı bilgilerini girin] (Connect-to-Remote-Linux-computer.md] ve **Bağlan**' a tıklayın. Visual Studio, bu makineyi **Linux-Debug**için varsayılan bağlantınız olarak CMakeSettings. JSON öğesine ekler. Ayrıca, [söz konusu uzak bağlantıya özel IntelliSense](https://docs.microsoft.com/en-us/cpp/linux/configure-a-linux-project?view=vs-2019#remote_intellisense)'i alabilmeniz için uzak makinenizden üstbilgileri çeker. Şimdi Visual Studio, dosyalarınızı uzak makineye gönderir ve uzak sistemde CMake önbelleğini oluşturur. Bu adımlar ağınızın hızına ve uzak makinenizin gücüne bağlı olarak biraz zaman alabilir. CMake çıkış penceresinde "hedef bilgi ayıklama işlemi tamamlandı" iletisi göründüğünde bunun tamamlandığını bilirsiniz.

## <a name="set-a-breakpoint-build-and-run-on-linux"></a>Linux üzerinde bir kesme noktası ayarlayın, derleyin ve çalıştırın

Bu bir masaüstü uygulaması olduğundan, hata ayıklama yapılandırmasına bazı ek yapılandırma bilgileri sağlamanız gerekir. 

1. CMake hedefleri görünümünde AppBasicExampleGui öğesine sağ tıklayın ve **Hata Ayıkla ve başlatma ayarları** ' nı seçerek Hidden **. vs** alt klasöründeki Launch. vs. json dosyasını açın. Bu dosya, geliştirme ortamınız için yereldir. İade etmek ve ekibinizle kaydetmek istiyorsanız, bunu projenizin köküne taşıyabilirsiniz. Bu dosyada AppBasicExampleGui için bir yapılandırma eklenmiştir. Bu varsayılan ayarlar çoğu durumda çalışır, ancak bu bir masaüstü uygulaması olduğu için programı Linux makinemizdeki bir şekilde başlatmak üzere bazı ek bilgiler sağlamanız gerekir. 
2. Linux makinenizde `DISPLAY` ortam değişkeninin değerini bilmeniz gerekir, bu komutu almak için bu komutu çalıştırın.

    ```cmd
    echo $DISPLAY
    ```

    AppBasicExampleGui yapılandırmasında, "pipeArgs" parametre dizisi vardır. İçinde "$ {debuggerCommand}" satırı bulunur. Bu, uzak makinede gdb 'yi Başlatan komuttur. Bu komutu çalıştırmadan önce Visual Studio 'Nun ekranı bu içeriğe dışarı aktarılması gerekir. Örneğin, görüntülerinizin değeri: 1 ise, bu satırı aşağıdaki gibi değiştirin:

    ```cmd
    "export DISPLAY=:1;${debuggerCommand}",
    ```
3. Uygulamamızı başlatmak ve hatalarını ayıklamak için, araç çubuğunda **Başlangıç öğesi Seç** açılan penceresini seçin ve AppBasicExampleGui öğesini seçin. Şimdi bu düğmeye veya **F5**'e basın. Bu işlem, uygulamayı ve onun bağımlılıklarını uzak Linux makinesinde oluşturur ve ardından Visual Studio hata ayıklayıcısı ekli olarak başlatır. Uzak Linux makinenizde bir uygulama penceresi göründüğünü görmeniz gerekir.

4. Farenizi uygulama penceresine taşıyın, bir düğmeye tıklayın ve kesme noktası isabet eder. Program yürütme duraklatılır, Visual Studio ön plana geri gelir ve kesme noktasından olursunuz. Ayrıca, Visual Studio 'da bir Linux konsol penceresi göründüğünü görmeniz gerekir. Bu pencere, uzak Linux makinesinden çıkış sağlar ve `stdin` girişi de kabul edebilir. Tüm Visual Studio pencereleri gibi, onu görmeyi tercih ettiğiniz yere yerleştirilebilir ve bu nesnenin konumu gelecekteki oturumlarda kalıcı olacak.

    ![Visual Studio Linux konsol penceresi](media/cmake-bullet3-linux-console.png)

5. Visual Studio kullanarak uygulama değişkenlerini, nesneleri, iş parçacıklarını, belleği ve kodunuzu etkileşimli olarak inceleyebilirsiniz. Ancak bu sefer, bu kez yerel Windows ortamınız yerine bir uzak Linux makinesinde yapabilirsiniz. Uygulamanın çalışmaya devam etmesini ve normal bir şekilde çıkmasına izin vermek için **devam** ' a tıklayabilir veya yerel yürütmede olduğu gibi Durdur düğmesine de basabilirsiniz.

6. Çağrı yığını penceresine bakın ve Visual Studio uygulamayı Linux üzerinde başlatmasından sonra `x11OpenGLWindow` ' a yapılan çağrıları görüntüleyin.

    ![Linux çağrı yığınını gösteren çağrı yığını penceresi](media/cmake-bullet3-linux-callstack.png)

## <a name="what-you-learned"></a>Öğrendikleriniz 

Bu öğreticide, doğrudan GitHub 'dan klonlanan ve Windows 'da oluşturulan, çalıştırılan ve hata ayıklamış bir kod temelini hiçbir değişiklik yapmadan gördünüz. Bu, küçük yapılandırma değişiklikleriyle birlikte, uzak bir Linux makinesinde oluşturulan, çalıştırılan ve hata ayıklamakta olan kod tabanına gelmiştir. 

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
