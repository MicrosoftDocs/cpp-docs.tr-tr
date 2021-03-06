---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: weak_ptr örnekleri oluşturma ve kullanma'
title: 'Nasıl yapılır: weak_ptr örnekleri oluşturma ve kullanma'
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
ms.openlocfilehash: 1c28ca6d759be513347885ead82498877e935a60
ms.sourcegitcommit: c0c9cdae79f19655e809a4979227c51bb19cff63
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102236757"
---
# <a name="how-to-create-and-use-weak_ptr-instances"></a>Nasıl yapılır: weak_ptr örnekleri oluşturma ve kullanma

Bazen bir nesnenin, başvuru sayısının artmasına neden olmadan bir [shared_ptr](../standard-library/shared-ptr-class.md) temel alınan nesnesine erişmek için bir yol depolaması gerekir. Genellikle, örnekler arasında döngüsel başvurular olduğunda bu durum oluşur `shared_ptr` .

En iyi tasarım, her seferinde, işaretçilerin paylaşılan sahipliğinin kaçınmaktır. Ancak, örneklerin sahipliğini paylaşıma almanız gerekiyorsa aralarındaki `shared_ptr` Döngüsel başvurulardan kaçının. Döngüsel başvurular kaçınılmaz veya bazı nedenlerle tercih edilse de, bir veya daha fazla Sahibe daha zayıf bir başvuru sağlamak için [weak_ptr](../standard-library/weak-ptr-class.md) kullanın `shared_ptr` . Bir kullanarak `weak_ptr` , var olan bir `shared_ptr` ilgili örnekler kümesine katılılan, ancak yalnızca temeldeki bellek kaynağı hala geçerliyse bir oluşturabilirsiniz. `weak_ptr`Kendisi başvuru saymasına katılmaz ve bu nedenle başvuru sayısının sıfıra gitmesini engellemez. Ancak, `weak_ptr` uygulamasının başlatıldığı yeni bir kopyasını elde etmek için kullanabilirsiniz `shared_ptr` . Bellek zaten silinmişse `weak_ptr` bool işleci döndürülür **`false`** . Bellek hala geçerliyse, yeni paylaşılan işaretçi başvuru sayısını artırır ve değişken kapsamda olduğu sürece belleğin geçerli olacağını garanti eder `shared_ptr` .

## <a name="example"></a>Örnek

Aşağıdaki kod örneğinde, `weak_ptr` dairesel bağımlılıklara sahip nesnelerin düzgün silinmesini sağlamak için kullanılan bir durum gösterilmektedir. Örneği incelerken, yalnızca alternatif çözümler değerlendirildikten sonra oluşturulduğunu varsayın. `Controller`Nesneler bir makine işleminin bazı yönlerini temsil eder ve bağımsız olarak çalışır. Her denetleyici, diğer denetleyicilerin durumunu dilediğiniz zaman sorgulayabilmelidir ve her biri `vector<weak_ptr<Controller>>` Bu amaç için özel bir içerir. Her vektör döngüsel bir başvuru içerir ve bu nedenle, `weak_ptr` örnekleri yerine kullanılır `shared_ptr` .

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

Bir deneme olarak, vektörü `others` bir olacak şekilde değiştirin `vector<shared_ptr<Controller>>` ve ardından çıktıda, döndüğünde hiçbir yok edicisi çağrıldığına dikkat edin `RunTest` .

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](../cpp/smart-pointers-modern-cpp.md)
