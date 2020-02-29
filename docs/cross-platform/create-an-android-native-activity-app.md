---
title: Android Yerel Etkinlik Uygulaması Oluşturma
ms.date: 10/17/2019
ms.assetid: 884014b1-5208-45ec-b0da-ad0070d2c24d
ms.openlocfilehash: f588c56acfd5c559e6b0bf1b8635e8b36c69548a
ms.sourcegitcommit: a673f6a54cc97e3d4cd032b10aa8dce7f0539d39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78177450"
---
# <a name="create-an-android-native-activity-app"></a>Android Yerel Etkinlik Uygulaması Oluşturma

Platformlar arası **mobil geliştirme C++**  yükünü iş yüküne yüklediğinizde, Visual Studio tam işlevli Android yerel etkinlik uygulamaları oluşturmak için kullanılabilir. Android yerel geliştirme seti (NDK), saf C/C++ kod kullanarak Android uygulamanızın çoğunluğunu uygulamanıza olanak tanıyan bir araç takımıdır. Bazı Java JNı kodu, C/C++ kodunuzun Android ile etkileşime geçmesini sağlamak için tutkalla işlevi görür. Android NDK, Android API Düzey 9 ile yerel etkinlik uygulamaları oluşturma özelliğini kullanıma sunmuştur. Yerel etkinlik kodu, Unreal Engine veya OpenGL kullanan oyun ve grafik kullanımı yoğun uygulamalar oluşturmak için yaygındır. Bu konu, OpenGL kullanan basit bir yerel etkinlik uygulamasının oluşturulmasında size kılavuzluk eder. Ek konular, yerel etkinlik kodunu düzenlemenin, oluşturmanın, hata ayıklamanın ve dağıtmanın geliştirici yaşam döngüsü boyunca size yol gösterir.

## <a name="requirements"></a>Gereksinimler

Android yerel etkinlik uygulaması oluşturabilmeniz için, tüm sistem gereksinimlerini karşıladığınızdan ve **Mobil geliştirmeyi C++**  Visual Studio 'da iş yüküyle yüklediğinizden emin olmanız gerekir. Daha fazla bilgi için bkz. [ile C++platformlar arası mobil geliştirmeyi çalıştırma ](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md). Yüklemede gerekli olan üçüncü taraf araçların ve SDK 'ların eklendiğinden ve Android öykünücüsünün yüklü olduğundan emin olun.

## <a name="create-a-new-native-activity-project"></a>Yeni bir yerel etkinlik projesi oluştur

Bu öğreticide ilk olarak yeni bir Android yerel etkinlik projesi oluşturup bir Android öykünücüsünde varsayılan uygulamayı derleyip çalıştırmalısınız.

::: moniker range="vs-2017"

1. Visual Studio 'da **dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunda, **Şablonlar**altında **görsel C++**  > **platformlar arası**' ı seçin ve ardından **yerel etkinlik uygulaması (Android)** şablonunu seçin.

1. Uygulamaya *MyAndroidApp*gibi bir ad verin ve ardından **Tamam**' ı seçin.

   ![Yerel etkinlik projesi oluşturma](../cross-platform/media/cppmdd-newproject.png "Yerel etkinlik projesi oluşturma")

   Visual Studio yeni çözümü oluşturur ve Çözüm Gezgini açar.

   ![Çözüm Gezgini yerel etkinlik projesi](../cross-platform/media/cppmdd-rc-na-solutionexp.png "Çözüm Gezgini yerel etkinlik projesi")

::: moniker-end

::: moniker range=">=vs-2019"

1. Visual Studio 'da **dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje oluştur** iletişim kutusunda, **yerel etkinlik uygulaması (Android)** şablonunu seçin ve ardından **İleri**' yi seçin.

1. **Yeni projenizi yapılandırın** iletişim kutusunda, **Proje adı**alanına *MyAndroidApp* gibi bir ad girin ve ardından **Oluştur**' u seçin.

   Visual Studio yeni çözümü oluşturur ve Çözüm Gezgini açar.

::: moniker-end

Yeni Android yerel etkinlik uygulaması çözümü iki proje içerir:

- `MyAndroidApp.NativeActivity`, uygulamanızın Android üzerinde yerel etkinlik olarak çalışması için başvuruları ve birleştirici kodu içerir. Birleştirici kodundan giriş noktalarının uygulanması *Main. cpp*' dir. Önceden derlenmiş üstbilgiler *pch. h*içinde. Bu yerel etkinlik uygulaması projesi, bir paylaşılan kitaplık olarak derlenir *. bu nedenle* paketleme projesi tarafından çekilir.

- `MyAndroidApp.Packaging`, bir Android cihazında veya öykünücüsünde dağıtım için *. apk* dosyası oluşturur. Bu, bildirim özelliklerini ayarladığınız kaynakları ve *AndroidManifest. xml* dosyasını içerir. Ayrıca, ant yapı sürecini denetleyen *Build. xml* dosyasını da içerir. Varsayılan olarak, doğrudan Visual Studio 'dan dağıtılabilmesi ve çalıştırmak için başlangıç projesi olarak ayarlanır.

## <a name="build-and-run-the-default-android-native-activity-app"></a>Varsayılan Android yerel etkinlik uygulamasını derleyin ve çalıştırın

Yükleme ve kurulumunuzu doğrulamak için şablon tarafından oluşturulan uygulamayı derleyin ve çalıştırın. Bu ilk test için, uygulamayı Android öykünücüsü tarafından yüklenen cihaz profillerinden birinde çalıştırın. Uygulamanızı başka bir hedefte test etmek isterseniz, hedef öykünücüsünü yükleyebilir veya cihazı bilgisayarınıza bağlayabilirsiniz.

## <a name="to-build-and-run-the-default-native-activity-app"></a>Varsayılan yerel etkinlik uygulamasını derlemek ve çalıştırmak için

1. Henüz seçili değilse, **çözüm platformları** açılan listesinden **x86** ' yı seçin.

     ![Çözüm platformları açılan x86 seçimi](../cross-platform/media/cppmdd-rc-na-solution-x86.png "Çözüm platformları açılan x86 seçimi")

     **Çözüm platformları** listesi görüntülenmiyorsa, **Düğme Ekle/Kaldır** listesinden **çözüm platformları** ' nı seçin ve ardından platformunuzu seçin.

1. Menü çubuğunda **derleme** > **Build Solution**' ı seçin.

     Çıkış penceresi, çözümdeki iki proje için yapı işleminin çıkışını görüntüler.

1. Dağıtım hedefleriniz olarak Android öykünücü profillerinden birini seçin.

     Başka öykünücüleri yüklediyseniz veya bir Android cihazı bağladıysanız, bunları dağıtım hedefi açılan listesinden seçebilirsiniz.

1. Hata ayıklamayı başlatmak için **F5** tuşuna basın veya+**F5** ' **e basarak hata** ayıklamadan başlayın.

   Varsayılan uygulama, Android öykünücüsünde olduğu gibi görünür.

   ![Uygulamanızı çalıştıran öykünücü](../cross-platform/media/cppmdd-emulator-running-app.png "Uygulamanızı çalıştıran öykünücü")

   Visual Studio, kodunuzu yüklemek ve dağıtmak için birkaç saniye geçen öykünücüyü başlatır. Uygulamanız başlatıldıktan sonra, kesme noktaları ayarlayabilir ve kod içinde ilerlemek, Yereller incelemek ve değerleri izlemek için hata ayıklayıcıyı kullanabilirsiniz.

1. Hata ayıklamayı durdurmak için **shıft**+**F5** tuşlarına basın.

   Öykünücü çalışmaya devam eden ayrı bir işlemdir. Kodunuzu aynı öykünücüye birden çok kez düzenleyebilir, derleyebilir ve dağıtabilirsiniz.
