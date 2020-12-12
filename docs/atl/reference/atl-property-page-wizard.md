---
description: 'Daha fazla bilgi edinin: ATL Özellik sayfası Sihirbazı'
title: ATL Özellik Sayfası Sihirbazı
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.ppg.overview
helpviewer_keywords:
- ATL projects, adding property pages
- ATL Property Page Wizard
ms.assetid: 6113e325-facd-4f68-b491-144d75209922
ms.openlocfilehash: 4ee266f66eddd85425982a1a4dbbb11613b74ad7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165270"
---
# <a name="atl-property-page-wizard"></a>ATL Özellik Sayfası Sihirbazı

::: moniker range="msvc-160"

Bu sihirbaz, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

Bu sihirbaz bir ATL projesine veya ATL desteği olan bir MFC projesine bir [özellik sayfası ekler](../../atl/reference/adding-an-atl-property-page.md) . ATL Özellik sayfası bir veya daha fazla COM nesnesinin özelliklerini ayarlamak için bir kullanıcı arabirimi sağlar.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008 ile başlayarak, bu sihirbaz tarafından oluşturulan kayıt betiği, COM bileşenlerini **HKEY_LOCAL_MACHINE** yerine **HKEY_CURRENT_USER** altına kaydeder. Bu davranışı değiştirmek için, ATL sihirbazının **tüm kullanıcılar Için kayıt bileşeni** seçeneğini ayarlayın.

## <a name="names"></a>Adlar

Projenize eklenecek nesne, arabirim ve sınıfların adlarını belirtin. **Kısa ad** dışında, diğer tüm kutular bağımsız olarak düzenlenebilir. **Kısa ad** için metni değiştirirseniz, değişiklik bu sayfadaki diğer tüm kutuların adlarına yansıtılır. COM bölümünde **coclass** adını değiştirirseniz, değişiklik **Type** ve **ProgID** kutularına yansıtılır. Bu adlandırma davranışı, özellik sayfanızı geliştirirken tüm adların sizin için kolayca tanımlanabilir olmasını sağlayacak şekilde tasarlanmıştır.

> [!NOTE]
> **Coclass** yalnızca öznitelik atanmış olmayan projelerde düzenlenebilir. Projeniz öznitelik içeriyorsa, **coclass**'ı düzenleyemezsiniz.

### <a name="c"></a>C++

Nesnesini uygulamak için oluşturulan C++ sınıfı için bilgiler sağlar.

|Süre|Tanım|
|-|-|
|**Kısa ad**|Nesne için kısaltılmış adı ayarlar. Sağladığınız ad, bu alanları ayrı ayrı değiştirmediğiniz müddetçe sınıf ve **coclass** adlarını, dosyayı (**. cpp** ve **. h**) adlarını, **tür** adını ve **ProgID**'yi belirler.|
|**. h dosyası**|Yeni nesnenin sınıfının başlık dosyasının adını ayarlar. Bu ad, varsayılan olarak, **kısa ad**'de sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek veya sınıf bildirimini mevcut bir dosyaya eklemek için üç nokta düğmesini tıklatın. Var olan bir dosyayı seçerseniz, sihirbazda **son** ' a tıklaana kadar sihirbaz onu seçilen konuma kaydetmez.<br /><br /> Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda, sihirbaz sınıf bildiriminin dosya içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.|
|**Sınıf**|Nesneyi uygulayan sınıfın adını ayarlar. Bu ad, ' C ' öncesinde, bir sınıf adı için tipik ön ek olan **kısa ad** içinde sağladığınız adı temel alır.|
|**. cpp dosyası**|Yeni nesnenin sınıfının uygulama dosyasının adını ayarlar. Bu ad, varsayılan olarak, **kısa ad**'de sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek için üç nokta düğmesine tıklayın. Bu dosya, sihirbazda **son** ' a tıklaana kadar seçili konuma kaydedilmez.<br /><br /> Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda sihirbaz, sınıf uygulamasının dosyanın içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.|
|**İlişkilendirilmesi**|Nesnenin öznitelikleri kullanıp kullanmadığını belirtir. Öznitelikli ATL projesine bir nesne ekliyorsanız, bu seçenek seçilir ve değiştirilemez, diğer bir deyişle, öznitelik desteğiyle oluşturulan bir projeye yalnızca öznitelikli nesneler ekleyebilirsiniz.<br /><br /> Öznitelik kullanan bir ATL projesine öznitelikli bir nesne ekleyebilirsiniz. Öznitelik desteği olmayan bir ATL projesi için bu seçeneği belirlerseniz, sihirbaz projeye öznitelik desteği eklemek isteyip istemediğinizi belirtmenizi ister.<br /><br /> Varsayılan olarak, bu seçeneği ayarladıktan sonra eklediğiniz tüm nesneler, öznitelikli olarak atanır (onay kutusu seçilidir). Öznitelikleri kullanmayan bir nesne eklemek için bu kutuyu temizleyebilirsiniz.<br /><br /> Daha fazla bilgi için bkz. [uygulama ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [özniteliklerin temel mekanizması](../../windows/attributes/cpp-attributes-com-net.md#basic-mechanics-of-attributes) .|

### <a name="com"></a>COM

Nesnesi için COM işlevselliği hakkında bilgi sağlar.

- **Coclass**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfının adını ayarlar.

   > [!NOTE]
   > Projenizi öznitelikleri kullanarak oluşturursanız veya bu sihirbaz sayfasında Özellik sayfasının öznitelikler kullandığını belirtirseniz, ATL özniteliğini içermediğinden bu seçeneği değiştiremezsiniz `coclass` .

- **Tür**

   Kayıt defterinde görünecek nesne açıklamasını ayarlar

- **ProgID**

   Kapsayıcının nesnenin CLSID yerine kullanabileceği adı ayarlar.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Seçenekler, ATL Özellik sayfası Sihirbazı](../../atl/reference/options-atl-property-page-wizard.md)<br/>
[Dizeler, ATL Özellik sayfası Sihirbazı](../../atl/reference/strings-atl-property-page-wizard.md)<br/>
[Örnek: Özellik sayfası uygulama](../../atl/example-implementing-a-property-page.md)
