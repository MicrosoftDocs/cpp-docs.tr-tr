---
title: ATL Basit Nesne Sihirbazı, seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.simple.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Simple Object Wizard, options
ms.assetid: 125fe179-942d-4181-8b82-33e92e1fd779
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1cef503bf9862f1259e25aff76a013d60776077
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883732"
---
# <a name="options-atl-simple-object-wizard"></a>ATL Basit Nesne Sihirbazı Seçenekleri
ATL Basit Nesne Sihirbazı bu sayfa, daha fazla verimlilik ve nesne için hata destek tasarlamak için kullanın.  
  
 ATL projeleri ve ATL COM sınıfları hakkında daha fazla bilgi için bkz. [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md).  
  
 **İş parçacığı modeli**  
 İş parçacıkları yönetmek için bir yöntemi gösterir. Varsayılan olarak projenin kullandığı **apartman** iş parçacığı oluşturma.  
  
 Bkz: [projenin iş parçacıklı Model belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) daha fazla bilgi için.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Tek**|Nesne her zaman birincil COM iş parçacığında çalışır belirtir. Bkz: [Single-Threaded apartmanlar](http://msdn.microsoft.com/library/windows/desktop/ms680112) ve [Inprocserver32](http://msdn.microsoft.com/library/windows/desktop/ms682390) daha fazla bilgi için.|  
|**Grup**|Nesne grubu iş parçacığı kullandığını belirtir. Eşdeğer tek iş parçacığı grubu. Her nesne bir boş iş parçacıklı bileşen nesne ömrü için kendi iş parçacığı için bir grup atanır; Ancak, birden çok iş parçacığı, birden çok nesne için kullanılabilir. Her grup, belirli bir iş parçacığına bağlıdır ve bir Windows ileti pompası (varsayılan) sahiptir.<br /><br /> Bkz: [Single-Threaded apartmanlar](http://msdn.microsoft.com/library/windows/desktop/ms680112) daha fazla bilgi için.|  
|**Her ikisi de**|Nesne grubu ya da boş iş parçacığı, oluşturulduktan bir iş parçacığının hangi tür gelen bağlı olarak kullanabileceğiniz belirtir.|  
|**Ücretsiz**|Nesneyi serbest iş parçacığı oluşturma kullandığını belirtir. Ücretsiz iş parçacığı için bir çoklu iş parçacığı apartman modeli eşdeğerdir. Bkz: [birden çok iş parçacıklı apartmanlar](http://msdn.microsoft.com/library/windows/desktop/ms693421) daha fazla bilgi için.|  
|**Nötr**|Nesne birden çok iş parçacıklı apartmanlar yönelik yönergeleri takip eder, ancak iş parçacığı herhangi bir türden yürütebilirsiniz belirtir.|  
  
 **Toplama**  
 Nesne kullanıp kullanmadığını gösteren [toplama](http://msdn.microsoft.com/library/windows/desktop/ms686558). Toplama nesnesine hangi istemcilere göstermek için arabirimleri seçer ve toplama nesnesi bunlar yönetimlerini uygularsanız gibi arabirimler gösterilir. Toplama nesnesi, istemciler yalnızca toplama nesnesi ile iletişim kurar.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|Evet|Nesnenin toplanabilir belirtir. Varsayılan.|  
|Hayır|Nesne değil toplanır belirtir.|  
|Yalnızca|Nesne toplanması gereken belirtir.|  
  
 **Arabirimi**  
 Nesne destekleyen arabirim türünü belirtir. Varsayılan olarak, nesne çift arabirim destekler.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Çift**|Nesne çift arabirim desteklediğini belirtir (özel arabirim işlevleri ek geç bağlama, vtable sahiptir `IDispatch` yöntemleri). Her iki COM istemcilerinin sağlar ve [Otomasyon denetleyicileri](../../mfc/automation-clients.md) nesneye erişim. Varsayılan.|  
|**Özel**|Nesne (özel arabirim işlevleri kendi vtable sahiptir) özel bir arabirim desteklediğini belirtir. Özel arabirim özellikle işlem sınırları arasında çift arabirim, daha hızlı olabilir.<br /><br /> -   **Otomasyon uyumlu** özel arabirim desteğine sahip bir nesneye erişmek için denetleyicileri Otomasyon sağlar.|  
  
 **Destek**  
 Nesne için ek destek gösterir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|`ISupportErrorInfo`|Desteği oluşturur [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) istemciye hata bilgilerini nesnenin dönebilmeniz arabirim.|  
|**Bağlantı noktaları**|Nesneniz için bağlantı noktaları, nesnenin sınıfı türetilen yaparak sağlar [Iconnectionpointcontainerımpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|  
|**Ücretsiz iş parçacıklı Sıralayıcı**|Aynı işlemdeki iş parçacıkları arasında verimli bir şekilde arabirim işaretçilerini sıralama bir ücretsiz iş parçacıklı bir Sıralayıcı nesnesini oluşturur. Nesnesi için kullanılabilir **hem** iş parçacığı modeli olarak.|  
|`IObjectWithSite` **(IE nesne desteği)**|Implements [Iobjectwithsiteımpl](../../atl/reference/iobjectwithsiteimpl-class.md), bir kapsayıcıda bir nesne ve alt site arasındaki iletişimi desteklemek için basit bir yol sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Basit Nesne Sihirbazı](../../atl/reference/atl-simple-object-wizard.md)   
 [ATL Basit Nesne](../../atl/reference/adding-an-atl-simple-object.md)   
 [İşlem sunucusu iş parçacığı oluşturma sorunları](http://msdn.microsoft.com/library/windows/desktop/ms687205)

