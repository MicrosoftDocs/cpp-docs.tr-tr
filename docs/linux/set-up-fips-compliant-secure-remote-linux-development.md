---
title: FIPS uyumlu güvenli uzak Linux geliştirmeyi ayarla
description: Visual Studio ile uzaktan geliştirme için bir Linux makinesi arasında FIPS uyumlu şifreleme bağlantısı nasıl kurulamaz?
ms.date: 01/17/2020
ms.openlocfilehash: 9a0e87f4ddf69bf489b52d4f83934d3279f2d085
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "76520895"
---
# <a name="set-up-fips-compliant-secure-remote-linux-development"></a>FIPS uyumlu güvenli uzak Linux geliştirmeyi ayarla

::: moniker range="<=vs-2017"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir. FIPS uyumlu güvenli uzaktan Linux geliştirme Visual Studio mevcuttur 2019 sürüm 16.5 ve sonraki.

::: moniker-end

::: moniker range="vs-2019"

Federal Bilgi İşlem Standardı (FIPS) Yayını 140-2, kriptografik modüller için ABD hükümetinin standart standardıdır. Standardın uygulamaları NIST tarafından doğrulanır. Windows [FIPS uyumlu şifreleme modülleri için destek doğruladı.](/windows/security/threat-protection/fips-140-validation) Visual Studio 2019 sürüm 16.5 ve sonraki sürümlerinde, uzaktan geliştirme için Linux sisteminize güvenli, FIPS uyumlu bir şifreleme bağlantısı kullanabilirsiniz.

Visual Studio ile uzak Linux sisteminiz arasında güvenli, FIPS uyumlu bir bağlantı nın nasıl ayarlayabilirsiniz: Bu kılavuz, Visual Studio'da CMake veya MSBuild Linux projeleri oluşturduğunuzda geçerlidir. Bu makale, [uzak Linux bilgisayarınıza bağlan'daki](connect-to-your-remote-linux-computer.md)bağlantı yönergelerinin FIPS uyumlu sürümüdür.

## <a name="prepare-a-fips-compliant-connection"></a>FIPS uyumlu bir bağlantı hazırlama

Visual Studio ile uzak Linux sisteminiz arasında FIPS uyumlu, şifreleme yle güvenli bir ssh bağlantısı kullanmak için bazı hazırlıklar gereklidir. FIPS-140-2 uyumluluğu için Visual Studio yalnızca RSA tuşlarını destekler.

Bu makaledeki örnekler, OpenSSH sunucu sürümü 7.6 ile Ubuntu 18.04 LTS'yi kullanamaz. Ancak, openssh orta derecede yeni bir sürümünü kullanarak herhangi bir dağıtım için talimatlar aynı olmalıdır.

### <a name="to-set-up-the-ssh-server-on-the-remote-system"></a>Uzak sistemde SSH sunucusunu kurmak için

1. Linux sisteminde OpenSSH sunucusunu yükleyin ve başlatın:

   ```bash
   sudo apt install openssh-server
   sudo service ssh start
   ```

1. Sistem önyükleme yaparken ssh sunucusunun otomatik olarak başlatılmasını istiyorsanız, systemctl kullanarak etkinleştirin:

   ```bash
   sudo systemctl enable ssh
   ```

1. Kök olarak */etc/ssh/sshd_config* açın. Aşağıdaki satırları edin (veya eklemeyin, yoksa) aşağıdaki satırları ekleyin:

   ```config
   Ciphers aes256-cbc,aes192-cbc,aes128-cbc,3des-cbc
   HostKeyAlgorithms ssh-rsa
   KexAlgorithms diffie-hellman-group-exchange-sha256,diffie-hellman-group-exchange-sha1,diffie-hellman-group14-sha1
   MACs hmac-sha2-256,hmac-sha1
   ```

   > [!NOTE]
   > ssh-rsa sadece FIPS uyumlu ana bilgisayar anahtar algoritması VS destekler. Aes\*-ctr algoritmaları da FIPS uyumludur, ancak Visual Studio'daki uygulama onaylanmaz. Ecdh-anahtar\* değişim algoritmaları FIPS uyumludur, ancak Visual Studio bunları desteklemez.

   Bu seçeneklerle sınırlı değilsin. Ek şifreler, ana bilgisayar anahtar algoritmaları ve benzeri kullanmak için ssh yapılandırabilirsiniz. Dikkate almak isteyebileceğin diğer bazı `PermitRootLogin` `PasswordAuthentication`ilgili `PermitEmptyPasswords`güvenlik seçenekleri , ve . Daha fazla bilgi için, sshd_config veya makale [SSH Server Configuration](https://www.ssh.com/ssh/sshd_config)için adam sayfasına bakın.

1. sshd_config kaydedip kapattıktan sonra, yeni yapılandırmayı uygulamak için ssh sunucusunu yeniden başlatın:

   ```bash
   sudo service ssh restart
   ```

Ardından, Windows bilgisayarınızda bir RSA anahtar çifti oluşturursunuz. Daha sonra ssh tarafından kullanılmak üzere uzak Linux sisteminin ortak anahtarını kopyalayaceksiniz.

### <a name="to-create-and-use-an-rsa-key-file"></a>RSA anahtar dosyası oluşturmak ve kullanmak için

1. Windows makinesinde, bu komutu kullanarak ortak/özel RSA anahtar çifti oluşturun:

   ```cmd
   ssh-keygen -t rsa -b 4096
   ```

   Komut ortak bir anahtar ve özel bir anahtar oluşturur. Varsayılan olarak, anahtarlar *%USERPROFILE%\\.ssh\\id_rsa* ve *%USERPROFILE%\\.ssh\\id_rsa.pub'a*kaydedilir. (Powershell'de `$env:USERPROFILE` cmd makro `%USERPROFILE%`yerine kullanın) Anahtar adını değiştirirseniz, değiştirilen adı izleyen adımlarda kullanın.  Artırılmış güvenlik için bir parola kullanmanızı öneririz.

1. Windows'dan ortak anahtarı Linux makinesine kopyalayın:

   ```cmd
   scp %USERPROFILE%\.ssh\id_rsa.pub user@hostname:
   ```

1. Linux sisteminde, yetkili anahtarlar listesine anahtarı ekleyin ve dosyanın doğru izinlere sahip olduğundan emin olun:

   ```bash
   cat ~/id_rsa.pub >> ~/.ssh/authorized_keys
   chmod 600 ~/.ssh/authorized_keys
   ```

1. Şimdi, yeni anahtarın SSH'de çalışıp çalışmamadığını test edebilirsiniz. Windows'dan oturum açabilmek için kullanın:

    ```cmd
    ssh -i %USERPROFILE%\.ssh\id_rsa user@hostname
    ```

SSH'yi başarıyla kurdunuz, şifreleme anahtarlarını oluşturdunuz ve dağıttınız ve bağlantınızı test ettin. Şimdi Visual Studio bağlantısını kurmaya hazırsınız.

## <a name="connect-to-the-remote-system-in-visual-studio"></a>Visual Studio'da uzak sisteme bağlanın

1. Visual Studio'da, **Seçenekler** iletişim kutusunu açmak için menü çubuğundaki **Araçlar > Seçenekler'i** seçin. Ardından Bağlantı Yöneticisi iletişim kutusunu açmak için **Platform > Bağlantı Yöneticisi'ni seçin.**

   Visual Studio'da daha önce bir bağlantı kurmadıysanız, projenizi ilk kez oluşturduğunuzda, Visual Studio Bağlantı Yöneticisi iletişim kutusunu sizin için açar.

1. Bağlantı Yöneticisi iletişim kutusunda, yeni bir bağlantı eklemek için **Ekle** düğmesini seçin.

   ![Bağlantı Yöneticisi](media/settings_connectionmanager.png)

   **Uzak Sisteme Bağlan** penceresi görüntülenir.

   ![Uzak Sisteme Bağlan](media/connect.png)

1. Uzak **Sisteme Bağlan** iletişim kutusunda, uzak makinenizin bağlantı ayrıntılarını girin.

   | Girdi | Açıklama
   | ----- | ---
   | **Ev Sahibi Adı**           | Hedef cihazınızın adı veya IP adresi
   | **Bağlantı noktası**                | SSH hizmetinin üzerinde çalışan bağlantı noktası, genellikle 22
   | **Kullanıcı adı**           | Kullanıcı olarak kimlik doğrulaması
   | **Kimlik doğrulaması türü** | FIPS uyumlu bağlantı için Özel Anahtar'ı seçin
   | **Özel anahtar dosyası**    | ssh bağlantısı için oluşturulan özel anahtar dosyası
   | **Parola**          | Yukarıda seçilen özel anahtarla kullanılan parola

   Kimlik doğrulama türünü **Özel Anahtar**olarak değiştirin. **Özel anahtar dosyası** alanında özel anahtarınıza giden yolu girin. Bunun yerine özel tuş dosyanıza gitmek için **Gözat** düğmesini kullanabilirsiniz. Ardından, **Passphrase** alanında özel anahtar dosyanızı şifrelemek için kullanılan parolayı girin.

1. Uzak bilgisayara bağlantı denemek için **Bağlan** düğmesini seçin.

   Bağlantı başarılı olursa, Visual Studio uzak başlıkları kullanacak şekilde IntelliSense'i yapılandırır. Daha fazla bilgi için uzak [sistemlerdeki üstbilgiler için IntelliSense'e](configure-a-linux-project.md#remote_intellisense)bakın.

   Bağlantı başarısız olursa, değiştirilmesi gereken giriş kutuları kırmızı ile özetlenir.

   ![Bağlantı Yöneticisi Hatası](media/settings_connectionmanagererror.png)

   Bağlantınızı giderme yle ilgili daha fazla bilgi için, [uzak Linux bilgisayarınıza bağlan'a](connect-to-your-remote-linux-computer.md)bakın.

## <a name="command-line-utility-for-the-connection-manager"></a>Bağlantı Yöneticisi için komut satırı yardımcı programı  

**Visual Studio 2019 sürüm 16.5 veya sonrası**: ConnectionManager.exe, Visual Studio dışındaki uzaktan geliştirme bağlantılarını yönetmek için bir komut satırı yardımcı programıdır. Yeni bir geliştirme makinesi sağlama gibi görevler için yararlıdır. Veya, sürekli entegrasyon için Visual Studio kurmak için kullanabilirsiniz. Örnekler ve ConnectionManager komutuna tam bir başvuru için [ConnectionManager başvurusuna](connectionmanager-reference.md)bakın.  

## <a name="optional-enable-or-disable-fips-mode"></a>İsteğe bağlı: FIPS modunu etkinleştirme veya devre dışı

Windows'da FIPS modunu genel olarak etkinleştirmek mümkündür.

1. FIPS modunu etkinleştirmek için, Çalıştır iletişim kutusunu açmak için **Windows+R** tuşuna basın ve ardından gpedit.msc'yi çalıştırın.

1. **Yerel İlkeler > Güvenlik Ayarları > Windows Ayarları > Yerel Bilgisayar Politikası > Bilgisayar Yapılandırması'nı** genişletin ve **Güvenlik Seçeneklerini**seçin.

1. **İlke**altında **Sistem şifrelemesini seçin: Şifreleme, karma ve imzalama için FIPS uyumlu algoritmaları kullanın**ve iletişim kutusunu açmak için **Enter** tuşuna basın.

1. Yerel **Güvenlik Ayarı** sekmesinde Etkin veya **Devre Dışı'yı**seçin ve ardından değişikliklerinizi kaydetmek için **Tamam'ı** seçin. **Enabled**

> [!WARNING]
> FIPS modunu etkinleştirmek bazı uygulamaların kırılmasına veya beklenmedik şekilde hareket etmesinin nedeni olabilir. Daha fazla bilgi için, ["FIPS modu" Artık Tavsiye Değil Neden](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/why-we-8217-re-not-recommending-8220-fips-mode-8221-anymore/ba-p/701037)blog yazısı bakın.

## <a name="additional-resources"></a>Ek kaynaklar

[FIPS 140 doğrulama microsoft belgeleri](/windows/security/threat-protection/fips-140-validation)

[FIPS 140-2: Şifreleme Modülleri için Güvenlik Gereksinimleri](https://csrc.nist.gov/publications/detail/fips/140/2/final) (NIST'den)

[Şifreleme Algoritma doğrulama programı: Doğrulama Notları](https://csrc.nist.gov/projects/cryptographic-algorithm-validation-program/Validation-Notes) (NIST'den)

Microsoft blog yazısı [neden artık "FIPS modu" Tavsiye değiliz](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/why-we-8217-re-not-recommending-8220-fips-mode-8221-anymore/ba-p/701037)

[SSH Sunucu Yapılandırması](https://www.ssh.com/ssh/sshd_config)

## <a name="see-also"></a>Ayrıca Bkz.

[Bir Linux projesini yapılandırma](configure-a-linux-project.md)\
[Linux CMake projesini yapılandırma](cmake-linux-project.md)\
[Uzak Linux bilgisayarınıza bağlanın](connect-to-your-remote-linux-computer.md)\
[Linux projenizi dağıtma, çalıştırma ve hata ayıklama](deploy-run-and-debug-your-linux-project.md)\
[CMake hata ayıklama oturumlarını yapılandırma](../build/configure-cmake-debugging-sessions.md)

::: moniker-end
