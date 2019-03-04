---
title: ATL Basit Nesne Sihirbazı Seçenekleri
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.simple.options
helpviewer_keywords:
- ATL Simple Object Wizard, options
ms.assetid: 125fe179-942d-4181-8b82-33e92e1fd779
ms.openlocfilehash: 327c78b00cbe69fcce4f055b0ae63c4dc2e5a7d9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273404"
---
# <a name="options-atl-simple-object-wizard"></a>ATL Basit Nesne Sihirbazı Seçenekleri

ATL Basit Nesne Sihirbazı bu sayfa, daha fazla verimlilik ve nesne için hata destek tasarlamak için kullanın.

ATL projeleri ve ATL COM sınıfları hakkında daha fazla bilgi için bkz. [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md).

- **İş parçacığı modeli**

   İş parçacıkları yönetmek için bir yöntemi gösterir. Varsayılan olarak projenin kullandığı **apartman** iş parçacığı oluşturma.

   Bkz: [projenin iş parçacıklı Model belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) daha fazla bilgi için.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Tek**|Nesne her zaman birincil COM iş parçacığında çalışır belirtir. Bkz: [Single-Threaded apartmanlar](/windows/desktop/com/single-threaded-apartments) ve [Inprocserver32](/windows/desktop/com/inprocserver32) daha fazla bilgi için.|
   |**Grup**|Nesne grubu iş parçacığı kullandığını belirtir. Eşdeğer tek iş parçacığı grubu. Her nesne bir boş iş parçacıklı bileşen nesne ömrü için kendi iş parçacığı için bir grup atanır; Ancak, birden çok iş parçacığı, birden çok nesne için kullanılabilir. Her grup, belirli bir iş parçacığına bağlıdır ve bir Windows ileti pompası (varsayılan) sahiptir.<br /><br /> Bkz: [Single-Threaded apartmanlar](/windows/desktop/com/single-threaded-apartments) daha fazla bilgi için.|
   |**Her ikisi de**|Nesne grubu ya da boş iş parçacığı, oluşturulduktan bir iş parçacığının hangi tür gelen bağlı olarak kullanabileceğiniz belirtir.|
   |**Ücretsiz**|Nesneyi serbest iş parçacığı oluşturma kullandığını belirtir. Ücretsiz iş parçacığı için bir çoklu iş parçacığı apartman modeli eşdeğerdir. Bkz: [birden çok iş parçacıklı apartmanlar](/windows/desktop/com/multithreaded-apartments) daha fazla bilgi için.|
   |**Nötr**|Nesne birden çok iş parçacıklı apartmanlar yönelik yönergeleri takip eder, ancak iş parçacığı herhangi bir türden yürütebilirsiniz belirtir.|

- **Toplama**

   Nesne kullanıp kullanmadığını gösteren [toplama](/windows/desktop/com/aggregation). Toplama nesnesine hangi istemcilere göstermek için arabirimleri seçer ve toplama nesnesi bunlar yönetimlerini uygularsanız gibi arabirimler gösterilir. Toplama nesnesi, istemciler yalnızca toplama nesnesi ile iletişim kurar.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Evet**|Nesnenin toplanabilir belirtir. Varsayılan.|
   |**Yok**|Nesne değil toplanır belirtir.|
   |**Yalnızca**|Nesne toplanması gereken belirtir.|

- **Arabirimi**

   Nesne destekleyen arabirim türünü belirtir. Varsayılan olarak, nesne çift arabirim destekler.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Çift**|Nesne çift arabirim desteklediğini belirtir (özel arabirim işlevleri ek geç bağlama, vtable sahiptir `IDispatch` yöntemleri). Her iki COM istemcilerinin sağlar ve [Otomasyon denetleyicileri](../../mfc/automation-clients.md) nesneye erişim. Varsayılan.|
   |**Özel**|Nesne (özel arabirim işlevleri kendi vtable sahiptir) özel bir arabirim desteklediğini belirtir. Özel arabirim özellikle işlem sınırları arasında çift arabirim, daha hızlı olabilir.<br /><br /> - **Otomasyon uyumlu** özel arabirim desteğine sahip bir nesneye erişmek için denetleyicileri Otomasyon sağlar.|

- **Destek**

   Nesne için ek destek gösterir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**ISupportErrorInfo**|Desteği oluşturur [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) istemciye hata bilgilerini nesnenin dönebilmeniz arabirim.|
   |**Bağlantı noktaları**|Nesneniz için bağlantı noktaları, nesnenin sınıfı türetilen yaparak sağlar [Iconnectionpointcontainerımpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|
   |**Ücretsiz iş parçacıklı Sıralayıcı**|Aynı işlemdeki iş parçacıkları arasında verimli bir şekilde arabirim işaretçilerini sıralama bir ücretsiz iş parçacıklı bir Sıralayıcı nesnesini oluşturur. Nesnesi için kullanılabilir **hem** iş parçacığı modeli olarak.|
   |**IObjectWithSite** (IE nesne desteği)|Implements [Iobjectwithsiteımpl](../../atl/reference/iobjectwithsiteimpl-class.md), bir kapsayıcıda bir nesne ve alt site arasındaki iletişimi desteklemek için basit bir yol sağlar.|

## <a name="see-also"></a>Ayrıca bkz.

[ATL Basit Nesne Sihirbazı](../../atl/reference/atl-simple-object-wizard.md)<br/>
[ATL Basit Nesne](../../atl/reference/adding-an-atl-simple-object.md)<br/>
[İşlem sunucusu iş parçacığı oluşturma sorunları](/windows/desktop/com/in-process-server-threading-issues)
