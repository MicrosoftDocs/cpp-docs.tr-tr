---
description: 'Daha fazla bilgi edinin: ATL Denetim Sihirbazı'
title: ATL Denetim Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.control.overview
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
- ATL Control Wizard
ms.assetid: 991f8e72-ffbc-4382-a4ce-e255acfba5b6
ms.openlocfilehash: 3dd36e9ad2e14a87b86a56b8c035c4d4f8407430
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165439"
---
# <a name="atl-control-wizard"></a>ATL Denetim Sihirbazı

ATL denetimine bir ATL projesine (veya ATL desteği olan bir MFC projesine) ekler. Bu Sihirbazı, üç tür denetimden birini eklemek için kullanabilirsiniz:

- Standart denetim

- Bileşik denetim

- DHTML denetimi

Bunlara ek olarak, en az bir denetim belirtebilirsiniz, bu da arabirimlerin çoğu kapsayıcıda açılması için varsayılanlar olarak sağlanmış olan [arabirimler](../../atl/reference/interfaces-atl-control-wizard.md) listesinden arabirimleri kaldırır. Sihirbazın **arabirimler** sayfasında denetim için desteklenecek arabirimleri ayarlayabilirsiniz.

## <a name="remarks"></a>Açıklamalar

Bu sihirbaz tarafından oluşturulan kayıt betiği, COM bileşenlerini HKEY_LOCAL_MACHINE yerine HKEY_CURRENT_USER altına kaydeder. Bu davranışı değiştirmek için, ATL sihirbazının **tüm kullanıcılar Için kayıt bileşeni** seçeneğini ayarlayın.

## <a name="names"></a>Adlar

Projenize eklenecek nesne, arabirim ve sınıfların adlarını belirtin. **Kısa ad** dışında, diğer tüm kutular bağımsız olarak değiştirilebilir. **Kısa ad** için metni değiştirirseniz, değişiklik bu sayfadaki diğer tüm kutuların adlarına yansıtılır. COM bölümünde **coclass** adını değiştirirseniz, değişiklik **tür** kutusuna yansıtılır, ancak **arabirim** adı ve **ProgID** değişmez. Bu adlandırma davranışı, denetiminizi geliştirirken tüm adların sizin için kolayca tanımlanabilir olmasını sağlayacak şekilde tasarlanmıştır.

> [!NOTE]
> **Coclass** yalnızca öznitelik olmayan denetimlerde düzenlenebilir. Projeniz öznitelik içeriyorsa, **coclass**'ı düzenleyemezsiniz.

### <a name="c"></a>C++

Nesnesini uygulamak için oluşturulan C++ sınıfı için bilgiler sağlar.

- **Kısa ad**

   Nesne için kısaltılmış adı ayarlar. Sağladığınız ad, sınıf ve **coclass** adlarını, dosyayı (. CPP ve. H) adları, arabirim adı ve **tür** adlarını tek tek değiştirmediğiniz müddetçe bu alanları.

- **Sınıf**

   Nesneyi uygulayan sınıfın adını ayarlar. Bu ad, ' C ' öncesinde, bir sınıf adı için tipik ön ek olan **kısa ad** içinde sağladığınız adı temel alır.

- **. h dosyası**

   Yeni nesnenin sınıfının başlık dosyasının adını ayarlar. Bu ad, varsayılan olarak, **kısa ad**'de sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek veya sınıf bildirimini mevcut bir dosyaya eklemek için üç nokta düğmesini tıklatın. Var olan bir dosyayı seçerseniz, sihirbaz, **son**' a kadar seçili konuma kaydetmez.

   Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda, sihirbaz sınıf bildiriminin dosya içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

- **. cpp dosyası**

   Yeni nesnenin sınıfının uygulama dosyasının adını ayarlar. Bu ad, varsayılan olarak, **kısa ad**'de sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek için üç nokta düğmesine tıklayın. Bu dosya, sihirbazda **son** ' a tıklaana kadar seçili konuma kaydedilmez.

   Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda sihirbaz, sınıf uygulamasının dosyanın içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

- **İlişkilendirilmesi**

   Nesnenin öznitelikleri kullanıp kullanmadığını belirtir. Öznitelikli ATL projesine bir nesne ekliyorsanız, bu seçenek seçilir ve değişiklik için kullanılamaz. Diğer bir deyişle, öznitelik desteğiyle oluşturulan bir projeye yalnızca öznitelikli nesneler ekleyebilirsiniz.

   Öznitelik kullanan bir ATL projesine öznitelikli bir nesne ekleyebilirsiniz. Öznitelik desteği olmayan bir ATL projesi için bu seçeneği belirlerseniz, sihirbaz projeye öznitelik desteği eklemek isteyip istemediğinizi belirtmenizi ister.

   Varsayılan olarak, bu seçeneği ayarladıktan sonra eklediğiniz tüm nesneler, öznitelikli olarak atanır (onay kutusu seçilidir). Öznitelikleri kullanmayan bir nesne eklemek için bu kutuyu temizleyebilirsiniz.

   Daha fazla bilgi için bkz. [uygulama ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [özniteliklerin temel mekanizması](../../windows/attributes/cpp-attributes-com-net.md#basic-mechanics-of-attributes) .

### <a name="com"></a>COM

Nesnesi için COM işlevselliği hakkında bilgi sağlar.

- **Coclass**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfının adını ayarlar.

   > [!NOTE]
   > Projenizi öznitelikleri kullanarak oluşturursanız veya bu sihirbaz sayfasında denetimin öznitelikleri kullandığı belirtirseniz, ATL **coclass** özniteliğini içermediğinden bu seçeneği değiştiremezsiniz.

- **Arabirim**

   Nesne için arabirimin adını ayarlar. Varsayılan olarak, bir arabirim adı "I" ile sona erer.

- **Tür**

   Kayıt defterinde görünecek nesne açıklamasını ayarlar

- **ProgID**

   Kapsayıcının nesnenin CLSID yerine kullanabileceği adı ayarlar. Bu alan otomatik olarak doldurulmuyor. Bu alanı el ile doldurmadıysanız, denetim diğer araçların kullanımına açık olmayabilir. Örneğin, bir olmadan oluşturulan ActiveX denetimleri, `ProgID` **ActiveX denetimi Ekle** iletişim kutusunda kullanılamaz. İletişim kutusu hakkında daha fazla bilgi için bkz. [ActiveX denetimleri ekleme](../../windows/adding-editing-or-deleting-controls.md#insert-activex-controls).

## <a name="see-also"></a>Ayrıca bkz.

[ATL denetimi](../../atl/reference/adding-an-atl-control.md)<br/>
[Bileşik denetime Işlevsellik ekleme](../../atl/adding-functionality-to-the-composite-control.md)<br/>
[ATL COM nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)
