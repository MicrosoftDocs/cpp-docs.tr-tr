---
title: ATL Active Server Page Bileşeni Sihirbazı
ms.date: 05/09/2019
helpviewer_keywords:
- ASP components, creating in ATL
ms.assetid: 5a5cb904-dbbf-44ea-ad3d-2ddd14c1d3c5
ms.openlocfilehash: 191b739354827dc1b7f0fd22e5ba2fd57f7b14d0
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923771"
---
# <a name="atl-active-server-page-component-wizard"></a>ATL Active Server Page Bileşeni Sihirbazı

::: moniker range="msvc-160"

Bu sihirbaz, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

Bu sihirbaz, proje bir Active Server Pages (ASP) bileşenine ekler. Microsoft Internet Information Services (IIS), Gelişmiş Web sayfası geliştirme mimarisinin bir parçası olarak ASP bileşenlerini kullanır.

Bu Sihirbazı kullanarak, bileşenin iş parçacığı modelini ve toplama desteğini belirtebilirsiniz. Hata bilgileri arabirimi, bağlantı noktaları ve serbest iş parçacıklı sıralama desteğini de belirtebilirsiniz.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008 ile başlayarak, bu sihirbaz tarafından oluşturulan kayıt betiği, COM bileşenlerini **HKEY_LOCAL_MACHINE** yerine **HKEY_CURRENT_USER** altına kaydeder. Bu davranışı değiştirmek için, ATL sihirbazının **tüm kullanıcılar Için kayıt bileşeni** seçeneğini ayarlayın.

## <a name="names"></a>Adlar

Projenize eklenecek nesne, arabirim ve sınıfların adlarını belirtin. **Kısa ad** dışında, diğer tüm kutular diğerlerinden bağımsız olarak düzenlenebilir. **Kısa ad** için metni değiştirirseniz, değişiklik bu sayfadaki diğer tüm kutuların adlarına yansıtılır.

COM bölümünde **coclass** adını değiştirirseniz, değişiklik **Type** ve **ProgID** kutularına yansıtılır, ancak **arabirim** adı değişmez. Bu adlandırma davranışı, denetiminizi geliştirirken tüm adların sizin için kolayca tanımlanabilir olmasını sağlayacak şekilde tasarlanmıştır.

### <a name="c"></a>C++

Nesnesi için oluşturulan C++ sınıfı için bilgiler sağlar.

- **Kısa ad**

   Nesnenin kök adını ayarlar. Sağladığınız ad, `Class` Bu alanları ayrı olarak değiştirmediğiniz müddetçe, ve **coclass** adlarını, **. cpp dosyasını** ve **. h dosya** adlarını, **arabirim** adını, **tür** adlarını ve **ProgID** 'yi belirler.

- **. h dosyası**

   Yeni nesnenin sınıfının başlık dosyasının adını ayarlar. Bu ad, varsayılan olarak, **kısa ad** 'de sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek veya sınıf bildirimini mevcut bir dosyaya eklemek için üç nokta düğmesini tıklatın. Var olan bir dosyayı seçerseniz, sihirbazda **son** ' a tıklaana kadar sihirbaz onu seçilen konuma kaydetmez.

   Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son** ' a tıkladığınızda, sihirbaz sınıf bildiriminin dosya içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

- **Sınıf**

   Oluşturulacak sınıfın adını ayarlar. Bu ad, ' C ' öncesinde, bir sınıf adı için tipik ön ek olan **kısa ad** içinde sağladığınız adı temel alır.

- **. cpp dosyası**

   Yeni nesnenin sınıfının uygulama dosyasının adını ayarlar. Bu ad, varsayılan olarak, **kısa ad** 'de sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek için üç nokta düğmesine tıklayın. Bu dosya, sihirbazda **son** ' a tıklaana kadar seçili konuma kaydedilmez.

   Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son** ' a tıkladığınızda sihirbaz, sınıf uygulamasının dosyanın içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

- **İlişkilendirilmesi**

   Nesnenin öznitelikleri kullanıp kullanmadığını belirtir. Öznitelikli ATL projesine bir nesne ekliyorsanız, bu seçenek seçilir ve değişiklik için kullanılamaz. Diğer bir deyişle, öznitelik desteğiyle oluşturulan bir projeye yalnızca öznitelikli nesneler ekleyebilirsiniz.

   Öznitelik desteği olmayan bir ATL projesi için bu seçeneği belirlerseniz, sihirbaz projeye öznitelik desteği eklemek isteyip istemediğinizi belirtmenizi ister.

   Öznitelik atanmış olmayan projeler için varsayılan olarak, bu seçeneği ayarladıktan sonra eklediğiniz tüm nesneler, öznitelikli olarak atanır (onay kutusu seçilidir). Öznitelikleri kullanmayan bir nesne eklemek için bu kutuyu temizleyebilirsiniz.

   Daha fazla bilgi için bkz. [uygulama ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [özniteliklerin temel mekanizması](../../windows/attributes/cpp-attributes-com-net.md#basic-mechanics-of-attributes) .

### <a name="com"></a>COM

Nesnesi için COM işlevselliği hakkında bilgi sağlar.

- **Coclass**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfının adını ayarlar. Projeniz veya bu nesne öznitelikleri kullanıyorsa, ATL **coclass** özniteliğini içermediğinden bu seçeneği değiştiremezsiniz.

- **Tür**

   Coclass için kayıt defterinde görünecek nesne açıklamasını ayarlar.

- **Arabirim**

   Nesneniz için oluşturduğunuz arabirimi ayarlar. Bu arabirim özel yöntemlerinizi içerir.

- **ProgID**

   Kapsayıcının nesnenin CLSID yerine kullanabileceği adı ayarlar.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[ATL Active Server sayfa bileşeni](../../atl/reference/adding-an-atl-active-server-page-component.md)
