---
title: "Nasıl yapılır: shared_ptr örnekleri oluşturma ve kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 7d6ebb73-fa0d-4b0b-a528-bf05de96518e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fdabfad3d1b4ae6ee07a8d9e660ab31cbdc1df03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-and-use-sharedptr-instances"></a>Nasıl yapılır: shared_ptr Örnekleri Oluşturma ve Kullanma
`shared_ptr` Türü bir işaretçidir akıllı C++ Standart kitaplığında senaryoları, birden fazla sahibi gerekebilir bellekte nesnesi ömrünü yönetmek için tasarlanmıştır. Başlatır sonra bir `shared_ptr` kopyalayın, işlev bağımsız değişkenleri değere göre geçirmek ve diğer atamak `shared_ptr` örnekleri. Tüm örnekleri aynı nesneye'nın üzerine gelin, yeni bir başvuru sayısı paylaşım erişimi azaltır ve bir "artırır denetim bloğu" `shared_ptr` eklenir, kapsam dışı geçip geçmeyeceğini veya sıfırlanır. Başvuru sayısı sıfır ulaştığında, denetim bloğu bellek kaynağı ve kendisini siler.  
  
 Aşağıda birkaç gösterilmiştir `shared_ptr` bir bellek konumunu işaret örnekleri.  
  
 [![Paylaşılan işaretçi](../cpp/media/shared_ptr.png "shared_ptr")](assetId:///9785ad08-31d8-411a-86a9-fb9cd9684c27)  
  
## <a name="example"></a>Örnek  
 Mümkün olduğunda kullanın [make_shared](../standard-library/memory-functions.md#make_shared) işlevi oluşturmak için bir `shared_ptr` bellek kaynağı ilk kez oluşturulduğunda. `make_shared`özel durum-güvenlidir. Aynı çağrı denetim bloğu ve kaynak için bellek ayırmak için kullanır ve böylece yapım ek yükünü azaltır. Kullanmıyorsanız, `make_shared`, kendisine geçirmeden önce nesneyi oluşturmak için bir açık yeni ifade kullanmak zorunda sonra `shared_ptr` Oluşturucusu. Aşağıdaki örnek, bildirme ve başlatmak için çeşitli yollar gösterir bir `shared_ptr` birlikte yeni bir nesne.  
  
 [!code-cpp[stl_smart_pointers#1](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_1.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bildirilip gösterilmektedir `shared_ptr` uygulamanız örnekleri paylaşılan bir başkası tarafından zaten ayrılmış bir nesnenin sahipliğini `shared_ptr`. Varsayımında `sp2` bir başlatılmış olduğunu `shared_ptr`.  
  
 [!code-cpp[stl_smart_pointers#2](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_2.cpp)]  
  
## <a name="example"></a>Örnek  
 `shared_ptr`öğeleri kopyalama algoritmaları kullanırken C++ Standart Kitaplığı kapsayıcılarında yararlıdır. Öğeleri kayabilir bir `shared_ptr`ve diğer kapsayıcılarını temelindeki bellek ihtiyacınız olduğu sürece geçerli ve artık olduğunu anlama ile kopyalayın. Aşağıdaki örnekte nasıl kullanılacağını gösterir `replace_copy_if` algoritmasına `shared_ptr` vektör örnekleri.  
  
 [!code-cpp[stl_smart_pointers#4](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_3.cpp)]  
  
## <a name="example"></a>Örnek  
 Kullanabileceğiniz `dynamic_pointer_cast`, `static_pointer_cast`, ve `const_pointer_cast` dönüştürmek için bir `shared_ptr`. Bu işlevler benzer `dynamic_cast`, `static_cast`, ve `const_cast` işleçler. Aşağıdaki örnek bir vektörü her öğesinin türetilen tür test etme gösterir `shared_ptr` , temel sınıflar, öğeleri kopyalayın ve bunlarla ilgili bilgileri görüntüler.  
  
 [!code-cpp[stl_smart_pointers#5](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_4.cpp)]  
  
## <a name="example"></a>Örnek  
 Geçirebilirsiniz bir `shared_ptr` aşağıdaki yollarla başka bir işlev için:  
  
-   Geçirmek `shared_ptr` değeriyle. Bu kopya oluşturucu çağırır, başvuru sayısını artırır ve Aranan sahibi yapar. Bu işlem bağlı olarak kaç önemli ek yükü az miktarda yoktur `shared_ptr` geçirme nesneleri. Çağıran ve çağrılan arasında kod Sözleşme (örtük veya açık) aranan bir sahip olması gerektiğinde bu seçeneği kullanın.  
  
-   Geçirmek `shared_ptr` başvuru veya const başvuru. Bu durumda, başvuru sayımı değil artırılır ve arayan kapsamının dışına geçmez sürece Aranan işaretçinin erişebilir. Veya, aranan oluşturmaya karar verebilirsiniz bir `shared_ptr` referansı temel alarak ve böylece bir paylaşılan sahibi olur. Çağıran ve çağrılan olanağıyla olduğunda veya, geçmesi gerektiğinde bu seçeneği kullanın bir `shared_ptr` ve performansı artırmak için kopyalama işlemi önlemek istiyorsanız.  
  
-   Temel alınan işaretçi veya temel alınan nesnede başvurusu geçirin. Bu nesne kullanılacak Aranan sağlar, ancak sahipliği paylaşma veya yaşam genişletmek için etkinleştirmez. Aranan oluşturursa bir `shared_ptr` ham işaretçiden itibaren yeni `shared_ptr` özgün bağımsızdır ve temel alınan kaynak denetlemez. Arayan sahipliğini korur çağıran ve çağrılan arasında sözleşme açıkça belirtir olduğunda bu seçeneği kullanın `shared_ptr` yaşam süresi.  
  
-   Ne zaman karar geçirmek nasıl bir `shared_ptr`, aranan temel alınan kaynak sahipliğini paylaşmak sahip olup olmadığını belirleyin. Bir "sahibi" bir nesneye veya, gerekli olduğu sürece, temel alınan kaynak için Canlı tutabilirsiniz işlevi değil. Aranan işaretçi ömrünü uzatabilir garanti etmek arayan varsa, kendi (işlev) yaşam süresi, ilk kullan seçeneği. Aranan ömrü genişletir olup olmadığını önemli değil, başvuruya göre geçirme ve veya kopyalama Aranan olanak tanır.  
  
-   Gerekirse bir yardımcı işlevi erişim temel işaretçi ve bilmeniz yardımcı işlevini yalnızca işaretçi kullanıyor ve arama işlevini döndürür, sonra bu işlev önce dönüş emin verin temel işaretçi sahipliğini paylaşmak yok. Bunu yalnızca işaretçi arayanın yaşam süresi içinde erişmelidir `shared_ptr`. Bu durumda, geçirmek güvenli `shared_ptr` başvuru veya geçişi ham işaretçi veya arka plandaki başvuru nesnesi. Bu şekilde geçirme küçük performans avantajı sağlar ve ayrıca programlama maksadınızı express yardımcı.  
  
-   Bazı durumlarda örneğin bir `std:vector<shared_ptr<T>>`, her geçmesi gerekebilir `shared_ptr` bir lambda ifadesi gövdesi veya adlandırılmış işlev nesnesi. Lambda veya işlev işaretçisi depolamayın, daha sonra geçirin `shared_ptr` her öğe için kopya Oluşturucu çağırma önlemek için başvuruya göre.    
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği nasıl `shared_ptr` tarafından sahip olunan bellek işaretçisi karşılaştırmaları etkinleştirmek için çeşitli Karşılaştırma işleçleri aşırı yüklemeler `shared_ptr` örnekleri.  
  
 [!code-cpp[stl_smart_pointers#3](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_6.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md)