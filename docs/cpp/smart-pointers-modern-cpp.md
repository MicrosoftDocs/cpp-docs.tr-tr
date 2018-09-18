---
title: Akıllı işaretçiler (Modern C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 909ef870-904c-49b6-b8cd-e9d0b7dc9435
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2710609cbf20861c77dae1cb0aea327983efef6e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098179"
---
# <a name="smart-pointers-modern-c"></a>Akıllı İşaretçiler (Modern C++)

Modern C++ programlamada standart kitaplık içeren *akıllı işaretçileri*, hangi programları sağlamak için kullanılan bellek ve kaynak sızıntıları ve özel durum açısından güvenli olmalarını.

## <a name="uses-for-smart-pointers"></a>Akıllı işaretçiler için kullanım alanları

Akıllı işaretçiler tanımlanmış `std` ad alanında [ \<bellek >](../standard-library/memory.md) üst bilgi dosyası. Bunlar çok önemlidir [RAII](../cpp/objects-own-resources-raii.md) veya *olduğu kaynak alımı başlatma* programlama deyimi. Bu deyimin ana amacı, kaynak alımının nesnenin başlatılmasıyla aynı anda gerçekleşmesini sağlamaktır; böylece nesne için tüm kaynaklar bir kod satırında oluşturulur ve hazır hale getirilir. Pratikte temel RAII prensibi, yığın tarafından ayrılan herhangi bir kaynağın sahipliğini örneğin, dinamik olarak ayrılan belek veya sistem nesnesi tanıtıcıları, yok edicisi kaynağı silmek veya boşaltmak için gereken kodu ve herhangi bir temizleme kodunu içeren ve yığın tarafından ayrılan bir nesneye vermektir.

Çoğu durumda gerçek bir kaynağı işaret etmek ve işaretçiyi hemen bir akıllı işaretçiye dönüştürmek için bir ham işaretçi veya kaynak tanıtıcısı kullanırsınız. Modern C++ programlamada, ham işaretçiler yalnızca performansın önemli olduğu ve sahiplik konusunda karışıklık olma ihtimali bulunmayan kapsam, döngü veya yardımcı işlevler açısından sınırlı olan küçük kod engellerinde kullanılır.

Aşağıdaki örnek, bir ham işaretçi bildirimini bir akıllı işaretçi bildirimi ile karşılaştırır.

[!code-cpp[smart_pointers_intro#1](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_1.cpp)]

Akıllı işaretçi, örnekte gösterildiği gibi, yığında bildirdiğiniz ve yığın tarafından ayrılan nesneyi gösteren ham işaretçiyi kullanarak başlattığınız bir sınıf şablonudur. Akıllı işaretçi başlatıldıktan sonra ham işaretçiyi üstlenir. Bu, akıllı işaretçinin, ham işaretçinin belirttiği belleği silmekten sorumlu olduğu anlamına gelir. Akıllı işaretçi yok edici silinecek çağrıyı içerir ve akıllı işaretçi yığında bildirildiğinden, akıllı işaretçi kapsam dışına çıktığında, yığının daha ileri bir yerinde bir özel durum olsa bile, yok edicisi çağrılır.

Benzer işaretçi işleçlerini kullanarak kapsüllenmiş işaretçiye erişin `->` ve `*`, akıllı işaretçi sınıfının kapsüllenmiş ham işaretçiyi döndürmek için aşırı yüklediği.

C++ akıllı işaretçi deyimi, C# gibi dillerde nesne oluşturmaya benzer: Nesneyi oluşturursunuz ve ardından sistemin doğru zamanda bunu silmesine izin verirsiniz. Fark arka planda ayrı bir çöp toplayıcının çalışmamasıdır; bellek standart C++ kapsama kuralları ile yönetilir, bu nedenle çalışma zamanı ortamı daha hızlı ve daha verimlidir.

> [!IMPORTANT]
>  Akıllı işaretçileri, asla parametre listesinde değil, her zaman ayrı bir kod satırında oluşturun, böylece belli parametre listesi ayırma kuralları nedeniyle küçük kaynak sızıntıları meydana gelmesine engel olursunuz.

Aşağıdaki örnekte gösterildiği nasıl bir `unique_ptr` C++ Standart Kitaplığı'ndan akıllı işaretçisi türünün, büyük bir nesneye bir işaretçi kapsüllemek için kullanılabilir.

[!code-cpp[smart_pointers_intro#2](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_2.cpp)]

Örnek akıllı işaretçileri kullanmak için aşağıdaki temel adımları gösterir.

1. Akıllı işaretçiyi otomatik bir (yerel) değişken olarak bildirin. (Kullanmayın **yeni** veya `malloc` ifade akıllı işaretçinin kendisinde.)

1. Tür parametresinde kapsüllenen işaretçinin, işaret edilen türünü belirtin.

1. Ham bir işaretçiyi bir **yeni**-akıllı işaretçi Oluşturucudaki nesne. (Bazı yardımcı program işlevleri veya akıllı işaretçi oluşturucuları bunu sizin için yapar.)

1. Aşırı yüklenen kullanın `->` ve `*` işleçlerini nesnelere erişmek üzere.

1. Akıllı işaretçinin nesneyi silmesine izin verin.

Akıllı işaretçiler bellek ve performans açısından mümkün olduğunda verimli olmak için tasarlanmıştır. Örneğin, yalnızca veri üyesi `unique_ptr` öğesi kapsüllenmiş bir işaretçidir. Diğer bir deyişle `unique_ptr` , dört bayt veya sekiz bayt işaretçiyle tam olarak aynı boyutta olan. Aşırı yüklendiği akıllı işaretçiyi kullanarak kapsüllenmiş işaretçiye erişim * ve -> işleçlerinin doğrudan ham işaretçiyle erişim daha önemli ölçüde yavaş değildir.

Akıllı işaretçilerin “dot” belirtimi kullanılarak erişilen kendi üye işlevleri vardır. Örneğin, bazı C++ Standart Kitaplığı akıllı işaretçilerin işaretçi sahipliğini serbest bir sıfırlama üye işlevi vardır. Bu, aşağıdaki örnekte gösterildiği şekilde akıllı işaretçi kapsam dışında çıkmadan önce akıllı işaretçinin sahip olduğu belleği boşaltmak istediğinizde yararlıdır.

[!code-cpp[smart_pointers_intro#3](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_3.cpp)]

Akıllı işaretçiler genelde ham işaretçilerine doğrudan erişmek için bir yol sağlar. C++ Standart Kitaplığı akıllı işaretçileri bir `get` üye işlev bu amaçla ve `CComPtr` bir ortak sahip `p` sınıf üyesi. Temel alınan işaretçiye doğrudan erişim sağladığınızda, akıllı işaretçiyi kendi kodunuzla bellek yönetmek amacıyla kullanırken, ham işaretçiyi de hala akıllı işaretçileri desteklemeyen koda geçirebilirsiniz.

[!code-cpp[smart_pointers_intro#4](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_4.cpp)]

## <a name="kinds-of-smart-pointers"></a>Akıllı İşaretçi Türleri

Aşağıdaki bölümde Windows programlama ortamında bulunan farklı türden akıllı işaretçiler özetlenir ve bunların ne zaman kullanılacağı açıklanır.

### <a name="c-standard-library-smart-pointers"></a>C++ Standart Kitaplığı akıllı işaretçiler

Bu akıllı işaretçileri eski C++ nesnelerine (POCO) işaretçi kapsüllemek için ilk seçenek olarak kullanın.

- `unique_ptr` Temel işaretçisinin tam olarak bir sahibi sağlar. İhtiyacınız olan belirli bilmiyorsanız varsayılan seçenek olarak değilseniz POCO için kullanmak bir `shared_ptr`. Bir yeni kullanıcıya taşınabilir, ancak kopyalanamaz veya paylaşılamaz. Değiştirir `auto_ptr`, kullanım dışı. Karşılaştırılacak `boost::scoped_ptr`. `unique_ptr` küçük ve verimli değildir; boyutu bir işaretçidir ve hızlı ekleme ve C++ Standart Kitaplığı koleksiyonu alma için rvalue başvurularını destekler. Üst bilgi dosyası: `<memory>`. Daha fazla bilgi için [nasıl yapılır: unique_ptr örnekleri oluşturma ve kullanma](../cpp/how-to-create-and-use-unique-ptr-instances.md) ve [unique_ptr sınıfı](../standard-library/unique-ptr-class.md).

- `shared_ptr` Başvuru sayılan akıllı işaretçi. Birden fazla sahibe tek bir ham işaretçi atamak istediğinizde kullanın, örnek olarak bir kapsayıcıdan işaretçi kopyası döndürüp orijinalini saklamak istediğinizde kullanın. Ham işaretçiyi tüm kadar silinmez `shared_ptr` sahipleri kapsam dışında çıkmadan veya aksi halde. Boyut iki işaretçi kadardır; biri nesne için ve biri başvuru sayısını içeren paylaşılan denetim bloğu için. Üst bilgi dosyası: `<memory>`. Daha fazla bilgi için [nasıl yapılır: shared_ptr örnekleri oluşturma ve kullanma](../cpp/how-to-create-and-use-shared-ptr-instances.md) ve [shared_ptr sınıfı](../standard-library/shared-ptr-class.md).

- `weak_ptr` Özel durum akıllı işaretçisi ile kullanılmak üzere `shared_ptr`. A `weak_ptr` bir veya daha fazla sahip olduğu bir nesneye erişim sağlar `shared_ptr` örnekler, ancak başvuru sayımına değil. Bir nesneyi görmek istiyorsanız ancak canlı kalmasını istemiyorsanız kullanın. Bazı durumlarda arasındaki döngüsel başvuruları bölmek için gereken `shared_ptr` örnekleri. Üst bilgi dosyası: `<memory>`. Daha fazla bilgi için [nasıl yapılır: weak_ptr örnekleri oluşturma ve kullanma](../cpp/how-to-create-and-use-weak-ptr-instances.md) ve [weak_ptr sınıfı](../standard-library/weak-ptr-class.md).

### <a name="smart-pointers-for-com-objects-classic-windows-programming"></a>{1&gt;COM Nesneleri (Klasik Windows Programlama) için Akıllı İşaretçiler&lt;1}

COM nesneleriyle çalışırken, arabirim işaretçilerini uygun akıllı işaretçi türüne sarın. Etkin Şablon Kitaplığı (ATL) çeşitli amaçlar için birçok akıllı işaretçi tanımlar. Ayrıca `_com_ptr_t` .tlb dosyalarından sarmalayıcı sınıflar oluşturduğunda, derleyicinin kullandığı akıllı işaretçi türü. ATL üstbilgi dosyalarını eklemek istemediğinizde en iyi seçenektir.

[CComPtr sınıfı](../atl/reference/ccomptr-class.md) ATL kullanabiliyorsanız bunu kullanın. Kullanarak başvuru sayımı gerçekleştirir `AddRef` ve `Release` yöntemleri. Daha fazla bilgi için [nasıl yapılır: oluşturma ve kullanım CComPtr ve CComQIPtr örnekleri](../cpp/how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md).

[CComQIPtr sınıfı](../atl/reference/ccomqiptr-class.md) Resembles `CComPtr` arama için Basitleştirilmiş söz dizimi sağlar `QueryInterface` COM nesnelerinde. Daha fazla bilgi için [nasıl yapılır: oluşturma ve kullanım CComPtr ve CComQIPtr örnekleri](../cpp/how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md).

[CComHeapPtr sınıfı](../atl/reference/ccomheapptr-class.md) kullanan nesneler için akıllı işaretçi `CoTaskMemFree` belleği boşaltmak için.

[Ccomgıtptr sınıfı](../atl/reference/ccomgitptr-class.md) genel arabirim tablosundan (GIT) alınan arabirimler için akıllı işaretçi.

[_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md) Resembles `CComQIPtr` işlev ancak ATL üstbilgilerine benzemez.

### <a name="atl-smart-pointers-for-poco-objects"></a>{1&gt;POCO Nesneleri için ATL Akıllı İşaretçiler&lt;1}

COM nesneleri için akıllı işaretçilere ek olarak, ATL aynı zamanda düz ve eski C++ nesnelerinde akıllı işaretçileri ve koleksiyonlarını tanımlar. Klasik Windows programlamada, özellikle kod taşınabilirliği gerekli olmadığında veya C++ Standart Kitaplığı ve ATL programlama modellerini karıştırmak istemediğinizde bu türler C++ Standart Kitaplığı koleksiyon için kullanışlı alternatiflerdir olan

[CAutoPtr sınıfı](../atl/reference/cautoptr-class.md) sahipliği bir kopyaya aktararak benzersiz sahipliği zorlayan akıllı işaretçi. Kullanım dışı karşılaştırılabilir `std::auto_ptr` sınıfı.

[CHeapPtr sınıfı](../atl/reference/cheapptr-class.md) C kullanılarak atanan nesneler için akıllı işaretçi [malloc](../c-runtime-library/reference/malloc.md) işlevi.

[CAutoVectorPtr sınıfı](../atl/reference/cautovectorptr-class.md) kullanılarak atanan diziler için akıllı işaretçi `new[]`.

[CAutoPtrArray sınıfı](../atl/reference/cautoptrarray-class.md) dizisi kapsülleyen sınıftır `CAutoPtr` öğeleri.

[CAutoPtrList sınıfı](../atl/reference/cautoptrlist-class.md) listesini yönlendirmeye yönelik yöntemleri kapsülleyen sınıftır `CAutoPtr` düğümleri.

## <a name="see-also"></a>Ayrıca bkz.

[C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)