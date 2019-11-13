---
title: Visual Studio 'da hedef Linux sisteminize bağlanma
description: Visual Studio C++ projesinin içinden bir uzak Linux makinesine veya Linux Için Windows alt sistemine bağlanma.
ms.date: 11/09/2019
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
ms.openlocfilehash: 6f7116ab5dc6c77f88d0787beac32d1c1e0a4716
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966569"
---
# <a name="connect-to-your-target-linux-system-in-visual-studio"></a>Visual Studio 'da hedef Linux sisteminize bağlanma

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

Bir Linux projesini, uzak bir makineyi veya Linux için Windows alt sistemini (WSL) hedefleyecek şekilde yapılandırabilirsiniz. Uzak makineler için ve Visual Studio 2017 üzerinde WSL için, uzak bir bağlantı ayarlamanız gerekir.

## <a name="connect-to-a-remote-linux-computer"></a>Uzak bir Linux bilgisayara bağlanma

Bir uzak Linux C++ SISTEMI (VM veya fiziksel makine) için bir Linux projesi oluştururken, Linux kaynak kodu uzak Linux bilgisayarınıza kopyalanır. Ardından, Visual Studio ayarları temel alınarak derlenir.

Bu uzak bağlantıyı kurmak için:

1. Projeyi ilk kez oluşturun. İsterseniz, el ile yeni bir giriş de oluşturabilirsiniz. **Araçlar > seçenekler**' i seçin, **platformlar arası > Bağlantı Yöneticisi** düğümünü açın ve sonra **Ekle** düğmesini seçin.

   ![Bağlantı Yöneticisi](media/settings_connectionmanager.png)

   Her iki senaryoda da **uzak sistem 'e Bağlan** penceresi görüntülenir.

   ![Uzak sisteme Bağlan](media/connect.png)

1. Aşağıdaki bilgileri girin:

   | Giriş | Açıklama
   | ----- | ---
   | **Ana bilgisayar adı**           | Hedef cihazınızın adı veya IP adresi
   | **Bağ**                | SSH hizmetinin üzerinde çalıştığı bağlantı noktası, genellikle 22
   | **Kullanıcı adı**           | Kimlik doğrulaması yapılacak Kullanıcı
   | **Kimlik doğrulama türü** | Parola ve özel anahtar her ikisi de desteklenir
   | **Parolayı**            | Girilen Kullanıcı adı için parola
   | **Özel anahtar dosyası**    | SSH bağlantısı için özel anahtar dosyası oluşturuldu
   | **Deyimi**          | Yukarıda seçilen özel anahtarla kullanılan parola

   Kimlik doğrulaması için bir parola ya da anahtar dosyası ve parola kullanabilirsiniz. Birçok geliştirme senaryosunda parola kimlik doğrulaması yeterlidir. Ortak/özel anahtar dosyası kullanmayı tercih ediyorsanız, yeni bir tane oluşturabilir veya [var olan](https://security.stackexchange.com/questions/10203/reusing-private-public-keys)bir dosyayı yeniden kullanabilirsiniz. Şu anda yalnızca RSA ve DSA anahtarları desteklenir.

   Aşağıdaki adımları izleyerek özel bir RSA anahtar dosyası oluşturabilirsiniz:

   1. Windows makinesinde, `ssh-keygen -t rsa`ile SSH anahtar çiftini oluşturun. Komut bir ortak anahtar ve özel anahtar oluşturur. Varsayılan olarak, `id_rsa.pub` ve `id_rsa`adlarını kullanarak anahtarları `C:\Users\%USERNAME%\.ssh`altına koyar.

   1. Windows 'tan ortak anahtarı Linux makinesine kopyalayın: `scp -p C:\Users\%USERNAME%\.ssh\id_rsa.pub user@hostname`.

   1. Linux sisteminde, anahtarı yetkili anahtarlar listesine ekleyin (ve dosyanın doğru izinlere sahip olduğundan emin olun): `cat ~/id_rsa.pub >> ~/.ssh/authorized_keys; chmod 600 ~/.ssh/authorized_keys`

1. Uzak bilgisayarla bağlantı kurmayı denemek için **Bağlan** düğmesini seçin.

   Bağlantı başarılı olursa, Visual Studio IntelliSense 'i uzak üstbilgileri kullanacak şekilde yapılandırmaya başlayacaktır. Daha fazla bilgi için bkz. [uzak sistemlerdeki üst bilgiler Için IntelliSense](configure-a-linux-project.md#remote_intellisense).

   Bağlantı başarısız olursa, değiştirilmesi gereken giriş kutuları kırmızı renkle gösterilir.

   ![Bağlantı Yöneticisi hatası](media/settings_connectionmanagererror.png)

   Kimlik doğrulaması için anahtar dosyaları kullanıyorsanız, hedef makinenin SSH sunucusunun çalıştığından ve doğru şekilde yapılandırıldığından emin olun.

   ::: moniker-end

   ::: moniker range="vs-2019"

   Bağlantı sorunlarını gidermeye yardımcı olmak üzere günlüğe yazmayı etkinleştirmek için, **platformlar arası > günlüğe kaydetme > araçlar > seçeneklere** gidin:

   ![Uzaktan günlüğe kaydetme](media/remote-logging-vs2019.png)

   Günlükler arasında bağlantılar, uzak makineye gönderilen tüm komutlar (bunların metin, çıkış kodu ve yürütme süresi) ve Visual Studio 'dan kabuğa giden tüm çıktılar bulunur. Günlüğe kaydetme, Visual Studio 'daki platformlar arası CMake projesi veya MSBuild tabanlı Linux projesi için geçerlidir.

   Çıktıyı bir dosyaya veya Çıkış Penceresi **çapraz platform günlüğü** bölmesine gidecek şekilde yapılandırabilirsiniz. MSBuild tabanlı Linux projeleri için, uzak makineye gönderilen MSBuild komutları, işlem dışı yayıldıklarından **Çıkış penceresi** yönlendirmez. Bunun yerine, "msbuild_" önekiyle birlikte bir dosyaya kaydedilir.

## <a name="tcp-port-forwarding"></a>TCP bağlantı noktası Iletme

Visual Studio 'nun Linux desteğinin TCP bağlantı noktası iletme bağımlılığı vardır. Uzak sisteminizde TCP bağlantı noktası iletme devre dışıysa, **rsync** ve **gdbserver** etkilenecek. 

rsync, hem MSBuild tabanlı Linux projeleri hem de CMake projeleri tarafından, [uzak sisteminizdeki üst bilgileri IntelliSense tarafından kullanılmak üzere Windows 'a kopyalamak](configure-a-linux-project.md#remote_intellisense)için kullanılır. TCP bağlantı noktası iletmeyi etkinleştirmezseniz, uzak üst bilgilerin otomatik indirilmesini devre dışı bırakın. Devre dışı bırakmak için **araçlar > seçenekler > platformlar arası > bağlantı yöneticisi > uzak üstbilgiler IntelliSense Yöneticisi**' ni kullanın. Uzak sistemde TCP bağlantı noktası iletme etkin değilse, IntelliSense için uzak üst bilgilerin indirilmesi başladığında bu hatayı görürsünüz:

![Üst bilgiler hatası](media/port-forwarding-headers-error.png)

Rsync, kaynak dosyaları uzak sisteme kopyalamak için Visual Studio 'nun CMake desteği tarafından da kullanılır. TCP bağlantı noktası iletmeyi etkinleştirebiliyorsanız, uzak kopya kaynakları yönteminiz olarak SFTP kullanabilirsiniz. SFTP genellikle rsync 'ten daha yavaştır, ancak TCP bağlantı noktası iletme bağımlılığı yoktur. Uzak kopya kaynakları yönteminizi [CMake ayarları düzenleyicisinde](../build/cmakesettings-reference.md#additional-settings-for-cmake-linux-projects) **remotecopysourcesmethod** özelliği ile yönetebilirsiniz. Uzak sisteminizde TCP bağlantı noktası iletme devre dışıysa, Csync çıkış penceresinde ilk kez rsync 'i çalıştırdığında bir hata görürsünüz.

![Rsync hatası](media/port-forwarding-copy-error.png)

Gdbserver, katıştırılmış cihazlarda hata ayıklama için kullanılabilir. TCP bağlantı noktası iletmeyi etkinleştirebiliyorsanız, tüm uzaktan hata ayıklama senaryolarında gdb kullanmanız gerekir. Uzak sistemdeki projelerde hata ayıklanırken, gdb varsayılan olarak kullanılır.

::: moniker-end

## <a name="connect-to-wsl"></a>WSL 'ye Bağlan

::: moniker range="vs-2017"

Visual Studio 2017 ' de, uzak bir Linux makinesi için kullandığınız için WSL 'ye bağlanmak üzere aynı adımları kullanırsınız. **Ana bilgisayar adı**için **localhost** kullanın.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 sürüm 16,1, C++ [Linux Için Windows alt sistemi (WSL)](/windows/wsl/about)ile kullanımı için yerel destek ekledi. Bu, yerel WSL yüklemenizde doğrudan oluşturabileceğiniz ve hata ayıklayacağınız anlamına gelir. Artık uzak bağlantı eklemeniz veya SSH yapılandırmanız gerekmez. [WSL 'nin nasıl yükleneceğine](/windows/wsl/install-win10) ilişkin ayrıntıları burada bulabilirsiniz.

WSL yüklemenizi Visual Studio ile çalışacak şekilde yapılandırmak için, aşağıdaki araçların yüklü olması gerekir: GCC veya Clang, gdb, Make, rsync ve zip. Bu komutları, bu komutu kullanarak apt 'yi kullanan distro 'lara 'ye yükleyebilirsiniz ve bu da g + + derleyicisini de yükler:

```bash
sudo apt install g++ gdb make rsync zip
```

Daha fazla bilgi için bkz. [Linux iş yükünü indirme, yükleme ve ayarlama](download-install-and-setup-the-linux-development-workload.md).

WSL için bir MSBuild projesi yapılandırmak üzere bkz. [Linux projesi yapılandırma](configure-a-linux-project.md). WSL için bir CMake projesi yapılandırmak için bkz. [Linux CMake projesini yapılandırma](cmake-linux-project.md). WSL ile basit bir konsol uygulaması oluşturmaya yönelik adım adım yönergeleri izlemek için, [ C++ Visual Studio 2019 ve Linux için Windows alt sistemi (WSL) ile birlikte](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/)bu giriş blog gönderisine göz atın.

::: moniker-end

## <a name="see-also"></a>Ayrıca Bkz.

[Linux projesi yapılandırma](configure-a-linux-project.md)\
[Linux CMake projesi yapılandırma](cmake-linux-project.md)\
[Linux projenizi dağıtın, çalıştırın ve hata ayıklayın](deploy-run-and-debug-your-linux-project.md)\
[CMake hata ayıklama oturumlarını yapılandırma](../build/configure-cmake-debugging-sessions.md)
