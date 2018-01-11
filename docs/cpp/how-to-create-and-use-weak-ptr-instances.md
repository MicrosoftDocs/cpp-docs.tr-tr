---
title: "Nasıl yapılır: weak_ptr örnekleri oluşturma ve kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3e51e523540e14905bef17edd52205c4d2102afa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-and-use-weakptr-instances"></a>Nasıl yapılır: weak_ptr Örnekleri Oluşturma ve Kullanma
Nesnenin temel alınan nesnenin erişmek için bir yol bazen depolamalısınız bir `shared_ptr` artırılması gereken başvuru sayısı neden olmadan. Genellikle bu durum arasında döngüsel başvurulardan olduğunda ortaya çıkar `shared_ptr` örnekleri.  
  
 Yapabilecekleriniz her işaretçileri paylaşılan sahipliğini önlemek için en iyi tasarım gerekir. Ancak, sahipliğini Paylaşılan gruplarınız varsa `shared_ptr` örnekleri, bunlar arasında döngüsel başvurulardan kaçının. Döngüsel başvurulardan kaçınılmaz ya da hatta tercih herhangi bir nedenden dolayı olduğunda kullanın `weak_ptr` bir veya daha fazla sahipleri başka zayıf bir başvuru vermek için `shared_ptr`. Kullanarak bir `weak_ptr`, oluşturabileceğiniz bir `shared_ptr` , birleşimler ilgili örnekleri, ancak yalnızca var olan bir dizi temel alınan bellek kaynağı hala geçerli ise. A `weak_ptr` kendisini başvuru sayımı katılmak ve bu nedenle, bu başvuru sayısı sıfır olarak gitmesini engellemek olamaz. Ancak, kullanabileceğiniz bir `weak_ptr` yeni bir kopyasını elde etmek için `shared_ptr` ile hangi başlatıldı. Bellek zaten silinmiş olması durumunda bir **bad_weak_ptr** özel durumu oluşur. Bellek hala geçerliyse, yeni paylaşılan işaretçi başvuru sayısını artırır ve bellek geçerli olacağını garanti eder sürece `shared_ptr` değişkeni kapsam içinde kalır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde bir durumu gösterir nerede `weak_ptr` döngüsel bağımlılıklar sahip nesneleri uygun silinmesini sağlamak için kullanılır. Örnek inceleyin gibi yalnızca alternatif çözümleri olarak kabul sonra oluşturulduğu varsayılmaktadır. `Controller` Nesneleri makine işlemi bazı yönlerinin temsil eder ve bağımsız olarak çalışır. Her denetleyici herhangi bir zamanda diğer denetleyicileri durumunu sorgulayabilir ve her biri özel içeren `vector<weak_ptr<Controller>>` bu amaç için. Her vektör bir döngüsel başvuru içeriyor ve bu nedenle, `weak_ptr` örnekleri yerine kullanılır `shared_ptr`.  
  
 [!code-cpp[stl_smart_pointers#222](../cpp/codesnippet/CPP/how-to-create-and-use-weak-ptr-instances_1.cpp)]  
  
```Output  
Creating Controller0Creating Controller1Creating Controller2Creating Controller3Creating Controller4push_back to v[0]: 1push_back to v[0]: 2push_back to v[0]: 3push_back to v[0]: 4push_back to v[1]: 0push_back to v[1]: 2push_back to v[1]: 3push_back to v[1]: 4push_back to v[2]: 0push_back to v[2]: 1push_back to v[2]: 3push_back to v[2]: 4push_back to v[3]: 0push_back to v[3]: 1push_back to v[3]: 2push_back to v[3]: 4push_back to v[4]: 0push_back to v[4]: 1push_back to v[4]: 2push_back to v[4]: 3use_count = 1Status of 1 = OnStatus of 2 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 2 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 2 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 2 = OnStatus of 3 = OnDestroying Controller0Destroying Controller1Destroying Controller2Destroying Controller3Destroying Controller4Press any key  
```  
  
 Vektör bir deney değiştirmek `others` olacak şekilde bir `vector<shared_ptr<Controller>>`ve ardından hiçbir Yıkıcılar çağrılan çıktıda fark zaman `TestRun` döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md)