---
title: ATL Denetim Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
- ATL Control Wizard
ms.assetid: 991f8e72-ffbc-4382-a4ce-e255acfba5b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1df64cd0661a7f905ebcc068efb698306ac9007e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="atl-control-wizard"></a>ATL Denetim Sihirbazı
ATL projesinde (veya MFC projesinde ATL desteği) ekler ATL Denetim. Üç tür denetimleri birini eklemek için bu sihirbazı kullanın:  
  
-   Standart denetimi  
  
-   Bileşik Denetim  
  
-   DHTML denetimi  
  
 Ayrıca, en az bir denetim arabirimlerinden kaldırma belirleyebileceğiniz [arabirimleri](../../atl/reference/interfaces-atl-control-wizard.md) çoğu kapsayıcılarında açmak için denetimleri için varsayılan olarak sağlanan listesi. Denetim için desteklenen istediğiniz arabirimleri ayarlayabilirsiniz **arabirimleri** Sihirbazı sayfası.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sihirbaz tarafından üretilen kayıt betik COM bileşenlerini HKEY_LOCAL_MACHINE yerine HKEY_CURRENT_USER altında kaydeder. Bu davranışı değiştirmek için ayarlanmış **kayıt bileşeni tüm kullanıcılar için** ATL Sihirbazı'nın seçeneği.  
  
## <a name="names"></a>Adlar  
 Nesne, arabirim ve projenize eklemek için sınıflar için adlarını belirtin. Dışında **kısa ad**, diğer tüm kutularının bağımsız olarak değiştirilebilir. Metni değiştirirseniz **kısa ad**, değişiklik bu sayfadaki tüm diğer kutularının adlarını yansıtılır. Değiştirirseniz **Coclass** COM bölümünde değişiklik adını yansıtılır **türü** kutusu, ancak **arabirimi** adı ve **ProgID** yapın değiştiremez. Bu adlandırma davranış denetiminizi geliştirdikçe tüm adlar kolayca tanımlanabilen yapmak için tasarlanmıştır.  
  
> [!NOTE]
>  **Coclass'ı** yalnızca nonattributed denetimlere düzenlenebilir. Projenizi öznitelikli, düzenleyemezsiniz **coclass'ı**.  
  
### <a name="c"></a>C++  
 Nesne uygulamak için oluşturulan C++ sınıfı için bilgiler sağlar.  
  
 **Kısa ad**  
 Nesne için kısa ad ayarlar. Sınıfı, sağladığınız ad belirler ve **Coclass** adları, dosyanın (. CPP ve. H) adları, arabirim adı ve **türü** alanlarla ayrı ayrı değiştirmediğiniz sürece adları.  
  
 **sınıfı**  
 Nesne uygulayan sınıf adını ayarlar. Bu ad, sağladığınız adına dayanarak **kısa ad**, öncesinde 'C', tipik bir sınıf adı öneki olarak.  
  
 **.h dosyası**  
 Yeni nesne sınıfı için üstbilgi dosyası adını ayarlar. Varsayılan olarak, bu ad sağladığınız adına dayalı **kısa ad**. Dosya adı tercih ettiğiniz bir konuma kaydedin veya varolan bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini tıklatın. Varolan bir dosyanın seçerseniz, sihirbaz bunu seçili konuma dek tıklatın kaydedilmeyecektir **son**.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf bildirimi dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
 **.cpp dosyası**  
 Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad sağladığınız adına dayalı **kısa ad**. Dosya adı seçiminizi konuma kaydetmek için üç nokta düğmesini tıklatın. Tıklattığınız kadar dosya seçili konuma kaydedilmez **son** Sihirbazı'nda.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf uygulamasını dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
 **Öznitelikli**  
 Nesne öznitelikleri kullanıp kullanmadığını belirtir. Öznitelik atanmış ATL projesinde nesneyi ekliyorsanız, bu seçenek seçilen ve değiştirmek mevcut değil. Diğer bir deyişle, öznitelik desteği ile oluşturulan bir proje yalnızca öznitelikli nesneleri ekleyebilirsiniz.  
  
 Öznitelikli nesne öznitelikleri kullanan yalnızca bir ATL projesine ekleyebilirsiniz. Destek özniteliğine sahip bir ATL projesi için bu seçeneği seçerseniz, Sihirbazı özniteliği desteği projeye eklemek isteyip istemediğinizi belirtmek için ister.  
  
 Varsayılan olarak, bu seçeneği belirledikten sonra eklediğiniz tüm nesnelerin öznitelikli olarak atanmış (onay kutusu seçilidir). Öznitelikleri kullanmayan nesne eklemek için bu kutuyu temizleyebilirsiniz.  
  
 Bkz: [uygulama ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [temel öznitelikleri mekanizması](../../windows/basic-mechanics-of-attributes.md) daha fazla bilgi için.  
  
### <a name="com"></a>COM  
 Nesne için COM işlevleri hakkında bilgi sağlar.  
  
 **coclass'ı**  
 Nesne tarafından desteklenen arabirimleri listesini içeren bileşen sınıfı adını ayarlar.  
  
> [!NOTE]
>  Öznitelikleri kullanarak projenizi oluşturmak ya da bu sihirbaz sayfasında denetim öznitelikleri kullanır gösteriyorsa, ATL içermemesi bu seçeneği değiştiremezsiniz **coclass** özniteliği.  
  
 **Arabirimi**  
 Nesne için arabirim adını ayarlar. Varsayılan olarak bir arabirim adı "I" eklenir.  
  
 **Türü**  
 Kayıt defterinde görünür nesne açıklaması ayarlar  
  
 **ProgID**  
 Kapsayıcı nesne CLSID yerine kullanabileceğiniz adını ayarlar. Bu alan otomatik olarak doldurulmamış. Bu alan el ile doldurmayın, diğer araçları denetimi kullanılamayabilir. Örneğin, olmadan oluşturulan ActiveX denetimlerini bir `ProgID` kullanılamayan **ActiveX denetimi Ekle** iletişim kutusu. İletişim kutusu hakkında daha fazla bilgi için bkz: [ActiveX denetimi Ekle iletişim kutusu](../../windows/insert-activex-control-dialog-box.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL denetimi](../../atl/reference/adding-an-atl-control.md)   
 [Bileşik Denetim işlevsellik ekleme](../../atl/adding-functionality-to-the-composite-control.md)   
 [ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)

