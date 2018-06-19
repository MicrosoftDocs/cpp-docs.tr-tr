---
title: Seçenekler, ATL Basit Nesne Sihirbazı | Microsoft Docs
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
ms.openlocfilehash: ffc38f5359b68b90f91a2643e1fbaa743a94e559
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364147"
---
# <a name="options-atl-simple-object-wizard"></a>ATL Basit Nesne Sihirbazı Seçenekleri
Daha fazla verimlilik ve nesne için hata desteği için tasarlamak için ATL Basit Nesne Sihirbazı'nın bu sayfayı kullanın.  
  
 ATL projeleri ve ATL COM sınıfları hakkında daha fazla bilgi için bkz: [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md).  
  
 **İş parçacığı modeli**  
 İş parçacığı yönetme yöntemini gösterir. Varsayılan olarak, projeyi kullanır **grup** iş parçacığı oluşturma.  
  
 Bkz: [projenin iş parçacıklı Model belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) daha fazla bilgi için.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|`Single`|Nesne her zaman birincil COM parçacığında çalıştıracağını belirtir. Bkz: [Single-Threaded grupların](http://msdn.microsoft.com/library/windows/desktop/ms680112) ve [Inprocserver32](http://msdn.microsoft.com/library/windows/desktop/ms682390) daha fazla bilgi için.|  
|**Grup**|Nesne Apartman iş parçacığı oluşturma kullandığını belirtir. Eşdeğer tek iş parçacığı grubu. Her bir boş iş parçacıklı bileşen nesnesinin ömrü boyunca nesnesi, iş parçacığı için bir grup atanır; Ancak, birden çok iş parçacığı birden fazla nesne kullanılabilir. Her grup için belirli bir iş parçacığı bağlıdır ve bir Windows ileti Pompalama (varsayılan) sahiptir.<br /><br /> Bkz: [Single-Threaded grupların](http://msdn.microsoft.com/library/windows/desktop/ms680112) daha fazla bilgi için.|  
|**Her ikisi**|Nesne grubu ya da boş iş parçacığı oluşturma, oluşturulduktan bir iş parçacığı hangi tür gelen bağlı olarak kullanabileceğiniz belirtir.|  
|**Boş**|Nesne serbest iş parçacığı oluşturmayı kullandığını belirtir. Boş iş parçacığı oluşturma için çoklu iş parçacığı apartman modeli eşdeğerdir. Bkz: [birden çok iş parçacıklı grupların](http://msdn.microsoft.com/library/windows/desktop/ms693421) daha fazla bilgi için.|  
|**Nötr**|Nesne birden çok iş parçacıklı grupların yönelik yönergeleri takip eder, ancak iş parçacığı her türlü yürütebilir belirtir.|  
  
 **Toplama**  
 Nesne kullanıp kullanmadığını belirten [toplama](http://msdn.microsoft.com/library/windows/desktop/ms686558). Hangi istemcilere göstermek için arabirimleri toplama bir nesne seçer ve onları toplama bir nesne uygulanırsa, gibi arabirimler gösterilir. Birleşik nesnesinin istemciler yalnızca toplama bir nesne ile iletişim kurar.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|Evet|Nesne kümelenebilir belirtir. Varsayılan.|  
|Hayır|Nesne olmayan toplanır belirtir.|  
|Yalnızca|Nesne toplanması gereken belirtir.|  
  
 **Arabirimi**  
 Nesne destekleyen arabirimi türünü belirtir. Varsayılan olarak, bir çift arabirim nesnesi destekler.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Çift**|Nesne çift arabirim desteği belirtir (kendi vtable özel arabirimi işlevleri artı geç bağlama sahip `IDispatch` yöntemleri). Her iki COM istemcileri sağlar ve [Otomasyon denetleyicileri](../../mfc/automation-clients.md) nesneye erişim. Varsayılan.|  
|**Özel**|Nesne (kendi vtable özel arabirimi işlevleri vardır) özel bir arabirim desteklediğini belirtir. Özel bir arabirim özellikle işlem sınırları boyunca bir çift arabirim hızlı olabilir.<br /><br /> -   **Otomasyon uyumlu** özel arabirim desteği olan bir nesneye erişim sağlayan Otomasyon denetleyicileri.|  
  
 **Destek**  
 Nesne için ek destek gösterir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**ISupportErrorInfo**|Desteği oluşturur [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) nesne istemciye hata bilgilerini dönebilmeniz arabirim.|  
|**Bağlantı noktaları**|Bağlantı noktaları, nesne için nesnenin sınıf türetin yaparak etkinleştirir [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|  
|**Ücretsiz iş parçacıklı Sıralayıcı**|Aynı işlemde iş parçacıkları arasında verimli bir şekilde arabirimi işaretçilerini sıralama için ücretsiz iş parçacıklı Sıralayıcı nesnesi oluşturur. Nesne belirtmek için kullanılabilir **her ikisi de** iş parçacığı modeli olarak.|  
|**IObjectWithSite (IE nesne desteği)**|Implements [IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md), bir nesne ve alt site arasındaki iletişimin bir kapsayıcıda desteklemek için basit bir yol sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Basit Nesne Sihirbazı](../../atl/reference/atl-simple-object-wizard.md)   
 [ATL Basit Nesne](../../atl/reference/adding-an-atl-simple-object.md)   
 [İşlemdeki sunucu iş parçacığı oluşturma sorunları](http://msdn.microsoft.com/library/windows/desktop/ms687205)

