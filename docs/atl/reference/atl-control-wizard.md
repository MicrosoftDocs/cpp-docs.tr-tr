---
title: ATL Denetim Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.control.overview
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
- ATL Control Wizard
ms.assetid: 991f8e72-ffbc-4382-a4ce-e255acfba5b6
ms.openlocfilehash: 58c3ebe4c2a15aa3f0d59191c37a7f2422a63ab5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261214"
---
# <a name="atl-control-wizard"></a>ATL Denetim Sihirbazı

ATL projesine (veya MFC projesinde ATL desteği olan) ekler ATL denetimi. Bu sihirbaz, üç denetim türlerinin birini eklemek için kullanabilirsiniz:

- Standart denetim

- Bileşik Denetim

- DHTML denetimi

Arabirimden kaldırma en az bir denetim ayrıca belirtebilirsiniz [arabirimleri](../../atl/reference/interfaces-atl-control-wizard.md) listesinde, çoğu kapsayıcılarda açmak için denetimleri için varsayılan olarak sağlanır. Denetim için desteklenen istediğiniz arabirimleri ayarlayabilirsiniz **arabirimleri** Sihirbazı sayfası.

## <a name="remarks"></a>Açıklamalar

Bu sihirbaz tarafından üretilen kayıt betiği COM bileşenlerini HKEY_LOCAL_MACHINE yerine HKEY_CURRENT_USER altında kaydeder. Bu davranışı değiştirmek için Ayarla **tüm kullanıcılar için kayıt bileşeni** ATL Sihirbazı seçeneği.

## <a name="names"></a>Adlar

Nesne, arabirimi ve projenize eklenecek sınıfların adlarını belirtin. Dışında **kısa ad**, diğer tüm kutularının bağımsız olarak değiştirilebilir. Metni değiştirirseniz **kısa ad**, değişiklik bu sayfadaki tüm diğer kutularının adlarını olarak yansıtılır. Değiştirirseniz **coclass'ı** ad değişikliği COM bölümünde yansıtılır **türü** kutusu, ancak **arabirimi** adı ve **ProgID** yapın değiştiremezsiniz. Bu adlandırma davranışı denetiminiz geliştirirken tüm adlarını kolayca tanımlanabilen yapmak için tasarlanmıştır.

> [!NOTE]
>  **Coclass'ı** yalnızca nonattributed denetimler düzenlenemez. Projenizi öznitelikli, düzenleyemezsiniz **coclass'ı**.

### <a name="c"></a>C++

Nesne uygulamak için oluşturulan C++ sınıfına ilişkin bilgi sağlar.

- **Kısa ad**

   Nesnenin kısaltılmış adını ayarlar. Sınıfı, sağladığınız ada belirler ve **coclass'ı** dosyasını adlandırır (. CPP ve. H) adları, arabirim adını ve **türü** alanlarla ayrı ayrı değiştirmediğiniz sürece adları.

- **Sınıfı**

   Nesne uygulayan sınıfın adını ayarlar. Bu ad, sağladığınız adına dayanarak **kısa ad**, 'C', tipik bir sınıf adı öneki öncesinde.

- **.h dosyası**

   Yeni nesne sınıfı için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız ada dayanır **kısa ad**. Dosya adı, tercih ettiğiniz bir konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesine tıklayın. Var olan bir dosya seçerseniz, sihirbaz, seçili konuma dek tıklatın kaydedilmeyecektir **son**.

   Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf bildirimi dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

- **.cpp dosyası**

   Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız ada dayanır **kısa ad**. Dosya adı, tercih ettiğiniz bir konuma kaydetmek için üç nokta düğmesine tıklayın. ' A kadar dosyasını seçili konuma kaydedilmez **son** Sihirbazı'nda.

   Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf uygulaması dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

- **Öznitelikli**

   Nesne öznitelikleri kullanıp kullanmadığını belirtir. Öznitelik atanmış ATL projesine nesne ekliyorsanız, bu seçenek, seçilen ve değiştirmek kullanılabilir. Diğer bir deyişle, yalnızca öznitelikli nesne özniteliği desteği ile oluşturulan bir projeye ekleyebilirsiniz.

   Öznitelikli nesneyi kullanan öznitelikleri yalnızca bir ATL projesine ekleyebilirsiniz. Destek özniteliğine sahip bir ATL projesi için bu seçeneği belirlerseniz, Sihirbazı özniteliği destek projeye eklemek isteyip istemediğinizi belirtmenizi ister.

   Varsayılan olarak, bu seçeneği belirledikten sonra eklediğiniz herhangi bir nesne öznitelikli olarak atanan (onay kutusu seçilidir). Öznitelikleri kullanmayan nesne eklemek için bu kutusunu temizleyebilirsiniz.

   Bkz: [uygulama ayarları, ATL Proje Sihirbazı'nı](../../atl/reference/application-settings-atl-project-wizard.md) ve [öznitelikleri temel mekanizması](../../windows/basic-mechanics-of-attributes.md) daha fazla bilgi için.

### <a name="com"></a>COM

Nesne için COM işlevleri hakkında bilgi sağlar.

- **Coclass'ı**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfı adını ayarlar.

   > [!NOTE]
   > Öznitelikleri kullanarak projenizi oluşturmak ya da Denetim öznitelikleri kullanır Bu sihirbaz sayfasındaki gösteriyorsa, ATL içermez çünkü bu seçeneği değiştiremezsiniz **coclass'ı** özniteliği.

- **Arabirimi**

   Nesne için arabirimin adını ayarlar. Varsayılan olarak, bir arabirim adı "I" ile eklenir.

- **Tür**

   Ayarlar kayıt defterinde görünür nesne açıklaması

- **ProgID**

   Kapsayıcı nesnesinin CLSID yerine kullanabileceği adını ayarlar. Bu alan otomatik olarak doldurulmamış. Bu alan el ile doldurmayın, denetimin diğer araçları kullanılamıyor olabilir. Örneğin, olmadan oluşturulan ActiveX denetimlerini bir `ProgID` kullanılamaz **ActiveX denetimi Ekle** iletişim kutusu. İletişim kutusu hakkında daha fazla bilgi için bkz. [ActiveX denetimi Ekle iletişim kutusu](../../windows/insert-activex-control-dialog-box.md).

## <a name="see-also"></a>Ayrıca bkz.

[ATL denetimi](../../atl/reference/adding-an-atl-control.md)<br/>
[Bileşik Denetime İşlevsellik Ekleme](../../atl/adding-functionality-to-the-composite-control.md)<br/>
[ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)
