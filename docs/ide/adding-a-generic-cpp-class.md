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
ms.openlocfilehash: d5c00a35e375d133fbd3a6ed7fe3591e4b0cd54b
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503126"
---
# <a name="add-a-generic-c-class"></a>Genel C++ sınıfı ekleme

**Sınıf görünümü**kullanarak genel C++ sınıfı ekleyebilirsiniz. Genel C++ sınıfı, tanımladığınız veya tanımladığınız bir sınıftan türetilmiş bir sınıftır.

**Bir projeye Genel C++ sınıfı eklemek için:**

1. **Sınıf görünümü**' de, yeni sınıfı eklemek istediğiniz projeye sağ tıklayın, **Ekle**' yi ve ardından **sınıf**' ı seçin.

1. [Sınıf Ekle](./adding-a-class-visual-cpp.md#add-class-dialog-box) iletişim kutusunda, Şablonlar bölmesinde, **C++ sınıfı**' nı seçin. [Genel C++ sınıf sihirbazını](#generic-c-class-wizard)göstermek için **Ekle** ' yi seçin.

1. Sihirbazda bir sınıf adı girip ayarları tanımlayın veya Varsayılanları kabul edin.

1. Sihirbazı kapatmak ve yeni Genel C++ sınıfını projede görüntülemek için **son**' u seçin.

## <a name="in-this-section"></a>Bu bölümde

- [Genel C++ sınıfı Sihirbazı](#generic-c-class-wizard)

## <a name="generic-c-class-wizard"></a>Genel C++ sınıfı Sihirbazı

Bir projeye Genel C++ sınıfı ekler. Sınıf, ATL veya MFC 'den kalıtımla almaz.

- **Sınıf adı**

  Yeni sınıfın adını ayarlar.

- **. h dosyası**

  Yeni sınıf için üst bilgi dosyasının adını ayarlar. Bu ad, varsayılan olarak, **sınıf adı**' nda sağladığınız adı temel alır. Üstbilgi dosyasını istediğiniz konuma kaydetmek veya sınıf bildirimini mevcut bir dosyaya eklemek için üç nokta düğmesini (**...**) seçin. Var olan bir dosyayı belirtip **son**' u seçerseniz, sihirbaz sınıf bildiriminin dosya içeriğine eklenip eklenmeyeceğini belirtmenizi ister. Bildirimi eklemek için **Evet**' i seçin; sihirbaza dönmek ve başka bir dosya adı belirtmek için **Hayır**' ı seçin.

- **. cpp dosyası**

  Yeni sınıf için uygulama dosyasının adını ayarlar. Bu ad, varsayılan olarak, **sınıf adı**' nda sağladığınız adı temel alır. Uygulama dosyasını istediğiniz konuma kaydetmek veya sınıf tanımını mevcut bir dosyaya eklemek için üç nokta düğmesini (**...**) seçin. Var olan bir dosyayı belirtip **son**' u seçerseniz, sihirbaz, sınıf tanımının dosya içeriğine eklenip eklenmeyeceğini belirtmenizi ister. Tanımı eklemek için **Evet**' i seçin; sihirbaza dönmek ve başka bir dosya adı belirtmek için **Hayır**' ı seçin.

- **Temel sınıf**

  Yeni sınıfın temel sınıfını ayarlar.

- **Erişim**

  Yeni sınıf için temel sınıf üyelerine erişimi ayarlar. Erişim değiştiricileri, diğer sınıfların sınıf üye işlevlerine sahip olduğu erişim düzeyini belirten anahtar kelimelerdir. Erişimin nasıl belirtilme hakkında daha fazla bilgi için bkz. [üye erişim denetimi](../cpp/member-access-control-cpp.md). Varsayılan olarak, sınıf erişim düzeyi olarak ayarlanır **`public`** .

  - **`public`**
  - **`protected`**
  - **`private`**
  - **Varsayılan** (hiçbir erişim değiştiricisi oluşturulmaz.)

- **Sanal yıkıcı**

  Sınıf yıkıcısında sanal olup olmadığını belirtir. Sanal yıkıcı kullanımı, türetilmiş sınıfların örnekleri silindiğinde doğru yıkıcının çağrıldığından emin olmanıza yardımcı olur.

- **Çizgi**

  Hem sınıf oluşturucusunu hem de sınıf tanımını başlık dosyasında satır içi işlevler olarak oluşturur.

- **Yönetilen**

  Seçildiğinde, yönetilen bir sınıf ve üstbilgi dosyası ekler. Temizlenme sırasında, yerel bir sınıf ve üstbilgi dosyası ekler.
