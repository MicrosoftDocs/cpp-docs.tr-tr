---
title: 'Nasıl yapılır: weak_ptr örnekleri oluşturma ve kullanma'
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
ms.openlocfilehash: 32e8d64fdb6449f1d40aec4161bfda54987ca66a
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245595"
---
# <a name="how-to-create-and-use-weak_ptr-instances"></a>Nasıl yapılır: weak_ptr örnekleri oluşturma ve kullanma

Bazen bir nesnenin, başvuru sayısının artmasına neden olmadan bir [shared_ptr](../standard-library/shared-ptr-class.md) temel alınan nesnesine erişmek için bir yol depolaması gerekir. Genellikle, bu durum `shared_ptr` örnekleri arasında döngüsel başvurular olduğunda meydana gelir.

En iyi tasarım, her seferinde, işaretçilerin paylaşılan sahipliğinin kaçınmaktır. Ancak, `shared_ptr` örneklerinin sahipliğinin paylaşıldığından, aralarında döngüsel başvuruların olmaması gerekir. Döngüsel başvurular kaçınılmaz veya bazı nedenlerle tercih edilse de, bir veya daha fazla Sahibe başka bir `shared_ptr`için zayıf bir başvuru sağlamak üzere [weak_ptr](../standard-library/weak-ptr-class.md) kullanın. `weak_ptr`kullanarak, mevcut bir ilgili örnekler kümesine katılan bir `shared_ptr` oluşturabilirsiniz, ancak yalnızca temeldeki bellek kaynağı hala geçerliyse. `weak_ptr` kendisi başvuru saymasına katılmaz ve bu nedenle başvuru sayısının sıfıra gitmesini engellemez. Ancak, `shared_ptr` başlatıldığı yeni bir kopyasını edinmeyi denemek için bir `weak_ptr` kullanabilirsiniz. Bellek zaten silinmişse `weak_ptr`bool işleci `false`döndürür. Bellek hala geçerliyse, yeni paylaşılan işaretçi başvuru sayısını artırır ve `shared_ptr` değişkeni kapsamda olduğu sürece belleğin geçerli olacağını garanti eder.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, dairesel bağımlılıklara sahip nesnelerin düzgün silinmesini sağlamak için `weak_ptr` kullanıldığı bir durumu gösterir. Örneği incelerken, yalnızca alternatif çözümler değerlendirildikten sonra oluşturulduğunu varsayın. `Controller` nesneler bir makine işleminin bazı yönlerini temsil eder ve bağımsız olarak çalışır. Her denetleyicinin, diğer denetleyicilerin durumunu dilediğiniz zaman sorgulayabilmesi ve her biri bu amaçla özel bir `vector<weak_ptr<Controller>>` içermesi gerekir. Her vektör döngüsel bir başvuru içerir ve bu nedenle `weak_ptr` örnekleri `shared_ptr`yerine kullanılır.

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

Bir deneme olarak, vektör `others` bir `vector<shared_ptr<Controller>>`olacak şekilde değiştirin ve sonra çıktıda `TestRun` döndürüldüğünde hiçbir yok edicisi çağrıldığına dikkat edin.

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](../cpp/smart-pointers-modern-cpp.md)
