---
title: Seçenekler, ATL Active Server Page bileşeni Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.options
helpviewer_keywords:
- ATL Active Server Page Component Wizard, options
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
ms.openlocfilehash: 7e9740a67f265484c349a4df644be882dba30c13
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280244"
---
# <a name="options-atl-active-server-page-component-wizard"></a>Seçenekler, ATL Active Server Page bileşeni Sihirbazı

Daha fazla verimlilik ve nesne için hata desteğe yönelik tasarlanacağını ATL Active Server sayfa bileşeni Sihirbazı, bu sayfayı kullanın.

ATL projeleri ve ATL COM sınıfları hakkında daha fazla bilgi için bkz. [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md).

- **İş parçacığı modeli**

   İş parçacıkları yönetmek için bir yöntemi gösterir. Varsayılan olarak projenin kullandığı **apartman** iş parçacığı oluşturma.

   Bkz: [projenin iş parçacıklı Model belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) daha fazla bilgi için.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Tek**|Nesne tek iş parçacıklı model kullandığını belirtir. Tek iş parçacığı modelinde, bir nesneyi her zaman birincil COM iş parçacığında çalışır. Bkz: [Single-Threaded apartmanlar](/windows/desktop/com/single-threaded-apartments) ve [Inprocserver32](/windows/desktop/com/inprocserver32) daha fazla bilgi için.|
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

- **Destek**

   Ek destek seçenekleri:

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**ISupportErrorInfo**|Desteği oluşturur [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) istemciye hata bilgilerini nesnenin dönebilmeniz arabirim.|
   |**Bağlantı noktaları**|Nesneniz için bağlantı noktaları, nesnenin sınıfı türetilen yaparak sağlar [Iconnectionpointcontainerımpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|
   |**Ücretsiz iş parçacıklı Sıralayıcı**|Aynı işlemdeki iş parçacıkları arasında verimli bir şekilde arabirim işaretçilerini sıralama bir ücretsiz iş parçacıklı bir Sıralayıcı nesnesini oluşturur. Belirtme nesne için kullanılabilen **hem** veya **ücretsiz** iş parçacığı modeli olarak.|

## <a name="see-also"></a>Ayrıca bkz.

[ATL Active Server Page Bileşeni Sihirbazı](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[ATL Active Server Page bileşeni](../../atl/reference/adding-an-atl-active-server-page-component.md)
