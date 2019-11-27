---
title: 'Nasıl yapılır: unique_ptr örnekleri oluşturma ve kullanma'
ms.custom: how-to
ms.date: 11/19/2018
ms.topic: conceptual
ms.assetid: 9a373030-e587-452f-b9a5-c5f9d58b7673
ms.openlocfilehash: 4b3362f71d1ccab0efb03d7e8705c6b3f25f9780
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246532"
---
# <a name="how-to-create-and-use-unique_ptr-instances"></a>Nasıl yapılır: unique_ptr örnekleri oluşturma ve kullanma

[Unique_ptr](../standard-library/unique-ptr-class.md) , işaretçisini paylaşmaz. Başka bir `unique_ptr`kopyalanamıyor, değere göre bir işleve geçirilemez veya kopyaların yapılmasını gerektiren herhangi C++ bir standart kitaplık algoritmasında kullanılamaz. Bir `unique_ptr` yalnızca taşınabilir. Bu, bellek kaynağının sahipliğinin başka bir `unique_ptr` aktarılmasının ve özgün `unique_ptr` artık sahip olmadığı anlamına gelir. Birden fazla sahiplik program mantığına karmaşıklık kattığından nesneyi tek sahiple kısıtlamanızı öneririz. Bu nedenle, düz C++ bir nesne için akıllı bir işaretçiye ihtiyacınız olduğunda `unique_ptr`kullanın ve bir `unique_ptr`oluşturduğunuzda [make_unique](../standard-library/memory-functions.md#make_unique) yardımcı işlevini kullanın.

Aşağıdaki diyagramda, iki `unique_ptr` örneği arasındaki sahipliğin aktarımı gösterilmektedir.

![Benzersiz&#95;bir PTR 'nin sahipliğini taşıma](media/unique_ptr.png "Benzersiz&#95;bir PTR 'nin sahipliğini taşıma")

`unique_ptr`, C++ standart kitaplıktaki `<memory>` üst bilgisinde tanımlanmıştır. Bu, bir ham işaretçi olarak tam olarak etkilidir ve C++ standart kitaplık kapsayıcılarında kullanılabilir. `unique_ptr` taşıma Oluşturucusu bir kopyalama işlemine C++ ihtiyacı ortadan kaldırdığı için, `unique_ptr` örneklerinin standart kitaplık kapsayıcılarına eklenmesi etkilidir.

## <a name="example-1"></a>Örnek 1

Aşağıdaki örnek, `unique_ptr` örneklerinin nasıl oluşturulacağını ve işlevler arasında nasıl geçirileceğini gösterir.

[!code-cpp[stl_smart_pointers#210](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_1.cpp)]

Bu örnekler `unique_ptr`bu temel özelliğini gösterir: taşınabilir, ancak kopyalanmaz. "Taşıma", sahipliği yeni bir `unique_ptr` aktarır ve eski `unique_ptr`sıfırlar.

## <a name="example-2"></a>Örnek 2

Aşağıdaki örnek, `unique_ptr` örneklerinin nasıl oluşturulacağını ve bir vektörde nasıl kullanılacağını gösterir.

[!code-cpp[stl_smart_pointers#211](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_2.cpp)]

For döngüsü aralığında `unique_ptr` başvuruya göre geçirildiğine dikkat edin. Burada değere göre geçiş yapmayı denerseniz, `unique_ptr` kopya Oluşturucu silindiği için derleyici bir hata oluşturur.

## <a name="example-3"></a>Örnek 3

Aşağıdaki örnek, bir sınıf üyesi olan bir `unique_ptr` başlatmayı gösterir.

[!code-cpp[stl_smart_pointers#212](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_3.cpp)]

## <a name="example-4"></a>Örnek 4

Bir diziye `unique_ptr` oluşturmak için [make_unique](../standard-library/memory-functions.md#make_unique) kullanabilirsiniz, ancak dizi öğelerini başlatmak için `make_unique` kullanamazsınız.

[!code-cpp[stl_smart_pointers#213](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_4.cpp)]

Daha fazla örnek için bkz. [make_unique](../standard-library/memory-functions.md#make_unique).

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](smart-pointers-modern-cpp.md)<br/>
[make_unique](../standard-library/memory-functions.md#make_unique)
