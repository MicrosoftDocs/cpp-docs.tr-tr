---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: unique_ptr örnekleri oluşturma ve kullanma'
title: 'Nasıl yapılır: unique_ptr örnekleri oluşturma ve kullanma'
ms.custom: how-to
ms.date: 11/19/2018
ms.topic: conceptual
ms.assetid: 9a373030-e587-452f-b9a5-c5f9d58b7673
ms.openlocfilehash: a53b3a9704c62803b50c9bde2c7db70c190a8008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268671"
---
# <a name="how-to-create-and-use-unique_ptr-instances"></a>Nasıl yapılır: unique_ptr örnekleri oluşturma ve kullanma

[Unique_ptr](../standard-library/unique-ptr-class.md) , işaretçisini paylaşmaz. Başka bir `unique_ptr` değere veya bir işleve geçirilemez, ya da kopyaların yapılması gereken herhangi bir C++ standart kitaplık algoritmasında kullanılamaz. `unique_ptr`Yalnızca taşınabilir. Bu, bellek kaynağının sahipliğinin başka bir sürümüne aktarılmasının `unique_ptr` ve özgün kaynağın `unique_ptr` artık sahip olmadığı anlamına gelir. Birden fazla sahiplik program mantığına karmaşıklık kattığından nesneyi tek sahiple kısıtlamanızı öneririz. Bu nedenle, düz bir C++ nesnesi için akıllı bir işaretçiye ihtiyacınız olduğunda, `unique_ptr` ve oluştururken `unique_ptr` [make_unique](../standard-library/memory-functions.md#make_unique) yardımcı işlevini kullanın.

Aşağıdaki diyagramda, iki örnek arasındaki sahipliğin aktarımı gösterilmektedir `unique_ptr` .

![Benzersiz bir&#95;PTR 'nin sahipliğini taşıma](media/unique_ptr.png "Benzersiz bir&#95;PTR 'nin sahipliğini taşıma")

`unique_ptr` , `<memory>` C++ standart kitaplığı 'ndaki üst bilgide tanımlanmıştır. Bu, bir ham işaretçi olarak tam olarak verimlidir ve C++ standart kitaplık kapsayıcılarında kullanılabilir. ' `unique_ptr` In taşıma Oluşturucusu `unique_ptr` bir kopyalama işlemine ihtiyacı ortadan kaldırdığı için, örneklerin C++ standart kitaplık kapsayıcılarına eklenmesi etkilidir.

## <a name="example-1"></a>Örnek 1

Aşağıdaki örnek, örneklerinin nasıl oluşturulacağını `unique_ptr` ve işlevler arasında nasıl geçirileceğini gösterir.

[!code-cpp[stl_smart_pointers#210](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_1.cpp)]

Bu örnekler, öğesinin bu temel özelliklerini gösterir `unique_ptr` : taşınabilir, ancak kopyalanmaz. "Taşıma" sahipliği yeni bir öğesine aktarır `unique_ptr` ve eskisini sıfırlar `unique_ptr` .

## <a name="example-2"></a>Örnek 2

Aşağıdaki örnek, örneklerinin nasıl oluşturulacağını `unique_ptr` ve bir vektör içinde nasıl kullanılacağını gösterir.

[!code-cpp[stl_smart_pointers#211](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_2.cpp)]

For döngüsü aralığında, `unique_ptr` başvurusunun başvuruya göre geçtiğini görürsünüz. Burada değere göre geçirmeye çalışırsanız, kopyalama Oluşturucusu silindiği için derleyici bir hata oluşturur `unique_ptr` .

## <a name="example-3"></a>Örnek 3

Aşağıdaki örnek, bir `unique_ptr` sınıf üyesi olan bir 'nın nasıl başlatılacağını göstermektedir.

[!code-cpp[stl_smart_pointers#212](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_3.cpp)]

## <a name="example-4"></a>Örnek 4

Bir diziye oluşturmak için [make_unique](../standard-library/memory-functions.md#make_unique) kullanabilirsiniz `unique_ptr` , ancak `make_unique` dizi öğelerini başlatmak için kullanamazsınız.

[!code-cpp[stl_smart_pointers#213](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_4.cpp)]

Daha fazla örnek için bkz. [make_unique](../standard-library/memory-functions.md#make_unique).

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](smart-pointers-modern-cpp.md)<br/>
[make_unique](../standard-library/memory-functions.md#make_unique)
