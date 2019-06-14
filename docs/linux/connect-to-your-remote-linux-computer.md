---
title: Hedef için Linux sisteminde Visual Studio bağlanma
description: Uzak Linux makinesinin veya WSL gelen bir Visual Studio içinde nasıl C++ proje.
ms.date: 06/11/2019
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
ms.openlocfilehash: 4003a7387981b60d22f0344463d1729974d437a7
ms.sourcegitcommit: fde637f823494532314790602c2819f889706ff6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67042683"
---
# <a name="connect-to-your-target-linux-system-in-visual-studio"></a>Hedef için Linux sisteminde Visual Studio bağlanma

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ile kullanılabilir ve üzerinde desteklenir.

::: moniker-end

::: moniker range=">=vs-2017"

Linux projesi hedef bir uzak makine ya da Windows alt sistemi Linux (WSL) yapılandırabilirsiniz.

## <a name="connect-to-a-remote-linux-computer"></a>Uzak Linux bilgisayara bağlanın

Oluşturma sırasında bir C++ Linux projesi bir uzak Linux Sistemi'nde (VM veya fiziksel makine), kod uzak Linux bilgisayarınıza kopyalanır ve sonra derlenmiş Linux Visual Studio ayarlarına göre. (Visual Studio 2017'de bu yönergeleri WSL için de bağlanmak için kullanın. Kullanma **localhost** için **ana bilgisayar adı**.)

Bu uzak bağlantı kurmak için:

1. İlk kez projeyi derlemeyi ya da el ile seçerek yeni bir giriş oluşturun **Araçlar > Seçenekler** ve açın **Çoklu Platform > Bağlantı Yöneticisi** düğüm ve tıklatın **Ekle** düğmesi.

   ![Bağlantı Yöneticisi](media/settings_connectionmanager.png)

   Her iki senaryoda **uzak sisteme Bağlan** penceresi görüntülenir.

   ![Uzak sisteme Bağlan](media/connect.png)

1. Aşağıdaki bilgileri girin:

   | Giriş | Açıklama
   | ----- | ---
   | **Ana bilgisayar adı**           | Hedef cihazınızın adı veya IP adresi
   | **Bağlantı noktası**                | Genellikle, 22 SSH hizmeti çalışıyor bağlantı noktası
   | **Kullanıcı adı**           | Kullanıcı olarak kimlik doğrulaması yapmak için
   | **Kimlik doğrulaması türü** | Parola veya özel anahtar desteklenir
   | **Parola**            | Girilen kullanıcı adının parolası
   | **Özel anahtar dosyası**    | Özel anahtar dosyası için ssh bağlantı oluşturuldu
   | **Parola**          | Yukarıda seçilen özel anahtarlı kullanılan parola

1. Tıklayın **Connect** uzak bilgisayara bağlanmaya düğmesi. 

   Bağlantı başarılı olursa, Visual Studio IntelliSense uzak üstbilgileri kullanmak üzere yapılandırma başlar. Daha fazla bilgi için [uzak sistemlerdeki üst bilgileri için IntelliSense](configure-a-linux-project.md#remote_intellisense).

   Değiştirilmesi gereken giriş kutularının bağlantı başarısız olursa, kırmızı renkle gösterilir.

   ![Bağlantı Yöneticisi hata](media/settings_connectionmanagererror.png)

   ::: moniker-end

   ::: moniker range="vs-2019"

   Git **Araçlar > Seçenekler > Çoklu Platform > Günlük** bağlantı sorunlarını gidermek günlük kaydını etkinleştirmek için:

   ![Uzaktan günlüğe kaydetme](media/remote-logging-vs2019.png)

   Günlükleri, bağlantılar, uzak makine (kendi metin, çıkış kodu ve yürütme süresi) ve tüm yazma işlemlerini Visual Studio'dan kabuğa gönderilen tüm komutları içerir. Platformlar arası CMake proje ya da Visual Studio'da MSBuild tabanlı Linux projesi için günlük çalışır.

   Çıkış bir dosyaya veya çok gitmek için yapılandırabileceğiniz **Çapraz Platform günlüğü** çıktı penceresinde bölmesi. MSBuild tabanlı Linux projeleri için MSBuild tarafından uzak makineye verilen komutları için yönlendirilmeyen **çıkış penceresine** çünkü bunlar yayılan giden işlem. Bunun yerine, bunlar "msbuild_" ön ekine sahip bir dosyaya kaydedilir.

## <a name="connect-to-wsl"></a>Bağlanmak için WSL

Visual Studio 2019 içinde sürüm 16.1, uzak bağlantı eklemek veya WSL hedeflenirken SSH'ı yapılandırmak gerekli değildir. Linux sisteminde gerekli olan tek şey gcc, gdb, oluştur, rsync ve zip. Visual Studio, rsync ve yalnızca ilk kullanımda üst bilgi dosyaları, WSL örneğinden IntelliSense için kullanılacak Windows dosya sistemi ayıklamak için zip gerektirir. Visual Studio 2019 içinde 16.1 sürümü, sürüm 1809 Windows üzerinde podpora WSL temel alır. Windows daha sonraki bir sürümünü çalıştıran, ancak Visual Studio henüz yeni WSL özelliklerinden almaz.

Distro apt destekliyorsa, bu komutla birlikte gerekli paketleri yükleyebilirsiniz:

```bash
sudo apt install g++ gdb make rsync zip
```

Projeniz için WSL yapılandırmak için bkz [Linux projesi yapılandırma](configure-a-linux-project.md) veya [Linux CMake projesi yapılandırma](cmake-linux-project.md) proje türünü bağlı olarak, sahip.

::: moniker-end

## <a name="see-also"></a>Ayrıca Bkz.

[Linux projesi yapılandırma](configure-a-linux-project.md)<br />
[Linux CMake projesi yapılandırma](cmake-linux-project.md)<br />
[Deply, çalıştırma ve Linux projenizin hatalarını ayıklama](deploy-run-and-debug-your-linux-project.md)<br />




