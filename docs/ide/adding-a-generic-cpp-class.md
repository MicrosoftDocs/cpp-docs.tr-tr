---
title: Genel C++ sınıfı ekleme
ms.date: 11/09/2018
f1_keywords:
- vc.codewiz.classes.adding.generic
- vc.codewiz.class.generic
helpviewer_keywords:
- Visual C++, classes
- generic classes, adding
- generic classes
- generic C++ class wizard [C++]
ms.assetid: e95a5a14-dbed-4edc-8551-344fe48613cb
ms.openlocfilehash: 08ebe572da605e0f6d4d712bd7e48159598ba844
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694146"
---
# <a name="add-a-generic-c-class"></a>Genel C++ sınıfı ekleme

Genel C++ sınıfı kullanarak ekleyebilirsiniz **sınıf görünümü**. Genel C++ sınıfı, tanımladığınız veya tanımladığınız bir sınıftan türetilen bir sınıftır.

**Genel C++ sınıfı için bir proje eklemek için:**

1. İçinde **sınıf görünümü**, yeni bir sınıf eklemek için seçmek istediğiniz projeye sağ tıklayıp **Ekle**ve ardından **sınıfı**.

1. İçinde [sınıfı Ekle](../ide/add-class-dialog-box.md) Şablonlar bölmesinde, Seç iletişim kutusu **C++ sınıfı**. Seçin **Ekle** görüntülenecek [genel C++ sınıfı Sihirbazı](#generic-c-class-wizard).

1. Sihirbazı'nda, bir sınıf adı sağlayın ve ayarlarını tanımlayın veya Varsayılanları kabul edin.

1. Sihirbazı kapatmak ve yeni genel C++ sınıfı projesinde görüntülemek için seçin **son**.

## <a name="in-this-section"></a>Bu bölümde

- [Genel C++ sınıfı Sihirbazı](#generic-c-class-wizard)

## <a name="generic-c-class-wizard"></a>Genel C++ sınıfı Sihirbazı

Projeye Genel C++ sınıfı ekler. Sınıfı, ATL veya MFC devralmaz.

- **Sınıf adı**

  Yeni bir sınıf adını ayarlar.

- **.h dosyası**

  Yeni bir sınıf için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıf adı**. Üst bilgi dosyası istediğiniz konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini seçin (**...** ). Var olan bir dosya belirtin ve seçeneğini belirlerseniz **son**, sihirbaz sınıf bildirimi dosya içeriği eklenmeyeceğini belirtmenizi ister. Bildirimi eklemek için seçin **Evet**; sihirbaza dönmek ve başka bir dosya adı belirtin, seçmek için **Hayır**.

- **.cpp dosyası**

  Yeni bir sınıf için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıf adı**. Uygulama dosyasına seçtiğiniz bir konuma kaydetmek için veya mevcut bir dosyaya sınıf tanımı eklemek için üç nokta düğmesini seçin (**...** ). Var olan bir dosya belirtin ve seçeneğini belirlerseniz **son**, sihirbaz sınıf tanımı için dosya içeriğini eklenmeyeceğini belirtmenizi ister. Tanımı eklemek için seçin **Evet**; sihirbaza dönmek ve başka bir dosya adı belirtin, seçmek için **Hayır**.

- **Temel sınıf**

  Yeni bir sınıf için taban sınıf ayarlar.

- **Erişim**

  Yeni bir sınıf için taban sınıf üyelerine erişimi ayarlar. Erişim değiştiricileri diğer sınıflara sahip sınıf üyesi işlevleri için erişim düzeyini belirten anahtar sözcüklerdir. Erişim belirtme hakkında daha fazla bilgi için bkz. [üye erişim denetimi](../cpp/member-access-control-cpp.md). Varsayılan olarak, sınıf erişim düzeyini ayarlamak `public`.

  - `public`
  - `protected`
  - `private`
  - **Varsayılan** (herhangi bir erişim değiştiricisi oluşturulur.)

- **Sanal yıkıcı**

  Sınıf yok edicisini sanal olup olmadığını belirtir. Sanal bir yıkıcı kullanımını türetilmiş sınıfların örneklerini silindiğinde doğru yok Edicisi çağrılır emin olmaya yardımcı olur.

- **Satır içi**

  Üstbilgi dosyasında, sınıf oluşturucusu hem satır içi işlevleri olarak sınıf tanımı oluşturur.

- **Yönetilen**

  Bu onay kutusu seçildiğinde, yönetilen bir sınıf ve üstbilgi dosyası ekler. Bu onay kutusu temizlenirse, yerel bir sınıf ve üstbilgi dosyası ekler.
