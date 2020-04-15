---
title: ATL Basit Nesne Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.simple.overview
helpviewer_keywords:
- ATL projects, adding objects
- ATL Simple Object Wizard
ms.assetid: f7f85741-9aad-4543-a917-a29b996364da
ms.openlocfilehash: bd4c9eede16ed086020dd8f12d90876e50a0a341
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319211"
---
# <a name="atl-simple-object-wizard"></a>ATL Basit Nesne Sihirbazı

Bu sihirbaz projeye en az COM nesnesi ekler. Nesneniz ve COM işlevselliği için C++ sınıfını ve dosyalarını tanımlayan adları belirtmek için sihirbazın bu sayfasını kullanın.

Nesnenin iş parçacığı modelini, toplama desteğini ve çift arabirimleri ve Otomasyonu destekleyip desteklemediğini belirtmek için bu sihirbazın [Seçenekler](../../atl/reference/options-atl-simple-object-wizard.md) sayfasını kullanın. Ayrıca hata bilgi arabirimi, bağlantı noktaları, Internet Explorer desteği ve serbest iş parçacığı mareşalleme desteği ni de belirtebilirsiniz.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008 ile başlayarak, bu sihirbaz tarafından üretilen kayıt komut dosyası **HKEY_LOCAL_MACHINE**yerine **HKEY_CURRENT_USER** altında COM bileşenleri kaydedecektir. Bu davranışı değiştirmek için, ATL Sihirbazı'nın tüm kullanıcılar için **Kayıt bileşenini** ayarlayın.

## <a name="names"></a>Adlar

Projenize eklenecek nesne, arabirim ve sınıfların adlarını belirtin. Kısa **ad**dışında, diğer tüm kutular diğerlerinden bağımsız olarak düzenlenebilir. **Kısa ad**metnini değiştirirseniz, değişiklik bu sayfadaki diğer tüm kutuların adlarında yansıtılır. COM bölümündeki **Coclass** adını değiştirirseniz, değişiklik **Tür** ve **ProgID** kutularına yansıtılır, ancak **Arabirim** adı değişmez. Bu adlandırma davranışı, denetiminizi geliştirirken tüm adları sizin için kolayca tanımlanabilir hale getirmek için tasarlanmıştır.

> [!NOTE]
> **Coclass** yalnızca atfedilmeyen projelerde değiştirilebilir. Projeniz atfedilen, **Coclass'ı**kaldıramazsınız.

## <a name="c"></a>C++

Nesne için oluşturulan C++ sınıfı için bilgi sağlar.

- **Kısa ad**

   Nesnenin kısaltılmış adını ayarlar. Sağladığınız ad, bu `Class` alanları `Coclass` tek tek değiştirmediğiniz sürece, **.cpp dosyasını** ve **.h dosya** adlarını, **Arabirim** adını, **Tür** adlarını ve **ProgID'yi**belirler.

- **.h dosyası**

   Yeni nesnenin sınıfı için üstbilgi dosyasının adını ayarlar. Varsayılan olarak, bu ad **Kısa ad**da sağladığınız adı temel alır. Dosya adını seçtiğiniz konuma kaydetmek veya sınıf bildirimini varolan bir dosyaya eklemek için elips düğmesini tıklatın. Varolan bir dosyayı seçerseniz, sihirbaz, sihirbazda **Bitir'i** tıklatana kadar dosyayı seçili konuma kaydetmez.

   Sihirbaz bir dosyanın üzerine yazmıyor. Varolan bir dosyanın adını seçerseniz, **Bitiş'i**tıklattığınızda, sihirbaz sınıf bildiriminin dosyanın içeriğine eklenip eklenmeyeceğini belirtmenizi ister. Dosyayı eklemek için **Evet'i** tıklatın; sihirbaza dönmek ve başka bir dosya adı belirtmek için **Hayır'ı** tıklatın.

- **Sınıfı**

   Oluşturulacak sınıfın adını ayarlar. Bu ad, bir sınıf adı için tipik önek olan 'C' öncesinde **Kısa adla**sağladığınız ada dayanır.

- **.cpp dosyası**

   Yeni nesnesınıfının uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad **Kısa ad**da sağladığınız adı temel alır. Dosya adını seçtiğiniz konuma kaydetmek için elips düğmesini tıklatın. Sihirbazda **Bitir'i** tıklatın kadar dosya seçili konuma kaydedilmez.

   Sihirbaz bir dosyanın üzerine yazmıyor. Varolan bir dosyanın adını seçerseniz, **Bitiş'i**tıklattığınızda, sihirbaz, sınıf uygulamasının dosyanın içeriğine eklenip eklenmeyeceğini belirtmenizi ister. Dosyayı eklemek için **Evet'i** tıklatın; sihirbaza dönmek ve başka bir dosya adı belirtmek için **Hayır'ı** tıklatın.

- **Yazarından**

   Nesnenin öznitelikleri kullanıp kullanmadığını gösterir. Atfedilen bir ATL projesine bir nesne ekliyorsanız, bu seçenek seçilir ve değiştirilemez. Diğer bir tarihte, yalnızca öznitelik desteğiyle oluşturulan bir projeye atfedilen nesneleri ekleyebilirsiniz.

   Yalnızca öznitelikleri kullanan bir ATL projesine atfedilen bir nesne ekleyebilirsiniz. Öznitelik desteği olmayan bir ATL projesi için bu seçeneği seçerseniz, sihirbaz projeye öznitelik desteği eklemek isteyip istemediğinizbelirtilir.

   Varsayılan olarak, bu seçeneği ayarladıktan sonra eklediğiniz nesneler atfedilen olarak belirlenir (onay kutusu seçilir). Öznitelikleri kullanmayan bir nesne eklemek için bu kutuyu temizleyebilirsiniz.

   Daha fazla bilgi için [Uygulama Ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [Özniteliklerin Temel Mekaniği](../../windows/basic-mechanics-of-attributes.md) bölümüne bakın.

## <a name="com"></a>COM

Nesne için COM işlevi hakkında bilgi sağlar.

- **Coclass**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfının adını ayarlar.

   > [!NOTE]
   > Projenizi öznitelikleri kullanarak oluşturursanız veya bu sihirbaz sayfasında nesnenin öznitelikleri kullandığını belirtirseniz, ATL `coclass` özniteliği içermediği için bu seçeneği değiştiremezsiniz.

- **Tür**

   Kayıt defterinde görünecek nesne açıklamasını ayarlar

- **Arabirim**

   Nesneniz için oluşturduğunuz arabirimi ayarlar. Bu arabirim, özel yöntemlerinizi içerir.

- **Progıd**

   Nesnenin CLSID yerine kapsayıcıların kullanabileceği adı ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Basit Nesne](../../atl/reference/adding-an-atl-simple-object.md)
