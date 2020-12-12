---
description: 'Hakkında daha fazla bilgi edinin: Android ve iOS üzerinde OpenGL ES uygulaması oluşturma'
title: Android ve iOS Üzerinde OpenGL ES uygulaması oluşturma
ms.date: 10/09/2019
ms.assetid: 76a67886-df57-4a81-accb-2e3c2eaf607b
ms.openlocfilehash: c840e9bbfd450c412ff7c0646127c157a3af565a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319423"
---
# <a name="build-an-opengl-es-application-on-android-and-ios"></a>Android ve iOS Üzerinde OpenGL ES uygulaması oluşturma

İOS uygulamaları ve ortak kod paylaşan android uygulamalar için Visual Studio çözümleri ve projeleri oluşturabilirsiniz. Bu makale, birleştirilmiş bir çözüm şablonunda size rehberlik eder. Hem bir iOS uygulaması hem de Android yerel etkinlik uygulaması oluşturur. Uygulamalar, her platformda aynı animasyonlu döndürme küpünü göstermek için OpenGL ES kullanan ortak C++ koduna sahiptir. OpenGL ES (katıştırılmış sistemler veya GLES için OpenGL), 2B ve 3B bir grafik API 'sidir. Birçok mobil cihazda desteklenir.

## <a name="requirements"></a>Gereksinimler

İOS ve Android için bir OpenGL ES uygulaması oluşturmak üzere tüm sistem gereksinimlerini karşılayın. Henüz yapmadıysanız, Visual Studio Yükleyicisi C++ iş yüküyle mobil geliştirme 'yi yükleyebilirsiniz. OpenGL ES şablonlarını almak ve iOS için derlemek için isteğe bağlı C++ iOS geliştirme araçları 'nı dahil edin. Android için derlemek için, C++ Android geliştirme araçları 'nı ve gerekli üçüncü taraf araçlarını yüklemek için: Android NDK, Apache Ant ve Google Android Emulator.

Intel platformlarında daha iyi öykünücü performansı için, tek bir seçenek Intel Hardware Accelerated Execution Manager (HAXM) yüklemektir. Ayrıntılı yönergeler için bkz. [C++ ile platformlar arası mobil geliştirme](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md).

İOS uygulamasını derlemek ve test etmek için bir Mac bilgisayara ihtiyacınız vardır. Yükleme yönergelerine göre ayarlayın. İOS geliştirme için ayarlama hakkında daha fazla bilgi için bkz. [iOS kullanarak derlemek için araçları kurma ve yapılandırma](../cross-platform/install-and-configure-tools-to-build-using-ios.md).

## <a name="create-a-new-opengles-application-project"></a>Yeni bir OpenGLES uygulama projesi oluşturma

Bu öğreticide, önce yeni bir OpenGL ES uygulama projesi oluşturursunuz. ardından, varsayılan uygulamayı bir Android öykünücüsünde oluşturup çalıştırın. Ardından, iOS için uygulamayı derleyin ve uygulamayı bir iOS cihazında çalıştırırsınız.

::: moniker range="msvc-150"

1. Visual Studio 'da **Dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunda, **Şablonlar** altında **Visual C++** > **platformlar arası**' ı seçin ve ardından **OpenGLES uygulaması (Android, iOS)** şablonunu seçin.

1. Uygulamaya *Myopengtasapp* gibi bir ad verin ve ardından **Tamam**' ı seçin.

   ![Yeni OpenGLES uygulama projesi](../cross-platform/media/cppmdd-opengles-newproj.png "Yeni OpenGLES uygulama projesi")

   Visual Studio yeni çözümü oluşturur ve Çözüm Gezgini açar.

   ![Çözüm Gezgini Myopengtasapp](../cross-platform/media/cppmdd-opengles-solexpl.png "Çözüm Gezgini Myopengtasapp")

::: moniker-end

::: moniker range=">=msvc-160"

1. Visual Studio 'da **Dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje oluştur** Iletişim kutusunda **OpenGLES uygulaması (Android, iOS)** şablonunu seçin ve ardından **İleri**' yi seçin.

1. **Yeni projenizi yapılandırın** iletişim kutusunda, **Proje adı** alanına *Myopengtasapp* gibi bir ad girin ve ardından **Oluştur**' u seçin.

   Visual Studio yeni çözümü oluşturur ve Çözüm Gezgini açar.

   ![Çözüm Gezgini Myopengtasapp](../cross-platform/media/cppmdd-opengles-solexpl.png "Çözüm Gezgini Myopengtasapp")

::: moniker-end

Yeni OpenGL ES uygulama çözümü, üç kitaplık projesi ve iki uygulama projesi içerir. Kitaplıklar klasörü, paylaşılan bir kod projesi içerir. Ve Paylaşılan koda başvuran, platforma özgü iki proje:

- `MyOpenGLESApp.Android.NativeActivity` Uygulamanızı Android 'de yerel bir etkinlik olarak uygulayan başvuruları ve birleştirici kodu içerir. Birleştirici kodundan gelen giriş noktaları, içindeki ortak paylaşılan kodu içeren *Main. cpp* öğesine uygulanır `MyOpenGLESApp.Shared` . Önceden derlenmiş üstbilgiler *pch. h* içinde. Bu yerel etkinlik uygulaması projesi, proje tarafından çekilen paylaşılan bir kitaplık (*. so*) dosyasında derlenir `MyOpenGLESApp.Android.Packaging` .

- `MyOpenGLESApp.iOS.StaticLibrary` içindeki paylaşılan kodu içeren bir iOS statik kitaplık (*. a*) dosyası oluşturur `MyOpenGLESApp.Shared` . Proje tarafından oluşturulan uygulamayla bağlantılıdır `MyOpenGLESApp.iOS.Application` .

- `MyOpenGLESApp.Shared` platformlar arasında çalışacak paylaşılan kodu içerir. Platforma özgü kodun koşullu derlenmesi için Önişlemci makrolarını kullanır. Paylaşılan kod hem hem de proje başvurusu tarafından alınır `MyOpenGLESApp.Android.NativeActivity` `MyOpenGLESApp.iOS.StaticLibrary` .

Çözüm, Android ve iOS platformları için uygulamalar oluşturmak üzere iki projeye sahiptir:

- `MyOpenGLESApp.Android.Packaging` Android cihazında veya öykünücüsünde dağıtım için *. apk* dosyası oluşturur. Bu dosya, bildirim özelliklerini ayarladığınız kaynakları ve AndroidManifest.xml dosyasını içerir. Ayrıca, ant yapı sürecini denetleyen *build.xml* dosyasını da içerir. Varsayılan olarak, doğrudan Visual Studio 'dan dağıtılabilmesi ve çalıştırmak için başlangıç projesi olarak ayarlanır.

- `MyOpenGLESApp.iOS.Application` içindeki C++ statik kitaplık koduna bağlanan bir iOS uygulaması oluşturmak için kaynaklar ve amaç-C birleştirici kodunu içerir `MyOpenGLESApp.iOS.StaticLibrary` . Bu proje, Visual Studio ve uzak aracı tarafından Mac 'e aktarılan bir yapı paketi oluşturur. Bu projeyi yapılandırdığınızda, Visual Studio uygulamanızı derlemek ve Mac 'te dağıtmak için dosyaları ve komutları gönderir.

## <a name="build-and-run-the-android-app"></a>Android uygulamasını derleme ve çalıştırma

Şablon tarafından oluşturulan çözüm, Android uygulamasını varsayılan proje olarak ayarlar.  Yükleme ve kurulumunuzu doğrulamak için bu uygulamayı derleyip çalıştırabilirsiniz. İlk test için, uygulamayı Android öykünücüsü tarafından yüklenen cihaz profillerinden birinde çalıştırın. Uygulamanızı başka bir hedefte test etmek isterseniz, hedef öykünücüyü yükleyebilirsiniz. Veya, bir cihazı bilgisayarınıza bağlayın.

### <a name="to-build-and-run-the-android-native-activity-app"></a>Android yerel etkinlik uygulamasını derlemek ve çalıştırmak için

1. Henüz seçili değilse, **çözüm platformları** açılan listesinden **x86** ' yı seçin.

   ![Çözüm platformunu x86 olarak ayarlama](../cross-platform/media/cppmdd-opengles-solutionplat.png "Çözüm platformunu x86 olarak ayarlama")

   Öykünücüyü hedeflemek için x86 kullanın. Bir cihazı hedeflemek için cihaz işlemcisini temel alan çözüm platformunu seçin. **Çözüm platformları** listesi görüntülenmiyorsa, **Düğme Ekle/Kaldır** listesinden **çözüm platformları** ' nı seçin ve ardından platformunuzu seçin.

1. **Çözüm Gezgini**' de, proje için kısayol menüsünü açın `MyOpenGLESApp.Android.Packaging` ve ardından **Oluştur**' u seçin.

   ![Android paketleme projesi oluştur](../cross-platform/media/cppmdd-opengles-andbuild.png "Android paketleme projesi oluştur")

   Çıkış penceresi, Android paylaşılan kitaplığı ve Android uygulaması için yapı işleminin çıkışını görüntüler.

   ![Android projeleri için derleme çıkışı](../cross-platform/media/cppmdd-opengles-andoutput.png "Android projeleri için derleme çıkışı")

1. Dağıtım hedefleriniz olarak öykünülmüş Android cihaz profillerinden birini seçin.

   ![Dağıtım hedefini seçin](../cross-platform/media/cppmdd-opengles-pickemulator.png "Dağıtım hedefini seçin")

   Başka öykünücüleri yüklemiş veya bir Android cihazı bağlamış olabilirsiniz. Bunları dağıtım hedefi açılan listesinden seçebilirsiniz. Uygulamayı çalıştırmak için, oluşturulan çözüm platformunun hedef cihazın platformuyla eşleşmesi gerekir.

1. Hata ayıklamayı başlatmak için **F5** 'e veya  + hata ayıklama olmadan başlamak için SHIFT **'e basın** .

   Visual Studio, kodunuzu yüklemek ve dağıtmak için birkaç saniye geçen öykünücüyü başlatır. Uygulamanın Öykünücüde nasıl göründüğü aşağıda verilmiştir:

   ![Android Emulator 'de çalışan uygulama](../cross-platform/media/cppmdd-opengles-andemulator.png "Android Emulator 'de çalışan uygulama")

   Uygulamanız başlatıldıktan sonra, kesme noktaları ayarlayabilir ve kod içinde ilerlemek, Yereller incelemek ve değerleri izlemek için hata ayıklayıcıyı kullanabilirsiniz.

1.  + Hata ayıklamayı durdurmak için SHIFT **F5** tuşuna basın.

   Öykünücü çalışmaya devam eden ayrı bir işlemdir. Kodunuzu aynı öykünücüye birden çok kez düzenleyebilir, derleyebilir ve dağıtabilirsiniz. Uygulamanız öykünücü üzerindeki uygulama koleksiyonunda görünür ve doğrudan buradan başlatılabilir.

   Oluşturulan Android yerel etkinlik uygulaması ve kitaplık projeleri, C++ paylaşılan kodunu dinamik bir kitaplığa koyar. Android platformuna sahip arabirime "tutkalla" kodunu içerir. Uygulama kodunun çoğu kitaplıkta bulunur. Bildirim, kaynak ve derleme yönergeleri paketleme projelerdir. Paylaşılan kod, NativeActivity projesindeki Main. cpp öğesinden çağrılır. Android yerel etkinliğinin nasıl programgörüntüleneceği hakkında daha fazla bilgi için bkz. Android Geliştirici NDK [kavramları](https://developer.android.com/ndk/guides/concepts.html) sayfası.

   Visual Studio, Android NDK 'yi kullanarak Android yerel etkinlik projelerini oluşturur. Platform araç takımı olarak Clang 'yi kullanır. Visual Studio, projenin özelliklerini hedef platformda derleme, bağlantı ve hata ayıklama komutlarıyla eşleştirir. Ayrıntılar için, Myopengtasapp. Android. NativeActivity projesi için **Özellik sayfaları** iletişim kutusunu açın. Komut satırı anahtarları hakkında daha fazla bilgi için bkz. [Clang derleyicisi Kullanıcı el kitabı](https://clang.llvm.org/docs/UsersManual.html).

## <a name="build-and-run-the-ios-app-on-an-ios-device"></a>İOS cihazında iOS uygulaması oluşturma ve çalıştırma

Visual Studio 'da iOS uygulama projesini oluşturun ve düzenleyin. Lisanslama kısıtlamaları nedeniyle, bir Mac 'ten oluşturulup dağıtılması gerekir. Visual Studio, proje dosyalarını aktarmak ve derleme, dağıtım ve hata ayıklama komutlarını yürütmek için Mac üzerinde çalışan bir uzak aracı ile iletişim kurar. İOS uygulamasını oluşturmadan önce, Mac ve Visual Studio 'Yu, iletişim kuracak şekilde ayarlayın ve yapılandırın. Ayrıntılı yönergeler için bkz. [iOS kullanarak derlemek için araçları yükleyip yapılandırma](../cross-platform/install-and-configure-tools-to-build-using-ios.md). Mac 'inizde uzak aracıyı çalıştırın ve Visual Studio ile eşleştirin. Ardından, yüklemenizi ve kurulumunuzu doğrulamak üzere iOS uygulamasını derleyip çalıştırabilirsiniz.

Uygulamanızı bir iOS cihazına dağıtmak için önce Xcode 'da otomatik oturum açmayı ayarlayın. Otomatik imzalama, uygulamanın bir derlemesini imzalamak için bir sağlama profili oluşturur.

### <a name="to-set-up-automatic-signing-on-xcode"></a>Xcode 'da otomatik imzalamayı ayarlamak için

1. Henüz yapmadıysanız, Mac 'inizde [Xcode](https://developer.apple.com/xcode/) 'u yükleyemezsiniz.

1. Mac 'inizde Xcode uygulamasını açın.

1. Yeni bir **tek görünüm uygulaması** Xcode projesi oluşturun. Proje oluşturma sırasında gerekli alanları girin. Proje yalnızca daha sonra uygulamanın bir derlemesini imzalamak için kullanılan bir sağlama profili oluşturmak için kullanıldığından, değerler rastgele olabilir.

1. [Apple bir geliştirici programı](https://developer.apple.com/programs/) hesabına KAYıTLı Apple Kimliğinizi Xcode 'a ekleyin. Apple KIMLIĞINIZ, uygulamaları imzalamak için imzalama kimliği olarak kullanılır. İmza kimliğinizi Xcode 'a eklemek için **Xcode** menüsünü açın ve **Tercihler**' i seçin. **Hesaplar** ' ı seçin ve Apple Kimliğinizi eklemek için Ekle düğmesine (+) tıklayın. Ayrıntılı yönergeler için bkz. [Apple ID hesabınızı ekleme](https://help.apple.com/xcode/mac/current/#/devaf282080a).

1. Xcode projesinin "genel" ayarlarından, **paket tanımlayıcısının** değerini olarak değiştirin `com.<NameOfVSProject>` ; burada, `<NameOfVSProject>` oluşturduğunuz Visual Studio çözüm projesiyle aynı addır. Örneğin, Visual Studio 'da adlı bir proje oluşturduysanız `MyOpenGLESApp` , **paket tanımlayıcısını** olarak ayarlayın `com.MyOpenGLESApp` .

   ![Xcode paket tanımlayıcısı](../cross-platform/media/cppmdd-opengles-iosxcodeid.png "Xcode paket tanımlayıcısı")

1. Otomatik imzalamayı etkinleştirmek için denetleyin. İmzalamayı otomatik olarak Yönet * *.

   ![Xcode otomatik imzalama](../cross-platform/media/cppmdd-opengles-iosxcodesign.png "Xcode otomatik imzalama")

1. Geliştirme **ekibi** olarak EKLEDIĞINIZ Apple kimliğinin ekip adını seçin.

   ![Xcode ekibi](../cross-platform/media/cppmdd-opengles-iosxcodeteam.png "Xcode ekibi")

### <a name="to-build-and-run-the-ios-app-on-an-ios-device"></a>İOS uygulamasını bir iOS cihazında derlemek ve çalıştırmak için

1. Mac 'inizde uzak aracıyı çalıştırın ve Visual Studio 'Nun uzak aracıyla eşleştirildiğini doğrulayın. Uzak aracıyı başlatmak için bir Terminal uygulaması penceresi açın ve girin `vcremote` . Daha fazla bilgi için bkz. [Visual Studio 'da uzak Aracıyı yapılandırma](../cross-platform/install-and-configure-tools-to-build-using-ios.md#ConfigureVS).

   ![Vcremote çalıştıran Mac Terminal penceresi](../cross-platform/media/cppmdd-common-vcremote.png "Vcremote çalıştıran Mac Terminal penceresi")

1. Mac 'e bir iOS cihazı ekleyin. Cihazınızı bir bilgisayara ilk kez iliştirmeniz durumunda, bir uyarı, cihazınıza erişmek için bilgisayara güvenip güvenmeyeceğinizi sorar. Cihazın Mac bilgisayarına güvenmesini sağlar.

1. Visual Studio 'da zaten seçili değilse, cihaz işlemcinizi temel alan **çözüm platformları** açılan listesinden çözüm platformunu seçin. Bu örnekte, bir **ARM64** işlemcisidir.

   ![Çözüm platformunu ARM64 olarak ayarla](../cross-platform/media/cppmdd-opengles-pickplatformarm64.png "Çözüm platformunu ARM64 olarak ayarla")

1. Çözüm Gezgini ' de, Myopengtasapp. iOS. Application projesinin kısayol menüsünü açın ve projeyi kaldırmak için **Projeyi Kaldır** ' ı seçin.

1. Yine, kaldırılan Myopengyesapp. iOS. Application projesi için kısayol menüsünü açın ve proje dosyasını düzenlemek için **projeyi Düzenle. PBXPROJ** öğesini seçin. `project.pbxproj`Dosyasında, `buildSettings` özniteliğini bulun ve `DEVELOPMENT_TEAM` Apple ekip kimliğinizi kullanarak ekleyin. Aşağıdaki ekran görüntüsünde, `123456ABC` Apple takım kimliği için örnek bir değer gösterilmektedir. Apple Team ID 'nizin değerini Xcode 'dan bulabilirsiniz. **Derleme ayarları** ' na gidin ve bir araç ipucu göstermek için geliştirme ekibi adınızın üzerine gelin. Araç ipucu takımınızın KIMLIĞINI gösterir.

   ![Geliştirme ekibini ayarla](../cross-platform/media/cppmdd-opengles-iosdevelopmentteam.png "Geliştirme ekibini ayarla")

1. Dosyayı kapatın `project.pbxproj` , ardından kaldırılan Myopengyesapp. iOS. Application projesinin kısayol menüsünü açın ve projeyi yeniden yüklemek Için **projeyi yeniden yükle** ' yi seçin.

1. Şimdi, projenin kısayol menüsünü açarak ve **Build**' i seçerek Myopengtasapp. IOS. Application projesini derleyin.

   ![İOS uygulama projesi oluştur](../cross-platform/media/cppmdd-opengles-iosbuild.png "İOS uygulama projesi oluştur")

   Çıkış penceresi, derleme işleminin çıkışını görüntüler. İOS statik kitaplığı ve iOS uygulaması için sonuçları gösterir. Mac üzerinde, uzak aracıyı çalıştıran Terminal penceresinde, komut ve dosya aktarımı etkinliği görüntülenir.

   Mac bilgisayarınızda, ortak tasarımın anahtarınıza erişmesine izin vermeniz istenebilir. Devam etmek için **Izin ver** ' i seçin.

1. Uygulamanızı Mac 'e iliştirilmiş cihazınızda çalıştırmak için araç çubuğunda iOS cihazınızı seçin. Uygulama başlamazsa, cihazın dağıtılan uygulamanızın cihazda yürütülmesi için izin verdiğinden emin olun. Bu izin, cihazdaki **Ayarlar**  >  **genel**  >  **cihaz yönetimi** bölümüne giderek ayarlanabilir. Geliştirici uygulama hesabınızı seçin, hesabınıza güvenin ve uygulamayı doğrulayın. Uygulamayı Visual Studio 'dan yeniden çalıştırmayı deneyin.

   ![iOS cihazında iOS uygulaması](../cross-platform/media/cppmdd-opengles-iosdevice.png "iOS cihazında iOS uygulaması")

   Uygulamanız başlatıldıktan sonra, kesme noktaları ayarlayabilir ve Visual Studio hata ayıklayıcısını kullanarak yerelleri inceleyebilir, çağrı yığınına bakın ve değerleri izleyin.

   ![İOS uygulamasında kesme noktasında hata ayıklayıcı](../cross-platform/media/cppmdd-opengles-iosdebug.png "İOS uygulamasında kesme noktasında hata ayıklayıcı")

1.  + Hata ayıklamayı durdurmak için SHIFT **F5** tuşuna basın.

   Oluşturulan iOS uygulaması ve kitaplık projeleri, C++ kodunu yalnızca paylaşılan kodu uygulayan bir statik kitaplığa koyar. Uygulama kodunun çoğu `Application` projede bulunur. Bu şablon projesindeki Paylaşılan kitaplık koduna yapılan çağrılar *Gameviewcontroller. d* dosyasında yapılır. İOS uygulamanızı derlemek için, Visual Studio, Mac üzerinde çalışan bir uzak istemciyle iletişim gerektiren Xcode platform araç takımını kullanır.

   Visual Studio, proje dosyalarını uzak istemciye aktarır. Ardından, Xcode kullanarak uygulamayı derlemek için komut gönderir. Uzak istemci, derleme durum bilgilerini Visual Studio 'ya geri gönderir. Uygulama başarıyla oluşturulduğunda, Visual Studio çalıştırmak ve uygulamada hata ayıklamak için komut gönderebilir. Visual Studio 'daki hata ayıklayıcı, iOS cihazınızda çalışan ve Mac 'nize bağlı uygulamayı denetler. Visual Studio, proje özelliklerini hedef iOS platformunda derlemek, bağlamak ve hata ayıklamak için kullanılan seçeneklere eşler. Derleyici komut satırı seçeneği ayrıntıları için, Myopengtasapp. iOS. StaticLibrary projesi için **Özellik sayfaları** iletişim kutusunu açın.

## <a name="customize-your-apps"></a>Uygulamalarınızı özelleştirme

Ortak işlevselliği eklemek veya değiştirmek için paylaşılan C++ kodunu değiştirebilirsiniz. Ve projelerindeki Paylaşılan koda yapılan çağrıları `MyOpenGLESApp.Android.NativeActivity` `MyOpenGLESApp.iOS.Application` eşleşecek şekilde değiştirin. Ön işlemci makrolarını, ortak kodunuzda platforma özgü bölümler belirtmek için kullanabilirsiniz. Ön işlemci makrosu, `__ANDROID__` Android için derleme yaptığınızda önceden tanımlanmıştır. Ön işlemci makrosu, `__APPLE__` iOS için derleme yaptığınızda önceden tanımlanmıştır.

Belirli bir proje platformu için IntelliSense 'i görmek için bağlam değiştirici açılan menüsünde projeyi seçin. Bu, düzenleyici penceresinin en üstündeki gezinti çubuğudur.

![Düzenleyicide proje bağlamı değiştirici açılan menüsü](../cross-platform/media/cppmdd-opengles-contextswitcher.png)

Geçerli proje tarafından kullanılan koddaki IntelliSense sorunları kırmızı dalgalı bir çizgiyle işaretlenir. Mor dalgalı çizgi, diğer projelerdeki bir sorunu ortaya kaldırır. Visual Studio, Java veya amaç-C dosyaları için kod renklendirme veya IntelliSense 'i desteklemez. Ancak, kaynak dosya ve kaynakları hala değiştirebilirsiniz. Uygulama adınızı, simgenizi ve diğer uygulama ayrıntılarını ayarlamak için bunları kullanın.
