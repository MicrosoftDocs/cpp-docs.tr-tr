---
title: ATL Özellik Sayfası Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.ppg.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding property pages
- ATL Property Page Wizard
ms.assetid: 6113e325-facd-4f68-b491-144d75209922
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17c5d863ef14aeddcd66f813449b514360f657a4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359788"
---
# <a name="atl-property-page-wizard"></a>ATL Özellik Sayfası Sihirbazı
Bu sihirbaz [özellik sayfası ATL projeye ekler](../../atl/reference/adding-an-atl-property-page.md) veya MFC projesinde ATL desteği. ATL özellik sayfası özelliklerini ayarlamak için bir kullanıcı arabirimi sağlar (veya yöntemleri çağırma) bir veya daha fazla COM Nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio 2008'den itibaren bu sihirbaz tarafından üretilen kayıt betik COM bileşenlerini altında kaydedeceksiniz **HKEY_CURRENT_USER** yerine **HKEY_LOCAL_MACHINE**. Bu davranışı değiştirmek için ayarlanmış **kayıt bileşeni tüm kullanıcılar için** ATL Sihirbazı'nın seçeneği.  
  
## <a name="names"></a>Adlar  
 Nesne, arabirim ve projenize eklemek için sınıflar için adlarını belirtin. Dışında **kısa ad**, diğer tüm kutularının bağımsız olarak düzenlenebilir. Metni değiştirirseniz **kısa ad**, değişiklik bu sayfadaki tüm diğer kutularının adlarını yansıtılır. Değiştirirseniz **Coclass** COM bölümünde değişiklik adını yansıtılır **türü** ve **ProgID** kutuları. Bu adlandırma davranış özellik sayfası geliştirdikçe tüm adlar kolayca tanımlanabilen yapmak için tasarlanmıştır.  
  
> [!NOTE]
>  **Coclass'ı** yalnızca nonattributed projelerde düzenlenebilir. Projenizi öznitelikli, düzenleyemezsiniz **coclass'ı**.  
  
### <a name="c"></a>C++  
 Nesne uygulamak için oluşturulan C++ sınıfı için bilgiler sağlar.  
  
|||  
|-|-|  
|Terim|Tanım|  
|**Kısa ad**|Nesne için kısa ad ayarlar. Sınıfı, sağladığınız ad belirler ve **Coclass** adları, dosyanın (**.cpp** ve **.h**) adları, **türü** adı ve  **ProgID**, bu alanları ayrı ayrı değiştirmediğiniz sürece.|  
|**.h dosyası**|Yeni nesne sınıfı için üstbilgi dosyası adını ayarlar. Varsayılan olarak, bu ad sağladığınız adına dayalı **kısa ad**. Dosya adı tercih ettiğiniz bir konuma kaydedin veya varolan bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini tıklatın. Varolan bir dosyanın seçerseniz, sihirbaz bunu seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.<br /><br /> Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf bildirimi dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.|  
|**sınıfı**|Nesne uygulayan sınıf adını ayarlar. Bu ad, sağladığınız adına dayanarak **kısa ad**, öncesinde 'C', tipik bir sınıf adı öneki olarak.|  
|**.cpp dosyası**|Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad sağladığınız adına dayalı **kısa ad**. Dosya adı seçiminizi konuma kaydetmek için üç nokta düğmesini tıklatın. Tıklattığınız kadar dosya seçili konuma kaydedilmez **son** Sihirbazı'nda.<br /><br /> Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf uygulamasını dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.|  
|**Öznitelikli**|Nesne öznitelikleri kullanıp kullanmadığını belirtir. Yalnızca bir öznitelik atanmış ATL projesine bir nesne ekleme, bu seçeneği seçili değilse ve değiştirmek mevcut değil, diğer bir deyişle, ekleyebileceğiniz öznitelik desteği ile oluşturulan bir proje nesneleri öznitelikli.<br /><br /> Öznitelikli nesne öznitelikleri kullanan yalnızca bir ATL projesine ekleyebilirsiniz. Destek özniteliğine sahip bir ATL projesi için bu seçeneği seçerseniz, Sihirbazı özniteliği desteği projeye eklemek isteyip istemediğinizi belirtmek için ister.<br /><br /> Varsayılan olarak, bu seçeneği belirledikten sonra eklediğiniz tüm nesnelerin öznitelikli olarak atanmış (onay kutusu seçilidir). Öznitelikleri kullanmayan nesne eklemek için bu kutuyu temizleyebilirsiniz.<br /><br /> Bkz: [uygulama ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [temel öznitelikleri mekanizması](../../windows/basic-mechanics-of-attributes.md) daha fazla bilgi için.|  
  
### <a name="com"></a>COM  
 Nesne için COM işlevleri hakkında bilgi sağlar.  
  
 **coclass'ı**  
 Nesne tarafından desteklenen arabirimleri listesini içeren bileşen sınıfı adını ayarlar.  
  
> [!NOTE]
>  Öznitelikleri kullanarak projenizi oluşturmak ya da bu sihirbaz sayfasındaki özellik sayfası öznitelikleri kullandığını gösteriyorsa, ATL içermemesi bu seçeneği değiştiremezsiniz `coclass` özniteliği.  
  
 **Türü**  
 Kayıt defterinde görünür nesne açıklaması ayarlar  
  
 **ProgID**  
 Kapsayıcı nesne CLSID yerine kullanabileceğiniz adını ayarlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Özellik Sayfası Sihirbazı Seçenekleri](../../atl/reference/options-atl-property-page-wizard.md)   
 [Dizeleri, ATL Özellik Sayfası Sihirbazı](../../atl/reference/strings-atl-property-page-wizard.md)   
 [Örnek: Özellik Sayfası Uygulama](../../atl/example-implementing-a-property-page.md)

