---
title: Üye işlevi ekleme
ms.date: 11/09/2018
f1_keywords:
- vc.codewiz.classes.member.function
- vc.codewiz.function.overview
helpviewer_keywords:
- member functions, adding to classes
- classes [C++], adding members
- add member function wizard [C++]
ms.assetid: 55b25ddb-541d-44ed-957c-974ef91cfc85
ms.openlocfilehash: c5423cfb8e2ea1b39001ec512c9c7f460d6a1a19
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228693"
---
# <a name="add-a-member-function"></a>Üye işlevi ekleme

**Sınıf görünümü**, herhangi bir sınıfa bir üye işlevi ekleyebilirsiniz. Bunu yaptığınızda, üstbilgi dosyasına bir bildirim eklenir ve daha sonra değiştirebileceğiniz bir saplama üye işlev gövdesi sınıfın uygulama dosyasına eklenir.

**Bir sınıfa üye işlevi eklemek için:**

1. **Sınıf görünümü**, projedeki sınıfları göstermek için proje düğümünü genişletin. ( **Sınıf görünümü**açmak için, menü çubuğunda **Görünüm**, **sınıf görünümü**' i seçin.)

1. Üye işlevi eklemek istediğiniz sınıf için kısayol menüsünü açın ve **Ekle**, **işlev Ekle**' yi seçin.

1. Üye işlevi hakkında uygun ayrıntıları sağlayın. Daha fazla bilgi için bkz. [üye Işlev ekleme Sihirbazı](#add-member-function-wizard).

1. Üye işlev kodunu oluşturmak için **son** düğmesini seçin.

## <a name="in-this-section"></a>Bu bölümde

- [Üye işlevi Ekleme Sihirbazı](#add-member-function-wizard)

## <a name="add-member-function-wizard"></a>Üye işlevi Ekleme Sihirbazı

Bu sihirbaz başlık dosyasına bir üye işlevi bildirimi ekler. Ayrıca, seçilen sınıf için uygulama dosyasına bir saplama üye işlev uygulamasını ekler.

Sihirbazı kullanarak üye işlevini ekledikten sonra, geliştirme ortamındaki kodu düzenleyebilirsiniz.

- **Dönüş türü**

  Eklemekte olduğunuz üye işlev için dönüş türünü ayarlar. Kendi dönüş türünü sağlayabilir veya kullanılabilir türler listesinden seçim yapabilirsiniz. Türler hakkında daha fazla bilgi için bkz. [temel türler](../cpp/fundamental-types-cpp.md).

  | | | |
  |---|---|---|
  | **`char`** | **`int`** | **`unsigned int`** |
  | **`double`** | **`long`** | **`unsigned long`** |
  | **`float`** | **`short`** | **`void`** |
  | `HRESULT` | **`unsigned char`** | |

- **İşlev adı**

  Eklemekte olduğunuz üye işlevin adını ayarlar.

- **Parametre türü**

  Üye işlevin parametreleri varsa, üye işlevi için eklemekte olduğunuz parametrenin türünü ayarlar. Kendi parametre türlerinizi sağlayabilir veya kullanılabilir türler listesinden seçim yapabilirsiniz.

  | | | |
  |---|---|---|
  | **`char`** | **`int`** | **`unsigned char`** |
  | **`double`** | **`long`** | **`unsigned int`** |
  | **`float`** | **`short`** | **`unsigned long`** |

- **Parametre adı**

  Üye işlevin parametreleri varsa, üye işlevi için eklemekte olduğunuz parametrenin adını ayarlar.

- **Parametre listesi**

  Üye işlevine eklemiş olduğunuz parametrelerin listesini görüntüler. Listeye bir parametre eklemek için, **parametre türü** ve **parametre adı** kutularına bir tür ve ad girin ve **Ekle**' yi seçin. Listeden bir parametreyi kaldırmak için parametreyi seçin ve **Kaldır**' ı seçin.

- **Erişim**

  Üye işlevine erişimi ayarlar. Erişim değiştiricileri, diğer sınıfların üye işlevine sahip olduğu erişimi belirten anahtar sözcüklerdir. Erişim belirtme hakkında daha fazla bilgi için bkz. [üye erişim denetimi](../cpp/member-access-control-cpp.md). Üye işlevi erişim düzeyi varsayılan olarak olarak ayarlanır **`public`** .

  - [genel](../cpp/public-cpp.md)
  - [protected](../cpp/protected-cpp.md)
  - [özelleştirme](../cpp/private-cpp.md)

  Yeni üye işlevinin statik mi, sanal mi olduğunu ve satır içi veya saf olduğunu kontrol edin. Üye işlevini saf olacak şekilde ayarlarsanız, **sanal** onay kutusu seçilidir ve **satır içi** onay kutusu kullanılamaz hale gelir. Varsayılan değer statik olmayan, sanal olmayan bir üye işlevdir.

  | Seçenek | Açıklama |
  |--------|-------------|
  | [Static](../cpp/storage-classes-cpp.md) |  İşlevin genel gibi davrandığını ve sınıf örneklemesi olmadan bile sınıfın dışında çağrılabilecek olduğunu belirtir. Üye işlevin statik olmayan üyelere erişimi yok. Olarak belirtilen bir üye işlevi `Static` sanal olamaz. |
  | [Sanal](../cpp/virtual-cpp.md) | Üye işlev çağrısını yapmak için kullanılan ifadeden bağımsız olarak, bir nesne için doğru üye işlevinin çağrıldığından emin olur. Olarak belirtilen bir üye işlevi `Virtual` statik olamaz. |
  | **Tam** | Belirtilen sanal üye işlev için hiçbir uygulamanın sağlanmadığını gösterir. **Saf** , yalnızca sanal üye işlevlerinde belirtilebilir. En az bir saf sanal üye işlevi içeren bir sınıf, soyut bir sınıf olarak kabul edilir. Soyut sınıftan türetilmiş sınıflar, saf sanal üye işlevini uygulamalıdır ya da soyut sınıflardır. |
  | [Çizgi](../cpp/inline-functions-cpp.md) | Derleyiciye üye işlevinin çağrıldığı her yere üye işlev gövdesinin bir kopyasını eklemesini söyler. **Satır içi** olarak belirtilen bir üye işlevi saf olamaz. |

- **. cpp dosyası**

  Saplama üye işlevi uygulamasının yazıldığı dosya konumunu ayarlar. Varsayılan olarak, üye işlevin eklendiği sınıf için. cpp dosyasına yazılır. Dosya adını değiştirmek için üç nokta düğmesini seçin. Üye işlevi uygulama, seçili dosyanın içeriğine eklenir.

- **Yorum**

  Üye işlevi için üstbilgi dosyasında bir açıklama sağlar.

- **İşlev imzası**

  **Son**' u seçtiğinizde koddan tam üye işlevini görüntüler. Bu kutudaki metni düzenleyemezsiniz. Üye işlevini değiştirmek için, sihirbazdaki ilgili kutuları değiştirin.
