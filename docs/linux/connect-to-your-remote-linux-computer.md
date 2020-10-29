---
title: Visual Studio 'da hedef Linux sisteminize bağlanma
description: Visual Studio C++ projesinin içinden bir uzak Linux makinesine veya Linux için Windows alt sistemine bağlanma.
ms.date: 01/17/2020
ms.openlocfilehash: da74d1c735a29304fdf46e920eac45580f386259
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921795"
---
# <a name="connect-to-your-target-linux-system-in-visual-studio"></a>Visual Studio 'da hedef Linux sisteminize bağlanma

::: moniker range="msvc-140"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range="msvc-150"

Bir Linux projesini, uzak bir makineyi veya Linux için Windows alt sistemini (WSL) hedefleyecek şekilde yapılandırabilirsiniz. Hem uzak makinelerde hem de WSL için, Visual Studio 2017 ' de uzak bağlantı ayarlamanız gerekir.

::: moniker-end

::: moniker range="msvc-160"

Bir Linux projesini, uzak bir makineyi veya Linux için Windows alt sistemini (WSL) hedefleyecek şekilde yapılandırabilirsiniz. Uzak makine için, Visual Studio 'da uzak bağlantı ayarlamanız gerekir. WSL 'ye bağlanmak için, [WSL 'ye Bağlan](#connect-to-wsl) bölümüne atlayın.

::: moniker-end

::: moniker range=">=msvc-150"

Uzak bir bağlantı kullanırken, Visual Studio uzak makinede C++ Linux projelerini oluşturur. Fiziksel bir makine, buluttaki bir VM veya WSL olması buna karşı değildir.
Projeyi derlemek için, Visual Studio kaynak kodu uzak Linux bilgisayarınıza kopyalar. Daha sonra kod, Visual Studio ayarlarına bağlı olarak derlenir.

::: moniker-end

::: moniker range="msvc-160"

> [!NOTE]
> Visual Studio 2019 sürüm 16,5 ve üzeri sürümleri, Uzaktan geliştirme için Linux sistemlerine yönelik güvenli, Federal bilgi Işleme standardı (FIPS) 140-2 ile uyumlu şifreleme bağlantılarını da destekler. FIPS uyumlu bir bağlantı kullanmak için bunun yerine [FIPS uyumlu güvenli uzak Linux geliştirme ayarlama](set-up-fips-compliant-secure-remote-linux-development.md) bölümündeki adımları izleyin.

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="set-up-the-ssh-server-on-the-remote-system"></a>Uzak sistemde SSH sunucusunu ayarlama

SSH zaten Linux sisteminizde ayarlanmamışsa ve çalışmıyorsa, yüklemek için aşağıdaki adımları izleyin. Bu makaledeki örneklerde, OpenSSH Server sürüm 7,6 ile Ubuntu 18,04 LTS kullanılır. Ancak, yönergeler, OpenSSH 'nin son zamanlarda oluşan sürümü kullanılarak herhangi bir deden dolayı aynı olmalıdır.

1. Linux sisteminde, OpenSSH sunucusunu yükleyip başlatın:

   ```bash
   sudo apt install openssh-server
   sudo service ssh start
   ```

1. SSH sunucusunun sistem önyüklendiğinde otomatik olarak başlamasını isterseniz, systemctl kullanarak etkinleştirin:

   ```bash
   sudo systemctl enable ssh
   ```

## <a name="set-up-the-remote-connection"></a>Uzak bağlantıyı ayarlama

1. Visual Studio 'da, **Seçenekler** iletişim kutusunu açmak için menü çubuğunda **Araçlar > seçenekler** ' i seçin. Sonra, bağlantı Yöneticisi iletişim kutusunu açmak için **platformlar arası > bağlantı Yöneticisi** ' ni seçin.

   Daha önce Visual Studio 'da bir bağlantı ayarlamadıysanız, projenizi ilk kez yapılandırdığınızda, Visual Studio sizin için bağlantı Yöneticisi iletişim kutusunu açar.

1. Bağlantı Yöneticisi iletişim kutusunda yeni bir bağlantı eklemek için **Ekle** düğmesini seçin.

   ![Bağlantı Yöneticisi](media/settings_connectionmanager.png)

   Her iki senaryoda da **uzak sistem 'e Bağlan** penceresi görüntülenir.

   ![Uzak sisteme Bağlan](media/connect.png)

1. Aşağıdaki bilgileri girin:

   | Giriş | Açıklama
   | ----- | ---
   | **Konak Adı**           | Hedef cihazınızın adı veya IP adresi
   | **Bağlantı noktası**                | SSH hizmetinin üzerinde çalıştığı bağlantı noktası, genellikle 22
   | **Kullanıcı adı**           | Kimlik doğrulaması yapılacak Kullanıcı
   | **Kimlik doğrulaması türü** | Parola ve özel anahtar her ikisi de desteklenir
   | **Parola**            | Girilen Kullanıcı adı için parola
   | **Özel anahtar dosyası**    | SSH bağlantısı için özel anahtar dosyası oluşturuldu
   | **Deyimi**          | Yukarıda seçilen özel anahtarla kullanılan parola

   Kimlik doğrulaması için bir parola ya da anahtar dosyası ve parola kullanabilirsiniz. Birçok geliştirme senaryosunda parola kimlik doğrulaması yeterlidir, ancak anahtar dosyaları daha güvenlidir. Zaten bir anahtar çiftiniz varsa, yeniden kullanmak mümkündür. Şu anda Visual Studio, uzak bağlantılar için yalnızca RSA ve DSA anahtarlarını destekliyor.

1. Uzak bilgisayarla bağlantı kurmayı denemek için **Bağlan** düğmesini seçin.

   Bağlantı başarılı olursa, Visual Studio IntelliSense 'i uzak üstbilgileri kullanacak şekilde yapılandırır. Daha fazla bilgi için bkz. [uzak sistemlerdeki üst bilgiler Için IntelliSense](configure-a-linux-project.md#remote_intellisense).

   Bağlantı başarısız olursa, değiştirilmesi gereken giriş kutuları kırmızı renkle gösterilir.

   ![Bağlantı Yöneticisi hatası](media/settings_connectionmanagererror.png)

   Kimlik doğrulaması için anahtar dosyaları kullanıyorsanız, hedef makinenin SSH sunucusunun çalıştığından ve doğru şekilde yapılandırıldığından emin olun.

   ::: moniker-end

   ::: moniker range="msvc-160"

## <a name="logging-for-remote-connections"></a>Uzak bağlantılar için günlüğe kaydetme

   Bağlantı sorunlarını gidermeye yardımcı olmak için günlük kaydını etkinleştirebilirsiniz. Menü çubuğunda **araçlar > seçenekler** ' i seçin. **Seçenekler** iletişim kutusunda, **platformlar arası > günlük kaydını** seçin:

   ![Uzaktan günlüğe kaydetme](media/remote-logging-vs2019.png)

   Günlükler arasında bağlantılar, uzak makineye gönderilen tüm komutlar (bunların metin, çıkış kodu ve yürütme süresi) ve Visual Studio 'dan kabuğa giden tüm çıktılar bulunur. Günlüğe kaydetme, Visual Studio 'daki platformlar arası CMake projesi veya MSBuild tabanlı Linux projesi için geçerlidir.

   Çıktıyı bir dosyaya veya çıkış penceresindeki **platformlar arası günlüğe kaydetme** bölmesine gidecek şekilde yapılandırabilirsiniz. MSBuild tabanlı Linux projeleri için, uzak makineye gönderilen MSBuild komutları, işlem dışı yayıldıklarından **Çıkış penceresi** yönlendirmez. Bunun yerine, "msbuild_" önekiyle birlikte bir dosyaya kaydedilir.

## <a name="command-line-utility-for-the-connection-manager"></a>Bağlantı Yöneticisi için komut satırı yardımcı programı  

**Visual studio 2019 sürüm 16,5 veya üzeri** : ConnectionManager.exe, Visual Studio dışında Uzaktan geliştirme bağlantılarını yönetmeye yönelik bir komut satırı yardımcı programıdır. Yeni bir geliştirme makinesi sağlama gibi görevler için faydalıdır. Ayrıca, bu uygulamayı kullanarak sürekli tümleştirme için Visual Studio 'Yu ayarlayabilirsiniz. Örnek olarak, ConnectionManager komutuna yönelik bir başvuru ve bkz. [ConnectionManager başvurusu](connectionmanager-reference.md).  

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="tcp-port-forwarding"></a>TCP bağlantı noktası Iletme

Visual Studio 'nun Linux desteğinin TCP bağlantı noktası iletme bağımlılığı vardır. Uzak sisteminizde TCP bağlantı noktası iletme devre dışıysa, **rsync** ve **gdbserver** etkilenir. Bu bağımlılık etkilenirse, geliştirici topluluğu 'nda bu [öneri biletini](https://developercommunity.visualstudio.com/idea/840265/dont-rely-on-ssh-tcp-port-forwarding-for-c-remote.html) kullanabilirsiniz.

rsync, hem MSBuild tabanlı Linux projeleri hem de CMake projeleri tarafından, [uzak sisteminizdeki üst bilgileri IntelliSense tarafından kullanılmak üzere Windows 'a kopyalamak](configure-a-linux-project.md#remote_intellisense)için kullanılır. TCP bağlantı noktası iletmeyi etkinleştirmezseniz, uzak üst bilgilerin otomatik indirilmesini devre dışı bırakın. Devre dışı bırakmak için **araçlar > seçenekler > platformlar arası > bağlantı yöneticisi > uzak üstbilgiler IntelliSense Yöneticisi** ' ni kullanın. Uzak sistemde TCP bağlantı noktası iletme etkin değilse, IntelliSense için uzak üst bilgilerin indirilmesi başladığında bu hatayı görürsünüz:

![Üst bilgiler hatası](media/port-forwarding-headers-error.png)

rsync, kaynak dosyaları uzak sisteme kopyalamak için Visual Studio 'nun CMake desteği tarafından da kullanılır. TCP bağlantı noktası iletmeyi etkinleştirebiliyorsanız, uzak kopya kaynakları yönteminiz olarak SFTP kullanabilirsiniz. SFTP genellikle rsync 'ten daha yavaştır, ancak TCP bağlantı noktası iletme bağımlılığı yoktur. Uzak kopya kaynakları yönteminizi [CMake ayarları düzenleyicisinde](../build/cmakesettings-reference.md#additional-settings-for-cmake-linux-projects) **remotecopysourcesmethod** özelliği ile yönetebilirsiniz. Uzak sisteminizde TCP bağlantı noktası iletme devre dışıysa, Csync çıkış penceresinde ilk kez rsync 'i çalıştırdığında bir hata görürsünüz.

![Rsync hatası](media/port-forwarding-copy-error.png)

gdbserver, katıştırılmış cihazlarda hata ayıklama için kullanılabilir. TCP bağlantı noktası iletmeyi etkinleştirebiliyorsanız, tüm uzaktan hata ayıklama senaryolarında gdb kullanmanız gerekir. uzak sistemdeki projelerde hata ayıklanırken, gdb varsayılan olarak kullanılır.

## <a name="connect-to-wsl"></a>WSL 'ye Bağlan

::: moniker-end

::: moniker range="msvc-150"

Visual Studio 2017 ' de, uzak bir Linux makinesi için kullandığınız için WSL 'ye bağlanmak üzere aynı adımları kullanırsınız. **Ana bilgisayar adı** için **localhost** kullanın.

::: moniker-end

::: moniker range="msvc-160"

Visual Studio 2019 sürüm 16,1, [Linux Için Windows alt sistemi (WSL)](/windows/wsl/about)ile C++ kullanımı için yerel destek ekledi. Bu, yerel WSL yüklemenizde doğrudan oluşturabileceğiniz ve hata ayıklayacağınız anlamına gelir. Artık uzak bağlantı eklemeniz veya SSH yapılandırmanız gerekmez. [WSL 'nin nasıl yükleneceğine](/windows/wsl/install-win10) ilişkin ayrıntıları burada bulabilirsiniz.

WSL yüklemenizi Visual Studio ile çalışacak şekilde yapılandırmak için aşağıdaki araçların yüklü olması gerekir: GCC veya Clang, gdb, Make, dokja-Build (yalnızca Visual Studio 2019 sürüm 16,6 veya üstünü kullanan CMake projeleri için gereklidir), rsync ve zip. Bu komutları, bu komutu kullanarak apt 'yi kullanan distro 'lara 'ye yükleyebilirsiniz ve bu da g + + derleyicisini de yükler:

```bash
sudo apt install g++ gdb make ninja-build rsync zip
```

Daha fazla bilgi için bkz. [Linux iş yükünü indirme, yükleme ve ayarlama](download-install-and-setup-the-linux-development-workload.md).

WSL için bir MSBuild projesi yapılandırmak üzere bkz. [Linux projesi yapılandırma](configure-a-linux-project.md). WSL için bir CMake projesi yapılandırmak için bkz. [Linux CMake projesini yapılandırma](cmake-linux-project.md). WSL ile basit bir konsol uygulaması oluşturmaya yönelik adım adım yönergeleri izlemek için, [Visual Studio 2019 ve Linux Için Windows alt sistemi (WSL) ile C++](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/)üzerinde bu giriş blog gönderisine göz atın.

::: moniker-end

## <a name="see-also"></a>Ayrıca Bkz.

[Linux projesi yapılandırma](configure-a-linux-project.md)\
[Linux CMake projesi yapılandırma](cmake-linux-project.md)\
[Linux projenizi dağıtın, çalıştırın ve hatalarını ayıklayın](deploy-run-and-debug-your-linux-project.md)\
[CMake hata ayıklama oturumlarını yapılandırma](../build/configure-cmake-debugging-sessions.md)
