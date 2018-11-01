---
title: ATL Active Server Page bileşeni Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.overview
helpviewer_keywords:
- ASP components, creating in ATL
- ATL Active Server Page Component Wizard
ms.assetid: 5a5cb904-dbbf-44ea-ad3d-2ddd14c1d3c5
ms.openlocfilehash: 80d7eefaa4b12d5aab8970f4b3c81fc644226e07
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50510870"
---
# <a name="atl-active-server-page-component-wizard"></a>ATL Active Server Page bileşeni Sihirbazı

Bu sihirbaz, Active Server Pages (ASP) bileşeni projeye ekler. Microsoft Internet Information Services (IIS) Web sayfası Gelişmiş geliştirme mimarisinin bir parçası olarak ASP bileşenleri kullanır.

Bu sihirbazı kullanarak model ve toplama desteğini bileşenin iş parçacığı belirtebilirsiniz. Hata bilgisi arabirimi, bağlantı noktaları ve ücretsiz iş parçacıklı sıralama desteği de belirtebilir.

> [!WARNING]
> Visual Studio 2017 sürüm 15.9 bu kod Sihirbazı kullanım dışıdır ve Visual Studio'nun gelecekteki bir sürümde kaldırılacak. Bu sihirbaz nadiren kullanılır. ATL ve MFC genel desteği, bu sihirbazın kaldırma işlemi etkilenmez. Bu kullanımdan kaldırma hakkındaki görüşlerinizi paylaşmak istiyorsanız, Lütfen tamamlayın [bu anketi](https://www.surveymonkey.com/r/QDWKKCN). Geri bildiriminiz bizim için önemlidir.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008'den itibaren bu sihirbaz tarafından üretilen kayıt betiği altında COM bileşenlerini kaydolacak **HKEY_CURRENT_USER** yerine **HKEY_LOCAL_MACHINE**. Bu davranışı değiştirmek için Ayarla **tüm kullanıcılar için kayıt bileşeni** ATL Sihirbazı seçeneği.

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

- **Türü**

   Coclass'ı için kayıt defterinde görünür nesne açıklaması ayarlar.

- **Arabirimi**

   Nesneniz için oluşturduğunuz arabirimi ayarlar. Bu arabirim, özel yöntemler içerir.

- **ProgID**

   Kapsayıcı nesnesinin CLSID yerine kullanabileceği adını ayarlar.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL Active Server Page bileşeni](../../atl/reference/adding-an-atl-active-server-page-component.md)
