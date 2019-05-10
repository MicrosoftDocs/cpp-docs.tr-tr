---
title: ATL Active Server Page bileşeni Sihirbazı
ms.date: 05/09/2019
helpviewer_keywords:
- ASP components, creating in ATL
ms.assetid: 5a5cb904-dbbf-44ea-ad3d-2ddd14c1d3c5
ms.openlocfilehash: d2f47176fb25b050e4b1f72053e4cbaaf89f569e
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524600"
---
# <a name="atl-active-server-page-component-wizard"></a>ATL Active Server Page bileşeni Sihirbazı

::: moniker range="vs-2019"

Bu sihirbaz, Visual Studio 2019 bulunan ve daha yeni değil.

::: moniker-end

::: moniker range="vs-2017"

Bu sihirbaz, Active Server Pages (ASP) bileşeni projeye ekler. Microsoft Internet Information Services (IIS) Web sayfası Gelişmiş geliştirme mimarisinin bir parçası olarak ASP bileşenleri kullanır.

Bu sihirbazı kullanarak model ve toplama desteğini bileşenin iş parçacığı belirtebilirsiniz. Hata bilgisi arabirimi, bağlantı noktaları ve ücretsiz iş parçacıklı sıralama desteği de belirtebilir.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008'den itibaren bu sihirbaz tarafından üretilen kayıt betiği COM bileşenlerini altında kaydeder **HKEY_CURRENT_USER** yerine **HKEY_LOCAL_MACHINE**. Bu davranışı değiştirmek için Ayarla **tüm kullanıcılar için kayıt bileşeni** ATL Sihirbazı seçeneği.

## <a name="names"></a>Adlar

Nesne, arabirimi ve projenize eklenecek sınıfların adlarını belirtin. Dışında **kısa ad**, diğerlerinden bağımsız olarak tüm kutuları düzenlenebilir. Metni değiştirirseniz **kısa ad**, değişiklik bu sayfadaki tüm diğer kutularının adlarını olarak yansıtılır.

Değiştirirseniz **coclass'ı** ad değişikliği COM bölümünde yansıtılır **türü** ve **ProgID** kutuları, ancak **arabirimi** adı değiştirmez. Bu adlandırma davranışı denetiminiz geliştirirken tüm adlarını kolayca tanımlanabilen yapmak için tasarlanmıştır.

### <a name="c"></a>C++

Nesne için oluşturulan C++ sınıfına ilişkin bilgi sağlar.

- **Kısa ad**

   Kök nesnenin adını ayarlar. Belirler, sağladığınız ada `Class` ve **coclass'ı** adları **.cpp dosyası** ve **.h dosyası** adları **arabirim**adı **türü** adları ve **ProgID**, bu alanları ayrı ayrı değiştirmediğiniz sürece.

- **.h dosyası**

   Yeni nesne sınıfı için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız ada dayanır **kısa ad**. Dosya adı, tercih ettiğiniz bir konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesine tıklayın. Var olan bir dosya seçerseniz, sihirbaz, seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.

   Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf bildirimi dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

- **Sınıfı**

   Oluşturulacak sınıfın adını ayarlar. Bu ad, sağladığınız adına dayanarak **kısa ad**, 'C', tipik bir sınıf adı öneki öncesinde.

- **.cpp dosyası**

   Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız ada dayanır **kısa ad**. Dosya adı, tercih ettiğiniz bir konuma kaydetmek için üç nokta düğmesine tıklayın. ' A kadar dosyasını seçili konuma kaydedilmez **son** Sihirbazı'nda.

   Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf uygulaması dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

- **Öznitelikli**

   Nesne öznitelikleri kullanıp kullanmadığını belirtir. Öznitelik atanmış ATL projesine nesne ekliyorsanız, bu seçenek, seçilen ve değiştirmek kullanılabilir. Diğer bir deyişle, yalnızca öznitelikli nesne özniteliği desteği ile oluşturulan bir projeye ekleyebilirsiniz.

   Destek özniteliğine sahip bir ATL projesi için bu seçeneği belirlerseniz, Sihirbazı özniteliği destek projeye eklemek isteyip istemediğinizi belirtmenizi ister.

   Öznitelikli gibi nonattributed projeleri için varsayılan olarak, bu seçeneği belirledikten sonra eklediğiniz tüm nesnelerin atanan (onay kutusu seçilidir). Öznitelikleri kullanmayan nesne eklemek için bu kutusunu temizleyebilirsiniz.

   Bkz: [uygulama ayarları, ATL Proje Sihirbazı'nı](../../atl/reference/application-settings-atl-project-wizard.md) ve [öznitelikleri temel mekanizması](../../windows/basic-mechanics-of-attributes.md) daha fazla bilgi için.

### <a name="com"></a>COM

Nesne için COM işlevleri hakkında bilgi sağlar.

- **Coclass'ı**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfı adını ayarlar. Projenizi veya bu nesne öznitelikleri kullanıyorsa, ATL içermez çünkü bu seçeneği değiştiremezsiniz **coclass'ı** özniteliği.

- **Tür**

   Coclass'ı için kayıt defterinde görünür nesne açıklaması ayarlar.

- **Arabirimi**

   Nesneniz için oluşturduğunuz arabirimi ayarlar. Bu arabirim, özel yöntemler içerir.

- **ProgID**

   Kapsayıcı nesnesinin CLSID yerine kullanabileceği adını ayarlar.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[ATL Active Server Page bileşeni](../../atl/reference/adding-an-atl-active-server-page-component.md)
