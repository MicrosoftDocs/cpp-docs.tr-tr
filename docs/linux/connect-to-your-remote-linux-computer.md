---
title: Visual Studio'da hedef Linux sisteminize bağlanın
description: Visual Studio C++ projesinin içinden uzak bir Linux makinesine veya Linux için Windows Alt Sistemine nasıl bağlanılır?
ms.date: 01/17/2020
ms.openlocfilehash: 624dce6bb05e4f4a961628e0c6f455e11c14dff8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364358"
---
# <a name="connect-to-your-target-linux-system-in-visual-studio"></a>Visual Studio'da hedef Linux sisteminize bağlanın

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range="vs-2017"

Bir Linux projesini uzak bir makineyi veya Linux için Windows Alt Sistemini (WSL) hedeflenebilmek için yapılandırabilirsiniz. Hem uzak makineler hem de WSL için Visual Studio 2017'de uzak bir bağlantı kurmanız gerekir.

::: moniker-end

::: moniker range="vs-2019"

Bir Linux projesini uzak bir makineyi veya Linux için Windows Alt Sistemini (WSL) hedeflenebilmek için yapılandırabilirsiniz. Uzak bir makine için Visual Studio'da uzak bir bağlantı kurmanız gerekir. WSL'ye bağlanmak için [WSL'ye bağlan](#connect-to-wsl) bölümüne geçin.

::: moniker-end

::: moniker range=">=vs-2017"

Visual Studio, uzak bir bağlantı kullanırken uzak makinede C++ Linux projeleri oluşturur. Fiziksel bir makine, bulutta bir VM veya WSL olması önemli değildir.
Projeyi oluşturmak için Visual Studio kaynak kodunu uzak Linux bilgisayarınıza kopyalar. Daha sonra, kod Visual Studio ayarlarına göre derlenir.

::: moniker-end

::: moniker range="vs-2019"

> [!NOTE]
> Visual Studio 2019 sürüm 16.5 ve daha sonra da güvenli destekler, Federal Bilgi İşlem Standardı (FIPS) uzaktan geliştirme için Linux sistemlerine 140-2 uyumlu şifreleme bağlantıları. FIPS uyumlu bir bağlantı kullanmak için, [FIPS uyumlu güvenli uzak Linux geliştirmesini ayarlama](set-up-fips-compliant-secure-remote-linux-development.md) adımlarını izleyin.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="set-up-the-ssh-server-on-the-remote-system"></a>Uzak sistemde SSH sunucusunu ayarlama

Linux sisteminizde ssh zaten kurulmamada ve çalışmıyorsa, yüklemek için aşağıdaki adımları izleyin. Bu makaledeki örnekler, OpenSSH sunucu sürümü 7.6 ile Ubuntu 18.04 LTS'yi kullanamaz. Ancak, openssh orta derecede yeni bir sürümünü kullanarak herhangi bir dağıtım için talimatlar aynı olmalıdır.

1. Linux sisteminde OpenSSH sunucusunu yükleyin ve başlatın:

   ```bash
   sudo apt install openssh-server
   sudo service ssh start
   ```

1. Sistem önyükleme yaparken ssh sunucusunun otomatik olarak başlatılmasını istiyorsanız, systemctl kullanarak etkinleştirin:

   ```bash
   sudo systemctl enable ssh
   ```

## <a name="set-up-the-remote-connection"></a>Uzak bağlantıyı ayarlama

1. Visual Studio'da, **Seçenekler** iletişim kutusunu açmak için menü çubuğundaki **Araçlar > Seçenekler'i** seçin. Ardından Bağlantı Yöneticisi iletişim kutusunu açmak için **Platform > Bağlantı Yöneticisi'ni seçin.**

   Visual Studio'da daha önce bir bağlantı kurmadıysanız, projenizi ilk kez oluşturduğunuzda, Visual Studio Bağlantı Yöneticisi iletişim kutusunu sizin için açar.

1. Bağlantı Yöneticisi iletişim kutusunda, yeni bir bağlantı eklemek için **Ekle** düğmesini seçin.

   ![Bağlantı Yöneticisi](media/settings_connectionmanager.png)

   Her iki senaryoda da **Uzak Sisteme Bağlan** penceresi görüntülenir.

   ![Uzak Sisteme Bağlan](media/connect.png)

1. Aşağıdaki bilgileri girin:

   | Girdi | Açıklama
   | ----- | ---
   | **Ev Sahibi Adı**           | Hedef cihazınızın adı veya IP adresi
   | **Bağlantı noktası**                | SSH hizmetinin üzerinde çalışan bağlantı noktası, genellikle 22
   | **Kullanıcı adı**           | Kullanıcı olarak kimlik doğrulaması
   | **Kimlik doğrulaması türü** | Parola ve Özel Anahtar desteklenir
   | **Parola**            | Girilen kullanıcı adının şifresi
   | **Özel anahtar dosyası**    | ssh bağlantısı için oluşturulan özel anahtar dosyası
   | **Parola**          | Yukarıda seçilen özel anahtarla kullanılan parola

   Kimlik doğrulaması için parola veya anahtar dosyası ve parola öbeği kullanabilirsiniz. Birçok geliştirme senaryosu için parola kimlik doğrulaması yeterlidir, ancak anahtar dosyaları daha güvenlidir. Zaten bir anahtar çiftiniz varsa, yeniden kullanmak mümkündür. Şu anda Visual Studio sadece uzak bağlantılar için RSA ve DSA tuşlarını destekler.

1. Uzak bilgisayara bağlantı denemek için **Bağlan** düğmesini seçin.

   Bağlantı başarılı olursa, Visual Studio uzak başlıkları kullanacak şekilde IntelliSense'i yapılandırır. Daha fazla bilgi için uzak [sistemlerdeki üstbilgiler için IntelliSense'e](configure-a-linux-project.md#remote_intellisense)bakın.

   Bağlantı başarısız olursa, değiştirilmesi gereken giriş kutuları kırmızı ile özetlenir.

   ![Bağlantı Yöneticisi Hatası](media/settings_connectionmanagererror.png)

   Kimlik doğrulaması için anahtar dosyaları kullanıyorsanız, hedef makinenin SSH sunucusunun düzgün çalıştırıldığından ve yapılandırıldığından emin olun.

   ::: moniker-end

   ::: moniker range="vs-2019"

## <a name="logging-for-remote-connections"></a>Uzak bağlantılar için günlük

   Bağlantı sorunlarını gidermeye yardımcı olmak için günlüğe kaydetmeyi etkinleştirebilirsiniz. Menü çubuğunda **Araçlar > Seçenekleri'ni**seçin. **Seçenekler** iletişim kutusunda, **Platform > Oturum Aç'ı seçin:**

   ![Uzaktan Günlük](media/remote-logging-vs2019.png)

   Günlükler bağlantıları, uzak makineye gönderilen tüm komutları (metin, çıkış kodu ve yürütme süresi) ve Visual Studio'dan kabuk için tüm çıktıları içerir. Günlük, Visual Studio'daki herhangi bir çapraz platform CMake projesi veya MSBuild tabanlı Linux projesi için çalışır.

   Çıktıyı bir dosyaya veya Çıktı penceresindeki **Çapraz Platform Günlüğe bölmesine** gidecek şekilde yapılandırabilirsiniz. MSBuild tabanlı Linux projeleri için, uzak makineye gönderilen MSBuild komutları, işlem dışı olarak yayıldığı için **Çıkış Penceresi'ne** yönlendirilir. Bunun yerine, "msbuild_" öneki yle bir dosyaya günlüğe kaydedilirler.

## <a name="command-line-utility-for-the-connection-manager"></a>Bağlantı Yöneticisi için komut satırı yardımcı programı  

**Visual Studio 2019 sürüm 16.5 veya sonrası**: ConnectionManager.exe, Visual Studio dışındaki uzaktan geliştirme bağlantılarını yönetmek için bir komut satırı yardımcı programıdır. Yeni bir geliştirme makinesi sağlama gibi görevler için yararlıdır. Veya, sürekli entegrasyon için Visual Studio kurmak için kullanabilirsiniz. Örnekler ve ConnectionManager komutuna tam bir başvuru için [ConnectionManager başvurusuna](connectionmanager-reference.md)bakın.  

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="tcp-port-forwarding"></a>TCP Bağlantı Noktası Yönlendirme

Visual Studio'nun Linux desteği, TCP bağlantı noktası yönlendirmeye bağımlıdır. TCP bağlantı noktası yönlendirmesi uzak sisteminizde devre dışı bırakılırsa **Rsync** ve **gdbserver** etkilenir. Bu bağımlılıksizi etkilerse, bu [öneri biletini](https://developercommunity.visualstudio.com/idea/840265/dont-rely-on-ssh-tcp-port-forwarding-for-c-remote.html) Geliştirici Topluluğu'nda oylayabilirsiniz.

rsync, [intelliSense tarafından kullanılmak üzere uzak sisteminizden Windows'a başlıkkopyalamak için](configure-a-linux-project.md#remote_intellisense)hem MSBuild tabanlı Linux projeleri hem de CMake projeleri tarafından kullanılır. TCP bağlantı noktası iletmesini etkinleştiremediyseniz, uzak üstbilginin otomatik karşıdan yüklerini devre dışı bırakın. Devre dışı kalmak için, **Araçlar > Seçenekleri > Çapraz Platform > Bağlantı Yöneticisi > Uzak Başlıklar IntelliSense Manager'ı**kullanın. Uzak sistemde TCP bağlantı noktası iletme etkin değilse, IntelliSense için uzak üstbilgi indirme başladığında bu hatayı görürsünüz:

![Üstbilgi Hatası](media/port-forwarding-headers-error.png)

rsync ayrıca Visual Studio'nun CMake desteği tarafından kaynak dosyaları uzak sisteme kopyalamak için de kullanılır. TCP bağlantı noktası iletmesini etkinleştiremezseniz, uzaktan kopyalama kaynakları yönteminiz olarak sftp'yi kullanabilirsiniz. sftp genellikle rsync daha yavaş, ancak TCP bağlantı noktası iletme bir bağımlılık yok. Uzaktan kopyalama kaynakları yönteminizi Uzaktan **CopySourcesMethod** özelliği ile [CMake Ayarları](../build/cmakesettings-reference.md#additional-settings-for-cmake-linux-projects)Düzenleyicisi'nde yönetebilirsiniz. Uzak sisteminizde TCP bağlantı noktası yönlendirmesi devre dışı bırakılırsa, CMake çıkış penceresinde rsync'i ilk kez çağırışında bir hata görürsünüz.

![Rsync Hatası](media/port-forwarding-copy-error.png)

gdbserver gömülü aygıtlarda hata ayıklama için kullanılabilir. TCP bağlantı noktası iletmesini etkinleştiremezseniz, tüm uzaktan hata ayıklama senaryoları için gdb kullanmanız gerekir. gdb, uzak bir sistemde hata ayıklama yaparken varsayılan olarak kullanılır.

## <a name="connect-to-wsl"></a>WSL'ye bağlan

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017'de, uzak bir Linux makinesinde kullandığınız gibi WSL'ye bağlanmak için de aynı adımları kullanırsınız. **Ana Bilgisayar Adı**için **localhost'u** kullanın.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 sürüm 16.1 Linux için [Windows Alt Sistemi (WSL)](/windows/wsl/about)ile C++ kullanmak için yerel destek ekledi. Bu, yerel WSL yüklemenizde doğrudan oluşturup hata ayıklama yapabileceğiniz anlamına gelir. Artık uzak bir bağlantı eklemenize veya SSH yapılandırmanız gerekmez. [WSL'nin nasıl yüklenirse yüklenebileceğiyle](/windows/wsl/install-win10) ilgili ayrıntıları burada bulabilirsiniz.

WSL yüklemenizi Visual Studio ile çalışacak şekilde yapılandırmak için aşağıdaki araçların yüklenmesi gerekir: gcc veya clang, gdb, make, ninja-build (yalnızca Visual Studio 2019 sürüm 16.6 veya sonraki sürüm kullanarak CMake projeleri için gereklidir), rsync ve zip. G++ derleyicisini de yükleyen bu komutu kullanarak apt kullanan dağıtımlara yükleyebilirsiniz:

```bash
sudo apt install g++ gdb make ninja-build rsync zip
```

Daha fazla bilgi için [Bkz. Linux iş yükünü İndir, yükle ve ayarla.](download-install-and-setup-the-linux-development-workload.md)

WSL için bir MSBuild projesini yapılandırmak için [bkz.](configure-a-linux-project.md) WSL için bir CMake projesini yapılandırmak için [bkz.](cmake-linux-project.md) WSL ile basit bir konsol uygulaması oluşturmak için adım adım yönergeleri takip etmek [için, Visual Studio 2019 ve Linux için Windows Alt Sistemi (WSL) ile C++](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/)bu tanıtım blog yazısı göz atın.

::: moniker-end

## <a name="see-also"></a>Ayrıca Bkz.

[Bir Linux projesini yapılandırma](configure-a-linux-project.md)\
[Linux CMake projesini yapılandırma](cmake-linux-project.md)\
[Linux projenizi dağıtma, çalıştırma ve hata ayıklama](deploy-run-and-debug-your-linux-project.md)\
[CMake hata ayıklama oturumlarını yapılandırma](../build/configure-cmake-debugging-sessions.md)
