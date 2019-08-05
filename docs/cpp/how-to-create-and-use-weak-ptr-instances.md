---
title: 'Nasıl yapılır: Weak_ptr örnekleri oluşturma ve kullanma'
ms.custom: how-to
ms.date: 07/12/2018
ms.topic: conceptual
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
ms.openlocfilehash: 63eed40117d1a79c69bd05e5bd1503d4222f556d
ms.sourcegitcommit: af4ab63866ed09b5988ed53f1bb6996a54f02484
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2019
ms.locfileid: "68787086"
---
# <a name="how-to-create-and-use-weak_ptr-instances"></a>Nasıl yapılır: Weak_ptr örnekleri oluşturma ve kullanma

Bazen bir nesne, başvuru sayısının arttırmasına neden olmadan bir `shared_ptr` öğesinin temel alınan nesnesine erişmek için bir yol depolamalıdır. Genellikle, örnekler arasında `shared_ptr` döngüsel başvurular olduğunda bu durum oluşur.

En iyi tasarım, her seferinde, işaretçilerin paylaşılan sahipliğinin kaçınmaktır. Ancak, `shared_ptr` örneklerin sahipliğini paylaşıma almanız gerekiyorsa aralarındaki döngüsel başvurulardan kaçının. Döngüsel başvurular kaçınılmaz veya bazı nedenlerle tercih edilse de, bir veya daha fazla Sahibe `weak_ptr` daha zayıf bir başvuru `shared_ptr`vermek için kullanın. Bir `weak_ptr`kullanarak, var olan bir ilgili örnekler `shared_ptr` kümesine katılılan, ancak yalnızca temeldeki bellek kaynağı hala geçerliyse bir oluşturabilirsiniz. `weak_ptr` Kendisi başvuru saymasına katılmaz ve bu nedenle başvuru sayısının sıfıra gitmesini engellemez. Ancak, `weak_ptr` `shared_ptr` uygulamasının başlatıldığı yeni bir kopyasını elde etmek için kullanabilirsiniz. Bellek zaten silinmişse bir `bad_weak_ptr` özel durum oluşturulur. Bellek hala geçerliyse, yeni paylaşılan işaretçi başvuru sayısını artırır ve `shared_ptr` değişken kapsamda olduğu sürece belleğin geçerli olacağını garanti eder.

## <a name="example"></a>Örnek

Aşağıdaki kod örneğinde, dairesel bağımlılıklara sahip nesnelerin `weak_ptr` düzgün silinmesini sağlamak için kullanılan bir durum gösterilmektedir. Örneği incelerken, yalnızca alternatif çözümler değerlendirildikten sonra oluşturulduğunu varsayın. `Controller` Nesneler bir makine işleminin bazı yönlerini temsil eder ve bağımsız olarak çalışır. Her denetleyici, diğer denetleyicilerin durumunu dilediğiniz zaman sorgulayabilmelidir ve her biri bu amaç için özel `vector<weak_ptr<Controller>>` bir içerir. Her vektör döngüsel bir başvuru içerir ve bu nedenle, `weak_ptr` örnekleri `shared_ptr`yerine kullanılır.

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
Status of 0 = On
Status of 1 = On
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

Bir deneme olarak, vektörü `others` bir `vector<shared_ptr<Controller>>`olacak şekilde değiştirin ve ardından çıktıda, `TestRun` döndüğünde hiçbir yok edicisi çağrıldığına dikkat edin.

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](../cpp/smart-pointers-modern-cpp.md)
