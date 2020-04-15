---
title: Akıllı işaretçiler (Modern C++)
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 909ef870-904c-49b6-b8cd-e9d0b7dc9435
ms.openlocfilehash: 0e93ce033649f5654595ae23a5f10da347879718
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365545"
---
# <a name="smart-pointers-modern-c"></a>Akıllı işaretçiler (Modern C++)

Standart Kitaplık, modern C++ programlamasında, programların bellek ve kaynak sızıntılarından arındırılmış ve özel durum açısından güvenli olmasını sağlamaya yardımcı olmak için kullanılan *akıllı işaretçiler*içerir.

## <a name="uses-for-smart-pointers"></a>Akıllı işaretçiler için kullanım alanları

Akıllı [ \<işaretçiler,](../standard-library/memory.md) bellek `std`>üstbilgi dosyasındaki ad alanında tanımlanır. Bunlar [RAII](objects-own-resources-raii.md) veya Kaynak *Edinimi* için çok önemlidir Başlatma programlama deyimidir. Bu deyimin ana amacı, kaynak alımının nesnenin başlatılmasıyla aynı anda gerçekleşmesini sağlamaktır; böylece nesne için tüm kaynaklar bir kod satırında oluşturulur ve hazır hale getirilir. Pratikte temel RAII prensibi, yığın tarafından ayrılan herhangi bir kaynağın sahipliğini örneğin, dinamik olarak ayrılan belek veya sistem nesnesi tanıtıcıları, yok edicisi kaynağı silmek veya boşaltmak için gereken kodu ve herhangi bir temizleme kodunu içeren ve yığın tarafından ayrılan bir nesneye vermektir.

Çoğu durumda gerçek bir kaynağı işaret etmek ve işaretçiyi hemen bir akıllı işaretçiye dönüştürmek için bir ham işaretçi veya kaynak tanıtıcısı kullanırsınız. Modern C++ programlamada, ham işaretçiler yalnızca performansın önemli olduğu ve sahiplik konusunda karışıklık olma ihtimali bulunmayan kapsam, döngü veya yardımcı işlevler açısından sınırlı olan küçük kod engellerinde kullanılır.

Aşağıdaki örnek, bir ham işaretçi bildirimini bir akıllı işaretçi bildirimi ile karşılaştırır.

[!code-cpp[smart_pointers_intro#1](codesnippet/CPP/smart-pointers-modern-cpp_1.cpp)]

Akıllı işaretçi, örnekte gösterildiği gibi, yığında bildirdiğiniz ve yığın tarafından ayrılan nesneyi gösteren ham işaretçiyi kullanarak başlattığınız bir sınıf şablonudur. Akıllı işaretçi başlatıldıktan sonra ham işaretçiyi üstlenir. Bu, akıllı işaretçinin, ham işaretçinin belirttiği belleği silmekten sorumlu olduğu anlamına gelir. Akıllı işaretçi yok edici silinecek çağrıyı içerir ve akıllı işaretçi yığında bildirildiğinden, akıllı işaretçi kapsam dışına çıktığında, yığının daha ileri bir yerinde bir özel durum olsa bile, yok edicisi çağrılır.

Tanıdık işaretçi işleçlerini kullanarak kapsüllenmiş `->` `*`işaretçiye erişin ve akıllı işaretçi sınıfı kapsüllenmiş ham işaretçiyi döndürmek için aşırı yüklenir.

C++ akıllı işaretçi deyimi, C# gibi dillerde nesne oluşturmaya benzer: Nesneyi oluşturursunuz ve ardından sistemin doğru zamanda bunu silmesine izin verirsiniz. Fark arka planda ayrı bir çöp toplayıcının çalışmamasıdır; bellek standart C++ kapsama kuralları ile yönetilir, bu nedenle çalışma zamanı ortamı daha hızlı ve daha verimlidir.

> [!IMPORTANT]
> Akıllı işaretçileri, asla parametre listesinde değil, her zaman ayrı bir kod satırında oluşturun, böylece belli parametre listesi ayırma kuralları nedeniyle küçük kaynak sızıntıları meydana gelmesine engel olursunuz.

Aşağıdaki örnek, C++ Standart Kitaplığı'ndan bir `unique_ptr` akıllı işaretçi türünün büyük bir nesneye işaretçi kapsüllemek için nasıl kullanılabileceğini gösterir.

[!code-cpp[smart_pointers_intro#2](codesnippet/CPP/smart-pointers-modern-cpp_2.cpp)]

Örnek akıllı işaretçileri kullanmak için aşağıdaki temel adımları gösterir.

1. Akıllı işaretçiyi otomatik bir (yerel) değişken olarak bildirin. (Akıllı işaretçiüzerinde `malloc` **yeni** veya ifade kullanmayın.)

1. Tür parametresinde kapsüllenen işaretçinin, işaret edilen türünü belirtin.

1. Ham bir işaretçiyi akıllı işaretçi oluşturucuda **yeni**bir -ed nesnesine geçirin. (Bazı yardımcı program işlevleri veya akıllı işaretçi oluşturucuları bunu sizin için yapar.)

1. Nesneye erişmek `->` `*` için aşırı yüklenen ve işleçleri kullanın.

1. Akıllı işaretçinin nesneyi silmesine izin verin.

Akıllı işaretçiler bellek ve performans açısından mümkün olduğunda verimli olmak için tasarlanmıştır. Örneğin, tek `unique_ptr` veri üyesi kapsüllenmiş işaretçidir. Bu, `unique_ptr` işaretçiyle tam olarak aynı boyutta olduğu anlamına gelir, dört bayt veya sekiz bayt. * ve -> işleçleri aşırı yüklenen akıllı işaretçi kullanarak kapsüllenmiş işaretçi erişim önemli ölçüde ham işaretçiler doğrudan erişme daha yavaş değildir.

Akıllı işaretçilerin kendi üye işlevleri vardır ve bu işlevlere "nokta" gösterimi kullanılarak erişilir. Örneğin, bazı C++ Standart Kitaplık akıllı işaretçileri, işaretçinin sahipliğini serbest bırakan bir sıfırlama üye işlevine sahiptir. Bu, aşağıdaki örnekte gösterildiği şekilde akıllı işaretçi kapsam dışında çıkmadan önce akıllı işaretçinin sahip olduğu belleği boşaltmak istediğinizde yararlıdır.

[!code-cpp[smart_pointers_intro#3](codesnippet/CPP/smart-pointers-modern-cpp_3.cpp)]

Akıllı işaretçiler genelde ham işaretçilerine doğrudan erişmek için bir yol sağlar. C++ Standart Kitaplık akıllı `get` işaretçileri bu `CComPtr` amaç için `p` bir üye işlevine sahiptir ve ortak sınıf üyesi vardır. Temel alınan işaretçiye doğrudan erişim sağladığınızda, akıllı işaretçiyi kendi kodunuzla bellek yönetmek amacıyla kullanırken, ham işaretçiyi de hala akıllı işaretçileri desteklemeyen koda geçirebilirsiniz.

[!code-cpp[smart_pointers_intro#4](codesnippet/CPP/smart-pointers-modern-cpp_4.cpp)]

## <a name="kinds-of-smart-pointers"></a>Akıllı işaretçiler in türleri

Aşağıdaki bölümde Windows programlama ortamında bulunan farklı türden akıllı işaretçiler özetlenir ve bunların ne zaman kullanılacağı açıklanır.

### <a name="c-standard-library-smart-pointers"></a>C++ Standart Kitaplık akıllı işaretçileri

Bu akıllı işaretçileri eski C++ nesnelerine (POCO) işaretçi kapsüllemek için ilk seçenek olarak kullanın.

- `unique_ptr`<br/>
   Temel alınan işaretçi için, kesin olarak tek bir sahibe izin verir. Poco için varsayılan seçenek olarak `shared_ptr`kullanın. Bir yeni kullanıcıya taşınabilir, ancak kopyalanamaz veya paylaşılamaz. `auto_ptr`Deprecated olan değiştirir. Karşılaştırın. `boost::scoped_ptr` `unique_ptr`küçük ve verimlidir; boyutu bir işaretçidir ve C++ Standart Kitaplık koleksiyonlarından hızlı ekleme ve alma için rvalue başvurularını destekler. Üstbilgi dosyası: `<memory>`. Daha fazla bilgi için [bkz: Nasıl: Unique_ptr Örnekleri ve](how-to-create-and-use-unique-ptr-instances.md) [unique_ptr Sınıfı](../standard-library/unique-ptr-class.md)oluşturma ve kullanma.

- `shared_ptr`<br/>
   Başvuru sayımı olan akıllı işaretçi. Birden fazla sahibe tek bir ham işaretçi atamak istediğinizde kullanın, örnek olarak bir kapsayıcıdan işaretçi kopyası döndürüp orijinalini saklamak istediğinizde kullanın. Ham işaretçi, tüm `shared_ptr` sahipler kapsam dışına çıkana veya başka bir şekilde sahiplenmeden vazgeçene kadar silinmez. Boyut iki işaretçi kadardır; biri nesne için ve biri başvuru sayısını içeren paylaşılan denetim bloğu için. Üstbilgi dosyası: `<memory>`. Daha fazla bilgi için [bkz: Nasıl: Shared_ptr Örnekleri ve](how-to-create-and-use-shared-ptr-instances.md) [shared_ptr Sınıfı](../standard-library/shared-ptr-class.md)Oluşturun ve Kullanın.

- `weak_ptr`<br/>
    Özel durum akıllı işaretçisi `shared_ptr`ile birlikte kullanılmak üzere. A, `weak_ptr` bir veya daha fazla `shared_ptr` örneğin sahip olduğu, ancak başvuru sayımına katılmayan bir nesneye erişim sağlar. Bir nesneyi görmek istiyorsanız ancak canlı kalmasını istemiyorsanız kullanın. Bazı durumlarda, örnekler arasında `shared_ptr` dairesel başvuruları kırmak için gereklidir. Üstbilgi dosyası: `<memory>`. Daha fazla bilgi için [bkz: Nasıl: Weak_ptr Örnekleri oluşturma ve kullanma](how-to-create-and-use-weak-ptr-instances.md) ve weak_ptr [Sınıf.](../standard-library/weak-ptr-class.md)

### <a name="smart-pointers-for-com-objects-classic-windows-programming"></a>COM nesneleri için akıllı işaretçiler (klasik Windows programlama)

COM nesneleriyle çalışırken, arabirim işaretçilerini uygun akıllı işaretçi türüne sarın. Etkin Şablon Kitaplığı (ATL) çeşitli amaçlar için birçok akıllı işaretçi tanımlar. Derleyicinin `_com_ptr_t` .tlb dosyalarından sarıcı sınıfları oluştururken kullandığı akıllı işaretçi türünü de kullanabilirsiniz. ATL üstbilgi dosyalarını eklemek istemediğinizde en iyi seçenektir.

[CComPtr Sınıfı](../atl/reference/ccomptr-class.md)<br/>
ATL kullanabiliyorsanız bunu kullanın. Referans sayma ve `AddRef` `Release` yöntemleri kullanarak gerçekleştirir. Daha fazla bilgi için [bkz: CComPtr ve CComQIPtr Örnekleri oluşturun ve kullanın.](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md)

[CComQIPtr Sınıfı](../atl/reference/ccomqiptr-class.md)<br/>
Benzer `CComPtr` ama aynı zamanda COM nesneleri `QueryInterface` aramak için basitleştirilmiş sözdizimi sağlar. Daha fazla bilgi için [bkz: CComPtr ve CComQIPtr Örnekleri oluşturun ve kullanın.](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md)

[CComHeapPtr Sınıfı](../atl/reference/ccomheapptr-class.md)<br/>
Boş bellek için kullanılan `CoTaskMemFree` nesneleriçin akıllı işaretçi.

[CComGITPtr Sınıfı](../atl/reference/ccomgitptr-class.md)<br/>
Genel arabirim tablosundan (GIT) alınan arabirimler için akıllı işaretçi.

[_com_ptr_t Sınıfı](com-ptr-t-class.md)<br/>
İşlevsellik te benzer, `CComQIPtr` ancak ATL üstbilgilerine bağlı değildir.

### <a name="atl-smart-pointers-for-poco-objects"></a>POCO nesneleri için ATL akıllı işaretçiler

COM nesneleri için akıllı işaretçilere ek olarak, ATL, düz eski C++ nesneleri (POCO) için akıllı işaretçileri ve akıllı işaretçilerin koleksiyonlarını da tanımlar. Klasik Windows programlamada, bu tür c++ Standart Kitaplığı koleksiyonlarına, özellikle kod taşınabilirliği gerekli olmadığında veya C++ Standart Kitaplığı ve ATL programlama modellerini karıştırmak istemediğinde yararlı alternatiflerdir.

[CAutoPtr Sınıfı](../atl/reference/cautoptr-class.md)<br/>
Sahipliği bir kopyaya aktararak benzersiz sahipliği zorlayan akıllı işaretçi. Amortismana uymulan `std::auto_ptr` sınıfla karşılaştırılabilir.

[CHeapPtr Sınıfı](../atl/reference/cheapptr-class.md)<br/>
C [malloc](../c-runtime-library/reference/malloc.md) işlevi kullanılarak ayrılan nesneler için akıllı işaretçi.

[CAutoVectorPtr Sınıfı](../atl/reference/cautovectorptr-class.md)<br/>
Kullanılarak `new[]`ayrılan diziler için akıllı işaretçi.

[CAutoPtrArray Sınıfı](../atl/reference/cautoptrarray-class.md)<br/>
Bir dizi öğeyi kapsülleyen `CAutoPtr` sınıf.

[CAutoPtrList Sınıfı](../atl/reference/cautoptrlist-class.md)<br/>
Düğüm listesini işlemek için yöntemleri kapsülleyen sınıf. `CAutoPtr`

## <a name="see-also"></a>Ayrıca bkz.

[İşaretçiler](pointers-cpp.md)<br/>
[C++ Dil Referansı](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplık](../standard-library/cpp-standard-library-reference.md)
