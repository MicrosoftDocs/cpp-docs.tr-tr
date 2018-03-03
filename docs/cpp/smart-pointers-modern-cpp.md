---
title: "Akıllı işaretçiler (Modern C++) | Microsoft Docs"
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
ms.assetid: 909ef870-904c-49b6-b8cd-e9d0b7dc9435
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e5883cc7f028c2d64c038a2cdbd9b8365b7e61d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="smart-pointers-modern-c"></a>Akıllı İşaretçiler (Modern C++)
Modern C++ programlama standart kitaplığı içerir *akıllı işaretçiler*, hangi programları sağlamaya yardımcı olmak için kullanılan bellek ücretsiz ve kaynak sızdırıyor ve özel durum güvenlidir.  
  
## <a name="uses-for-smart-pointers"></a>Akıllı işaretçiler için kullanım alanları  
 Akıllı işaretçiler tanımlanmış `std` ad alanında [ \<bellek >](../standard-library/memory.md) üstbilgi dosyası. İçin kritik önem taşıyan [RAII](../cpp/objects-own-resources-raii.md) veya *kaynak edinme olan Initialialization* programlama deyim. Bu deyimin ana amacı, kaynak alımının nesnenin başlatılmasıyla aynı anda gerçekleşmesini sağlamaktır; böylece nesne için tüm kaynaklar bir kod satırında oluşturulur ve hazır hale getirilir. Pratikte temel RAII prensibi, yığın tarafından ayrılan herhangi bir kaynağın sahipliğini örneğin, dinamik olarak ayrılan belek veya sistem nesnesi tanıtıcıları, yok edicisi kaynağı silmek veya boşaltmak için gereken kodu ve herhangi bir temizleme kodunu içeren ve yığın tarafından ayrılan bir nesneye vermektir.  
  
 Çoğu durumda gerçek bir kaynağı işaret etmek ve işaretçiyi hemen bir akıllı işaretçiye dönüştürmek için bir ham işaretçi veya kaynak tanıtıcısı kullanırsınız. Modern C++ programlamada, ham işaretçiler yalnızca performansın önemli olduğu ve sahiplik konusunda karışıklık olma ihtimali bulunmayan kapsam, döngü veya yardımcı işlevler açısından sınırlı olan küçük kod engellerinde kullanılır.  
  
 Aşağıdaki örnek, bir ham işaretçi bildirimini bir akıllı işaretçi bildirimi ile karşılaştırır.  
  
 [!code-cpp[smart_pointers_intro#1](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_1.cpp)]  
  
 Akıllı işaretçi, örnekte gösterildiği gibi, yığında bildirdiğiniz ve yığın tarafından ayrılan nesneyi gösteren ham işaretçiyi kullanarak başlattığınız bir sınıf şablonudur. Akıllı işaretçi başlatıldıktan sonra ham işaretçiyi üstlenir. Bu, akıllı işaretçinin, ham işaretçinin belirttiği belleği silmekten sorumlu olduğu anlamına gelir. Akıllı işaretçi yok edici silinecek çağrıyı içerir ve akıllı işaretçi yığında bildirildiğinden, akıllı işaretçi kapsam dışına çıktığında, yığının daha ileri bir yerinde bir özel durum olsa bile, yok edicisi çağrılır.  
  
 Tanıdık işaretçi işleçleri kullanarak kapsüllenmiş işaretçi erişim `->` ve `*`, hangi kapsüllenmiş ham işaretçi döndürmek için akıllı işaretçi sınıfı overloads.  
  
 C++ akıllı işaretçi deyimi, C# gibi dillerde nesne oluşturmaya benzer: Nesneyi oluşturursunuz ve ardından sistemin doğru zamanda bunu silmesine izin verirsiniz. Fark arka planda ayrı bir çöp toplayıcının çalışmamasıdır; bellek standart C++ kapsama kuralları ile yönetilir, bu nedenle çalışma zamanı ortamı daha hızlı ve daha verimlidir.  
  
> [!IMPORTANT]
>  Akıllı işaretçileri, asla parametre listesinde değil, her zaman ayrı bir kod satırında oluşturun, böylece belli parametre listesi ayırma kuralları nedeniyle küçük kaynak sızıntıları meydana gelmesine engel olursunuz.  
  
 Aşağıdaki örnekte gösterildiği nasıl bir `unique_ptr` akıllı işaretçi türü C++ Standart Kitaplığı, geniş bir nesne için bir işaretçi kapsülleyen kullanılabilirdi.  
  
 [!code-cpp[smart_pointers_intro#2](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_2.cpp)]  
  
 Örnek akıllı işaretçileri kullanmak için aşağıdaki temel adımları gösterir.  
  
1.  Akıllı işaretçiyi otomatik bir (yerel) değişken olarak bildirin. (Kullanmayın `new` veya `malloc` akıllı işaretçi ifadeye.)  
  
2.  Tür parametresinde kapsüllenen işaretçinin, işaret edilen türünü belirtin.  
  
3.  Ham işaretçi bir `new`-ed nesnesinde akıllı işaretçi Oluşturucusu. (Bazı yardımcı program işlevleri veya akıllı işaretçi oluşturucuları bunu sizin için yapar.)  
  
4.  Aşırı yüklenmiş kullanmak `->` ve `*` nesneye erişim işleçler.  
  
5.  Akıllı işaretçinin nesneyi silmesine izin verin.  
  
 Akıllı işaretçiler bellek ve performans açısından mümkün olduğunda verimli olmak için tasarlanmıştır. Örneğin, yalnızca veri üyesi `unique_ptr` kapsüllenmiş işaretçidir. Bunun anlamı `unique_ptr` dört bayt veya sekiz bayt bu işaretçiyi tam olarak aynı boyutta değil. Aşırı yüklenmiş akıllı işaretçi kullanarak kapsüllenmiş işaretçi erişim * ve işleçler -> Ham işaretçileri doğrudan erişimini daha önemli ölçüde daha yavaş değil.  
  
 Akıllı işaretçilerin “dot” belirtimi kullanılarak erişilen kendi üye işlevleri vardır. Örneğin, bazı C++ Standart Kitaplığı akıllı işaretçiler işaretçinin sahipliğini serbest sıfırlama üye işlevi vardır. Bu, aşağıdaki örnekte gösterildiği şekilde akıllı işaretçi kapsam dışında çıkmadan önce akıllı işaretçinin sahip olduğu belleği boşaltmak istediğinizde yararlıdır.  
  
 [!code-cpp[smart_pointers_intro#3](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_3.cpp)]  
  
 Akıllı işaretçiler genelde ham işaretçilerine doğrudan erişmek için bir yol sağlar. C++ Standart Kitaplığı akıllı işaretçiler sahip bir `get` üye işlevi bu amaç için ve `CComPtr` ortak olan `p` sınıf üyesi. Temel alınan işaretçiye doğrudan erişim sağladığınızda, akıllı işaretçiyi kendi kodunuzla bellek yönetmek amacıyla kullanırken, ham işaretçiyi de hala akıllı işaretçileri desteklemeyen koda geçirebilirsiniz.  
  
 [!code-cpp[smart_pointers_intro#4](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_4.cpp)]  
  
## <a name="kinds-of-smart-pointers"></a>Akıllı İşaretçi Türleri  
 Aşağıdaki bölümde Windows programlama ortamında bulunan farklı türden akıllı işaretçiler özetlenir ve bunların ne zaman kullanılacağı açıklanır.  
  
 **C++ Standart Kitaplığı akıllı işaretçiler**  
 Bu akıllı işaretçileri eski C++ nesnelerine (POCO) işaretçi kapsüllemek için ilk seçenek olarak kullanın.  
  
-   `unique_ptr`   
     Temel alınan işaretçi için, kesin olarak tek bir sahibe izin verir. İhtiyaç duyduğunuz belirli bilmiyorsanız varsayılan seçim olarak POCO için kullanmak bir `shared_ptr`. Bir yeni kullanıcıya taşınabilir, ancak kopyalanamaz veya paylaşılamaz. Değiştirir `auto_ptr`, kullanım dışı. Karşılaştırılacak `boost::scoped_ptr`. `unique_ptr`küçük ve etkili değildir; bir işaretçi boyutudur ve hızlı ekleme ve C++ Standart Kitaplığı koleksiyonundan alımı için rvalue başvuru destekler. Üstbilgi dosyası: `<memory>`. Daha fazla bilgi için bkz: [nasıl yapılır: unique_ptr örnekleri oluşturma ve kullanma](../cpp/how-to-create-and-use-unique-ptr-instances.md) ve [unique_ptr sınıfı](../standard-library/unique-ptr-class.md).  
  
-   `shared_ptr`   
     Başvuru sayımı olan akıllı işaretçi. Birden fazla sahibe tek bir ham işaretçi atamak istediğinizde kullanın, örnek olarak bir kapsayıcıdan işaretçi kopyası döndürüp orijinalini saklamak istediğinizde kullanın. Ham işaretçi tüm kadar silinmez `shared_ptr` sahipler fazlası kapsam dışında veya aksi halde sahipliği verdiğiniz. Boyut iki işaretçi kadardır; biri nesne için ve biri başvuru sayısını içeren paylaşılan denetim bloğu için. Üstbilgi dosyası: `<memory>`. Daha fazla bilgi için bkz: [nasıl yapılır: shared_ptr örnekleri oluşturma ve kullanma](../cpp/how-to-create-and-use-shared-ptr-instances.md) ve [shared_ptr sınıfı](../standard-library/shared-ptr-class.md).  
  
-   `weak_ptr`   
    Özel durum akıllı işaretçisi ile birlikte kullanmak için `shared_ptr`. A `weak_ptr` bir veya daha fazla ait bir nesneye erişimi sağlayan `shared_ptr` örnekler, ancak başvuru sayımı katılmıyor. Bir nesneyi görmek istiyorsanız ancak canlı kalmasını istemiyorsanız kullanın. Bazı durumlarda arasında dairesel başvurular ayırmak için gerekli `shared_ptr` örnekleri. Üstbilgi dosyası: `<memory>`. Daha fazla bilgi için bkz: [nasıl yapılır: weak_ptr örnekleri oluşturma ve kullanma](../cpp/how-to-create-and-use-weak-ptr-instances.md) ve [weak_ptr sınıfı](../standard-library/weak-ptr-class.md).  
  
 **COM nesneleri (Klasik Windows programlama) için akıllı işaretçiler**  
 COM nesneleriyle çalışırken, arabirim işaretçilerini uygun akıllı işaretçi türüne sarın. Etkin Şablon Kitaplığı (ATL) çeşitli amaçlar için birçok akıllı işaretçi tanımlar. Aynı zamanda `_com_ptr_t` .tlb dosyaları sarmalayıcı sınıflar oluşturduğunda, derleyici kullanan akıllı işaretçi türü. ATL üstbilgi dosyalarını eklemek istemediğinizde en iyi seçenektir.  
  
 [CComPtr Sınıfı](../atl/reference/ccomptr-class.md)  
 ATL kullanabiliyorsanız bunu kullanın. Başvuru kullanarak sayım gerçekleştirir `AddRef` ve `Release` yöntemleri. Daha fazla bilgi için bkz: [nasıl yapılır: oluşturmak ve kullanım CComPtr ve CComQIPtr örnekleri](../cpp/how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md).  
  
 [CComQIPtr Sınıfı](../atl/reference/ccomqiptr-class.md)  
 Benzer `CComPtr` ancak aynı zamanda çağırmak için Basitleştirilmiş söz dizimi sağlar `QueryInterface` COM nesnelerinde. Daha fazla bilgi için bkz: [nasıl yapılır: oluşturmak ve kullanım CComPtr ve CComQIPtr örnekleri](../cpp/how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md).  
  
 [CComHeapPtr Sınıfı](../atl/reference/ccomheapptr-class.md)  
 Nesnelerin akıllı işaretçi `CoTaskMemFree` belleği boşaltmak için.  
  
 [CComGITPtr Sınıfı](../atl/reference/ccomgitptr-class.md)  
 Genel arabirim tablosundan (GIT) alınan arabirimler için akıllı işaretçi.  
  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)  
 Benzer `CComQIPtr` işlev ATL üstbilgilerinde bağlı değildir ancak.  
  
 **ATL POCO nesneler için akıllı işaretçiler**  
 COM nesneleri için akıllı işaretçilere ek olarak, ATL aynı zamanda düz ve eski C++ nesnelerinde akıllı işaretçileri ve koleksiyonlarını tanımlar. Klasik Windows programlamada bu C++ Standart Kitaplığı koleksiyonları yararlı alternatifleri özellikle kod taşınabilirlik gerekli olmadığında veya programlama modelleri C++ Standart Kitaplığı ve ATL karışık istemediğinizde türleridir  
  
 [CAutoPtr Sınıfı](../atl/reference/cautoptr-class.md)  
 Sahipliği bir kopyaya aktararak benzersiz sahipliği zorlayan akıllı işaretçi. Kullanım dışı için karşılaştırılabilir `std::auto_ptr` sınıfı.  
  
 [CHeapPtr Sınıfı](../atl/reference/cheapptr-class.md)  
 C kullanarak ayrılmış nesneleri için akıllı işaretçi [malloc](../c-runtime-library/reference/malloc.md) işlevi.  
  
 [CAutoVectorPtr Sınıfı](../atl/reference/cautovectorptr-class.md)  
 Kullanarak ayrılan diziler için akıllı işaretçi `new[]`.  
  
 [CAutoPtrArray Sınıfı](../atl/reference/cautoptrarray-class.md)  
 Bir dizi yalıtır sınıfı `CAutoPtr` öğeleri.  
  
 [CAutoPtrList Sınıfı](../atl/reference/cautoptrlist-class.md)  
 Listesini yönetmek için yöntemler yalıtır sınıfı `CAutoPtr` düğümleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)   
