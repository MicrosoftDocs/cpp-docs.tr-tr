---
title: 'Nasıl yapılır: shared_ptr örnekleri oluşturma ve kullanma | Microsoft Docs'
ms.custom: how-to
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7d6ebb73-fa0d-4b0b-a528-bf05de96518e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0b74909e048789662800569f8d996747fb8cadf
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403050"
---
# <a name="how-to-create-and-use-sharedptr-instances"></a>Nasıl yapılır: shared_ptr Örnekleri Oluşturma ve Kullanma
`shared_ptr` Senaryoları, birden fazla sahibi gerekebilir bellekteki nesnenin ömrünü yönetmek için tasarlanan C++ Standart Kitaplığı'nda bir akıllı işaretçi türüdür. Başlatın, sonra bir `shared_ptr` kopyalayın, değer tarafından işlev bağımsız değişkenleri geçirme ve diğer atamak `shared_ptr` örnekleri. Tüm örnekleri aynı nesneye'nın üzerine gelin, yeni bir başvuru sayısı paylaşım erişimi için bir "artırır denetim bloğu" ve azaltır `shared_ptr` eklenir, kapsamın dışına çıkıncaya veya sıfırlanır. Başvuru sayısı sıfır ulaştığında, denetim bloğu bellek kaynağı ve kendisini siler.  
  
 Aşağıda birkaç gösterilmiştir `shared_ptr` bir bellek konumuna işaret örnekleri.  
  
 [![Paylaşılan işaretçi](../cpp/media/shared_ptr.png "shared_ptr")](assetId:///9785ad08-31d8-411a-86a9-fb9cd9684c27)  
  
## <a name="example"></a>Örnek  
 Mümkün olduğunda kullanın [make_shared](../standard-library/memory-functions.md#make_shared) oluşturmak için işlevi bir `shared_ptr` bellek kaynağı ilk kez oluşturulduğunda. `make_shared` özel durum-güvenli olmayandır. Aynı çağrı denetim bloğu ve kaynak için bellek ayırmak için kullanır ve böylece oluşturma ek yükü azaltır. Kullanmıyorsanız, `make_shared`, kendisine geçirdiğiniz önce nesne oluşturmak için açık bir new ifadesi kullanmayı sahip `shared_ptr` Oluşturucusu. Aşağıdaki örnek, bildirmek ve başlatmak için çeşitli yollar gösterir. bir `shared_ptr` birlikte yeni bir nesne.  
  
 [!code-cpp[stl_smart_pointers#1](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_1.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bildirmek ve başlatmak gösterilmektedir `shared_ptr` uygulamanız örnekler paylaşılan bir başkası tarafından zaten ayrılmış bir nesne sahipliğini `shared_ptr`. Varsayımında `sp2` başlatılan bir olan `shared_ptr`.  
  
 [!code-cpp[stl_smart_pointers#2](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_2.cpp)]  
  
## <a name="example"></a>Örnek  
 `shared_ptr` C++ Standart Kitaplığı kapsayıcıları öğeleri kopyala algoritmalar kullandığınızda da yararlıdır. Öğeleri kaydırılabilir bir `shared_ptr`ve diğer temel alınan bellek ihtiyacınız olduğu sürece geçerli ve artık olduğunu anlama kapsayıcılarla kopyalayın. Aşağıdaki örnek nasıl kullanılacağını gösterir `replace_copy_if` algoritmasına `shared_ptr` vektördeki örnekleri.  
  
 [!code-cpp[stl_smart_pointers#4](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_3.cpp)]  
  
## <a name="example"></a>Örnek  
 Kullanabileceğiniz `dynamic_pointer_cast`, `static_pointer_cast`, ve `const_pointer_cast` dönüştürülecek bir `shared_ptr`. Bu işlevler benzer `dynamic_cast`, `static_cast`, ve `const_cast` işleçleri. Aşağıdaki örnek, bir vektör her öğenin türetilmiş tür test etme gösterir `shared_ptr` , temel sınıflar, öğeleri kopyalayın ve bunlarla ilgili bilgileri görüntüler.  
  
 [!code-cpp[stl_smart_pointers#5](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_4.cpp)]  
  
## <a name="example"></a>Örnek  
 Geçirebilirsiniz bir `shared_ptr` aşağıdaki yollarla başka bir işleve:  
  
-   Geçirmek `shared_ptr` değere göre. Bu kopya oluşturucusunu çağırır, başvuru sayısını artırır ve çağrılan sahibi yapar. Az miktarda bir kaç bağlı olarak önemli bu işlem ek yükü var. `shared_ptr` , kaçı nesneleri. Çağıran ve çağrılan arasında kod Sözleşmesi (örtük veya açık) çağrılan sahibi olmanız gerektiğinde bu seçeneği kullanın.  
  
-   Geçirmek `shared_ptr` başvuru veya const başvuru. Bu durumda, başvuru sayısını değil artırılır ve çağıran kapsam dışına geçmez sürece çağrılan işaretçi erişebilirsiniz. Ya da çağrılan oluşturmaya karar bir `shared_ptr` Referanslı ve böylece bir paylaşılan sahibi. Çağrılan olanağıyla çağırana sahip olduğunda ya da geçirmeniz gerekir bu seçeneği kullanın. bir `shared_ptr` ve performansı artırmak için kopyalama işlemini ortadan kaldırmak istiyorsanız.  
  
-   Temel alınan işaretçiye veya arka plandaki nesneye bir başvuru geçirin. Bu nesne kullanmak Aranan sağlar, ancak bu paylaşım sahipliğinin veya ömrü genişletmek etkinleştirmez. Çağrılan oluşturursa bir `shared_ptr` ham işaretçisinden yeni `shared_ptr` orijinalden bağımsızdır ve temel alınan kaynak denetlemez. Sözleşme çağıran ve çağrılan arasında NET bir şekilde çağıran sahipliğini korur belirttiğinde, bu seçeneği kullanın. `shared_ptr` yaşam süresi.  
  
-   Ne zaman karar geçirmek nasıl bir `shared_ptr`, çağrılan temel alınan kaynağın sahipliği paylaşmaya gerekip gerekmediğini belirlemek. "Sahip" nesne veya işlev ihtiyaç duyduğu sürece, temel alınan kaynak için canlı tut ' dir. Çağrılan işaretçi ömrünü genişletebilirsiniz güvence altına almak çağırıcı sahip değilse, (işlev) yaşam süresi, ilk kullanım seçeneği. Çağrılan yaşam süresini uzatır olup olmadığını İlgilenmiyor, başvuruya göre ve veya kopyalama çağrılan olanak tanır.  
  
-   Gerekirse temel alınan işaretçi sahipliğini paylaşmak yardımcı işlevini yalnızca işaretçi kullanıyor ve çağıran işlevi döndürür ve ardından bu işlev önce iade, temel alınan işaretçi için ve bir yardımcı işlev erişim bilmeniz verin yok. Yalnızca işaretçi arayanın yaşam süresi içinde erişmek sahip `shared_ptr`. Bu durumda, geçirilecek güvenli `shared_ptr` başvuru veya pass ham işaretçi veya başvuru temel alınan nesne. Bu şekilde geçirme küçük performans artar ve ayrıca, programlama amacınızla express yardımcı olabilir.  
  
-   Bazı durumlarda örneğin bir `std:vector<shared_ptr<T>>`, her geçmesi gerekebilir `shared_ptr` bir lambda ifadesi gövdesinin veya adlandırılmış işlev nesnesi. Lambda veya işlev işaretçisi depolamayın ardından geçirmesi `shared_ptr` her öğe için kopya Oluşturucusu çağrılırken önlemek için başvuruya göre.    
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği nasıl `shared_ptr` tarafından sahip olunan bir bellek işaretçi karşılaştırmalar etkinleştirmek için çeşitli Karşılaştırma işleçleri aşırı `shared_ptr` örnekleri.  
  
 [!code-cpp[stl_smart_pointers#3](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_6.cpp)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md)