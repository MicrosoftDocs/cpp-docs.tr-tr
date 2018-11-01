---
title: ATL Basit Nesne Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.simple.overview
helpviewer_keywords:
- ATL projects, adding objects
- ATL Simple Object Wizard
ms.assetid: f7f85741-9aad-4543-a917-a29b996364da
ms.openlocfilehash: 7b1d83e74c08f8cb0109c6e5db19ba0e4ebeda6e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522498"
---
# <a name="atl-simple-object-wizard"></a>ATL Basit Nesne Sihirbazı

Bu sihirbaz, projeye en az bir COM nesnesi ekler. Sihirbazın bu sayfası, nesnenizin ve COM işlevselliği için dosyaları ve C++ sınıfı tanımlayan adlarını belirtmek için kullanın.

Kullanım [seçenekleri](../../atl/reference/options-atl-simple-object-wizard.md) nesnenin iş parçacığı modeli, kendi toplama belirtmek için bu sihirbazın destekler ve ikili arabirimler ve Otomasyon destekleyip. Hata bilgisi arabirimi, bağlantı noktaları, Internet Explorer desteği ve ücretsiz iş parçacıklı sıralama desteği de belirtebilir.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008'den itibaren bu sihirbaz tarafından üretilen kayıt betiği altında COM bileşenlerini kaydolacak **HKEY_CURRENT_USER** yerine **HKEY_LOCAL_MACHINE**. Bu davranışı değiştirmek için Ayarla **tüm kullanıcılar için kayıt bileşeni** ATL Sihirbazı seçeneği.

## <a name="names"></a>Adlar

Nesne, arabirimi ve projenize eklenecek sınıfların adlarını belirtin. Dışında **kısa ad**, diğerlerinden bağımsız olarak tüm kutuları düzenlenebilir. Metni değiştirirseniz **kısa ad**, değişiklik bu sayfadaki tüm diğer kutularının adlarını olarak yansıtılır. Değiştirirseniz **coclass'ı** ad değişikliği COM bölümünde yansıtılır **türü** ve **ProgID** kutuları, ancak **arabirimi** adı değiştirmez. Bu adlandırma davranışı denetiminiz geliştirirken tüm adlarını kolayca tanımlanabilen yapmak için tasarlanmıştır.

> [!NOTE]
>  **Coclass'ı** nonattributed projelerine yalnızca düzenlenebilir. Projenizi öznitelikli, düzenleyemezsiniz **coclass'ı**.

## <a name="c"></a>C++

Nesne için oluşturulan C++ sınıfına ilişkin bilgi sağlar.

- **Kısa ad**

   Nesnenin kısaltılmış adını ayarlar. Belirler, sağladığınız ada `Class` ve `Coclass` adları **.cpp dosyası** ve **.h dosyası** adları **arabirimi** adı, **Türü** adları ve **ProgID**, bu alanları ayrı ayrı değiştirmediğiniz sürece.

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

   Öznitelikli nesneyi kullanan öznitelikleri yalnızca bir ATL projesine ekleyebilirsiniz. Destek özniteliğine sahip bir ATL projesi için bu seçeneği belirlerseniz, Sihirbazı özniteliği destek projeye eklemek isteyip istemediğinizi belirtmenizi ister.

   Varsayılan olarak, bu seçeneği belirledikten sonra eklediğiniz herhangi bir nesne öznitelikli olarak atanan (onay kutusu seçilidir). Öznitelikleri kullanmayan nesne eklemek için bu kutusunu temizleyebilirsiniz.

   Bkz: [uygulama ayarları, ATL Proje Sihirbazı'nı](../../atl/reference/application-settings-atl-project-wizard.md) ve [öznitelikleri temel mekanizması](../../windows/basic-mechanics-of-attributes.md) daha fazla bilgi için.

## <a name="com"></a>COM

Nesne için COM işlevleri hakkında bilgi sağlar.

- **Coclass'ı**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfı adını ayarlar.

   > [!NOTE]
   > Öznitelikleri kullanarak projenizi oluşturmak ya da nesne öznitelikleri kullanır Bu sihirbaz sayfasındaki gösteriyorsa, ATL içermez çünkü bu seçeneği değiştiremezsiniz `coclass` özniteliği.

- **Türü**

   Ayarlar kayıt defterinde görünür nesne açıklaması

- **Arabirimi**

   Nesneniz için oluşturduğunuz arabirimi ayarlar. Bu arabirim, özel yöntemler içerir.

- **ProgID**

   Kapsayıcı nesnesinin CLSID yerine kullanabileceği adını ayarlar.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL Basit Nesne](../../atl/reference/adding-an-atl-simple-object.md)

