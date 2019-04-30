---
title: Üye işlevi Ekle
ms.date: 11/09/2018
f1_keywords:
- vc.codewiz.classes.member.function
- vc.codewiz.function.overview
helpviewer_keywords:
- member functions, adding to classes
- classes [C++], adding members
- add member function wizard [C++]
ms.assetid: 55b25ddb-541d-44ed-957c-974ef91cfc85
ms.openlocfilehash: 1cd7abbbc43ae56861b3b83451b41933b8b0b4f0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345994"
---
# <a name="add-a-member-function"></a>Üye işlevi Ekle

İçinde **sınıf görünümü**, herhangi bir sınıfın bir üye işlev ekleyebilirsiniz. Bunu yaptığınızda bir bildirimi üstbilgi dosyasına eklenir ve daha sonra değiştirebilirsiniz sınıf uygulaması dosya için bir saplama üye işlev gövdesinin eklenir.

**Üye işlevi bir sınıfa eklemek için:**

1. İçinde **sınıf görünümü**, projede sınıflarını görüntülemek için proje düğümünü genişletin. (Açmak için **sınıf görünümü**, menü çubuğunda, **görünümü**, **sınıf görünümü**.)

1. Üye işlev eklemek ve ardından istediğiniz sınıfı için kısayol menüsünü açın **Ekle**, **işlev Ekle**.

1. Üye işlevi uygun ayrıntılarını sağlayın. Daha fazla bilgi için [Ekle üye işlev Sihirbazı'nı](#add-member-function-wizard).

1. Seçin **son** üye işlev kodunu oluşturmak için düğme.

## <a name="in-this-section"></a>Bu bölümde

- [Üye işlevi Ekleme Sihirbazı](#add-member-function-wizard)

## <a name="add-member-function-wizard"></a>Üye işlevi Ekleme Sihirbazı

Bu sihirbaz bir üye işlev bildirimi için üst bilgi dosyası ekler. Ayrıca seçilen sınıf için uygulama dosyası için bir saplama üye işlev uygulaması ekler.

Sihirbazı kullanarak üye işlevi ekledikten sonra kodu geliştirme ortamında düzenleyebilirsiniz.

- **Dönüş türü**

  Eklediğiniz üye işlevin dönüş türünü ayarlar. Kullanılabilir türler listesinden seçebilir veya kendi dönüş türü sağlayabilir. Türleri hakkında daha fazla bilgi için bkz: [temel türler](../cpp/fundamental-types-cpp.md).

  | | | |
  |---|---|---|
  | `char` | `int` | `unsigned int` |
  | `double` | `long` | `unsigned long` |
  | `float` | `short` | `void` |
  | `HRESULT` | `unsigned char` | |

- **İşlev adı**

  Eklediğiniz üye işlevin adını ayarlar.

- **Parametre türü**

  Üye işlevi parametrelere sahipse üye işlevi için ekleme parametresinin türünü ayarlar. Kendi parametre türü sağlayabilir veya kullanılabilir türler listesinden seçebilirsiniz.

  | | | |
  |---|---|---|
  | `char` | `int` | `unsigned char` |
  | `double` | `long` | `unsigned int` |
  | `float` | `short` | `unsigned long` |

- **Parametre adı**

  Üye işlevi parametrelere sahipse, üye işlevi için eklediğiniz bir parametre adını ayarlar.

- **Parametre listesi**

  Eklediğiniz üye işlevi için parametre listesini görüntüler. Bir parametre listesine eklenecek bir türü sağlayın ve içinde ad **parametre türü** ve **parametre adı** kutuları ve select **Ekle**. Parametre listesinden kaldırmak için parametreyi seçin ve seçin **Kaldır**.

- **Erişim**

  Üye işlevine erişim ayarlar. Erişim değiştiricileri, diğer sınıfların üye işleve sahip erişimi belirtin sözcüklerdir. Erişim belirtme hakkında daha fazla bilgi için bkz. [üye erişim denetimi](../cpp/member-access-control-cpp.md). Üye işlevi erişim düzeyini ayarlamak `public` varsayılan olarak.

  - [public](../cpp/public-cpp.md)
  - [protected](../cpp/protected-cpp.md)
  - [private](../cpp/private-cpp.md)

  Yeni üye işlevini statik veya sanal olmasına ve satır içi olup denetleyin veya saf. Saf, üye işlevi ayarlarsanız **sanal** onay kutusu seçildiğinde ve **satır içi** onay kutusu kullanım dışı olur. Varsayılan, statik olmayan, sanal olmayan üye işlevi olmasıdır.

  | Seçenek | Açıklama |
  |--------|-------------|
  | [Static](../cpp/storage-classes-cpp.md) |  İşlev genel gibi davranır ve sınıf örnekleme olmasa bile bir sınıf dışında çağrılabilir belirtir. Üye işlevini statik olmayan üyeler için erişim yok. Belirtilen bir üye işlev `Static` sanal olamaz. |
  | [Sanal](../cpp/virtual-cpp.md) | Doğru üye işlevi üye işlev çağrısını yapmak için kullanılan ifade bağımsız olarak bir nesne için çağrıldığından emin emin olur. Belirtilen bir üye işlev `Virtual` statik olamaz. |
  | **saf** | Hiçbir uygulama sanal üye işlev için bildirilen verilmesi gerektiğini gösterir. **Saf** yalnızca sanal üye işlevlerde belirtilebilir. En az bir saf sanal üye işlevi içeren bir sınıf, soyut bir sınıf olarak kabul edilir. Soyut sınıftan türetilmiş sınıflar saf sanal üye işlevi uygulamak zorundadır veya onlar da soyut sınıflardır. |
  | [Satır içi](../cpp/inline-functions-cpp.md) | Üye işlevi çağrılan her yere üye işlev gövdesinin bir kopyasını eklemek için derleyicinin sağlar. Belirtilen bir üye işlev **satır içi** saf olamaz. |

- **.cpp dosyası**

  Saplama üye işlev uygulaması yazıldığı dosya konumunu ayarlar. Varsayılan olarak, üye işlevi ekleneceği sınıfı .cpp dosyası öğesine yazılır. Dosya adını değiştirmek için üç nokta düğmesini seçin. Üye işlev uygulaması, seçilen dosya içeriğini eklenir.

- **Yorum**

  Üstbilgi dosyasında üye işlevi için bir açıklama sağlar.

- **İşlev imzası**

  Üye işlevi koddan verbatim seçtiğinizde görüntüler **son**. Bu kutuda metni düzenleyemez. Üye işlevi değiştirmek için uygun kutulara Sihirbazı'nı değiştirin.
