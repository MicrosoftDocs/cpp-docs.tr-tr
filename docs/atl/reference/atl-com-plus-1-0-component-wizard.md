---
title: ATL COM+ 1.0 Bileşeni Sihirbazı
ms.date: 05/08/2019
helpviewer_keywords:
- ATL projects, adding components
ms.assetid: 11670681-8671-4122-96a4-2e52f8dadce0
ms.openlocfilehash: d5c0c0c8edb6b698d3d8f50736121d987af98492
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321686"
---
# <a name="atl-com-10-component-wizard"></a>ATL COM+ 1.0 Bileşeni Sihirbazı

::: moniker range="vs-2019"

Bu sihirbaz Visual Studio 2019 ve sonraki yıllarda kullanılamaz.

::: moniker-end

::: moniker range="<=vs-2017"

Projenize, işlemler de dahil olmak üzere COM+ 1.0 hizmetlerini destekleyen bir nesne eklemek için bu sihirbazı kullanın.

Nesnenin çift arabirimleri ve Otomasyonu destekleyip desteklemediğini belirtebilirsiniz. Ayrıca hata bilgi arabirimi, gelişmiş nesne denetimi, işlemler ve asynchronous ileti sıraya destek belirtebilirsiniz.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008 ile başlayarak, bu sihirbaz tarafından üretilen kayıt komut dosyası **HKEY_LOCAL_MACHINE**yerine **HKEY_CURRENT_USER** altında COM bileşenleri kaydedecektir. Bu davranışı değiştirmek için, ATL Sihirbazı'nın tüm kullanıcılar için **Kayıt bileşenini** ayarlayın.

## <a name="names"></a>Adlar

Projenize eklenecek nesne, arabirim ve sınıfların adlarını belirtin. **Kısa ad**dışında, diğer tüm kutular diğerlerinden bağımsız olarak düzenlenebilir. **Kısa ad**metnini değiştirirseniz, değişiklik bu sayfadaki diğer tüm kutuların adlarında yansıtılır. COM bölümündeki **Coclass** adını değiştirirseniz, değişiklik **Tür** ve **ProgID** kutularına yansıtılır, ancak **Arabirim** adı değişmez. Bu adlandırma davranışı, denetiminizi geliştirirken tüm adları sizin için kolayca tanımlanabilir hale getirmek için tasarlanmıştır.

- **Kısa ad**

   Nesnenin kısaltılmış adını ayarlar. Sağladığınız ad, bu `Class` alanları `Coclass` tek tek değiştirmediğiniz sürece, **.cpp dosyasını** ve **.h dosya** adlarını, **Arabirim** adını, **Tür** adlarını ve **ProgID'yi**belirler.

- **.h dosyası**

   Yeni nesnenin sınıfı için üstbilgi dosyasının adını ayarlar. Varsayılan olarak, bu ad **Kısa ad**da sağladığınız adı temel alır. Dosya adını seçtiğiniz konuma kaydetmek veya sınıf bildirimini varolan bir dosyaya eklemek için elips düğmesini tıklatın. Varolan bir dosyayı seçerseniz, sihirbaz, sihirbazda **Bitir'i** tıklatana kadar dosyayı seçili konuma kaydetmez.

   Sihirbaz bir dosyanın üzerine yazmıyor. Varolan bir dosyanın adını seçerseniz, **Bitiş'i**tıklattığınızda, sihirbaz sınıf bildiriminin dosyanın içeriğine eklenip eklenmeyeceğini belirtmenizi ister. Dosyayı eklemek için **Evet'i** tıklatın; sihirbaza dönmek ve başka bir dosya adı belirtmek için **Hayır'ı** tıklatın.

- **Sınıfı**

   Oluşturulacak sınıfın adını ayarlar. Bu ad, bir sınıf adı için tipik önek olan 'C' öncesinde **kısa adla**sağladığınız ada dayanır.

- **.cpp dosyası**

   Yeni nesnesınıfının uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad **Kısa ad**da sağladığınız adı temel alır. Dosya adını seçtiğiniz konuma kaydetmek için elips düğmesini tıklatın. Sihirbazda **Bitir'i** tıklatın kadar dosya seçili konuma kaydedilmez.

   Sihirbaz bir dosyanın üzerine yazmıyor. Varolan bir dosyanın adını seçerseniz, **Bitiş'i**tıklattığınızda, sihirbaz, sınıf uygulamasının dosyanın içeriğine eklenip eklenmeyeceğini belirtmenizi ister. Dosyayı eklemek için **Evet'i** tıklatın; sihirbaza dönmek ve başka bir dosya adı belirtmek için **Hayır'ı** tıklatın.

- **Yazarından**

   Nesnenin öznitelikleri kullanıp kullanmadığını gösterir. Atfedilen bir ATL projesine bir nesne ekliyorsanız, bu seçenek seçilir ve değiştirilemez. Diğer bir tarihte, yalnızca öznitelik desteğiyle oluşturulan bir projeye atfedilen nesneleri ekleyebilirsiniz.

   Öznitelik desteği olmayan bir ATL projesi için bu seçeneği seçerseniz, sihirbaz projeye öznitelik desteği eklemek isteyip istemediğinizbelirtilir.

   Bu seçeneği ayarladıkten sonra eklediğiniz tüm nesneler varsayılan olarak atfedilen olarak belirlenir (onay kutusu seçilir). Öznitelikleri kullanmayan bir nesne eklemek için bu kutuyu temizleyebilirsiniz.

   Daha fazla bilgi için [Uygulama Ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [Özniteliklerin Temel Mekaniği](../../windows/basic-mechanics-of-attributes.md) bölümüne bakın.

### <a name="com"></a>COM

Nesne için COM işlevi hakkında bilgi sağlar.

- **Coclass**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfının adını ayarlar.

> [!NOTE]
> Projenizi öznitelikleri kullanarak oluşturursanız veya bu sihirbaz sayfasında COM+ 1.0 bileşeninin öznitelikleri kullandığını belirtirseniz, ATL `coclass` özniteliği içermediği için bu seçeneği değiştiremezsiniz.

- **Tür**

   Kayıt defterinde görünecek nesne açıklamasını ayarlar

- **Arabirim**

   Nesneniz için oluşturduğunuz arabirimi ayarlar. Bu arabirim, özel yöntemlerinizi içerir.

- **Progıd**

   Nesnenin CLSID yerine kapsayıcıların kullanabileceği adı ayarlar.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM+ 1.0 Bileşen](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)
