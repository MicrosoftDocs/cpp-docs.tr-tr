---
title: "Seçenekler, ATL Active Server sayfası Bileşen Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.codewiz.class.atl.asp.options
dev_langs: C++
helpviewer_keywords: ATL Active Server Page Component Wizard, options
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6564b340458ae7e9a8e137d2338ba68b3e729a0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="options-atl-active-server-page-component-wizard"></a>Seçenekler, ATL Active Server sayfası Bileşen Sihirbazı
Daha fazla verimlilik ve nesne için hata desteği için tasarlamak için bu sayfayı ATL etkin sunucu sayfası Bileşen Sihirbazı'nı kullanın.  
  
 ATL projeleri ve ATL COM sınıfları hakkında daha fazla bilgi için bkz: [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md).  
  
 **İş parçacığı modeli**  
 İş parçacığı yönetme yöntemini gösterir. Varsayılan olarak, projeyi kullanır **grup** iş parçacığı oluşturma.  
  
 Bkz: [projenin iş parçacıklı Model belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) daha fazla bilgi için.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|`Single`|Nesne tek iş parçacıklı model kullandığını belirtir. Çoklu iş parçacığı modeli nesnenin her zaman birincil COM parçacığında çalışır. Bkz: [Single-Threaded grupların](http://msdn.microsoft.com/library/windows/desktop/ms680112) ve [Inprocserver32](http://msdn.microsoft.com/library/windows/desktop/ms682390) daha fazla bilgi için.|  
|**Grup**|Nesne Apartman iş parçacığı oluşturma kullandığını belirtir. Eşdeğer tek iş parçacığı grubu. Her bir boş iş parçacıklı bileşen nesnesinin ömrü boyunca nesnesi, iş parçacığı için bir grup atanır; Ancak, birden çok iş parçacığı birden fazla nesne kullanılabilir. Her grup için belirli bir iş parçacığı bağlıdır ve bir Windows ileti Pompalama (varsayılan) sahiptir.<br /><br /> Bkz: [Single-Threaded grupların](http://msdn.microsoft.com/library/windows/desktop/ms680112) daha fazla bilgi için.|  
|**Her ikisi**|Nesne grubu ya da boş iş parçacığı oluşturma, oluşturulduktan bir iş parçacığı hangi tür gelen bağlı olarak kullanabileceğiniz belirtir.|  
|**Boş**|Nesne serbest iş parçacığı oluşturmayı kullandığını belirtir. Boş iş parçacığı oluşturma için çoklu iş parçacığı apartman modeli eşdeğerdir. Bkz: [birden çok iş parçacıklı grupların](http://msdn.microsoft.com/library/windows/desktop/ms693421) daha fazla bilgi için.|  
|**Nötr** (yalnızca Windows 2000)|Nesne birden çok iş parçacıklı grupların yönelik yönergeleri takip eder, ancak iş parçacığı her türlü yürütebilir belirtir.|  
  
 **Toplama**  
 Nesne kullanıp kullanmadığını belirten [toplama](http://msdn.microsoft.com/library/windows/desktop/ms686558). Hangi istemcilere göstermek için arabirimleri toplama bir nesne seçer ve onları toplama bir nesne uygulanırsa, gibi arabirimler gösterilir. Birleşik nesnesinin istemciler yalnızca toplama bir nesne ile iletişim kurar.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Evet**|Nesne kümelenebilir belirtir. Varsayılan.|  
|**Yok**|Nesne olmayan toplanır belirtir.|  
|**Yalnızca**|Nesne toplanması gereken belirtir.|  
  
 **Destek**  
 (Eklenecek öğe açıklaması)  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**ISupportErrorInfo**|Desteği oluşturur [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) nesne istemciye hata bilgilerini dönebilmeniz arabirim.|  
|**Bağlantı noktaları**|Bağlantı noktaları, nesne için nesnenin sınıf türetin yaparak etkinleştirir [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|  
|**Ücretsiz iş parçacıklı Sıralayıcı**|Aynı işlemde iş parçacıkları arasında verimli bir şekilde arabirimi işaretçilerini sıralama için ücretsiz iş parçacıklı Sıralayıcı nesnesi oluşturur. Ya da belirtme nesne için kullanılabilen **her ikisi de** veya **serbest** iş parçacığı modeli olarak.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Active Server sayfası Bileşen Sihirbazı](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server sayfası bileşeni](../../atl/reference/adding-an-atl-active-server-page-component.md)

