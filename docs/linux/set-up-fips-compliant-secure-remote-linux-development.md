---
title: FIPS uyumlu güvenli uzak Linux geliştirmeyi ayarlama
description: Uzaktan geliştirme için Visual Studio ile Linux makinesi arasında FIPS ile uyumlu bir şifreleme bağlantısı kurma.
ms.date: 01/17/2020
ms.openlocfilehash: 9a0e87f4ddf69bf489b52d4f83934d3279f2d085
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76520895"
---
# <a name="set-up-fips-compliant-secure-remote-linux-development"></a>FIPS uyumlu güvenli uzak Linux geliştirmeyi ayarlama

::: moniker range="<=vs-2017"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir. FIPS uyumlu güvenli uzak Linux geliştirme, Visual Studio 2019 sürüm 16,5 ve sonraki sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range="vs-2019"

Federal bilgi Işleme standardı (FIPS) yayını 140-2, şifreleme modülleri için ABD devlet standardıdır. Standart uygulamaları NıST tarafından onaylanır. Windows, [FIPS uyumlu şifreleme modülleri için desteği doğruladı](/windows/security/threat-protection/fips-140-validation). Visual Studio 2019 sürüm 16,5 ve sonraki sürümlerde, Linux sisteminize Uzaktan geliştirme için güvenli, FIPS uyumlu bir şifreleme bağlantısı kullanabilirsiniz.

Visual Studio ile uzak Linux sisteminiz arasında güvenli, FIPS uyumlu bir bağlantı kurma hakkında daha fazla bilgiyi burada bulabilirsiniz. Bu kılavuz, Visual Studio 'da CMake veya MSBuild Linux projelerini yapılandırdığınızda geçerlidir. Bu makale, [uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md)bölümündeki bağlantı yönergelerinin FIPS uyumlu sürümüdür.

## <a name="prepare-a-fips-compliant-connection"></a>FIPS uyumlu bir bağlantı hazırlama

Visual Studio ile uzak Linux sisteminiz arasında FIPS uyumlu, şifreli olarak güvenli bir SSH bağlantısı kullanmak için bazı hazırlıklar gerekir. FIPS-140-2 uyumluluğu için, Visual Studio yalnızca RSA anahtarlarını destekler.

Bu makaledeki örneklerde, OpenSSH Server sürüm 7,6 ile Ubuntu 18,04 LTS kullanılır. Ancak, yönergeler, OpenSSH 'nin son zamanlarda oluşan sürümü kullanılarak herhangi bir deden dolayı aynı olmalıdır.

### <a name="to-set-up-the-ssh-server-on-the-remote-system"></a>Uzak sistemde SSH sunucusunu ayarlamak için

1. Linux sisteminde, OpenSSH sunucusunu yükleyip başlatın:

   ```bash
   sudo apt install openssh-server
   sudo service ssh start
   ```

1. SSH sunucusunun sistem önyüklendiğinde otomatik olarak başlamasını isterseniz, systemctl kullanarak etkinleştirin:

   ```bash
   sudo systemctl enable ssh
   ```

1. */Etc/ssh/sshd_config* öğesini kök olarak açın. Aşağıdaki satırları düzenleyin (veya yoksa ekleyin):

   ```config
   Ciphers aes256-cbc,aes192-cbc,aes128-cbc,3des-cbc
   HostKeyAlgorithms ssh-rsa
   KexAlgorithms diffie-hellman-group-exchange-sha256,diffie-hellman-group-exchange-sha1,diffie-hellman-group14-sha1
   MACs hmac-sha2-256,hmac-sha1
   ```

   > [!NOTE]
   > ssh-rsa, FIPS uyumlu tek konak anahtar algoritması Ile desteklenir. AES\*-Mrk algoritmaları ayrıca FIPS uyumludur, ancak Visual Studio 'daki uygulama onaylanmamış değildir. ECDH-\* anahtar değişim algoritmaları FIPS uyumludur, ancak Visual Studio bunları desteklemez.

   Bu seçeneklerle sınırlı değilsiniz. SSH 'yi ek şifrelemeler, ana bilgisayar anahtar algoritmaları vb. kullanacak şekilde yapılandırabilirsiniz. Göz önünde bulundurmanız isteyebileceğiniz bazı ilgili güvenlik seçenekleri şunlardır `PermitRootLogin`, `PasswordAuthentication`ve `PermitEmptyPasswords`. Daha fazla bilgi için, sshd_config için Man sayfasına veya [SSH sunucusu yapılandırması](https://www.ssh.com/ssh/sshd_config)makalesine bakın.

1. Sshd_config kaydettikten ve kapattıktan sonra, yeni yapılandırmayı uygulamak için SSH sunucusunu yeniden başlatın:

   ```bash
   sudo service ssh restart
   ```

Ardından, Windows bilgisayarınızda bir RSA anahtar çifti oluşturacaksınız. Daha sonra, SSH tarafından kullanılmak üzere ortak anahtarı uzak Linux sistemine kopyalayacaksınız.

### <a name="to-create-and-use-an-rsa-key-file"></a>Bir RSA anahtar dosyası oluşturmak ve kullanmak için

1. Windows makinesinde, şu komutu kullanarak bir ortak/özel RSA anahtar çifti oluşturun:

   ```cmd
   ssh-keygen -t rsa -b 4096
   ```

   Komut bir ortak anahtar ve özel anahtar oluşturur. Anahtarlar varsayılan olarak *% userprofile%\\. ssh\\id_rsa* ve *% userprofile%\\. SSH\\id_rsa. pub*' a kaydedilir. (PowerShell 'de, cmd makrosu yerine `$env:USERPROFILE` kullanın `%USERPROFILE%`) Anahtar adını değiştirirseniz, aşağıdaki adımlarda değiştirilen adı kullanın.  Daha fazla güvenlik için bir parola kullanmanızı öneririz.

1. Windows 'tan ortak anahtarı Linux makinesine kopyalayın:

   ```cmd
   scp %USERPROFILE%\.ssh\id_rsa.pub user@hostname:
   ```

1. Linux sisteminde, anahtarı yetkili anahtarlar listesine ekleyin ve dosyanın doğru izinlere sahip olduğundan emin olun:

   ```bash
   cat ~/id_rsa.pub >> ~/.ssh/authorized_keys
   chmod 600 ~/.ssh/authorized_keys
   ```

1. Şimdi, yeni anahtarın SSH 'de çalışıp çalışmadığını görmek için test edebilirsiniz. Windows 'da oturum açmak için kullanın:

    ```cmd
    ssh -i %USERPROFILE%\.ssh\id_rsa user@hostname
    ```

SSH 'yi başarıyla ayarlamış, şifreleme anahtarları oluşturmuş ve dağıtmış ve bağlantınızı test tamamladınız. Şimdi Visual Studio bağlantısını ayarlamaya hazırsınız.

## <a name="connect-to-the-remote-system-in-visual-studio"></a>Visual Studio 'da uzak sisteme bağlanma

1. Visual Studio 'da, **Seçenekler** iletişim kutusunu açmak için menü çubuğunda **Araçlar > Seçenekler** ' i seçin. Sonra, bağlantı Yöneticisi iletişim kutusunu açmak için **platformlar arası > bağlantı Yöneticisi** ' ni seçin.

   Daha önce Visual Studio 'da bir bağlantı ayarlamadıysanız, projenizi ilk kez yapılandırdığınızda, Visual Studio sizin için bağlantı Yöneticisi iletişim kutusunu açar.

1. Bağlantı Yöneticisi iletişim kutusunda yeni bir bağlantı eklemek için **Ekle** düğmesini seçin.

   ![Bağlantı Yöneticisi](media/settings_connectionmanager.png)

   **Uzak sisteme Bağlan** penceresi görüntülenir.

   ![Uzak sisteme Bağlan](media/connect.png)

1. **Uzak sisteme Bağlan** iletişim kutusunda, uzak makinenizin bağlantı ayrıntılarını girin.

   | Giriş | Açıklama
   | ----- | ---
   | **Ana bilgisayar adı**           | Hedef cihazınızın adı veya IP adresi
   | **Bağlantı noktası**                | SSH hizmetinin üzerinde çalıştığı bağlantı noktası, genellikle 22
   | **Kullanıcı adı**           | Kimlik doğrulaması yapılacak Kullanıcı
   | **Kimlik doğrulama türü** | FIPS uyumlu bir bağlantı için özel anahtar seçin
   | **Özel anahtar dosyası**    | SSH bağlantısı için özel anahtar dosyası oluşturuldu
   | **Deyimi**          | Yukarıda seçilen özel anahtarla kullanılan parola

   Kimlik doğrulama türünü **özel anahtarla**değiştirin. Özel anahtar **dosyası** alanına özel anahtarınızın yolunu girin. Bunun yerine özel anahtar dosyanıza gitmek için, **tarayıcı** düğmesini kullanabilirsiniz. Ardından, **parola** alanında özel anahtar dosyanızı şifrelemek için kullanılan parolayı girin.

1. Uzak bilgisayarla bağlantı kurmayı denemek için **Bağlan** düğmesini seçin.

   Bağlantı başarılı olursa, Visual Studio IntelliSense 'i uzak üstbilgileri kullanacak şekilde yapılandırır. Daha fazla bilgi için bkz. [uzak sistemlerdeki üst bilgiler Için IntelliSense](configure-a-linux-project.md#remote_intellisense).

   Bağlantı başarısız olursa, değiştirilmesi gereken giriş kutuları kırmızı renkle gösterilir.

   ![Bağlantı Yöneticisi hatası](media/settings_connectionmanagererror.png)

   Bağlantınızın sorunlarını giderme hakkında daha fazla bilgi için bkz. [uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md).

## <a name="command-line-utility-for-the-connection-manager"></a>Bağlantı Yöneticisi için komut satırı yardımcı programı  

**Visual studio 2019 sürüm 16,5 veya üzeri**: ConnectionManager. exe, Visual Studio dışında Uzaktan geliştirme bağlantılarını yönetmeye yönelik bir komut satırı yardımcı programıdır. Yeni bir geliştirme makinesi sağlama gibi görevler için faydalıdır. Ayrıca, bu uygulamayı kullanarak sürekli tümleştirme için Visual Studio 'Yu ayarlayabilirsiniz. Örnek olarak, ConnectionManager komutuna yönelik bir başvuru ve bkz. [ConnectionManager başvurusu](connectionmanager-reference.md).  

## <a name="optional-enable-or-disable-fips-mode"></a>İsteğe bağlı: FIPS modunu etkinleştirme veya devre dışı bırakma

Windows 'da FIPS modunu genel olarak etkinleştirmek mümkündür.

1. FIPS modunu etkinleştirmek için **Windows + R** tuşlarına basarak Çalıştır iletişim kutusunu açın ve sonra gpedit. msc ' yi çalıştırın.

1. **Yerel bilgisayar ilkesi > bilgisayar yapılandırması > Windows ayarları > güvenlik ayarları > yerel ilkeler** ' i genişletin ve **güvenlik seçenekleri**' ni seçin.

1. **İlke**altında **Sistem şifreleme: şifreleme, karma ve imzalama için FIPS Ile uyumlu algoritmalar kullanın**ve ardından Iletişim kutusunu açmak için **ENTER** tuşuna basın.

1. **Yerel güvenlik ayarı** sekmesinde **etkin** veya **devre dışı**' yı seçin ve ardından değişikliklerinizi kaydetmek için **Tamam** ' ı seçin.

> [!WARNING]
> FIPS modunu etkinleştirmek bazı uygulamaların beklenmedik şekilde kesilmesine veya davranmasına neden olabilir. Daha fazla bilgi için [artık "FIPS modunu" önermediğimiz](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/why-we-8217-re-not-recommending-8220-fips-mode-8221-anymore/ba-p/701037)blog gönderisine bakın.

## <a name="additional-resources"></a>Ek kaynaklar

[FIPS 140 doğrulamasında Microsoft belgeleri](/windows/security/threat-protection/fips-140-validation)

[Fıps 140-2: şifreleme modülleri Için güvenlik gereksinimleri](https://csrc.nist.gov/publications/detail/fips/140/2/final) (NIST 'den)

[Şifreleme algoritması doğrulama programı: doğrulama notları](https://csrc.nist.gov/projects/cryptographic-algorithm-validation-program/Validation-Notes) (NIST 'den)

Microsoft blog gönderisi [artık "FIPS modunu" önermediğimiz](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/why-we-8217-re-not-recommending-8220-fips-mode-8221-anymore/ba-p/701037)

[SSH sunucusu yapılandırması](https://www.ssh.com/ssh/sshd_config)

## <a name="see-also"></a>Ayrıca Bkz.

[Linux projesi yapılandırma](configure-a-linux-project.md)\
[Linux CMake projesi yapılandırma](cmake-linux-project.md)\
[Uzak Linux bilgisayarınıza bağlanın](connect-to-your-remote-linux-computer.md)\
[Linux projenizi dağıtın, çalıştırın ve hata ayıklayın](deploy-run-and-debug-your-linux-project.md)\
[CMake hata ayıklama oturumlarını yapılandırma](../build/configure-cmake-debugging-sessions.md)

::: moniker-end
