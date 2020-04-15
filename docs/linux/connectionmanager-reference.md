---
title: ConnectionManager başvurusu
ms.date: 01/17/2020
f1_keywords:
- ConnectionManager
helpviewer_keywords:
- ConnectionManager program
ms.openlocfilehash: 1c6236cedba88714e9918dd2c096b5e78d2f08ce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "77258039"
---
# <a name="connectionmanager-reference"></a>ConnectionManager başvurusu

::: moniker range="<=vs-2017"

ConnectionManager.exe Visual Studio 2019 sürümü 16.5 ve sonrası mevcuttur.

::: moniker-end

::: moniker range="vs-2019"

ConnectionManager.exe, Visual Studio dışındaki uzaktan geliştirme bağlantılarını yönetmek için bir komut satırı yardımcı programıdır. Yeni bir geliştirme makinesi sağlama gibi görevler için yararlıdır. Veya, sürekli entegrasyon için Visual Studio kurmak için kullanabilirsiniz.Geliştirici Komut Istem penceresinde kullanabilirsiniz. Geliştirici Komut KomutU İstemi hakkında daha fazla bilgi için [bkz.](../build/building-on-the-command-line.md)

ConnectionManager.exe Visual Studio 2019 sürümü 16.5 ve sonrası mevcuttur. Visual Studio Installer'daki C++ iş **yüküyle Linux geliştirmenin** bir parçasıdır. Yükleyicideki **Bağlantı Yöneticisi** bileşenini seçtiğinizde otomatik olarak yüklenir. Bu *% VCIDEInstallDir%\\\\Linux bin\\ConnectionManagerExe\\ConnectionManager.exe*yüklü.

ConnectionManager.exe'nin işlevselliği Visual Studio'da da mevcuttur. IDE'deki uzak geliştirme bağlantılarını yönetmek için menü çubuğunda Seçenekler iletişim kutusunu açmak için **Araçlar** > **Seçenekleri'ni** seçin. Seçenekler iletişim kutusunda, **PlatformLar** > Arası**Bağlantı Yöneticisi'ni**seçin.

## <a name="syntax"></a>Sözdizimi

> **ConnectionManager.exe** *komut* \[ \[bağımsız *değişkenleri*] *seçenekleri*]

### <a name="commands-and-arguments"></a>Komutlar ve bağımsız değişkenler

- **add** *kullanıcı\@ana bilgisayarı* \[ **ekle --port** \[ *port*] \[ **--parola** *şifresi*] **--privatekey** *privatekey_file*]

  Kimlik doğrular ve yeni bir bağlantı ekler. Varsayılan olarak, bağlantı noktası 22 ve parola kimlik doğrulaması kullanır. (Bir parola girmeniz istenir.) Özel bir anahtar için parola belirtmek için hem **parola** hem de **-privatekey'i** kullanın.

- **connection_id** \[ *connection_id* *kullanıcı\@ana bilgisayarı* \[kaldırın **--bağlantı noktası** ]] *port* \|

  Bağlantıyı kaldırır. Bağımsız değişken belirtilmemişse, hangi bağlantının kaldırılacak olduğunu belirtmeniz istenir.

- **remove-all**

  Depolanan tüm bağlantıları kaldırır.

- **list**

  Depolanan tüm bağlantıların bilgilerini ve bağlantılarını görüntüler.

- **Yardım**

  Yardım ekranı görüntüler.

- **Sürüm**

  Sürüm bilgilerini görüntüler.

### <a name="options"></a>Seçenekler

- **-q**, **--sessiz**

  Çıkışını engeller `stdout` `stderr`veya .

- **--no-prompt**

  Uygun olduğunda istem yerine başarısız olabilir.

- **--doğrulama**

  Kimlik doğrulama olmadan bağlantı ekleme veya değiştirme.

- **--dosya** *adı*

  Sağlanan *dosya adından*bağlantı bilgilerini okuyun.

- **--no-telemetri**

  Kullanım verilerini Microsoft'a geri göndermeyi devre dışı kındırın. Kullanım verileri toplanır ve **--telemetri olmayan** bayrak geçirilmediği sürece Microsoft'a geri gönderilir.  

- **-n**, **--kuru-çalıştır**

  Komutun kuru bir çalışma yapar.

- **-p**

  **--password**ile aynı.

- **-i**

  **--privatekey**ile aynı.

## <a name="examples"></a>Örnekler

Bu komut, localhost 'da "kullanıcı" adlı bir kullanıcı için bir bağlantı ekler. Bağlantı, *%USERPROFILE%\.ssh\id_rsa'da*bulunan kimlik doğrulama için anahtar bir dosya kullanır.

```cmd
ConnectionManager.exe add user@127.0.0.1 --privatekey "%USERPROFILE%\.ssh\id_rsa"
```

Bu komut, 1975957870 kimliğine sahip bağlantıyı bağlantı listesinden kaldırır.

```cmd
ConnectionManager.exe remove 1975957870
```

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da hedef Linux sisteminize bağlanın](connect-to-your-remote-linux-computer.md)

::: moniker-end
