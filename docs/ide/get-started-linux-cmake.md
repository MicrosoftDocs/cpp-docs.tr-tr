---
title: Visual Studio'da C++ platformlar arası projeler oluşturma
description: Bu öğreticide, ayarlama, derleme ve hata ayıklama hem Linux hem de Windows hedefleyen Visual Studio'da C++ açık kaynaklı CMake projesi gösterilmektedir.
author: mikeblome
ms.topic: tutorial
ms.date: 03/05/2019
ms.openlocfilehash: 5802c3f3fc82de9c43f34b93910e5837424cdd0c
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57566928"
---
# <a name="tutorial-create-c-cross-platform-projects-in-visual-studio"></a>Öğretici: Visual Studio'da C++ platformlar arası projeler oluşturma 

Visual Studio C ve C++ geliştirme artık yalnızca Windows için değil. Bu öğreticide, Visual Studio oluşturma veya Visual Studio projeleri oluşturmak zorunda kalmadan CMake tabanlı platformlar arası geliştirme için C++ kullanın. gösterilmektedir. CMakeLists.txt dosyasını içeren bir klasörü açtığınızda Visual Studio IntelliSense derleme ayarlarını yapılandırır ve otomatik olarak. Hızlı düzenleme, oluşturma ve kodunuzu Windows üzerinde yerel olarak hata ayıklama ve ardından aynı Linux'ta, tüm Visual Studio içinden yapmak için yapılandırmayı geçiş yapabilirsiniz.

Bu öğreticide şunların nasıl yapıladığını öğreneceksiniz:

> [!div class="checklist"]
> * bir açık kaynak CMake projesini github'dan kopyalama
> * Projeyi Visual Studio'da açın. 
> * derleme ve yürütülebilir bir hedef Windows üzerinde hata ayıklama
> * bir Linux makineye bir bağlantı ekleyin
> * derleme ve Linux üzerinde aynı hedefi hata ayıklama

## <a name="prerequisites"></a>Önkoşullar

- Platformlar arası C++ geliştirme için Visual Studio'yu ayarlama
    - İlk ihtiyacınız [Visual Studio'nun yüklü](https://visualstudio.microsoft.com/vs/). Ardından, sahip olduğunuz onaylayın **C++ ile masaüstü geliştirme** ve **C++ iş yükleri ile Linux geliştirme** yüklü. Bu en küçük yükleme yalnızca 3 GB, bağlı olarak, indirme hızı yükleme 10 dakikadan fazla sürmez.
- Platformlar arası C++ geliştirme için bir Linux Makine'yi ayarlayın
    - Visual Studio, herhangi bir belirli dağıtım Linux gerektirmez. İşletim sistemi Linux (WSL) bir sanal makine, Bulut veya Windows alt sistemi, fiziksel makine üzerinde çalışabilir. Ancak, Bu öğretici için bir grafik ortamı gereklidir; Bu nedenle öncelikle komut satırı işlemleri için tasarlandığından WSL önerilmez.
    - Linux makinesinde Visual Studio gerektirir araçlar şunlardır: C++ Derleyicileri, GDB, ssh ve zip. Debian tabanlı sistemlerde, bu bağımlılıklar şu şekilde yükleyebilirsiniz.
    
    ```cmd
        sudo apt install -y openssh-server build-essential gdb zip
    ```
    - Visual Studio, Linux makinesi CMake sunucusu modu (en az 3.8) etkin olan yeni bir sürümüne sahip olmasını gerektirir. Microsoft, üzerinde herhangi bir Linux distro yükleyebileceğiniz CMake Evrensel yapısı oluşturur. En son özelliklere sahip olmasını sağlamak için bu derleme kullanmanızı öneririz. CMake ikili dosyaları alabileceğiniz [CMake Deponun Microsoft çatal](https://github.com/Microsoft/CMake/releases) GitHub üzerinde. O sayfaya gidin ve Linux makinenizde sistem mimarinizle eşleşen sonra yürütülebilir olarak işaretlemek sürümünü karşıdan yükleyin:
    
    ```cmd
        wget <path to binary>
        chmod +x cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh
    ```
    - Komut dosyasını çalıştırmak için seçenekleri görebilirsiniz `-–help`. Kullanmanızı öneririz `–prefix` yükleme belirtmek için seçeneği **/usr/local** yolu, Visual Studio için CMake nerede arar varsayılan konumu olduğundan. Aşağıdaki örnek, Linux x86_64 betik gösterir. Farklı bir hedef platform kullanıyorsanız gerektiği gibi değiştirebilirsiniz. 
    
    ```cmd
        sudo ./cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh --skip-license --prefix=/usr/local
    ```
- Windows makinenizde yüklü windows için Git.
- Bir GitHub hesabı.

## <a name="clone-an-open-source-cmake-project-from-github"></a>Bir açık kaynak CMake projesini github'dan kopyalama

Bu öğretici, çeşitli farklı uygulamalar için çakışma algılama ve fizik benzetimleri sağlayan, GitHub üzerinde madde işareti fizik SDK'sını kullanır. Bu, derleme ve çalıştırma ek kod yazmak zorunda kalmadan örnek yürütülebilir programlar içerir. Bu öğreticide herhangi bir kaynak kodunun değiştirilmesi değil ya da yapı komut dosyaları. Başlamak için Visual Studio'nun yüklü olduğu bullet3 depoyu github'dan makineye kopyalayın. 

```cmd

git clone https://github.com/bulletphysics/bullet3.git

```

1. Visual Studio ana menüden seçin **Dosya > Aç > CMake** ve az önce indirdiğiniz bullet3 deponun kökünde CMakeLists.txt dosyasına gidin.

    ![Visual Studio menüsünde Dosya > Aç > CMake](media/cmake-open-cmake.png)

    Klasörü açın hemen sonra klasör yapınız görünmez **Çözüm Gezgini**.

    ![Visual Studio Çözüm Gezgini klasör görünümü](media/cmake-bullet3-solution-explorer.png)

    Bu görünüm mantıksal veya filtrelenmiş bir görünüm değil disk üzerinde tam olarak nedir gösterir. Varsayılan olarak, onu gizli dosya göstermez. 

2. Tuşuna **tüm dosyaları göster** klasördeki tüm dosyaları görmek için düğme.

    ![Visual Studio Çözüm Gezgini tüm dosyaları göster düğmesi](media/cmake-bullet3-show-all-files.png)

## <a name="switch-to-targets-view"></a>Hedefleri görünümüne geç

CMake kullanan bir klasörü açtığınızda Visual Studio CMake önbellek otomatik olarak oluşturur. Bu işlem, projenize boyutuna bağlı olarak birkaç dakika sürebilir. 

1. İçinde **çıkış penceresine**seçin **çıktıyı Göster** seçip **CMake** önbellek oluşturma işlemi durumunu izlemek için. İşlem tamamlandığında, "hedef bilgilerini ayıklama işlemi tamamlandı" diyor.

    ![Visual Studio çıkış penceresine adresinden çıkış gösteriliyor](media/cmake-bullet3-output-window.png)

    Bu işlem tamamlandıktan sonra IntelliSense yapılandırılmış, proje oluşturabilir ve uygulamada hata ayıklaması yapabilirsiniz. Visual Studio artık CMakeLists dosyalarında belirtilen hedeflere göre çözümünün mantıksal görünümünü sağlar. 

2. Kullanım **çözümler ve klasörler** düğmesine **Çözüm Gezgini** CMake hedefleri görünümüne geçin.

    ![Çözümler ve klasörler düğmesi CMake göstermek için Çözüm Gezgini'nde görünümü hedefler](media/cmake-bullet3-show-targets.png)

    Madde işareti SDK'sı için gibi görünüyor, görünümü şu şekildedir:

    ![Çözüm Gezgini CMake hedefleri görünümü](media/cmake-bullet3-targets-view.png)

    Hedefleri görünümü bu kaynağı tabanı olarak daha sezgisel bir görünüm sağlar. Bazı hedefler kitaplıklar ve diğer yürütülebilir dosyalar görebilirsiniz. 

3. Bu dosyalar disk üzerinde bulunabilir olsunlar, kaynak kodu dosyaları görmek için CMake hedefleri görünümü düğümünde genişletin.

## <a name="set-a-breakpoint-build-and-run"></a>Kesme noktası, derleme ve çalıştırma

Bu adımda, madde işareti fizik Kitaplığı gösteren bir örnek program hata ayıklama.
  
1. İçinde **Çözüm Gezgini**AppBasicExampleGui seçin ve genişletin. 
1. Dosyayı açmak `BasicExample.cpp`. 
1. Çalışan uygulamada tıkladığınızda, isabet bir kesme noktası ayarlayın. Tıklama olayı, yöntemde yardımcı bir sınıf içinde gerçekleştirilir. Hızla gitmek için:

    1. Seçin `CommonRigidBodyBase` , struct `BasicExample` 30 satırı türetilir.
    1. Sağ tıklatın ve seçin **Tanıma Git**. Üst bilgide CommonRigidBodyBase.h sunulmuştur. 
    1. Yukarıdaki kaynak tarayıcısı görünümünde olduğunuzu görmelisiniz `CommonRigidBodyBase`. Sağa incelemek için üyeleri seçebilirsiniz. Açılan listeyi tıklatın ve seçin `mouseButtonCallback` , bu işlevin üst bilgisindeki tanımına gidin.

        ![Visual Studio üye listesi araç çubuğu](media/cmake-bullet3-member-list-toolbar.png)

1. Bu işlevdeki ilk satırında bir kesme noktası koyun. Visual Studio hata ayıklayıcı altında başlatıldığında uygulama penceresi içinde bir fare düğmesine tıkladığınızda bu erişilecektir.

1. Uygulamayı başlatmak için araç çubuğunda "Başlangıç öğesi seçin" ifadesini içeren oynatma simgesine ile açılan Başlat'ı seçin. Aşağı açılan select AppBasicExampleGui.exe. Yürütülebilir adı Şimdi Başlat düğmesine görüntüler:

    ![Visual Studio araç başlangıç öğesini seçmek için aşağı açılan Başlat](media/cmake-bullet3-launch-button.png)

5.  Gerekli bağımlılıkları ve uygulama oluşturmak için Başlat düğmesine basın ve ardından Visual Studio hata ayıklayıcısı ekli başlatın. Birkaç dakika sonra çalışan uygulamada görünür:

    ![Visual Studio hata ayıklama bir Windows uygulaması](media/cmake-bullet3-launched.png)

6. Uygulama penceresine fareyi hareket ettirin ve kesme noktası tetiklemek için bir düğmeye tıklayın. Bu Visual Studio nerede yürütülmesi duraklatıldı satır gösteren düzenleyiciyle ön plana geri getirir. Uygulama değişkenleri, nesneleri, iş parçacıkları ve bellek incelemek mümkün olacaktır. Etkileşimli olarak kodunuza adım geçebilirsiniz. Tıklayabilirsiniz **devam** sürdürün ve normal çıkış veya Durdur düğmesini kullanarak Visual Studio içinde yürütme sona ermesi izin vermek için.

## <a name="add-an-explicit-windows-x64-debug-configuration"></a>Bir açık Windows x64 hata ayıklama Yapılandırması Ekle

Şu ana kadar varsayılan kullanmakta olduğunuz **x64 hata ayıklama** Windows için yapılandırma. Yapılandırmaları olan Visual Studio platformdan nasıl anlayan giderek CMake için kullanılacak hedef. Varsayılan yapılandırma, diskte temsil değil. Visual Studio, bir yapılandırma açıkça eklediğinizde, belirttiğiniz tüm yapılandırmalar için ayarları ile doldurulur CMakeSettings.json adlı bir dosya oluşturur. 

1. Tıklayarak yeni bir yapılandırma ekleyin yapılandırma araç çubuğundaki açılır ve seçerek **yapılandırmaları Yönet...**

    ![Aşağı açılan yapılandırmasını yönetme](media/cmake-bullet3-manage-configurations.png)

    **CMakeSettings yapılandırmasına ekleyin** iletişim kutusu görüntülenir.

    ![Yapılandırma CMakeSettings iletişim kutusuna ekleyin.](media/cmake-bullet3-add-configuration-x64-debug.png)

    Bu iletişim kutusu, oluşturacağınız tüm özel yapılandırmaları yanı sıra, Visual Studio ile birlikte tüm yapılandırmalarını gösterir. Varsayılan kullanmaya devam etmek istiyorsanız **x64 hata ayıklama** yapılandırması, eklediğiniz ilk öğe olmalıdır. Bu yapılandırma öğesini ekleyerek geri ve İleri yapılandırmaları Windows ile Linux arasında geçiş yapabilirsiniz olacaktır. Seçin **x64 hata ayıklama** tıklatıp **seçin**. Bunun için bir yapılandırma ile CMakeSettings.json dosyasına oluşturur **x64 hata ayıklama** ve bu yapılandırma varsayılan yerine kullanılacak Visual Studio geçer. Yapılandırma açılan adının bir parçası artık "(varsayılan)" diyor görürsünüz. Ad parametresindeki doğrudan CMakeSettings.json değiştirerek yapılandırmalarınız için gibi istediğiniz bir adı kullanabilirsiniz.

##  <a name="add-a-linux-configuration-and-connect-to-the-remote-machine"></a>Uzak makineye bağlanın ve Linux yapılandırma Ekle

1. Şimdi bir Linux yapılandırmasına ekleyin. CMakeSettings.json dosyaya sağ **Çözüm Gezgini** görüntüleyebilir ve seçebilir **Yapılandırması Ekle**. Aynı Yapılandırması Ekle iletişim kutusu CMakeSettings önce görürsünüz. Seçin **Linux hata ayıklama** bu kez, sonra CMakeSettings.json dosyasına kaydedin. 
2. Şimdi seçtiğiniz **Linux hata ayıklama** yapılandırmasında açılır.

    ![Yapılandırmayı açılan X64 hata ayıklama ve Linux hata ayıklama seçenekleri ile Başlat](media/cmake-bullet3-linux-configuration-item.png)

    Bu bir Linux sistemine bağlanırken ilk kez kullanıyorsanız **uzak sisteme Bağlan** iletişim kutusu görüntülenir.

    ![Visual Studio Connect Uzak sistemin iletişim kutusu](media/cmake-bullet3-connection-manager.png)

    Uzak bağlantı eklediyseniz bu pencereyi giderek açabilirsiniz **Araçlar > Seçenekler > Çoklu Platform > Bağlantı Yöneticisi**.
 
3. Linux makinenize bağlantı bilgisi sağlamalı ve tıklayın **Connect**. Visual Studio için varsayılan olarak bu makineye CMakeSettings.json seçeceğine ekler **Linux hata ayıklama**. Kullandığınızda, IntelliSense bu makineye belirli alabilmeniz Ayrıca, uzak makineden üstbilgileri aşağı çeker. Visual Studio, dosyaları uzak makineye göndermek, daha sonra CMake önbelleğini oluşturun ve yaptığınızda Visual Studio temel aynı kaynak, uzak Linux makinesinin ile kullanmak için yapılandırılacaktır. Bu adımlar, ağ hızına ve uzak makinenizi gücünü bağlı olarak biraz zaman alabilir. CMake çıkış penceresinde "hedef bilgilerini ayıklama işlemi tamamlandı" iletisi göründüğünde bu işlem tamamlandıktan öğrenmiş olacaksınız.

## <a name="set-a-breakpoint-build-and-run-on-linux"></a>Bir kesme noktası ayarlayın, derleme ve Linux üzerinde çalıştırın

Bu bir masaüstü uygulaması olduğundan, hata ayıklama yapılandırması için bazı ek yapılandırma bilgileri vermeniz gerekir. 

1. CMake hedefleri görünümü AppBasicExampleGui sağ tıklatın ve seçin **hata ayıklama ve başlatma ayarları** gizli launch.vs.json dosyasını açmak için **.vs** alt. Bu dosya, geliştirme ortamınızı yereldir. İçinde ve kaydedin, ekibinizle birlikte iade istiyorsanız, projenizin kök ile taşıyabilirsiniz. Bu dosyada bir yapılandırma için AppBasicExampleGui eklendi. Bu varsayılan ayarları çoğu zaman uyumludur, ancak bu şekilde programını başlatmak için bazı ek bilgiler sağlamanız gereken bir masaüstü uygulaması olduğundan bizim Linux makinesinde görebilirsiniz. 
2. Ortam değişkeninin değerini bilmeniz gereken `DISPLAY` Linux makinenizde almak için şu komutu çalıştırın.

    ```cmd
    echo $DISPLAY
    ```

    AppBasicExampleGui yapılandırmasında bir parametre dizisi "pipeArgs" yoktur. Burada içinde bir satır olduğundan "${debuggerCommand}". Bu uzak makinede gdb başlatan komuttur. Bu komutu çalıştırmadan önce bu bağlamda ekranını dışarı aktarmak Visual Studio gerekir. Örneğin, ekranınıza değerini: 1, bu satırı aşağıdaki gibi değiştirin:

    ```cmd
    "export DISPLAY=:1;${debuggerCommand}",
    ```
3. Uygulamamızı hata ayıklama ve başlatma için artık seçim **başlangıç öğesi seçin** açılan araç çubuğunda ve AppBasicExampleGui seçin. Artık bu düğmeyi tuşuna basın veya isabet **F5**. Bu uygulamayı derler ve bağımlılıklarını uzak Linux makinesine sonra Visual Studio hata ayıklayıcısı ekli başlatın. Uzak Linux makinenizde görünür bir uygulama penceresini görmeniz gerekir.

4. Uygulama penceresine fareyi hareket ettirin bir düğmeye tıklayın ve kesme noktasına ulaşırsınız. Program yürütme duraklatır, Visual Studio ön plana geri gelir ve, kesme noktasında olacaktır. Ayrıca, Visual Studio'da görünen bir Linux konsol penceresi görmeniz gerekir. Bu pencere, uzak Linux makinesinin çıktısını sağlar ve ayrıca girişi kabul edebilir `stdin`. Tüm Visual Studio penceresi gibi burada görmek tercih ettiğiniz ve konumunu gelecek oturumlarda kalıcı hale sabitlenebilir.

    ![Visual Studio Linux konsol penceresi](media/cmake-bullet3-linux-console.png)

5. Kodunuzu etkileşimli olarak Visual Studio kullanarak uygulama değişkenleri, nesneleri, iş parçacıkları, bellek ve adım inceleyebilirsiniz. Ancak bu kez, tüm bu uzak Linux makinesinde yerine yerel Windows ortamınızı yapıyor. Tıklayabilirsiniz **devam** kaldığınız yerden devam edip çıkmak normalde, izin vermek amacıyla veya ile olduğu gibi yerel yürütme Durdur düğmesine basabilirsiniz.

6. Çağrı yığını penceresinde arayın ve çağrıları görüntülemek `x11OpenGLWindow` beri uygulamanın Linux üzerinde Visual Studio başlatılır.

    ![Çağrı yığını penceresi Linux çağrı yığınını gösteren](media/cmake-bullet3-linux-callstack.png)

## <a name="what-you-learned"></a>Öğrendikleriniz 

Bu öğreticide, doğrudan github'dan kopyalanan ve yerleşik, çalıştırma ve hata ayıklaması Windows üzerinde herhangi bir değişiklik ile temel bir kod gördünüz. Bu kod tabanı küçük yapılandırma değişiklikleriyle gelen, yerleşik, çalıştırın ve Linux makinesinde uzaktan hata ayıklama. 

## <a name="next-steps"></a>Sonraki adımlar

Yapılandırma ve CMake projeleri Visual Studio'da hata ayıklama hakkında daha fazla bilgi edinin:

> [!div class="nextstepaction"]
> [Visual C++ için CMake araçları](../ide/cmake-tools-for-visual-cpp.md)<br/><br/>
> [Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)<br/><br/>
> [Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)<br/><br/>
> [CMake derleme ayarlarını özelleştirme](customize-cmake-settings.md)<br/><br/>
> [Hata ayıklama oturumları CMake yapılandırma](configure-cmake-debugging-sessions.md)<br/><br/>
> [Dağıtma, çalıştırma ve Linux projenizin hatalarını ayıklama](../linux/deploy-run-and-debug-your-linux-project.md)<br/><br/>
> [Önceden tanımlanmış CMake yapılandırma başvurusu](cmake-predefined-configuration-reference.md)
> 
