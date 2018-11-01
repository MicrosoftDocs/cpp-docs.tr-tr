---
title: Üye İşlevi Ekleme Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.function.overview
helpviewer_keywords:
- Add Member Function Wizard [C++]
ms.assetid: 13b6defc-faa6-4d57-83db-9dd854cbea3d
ms.openlocfilehash: 6ba95026d712c71a9d706baddfefda548100c64a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615052"
---
# <a name="add-member-function-wizard"></a>Üye İşlevi Ekleme Sihirbazı

Bu sihirbaz bir üye işlev bildirimi üstbilgi dosyası ve bir saplama üye işlev uygulaması için seçilen bir sınıf uygulama dosyaya ekler.

Sihirbazı kullanarak üye işlevi ekledikten sonra kodu geliştirme ortamında düzenleyebilirsiniz.

- **Dönüş türü**

   Eklediğiniz üye işlevin dönüş türünü ayarlar. Kullanılabilir türler listesinden seçebilir veya kendi dönüş türü sağlayabilir. Türleri hakkında daha fazla bilgi için bkz: [temel türler](../cpp/fundamental-types-cpp.md).

   ||||
   |-|-|-|
   |**char**|**int**|**işaretsiz int**|
   |**double**|**long**|**İmzasız long**|
   |**float**|**short**|**void**|
   |`HRESULT`|**İmzasız char**||

- **İşlev adı**

   Eklediğiniz üye işlevin adını ayarlar.

- **Parametre türü**

   Üye işlevi parametrelere sahipse, eklediğiniz üye işlevi için parametre türünü ayarlar. Kendi parametre türü sağlayabilir veya kullanılabilir türler listesinden seçebilirsiniz.

   ||||
   |-|-|-|
   |**char**|**int**|**İmzasız char**|
   |**double**|**long**|**işaretsiz int**|
   |**float**|**short**|**İmzasız long**|

- **Parametre adı**

   Üye işlevi parametrelere sahipse, eklediğiniz üye işlevi için parametre adını ayarlar.

- **Parametre listesi**

   Eklediğiniz üye işlevi için parametre listesini görüntüler. Bir parametre listesine eklenecek bir türü sağlayın ve içinde ad **parametre türü** ve **parametre adı** kutuları ve tıklatın **Ekle**. Parametre listesinden kaldırmak için parametreyi seçin ve **Kaldır**.

- **Erişim**

   Üye işlevine erişim ayarlar. Erişim değiştiricileri, diğer sınıfların üye işleve sahip erişimi belirtin sözcüklerdir. Bkz: [üye erişim denetimi](../cpp/member-access-control-cpp.md) erişim belirtme hakkında daha fazla bilgi için. Üye işlevi erişim düzeyini ayarlamak **genel** varsayılan olarak.

   - [public](../cpp/public-cpp.md)

   - [protected](../cpp/protected-cpp.md)

   - [private](../cpp/private-cpp.md)

   Yeni üye işlevini statik veya sanal olmasına ve satır içi olup denetleyin veya saf. Saf, üye işlevi ayarlarsanız `Virtual` onay kutusu seçildiğinde ve **satır içi** onay kutusu kullanım dışı olur. Varsayılan, statik olmayan, sanal olmayan üye işlevi olmasıdır.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |[Static](../cpp/storage-classes-cpp.md)|İşlev genel gibi davranır ve dışında olsa da hiçbir sınıf örnekleme sınıfı çağrılabilir belirtir. Üye işlevini statik olmayan üyeler için erişim yok. Belirtilen bir üye işlev `Static` sanal olamaz.|
   |[Sanal](../cpp/virtual-cpp.md)|Ne olursa olsun üye işlev çağrısını yapmak için kullanılan ifade bir nesne için doğru üye işlev çağrılırsa sağlar. Belirtilen bir üye işlev `Virtual` statik olamaz.|
   |**saf**|Hiçbir uygulama sanal üye işlev için bildirilen verilmesi gerektiğini gösterir. Bu nedenle, **saf** yalnızca sanal üye işlevlerde belirtilebilir. En az bir saf sanal üye işlevi içeren bir sınıf, soyut bir sınıf olarak kabul edilir. Soyut sınıftan türetilmiş sınıflar saf sanal üye işlevi uygulamak zorundadır veya onlar da soyut sınıflardır.|
   |[Satır içi](../cpp/inline-functions-cpp.md)|Üye işlevi çağrılan her yere üye işlev gövdesinin bir kopyasını eklemek için derleyicinin sağlar. Belirtilen bir üye işlev **satır içi** saf olamaz.|

- **.cpp dosyası**

   Saplama üye işlev uygulaması yazıldığı dosya konumunu ayarlar. Varsayılan olarak, üye işlevi ekleneceği sınıfı .cpp dosyası öğesine yazılır. Dosya adını değiştirmek için üç nokta düğmesine tıklayın. Üye işlev uygulaması, seçilen dosya içeriğini eklenir.

- **Yorum**

   Üstbilgi dosyasında üye işlevi için bir açıklama sağlar.

- **İşlev imzası**

   Üye işlevi tıkladığınızda kod içinde göründüğü gibi görüntüler **son**. Bu kutuda metni düzenleyemez. Üye işlevi değiştirmek için uygun kutulara Sihirbazı'nı değiştirin.

## <a name="see-also"></a>Ayrıca Bkz.

[Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)