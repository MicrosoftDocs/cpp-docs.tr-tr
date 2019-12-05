---
title: Visual Studio’ya C++ desteği yükleme
description: Visual Studio için Visual Studio desteğini yüklerC++
ms.custom: mvc
ms.date: 04/02/2019
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: a20a2432cbf8c4dc5f211f6f483c0084888f1199
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857170"
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio’ya C++ desteği yükleme

Visual Studio 'Yu ve görsel C++ araçları henüz indirmediyseniz, şu şekilde çalışmaya başlayın.

::: moniker range="vs-2019"

## <a name="visual-studio-2019-installation"></a>Visual Studio 2019 yüklemesi

Visual Studio 2019 'e hoş geldiniz! Bu sürümde, yalnızca ihtiyacınız olan özellikleri seçmek ve yüklemek çok kolay. En düşük minimum kaplama nedeniyle, hızlı bir şekilde ve daha az sistem etkisinden yüklenir.

> [!NOTE]
> Bu konu, Windows üzerinde Visual Studio yüklemesi için geçerlidir. [Visual Studio Code](https://code.visualstudio.com/) , Windows, Mac ve Linux sistemlerinde çalışan hafif, platformlar arası bir geliştirme ortamıdır. Visual Studio Code uzantısı Microsoft [CC++ /for](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) The IntelliSense, hata ayıklama, kod biçimlendirme ve otomatik tamamlamayı destekler. Mac için Visual Studio, Microsoft C++'u desteklemez, ancak .net dillerini ve platformlar arası geliştirmeyi destekler. Yükleme yönergeleri için bkz. [yükleme Mac için Visual Studio](/visualstudio/mac/installation/).

Else bu sürümdeki yenilikler hakkında daha fazla bilgi edinmek istiyorsunuz? Bkz. Visual Studio [sürüm notları](/visualstudio/releases/2019/release-notes/).

Yüklenmeye hazır? Biz, bunu, adım adım konusunda rehberlik edelim.

### <a name="step-1---make-sure-your-computer-is-ready-for-visual-studio"></a>1\. adım: bilgisayarınızın Visual Studio'ya hazır olduğundan emin olun

Visual Studio yükleme başlamadan önce:

1. Denetleme [sistem gereksinimleri](/visualstudio/releases/2019/system-requirements). Bu gereksinimler, bilgisayarınızın Visual Studio 2019 ' i destekleyip desteklemediğini bilmenizi sağlamaya yardımcı olur.

1. En son Windows güncelleştirmelerini uygulayın. Bu güncelleştirmeler, bilgisayarınızda Visual Studio için en son güvenlik güncelleştirmelerini hem gerekli sistem bileşenlerine sahip olun.

1. Yeniden başlatma. Yeniden başlatma bekleyen yükleme veya güncelleştirmelerin Visual Studio yüklemesini engellememesini sağlar.

1. Alan boşaltın. Gereksiz dosyaları ve uygulamalar, % SYSTEMDRIVE %, örneğin, Disk Temizleme uygulamayı çalıştıran kaldırın.

Visual Studio 'nun önceki sürümlerini Visual Studio 2019 ile yan yana çalıştırma hakkında sorularınız için [Visual studio 2019 Platform hedefleme ve uyumluluk](/visualstudio/releases/2019/compatibility/) sayfasına bakın.

### <a name="step-2---download-visual-studio"></a>Adım 2 - Visual Studio indirme

Ardından, Visual Studio önyükleyicisi dosyasını indirin. Bunu yapmak için, aşağıdaki düğmeyi seçin, istediğiniz Visual Studio sürümünü seçin, **Kaydet**' i seçin ve sonra **klasörü aç**' ı seçin.

 > [!div class="button"]
 > [Visual Studio 'Yu indirin](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+rc)

### <a name="step-3---install-the-visual-studio-installer"></a>3\. adım - Visual Studio Yükleyicisi'ni yükleme

Visual Studio Yükleyicisi yüklemek için önyükleyici dosyasını çalıştırın. Bu yeni basit yükleyici, Visual Studio 'Yu yüklemek ve özelleştirmek için ihtiyacınız olan her şeyi içerir.

1. Öğesinden, **indirir** klasöründe eşleşen veya benzer bir aşağıdaki dosyalar önyükleyici çift tıklayın:

   * **vs_community.exe** Visual Studio Community için
   * **vs_professional.exe** Visual Studio Professional
   * **vs_enterprise.exe** için Visual Studio Enterprise

   Bir kullanıcı hesabı denetimi bildirimi alırsanız **Evet**' i seçin.

1. Microsoft onaylamak için isteriz [lisans koşulları](https://visualstudio.microsoft.com/license-terms/) ve Microsoft [gizlilik bildirimi](https://privacy.microsoft.com/privacystatement). Seçin **devam**.

### <a name="step-4---choose-workloads"></a>4\. adım-iş yüklerini seçin

Yükleyici yüklendikten sonra, istediğiniz *iş yüklerini*veya özellik kümelerini seçerek yüklemenizi özelleştirmek için kullanabilirsiniz. İşte nasıl.

1. Bulmak istediğiniz iş yükünü **Visual Studio'yu** ekran.

   ![Visual Studio 2019: iş yükü yüklemesi](../get-started/media/vs-installer-workloads.png)

   Temel C++ destek için "ile C++masaüstü geliştirme" iş yükünü seçin. Bu, temel kod düzenleme açın ve projeye gerek kalmadan herhangi bir klasörden kodu düzenleme olanağı 20'den dil için destek içerir ve tümleşik kaynak kod denetimi varsayılan çekirdek Düzenleyicisi ile birlikte gelir.

   Ek iş yükleri diğer C++ geliştirme türlerini destekler. Örneğin, Microsoft Store için Windows Çalışma Zamanı kullanan uygulamalar oluşturmak için "Evrensel Windows Platformu geliştirme" iş yükünü seçin. DirectX, Unreal ve C++Cocos2d kullanan oyunlar oluşturmak Için "oyun ile oyun geliştirme" seçeneğini belirleyin. IoT geliştirme dahil olmak üzere C++Linux platformunu hedeflemek Için "Linux ile geliştirme" seçeneğini belirleyin.

   **Yükleme ayrıntıları** bölmesi, her iş yükü tarafından yüklenen dahil edilen ve isteğe bağlı bileşenleri listeler. Bu listedeki isteğe bağlı bileşenleri seçebilir veya seçimden kaldırabilirsiniz. Örneğin, Visual Studio 2017 veya 2015 derleyici araç kümelerini kullanarak geliştirmeyi desteklemek için MSVC v141 veya MSVC v140 isteğe bağlı bileşenlerini seçin. MFC, deneysel modüller dil uzantısı, IncrediBuild ve daha fazlası için destek ekleyebilirsiniz.

1. İstediğiniz iş yüklerini ve isteğe bağlı bileşenleri seçtikten sonra, **yükler**' i seçin.

    Ardından, durum ekranları, Visual Studio yüklemenizin ilerleme durumunu gösteren görünür.

> [!TIP]
> Yüklemeden sonra herhangi bir zamanda iş yükleri veya başlangıçta yüklenmedi bileşenleri yükleyebilirsiniz. Visual Studio'nun varsa **Araçları** > **araçları ve özellikleri Al...**  Visual Studio yükleyicisi açılır. Veya açık **Visual Studio yükleyicisi** Başlat menüsünden. Buradan, yüklemek istediğiniz iş yüklerini veya bileşenleri seçebilirsiniz. Ardından **Değiştir**' i seçin.

### <a name="step-5---choose-individual-components-optional"></a>5\. adım-tek tek bileşenleri seçin (Isteğe bağlı)

Visual Studio yüklemenizi özelleştirmek için Iş yükleri özelliğini kullanmak istemiyorsanız veya bir iş yükü yüklemesinden daha fazla bileşen eklemek istiyorsanız, **tek** tek bileşenler sekmesinden tek tek bileşenleri yükleyerek veya ekleyerek bunu yapabilirsiniz. istediğinizi seçin ve ardından istemleri takip edin.

  ![Visual Studio 2019-ayrı bileşenleri yükler](../get-started/media/vs-installer-individual-components.png "Visual Studio bireysel bileşenlerini yükler")

### <a name="step-6---install-language-packs-optional"></a>6\. adım - yükleme dil paketleri (isteğe bağlı)

Varsayılan olarak, yükleyici programı ilk kez çalıştığında işletim sisteminin dilini eşleştirmeye çalışır. Visual Studio 'Yu seçtiğiniz bir dilde yüklemek için Visual Studio Yükleyicisi **dil paketleri** sekmesini seçin ve ardından istemleri izleyin.

  ![Visual Studio 2019-dil paketlerini yükler](../get-started/media/vs-installer-language-packs.png "Visual Studio dil paketlerini yükler")

#### <a name="change-the-installer-language-from-the-command-line"></a>Komut satırından yükleyici dilini değiştirme

Varsayılan dilini değiştirme başka bir komut satırından yükleyiciyi çalıştırarak yoludur. Örneğin, aşağıdaki komutu kullanarak İngilizce olarak çalıştırmak için yükleyici zorlayabilirsiniz: `vs_installer.exe --locale en-US`. Yükleyici bir sonraki sefer çalıştırıldığında bu ayarı anımsayacaktır. Aşağıdaki Dil belirteçler yükleyici destekler: zh-cn, zh-tw, cs-cz, en-us, es-es, fr-fr, de-de, it-IT, ja-jp, ko-kr, pl-pl, pt-br, ru-ru ve tr-tr.

### <a name="step-7---change-the-installation-location-optional"></a>7\. adım - (isteğe bağlı) yükleme konumunu değiştirme

Visual Studio 'nun yükleme ayak izini sistem sürücünüzde azaltabilirsiniz. İndirme önbelleğini, paylaşılan bileşenler, SDK'ları ve araçları farklı sürücülere taşıma ve Visual Studio en hızlı çalışan sürücüde korumak seçebilirsiniz.

  ![Visual Studio 2019-yükleme konumlarını değiştirme](../get-started/media/vs-installer-installation-locations.png "Yükleme konumunu değiştirme")

> [!IMPORTANT]
> Yalnızca Visual Studio 'Yu ilk kez yüklediğinizde, farklı bir sürücü seçebilirsiniz. Zaten yüklediyseniz ve sürücüleri değiştirmek istiyorsanız, Visual Studio 'Yu kaldırmalı ve ardından yeniden yüklemeniz gerekir.

### <a name="step-8---start-developing"></a>8\. adım - geliştirmeye başlayın

1. Visual Studio yüklemesi tamamlandıktan sonra, Visual Studio ile geliştirmeye başlamak için **Başlat** düğmesini seçin.

1. Başlangıç penceresinde **Yeni proje oluştur**' u seçin.

1. Arama kutusuna, kullanılabilir şablonların listesini görmek için oluşturmak istediğiniz uygulamanın türünü girin. Şablon listesi, yükleme sırasında seçtiğiniz iş yüküne bağlıdır. Farklı şablonları görmek için farklı iş yükleri seçin.

   Ayrıca, **dil** açılan listesini kullanarak, aramanızı belirli bir programlama diline göre filtreleyebilirsiniz. **Platform** listesini ve **Proje türü** listesini kullanarak filtre uygulayabilirsiniz.

1. Visual Studio yeni projenizi açar ve kodlamaya hazırsınız!

::: moniker-end

::: moniker range="<=vs-2017"

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017 yüklemesi

Visual Studio 2017 ' de, yalnızca ihtiyacınız olan özellikleri kolayca seçebilir ve yükleyebilirsiniz. En düşük minimum kaplama nedeniyle, hızlı bir şekilde ve daha az sistem etkisinden yüklenir.

### <a name="prerequisites"></a>Prerequisites

- Geniş bant internet bağlantısı. Visual Studio yükleyicisi birkaç gigabayt veri indirebilir.

- Microsoft Windows 7 veya sonraki sürümlerini çalıştıran bir bilgisayar. En iyi geliştirme deneyimi için Windows 10 ' un kullanılması önerilir. Visual Studio 'Yu yüklemeden önce en son güncelleştirmelerin sisteminize uygulandığından emin olun.

- Yeterli boş disk alanı. Visual Studio için en az 7 GB disk alanı gerekir ve birçok ortak seçenek yüklüyse 50 GB veya daha fazla sürebilir. Bunu C: sürücünüze yüklemenizi öneririz.

Disk alanı ve işletim sistemi gereksinimleriyle ilgili ayrıntılı bilgi için bkz. [Visual Studio ürün ailesi sistem gereksinimleri](/visualstudio/productinfo/vs2017-system-requirements-vs). Yükleyici, seçtiğiniz seçenekler için ne kadar disk alanı gerektiğini bildirir.

### <a name="download-and-install"></a>İndirme ve yükleme

1. Windows için en son Visual Studio 2017 yükleyicisini indirin.

   > [!div class="nextstepaction"]
   > [Visual Studio 2017 Community'yi yükleyin](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > Topluluk sürümü bireysel geliştiriciler, sınıfta öğrenim ortamı, akademik araştırma ve açık kaynak geliştirme için ' dir. Diğer kullanımlar için yükleme [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) veya [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

1. İndirdiğiniz yükleyici dosyasını bulun ve çalıştırın. Bu, tarayıcınızda görüntülenebilir veya Indirmeler klasörünüzde bulunabilir. Yükleyicinin çalışması için yönetici ayrıcalıklarına ihtiyacı vardır. Yükleyicinin sisteminizde değişiklik yapmasına izin vermenizi isteyen bir **Kullanıcı hesabı denetimi** iletişim kutusu görebilirsiniz; **Evet**' i seçin. Sorun yaşıyorsanız, dosya Gezgini 'nde indirilen dosyayı bulun, yükleyici simgesine sağ tıklayın ve bağlam menüsünde **yönetici olarak çalıştır** ' ı seçin.

   ![Visual Studio Yükleyicisi indirin ve yükleyin](media/vscpp-concierge-run-installer.gif "Visual Studio Yükleyicisi indirin ve yükleyin")

1. Yükleyici belirli geliştirme alanlar için ilgili seçenekleri gruplarıdır iş yüklerinin bir listesini sunar. C++ Desteği artık varsayılan olarak yüklenmeyen isteğe bağlı iş yüklerinin bir parçasıdır.

   ![İş yükü ile C++ masaüstü geliştirme](media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

   İçin C++, iş yüküyle **Masaüstü geliştirmeyi C++**  seçin ve ardından **Install**' ı seçin.

   ![C++ İş yüküyle masaüstü geliştirmeyi yükler](media/vscpp-concierge-choose-workload.gif "C++ İş yüküyle masaüstü geliştirmeyi yükler")

1. Yükleme tamamlandığında, Visual Studio 'Yu başlatmak için **Başlat** düğmesini seçin.

   Visual Studio 'Yu ilk kez çalıştırdığınızda bir Microsoft hesabı ile oturum açmanız istenir. Bir tane yoksa, ücretsiz olarak oluşturabilirsiniz. Ayrıca bir tema seçmeniz gerekir. Endişelenmeyin, isterseniz daha sonra değiştirebilirsiniz.

   Bu işlem, Visual Studio 'Yu ilk kez çalıştırdığınızda kullanıma hazırlamak için birkaç dakika sürebilir. Hızlı bir zaman atlamalı şekilde şöyle görünür:

   ![Visual Studio 2017 oturum açma](media/vscpp-quickstart-first-run.gif "Visual Studio 2017 oturum açma")

   Visual Studio, tekrar çalıştırdığınızda daha hızlı başlar.

1. Visual Studio açıldığında, başlık çubuğundaki bayrak simgesinin vurgulandığını kontrol edin:

   ![Visual Studio 2017 bildirim bayrağı](media/vscpp-first-start-page-flag.png "Visual Studio 2017 bildirim bayrağı")

   Vurgulandığında, **Bildirimler** penceresini açmak için seçin. Visual Studio için kullanılabilen güncelleştirmeler varsa, bunları şimdi yüklemenizi öneririz. Yükleme tamamlandıktan sonra Visual Studio 'Yu yeniden başlatın.

::: moniker-end

::: moniker range="<vs-2017"

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015 yüklemesi

Visual Studio 2015 ' i yüklemek için [Visual Studio 'nun eski sürümlerini indirme](https://www.visualstudio.com/vs/older-downloads/)bölümüne gidin. Kurulum programını çalıştırın ve **özel yükleme** ' yi seçin ve ardından C++ bileşeni seçin. Mevcut bir C++ Visual Studio 2015 yüklemesine destek eklemek Için Windows Başlat düğmesine tıklayın ve **Program Ekle Kaldır**yazın. Program sonuçlar listesinden açın ve ardından yüklü programlar listesinde Visual Studio 2015 yüklemenizi bulun. Çift tıklayın, ardından **Değiştir** ' i seçin ve yüklenecek görsel C++ bileşenleri seçin.

Genel olarak, Visual Studio 2015 derleyicisini kullanarak kodunuzun derlenmesi gerekebilse bile Visual Studio 2017 ' i kullanmanızı kesinlikle öneririz. Daha fazla bilgi için [yerel çoklu sürüm desteğinin Visual Studio'da eski projeleri oluşturmak için kullanmak](../porting/use-native-multi-targeting.md).

::: moniker-end

Visual Studio çalışırken, bir sonraki adıma devam etmek için hazırsınız demektir.

## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [C++ Proje oluşturma](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
