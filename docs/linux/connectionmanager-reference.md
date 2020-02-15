---
title: ConnectionManager başvurusu
ms.date: 01/17/2020
f1_keywords:
- ConnectionManager
helpviewer_keywords:
- ConnectionManager program
ms.openlocfilehash: 1c6236cedba88714e9918dd2c096b5e78d2f08ce
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77258039"
---
# <a name="connectionmanager-reference"></a>ConnectionManager başvurusu

::: moniker range="<=vs-2017"

ConnectionManager. exe, Visual Studio 2019 sürüm 16,5 ve sonraki sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range="vs-2019"

ConnectionManager. exe, Visual Studio dışında Uzaktan geliştirme bağlantılarını yönetmeye yönelik bir komut satırı yardımcı programıdır. Yeni bir geliştirme makinesi sağlama gibi görevler için faydalıdır. Veya, sürekli tümleştirme için Visual Studio 'Yu ayarlamak üzere kullanın. Bunu, bir Geliştirici Komut İstemi penceresinde kullanabilirsiniz. Geliştirici Komut İstemi hakkında daha fazla bilgi için bkz. [komut satırından Microsoft C++ araç takımını kullanma](../build/building-on-the-command-line.md).

ConnectionManager. exe, Visual Studio 2019 sürüm 16,5 ve sonraki sürümlerinde kullanılabilir. Visual Studio yükleyicisi iş yüküyle **Linux geliştirmenin C++**  bir parçasıdır. Ayrıca, yükleyicide **Bağlantı Yöneticisi** bileşenini seçtiğinizde de otomatik olarak yüklenir. *% Vcıdeınstalldir%\\Linux\\bin\\ConnectionManagerExe\\ConnectionManager. exe*dosyasına yüklendi.

ConnectionManager. exe işlevselliği, Visual Studio 'da da kullanılabilir. IDE 'deki Uzaktan geliştirme bağlantılarını yönetmek için, menü çubuğunda **araçlar** > **Seçenekler** ' i seçerek Seçenekler iletişim kutusunu açın. Seçenekler iletişim kutusunda, **Çapraz Platform** > **Bağlantı Yöneticisi**' ni seçin.

## <a name="syntax"></a>Sözdizimi

> **ConnectionManager. exe** *komutu* \[*bağımsız değişkenler*] \[*Seçenekler*]

### <a name="commands-and-arguments"></a>Komutlar ve bağımsız değişkenler

- *Kullanıcı\@ana bilgisayar* \[ **--bağlantı noktası** *bağlantı noktası*] \[ **--parola** *parolası*] \[ **--PrivateKey** *privatekey_file*]

  Kimlik doğrulaması yapar ve yeni bir bağlantı ekler. Varsayılan olarak, 22 ve parola kimlik doğrulaması bağlantı noktasını kullanır. (Bir parola girmeniz istenir.) Özel anahtar için bir parola belirtmek üzere **--Password** ve **--PrivateKey** kullanın.

- \[*connection_id* \| *Kullanıcı\@ana bilgisayar* \[ **--bağlantı noktası** *bağlantı noktası*]] **kaldırın**

  Bir bağlantıyı kaldırır. Herhangi bir bağımsız değişken belirtilmemişse, hangi bağlantının kaldırılacağını belirtmeniz istenir.

- **Tümünü Kaldır**

  Tüm depolanan bağlantıları kaldırır.

- **list**

  Tüm depolanan bağlantıların bilgilerini ve kimliklerini görüntüler.

- **Yardım**

  Yardım ekranını görüntüler.

- **version**

  Sürüm bilgilerini görüntüler.

### <a name="options"></a>Seçenekler

- **-q**, **--quiet**

  `stdout` veya `stderr`çıkışı önler.

- **--No-Prompt**

  Uygun olduğunda istem yerine başarısız olur.

- **--No-doğrula**

  Kimlik doğrulaması olmadan bir bağlantı ekleyin veya değiştirin.

- **--Dosya** *dosya adı*

  Belirtilen *dosya adından*bağlantı bilgilerini okuyun.

- **--No-telemetri**

  Kullanım verilerini Microsoft 'a geri göndermeyi devre dışı bırakın. Kullanım verileri toplanır ve **--No-telemetri** bayrağı geçirilmediği takdirde Microsoft 'a geri gönderilir.  

- **-n**, **--kuru-Çalıştır**

  Komutun bir kuru çalıştırması yapar.

- **-p**

  **--Password**.

- **-ı**

  **--PrivateKey**ile aynı.

## <a name="examples"></a>Örnekler

Bu komut localhost üzerinde "user" adlı bir kullanıcı için bağlantı ekler. Bağlantı, *% USERPROFILE%\.SSH \ id_rsa*içinde bulunan kimlik doğrulaması için bir anahtar dosyası kullanıyor.

```cmd
ConnectionManager.exe add user@127.0.0.1 --privatekey "%USERPROFILE%\.ssh\id_rsa"
```

Bu komut, KIMLIK 1975957870 olan bağlantıyı bağlantı listesinden kaldırır.

```cmd
ConnectionManager.exe remove 1975957870
```

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da hedef Linux sisteminize bağlanma](connect-to-your-remote-linux-computer.md)

::: moniker-end
