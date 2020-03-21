---
title: ATL COM+ 1.0 Bileşeni Sihirbazı
ms.date: 05/08/2019
helpviewer_keywords:
- ATL projects, adding components
ms.assetid: 11670681-8671-4122-96a4-2e52f8dadce0
ms.openlocfilehash: eaecd0d4e6e2b024ce3312719e7104298d3f9a66
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075278"
---
# <a name="atl-com-10-component-wizard"></a>ATL COM+ 1.0 Bileşeni Sihirbazı

::: moniker range="vs-2019"

Bu sihirbaz, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=vs-2017"

Projenize, işlemler de dahil olmak üzere COM+ 1,0 hizmetlerini destekleyen bir nesne eklemek için bu sihirbazı kullanın.

Nesnenin çift arabirimleri ve Otomasyonu destekleyip desteklemediğini belirtebilirsiniz. Hata bilgileri arabirimi, gelişmiş nesne denetimi, işlemler ve zaman uyumsuz Message Queuing için de destek belirtebilirsiniz.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008 ile başlayarak, bu sihirbaz tarafından oluşturulan kayıt betiği, COM bileşenlerini **HKEY_LOCAL_MACHINE**yerine **HKEY_CURRENT_USER** altına kaydeder. Bu davranışı değiştirmek için, ATL sihirbazının **tüm kullanıcılar Için kayıt bileşeni** seçeneğini ayarlayın.

## <a name="names"></a>Adlar

Projenize eklenecek nesne, arabirim ve sınıfların adlarını belirtin. **Kısa ad**hariç olmak üzere, diğer tüm kutular diğerlerinden bağımsız olarak düzenlenebilir. **Kısa ad**için metni değiştirirseniz, değişiklik bu sayfadaki diğer tüm kutuların adlarına yansıtılır. COM bölümünde **coclass** adını değiştirirseniz, değişiklik **Type** ve **ProgID** kutularına yansıtılır, ancak **arabirim** adı değişmez. Bu adlandırma davranışı, denetiminizi geliştirirken tüm adların sizin için kolayca tanımlanabilir olmasını sağlayacak şekilde tasarlanmıştır.

- **Kısa ad**

   Nesne için kısaltılmış adı ayarlar. Sağladığınız ad, bu alanları ayrı olarak değiştirmediğiniz müddetçe, `Class` ve `Coclass` adlarını, **. cpp dosyasını** ve **. h dosya** adlarını **, arabirim** adını, **tür** adlarını ve **ProgID**'yi belirler.

- **. h dosyası**

   Yeni nesnenin sınıfının başlık dosyasının adını ayarlar. Bu ad, varsayılan olarak, **kısa ad**'de sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek veya sınıf bildirimini mevcut bir dosyaya eklemek için üç nokta düğmesini tıklatın. Var olan bir dosyayı seçerseniz, sihirbazda **son** ' a tıklaana kadar sihirbaz onu seçilen konuma kaydetmez.

   Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda, sihirbaz sınıf bildiriminin dosya içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

- **Sınıfı**

   Oluşturulacak sınıfın adını ayarlar. Bu ad, bir sınıf adı için tipik ön ek olan **kısa ad**' C ' ile verdiğiniz adı temel alır.

- **. cpp dosyası**

   Yeni nesnenin sınıfının uygulama dosyasının adını ayarlar. Bu ad, varsayılan olarak, **kısa ad**'de sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek için üç nokta düğmesine tıklayın. Bu dosya, sihirbazda **son** ' a tıklaana kadar seçili konuma kaydedilmez.

   Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda sihirbaz, sınıf uygulamasının dosyanın içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

- **İlişkilendirilmesi**

   Nesnenin öznitelikleri kullanıp kullanmadığını belirtir. Öznitelikli ATL projesine bir nesne ekliyorsanız, bu seçenek seçilir ve değişiklik için kullanılamaz. Diğer bir deyişle, öznitelik desteğiyle oluşturulan bir projeye yalnızca öznitelikli nesneler ekleyebilirsiniz.

   Öznitelik desteği olmayan bir ATL projesi için bu seçeneği belirlerseniz, sihirbaz projeye öznitelik desteği eklemek isteyip istemediğinizi belirtmenizi ister.

   Daha sonra eklediğiniz herhangi bir nesne varsayılan olarak öznitelikli şekilde belirlenir (onay kutusu seçilidir). Öznitelikleri kullanmayan bir nesne eklemek için bu kutuyu temizleyebilirsiniz.

   Daha fazla bilgi için bkz. [uygulama ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [özniteliklerin temel mekanizması](../../windows/basic-mechanics-of-attributes.md) .

### <a name="com"></a>COM

Nesnesi için COM işlevselliği hakkında bilgi sağlar.

- **Coclass**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfının adını ayarlar.

> [!NOTE]
>  Projenizi öznitelikleri kullanarak oluşturursanız veya bu sihirbaz sayfasında COM+ 1,0 bileşeninin öznitelikleri kullandığını belirtirseniz, ATL `coclass` özniteliğini içermediğinden bu seçeneği değiştiremezsiniz.

- **Tür**

   Kayıt defterinde görünecek nesne açıklamasını ayarlar

- **Arayüz**

   Nesneniz için oluşturduğunuz arabirimi ayarlar. Bu arabirim özel yöntemlerinizi içerir.

- **ProgID**

   Kapsayıcının nesnenin CLSID yerine kullanabileceği adı ayarlar.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM+ 1,0 bileşeni](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)
