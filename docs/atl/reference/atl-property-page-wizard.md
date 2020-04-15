---
title: ATL Özellik Sayfası Sihirbazı
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.ppg.overview
helpviewer_keywords:
- ATL projects, adding property pages
- ATL Property Page Wizard
ms.assetid: 6113e325-facd-4f68-b491-144d75209922
ms.openlocfilehash: eaf070d5a98a05dbe3102afac8317ffd59298ad2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321672"
---
# <a name="atl-property-page-wizard"></a>ATL Özellik Sayfası Sihirbazı

::: moniker range="vs-2019"

Bu sihirbaz Visual Studio 2019 ve sonraki yıllarda kullanılamaz.

::: moniker-end

::: moniker range="<=vs-2017"

Bu sihirbaz, [bir ATL projesine](../../atl/reference/adding-an-atl-property-page.md) veya ATL destekli bir MFC projesine özellik sayfası ekler. ATL özellik sayfası, bir veya daha fazla COM nesnesinin özelliklerini ayarlamak (veya yöntemleri çağırmak) için bir kullanıcı arabirimi sağlar.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008 ile başlayarak, bu sihirbaz tarafından üretilen kayıt komut dosyası **HKEY_LOCAL_MACHINE**yerine **HKEY_CURRENT_USER** altında COM bileşenleri kaydedecektir. Bu davranışı değiştirmek için, ATL Sihirbazı'nın tüm kullanıcılar için **Kayıt bileşenini** ayarlayın.

## <a name="names"></a>Adlar

Projenize eklenecek nesne, arabirim ve sınıfların adlarını belirtin. Kısa **ad**dışında, diğer tüm kutular bağımsız olarak düzenlenebilir. **Kısa ad**metnini değiştirirseniz, değişiklik bu sayfadaki diğer tüm kutuların adlarında yansıtılır. COM bölümündeki **Coclass** adını değiştirirseniz, değişiklik **Tür** ve **ProgID** kutularına yansıtılır. Bu adlandırma davranışı, özellik sayfanızı geliştirirken tüm adları sizin için kolayca tanımlanabilir hale getirmek için tasarlanmıştır.

> [!NOTE]
> **Coclass** yalnızca atfedilmeyen projelerde değiştirilebilir. Projeniz atfedilen, **Coclass'ı**kaldıramazsınız.

### <a name="c"></a>C++

Nesneyi uygulamak için oluşturulan C++ sınıfı için bilgi sağlar.

|||
|-|-|
|Sözleşme Dönemi|Tanım|
|**Kısa ad**|Nesnenin kısaltılmış adını ayarlar. Sağladığınız ad, sınıf ve **Coclass** adlarını, dosyayı (**.cpp** ve **.h**) adlarını, **Tür** adını ve **ProgID'yi,** bu alanları tek tek değiştirmediğiniz sürece belirler.|
|**.h dosyası**|Yeni nesnenin sınıfı için üstbilgi dosyasının adını ayarlar. Varsayılan olarak, bu ad **Kısa ad**da sağladığınız adı temel alır. Dosya adını seçtiğiniz konuma kaydetmek veya sınıf bildirimini varolan bir dosyaya eklemek için elips düğmesini tıklatın. Varolan bir dosyayı seçerseniz, sihirbaz, sihirbazda **Bitir'i** tıklatana kadar dosyayı seçili konuma kaydetmez.<br /><br /> Sihirbaz bir dosyanın üzerine yazmıyor. Varolan bir dosyanın adını seçerseniz, **Bitiş'i**tıklattığınızda, sihirbaz sınıf bildiriminin dosyanın içeriğine eklenip eklenmeyeceğini belirtmenizi ister. Dosyayı eklemek için **Evet'i** tıklatın; sihirbaza dönmek ve başka bir dosya adı belirtmek için **Hayır'ı** tıklatın.|
|**Sınıfı**|Nesneyi uygulayan sınıfın adını ayarlar. Bu ad, bir sınıf adı için tipik önek olan 'C' öncesinde **Kısa adla**sağladığınız ada dayanır.|
|**.cpp dosyası**|Yeni nesnesınıfının uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad **Kısa ad**da sağladığınız adı temel alır. Dosya adını seçtiğiniz konuma kaydetmek için elips düğmesini tıklatın. Sihirbazda **Bitir'i** tıklatın kadar dosya seçili konuma kaydedilmez.<br /><br /> Sihirbaz bir dosyanın üzerine yazmıyor. Varolan bir dosyanın adını seçerseniz, **Bitiş'i**tıklattığınızda, sihirbaz, sınıf uygulamasının dosyanın içeriğine eklenip eklenmeyeceğini belirtmenizi ister. Dosyayı eklemek için **Evet'i** tıklatın; sihirbaza dönmek ve başka bir dosya adı belirtmek için **Hayır'ı** tıklatın.|
|**Yazarından**|Nesnenin öznitelikleri kullanıp kullanmadığını gösterir. Atfedilen bir ATL projesine bir nesne ekliyorsanız, bu seçenek seçilir ve değiştirilemez, diğer bir süre önce öznitelik desteğiyle oluşturulan projeye atfedilen nesneleri ekleyebilirsiniz.<br /><br /> Yalnızca öznitelikleri kullanan bir ATL projesine atfedilen bir nesne ekleyebilirsiniz. Öznitelik desteği olmayan bir ATL projesi için bu seçeneği seçerseniz, sihirbaz projeye öznitelik desteği eklemek isteyip istemediğinizbelirtilir.<br /><br /> Varsayılan olarak, bu seçeneği ayarladıktan sonra eklediğiniz nesneler atfedilen olarak belirlenir (onay kutusu seçilir). Öznitelikleri kullanmayan bir nesne eklemek için bu kutuyu temizleyebilirsiniz.<br /><br /> Daha fazla bilgi için [Uygulama Ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [Özniteliklerin Temel Mekaniği](../../windows/basic-mechanics-of-attributes.md) bölümüne bakın.|

### <a name="com"></a>COM

Nesne için COM işlevi hakkında bilgi sağlar.

- **Coclass**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfının adını ayarlar.

   > [!NOTE]
   > Projenizi öznitelikleri kullanarak oluşturursanız veya bu sihirbaz sayfasında özellik sayfasının öznitelikleri kullandığını belirtirseniz, ATL `coclass` özniteliği içermediği için bu seçeneği değiştiremezsiniz.

- **Tür**

   Kayıt defterinde görünecek nesne açıklamasını ayarlar

- **Progıd**

   Nesnenin CLSID yerine kapsayıcıların kullanabileceği adı ayarlar.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Seçenekler, ATL Özellik Sayfa Sihirbazı](../../atl/reference/options-atl-property-page-wizard.md)<br/>
[Dizeleri, ATL Özellik Sayfa Sihirbazı](../../atl/reference/strings-atl-property-page-wizard.md)<br/>
[Örnek: Özellik Sayfası Uygulama](../../atl/example-implementing-a-property-page.md)
