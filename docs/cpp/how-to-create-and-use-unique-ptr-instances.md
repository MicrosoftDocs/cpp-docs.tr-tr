---
title: 'Nasıl yapılır: unique_ptr örnekleri oluşturma ve kullanma | Microsoft Docs'
ms.custom: how-to
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 9a373030-e587-452f-b9a5-c5f9d58b7673
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82cf4fb475f9c89a4a088cac9d5ee0e1231d436e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-create-and-use-uniqueptr-instances"></a>Nasıl yapılır: unique_ptr Örnekleri Oluşturma ve Kullanma
A [unique_ptr](../standard-library/unique-ptr-class.md) işaretçisini paylaşmaz. Bunu başka bir kopyalanamaz `unique_ptr`değere göre bir işleve veya oluşturulabilecek kopyalarının gerektiren tüm C++ Standart Kitaplığı algoritması kullanılır. A `unique_ptr` yalnızca taşınabilir. Bu bellek kaynağı sahipliğini başka aktarılır anlamına gelir `unique_ptr` ve özgün `unique_ptr` artık sahibi. Birden fazla sahiplik program mantığına karmaşıklık kattığından nesneyi tek sahiple kısıtlamanızı öneririz. Bu nedenle, akıllı bir işaretçi bir düz C++ nesne için ihtiyacınız olduğunda kullanın `unique_ptr`, ve oluşturduğunuzda bir `unique_ptr`, kullanın [make_unique](../standard-library/memory-functions.md#make_unique) yardımcı işlevi.  
  
 Aşağıdaki diyagramda iki arasında sahipliğini aktarma gösterilmektedir `unique_ptr` örnekleri.  
  
 ![Benzersiz bir sahipliğini taşıma&#95;ptr](../cpp/media/unique_ptr.png "unique_ptr")  
  
 `unique_ptr` tanımlanan `<memory>` C++ Standart Kitaplığı'nda başlığı. Tam olduğundan ham işaretçi olarak verimlidir ve C++ Standart Kitaplığı kapsayıcıları kullanılabilir. Eklenmesi `unique_ptr` C++ Standart Kitaplığı kapsayıcıları örneklerine verimli olduğundan taşıma oluşturucusunun `unique_ptr` bir kopyalama işlemi gereksinimini ortadan kaldırır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösterir `unique_ptr` örnekleri ve işlevleri arasında geçirin.  
  
 [!code-cpp[stl_smart_pointers#210](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_1.cpp)]  
  
 Bu temel karakteristiğini, bu örneklerde görüldüğü `unique_ptr`: taşınmış ancak kopyalanmadı. Yeni bir sahiplik aktarır "Taşıma" `unique_ptr` ve eski sıfırlar `unique_ptr`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösterir `unique_ptr` örnekleri ve bunları bir vektör kullanın.  
  
 [!code-cpp[stl_smart_pointers#211](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_2.cpp)]  
  
 For döngüsü aralığında dikkat `unique_ptr` başvuruya göre geçirilir. Burada değeri geçirmeye çalışırsanız, derleyici bir hata nedeniyle özel durum oluşturacak `unique_ptr` kopya Oluşturucu silinir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl başlatılacağını gösteren bir `unique_ptr` bir sınıf üyesi.  
  
 [!code-cpp[stl_smart_pointers#212](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_3.cpp)]  
  
## <a name="example"></a>Örnek  
 Kullanabileceğiniz [make_unique](../standard-library/memory-functions.md#make_unique) oluşturmak için bir `unique_ptr` bir diziye ancak kullanamazsınız `make_unique` dizi öğeleri başlatılamadı.  
  
 [!code-cpp[stl_smart_pointers#213](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_4.cpp)]  
  
 Daha fazla örnek için bkz: [make_unique](../standard-library/memory-functions.md#make_unique).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md)   
 [make_unique](../standard-library/memory-functions.md#make_unique)