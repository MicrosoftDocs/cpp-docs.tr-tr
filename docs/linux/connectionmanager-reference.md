---
title: ConnectionManager başvurusu
description: Bir komut satırı aracından uzak SSH bağlantılarınızı yönetme.
ms.date: 10/7/2020
f1_keywords:
- ConnectionManager
helpviewer_keywords:
- ConnectionManager program
ms.openlocfilehash: 065a2cf6d6a2fe7d7e418299255c5bbf1f2bf753
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921626"
---
# <a name="connectionmanager-reference"></a>ConnectionManager başvurusu

::: moniker range="<=msvc-150"

ConnectionManager.exe, Visual Studio 2019 sürüm 16,5 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range="msvc-160"

ConnectionManager.exe, Visual Studio dışında Uzaktan geliştirme bağlantılarını yönetmeye yönelik bir komut satırı yardımcı programıdır. Yeni bir geliştirme makinesi sağlama gibi görevler için faydalıdır. Veya, sürekli tümleştirme için Visual Studio 'Yu ayarlamak üzere kullanın. Bunu, bir Geliştirici Komut İstemi penceresinde kullanabilirsiniz. Geliştirici Komut İstemi hakkında daha fazla bilgi için, bkz. [komut satırından Microsoft C++ araç takımını kullanma](../build/building-on-the-command-line.md).

ConnectionManager.exe, Visual Studio 2019 sürüm 16,5 ve üzeri sürümlerde kullanılabilir. Bu, Visual Studio Yükleyicisi C++ iş yüküne **sahip Linux geliştirmenin** bir parçasıdır. Ayrıca, yükleyicide **Bağlantı Yöneticisi** bileşenini seçtiğinizde de otomatik olarak yüklenir. *% Vcıdeınstalldir% \\ Linux \\ bin \\ connectionmanagerexe \\ConnectionManager.exe* yüklendi.

ConnectionManager.exe işlevselliği, Visual Studio 'da da kullanılabilir. IDE 'deki Uzaktan geliştirme bağlantılarını yönetmek için, menü çubuğunda **Araçlar**  >  **Seçenekler** ' i seçerek Seçenekler iletişim kutusunu açın. Seçenekler iletişim kutusunda **platformlar arası**  >  **Bağlantı Yöneticisi** ' ni seçin.

## <a name="syntax"></a>Syntax

> **`ConnectionManager.exe`***komut* \[ *bağımsız değişkenler* ] \[ *Seçenekler* ]

### <a name="commands-and-arguments"></a>Komutlar ve bağımsız değişkenler

- **`add`***Kullanıcı \@ Konağı* \[ **`--port`** *bağlantı noktası* ] \[ **`--password`** *password* parola \[ ] **`--privatekey`** *privatekey_file* ]

  Kimlik doğrulaması yapar ve yeni bir bağlantı ekler. Varsayılan olarak, 22 ve parola kimlik doğrulaması bağlantı noktasını kullanır. (Bir parola girmeniz istenir.) **-`-password`** **`--privatekey`** Özel anahtar için bir parola belirtmek üzere hem hem de kullanın.

- **`remove`**\[ *connection_id* \| *Kullanıcı \@ ana bilgisayar* \[ **`--port`** *bağlantı noktası* ]]

  Bir bağlantıyı kaldırır. Herhangi bir bağımsız değişken belirtilmemişse, hangi bağlantının kaldırılacağını belirtmeniz istenir.
  
- **`modify`**\[ *varsayılan* \| *connection_id* \| *Kullanıcı \@ ana bilgisayar* \[ **`--port`** *bağlantı noktası* ]] \[ **`--property`** *anahtar = değer* ]

  Bir bağlantı üzerindeki bir özelliği tanımlar veya değiştirir. \
  *Değer* boşsa, özellik *anahtarı* silinir. \
  Kimlik doğrulaması başarısız olursa hiçbir değişiklik yapılmaz. \
  Hiçbir bağlantı belirtilmemişse ( *varsayılan* olarak, yukarıda belirlenir), kullanıcının varsayılan uzak bağlantısı kullanılır.

- **`remove-all`**

  Tüm depolanan bağlantıları kaldırır.
  
- **`clean`**

  Artık mevcut olmayan bağlantılar için üst bilgi önbelleğini siler. 

- **`list`** \[**`--properties`** ]

  Depolanan tüm bağlantıların bilgilerini, kimliklerini ve özelliklerini görüntüler. 

- **`help`**

  Yardım ekranını görüntüler.

- **`version`**

  Sürüm bilgilerini görüntüler.

### <a name="options"></a>Seçenekler

- **`-q`** , **`--quiet`**

  Veya için çıktıyı `stdout` engeller `stderr` .

- **`--no-prompt`**

  Uygun olduğunda istem yerine başarısız olur.

- **`--no-verify`**

  Kimlik doğrulaması olmadan bir bağlantı ekleyin veya değiştirin.

- **`--file`***dosya adı*

  Belirtilen *dosya adından* bağlantı bilgilerini okuyun.

- **`--no-telemetry`**

  Kullanım verilerini Microsoft 'a geri göndermeyi devre dışı bırakın. Kullanım verileri toplanır ve bayrak geçirilmediği takdirde Microsoft 'a geri gönderilir **`--no-telemetry`** .  

- **`-n`** , **`--dry-run`**

  Komutun bir kuru çalıştırması yapar.
 
- **`--p`**

  Aynı **`--password`** .

- **`-i`**

  Aynı **`--privatekey`** .

## <a name="examples"></a>Örnekler

Bu komut localhost üzerinde "user" adlı bir kullanıcı için bağlantı ekler. Bağlantı, *% USERPROFILE% \. ssh \ id_rsa* içinde bulunan kimlik doğrulaması için bir anahtar dosyası kullanıyor.

```cmd
ConnectionManager.exe add user@127.0.0.1 --privatekey "%USERPROFILE%\.ssh\id_rsa"
```

Bu komut, KIMLIK 1975957870 olan bağlantıyı bağlantı listesinden kaldırır.

```cmd
ConnectionManager.exe remove 1975957870
```

Bu komut, bağlantı KIMLIĞI 21212121 olan bağlantı için kabuğun seçimini geçersiz kılar. Desteklenen kabuklar: **`sh, csh, bash, tcsh, ksh, zsh, dash`** . Linux sisteminde bulunan kabuk desteklenmiyorsa, tüm komutlar için açık olarak kullanılacak geri dönebiliriz **`sh`** .

```cmd
ConnectionManager.exe modify 21212121 --property shell=csh
```

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da hedef Linux sisteminize bağlanma](connect-to-your-remote-linux-computer.md)

::: moniker-end