---
title: Visual Studio’ya C++ desteği yükleme
description: Visual C++ için Visual Studio desteğini yükler
ms.custom: mvc
ms.date: 04/02/2019
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: d3018bef9254a8eab557057c035cde84310a2452
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335360"
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio’ya C++ desteği yükleme

Visual Studio 'Yu ve Visual C++ araçlarını henüz indirmediyseniz, şu şekilde çalışmaya başlayın.

::: moniker range="vs-2019"

## <a name="visual-studio-2019-installation"></a>Visual Studio 2019 yüklemesi

Visual Studio 2019 'e hoş geldiniz! Bu sürümde, yalnızca ihtiyacınız olan özellikleri seçmek ve yüklemek çok kolay. En düşük minimum kaplama nedeniyle, hızlı bir şekilde ve daha az sistem etkisinden yüklenir.

> [!NOTE]
> Bu konu, Windows üzerinde Visual Studio yüklemesi için geçerlidir. [Visual Studio Code](https://code.visualstudio.com/) , Windows, Mac ve Linux sistemlerinde çalışan hafif, platformlar arası bir geliştirme ortamıdır. Visual Studio Code uzantısı [Için Microsoft C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) , IntelliSense, hata ayıklama, kod biçimlendirme ve otomatik tamamlamayı destekler. Mac için Visual Studio, Microsoft C++ desteklemez, ancak .NET dillerini ve platformlar arası geliştirmeyi destekler. Yükleme yönergeleri için bkz. [yükleme Mac için Visual Studio](/visualstudio/mac/installation/).

Bu sürümdeki yenilikler hakkında daha fazla bilgi edinmek istiyor musunuz? Bkz. Visual Studio [sürüm notları](/visualstudio/releases/2019/release-notes/).

Yüklenmeye hazırlanıyor mi? Adım adım size kılavuzluk ederiz.

### <a name="step-1---make-sure-your-computer-is-ready-for-visual-studio"></a>1. adım-bilgisayarınızın Visual Studio için hazırlanmaya çalıştığından emin olun

Visual Studio 'Yu yüklemeye başlamadan önce:

1. [Sistem gereksinimlerini](/visualstudio/releases/2019/system-requirements)denetleyin. Bu gereksinimler, bilgisayarınızın Visual Studio 2019 ' i destekleyip desteklemediğini bilmenizi sağlamaya yardımcı olur.

1. En son Windows güncelleştirmelerini uygulayın. Bu güncelleştirmeler, bilgisayarınızda hem en son güvenlik güncelleştirmelerinin hem de Visual Studio için gerekli sistem bileşenlerinin bulunduğundan emin olun.

1. Makine. Yeniden başlatma, bekleyen yükleme veya güncelleştirmelerin Visual Studio yüklemesini desteklemez.

1. Boş alan açın. % SystemDrive% öğesinden gereksiz dosya ve uygulamaları, örneğin, disk temizleme uygulamasını çalıştırmak için kaldırın.

Visual Studio 'nun önceki sürümlerini Visual Studio 2019 ile yan yana çalıştırma hakkında sorularınız için [Visual studio 2019 Platform hedefleme ve uyumluluk](/visualstudio/releases/2019/compatibility/) sayfasına bakın.

### <a name="step-2---download-visual-studio"></a>2. adım-Visual Studio 'Yu Indirme

Ardından, Visual Studio önyükleyici dosyasını indirin. Bunu yapmak için, aşağıdaki düğmeyi seçin, istediğiniz Visual Studio sürümünü seçin, **Kaydet**' i seçin ve sonra **klasörü aç**' ı seçin.

 > [!div class="button"]
 > [Visual Studio’yu İndir](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+rc)

### <a name="step-3---install-the-visual-studio-installer"></a>3. adım-Visual Studio yükleyicisini yükleme

Visual Studio Yükleyicisi yüklemek için önyükleyici dosyasını çalıştırın. Bu yeni basit yükleyici, Visual Studio 'Yu yüklemek ve özelleştirmek için ihtiyacınız olan her şeyi içerir.

1. **İndirmeler** klasöründen, eşleşen önyükleyiciyi çift tıklayın veya aşağıdaki dosyalardan birine benzer:

   - Visual Studio Community için **vs_community. exe**
   - Visual Studio Professional için **vS_professional. exe**
   - Visual Studio Enterprise için **vs_enterprise. exe**

   Bir kullanıcı hesabı denetimi bildirimi alırsanız **Evet**' i seçin.

1. Microsoft [Lisans koşulları](https://visualstudio.microsoft.com/license-terms/) ' nı ve Microsoft [Gizlilik bildirimi](https://privacy.microsoft.com/privacystatement)' ni kabul etmeniz istenir. **Devam**'ı seçin.

### <a name="step-4---choose-workloads"></a>4. adım-iş yüklerini seçin

Yükleyici yüklendikten sonra, istediğiniz *iş yüklerini*veya özellik kümelerini seçerek yüklemenizi özelleştirmek için kullanabilirsiniz. Aşağıdaki adımları uygulayın:

1. **Visual Studio 'Yu yükleme** ekranında istediğiniz iş yükünü bulun.

   ![Visual Studio 2019: iş yükü yüklemesi](../get-started/media/vs-installer-workloads.png)

   Core C++ desteği için "C++ ile masaüstü geliştirme" iş yükünü seçin. 20 ' den fazla dil için temel kod düzenleme desteğini içeren, bir proje gerektirmeden herhangi bir klasörden kod açma ve düzenleme özelliği ve Tümleşik kaynak kodu denetimi olan varsayılan çekirdek Düzenleyicisi ile gelir.

   Ek iş yükleri diğer C++ geliştirme türlerini destekler. Örneğin, Microsoft Store için Windows Çalışma Zamanı kullanan uygulamalar oluşturmak için "Evrensel Windows Platformu geliştirme" iş yükünü seçin. DirectX, Unreal ve Cocos2d kullanan oyunlar oluşturmak için "C++ ile oyun geliştirme" seçeneğini belirleyin. IoT geliştirme dahil olmak üzere Linux platformunu hedeflemek için "C++ ile Linux geliştirme" seçeneğini belirleyin.

   **Yükleme ayrıntıları** bölmesi, her iş yükü tarafından yüklenen dahil edilen ve isteğe bağlı bileşenleri listeler. Bu listedeki isteğe bağlı bileşenleri seçebilir veya seçimden kaldırabilirsiniz. Örneğin, Visual Studio 2017 veya 2015 derleyici araç kümelerini kullanarak geliştirmeyi desteklemek için MSVC v141 veya MSVC v140 isteğe bağlı bileşenlerini seçin. MFC, deneysel modüller dil uzantısı, IncrediBuild ve daha fazlası için destek ekleyebilirsiniz.

1. İstediğiniz iş yüklerini ve isteğe bağlı bileşenleri seçtikten sonra, **yükler**' i seçin.

   Ardından, Visual Studio yüklemenizin ilerlemesini gösteren durum ekranları görüntülenir.

> [!TIP]
> Yüklemeden sonra dilediğiniz zaman, ilk olarak yüklediğiniz iş yüklerini veya bileşenleri yükleyebilirsiniz. Visual Studio açıksa **Araçlar** > ' a gidin**Araçlar ve Özellikler al...** Visual Studio yükleyicisi açılır. Ya da, Başlat menüsünden **Visual Studio yükleyicisi** açın. Buradan, yüklemek istediğiniz iş yüklerini veya bileşenleri seçebilirsiniz. Ardından **Değiştir**' i seçin.

### <a name="step-5---choose-individual-components-optional"></a>5. adım-tek tek bileşenleri seçin (Isteğe bağlı)

Visual Studio yüklemenizi özelleştirmek için Iş yükleri özelliğini kullanmak istemiyorsanız veya bir iş yükü yüklemesinden daha fazla bileşen eklemek istiyorsanız, **tek** tek bileşenler sekmesinden tek tek bileşenleri yükleyerek veya ekleyerek bunu yapabilirsiniz. istediğinizi seçin ve ardından istemleri takip edin.

  ![Visual Studio 2019-ayrı bileşenleri yükler](../get-started/media/vs-installer-individual-components.png "Visual Studio bireysel bileşenlerini yükler")

### <a name="step-6---install-language-packs-optional"></a>6. adım-dil paketlerini (Isteğe bağlı) yükler

Varsayılan olarak, yükleyici programı ilk kez çalıştırıldığında işletim sisteminin dilini eşleştirmeye çalışır. Visual Studio 'Yu seçtiğiniz bir dilde yüklemek için Visual Studio Yükleyicisi **dil paketleri** sekmesini seçin ve ardından istemleri izleyin.

  ![Visual Studio 2019-dil paketlerini yükler](../get-started/media/vs-installer-language-packs.png "Visual Studio dil paketlerini yükler")

#### <a name="change-the-installer-language-from-the-command-line"></a>Yükleyici dilini komut satırından değiştirme

Varsayılan dili değiştirebilmeniz için, yükleyiciyi komut satırından çalıştırmak sizin için başka bir yoldur. Örneğin, aşağıdaki komutu kullanarak yükleyiciyi Ingilizce olarak çalışmaya zorlayabilirsiniz: `vs_installer.exe --locale en-US`. Yükleyici bir sonraki sefer çalıştırıldığında bu ayarı anımsayacaktır. Yükleyici şu dil belirteçlerini destekler: zh-cn, zh-tw, CS-CZ, en-US, es-es, fr-fr, de-de, IT-it, ja-JP

### <a name="step-7---change-the-installation-location-optional"></a>7. adım-yükleme konumunu değiştirme (Isteğe bağlı)

Visual Studio 'nun yükleme ayak izini sistem sürücünüzde azaltabilirsiniz. İndirme önbelleğini, paylaşılan bileşenleri, SDK 'Ları ve araçları farklı sürücülere taşımayı ve Visual Studio 'Yu en hızlı şekilde çalıştıran sürücüde tutmayı seçebilirsiniz.

  ![Visual Studio 2019-yükleme konumlarını değiştirme](../get-started/media/vs-installer-installation-locations.png "Yükleme konumunu değiştirme")

> [!IMPORTANT]
> Yalnızca Visual Studio 'Yu ilk kez yüklediğinizde, farklı bir sürücü seçebilirsiniz. Zaten yüklediyseniz ve sürücüleri değiştirmek istiyorsanız, Visual Studio 'Yu kaldırmalı ve ardından yeniden yüklemeniz gerekir.

### <a name="step-8---start-developing"></a>8. adım-geliştirmeye başlama

1. Visual Studio yüklemesi tamamlandıktan sonra, Visual Studio ile geliştirmeye başlamak için **Başlat** düğmesini seçin.

1. Başlangıç penceresinde **Yeni proje oluştur**' u seçin.

1. Arama kutusuna, kullanılabilir şablonların listesini görmek için oluşturmak istediğiniz uygulamanın türünü girin. Şablon listesi, yükleme sırasında seçtiğiniz iş yüküne bağlıdır. Farklı şablonları görmek için farklı iş yükleri seçin.

   Ayrıca, **dil** açılan listesini kullanarak, aramanızı belirli bir programlama diline göre filtreleyebilirsiniz. **Platform** listesini ve **Proje türü** listesini kullanarak filtre uygulayabilirsiniz.

1. Visual Studio yeni projenizi açar ve kodlamaya hazırsınız!

::: moniker-end

::: moniker range="<=vs-2017"

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017 yüklemesi

Visual Studio 2017 ' de, yalnızca ihtiyacınız olan özellikleri kolayca seçebilir ve yükleyebilirsiniz. En düşük minimum kaplama nedeniyle, hızlı bir şekilde ve daha az sistem etkisinden yüklenir.

### <a name="prerequisites"></a>Ön koşullar

- Geniş bant internet bağlantısı. Visual Studio yükleyicisi birkaç gigabayt veri indirebilir.

- Microsoft Windows 7 veya sonraki sürümlerini çalıştıran bir bilgisayar. En iyi geliştirme deneyimi için Windows 10 ' un kullanılması önerilir. Visual Studio 'Yu yüklemeden önce en son güncelleştirmelerin sisteminize uygulandığından emin olun.

- Yeterli boş disk alanı. Visual Studio için en az 7 GB disk alanı gerekir ve birçok ortak seçenek yüklüyse 50 GB veya daha fazla sürebilir. Bunu C: sürücünüze yüklemenizi öneririz.

Disk alanı ve işletim sistemi gereksinimleriyle ilgili ayrıntılı bilgi için bkz. [Visual Studio ürün ailesi sistem gereksinimleri](/visualstudio/productinfo/vs2017-system-requirements-vs). Yükleyici, seçtiğiniz seçenekler için ne kadar disk alanı gerektiğini bildirir.

### <a name="download-and-install"></a>İndirme ve yükleme

1. Windows için en son Visual Studio 2017 yükleyicisini indirin.

   > [!div class="nextstepaction"]
   > [Visual Studio 2017 Community 'yi yükler](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > Topluluk sürümü, bireysel geliştiriciler, ders öğrenimi, akademik araştırmalar ve açık kaynak geliştirmesi içindir. Diğer kullanımlar için, [Visual studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) veya [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)'ı yükler.

1. İndirdiğiniz yükleyici dosyasını bulun ve çalıştırın. Bu, tarayıcınızda görüntülenebilir veya Indirmeler klasörünüzde bulunabilir. Yükleyicinin çalışması için yönetici ayrıcalıklarına ihtiyacı vardır. Yükleyicinin sisteminizde değişiklik yapmasına izin vermenizi isteyen bir **Kullanıcı hesabı denetimi** iletişim kutusu görebilirsiniz; **Evet**' i seçin. Sorun yaşıyorsanız, dosya Gezgini 'nde indirilen dosyayı bulun, yükleyici simgesine sağ tıklayın ve bağlam menüsünde **yönetici olarak çalıştır** ' ı seçin.

   ![Visual Studio Yükleyicisi indirin ve yükleyin](media/vscpp-concierge-run-installer.gif "Visual Studio Yükleyicisi indirin ve yükleyin")

1. Yükleyici, belirli bir geliştirme alanı için ilgili seçeneklerin grupları olan iş yüklerinin bir listesini sunar. C++ desteği artık varsayılan olarak yüklenmeyen isteğe bağlı iş yüklerinin bir parçasıdır.

   ![C++ iş yükü ile masaüstü geliştirme](media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

   C++ için C++ iş yüküne **sahip masaüstü geliştirmeyi** seçin ve ardından **Install**' ı seçin.

   ![C++ iş yüküyle masaüstü geliştirmeyi yükler](media/vscpp-concierge-choose-workload.gif "C++ iş yüküyle masaüstü geliştirmeyi yükler")

1. Yükleme tamamlandığında, Visual Studio 'Yu başlatmak için **Başlat** düğmesini seçin.

   Visual Studio 'Yu ilk kez çalıştırdığınızda bir Microsoft hesabı ile oturum açmanız istenir. Microsoft hesabınız yoksa ücretsiz olarak oluşturabilirsiniz. Ayrıca bir tema seçmeniz gerekir. Endişelenmeyin, isterseniz daha sonra değiştirebilirsiniz.

   Bu işlem, Visual Studio 'Yu ilk kez çalıştırdığınızda kullanıma hazırlamak için birkaç dakika sürebilir. Hızlı bir zaman atlamalı şekilde şöyle görünür:

   ![Visual Studio 2017 oturum açma](media/vscpp-quickstart-first-run.gif "Visual Studio 2017 oturum açma")

   Visual Studio, tekrar çalıştırdığınızda daha hızlı başlar.

1. Visual Studio açıldığında, başlık çubuğundaki bayrak simgesinin vurgulandığını kontrol edin:

   ![Visual Studio 2017 bildirim bayrağı](media/vscpp-first-start-page-flag.png "Visual Studio 2017 bildirim bayrağı")

   Vurgulandığında, **Bildirimler** penceresini açmak için seçin. Visual Studio için kullanılabilen güncelleştirmeler varsa, bunları şimdi yüklemenizi öneririz. Yükleme tamamlandıktan sonra Visual Studio 'Yu yeniden başlatın.

::: moniker-end

::: moniker range="<vs-2017"

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015 yüklemesi

Visual Studio 2015 ' i yüklemek için [Visual Studio 'nun eski sürümlerini indirme](https://www.visualstudio.com/vs/older-downloads/)bölümüne gidin. Kurulum programını çalıştırın ve **özel yükleme** ' yi seçin ve ardından C++ bileşenini seçin. Mevcut bir Visual Studio 2015 yüklemesine C++ desteği eklemek için, Windows Başlat düğmesine tıklayın ve **Program Ekle Kaldır**yazın. Program sonuçlar listesinden açın ve ardından yüklü programlar listesinde Visual Studio 2015 yüklemenizi bulun. Çift tıklayın ve ardından **Değiştir** ' i seçin ve yüklenecek Visual C++ bileşenleri ' ni seçin.

Genel olarak, Visual Studio 2015 derleyicisini kullanarak kodunuzun derlenmesi gerekebilse bile Visual Studio 2017 ' i kullanmanızı kesinlikle öneririz. Daha fazla bilgi için bkz. [Eski projeler oluşturmak Için Visual Studio 'da yerel çoklu sürüm kullanımını kullanma](../porting/use-native-multi-targeting.md).

::: moniker-end

Visual Studio çalışırken, bir sonraki adıma devam etmek için hazırsınız demektir.

## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [C++ projesi oluşturma](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
