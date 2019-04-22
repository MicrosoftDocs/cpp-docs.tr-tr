---
title: Visual Studio’ya C++ desteği yükleme
description: Visual C++ için Visual Studio desteği yükleme
ms.custom: mvc
ms.date: 04/02/2019
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 2c2bed4063194bdc3c0f3fbc405be6bf9a4031e7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58870786"
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio’ya C++ desteği yükleme

İndirilen ve henüz Visual Studio ve Visual C++ Araçları yüklü olmayan, kullanmaya nasıl başlayacağınızı aşağıda verilmiştir.

::: moniker range="vs-2019"

## <a name="visual-studio-2019-installation"></a>Visual Studio 2019 yüklemesi

Hoş Geldiniz Visual Studio 2019! Bu sürümde, seçin ve yalnızca gereksinim duyduğunuz özellikleri yüklemek kolaydır. Ve kendi kapladığı alan alt nedeniyle, hızlı ve sistemi daha az etkileyerek yükler.

> [!NOTE]
> Bu konu, Windows üzerinde Visual Studio yüklemeniz için geçerlidir. [Visual Studio Code](https://code.visualstudio.com/) Windows, Mac ve Linux sistemlerinde çalıştırılan bir basit, platformlar arası geliştirme ortamıdır. Microsoft [Visual Studio Code için C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) uzantısı IntelliSense, hata ayıklama, kod biçimlendirme, otomatik tamamlanmasını destekler. Mac için Visual Studio, Microsoft C++ desteklemez ancak .NET diller ve platformlar arası geliştirmeyi destekler. Yükleme yönergeleri için bkz. [Mac için Visual Studio](/visualstudio/mac/installation/).

Else bu sürümdeki yenilikler hakkında daha fazla bilgi edinmek istiyorsunuz? Visual Studio bkz [sürüm notları](/visualstudio/releases/2019/release-notes/).

Yüklenmeye hazır? Biz, bunu, adım adım konusunda rehberlik edelim.

### <a name="step-1---make-sure-your-computer-is-ready-for-visual-studio"></a>1. adım: bilgisayarınızın Visual Studio'ya hazır olduğundan emin olun

Visual Studio yükleme başlamadan önce:

1. Denetleme [sistem gereksinimleri](/visualstudio/releases/2019/system-requirements). Bu gereksinimleri bilgisayarınıza Visual Studio 2019 destekleyip desteklemediğini bilmenize yardımcı olur.

1. En son Windows güncelleştirmelerini uygulayın. Bu güncelleştirmeler, bilgisayarınızda Visual Studio için en son güvenlik güncelleştirmelerini hem gerekli sistem bileşenlerine sahip olun.

1. Yeniden başlatma. Yeniden başlatma bekleyen yükleme veya güncelleştirmelerin Visual Studio yüklemesini engellememesini sağlar.

1. Alan boşaltın. Gereksiz dosyaları ve uygulamalar, % SYSTEMDRIVE %, örneğin, Disk Temizleme uygulamayı çalıştıran kaldırın.

Visual Studio 2019 ile yan yana Visual Studio'nun önceki sürümleri çalıştıran hakkında sorular için bkz [Visual Studio 2019 Platform hedefleme ve Uyumluluk](/visualstudio/releases/2019/compatibility/) sayfası.

### <a name="step-2---download-visual-studio"></a>Adım 2 - Visual Studio indirme

Ardından, Visual Studio önyükleyicisi dosyasını indirin. Bunu yapmak için aşağıdaki düğmeyi seçin, seçmek istediğiniz Visual Studio sürümünü **Kaydet**ve ardından **Klasör Aç**.

 > [!div class="button"]
 > [Visual Studio'yu indirin](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+rc)

### <a name="step-3---install-the-visual-studio-installer"></a>3. adım - Visual Studio Yükleyicisi'ni yükleme

Visual Studio Yükleyicisi'ni yüklemek için önyükleyici dosyasını çalıştırın. Yeni Basit yükleyicinin hem yüklemek ve Visual Studio'yu özelleştirme için gereken her şeyi içerir.

1. Öğesinden, **indirir** klasöründe eşleşen veya benzer bir aşağıdaki dosyalar önyükleyici çift tıklayın:

   * **vs_community.exe** Visual Studio Community için
   * **vs_professional.exe** Visual Studio Professional
   * **vs_enterprise.exe** için Visual Studio Enterprise

   Bir kullanıcı hesabı denetimi bildirim alırsanız seçin **Evet**.

1. Microsoft onaylamak için isteriz [lisans koşulları](https://visualstudio.microsoft.com/license-terms/) ve Microsoft [gizlilik bildirimi](https://privacy.microsoft.com/privacystatement). Seçin **devam**.

### <a name="step-4---choose-workloads"></a>4. adım - iş yüklerini seçme

Yükleyici yüklendikten sonra bunu seçerek yüklemenizi özelleştirmek için kullanabileceğiniz *iş yükleri*, ya da özellik istediğiniz ayarlar. İşte nasıl.

1. Bulmak istediğiniz iş yükünü **Visual Studio'yu** ekran.

   ![Visual Studio 2019 : Bir iş yükünü yükleyin](../get-started/media/vs-installer-workloads.png)

   Çekirdek C++ desteği için "C++ ile masaüstü geliştirme" iş yükünü seçin. Bu, temel kod düzenleme açın ve projeye gerek kalmadan herhangi bir klasörden kodu düzenleme olanağı 20'den dil için destek içerir ve tümleşik kaynak kod denetimi varsayılan çekirdek Düzenleyicisi ile birlikte gelir.

   Ek iş yüklerinin başka türden bir C++ geliştirme desteği. Örneğin, Windows çalışma zamanı için Microsoft Store kullanan uygulamalar oluşturmak için "Evrensel Windows platformu geliştirme" iş yükünü seçin. "C++ ile oyun geliştirme" seçin DirectX, Unreal ve Cocos2d kullanan oyunlar oluşturmak için. "C++ ile Linux geliştirme" IOT geliştirme de dahil olmak üzere, hedef Linux platformlarını seçin.

   **Yükleme ayrıntıları** bölmesi, her iş yükü tarafından bulunan ve isteğe bağlı bileşenleri listeler. Bu listedeki isteğe bağlı bileşenlerin seçimlerini kaldırın ya da seçin. Örneğin, Visual Studio 2017 veya 2015 derleyici araç takımları kullanarak geliştirme desteği için MSVC v141 veya MSVC v140 isteğe bağlı bileşenleri seçin. MFC, Deneysel modülleri dil uzantısı, IncrediBuild ve daha fazlası için destek ekleyebilirsiniz.

1. İstediğiniz isteğe bağlı bileşenleri ve workload(s) seçtikten sonra seçin **yükleme**.

    Ardından, durum ekranları, Visual Studio yüklemenizin ilerleme durumunu gösteren görünür.

> [!TIP]
> Yüklemeden sonra herhangi bir zamanda iş yükleri veya başlangıçta yüklenmedi bileşenleri yükleyebilirsiniz. Visual Studio'nun varsa **Araçları** > **araçları ve özellikleri Al...**  Visual Studio yükleyicisi açılır. Veya açık **Visual Studio yükleyicisi** Başlat menüsünden. Burada, iş yükleri veya yüklemek istediğiniz bileşenleri seçebilirsiniz. Ardından, **Değiştir**.

## <a name="step-5---choose-individual-components-optional"></a>5. adım - (isteğe bağlı) bileşenleri tek tek seçme

Visual Studio yüklemenizi özelleştirmek için iş yüklerini özelliğini kullanmak istemediğiniz ya da bir iş yükü yükler çok daha fazla bileşen eklemek istediğiniz, yükleme veya tek tek bileşenleri ekleyerek bunu yapabilirsiniz **bağımsızbileşenler** sekmesi. Neleri istediğiniz ve daha sonra izleyin seçin yönergeleri.

  ![Visual Studio 2019 - tek tek bileşenleri yükle](../get-started/media/vs-installer-individual-components.png "tek tek bileşenler Visual Studio'yu yükleyin")

## <a name="step-6---install-language-packs-optional"></a>6. adım - yükleme dil paketleri (isteğe bağlı)

Varsayılan olarak, yükleyici programı ilk kez çalıştığında işletim sisteminin dilini eşleştirmeye çalışır. Visual Studio bir dilde yüklemek için seçin **dil paketlerini** sekmesinde Visual Studio Yükleyicisi'nden ve ardından yönergeleri izleyin.

  ![Visual Studio 2019 - yükleme dil paketlerini](../get-started/media/vs-installer-language-packs.png "Visual Studio'yu yükleyin dil paketleri")

### <a name="change-the-installer-language-from-the-command-line"></a>Komut satırından yükleyici dilini değiştirme

Varsayılan dilini değiştirme başka bir komut satırından yükleyiciyi çalıştırarak yoludur. Örneğin, aşağıdaki komutu kullanarak İngilizce olarak çalıştırmak için yükleyici zorlayabilirsiniz: `vs_installer.exe --locale en-US`. Yükleyici, sonraki açışınızda çalıştırdığınızda bu ayar hatırlanır. Aşağıdaki Dil belirteçler yükleyici destekler: zh-cn, zh-tw, cs-cz, en-us, es-es, fr-fr, de-de, it-IT, ja-jp, ko-kr, pl-pl, pt-br, ru-ru ve tr-tr.

### <a name="step-7---change-the-installation-location-optional"></a>7. adım - (isteğe bağlı) yükleme konumunu değiştirme

Visual Studio yükleme ayak izini sistem sürücünüzde azaltabilir. İndirme önbelleğini, paylaşılan bileşenler, SDK'ları ve araçları farklı sürücülere taşıma ve Visual Studio en hızlı çalışan sürücüde korumak seçebilirsiniz.

  ![Visual Studio 2019 - değişiklik yükleme konumlarını](../get-started/media/vs-installer-installation-locations.png "yükleme konumunu değiştirme")

> [!IMPORTANT]
> Yalnızca Visual Studio ilk kez yüklediğinizde, farklı bir sürücü seçebilirsiniz. Yüklemiş olduğunuz ve sürücüleri değiştirmek istiyorsanız, Visual Studio'yu kaldırın ve yeniden yükleyin.

## <a name="step-8---start-developing"></a>8. adım - geliştirmeye başlayın

1. Visual Studio yüklemesi tamamlandıktan sonra seçin **başlatma** Visual Studio ile geliştirmeye başlamak için düğme.

1. Pencerenin başlangıç seçin **yeni bir proje oluşturma**.

1. Arama kutusuna, kullanılabilir şablonların listesini görmek için oluşturmak istediğiniz uygulamanın türüne girin. Şablonlar listesinde, yükleme sırasında seçtiğiniz workload(s) bağlıdır. Farklı şablonları görmek için farklı iş yüklerini seçin.

   Kullanarak aramanızı belirli bir programlama dili için filtreleyebilirsiniz **dil** aşağı açılan listesi. Kullanarak filtreleyebilirsiniz **Platform** listesi ve **proje türü** çok listesi.

1. Yeni projeniz Visual Studio açar ve kodu hazırsınız!

::: moniker-end

::: moniker range="<=vs-2017"

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017 yüklemesi

Visual Studio 2017'de seçin ve yalnızca gereksinim duyduğunuz özellikleri yüklemek kolaydır. Ve kendi kapladığı alan alt nedeniyle, hızlı ve sistemi daha az etkileyerek yükler.

### <a name="prerequisites"></a>Önkoşullar

- Geniş bant internet bağlantısı. Visual Studio yükleyicisinin birçok gigabayta kadar veri indirebilirsiniz.

- Microsoft Windows 7 veya sonraki sürümleri çalıştıran bir bilgisayar. Windows 10 için en iyi geliştirme deneyimi öneririz. Visual Studio yüklemeden önce en son güncelleştirmeleri sisteminize uygulandığından emin olun.

- Yeterli boş disk alanı. Visual Studio, en az 7 GB disk alanı gerektirir ve birçok ortak seçenekleri yüklüyse, 50 GB veya daha fazla sürebilir. C: sürücünüzde yüklemeniz önerilir.

Disk alanı ve işletim sistemi gereksinimleri hakkında daha fazla bilgi için bkz: [Visual Studio ürün ailesi sistem gereksinimleri](/visualstudio/productinfo/vs2017-system-requirements-vs). Yükleyici seçenekleri için ne kadar disk alanı gereklidir bildirir.

### <a name="download-and-install"></a>İndirme ve yükleme

1. Windows için en son Visual Studio 2017 Yükleyicisi'ni indirin.

   > [!div class="nextstepaction"]
   > [Visual Studio 2017 Community'yi yükleyin](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > Topluluk sürümü bireysel geliştiriciler, sınıfta öğrenim ortamı, akademik araştırma ve açık kaynak geliştirme için ' dir. Diğer kullanımlar için yükleme [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) veya [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

1. Yükleyici dosyasını indirdiğiniz ve uygulamayı bulun. Tarayıcınızda görüntülenebilir veya indirilenler klasörünüze fark edebilirsiniz. Yükleyiciyi çalıştırmak için yönetici ayrıcalıkları gerekir. Görebileceğiniz bir **kullanıcı hesabı denetimi** seçin; sisteminize değişiklik kurucusunun izni vermek isteyen bir iletişim **Evet**. Sorun yaşıyorsanız, dosya Gezgini'nde indirilen dosyayı bulmak, yükleyici simgesini sağ tıklatın ve seçin **yönetici olarak çalıştır** bağlam menüsünden.

   ![Visual Studio Yükleyicisi'nin karşıdan yükleyip](media/vscpp-concierge-run-installer.gif "indirip Visual Studio Yükleyicisi'ni yükleyin")

1. Yükleyici belirli geliştirme alanlar için ilgili seçenekleri gruplarıdır iş yüklerinin bir listesini sunar. Podporu iOS Pro C++ artık varsayılan olarak yüklü değildir isteğe bağlı iş yüklerinin parçasıdır.

   ![C++ iş yükünde ile masaüstü geliştirme](media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

   C++ için seçin **C++ ile masaüstü geliştirme** iş yükü ve ardından **yükleme**.

   ![Masaüstü uygulama geliştirme ile C++ iş yükünü yükleyin](media/vscpp-concierge-choose-workload.gif "Masaüstü uygulama geliştirme ile C++ iş yükünü yükleyin.")

1. Yükleme tamamlandığında seçin **başlatma** Visual Studio'yu başlatmak için düğme.

   Visual Studio'yu çalıştırdığınız ilk kez bir Microsoft Account oturum istenir. Yoksa, bir ücretsiz oluşturabilirsiniz. Ayrıca, bir tema seçmeniz gerekir. Endişelenmeyin, isterseniz, daha sonra değiştirebilirsiniz.

   Birçok Visual Studio sürebilir hazır hale getirmek için dakika, onu çalıştırdığınız ilk kez kullanın. İşte bu şekilde bir hızlı atlamalı görünür:

   ![Visual Studio 2017 oturum](media/vscpp-quickstart-first-run.gif "Visual Studio 2017 oturum açın")

   Yeniden çalıştırdığınızda visual Studio çok daha hızlı başlatılır.

1. Visual Studio açıldığında başlık çubuğunda bayrak simgesine vurgulanır denetleyin:

   ![Visual Studio 2017 bildirim bayrağı](media/vscpp-first-start-page-flag.png "Visual Studio 2017 bildirim bayrağı")

   Vurgulanır, açmak için seçmeniz **bildirimleri** penceresi. Visual Studio için kullanılabilen herhangi bir güncelleştirme varsa, artık yüklemeniz kesinlikle önerilir. Yükleme tamamlandıktan sonra Visual Studio'yu yeniden başlatın.

::: moniker-end

::: moniker range="<vs-2017"

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015 yüklemesi

Visual Studio 2015'i yüklemek için Git [Visual Studio'nun eski sürümlerini indirin](https://www.visualstudio.com/vs/older-downloads/). Kurulum programını çalıştırın ve seçin **özel yükleme** C++ bileşeni seçin. Mevcut bir Visual Studio 2015 yüklemesini C++ desteği eklemek için Windows Başlat düğmesini türü tıklayın ve **Program Ekle/Kaldır**. Sonuç listesinden programını açın ve ardından Visual Studio 2015 yüklemenizi yüklü programlar listesinde bulun. Çift tıklayın ve ardından **Değiştir** ve yüklemek için Visual C++ bileşenleri seçin.

Genel olarak, Visual Studio 2015 derleyici kullanarak kodunuzu derlemek için ihtiyacınız olsa bile, Visual Studio 2017 kullanmanızı öneririz. Daha fazla bilgi için [yerel çoklu sürüm desteğinin Visual Studio'da eski projeleri oluşturmak için kullanmak](../porting/use-native-multi-targeting.md).

::: moniker-end

Visual Studio çalışırken, sonraki adıma devam etmek hazırsınız demektir.

## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [C++ projesi oluşturma](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
