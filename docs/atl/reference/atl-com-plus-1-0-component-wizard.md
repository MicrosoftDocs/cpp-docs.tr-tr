---
title: ATL COM + 1.0 bileşeni Sihirbazı
ms.date: 05/08/2019
helpviewer_keywords:
- ATL projects, adding components
ms.assetid: 11670681-8671-4122-96a4-2e52f8dadce0
ms.openlocfilehash: e8ab9238f921b3c4e5c0eb396f0b26e46ab2a244
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524681"
---
# <a name="atl-com-10-component-wizard"></a>ATL COM + 1.0 bileşeni Sihirbazı

::: moniker range="vs-2019"

Bu sihirbaz, Visual Studio 2019 bulunan ve daha yeni değil.

::: moniker-end

::: moniker range="vs-2017"

Nesne işlemleri dahil olmak üzere, COM + 1.0 hizmetlerini destekleyen projenize eklemek için bu sihirbazı kullanın.

Çift arabirimler ve Otomasyon nesne destekleyip desteklemediğini belirleyebilirsiniz. Hata bilgisi arabirimi, Gelişmiş nesne denetimi, işlemler ve zaman uyumsuz ileti sıraya alma desteği de belirtebilir.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008'den itibaren bu sihirbaz tarafından üretilen kayıt betiği altında COM bileşenlerini kaydolacak **HKEY_CURRENT_USER** yerine **HKEY_LOCAL_MACHINE**. Bu davranışı değiştirmek için Ayarla **tüm kullanıcılar için kayıt bileşeni** ATL Sihirbazı seçeneği.

## <a name="names"></a>Adlar

Nesne, arabirimi ve projenize eklenecek sınıfların adlarını belirtin. Dışında **kısa ad**, diğerlerinden bağımsız olarak tüm kutuları düzenlenebilir. Metni değiştirirseniz **kısa ad**, değişiklik bu sayfadaki tüm diğer kutularının adlarını olarak yansıtılır. Değiştirirseniz **coclass'ı** ad değişikliği COM bölümünde yansıtılır **türü** ve **ProgID** kutuları, ancak **arabirimi** adı değiştirmez. Bu adlandırma davranışı denetiminiz geliştirirken tüm adlarını kolayca tanımlanabilen yapmak için tasarlanmıştır.

- **Kısa ad**

   Nesnenin kısaltılmış adını ayarlar. Belirler, sağladığınız ada `Class` ve `Coclass` adları **.cpp dosyası** ve **.h dosyası** adları **arabirimi** adı, **Türü** adları ve **ProgID**, bu alanları ayrı ayrı değiştirmediğiniz sürece.

- **.h dosyası**

   Yeni nesne sınıfı için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız ada dayanır **kısa ad**. Dosya adı, tercih ettiğiniz bir konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesine tıklayın. Var olan bir dosya seçerseniz, sihirbaz, seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.

   Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf bildirimi dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

- **Sınıfı**

   Oluşturulacak sınıfın adını ayarlar. Bu ad, size sağlamak adına dayanarak **kısa ad**, 'C', tipik bir sınıf adı öneki öncesinde.

- **.cpp dosyası**

   Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **kısa ad**. Dosya adı, tercih ettiğiniz bir konuma kaydetmek için üç nokta düğmesine tıklayın. ' A kadar dosyasını seçili konuma kaydedilmez **son** Sihirbazı'nda.

   Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf uygulaması dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

- **Öznitelikli**

   Nesne öznitelikleri kullanıp kullanmadığını belirtir. Öznitelik atanmış ATL projesine nesne ekliyorsanız, bu seçenek, seçilen ve değiştirmek kullanılabilir. Diğer bir deyişle, yalnızca öznitelikli nesne özniteliği desteği ile oluşturulan bir projeye ekleyebilirsiniz.

   Destek özniteliğine sahip bir ATL projesi için bu seçeneği belirlerseniz, Sihirbazı özniteliği destek projeye eklemek isteyip istemediğinizi belirtmenizi ister.

   Bu seçeneğin ayarlanması aşağıdaki eklediğiniz herhangi bir nesne öznitelikli (onay kutusu seçilidir) varsayılan olarak belirlenmiştir. Öznitelikleri kullanmayan nesne eklemek için bu kutusunu temizleyebilirsiniz.

   Bkz: [uygulama ayarları, ATL Proje Sihirbazı'nı](../../atl/reference/application-settings-atl-project-wizard.md) ve [öznitelikleri temel mekanizması](../../windows/basic-mechanics-of-attributes.md) daha fazla bilgi için.

### <a name="com"></a>COM

Nesne için COM işlevleri hakkında bilgi sağlar.

- **Coclass'ı**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfı adını ayarlar.

> [!NOTE]
>  Öznitelikleri kullanarak projenizi oluşturmak ya da COM + 1.0 bileşeni öznitelikleri kullanır Bu sihirbaz sayfasındaki gösteriyorsa, ATL içermez çünkü bu seçeneği değiştiremezsiniz `coclass` özniteliği.

- **Tür**

   Ayarlar kayıt defterinde görünür nesne açıklaması

- **Arabirimi**

   Nesneniz için oluşturduğunuz arabirimi ayarlar. Bu arabirim, özel yöntemler içerir.

- **ProgID**

   Kapsayıcı nesnesinin CLSID yerine kullanabileceği adını ayarlar.
   
::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM + 1.0 bileşeni](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)
