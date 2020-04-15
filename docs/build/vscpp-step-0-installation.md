---
title: Visual Studio’ya C++ desteği yükleme
description: Visual C++ için Visual Studio desteği yükleyin
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

Visual Studio ve Visual C++ araçlarını henüz indirmediyseniz ve yüklemediyseniz, şu şekilde başlayın.

::: moniker range="vs-2019"

## <a name="visual-studio-2019-installation"></a>Visual Studio 2019 Kurulumu

Visual Studio 2019'a Hoş Geldiniz! Bu sürümde, yalnızca ihtiyacınız olan özellikleri seçmek ve yüklemek kolaydır. Ve azaltılmış minimum ayak izi nedeniyle, hızlı ve daha az sistem etkisi ile yükler.

> [!NOTE]
> Bu konu, Visual Studio'nun Windows'a yüklenmesi için geçerlidir. [Visual Studio Code,](https://code.visualstudio.com/) Windows, Mac ve Linux sistemlerinde çalışan hafif, platformlar arası bir geliştirme ortamıdır. Visual Studio Code uzantısı için Microsoft [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) IntelliSense, hata ayıklama, kod biçimlendirme, otomatik tamamlama destekler. Mac için Visual Studio Microsoft C++'ı desteklemez, ancak .NET dillerini ve platformlar arası geliştirmeyi destekler. Yükleme yönergeleri [için, Mac için Visual Studio Yükle'ye](/visualstudio/mac/installation/)bakın.

Bu sürümde yeni ne hakkında daha fazla şey öğrenmek ister misiniz? Visual Studio [sürüm notlarına](/visualstudio/releases/2019/release-notes/)bakın.

Yüklemeye hazır mısınız? Adım adım sana yol bulacağız.

### <a name="step-1---make-sure-your-computer-is-ready-for-visual-studio"></a>Adım 1 - Bilgisayarınızın Visual Studio için hazır olduğundan emin olun

Visual Studio'u yüklemeye başlamadan önce:

1. Sistem [gereksinimlerini](/visualstudio/releases/2019/system-requirements)kontrol edin. Bu gereksinimler, bilgisayarınızın Visual Studio 2019'u destekleyip desteklemediğini anlamanıza yardımcı olur.

1. En son Windows güncelleştirmelerini uygulayın. Bu güncelleştirmeler, bilgisayarınızın Visual Studio için hem en son güvenlik güncelleştirmeleri hem de gerekli sistem bileşenlerine sahip olmasını sağlar.

1. Yeni -den başlatma. Yeniden başlatma, bekleyen yüklemelerin veya güncelleştirmelerin Visual Studio yüklemesini engellememesini sağlar.

1. Yer aç. Disk Temizleme uygulamasını çalıştırarak gereksiz dosyaları ve uygulamaları %SystemDrive%'inizden kaldırın.

Visual Studio 2019 ile Visual Studio'nun önceki sürümlerini yan yana çalıştırmakla ilgili sorularınız için [Visual Studio 2019 Platform Hedefleme ve Uyumluluk](/visualstudio/releases/2019/compatibility/) sayfasına bakın.

### <a name="step-2---download-visual-studio"></a>Adım 2 - Visual Studio İndir

Sonra, Visual Studio bootstrapper dosyasını indirin. Bunu yapmak için aşağıdaki düğmeyi seçin, Istediğiniz Visual Studio sürümünü seçin, **Kaydet'i**seçin ve ardından **Klasörü Aç'ı**seçin.

 > [!div class="button"]
 > [Visual Studio’yu İndir](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+rc)

### <a name="step-3---install-the-visual-studio-installer"></a>Adım 3 - Visual Studio yükleyicisini yükleyin

Visual Studio Installer'ı yüklemek için bootstrapper dosyasını çalıştırın. Bu yeni hafif yükleyici, Visual Studio'yı yüklemek ve özelleştirmek için ihtiyacınız olan her şeyi içerir.

1. **İndirilenler** klasörünüzden, aşağıdaki dosyalarla eşleşen veya benzer olan bootstrapper'ı çift tıklatın:

   - Visual Studio Community için **vs_community.exe**
   - Visual Studio Professional için **vs_professional.exe**
   - Visual Studio Enterprise için **vs_enterprise.exe**

   Bir Kullanıcı Hesabı Denetimi bildirimi **alırsanız, Evet'i**seçin.

1. Microsoft [Lisans Koşullarını](https://visualstudio.microsoft.com/license-terms/) ve Microsoft [Gizlilik Bildirimi'ni](https://privacy.microsoft.com/privacystatement)kabul etmenizi isteriz. **Devam**'ı seçin.

### <a name="step-4---choose-workloads"></a>Adım 4 - İş yüklerini seçin

Yükleyici yüklendikten sonra, istediğiniz *iş yüklerini*veya özellik kümelerini seçerek yüklemenizi özelleştirmek için kullanabilirsiniz. Aşağıdaki adımları uygulayın:

1. **Yükleme Visual Studio** ekranında istediğiniz iş yükünü bulun.

   ![Visual Studio 2019: İş yükü yükleyin](../get-started/media/vs-installer-workloads.png)

   Çekirdek C++ desteği için "C++'lı masaüstü geliştirme" iş yükünü seçin. 20'den fazla dil için temel kod düzenleme desteği, proje gerektirmeden herhangi bir klasörden kod açma ve düzenleme olanağı ve tümleşik kaynak kodu denetimi içeren varsayılan çekirdek düzenleyicisi ile birlikte gelir.

   Ek iş yükleri diğer C++ geliştirme türlerini destekler. Örneğin, Microsoft Mağazası için Windows Çalışma Zamanı'nı kullanan uygulamalar oluşturmak için "Evrensel Windows Platformu geliştirme" iş yükünü seçin. DirectX, Unreal ve Cocos2d kullanan oyunlar oluşturmak için "C++'lı oyun geliştirme"yi seçin. IoT geliştirme de dahil olmak üzere Linux platformlarını hedeflemek için "C++'lı Linux geliştirme"yi seçin.

   **Yükleme ayrıntıları** bölmesi, her iş yükü tarafından yüklenen dahil edilen ve isteğe bağlı bileşenleri listeler. Bu listede isteğe bağlı bileşenleri seçebilir veya listeden seçebilirsiniz. Örneğin, Visual Studio 2017 veya 2015 derleyici araç kümelerini kullanarak geliştirmeyi desteklemek için MSVC v141 veya MSVC v140 isteğe bağlı bileşenleri ni seçin. MFC, deneysel Modüller dil uzantısı, InCrediBuild ve daha fazlası için destek ekleyebilirsiniz.

1. İstediğiniz iş yükü(ler) ve isteğe bağlı bileşenleri seçtikten sonra **Yükle'yi**seçin.

   Ardından, Visual Studio yüklemenizin ilerlemesini gösteren durum ekranları görüntülenir.

> [!TIP]
> Yüklemeden sonra istediğiniz zaman, başlangıçta yüklemediğiniz iş yüklerini veya bileşenleri yükleyebilirsiniz. Visual Studio açıksa, **Araçlar** > **Al Araçları ve Özellikleri...** Veya Başlat menüsünden **Visual Studio Installer'ı** açın. Buradan, yüklemek istediğiniz iş yüklerini veya bileşenleri seçebilirsiniz. Ardından **Değiştir'i**seçin.

### <a name="step-5---choose-individual-components-optional"></a>Adım 5 - Tek tek bileşenleri seçin (İsteğe bağlı)

Visual Studio yüklemenizi özelleştirmek için İş Yükleri özelliğini kullanmak istemiyorsanız veya iş yükü yüklemelerinden daha fazla bileşen eklemek istiyorsanız, bunu **Tek tek bileşenler** sekmesinden tek tek bileşenleri yükleyerek veya ekleyerek yapabilirsiniz.

  ![Visual Studio 2019 - Tek tek bileşenleri yükleyin](../get-started/media/vs-installer-individual-components.png "Visual Studio'ya tek tek bileşenleri yükleyin")

### <a name="step-6---install-language-packs-optional"></a>Adım 6 - Dil paketlerini yükleyin (İsteğe bağlı)

Varsayılan olarak, yükleyici programı ilk kez çalıştığında işletim sisteminin dilini eşleştirmeye çalışır. Visual Studio'yu seçtiğiniz bir dilde yüklemek için Visual Studio Installer'dan **Dil paketleri** sekmesini seçin ve ardından istemleri izleyin.

  ![Visual Studio 2019 - Dil paketlerini yükleyin](../get-started/media/vs-installer-language-packs.png "Visual Studio dil paketlerini yükleyin")

#### <a name="change-the-installer-language-from-the-command-line"></a>Yükleyici dilini komut satırından değiştirme

Varsayılan dili değiştirmenin başka bir yolu da yükleyiciyi komut satırından çalıştırmaktır. Örneğin, aşağıdaki komutu kullanarak yükleyiciyi İngilizce olarak çalıştırmaya zorlayabilirsiniz: `vs_installer.exe --locale en-US`. Yükleyici, bir sonraki çalıştırıldığında bu ayarı hatırlar. Yükleyici aşağıdaki dil belirteçlerini destekler: zh-cn, zh-tw, cs-cz, en-us, es-es, fr-fr, de-de, it-it, ja-jp, ko-kr, pl-pl, pt-br, ru-ru ve tr-tr.

### <a name="step-7---change-the-installation-location-optional"></a>Adım 7 - Yükleme konumunu değiştirme (İsteğe bağlı)

Visual Studio'nun sistem sürücünüzdeki kurulum ayak izini azaltabilirsiniz. İndirme önbelleğini, paylaşılan bileşenleri, SDK'ları ve araçları farklı sürücülere taşımayı seçebilir ve Visual Studio'yu en hızlı çalıştıran sürücüde tutabilirsiniz.

  ![Visual Studio 2019 - Kurulum konumlarını değiştir](../get-started/media/vs-installer-installation-locations.png "Yükleme konumunu değiştirme")

> [!IMPORTANT]
> Farklı bir sürücüyü yalnızca Visual Studio'yı ilk yüklediğinizde seçebilirsiniz. Zaten yüklediyseniz ve sürücüleri değiştirmek istiyorsanız, Visual Studio'yı kaldırmanız ve sonra yeniden yüklemeniz gerekir.

### <a name="step-8---start-developing"></a>Adım 8 - Geliştirmeye başlayın

1. Visual Studio yüklemesi tamamlandıktan sonra Visual Studio ile geliştirmeye başlamak için **Başlat** düğmesini seçin.

1. Başlangıç penceresinde yeni **bir proje oluştur'u**seçin.

1. Arama kutusuna, kullanılabilir şablonların listesini görmek için oluşturmak istediğiniz uygulama türünü girin. Şablonlar listesi, yükleme sırasında seçtiğiniz iş yüküne bağlıdır. Farklı şablonları görmek için farklı iş yüklerini seçin.

   **Ayrıca, Dil** açılır listesini kullanarak belirli bir programlama dili için aramanıza filtre uygulayabilirsiniz. **Platform** listesini ve **Proje türü** listesini de kullanarak filtre uygulayabilirsiniz.

1. Visual Studio yeni projenizi açıyor ve kodlamaya hazırsınız!

::: moniker-end

::: moniker range="<=vs-2017"

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017 Kurulumu

Visual Studio 2017'de sadece ihtiyacınız olan özellikleri seçmek ve yüklemek çok kolay. Ve azaltılmış minimum ayak izi nedeniyle, hızlı ve daha az sistem etkisi ile yükler.

### <a name="prerequisites"></a>Ön koşullar

- Geniş bant internet bağlantısı. Visual Studio yükleyicisi birkaç gigabayt lık veri indirebilir.

- Microsoft Windows 7 veya sonraki sürümleri çalıştıran bir bilgisayar. En iyi geliştirme deneyimi için Windows 10'u öneririz. Visual Studio'yu yüklemeden önce sisteminize en son güncellemelerin uygulandığından emin olun.

- Yeterli boş disk alanı. Visual Studio en az 7 GB disk alanı gerektirir ve birçok ortak seçenek yüklenirse 50 GB veya daha fazla sürebilir. C: sürücünüze yüklemenizi öneririz.

Disk alanı ve işletim sistemi gereksinimleri hakkında ayrıntılı bilgi için [Visual Studio Ürün Aile Sistemi Gereksinimleri'ne](/visualstudio/productinfo/vs2017-system-requirements-vs)bakın. Yükleyici, seçtiğiniz seçenekler için ne kadar disk alanı gerektiğini bildirir.

### <a name="download-and-install"></a>İndirme ve yükleme

1. Windows için en son Visual Studio 2017 yükleyicisini indirin.

   > [!div class="nextstepaction"]
   > [Visual Studio 2017 Topluluğu'nu Yükleyin](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > Topluluk sürümü bireysel geliştiriciler, sınıf öğrenimi, akademik araştırma ve açık kaynak geliştirme içindir. Diğer kullanımlar için [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) veya Visual Studio [2017 Enterprise'ı](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)yükleyin.

1. İndirdiğiniz yükleyici dosyasını bulun ve çalıştırın. Tarayıcınızda görüntülenebilir veya İndirilenler klasörünüzde bulabilirsiniz. Yükleyicinin çalışması için Yönetici ayrıcalıklarına ihtiyacı vardır. Yükleyicinin sisteminizde değişiklik yapmasına izin vermenizi isteyen bir **Kullanıcı Hesabı Denetimi** iletişim kutusu görebilirsiniz; **Evet'i**seçin. Sorun yaşıyorsanız, Dosya Gezgini'nde indirilen dosyayı bulun, yükleyici simgesine sağ tıklayın ve bağlam menüsünden **Yönetici Olarak Çalıştır'ı** seçin.

   ![Visual Studio Yükleyicisini indirin ve kurun](media/vscpp-concierge-run-installer.gif "Visual Studio Yükleyicisini indirin ve kurun")

1. Yükleyici, belirli geliştirme alanları için ilgili seçenek grupları olan iş yüklerinin bir listesini sunar. C++ desteği artık varsayılan olarak yüklenmemiş isteğe bağlı iş yüklerinin bir parçasıdır.

   ![C++ iş yüküile masaüstü geliştirme](media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

   C++ için C++ iş **yüküne sahip Masaüstü geliştirmesini** seçin ve ardından **Yükle'yi**seçin.

   ![C++ iş yüküyle Masaüstü geliştirmeyi yükleme](media/vscpp-concierge-choose-workload.gif "C++ iş yüküyle Masaüstü geliştirmeyi yükleme")

1. Yükleme tamamlandığında, Visual Studio'yu başlatmak için **Başlat** düğmesini seçin.

   Visual Studio'yu ilk çalıştırdığınızda, bir Microsoft Hesabı ile oturum açmanız istenir. Eğer yoksa, ücretsiz bir oluşturabilirsiniz. Ayrıca bir tema seçmelisiniz. Merak etme, istersen daha sonra değiştirebilirsin.

   Visual Studio'yu ilk çalıştırdığınızda kullanıma hazır hale getirmek birkaç dakika sürebilir. Hızlı bir zaman atlamalı olarak şu şekilde görünür:

   ![Visual Studio 2017 oturum açma](media/vscpp-quickstart-first-run.gif "Visual Studio 2017 oturum açma")

   Visual Studio yeniden çalıştırdığınızda çok daha hızlı başlar.

1. Visual Studio açıldığında, başlık çubuğundaki bayrak simgesinin vurgulanmış olup olmadığını kontrol edin:

   ![Visual Studio 2017 bildirim bayrağı](media/vscpp-first-start-page-flag.png "Visual Studio 2017 bildirim bayrağı")

   Vurgulanmışsa, **Bildirimler** penceresini açmak için onu seçin. Visual Studio için herhangi bir güncelleme varsa, bunları şimdi yüklemenizi öneririz. Yükleme tamamlandıktan sonra Visual Studio'yu yeniden başlatın.

::: moniker-end

::: moniker range="<vs-2017"

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015 Kurulumu

Visual Studio 2015'i yüklemek için [Visual Studio'nun eski sürümlerini indirin.](https://www.visualstudio.com/vs/older-downloads/) Kurulum programını çalıştırın ve **Özel yüklemeyi** seçin ve ardından C++ bileşenini seçin. Varolan visual studio 2015 yüklemesine C++ desteği eklemek için Windows Başlat düğmesine tıklayın ve **Programları Kaldır'ı ekle**yazın. Programı sonuç listesinden açın ve Visual Studio 2015 yüklemenizi yüklü programlar listesinde bulun. Çift tıklatın, ardından **Değiştir'i** seçin ve yüklemek için Visual C++ bileşenlerini seçin.

Genel olarak, Visual Studio 2015 derleyicisini kullanarak kodunuzu derlemeniz gerekse bile Visual Studio 2017'yi kullanmanızı öneririz. Daha fazla bilgi için [bkz.](../porting/use-native-multi-targeting.md)

::: moniker-end

Visual Studio çalışırken, bir sonraki adıma devam etmeye hazırsınız.

## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [C++ projesi oluşturma](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
