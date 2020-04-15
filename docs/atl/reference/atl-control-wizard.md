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
ms.openlocfilehash: a10c5c358901122dda37b395c1f0fa5cdc30ce30
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321707"
---
# <a name="atl-control-wizard"></a>ATL Denetim Sihirbazı

Bir ATL projesine (veya ATL destekli bir MFC projesine) Bir ATL denetimi ekler. Bu sihirbazı üç tür denetimden birini eklemek için kullanabilirsiniz:

- Standart kontrol

- Kompozit kontrol

- DHTML denetimi

Ayrıca, çoğu kapsayıcıda açılacak denetimler için varsayılan olarak sağlanan [arabirimleri Arabirimler](../../atl/reference/interfaces-atl-control-wizard.md) listesinden kaldırarak en az denetim belirtebilirsiniz. Sihirbazın **Arabirimleri** sayfasında denetim için desteklenen istediğiniz arabirimleri ayarlayabilirsiniz.

## <a name="remarks"></a>Açıklamalar

Bu sihirbaz tarafından üretilen kayıt komut dosyası, COM bileşenlerini HKEY_LOCAL_MACHINE yerine HKEY_CURRENT_USER altında kaydeder. Bu davranışı değiştirmek için, ATL Sihirbazı'nın tüm kullanıcılar için **Kayıt bileşenini** ayarlayın.

## <a name="names"></a>Adlar

Projenize eklenecek nesne, arabirim ve sınıfların adlarını belirtin. Kısa **ad**dışında, diğer tüm kutular bağımsız olarak değiştirilebilir. **Kısa ad**metnini değiştirirseniz, değişiklik bu sayfadaki diğer tüm kutuların adlarında yansıtılır. COM bölümündeki **Coclass** adını değiştirirseniz, değişiklik **Tür** kutusuna yansıtılır, ancak **Arabirim** adı ve **ProgID** değişmez. Bu adlandırma davranışı, denetiminizi geliştirirken tüm adları sizin için kolayca tanımlanabilir hale getirmek için tasarlanmıştır.

> [!NOTE]
> **Coclass** yalnızca atfedilmeyen denetimlerde değiştirilebilir. Projeniz atfedilen, **Coclass'ı**kaldıramazsınız.

### <a name="c"></a>C++

Nesneyi uygulamak için oluşturulan C++ sınıfı için bilgi sağlar.

- **Kısa ad**

   Nesnenin kısaltılmış adını ayarlar. Sağladığınız ad sınıf ve **Coclass** adlarını, dosyayı (. CPP ve . H) adları, arabirim adı ve **Tür** adları, bu alanları tek tek değiştirmediğiniz sürece.

- **Sınıfı**

   Nesneyi uygulayan sınıfın adını ayarlar. Bu ad, bir sınıf adı için tipik önek olan 'C' öncesinde **Kısa adla**sağladığınız ada dayanır.

- **.h dosyası**

   Yeni nesnenin sınıfı için üstbilgi dosyasının adını ayarlar. Varsayılan olarak, bu ad **Kısa ad**da sağladığınız adı temel alır. Dosya adını seçtiğiniz konuma kaydetmek veya sınıf bildirimini varolan bir dosyaya eklemek için elips düğmesini tıklatın. Varolan bir dosyayı seçerseniz, **sihirbaz bunu Bitiş'i**tıklatana kadar seçili konuma kaydetmez.

   Sihirbaz bir dosyanın üzerine yazmıyor. Varolan bir dosyanın adını seçerseniz, **Bitiş'i**tıklattığınızda, sihirbaz sınıf bildiriminin dosyanın içeriğine eklenip eklenmeyeceğini belirtmenizi ister. Dosyayı eklemek için **Evet'i** tıklatın; sihirbaza dönmek ve başka bir dosya adı belirtmek için **Hayır'ı** tıklatın.

- **.cpp dosyası**

   Yeni nesnesınıfının uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad **Kısa ad**da sağladığınız adı temel alır. Dosya adını seçtiğiniz konuma kaydetmek için elips düğmesini tıklatın. Sihirbazda **Bitir'i** tıklatın kadar dosya seçili konuma kaydedilmez.

   Sihirbaz bir dosyanın üzerine yazmıyor. Varolan bir dosyanın adını seçerseniz, **Bitiş'i**tıklattığınızda, sihirbaz, sınıf uygulamasının dosyanın içeriğine eklenip eklenmeyeceğini belirtmenizi ister. Dosyayı eklemek için **Evet'i** tıklatın; sihirbaza dönmek ve başka bir dosya adı belirtmek için **Hayır'ı** tıklatın.

- **Yazarından**

   Nesnenin öznitelikleri kullanıp kullanmadığını gösterir. Atfedilen bir ATL projesine bir nesne ekliyorsanız, bu seçenek seçilir ve değiştirilemez. Diğer bir tarihte, yalnızca öznitelik desteğiyle oluşturulan bir projeye atfedilen nesneleri ekleyebilirsiniz.

   Yalnızca öznitelikleri kullanan bir ATL projesine atfedilen bir nesne ekleyebilirsiniz. Öznitelik desteği olmayan bir ATL projesi için bu seçeneği seçerseniz, sihirbaz projeye öznitelik desteği eklemek isteyip istemediğinizbelirtilir.

   Varsayılan olarak, bu seçeneği ayarladıktan sonra eklediğiniz nesneler atfedilen olarak belirlenir (onay kutusu seçilir). Öznitelikleri kullanmayan bir nesne eklemek için bu kutuyu temizleyebilirsiniz.

   Daha fazla bilgi için [Uygulama Ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [Özniteliklerin Temel Mekaniği](../../windows/basic-mechanics-of-attributes.md) bölümüne bakın.

### <a name="com"></a>COM

Nesne için COM işlevi hakkında bilgi sağlar.

- **Coclass**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfının adını ayarlar.

   > [!NOTE]
   > Projenizi öznitelikleri kullanarak oluşturursanız veya bu sihirbaz sayfasında denetimin öznitelikleri kullandığını belirtirseniz, ATL **ortak sınıf** özniteliği içermediği için bu seçeneği değiştiremezsiniz.

- **Arabirim**

   Nesne için arabirimin adını ayarlar. Varsayılan olarak bir arabirim adı "I" ile hazırlanır.

- **Tür**

   Kayıt defterinde görünecek nesne açıklamasını ayarlar

- **Progıd**

   Nesnenin CLSID yerine kapsayıcıların kullanabileceği adı ayarlar. Bu alan otomatik olarak doldurulmadı. Bu alanı el ile doldurmazsanız, denetim diğer araçlar için kullanılamayabilir. Örneğin, EtkinX `ProgID` Denetimi Ekle iletişim kutusunda **insert activex denetimkutusunda** kullanılabilir. İletişim kutusu hakkında daha fazla bilgi için [ActiveX Denetimi İletişim Kutusu Ekle'ye](../../windows/insert-activex-control-dialog-box.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Kontrolü](../../atl/reference/adding-an-atl-control.md)<br/>
[Bileşik Denetime İşlevsellik Ekleme](../../atl/adding-functionality-to-the-composite-control.md)<br/>
[ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)
