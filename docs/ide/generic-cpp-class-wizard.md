---
title: Genel C++ Sınıfı Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.generic
helpviewer_keywords:
- Generic C++ Class Wizard [C++]
ms.assetid: aa95be9e-fc1b-45db-a11d-0d32c4929077
ms.openlocfilehash: e3db091585615dcdccaab7c99c18a923802b31a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451044"
---
# <a name="generic-c-class-wizard"></a>Genel C++ Sınıfı Sihirbazı

Projeye Genel C++ sınıfı ekler. Sınıfı, ATL veya MFC devralmaz.

- **Sınıf adı**

   Yeni bir sınıf adını ayarlar.

- **.h dosyası**

   Yeni bir sınıf için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıf adı**. Üst bilgi dosyası istediğiniz konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini (**...** ). ' A tıkladığınızda, var olan bir dosya belirtirseniz **son**, sihirbaz sınıf bildirimi dosya içeriğini eklenmeyeceğini belirtmenizi ister. Bildirimi eklemek için tıklatın **Evet**; sihirbaza dönmek ve başka bir dosya adı belirtin, tıklatın **Hayır**.

- **.cpp dosyası**

   Yeni bir sınıf için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıf adı**. Uygulama dosyası istediğiniz konuma kaydedin veya mevcut bir dosyaya sınıf tanımı eklemek için üç nokta düğmesini (**...** ). ' A tıkladığınızda, var olan bir dosya belirtirseniz **son**, sihirbaz sınıf tanımının dosyasının içeriğini eklenmeyeceğini belirtmenizi ister. Tanımı eklemek için tıklatın **Evet**; sihirbaza dönmek ve başka bir dosya adı belirtin, tıklatın **Hayır**.

- **Temel sınıf**

   Yeni bir sınıf için taban sınıf ayarlar.

- **Erişim**

   Yeni bir sınıf için taban sınıf üyelerine erişimi ayarlar. Erişim değiştiricileri diğer sınıflara sahip sınıf üyesi işlevleri için erişim düzeyini belirten anahtar sözcüklerdir. Erişim belirtme hakkında daha fazla bilgi için bkz. [üye erişim denetimi](../cpp/member-access-control-cpp.md). Varsayılan olarak, sınıf erişim düzeyini ayarlamak `public`.

   - `public`

   - `protected`

   - `private`

   - **Varsayılan** (herhangi bir erişim değiştiricisi oluşturulur.)

- **Sanal yıkıcı**

   Sınıf yok edicisini sanal olup olmadığını belirtir. Sanal bir yıkıcı kullanılmasını, özel olarak türetilmiş sınıfların örneklerini silindiğinde doğru yok Edicisi çağrılır sağlamaya yardımcı olur.

- **Satır içi**

   Üstbilgi dosyasında, sınıf oluşturucusu hem satır içi işlevleri olarak sınıf tanımı oluşturur.

- **Yönetilen**

   Bu onay kutusu seçildiğinde, yönetilen bir sınıf ve üstbilgi dosyası ekler. Bu onay kutusu temizlenirse, yerel bir sınıf ve üstbilgi dosyası ekler.

## <a name="see-also"></a>Ayrıca Bkz.

[Genel C++ Sınıfı Ekleme](../ide/adding-a-generic-cpp-class.md)