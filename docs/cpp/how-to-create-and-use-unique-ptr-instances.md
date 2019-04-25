---
title: 'Nasıl yapılır: Unique_ptr örnekleri oluşturma ve kullanma'
ms.custom: how-to
ms.date: 11/19/2018
ms.topic: conceptual
ms.assetid: 9a373030-e587-452f-b9a5-c5f9d58b7673
ms.openlocfilehash: 48e459b69592bf4c231407c2a378a7b7e01ff4ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153659"
---
# <a name="how-to-create-and-use-uniqueptr-instances"></a>Nasıl yapılır: Unique_ptr örnekleri oluşturma ve kullanma

A [unique_ptr](../standard-library/unique-ptr-class.md) işaretçisini paylaşmaz. Bunu başka kopyalanamaz `unique_ptr`, bir işleve değer olarak geçilemez veya yapılacak kopya oluşturmayı gerektiren herhangi bir C++ Standart Kitaplığı algoritmasında kullanılamaz. A `unique_ptr` yalnızca taşınabilir. Bu bellek kaynağının sahipliğinin başka aktarılır anlamına gelir `unique_ptr` ve özgün `unique_ptr` INI artık belleğe sahip. Birden fazla sahiplik program mantığına karmaşıklık kattığından nesneyi tek sahiple kısıtlamanızı öneririz. Bu nedenle, gerektiğinde bir akıllı işaretçi için bir düz C++ nesnesi `unique_ptr`, oluşturduğunuzda bir `unique_ptr`, kullanın [make_unique](../standard-library/memory-functions.md#make_unique) yardımcı işlevi.

Aşağıdaki diyagramda iki arasında sahipliğin aktarılması gösterilmiştir `unique_ptr` örnekleri.

![Benzersiz bir sahipliğini taşıma&#95;ptr](../cpp/media/unique_ptr.png "sahipliğini benzersiz bir taşıma&#95;ptr")

`unique_ptr` tanımlanan `<memory>` C++ Standart Kitaplığı üst bilgisi. Bu tam olarak ham işaretçi olarak kadar verimli ve C++ Standart Kitaplığı kapsayıcıları kullanılabilir. Ek `unique_ptr` C++ Standart Kitaplığı kapsayıcıları örneklerine verimlidir çünkü taşıma Oluşturucusu `unique_ptr` kopyalama işlemine ihtiyacı ortadan kaldırır.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir `unique_ptr` örnekleri ve bunları işlevler arasında geçirin.

[!code-cpp[stl_smart_pointers#210](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_1.cpp)]

Bu örneklerde, temel özelliklerini gösterir `unique_ptr`:, taşınabilir, ancak kopyalanamaz. "Taşıma" sahipliği yeni bir aktarır `unique_ptr` ve eski sıfırlar `unique_ptr`.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir `unique_ptr` örnekler ve vektör içinde kullanabilirsiniz.

[!code-cpp[stl_smart_pointers#211](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_2.cpp)]

Döngü aralığında dikkat `unique_ptr` başvuruyla geçirildi. Burada değişkeni değer olarak denerseniz, derleyici bir hata verir `unique_ptr` kopya kurucusu silindiğinden.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl başlatılacağını gösterir. bir `unique_ptr` sınıf üyesi olan.

[!code-cpp[stl_smart_pointers#212](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_3.cpp)]

## <a name="example"></a>Örnek

Kullanabileceğiniz [make_unique](../standard-library/memory-functions.md#make_unique) oluşturmak için bir `unique_ptr` bir diziye ancak kullanamazsınız `make_unique` dizi öğelerini başlatmak için.

[!code-cpp[stl_smart_pointers#213](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_4.cpp)]

Daha fazla örnek için bkz. [make_unique](../standard-library/memory-functions.md#make_unique).

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](../cpp/smart-pointers-modern-cpp.md)<br/>
[make_unique](../standard-library/memory-functions.md#make_unique)
