---
title: Visual Studio 'da hedef Linux sisteminize bağlanma
description: Visual Studio C++ projesinin içinden bir uzak Linux makinesine veya WSL 'ye bağlanma.
ms.date: 06/19/2019
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
ms.openlocfilehash: cd107f096e4395f93775ee80b889cc0efd627166
ms.sourcegitcommit: 610751254a01cba6ad15fb1e1764ecb2e71f66bf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2019
ms.locfileid: "68313425"
---
# <a name="connect-to-your-target-linux-system-in-visual-studio"></a>Visual Studio 'da hedef Linux sisteminize bağlanma

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

Bir Linux projesini, uzak bir makineyi veya Linux için Windows alt sistemini (WSL) hedefleyecek şekilde yapılandırabilirsiniz. Uzak makineler için ve Visual Studio 2017 üzerinde WSL için, uzak bir bağlantı ayarlamanız gerekir. 

## <a name="connect-to-a-remote-linux-computer"></a>Uzak bir Linux bilgisayara bağlanma

Bir uzak Linux C++ SISTEMI (VM veya fiziksel makine) için bir Linux projesi oluştururken, Linux kaynak kodu uzak Linux bilgisayarınıza kopyalanır ve ardından Visual Studio ayarlarına bağlı olarak derlenir.

Bu uzak bağlantıyı kurmak için:

1. Projeyi ilk kez oluşturun veya **araçlar > seçenekler** ' i seçip **platformlar arası > Bağlantı Yöneticisi** düğümünü açın ve **Ekle** düğmesine tıklayın.

   ![Bağlantı Yöneticisi](media/settings_connectionmanager.png)

   Her iki senaryoda da **uzak sistem 'e Bağlan** penceresi görüntülenir.

   ![Uzak sisteme Bağlan](media/connect.png)

1. Aşağıdaki bilgileri girin:

   | Giriş | Açıklama
   | ----- | ---
   | **Ana bilgisayar adı**           | Hedef cihazınızın adı veya IP adresi
   | **Bağ**                | SSH hizmetinin üzerinde çalıştığı bağlantı noktası, genellikle 22
   | **Kullanıcı adı**           | Kimlik doğrulaması yapılacak Kullanıcı
   | **Kimlik doğrulama türü** | Parola veya özel anahtar desteklenir
   | **Parola**            | Girilen Kullanıcı adı için parola
   | **Özel anahtar dosyası**    | SSH bağlantısı için özel anahtar dosyası oluşturuldu
   | **Deyimi**          | Yukarıda seçilen özel anahtarla kullanılan parola

   Kimlik doğrulaması için bir parola ya da anahtar dosyası ve parola kullanabilirsiniz. Birçok geliştirme senaryosunda parola kimlik doğrulaması yeterlidir. Ortak/özel anahtar dosyası kullanmayı tercih ediyorsanız, yeni bir tane oluşturabilir veya [var olan](https://security.stackexchange.com/questions/10203/reusing-private-public-keys)bir dosyayı yeniden kullanabilirsiniz. Şu anda yalnızca RSA ve DSA anahtarları desteklenir. 
   
   Aşağıdaki adımları izleyerek özel bir RSA anahtar dosyası oluşturabilirsiniz:

    1. Windows makinesinde, ile `ssh-keygen -t rsa`SSH anahtar çiftini oluşturun. Bu, bir ortak anahtar ve özel anahtar oluşturur. Varsayılan olarak anahtarlar ve `C:\Users\%USERNAME%\.ssh` `id_rsa.pub` `id_rsa`adlarıyla birlikte yerleştirilir.

    1. Windows 'tan ortak anahtarı Linux makinesine kopyalayın: `scp -p C:\Users\%USERNAME%\.ssh\id_rsa.pub user@hostname`.

    1. Linux sisteminde, anahtarı yetkili anahtarlar listesine ekleyin (ve dosyanın doğru izinlere sahip olduğundan emin olun):`cat ~/id_rsa.pub >> ~/.ssh/authorized_keys; chmod 600 ~/.ssh/authorized_keys`

1. Uzak bilgisayara bir bağlantı denemek için **Bağlan** düğmesine tıklayın. 

   Bağlantı başarılı olursa, Visual Studio IntelliSense 'i uzak üstbilgileri kullanacak şekilde yapılandırmaya başlayacaktır. Daha fazla bilgi için bkz. [uzak sistemlerdeki üst bilgiler Için IntelliSense](configure-a-linux-project.md#remote_intellisense).

   Bağlantı başarısız olursa, değiştirilmesi gereken giriş kutuları kırmızı renkle gösterilir.

   ![Bağlantı Yöneticisi hatası](media/settings_connectionmanagererror.png)

   Kimlik doğrulaması için anahtar dosyaları kullanıyorsanız, hedef makinenin SSH sunucusunun çalıştığından ve doğru şekilde yapılandırıldığından emin olun.

   ::: moniker-end

   ::: moniker range="vs-2019"

   Bağlantı sorunlarını gidermeye yardımcı olmak üzere günlüğe yazmayı etkinleştirmek için, **platformlar arası > günlüğe kaydetme > araçlar > seçeneklere** gidin:

   ![Uzaktan günlüğe kaydetme](media/remote-logging-vs2019.png)

   Günlükler arasında bağlantılar, uzak makineye gönderilen tüm komutlar (bunların metin, çıkış kodu ve yürütme süresi) ve Visual Studio 'dan kabuğa giden tüm çıktılar bulunur. Günlüğe kaydetme, Visual Studio 'daki platformlar arası CMake projesi veya MSBuild tabanlı Linux projesi için geçerlidir.

   Çıktıyı bir dosyaya veya Çıkış Penceresi **çapraz platform günlüğü** bölmesine gidecek şekilde yapılandırabilirsiniz. MSBuild tabanlı Linux projeleri için, MSBuild tarafından uzak makineye verilen komutlar, işlem dışı yayıldıklarından **Çıkış penceresi** yönlendirmemektedir. Bunun yerine, "msbuild_" ön ekine sahip bir dosyaya kaydedilir.

   ::: moniker-end

## <a name="connect-to-wsl"></a>WSL 'ye Bağlan

::: moniker range="vs-2017"

Visual Studio 2017 ' de, bu makalenin önceki kısımlarında açıklandığı gibi, uzak bir Linux makinesine bağlanırken aynı adımları kullanarak WSL 'ye bağlanırsınız. **Ana bilgisayar adı**için **localhost** kullanın.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 sürüm 16,1, C++ [Linux Için Windows alt sistemi (WSL)](https://docs.microsoft.com/windows/wsl/about)ile kullanımı için yerel destek ekledi.  Bu, artık yerel WSL yüklemenizde derleme ve hata ayıklama yapmak için uzak bir bağlantı eklemeniz veya SSH yapılandırmanız gerekmediği anlamına gelir. [WSL 'nin nasıl yükleneceğine](https://docs.microsoft.com/windows/wsl/install-win10) ilişkin ayrıntıları burada bulabilirsiniz.

WSL yüklemenizi Visual Studio ile çalışacak şekilde yapılandırmak için aşağıdaki araçların yüklü olması gerekir: GCC, gdb, Make, rsync ve zip. Bu komutu kullanarak, apt 'yi kullanan distro 'lara 'e yükleyebilirsiniz: 

```bash
sudo apt install g++ gdb make rsync zip
```

Projenizi WSL için yapılandırmak üzere bkz. [bir Linux projesi yapılandırma](configure-a-linux-project.md) veya sahip olduğunuz proje türüne bağlı olarak [bir Linux CMake projesi yapılandırma](cmake-linux-project.md) . WSL ile basit bir konsol uygulaması oluşturmaya yönelik adım adım yönergeleri izlemek için, [ C++ Visual Studio 2019 ve Linux için Windows alt sistemi (WSL) ile birlikte](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/)bu giriş blog gönderisine göz atın.

::: moniker-end

## <a name="see-also"></a>Ayrıca Bkz.

[Linux projesi yapılandırma](configure-a-linux-project.md)<br />
[Linux CMake projesi yapılandırma](cmake-linux-project.md)<br />
[Linux projenizi dağıtma, çalıştırma ve hata ayıklama](deploy-run-and-debug-your-linux-project.md)<br />




