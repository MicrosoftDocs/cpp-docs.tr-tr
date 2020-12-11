---
description: 'Daha fazla bilgi edinin: seçenekler, ATL basit nesne Sihirbazı'
title: Seçenekler, ATL basit nesne Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.simple.options
helpviewer_keywords:
- ATL Simple Object Wizard, options
ms.assetid: 125fe179-942d-4181-8b82-33e92e1fd779
ms.openlocfilehash: 37353358aecddc084e5f29c6c6ee75b393fe8ded
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157847"
---
# <a name="options-atl-simple-object-wizard"></a>Seçenekler, ATL basit nesne Sihirbazı

Nesne için daha fazla verimlilik ve hata desteğini tasarlamak üzere ATL basit nesne Sihirbazı 'nın bu sayfasını kullanın.

ATL projeleri ve ATL COM sınıfları hakkında daha fazla bilgi için bkz. [atl com Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md).

- **İş parçacığı modeli**

   İş parçacıklarını yönetme yöntemini gösterir. Varsayılan olarak, proje **apartman** iş parçacığı kullanır.

   Daha fazla bilgi için bkz. [projenin Iş parçacığı modelini belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) .

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Tek**|Nesnenin her zaman birincil COM iş parçacığında çalışacağını belirtir. Daha fazla bilgi için bkz. [tek Iş parçacıklı Apartments](/windows/win32/com/single-threaded-apartments) ve [ınprocserver32](/windows/win32/com/inprocserver32) .|
   |**Yapı**|Nesnenin apartman iş parçacığı kullandığını belirtir. Tek iş parçacığı grubu ile eşdeğerdir. Bir apartman iş parçacıklı bileşenin her nesnesine, nesne ömrü boyunca iş parçacığı için bir grup atanır; Ancak birden çok nesne için birden çok iş parçacığı kullanılabilir. Her grup belirli bir iş parçacığına bağlanır ve bir Windows ileti göndericisi (varsayılan) vardır.<br /><br /> Daha fazla bilgi için bkz. [tek Iş parçacıklı apartmanlar](/windows/win32/com/single-threaded-apartments) .|
   |**Her ikisi**|Nesnenin, oluşturduğu iş parçacığı türünden bağımsız olarak Apartment veya Free iş parçacığı kullanıp kullanbileceğini belirtir.|
   |**Ücretsiz**|Nesnenin serbest iş parçacığı kullandığını belirtir. Ücretsiz iş parçacığı, bir çoklu iş parçacığı grubu modeliyle eşdeğerdir. Daha fazla bilgi için bkz. [Çoklu Iş parçacıklı Apartments](/windows/win32/com/multithreaded-apartments) .|
   |**Kültür**|Nesnenin çok iş parçacıklı apartmanlar için yönergeleri takip eder, ancak her türlü iş parçacığı üzerinde yürütebileceğini belirtir.|

- **Toplama**

   Nesnenin [toplamayı](/windows/win32/com/aggregation)kullanıp kullanmadığını belirtir. Toplama nesnesi, istemcilere hangi arabirimlerin sunumasını seçer ve arabirimler toplama nesnesi tarafından uygulandıkları gibi gösterilir. Toplama nesnesinin istemcileri yalnızca toplama nesnesiyle iletişim kurar.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Evet**|Nesnenin toplanabilecek olduğunu belirtir. Varsayılan.|
   |**Hayır**|Nesnenin toplanmadığını belirtir.|
   |**Yalnızca**|Nesnenin toplanması gerektiğini belirtir.|

- **Arabirim**

   Nesnenin desteklediği arabirimin türünü gösterir. Varsayılan olarak, nesnesi bir çift arabirimi destekler.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**İkili**|Nesnenin çift arabirimi desteklediğini belirtir (vtable, özel arabirim işlevlerine ve geç bağlama `IDispatch` yöntemlerine sahiptir). Hem COM istemcilerinin hem de [Otomasyon denetleyicilerinin](../../mfc/automation-clients.md) nesneye erişmesine izin verir. Varsayılan.|
   |**Özel**|Nesnenin özel arabirimi desteklediğini belirtir (vtable 'ın özel arabirim işlevleri vardır). Özel bir arabirim, özellikle işlem sınırları genelinde bir çift arabirimden daha hızlı olabilir.<br /><br /> - **Otomasyon uyumlu** Otomasyon denetleyicilerinin özel arabirim desteğine sahip bir nesneye erişmesine izin verir.|

- **Destek**

   Nesne için ek desteği gösterir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Iupporterrorınfo**|, Nesnenin istemciye hata bilgilerini döndürebilmesi için [ıupporterrorınfo](../../atl/reference/isupporterrorinfoimpl-class.md) arabirimi için destek oluşturur.|
   |**Bağlantı noktaları**|, Nesnenizin sınıfının [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)'den türemesini sağlayarak nesneniz için bağlantı noktalarını mümkün hale getirir.|
   |**Serbest iş parçacıklı Sıralayıcı**|Aynı işlemdeki iş parçacıkları arasında arabirim işaretçilerini etkili bir şekilde sıralamak için serbest iş parçacıklı Sıralayıcı nesnesi oluşturur. **Her Ikisini de** iş parçacığı modeli olarak belirten nesne için kullanılabilir.|
   |**IObjectWithSite** (IE nesne desteği)|Bir kapsayıcı içindeki bir nesne ile sitesi arasındaki iletişimi desteklemeye yönelik basit bir yol sağlayan [IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md)'yi uygular.|

## <a name="see-also"></a>Ayrıca bkz.

[ATL Basit Nesne Sihirbazı](../../atl/reference/atl-simple-object-wizard.md)<br/>
[ATL basit nesnesi](../../atl/reference/adding-an-atl-simple-object.md)<br/>
[Işlem içi sunucu Iş parçacığı sorunları](/windows/win32/com/in-process-server-threading-issues)
