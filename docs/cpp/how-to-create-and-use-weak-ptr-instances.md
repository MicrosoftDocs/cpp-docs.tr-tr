---
title: 'Nasıl yapılır: weak_ptr örnekleri oluşturma ve kullanma | Microsoft Docs'
ms.custom: how-to
ms.date: 07/12/2018
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73b70a68226be14b7e99afe125b3dcd8b6784601
ms.sourcegitcommit: 9ad287c88bdccee2747832659fe50c2e5d682a0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39034822"
---
# <a name="how-to-create-and-use-weakptr-instances"></a>Nasıl yapılır: weak_ptr Örnekleri Oluşturma ve Kullanma
Bazen bir nesne arka plandaki nesneye erişme yolunu saklaması gerekir bir `shared_ptr` arttırılacak başvuru sayısının artmasına neden olmadan. Genellikle bu durum arasında döngüsel başvurular olduğunda ortaya çıkar `shared_ptr` örnekleri.  

 En iyi tasarım, olabildiğince paylaşılan işaretçi sahipliğinden kaçınmaktır. Ancak, sahipliğini Paylaşılan gruplarınız varsa `shared_ptr` örnekleri, bunlar arasında döngüsel başvurulardan kaçının. Döngüsel başvurular kaçınılmaz veya tercih herhangi bir nedenden dolayı olduğunuzda kullanın `weak_ptr` bir veya daha fazla sahipleri zayıf bir başvuru yapmasını sağlamak için `shared_ptr`. Kullanarak bir `weak_ptr`, oluşturabileceğiniz bir `shared_ptr` katılan ilgili örnekler, ancak yalnızca var olan bir dizi temel alınan bellek kaynağı hala geçerliyse. A `weak_ptr` kendisini başvuru sayımına değil ve bu nedenle, bu sıfıra gitmesi başvuru sayısı önleyemez. Ancak, kullanabileceğiniz bir `weak_ptr` yeni bir kopyasını elde etmek `shared_ptr` başlatılacağı ile. Bellek zaten silinmişse bir `bad_weak_ptr` özel durumu oluşturulur. Bellek hala geçerliyse, yeni paylaşılan işaretçi başvuru sayısını artırır ve belleğin geçerli olacağını garanti eder sürece `shared_ptr` değişkeni kapsam dahilinde kaldığı.  

## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği bir durumu gösterir. burada `weak_ptr` döngüsel bağımlılıkları olan nesnelerin düzgün silinmesi sağlamak için kullanılır. Örneği incelerken, yalnızca alternatif çözümler dikkate sonra oluşturulduğunu varsayın. `Controller` Nesneleri makine işleminin bazı yönlerini temsil eder ve bunlar bağımsız olarak çalışır. Her denetleyici herhangi bir zamanda diğer denetleyicilerin durumunu sorgulayabilir ve her biri bir özel içeren `vector<weak_ptr<Controller>>` bu amaç için. Her vektör bir döngüsel başvuru içerir ve bu nedenle, `weak_ptr` örneği yerine kullanılır `shared_ptr`.  

 [!code-cpp[stl_smart_pointers#222](../cpp/codesnippet/CPP/how-to-create-and-use-weak-ptr-instances_1.cpp)]  

```Output  
Creating Controller0  
Creating Controller1  
Creating Controller2  
Creating Controller3  
Creating Controller4  
push_back to v[0]: 1  
push_back to v[0]: 2  
push_back to v[0]: 3  
push_back to v[0]: 4  
push_back to v[1]: 0  
push_back to v[1]: 2  
push_back to v[1]: 3  
push_back to v[1]: 4  
push_back to v[2]: 0  
push_back to v[2]: 1  
push_back to v[2]: 3  
push_back to v[2]: 4  
push_back to v[3]: 0  
push_back to v[3]: 1  
push_back to v[3]: 2  
push_back to v[3]: 4  
push_back to v[4]: 0  
push_back to v[4]: 1  
push_back to v[4]: 2  
push_back to v[4]: 3
use_count = 1  
Status of 1 = On  
Status of 2 = On  
Status of 3 = On  
Status of 4 = On  
use_count = 1  
Status of 0 = On  
Status of 2 = On  
Status of 3 = On  
Status of 4 = On  
use_count = 1  
Status of 0 = On  
Status of 1 = On  
Status of 3 = On  
Status of 4 = On  
use_count = 1  
Status of 0 = O  
nStatus of 1 = On  
Status of 2 = On  
Status of 4 = On  
use_count = 1  
Status of 0 = On  
Status of 1 = On  
Status of 2 = On  
Status of 3 = On  
Destroying Controller0  
Destroying Controller1  
Destroying Controller2  
Destroying Controller3  
Destroying Controller4  
Press any key  
```  

 Bir deney vektör değiştirme `others` olacak şekilde bir `vector<shared_ptr<Controller>>`ve sonra da çıktıda hiçbir yok edicinin çağrılmadığına dikkat edin, `TestRun` döndürür.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md)