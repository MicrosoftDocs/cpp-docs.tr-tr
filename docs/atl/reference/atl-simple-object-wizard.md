---
description: 'Daha fazla bilgi edinin: ATL basit nesne Sihirbazı'
title: ATL Basit Nesne Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.simple.overview
helpviewer_keywords:
- ATL projects, adding objects
- ATL Simple Object Wizard
ms.assetid: f7f85741-9aad-4543-a917-a29b996364da
ms.openlocfilehash: c19613e1b1b6bd746106ff57a87dcf0f7d3ad838
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158666"
---
# <a name="atl-simple-object-wizard"></a>ATL Basit Nesne Sihirbazı

Bu sihirbaz projeye en az bir COM nesnesi ekler. Nesnenizin ve COM işlevlerinin C++ sınıfını ve dosyalarını tanımlayan adları belirtmek için sihirbazın bu sayfasını kullanın.

Nesnenin iş parçacığı modelini, toplama desteğini ve çift arabirimleri ve Otomasyonu destekleyip desteklemediğini belirlemek için bu sihirbazın [Seçenekler](../../atl/reference/options-atl-simple-object-wizard.md) sayfasını kullanın. Hata bilgileri arabirimi, bağlantı noktaları, Internet Explorer desteği ve serbest iş parçacıklı sıralama desteğini de belirtebilirsiniz.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008 ile başlayarak, bu sihirbaz tarafından oluşturulan kayıt betiği, COM bileşenlerini **HKEY_LOCAL_MACHINE** yerine **HKEY_CURRENT_USER** altına kaydeder. Bu davranışı değiştirmek için, ATL sihirbazının **tüm kullanıcılar Için kayıt bileşeni** seçeneğini ayarlayın.

## <a name="names"></a>Adlar

Projenize eklenecek nesne, arabirim ve sınıfların adlarını belirtin. **Kısa ad** dışında, diğer tüm kutular diğerlerinden bağımsız olarak düzenlenebilir. **Kısa ad** için metni değiştirirseniz, değişiklik bu sayfadaki diğer tüm kutuların adlarına yansıtılır. COM bölümünde **coclass** adını değiştirirseniz, değişiklik **Type** ve **ProgID** kutularına yansıtılır, ancak **arabirim** adı değişmez. Bu adlandırma davranışı, denetiminizi geliştirirken tüm adların sizin için kolayca tanımlanabilir olmasını sağlayacak şekilde tasarlanmıştır.

> [!NOTE]
> **Coclass** yalnızca öznitelik atanmış olmayan projelerde düzenlenebilir. Projeniz öznitelik içeriyorsa, **coclass**'ı düzenleyemezsiniz.

## <a name="c"></a>C++

Nesnesi için oluşturulan C++ sınıfı için bilgiler sağlar.

- **Kısa ad**

   Nesne için kısaltılmış adı ayarlar. Sağladığınız ad, `Class` `Coclass` Bu alanları ayrı olarak değiştirmediğiniz müddetçe, ve adlarını, **. cpp dosyasını** ve **. h dosya** adlarını, **arabirim** adını, **tür** adlarını ve **ProgID**'yi belirler.

- **. h dosyası**

   Yeni nesnenin sınıfının başlık dosyasının adını ayarlar. Bu ad, varsayılan olarak, **kısa ad**'de sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek veya sınıf bildirimini mevcut bir dosyaya eklemek için üç nokta düğmesini tıklatın. Var olan bir dosyayı seçerseniz, sihirbazda **son** ' a tıklaana kadar sihirbaz onu seçilen konuma kaydetmez.

   Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda, sihirbaz sınıf bildiriminin dosya içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

- **Sınıf**

   Oluşturulacak sınıfın adını ayarlar. Bu ad, ' C ' öncesinde, bir sınıf adı için tipik ön ek olan **kısa ad** içinde sağladığınız adı temel alır.

- **. cpp dosyası**

   Yeni nesnenin sınıfının uygulama dosyasının adını ayarlar. Bu ad, varsayılan olarak, **kısa ad**'de sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek için üç nokta düğmesine tıklayın. Bu dosya, sihirbazda **son** ' a tıklaana kadar seçili konuma kaydedilmez.

   Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda sihirbaz, sınıf uygulamasının dosyanın içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

- **İlişkilendirilmesi**

   Nesnenin öznitelikleri kullanıp kullanmadığını belirtir. Öznitelikli ATL projesine bir nesne ekliyorsanız, bu seçenek seçilir ve değişiklik için kullanılamaz. Diğer bir deyişle, öznitelik desteğiyle oluşturulan bir projeye yalnızca öznitelikli nesneler ekleyebilirsiniz.

   Öznitelik kullanan bir ATL projesine öznitelikli bir nesne ekleyebilirsiniz. Öznitelik desteği olmayan bir ATL projesi için bu seçeneği belirlerseniz, sihirbaz projeye öznitelik desteği eklemek isteyip istemediğinizi belirtmenizi ister.

   Varsayılan olarak, bu seçeneği ayarladıktan sonra eklediğiniz tüm nesneler, öznitelikli olarak atanır (onay kutusu seçilidir). Öznitelikleri kullanmayan bir nesne eklemek için bu kutuyu temizleyebilirsiniz.

   Daha fazla bilgi için bkz. [uygulama ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [özniteliklerin temel mekanizması](../../windows/attributes/cpp-attributes-com-net.md#basic-mechanics-of-attributes) .

## <a name="com"></a>COM

Nesnesi için COM işlevselliği hakkında bilgi sağlar.

- **Coclass**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfının adını ayarlar.

   > [!NOTE]
   > Projenizi öznitelikleri kullanarak oluşturursanız veya bu sihirbaz sayfasında nesnenin öznitelikleri kullandığı belirtirseniz, ATL özniteliğini içermediğinden bu seçeneği değiştiremezsiniz `coclass` .

- **Tür**

   Kayıt defterinde görünecek nesne açıklamasını ayarlar

- **Arabirim**

   Nesneniz için oluşturduğunuz arabirimi ayarlar. Bu arabirim özel yöntemlerinizi içerir.

- **ProgID**

   Kapsayıcının nesnenin CLSID yerine kullanabileceği adı ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[ATL basit nesnesi](../../atl/reference/adding-an-atl-simple-object.md)
