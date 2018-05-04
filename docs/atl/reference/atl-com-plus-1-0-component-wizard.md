---
title: ATL COM + 1.0 Bileşen Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.mts.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding components
- ATL COM+ 1.0 Component Wizard
ms.assetid: 11670681-8671-4122-96a4-2e52f8dadce0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 19151ca659f7bc3235f84eefb39b640c4856fa43
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="atl-com-10-component-wizard"></a>ATL COM + 1.0 Bileşen Sihirbazı
Projenize işlemleri dahil olmak üzere, COM + 1.0 hizmetlerini destekleyen bir nesne eklemek için bu sihirbazı kullanın.  
  
 Nesne çift arabirimler ve Otomasyon destekleyip desteklemediğini belirleyebilirsiniz. Hata bilgisi arabirimi, Gelişmiş nesne denetimi, işlemleri ve zaman uyumsuz message queuing için destek de belirtebilirsiniz.  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio 2008'den itibaren bu sihirbaz tarafından üretilen kayıt betik COM bileşenlerini altında kaydedeceksiniz **HKEY_CURRENT_USER** yerine **HKEY_LOCAL_MACHINE**. Bu davranışı değiştirmek için ayarlanmış **kayıt bileşeni tüm kullanıcılar için** ATL Sihirbazı'nın seçeneği.  
  
## <a name="names"></a>Adlar  
 Nesne, arabirim ve projenize eklemek için sınıflar için adlarını belirtin. Dışında **kısa ad**, diğer tüm kutularının bağımsız olarak diğer düzenlenebilir. Metni değiştirirseniz **kısa ad**, değişiklik bu sayfadaki tüm diğer kutularının adlarını yansıtılır. Değiştirirseniz **Coclass** COM bölümünde değişiklik adını yansıtılır **türü** ve **ProgID** kutuları, ancak **arabirimi** adı değiştirmez. Bu adlandırma davranış denetiminizi geliştirdikçe tüm adlar kolayca tanımlanabilen yapmak için tasarlanmıştır.  
  
 **Kısa ad**  
 Nesne için kısa ad ayarlar. Belirler sağladığınız ad `Class` ve `Coclass` adları, **.cpp dosya** ve **.h dosyası** adları, **arabirimi** adı, **Türü** adları ve **ProgID**, bu alanları ayrı ayrı değiştirmediğiniz sürece.  
  
 **.h dosyası**  
 Yeni nesne sınıfı için üstbilgi dosyası adını ayarlar. Varsayılan olarak, bu ad sağladığınız adına dayalı **kısa ad**. Dosya adı tercih ettiğiniz bir konuma kaydedin veya varolan bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini tıklatın. Varolan bir dosyanın seçerseniz, sihirbaz bunu seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf bildirimi dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
 **sınıfı**  
 Oluşturulacak sınıfın adını ayarlar. Bu ad, size sağlamak adına dayanarak **kısa ad**, öncesinde 'C', tipik bir sınıf adı öneki olarak.  
  
 **.cpp dosyası**  
 Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adının dayanır **kısa ad**. Dosya adı seçiminizi konuma kaydetmek için üç nokta düğmesini tıklatın. Tıklattığınız kadar dosya seçili konuma kaydedilmez **son** Sihirbazı'nda.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf uygulamasını dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
 **Öznitelikli**  
 Nesne öznitelikleri kullanıp kullanmadığını belirtir. Öznitelik atanmış ATL projesinde nesneyi ekliyorsanız, bu seçenek seçilen ve değiştirmek mevcut değil. Diğer bir deyişle, öznitelik desteği ile oluşturulan bir proje yalnızca öznitelikli nesneleri ekleyebilirsiniz.  
  
 Destek özniteliğine sahip bir ATL projesi için bu seçeneği seçerseniz, Sihirbazı özniteliği desteği projeye eklemek isteyip istemediğinizi belirtmek için ister.  
  
 Bu seçeneğin ayarlanması aşağıdaki eklediğiniz tüm nesnelerin öznitelikli (onay kutusu seçilidir) varsayılan olarak belirlenir. Öznitelikleri kullanmayan nesne eklemek için bu kutuyu temizleyebilirsiniz.  
  
 Bkz: [uygulama ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [temel öznitelikleri mekanizması](../../windows/basic-mechanics-of-attributes.md) daha fazla bilgi için.  
  
### <a name="com"></a>COM  
 Nesne için COM işlevleri hakkında bilgi sağlar.  
  
 **coclass'ı**  
 Nesne tarafından desteklenen arabirimleri listesini içeren bileşen sınıfı adını ayarlar.  
  
> [!NOTE]
>  Öznitelikleri kullanarak projenizi oluşturmak ya da bu sihirbaz sayfasındaki COM + 1.0 bileşeni özniteliklerini kullanır gösteriyorsa, ATL içermemesi bu seçeneği değiştiremezsiniz `coclass` özniteliği.  
  
 **Türü**  
 Kayıt defterinde görünür nesne açıklaması ayarlar  
  
 **Arabirimi**  
 Nesne için oluşturduğunuz arabirimi ayarlar. Bu arabirim, özel yöntemler içerir.  
  
 **ProgID**  
 Kapsayıcı nesne CLSID yerine kullanabileceğiniz adını ayarlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM + 1.0 bileşeni](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)

