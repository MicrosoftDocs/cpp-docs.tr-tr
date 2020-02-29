---
title: iOS kullanarak derlemeye yönelik araçları yükleme ve yapılandırma
ms.date: 10/17/2019
ms.assetid: d0c311c9-9eb9-42c5-ba07-25604362cd28
ms.openlocfilehash: 87c02f5399465c6131fad2bb9839698699d1e488
ms.sourcegitcommit: a673f6a54cc97e3d4cd032b10aa8dce7f0539d39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78177565"
---
# <a name="install-and-configure-tools-to-build-using-ios"></a>iOS kullanarak derlemeye yönelik araçları yükleme ve yapılandırma

İOS kodu düzenleme, hata ayıklama ve iOS simülatörü veya bir iOS cihazına dağıtmak için Visual Studio ile platformlar arası **Mobil geliştirmeyle C++**  birlikte kullanabilirsiniz. Ancak lisanslama kısıtlamaları nedeniyle kodun bir Mac üzerinde oluşturulması ve uzaktan çalıştırılması gerekir. Visual Studio kullanarak iOS uygulamaları derlemek ve çalıştırmak için, Mac 'inizde [vcremote](https://www.npmjs.com/package/vcremote)uzak aracısını ayarlamanız ve yapılandırmanız gerekir. Uzak Aracı, Visual Studio 'dan derleme isteklerini işler ve uygulamayı Mac 'e bağlı iOS cihazında veya Mac üzerindeki iOS simülatörü üzerinde çalıştırır.

> [!NOTE]
> Mac yerine bulutta barındırılan Mac Hizmetleri kullanma hakkında daha fazla bilgi için bkz. [Visual Studio 'yu bulutta barındırılan Mac 'e bağlamak Için yapılandırma](/visualstudio/cross-platform/tools-for-cordova/tips-workarounds/host-a-mac-in-the-cloud?view=toolsforcordova-2017#configure-visual-studio-to-connect-to-your-cloud-hosted-mac). Yönergeler, Apache Cordova için Visual Studio Araçları kullanarak oluşturma içindir. Kullanarak C++oluşturma yönergelerini kullanmak için, `remotebuild`için `vcremote` değiştirin.

İOS kullanarak derlemek için araçları yükledikten sonra, Visual Studio ve Mac 'te iOS geliştirmesi için uzak aracıyı hızlı bir şekilde yapılandırmak ve güncellemek üzere bu makaleye başvurun.

## <a name="prerequisites"></a>Önkoşullar

İOS için kod geliştirmek üzere uzak aracıyı yüklemek ve kullanmak için, önce aşağıdaki önkoşullara sahip olmanız gerekir:

- MacOS Mojave sürüm 10,14 veya üstünü çalıştıran bir Mac bilgisayar

- Bir [Apple Kimliği](https://appleid.apple.com/)

- Etkin bir [Apple geliştirici programı](https://developer.apple.com/programs/) hesabı

   Bir iOS cihazına yalnızca test için yük dışarıdan yüklemeye izin veren ancak dağıtım için değil, ücretsiz bir hesap alabilirsiniz.

- [Xcode](https://developer.apple.com/xcode/downloads/) sürüm 10.2.1 veya üzeri

   Xcode, App Store 'dan indirilebilir.

- Xcode komut satırı araçları

   Xcode komut satırı araçlarını yüklemek için, Mac 'inizde Terminal uygulamasını açın ve şu komutu girin:

   `xcode-select --install`

- Xcode 'da uygulamaları imzalamak için imzalama kimliği olarak yapılandırılmış bir Apple KIMLIĞI hesabı

   Xcode 'da imzalama kimliğinizi görmek veya ayarlamak için **Xcode** menüsünü açın ve **Tercihler**' i seçin. **Hesaplar** ' ı seçin ve Apple Kimliğinizi seçin ve ardından **Ayrıntıları görüntüle** düğmesini seçin. Ayrıntılı yönergeler için bkz. [Apple ID hesabınızı ekleme](https://help.apple.com/xcode/mac/current/#/devaf282080a) .

   İmzalama gereksinimleri hakkında ayrıntılı bilgi için bkz. [uygulama Imzalama nedir?](https://help.apple.com/xcode/mac/current/#/dev3a05256b8).

- Geliştirme için bir iOS cihazı kullanıyorsanız, cihazınız için Xcode 'da yapılandırılmış bir sağlama profili

   Xcode, gerektiğinde sizin için imza sertifikaları oluşturduğu otomatik imza sağlar. Xcode otomatik imzalama hakkında ayrıntılı bilgi için bkz. [Otomatik imzalama](https://help.apple.com/xcode/mac/current/#/dev80cc24546).

   El ile imzalama yapmak istiyorsanız, uygulamanız için bir sağlama profili oluşturmanız gerekir. Sağlama profilleri oluşturma hakkında ayrıntılı bilgi için bkz. [bir geliştirme sağlama profili oluşturma](https://help.apple.com/developer-account/#/devf2eb157f8).

- [Node. js](https://nodejs.org/) sürüm 12.14.1 ve NPM sürüm 6.13.4

   Mac 'inizde Node. js sürüm 12.14.1 'yi yükler. Node. js paketini yüklerseniz, NPM sürüm 6.13.4 ile birlikte gelmelidir. Diğer Node. js ve NPM sürümleri, `vcremote` yüklemesinin başarısız olmasına neden olabilecek `vcremote`uzak aracıda kullanılan bazı modülleri desteklemiyor olabilir. Node. js ' nin [düğüm sürümü Yöneticisi](https://nodejs.org/en/download/package-manager/#nvm)gibi bir paket Yöneticisi kullanarak yüklenmesini öneririz. Bazı modüller `sudo`kullanılırken yüklenemeyebilir, Node. js ' yi yüklemek için komut `sudo` kullanmaktan kaçının.

## <a name="Install"></a>İOS için uzak aracıyı yükler

Mobil geliştirme iş yüküyle birlikte C++ yüklediğinizde, Visual Studio [vcremote](https://www.npmjs.com/package/vcremote)Ile iletişim kurabilir, Mac 'inizde çalışan uzak bir aracı, dosyaları aktarmak, iOS uygulamanızı derlemek ve çalıştırmak ve hata ayıklama komutları göndermek için kullanılabilir.

Uzak aracıyı yüklemeden önce, [önkoşulları](#prerequisites) karşıladığınızdan ve [platformlar arası C++mobil geliştirmeyi yükleme ](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md#install-the-tools)' deki yükleme adımlarını tamamladığınızdan emin olun.

### <a name="DownloadInstall"></a>Uzak aracıyı indirmek ve yüklemek için

- Mac inizdeki Terminal uygulamasından, kullanılmakta olan Node. js sürümünün gerekli sürüm 12.14.1 olduğunu doğrulayın. Sürümü doğrulamak için şu komutu çalıştırın:

  `node -v`
  
  Doğru sürüm değilse, önkoşullardan Node. js yükleme talimatlarını izlemeniz gerekebilir. Ardından Node. js ' yi yeniden başlatın.

- Gerekli Node. js ' nin kullanımda olduğunu doğruladıktan sonra, bu Node. js sürümüne vcremote yüklemek için şu komutu çalıştırın:

   `npm install -g --unsafe-perm vcremote`

   Genel yükleme ( **-g**) anahtarı önerilir, ancak gerekli değildir. Genel yükleme anahtarını kullanmıyorsanız, vcremote, Terminal uygulamasındaki geçerli etkin yolun altına yüklenir.

   Yükleme sırasında, `vcremote` yüklenir ve geliştirici modu Mac 'inizde etkinleştirilir. [Homebrew](https://brew.sh/) ve iki NPM paketi, `vcremote-lib` ve `vcremote-utils`de yüklüdür. Yükleme tamamlandığında, atlanan isteğe bağlı bağımlılıklara ilişkin uyarıları yoksaymak güvenlidir.

   > [!NOTE]
   > Homebrew 'yi yüklemek için sudo (yönetici) erişiminizin olması gerekir. Sudo olmadan `vcremote` yüklemeniz gerekiyorsa, homebrew 'yi bir usr/yerel konuma el ile yükleyebilir ve bin klasörünü yolunuza ekleyebilirsiniz. Daha fazla bilgi için [homebrew belgelerine](https://github.com/Homebrew/homebrew/wiki/Installation)bakın. Geliştirici modunu el ile etkinleştirmek için bu komutu Terminal uygulamasına girin: `DevToolsSecurity -enable`

Visual Studio 'nun yeni bir sürümüne güncelleştirirseniz, uzak aracının geçerli sürümüne de güncelleştirmeniz gerekir. Uzak aracıyı güncelleştirmek için uzak aracıyı indirme ve yükleme adımlarını yineleyin.

## <a name="Start"></a>Uzak aracıyı başlatma

İOS kodunuzu derlemek ve çalıştırmak için uzak aracının Visual Studio için çalışıyor olması gerekir. İletişim kurabilmesi için, Visual Studio 'Nun uzak aracıyla eşleştirilmiş olması gerekir. Varsayılan olarak, uzak Aracı, Visual Studio ile eşleştirmek için PIN gerektiren güvenli bağlantı modunda çalışır.

### <a name="RemoteAgentStartServer"></a>Uzak aracıyı başlatmak için

- Mac inizdeki Terminal uygulamasından şunu girin:

   `vcremote`

   Bu komut, uzak aracıyı `~/vcremote`varsayılan bir yapı diziniyle başlatır. Ek yapılandırma seçenekleri için bkz. [Mac üzerinde uzak Aracıyı yapılandırma](#ConfigureMac).

Aracıyı ilk kez başlattığınızda ve her yeni istemci sertifikası oluşturduğunuzda, ana bilgisayar adı, bağlantı noktası ve PIN dahil olmak üzere Visual Studio 'da aracıyı yapılandırmak için gerekli bilgiler sunulur.

![Güvenli PIN oluşturmak için vcremote kullanın](../cross-platform/media/cppmdd-vcremote-generateclientcert.png "Güvenli PIN oluşturmak için vcremote kullanın")

Visual Studio 'da ana bilgisayar adını kullanarak uzak aracıyı yapılandırmak istiyorsanız, erişilebilir olduğunu doğrulamak için ana bilgisayar adını kullanarak Windows 'dan Mac 'e ping gönderin. Aksi takdirde, bunun yerine IP adresini kullanmanız gerekebilir.

Oluşturulan PIN bir kerelik kullanım içindir ve yalnızca sınırlı bir süre için geçerlidir. Zaman sona ermeden önce Visual Studio 'Yu uzak aracı ile eşleştirmeyin, yeni bir PIN oluşturmanız gerekecektir. Daha fazla bilgi için bkz. [Yeni bir güvenlik PIN 'ı oluşturma](#GeneratePIN).

Uzak aracıyı güvenli olmayan modda kullanabilirsiniz. Güvenli olmayan modda uzak Aracı, PIN olmadan Visual Studio ile eşleştirilebilir.

#### <a name="to-disable-secured-connection-mode"></a>Güvenli bağlantı modunu devre dışı bırakmak için

- `vcremote`güvenli bağlantı modunu devre dışı bırakmak için, aşağıdaki komutu Mac 'inizde Terminal uygulamasına girin:

   `vcremote --secure false`

#### <a name="to-enable-secured-connection-mode"></a>Güvenli bağlantı modunu etkinleştirmek için

- Güvenli bağlantı modunu etkinleştirmek için şu komutu girin:

   `vcremote --secure true`

Uzak aracıyı başlattığınızda, bunu durdurmadan, Visual Studio 'dan kullanabilirsiniz.

#### <a name="to-stop-the-remote-agent"></a>Uzak aracıyı durdurmak için

- `vcremote` Terminal penceresinde, **denetim**+**C**yazın.

## <a name="ConfigureVS"></a>Visual Studio 'da uzak Aracıyı yapılandırma

Visual Studio 'dan uzak aracıya bağlanmak için, Visual Studio seçeneklerinde uzak yapılandırmayı belirtmeniz gerekir.

### <a name="to-configure-the-remote-agent-from-visual-studio"></a>Uzak aracıyı Visual Studio 'dan yapılandırmak için

1. Aracı Mac 'inizde zaten çalışmıyorsa, [uzak aracıyı başlatma](#Start)bölümündeki adımları izleyin. Visual Studio 'nun projenizi başarıyla eşleştirmesine, bağlamaya ve derlemenize yönelik `vcremote`, Mac 'nizin çalışıyor olması gerekir.

1. Mac 'inizde, Mac 'nizin ana bilgisayar adını veya IP adresini alın.

   Terminal penceresinde **ifconfig** komutunu kullanarak IP adresini alabilirsiniz. Etkin ağ arabirimi altında listelenen Inet adresini kullanın.

1. Visual Studio menü çubuğunda **Araçlar**, **Seçenekler**' i seçin.

1. **Seçenekler** iletişim kutusunda **platformlar arası**, **C++** **iOS**' ı genişletin.

1. **Ana bilgisayar adı** ve **bağlantı noktası** alanlarında, uzak aracı tarafından başlatıldığında belirtilen değerleri girin. Ana bilgisayar adı, Mac 'nizin DNS adı veya IP adresi olabilir. Varsayılan bağlantı noktası 3030 ' dir.

   > [!NOTE]
   > Ana bilgisayar adını kullanarak Mac 'e ping yapamadıysanız IP adresini kullanmanız gerekebilir.

1. Uzak aracıyı varsayılan güvenli bağlantı modunda kullanıyorsanız, **güvenli** onay kutusunu işaretleyin, sonra **PIN** alanına uzak aracı tarafından belirtilen PIN değerini girin. Uzak aracıyı güvenli olmayan bağlantı modunda kullanıyorsanız, **güvenli** onay kutusunu temizleyip **sabitle** alanını boş bırakın.

1. Eşleştirmeyi etkinleştirmek için **çift** seçin.

   ![İOS derlemeleri için vcremote bağlantısını yapılandırma](../cross-platform/media/cppmdd-options-ios.png "İOS derlemeleri için vcremote bağlantısını yapılandırma")

   Eşleştirme, ana bilgisayar adı veya bağlantı noktası değiştirilene kadar devam ettirir. **Seçenekler** iletişim kutusunda ana bilgisayar adını veya bağlantı noktasını değiştirirseniz, değişikliği geri almak için, önceki eşleştirmeye geri dönmek Için **geri al** düğmesini seçin.

   Eşleştirme başarılı olmazsa uzak [aracıyı başlatma](#Start)bölümündeki adımları izleyerek uzak aracının çalıştığını doğrulayın. Uzak aracı PIN 'ı oluşturulduktan sonra çok fazla zaman geçtiyse, Mac üzerinde [Yeni bir güvenlik PIN 'ı oluşturma](#GeneratePIN) ' daki adımları izleyin ve sonra yeniden deneyin. Mac 'nizin ana bilgisayar adını kullanıyorsanız, bunun yerine **ana bilgisayar adı** alanındaki IP adresini kullanmayı deneyin.

1. Uzak **kök** alanındaki klasör adını, Mac 'teki giriş ( *~* ) dizininizde bulunan uzak aracı tarafından kullanılacak klasörü belirtmek için güncelleştirin. Varsayılan olarak, uzak aracı uzak kök olarak `/Users/<username>/vcremote` kullanır.

1. Uzaktan eşleştirme bağlantı ayarlarını kaydetmek için **Tamam ' ı** seçin.

Visual Studio, kullandığınız her seferinde Mac 'inizde uzak aracıya bağlanmak için aynı bilgileri kullanır. Mac 'inizde yeni bir güvenlik sertifikası oluşturmadığınız veya ana bilgisayar adı veya IP adresi değiştiği takdirde, Visual Studio 'Yu uzak aracıyla yeniden eşleştirmenizi gerektirmez.

## <a name="GeneratePIN"></a>Yeni bir güvenlik PIN 'ı oluştur

Uzak aracıyı ilk kez başlattığınızda, oluşturulan PIN, varsayılan olarak 10 dakika boyunca sınırlı bir süre için geçerlidir. Zaman sona ermeden önce Visual Studio 'Yu uzak aracıya eşleştirmezseniz, yeni bir PIN oluşturmanız gerekir.

### <a name="to-generate-a-new-pin"></a>Yeni bir PIN oluşturmak için

1. Aracıyı durdurun veya Mac 'inizde ikinci bir Terminal uygulaması penceresi açın ve bunu kullanarak komutu girin.

1. Terminal uygulamasına şu komutu girin:

   `vcremote generateClientCert`

   Uzak aracı yeni bir geçici PIN oluşturur. Visual Studio 'Yu yeni PIN kullanarak eşleştirmek için, [Visual Studio 'da uzak Aracıyı yapılandırma](#ConfigureVS)bölümündeki adımları yineleyin.

## <a name="GenerateCert"></a>Yeni bir sunucu sertifikası oluştur

Güvenlik nedeniyle, Visual Studio 'Yu uzak aracıyla eşleştirmeyen sunucu sertifikaları, Mac 'nizin IP adresine veya ana bilgisayar adına bağlıdır. Bu değerler değiştiğinde, yeni bir sunucu sertifikası oluşturmanız ve ardından Visual Studio 'Yu yeni değerlerle yeniden yapılandırmanız gerekir.

### <a name="to-generate-a-new-server-certificate"></a>Yeni bir sunucu sertifikası oluşturmak için

1. `vcremote` aracısını durdurun.

1. Terminal uygulamasına şu komutu girin:

   `vcremote resetServerCert`

1. Onay istendiğinde `Y`girin.

1. Terminal uygulamasına şu komutu girin:

   `vcremote generateClientCert`

   Bu komut yeni bir geçici PIN oluşturur.

1. Visual Studio 'Yu yeni PIN kullanarak eşleştirmek için, [Visual Studio 'da uzak Aracıyı yapılandırma](#ConfigureVS)bölümündeki adımları yineleyin.

## <a name="ConfigureMac"></a>Mac 'te uzak Aracıyı yapılandırma

Uzak aracıyı çeşitli komut satırı seçeneklerini kullanarak yapılandırabilirsiniz. Örneğin, derleme isteklerini dinlemek için bağlantı noktasını belirtebilir ve dosya sisteminde korunacak en fazla derleme sayısını belirtebilirsiniz. Varsayılan olarak, sınır 10 derlemedir. Uzak Aracı, kapatırken en fazla uzunluğu aşan yapıları kaldırır.

### <a name="to-configure-the-remote-agent"></a>Uzak aracıyı yapılandırmak için

- Uzak aracı komutlarının tüm listesini görmek için, Terminal uygulamasında şunu girin:

   `vcremote --help`

- Güvenli modu devre dışı bırakmak ve basit HTTP tabanlı bağlantıları etkinleştirmek için şunu girin:

   `vcremote --secure false`

   Bu seçeneği kullandığınızda, aracıyı Visual Studio 'da yapılandırırken **güvenli** onay kutusunun işaretini kaldırın ve **PIN** alanını boş bırakın.

- Uzak Aracı dosyaları için bir konum belirtmek üzere şunu girin:

   `vcremote --serverDir directory_path`

   Burada *directory_path* , günlük dosyalarının, derlemelerin ve sunucu sertifikalarının yerleştirileceği Mac 'inizde yer alır. Varsayılan olarak, bu konum `/Users/<username>/vcremote`. Derlemeler, bu konumda yapı numarasına göre düzenlenir.

- `stdout` yakalamak ve Server. log adlı bir dosyaya `stderr` bir arka plan işlemi kullanmak için şunu girin:

   `vcremote > server.log 2>&1 &`

   Server. log dosyası, derleme sorunlarını gidermeye yardımcı olabilir.

- Aracıyı komut satırı parametreleri yerine bir yapılandırma dosyası kullanarak çalıştırmak için şunu girin:

   `vcremote --config config_file_path`

   Burada *config_file_path* , JSON biçimindeki bir yapılandırma dosyasının yoludur. Başlangıç seçenekleri ve değerleri tire içermemelidir.

## <a name="troubleshoot-the-remote-agent"></a>Uzak aracı sorunlarını giderme

### <a name="debugging-on-an-ios-device"></a>İOS cihazında hata ayıklama

Bir iOS cihazında hata ayıklama çalışmazsa, bir iOS cihazından iletişim kurmak için kullanılan [ıdeviceınstaller](https://github.com/libimobiledevice/ideviceinstaller)aracı ile ilgili sorunlar olabilir. Bu araç genellikle `vcremote`yüklemesi sırasında homebrew 'dan yüklenir. Geçici çözüm olarak aşağıdaki adımları izleyin.

Aşağıdaki komutları sırasıyla çalıştırarak Terminal uygulamasını açın ve `ideviceinstaller` ve bağımlılıklarını güncelleştirin:

1. Homebrew 'ın güncelleştirildiğinden emin olun

   `brew update`

1. `libimobiledevice` ve `usbmuxd` kaldır

   `brew uninstall --ignore-dependencies libimobiledevice`

   `brew uninstall --ignore-dependencies usbmuxd`

1. `libimobiledevice` ve `usbmuxd` en son sürümünü yükleyip

   `brew install --HEAD usbmuxd`

   `brew unlink usbmuxd`

   `brew link usbmuxd`

   `brew install --HEAD libimobiledevice`

1. `ideviceinstaller` kaldırın ve yeniden yükleyin

   `brew uninstall ideviceinstaller`

   `brew install ideviceinstaller`

Cihazda yüklü olan uygulamaları listeleyerek `ideviceinstaller` cihazla iletişim kurabildiğini doğrulayın:

`ideviceinstaller -l`

`ideviceinstaller` `/var/db/lockdown`klasöre erişemeyeceği hatalar varsa, bu klasördeki ayrıcalığı şu şekilde değiştirin:

`sudo chmod 777 /var/db/lockdown`

Ardından `ideviceinstaller` cihazla iletişim kurabiliyorsa tekrar doğrulayın.

## <a name="see-also"></a>Ayrıca bkz.

- [İle platformlar arası mobil geliştirmeC++](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)
