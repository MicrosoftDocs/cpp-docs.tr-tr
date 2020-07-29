---
title: Akıllı işaretçiler (Modern C++)
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 909ef870-904c-49b6-b8cd-e9d0b7dc9435
ms.openlocfilehash: 698843ced3235d9622af3610a5209669407e9e05
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186145"
---
# <a name="smart-pointers-modern-c"></a>Akıllı işaretçiler (Modern C++)

Modern C++ programlamada standart kitaplık, programların bellek ve kaynak sızıntılarını boşaltmasını ve özel durum açısından güvenli olmasını sağlamaya yardımcı olmak için kullanılan *akıllı işaretçiler*içerir.

## <a name="uses-for-smart-pointers"></a>Akıllı işaretçiler için kullanım alanları

Akıllı işaretçiler, `std` üstbilgi dosyasındaki ad alanında tanımlanır [\<memory>](../standard-library/memory.md) . Bu, [Aİİ](objects-own-resources-raii.md) veya *kaynak alımı* için çok önemlidir. Bu deyimin ana amacı, kaynak alımının nesnenin başlatılmasıyla aynı anda gerçekleşmesini sağlamaktır; böylece nesne için tüm kaynaklar bir kod satırında oluşturulur ve hazır hale getirilir. Pratikte temel RAII prensibi, yığın tarafından ayrılan herhangi bir kaynağın sahipliğini örneğin, dinamik olarak ayrılan belek veya sistem nesnesi tanıtıcıları, yok edicisi kaynağı silmek veya boşaltmak için gereken kodu ve herhangi bir temizleme kodunu içeren ve yığın tarafından ayrılan bir nesneye vermektir.

Çoğu durumda gerçek bir kaynağı işaret etmek ve işaretçiyi hemen bir akıllı işaretçiye dönüştürmek için bir ham işaretçi veya kaynak tanıtıcısı kullanırsınız. Modern C++ programlamada, ham işaretçiler yalnızca performansın önemli olduğu ve sahiplik konusunda karışıklık olma ihtimali bulunmayan kapsam, döngü veya yardımcı işlevler açısından sınırlı olan küçük kod engellerinde kullanılır.

Aşağıdaki örnek, bir ham işaretçi bildirimini bir akıllı işaretçi bildirimi ile karşılaştırır.

[!code-cpp[smart_pointers_intro#1](codesnippet/CPP/smart-pointers-modern-cpp_1.cpp)]

Akıllı işaretçi, örnekte gösterildiği gibi, yığında bildirdiğiniz ve yığın tarafından ayrılan nesneyi gösteren ham işaretçiyi kullanarak başlattığınız bir sınıf şablonudur. Akıllı işaretçi başlatıldıktan sonra ham işaretçiyi üstlenir. Bu, akıllı işaretçinin, ham işaretçinin belirttiği belleği silmekten sorumlu olduğu anlamına gelir. Akıllı işaretçi yok edici silinecek çağrıyı içerir ve akıllı işaretçi yığında bildirildiğinden, akıllı işaretçi kapsam dışına çıktığında, yığının daha ileri bir yerinde bir özel durum olsa bile, yok edicisi çağrılır.

Tanıdık işaretçi işleçlerini kullanarak kapsüllenmiş işaretçiye erişin `->` ve `*` akıllı işaretçi sınıfının kapsüllenmiş ham işaretçiyi döndürmek için aşırı yüklerini kullanın.

C++ akıllı işaretçi deyimi, C# gibi dillerde nesne oluşturmaya benzer: Nesneyi oluşturursunuz ve ardından sistemin doğru zamanda bunu silmesine izin verirsiniz. Fark arka planda ayrı bir çöp toplayıcının çalışmamasıdır; bellek standart C++ kapsama kuralları ile yönetilir, bu nedenle çalışma zamanı ortamı daha hızlı ve daha verimlidir.

> [!IMPORTANT]
> Akıllı işaretçileri, asla parametre listesinde değil, her zaman ayrı bir kod satırında oluşturun, böylece belli parametre listesi ayırma kuralları nedeniyle küçük kaynak sızıntıları meydana gelmesine engel olursunuz.

Aşağıdaki örnek, `unique_ptr` C++ standart kitaplığı 'ndan bir akıllı işaretçi türünün, büyük bir nesne işaretçisini kapsüllemek için nasıl kullanılabileceğini gösterir.

[!code-cpp[smart_pointers_intro#2](codesnippet/CPP/smart-pointers-modern-cpp_2.cpp)]

Örnek akıllı işaretçileri kullanmak için aşağıdaki temel adımları gösterir.

1. Akıllı işaretçiyi otomatik bir (yerel) değişken olarak bildirin. ( **`new`** `malloc` Akıllı işaretçinin kendisinde or ifadesini kullanmayın.)

1. Tür parametresinde kapsüllenen işaretçinin, işaret edilen türünü belirtin.

1. Akıllı işaretçi oluşturucusunda, bir ham işaretçiyi bir to **`new`** Ed nesnesine geçirin. (Bazı yardımcı program işlevleri veya akıllı işaretçi oluşturucuları bunu sizin için yapar.)

1. `->` `*` Nesneye erişmek için aşırı yüklenmiş ve işleçleri kullanın.

1. Akıllı işaretçinin nesneyi silmesine izin verin.

Akıllı işaretçiler bellek ve performans açısından mümkün olduğunda verimli olmak için tasarlanmıştır. Örneğin, içindeki tek veri üyesi `unique_ptr` kapsüllenmiş işaretçisidir. Bu, `unique_ptr` dört bayt veya sekiz bayt olmak üzere bu işaretçi ile tam olarak aynı boyutta olduğu anlamına gelir. Akıllı işaretçi kullanılarak kapsüllenmiş işaretçiye erişmek * ve-> işleçleri ham işaretçilere doğrudan erişmekten önemli ölçüde yavaştır.

Akıllı işaretçilerin "nokta" gösterimi kullanılarak erişilen kendi üye işlevleri vardır. Örneğin, bazı C++ standart kitaplığı akıllı işaretçilerin, işaretçinin sahipliğini serbest bırakma bir sıfırlama üye işlevi vardır. Bu, aşağıdaki örnekte gösterildiği şekilde akıllı işaretçi kapsam dışında çıkmadan önce akıllı işaretçinin sahip olduğu belleği boşaltmak istediğinizde yararlıdır.

[!code-cpp[smart_pointers_intro#3](codesnippet/CPP/smart-pointers-modern-cpp_3.cpp)]

Akıllı işaretçiler genelde ham işaretçilerine doğrudan erişmek için bir yol sağlar. C++ standart kitaplığı akıllı işaretçilerinin `get` Bu amaçla bir üye işlevi vardır ve `CComPtr` bir ortak `p` sınıf üyesine sahiptir. Temel alınan işaretçiye doğrudan erişim sağladığınızda, akıllı işaretçiyi kendi kodunuzla bellek yönetmek amacıyla kullanırken, ham işaretçiyi de hala akıllı işaretçileri desteklemeyen koda geçirebilirsiniz.

[!code-cpp[smart_pointers_intro#4](codesnippet/CPP/smart-pointers-modern-cpp_4.cpp)]

## <a name="kinds-of-smart-pointers"></a>Akıllı işaretçi türleri

Aşağıdaki bölümde Windows programlama ortamında bulunan farklı türden akıllı işaretçiler özetlenir ve bunların ne zaman kullanılacağı açıklanır.

### <a name="c-standard-library-smart-pointers"></a>C++ standart kitaplığı akıllı işaretçiler

Bu akıllı işaretçileri eski C++ nesnelerine (POCO) işaretçi kapsüllemek için ilk seçenek olarak kullanın.

- `unique_ptr`<br/>
   Temel alınan işaretçi için, kesin olarak tek bir sahibe izin verir. İçin gerekli olan belirli bir bilginiz olmadığı sürece POCO için varsayılan seçenek olarak kullanın `shared_ptr` . Bir yeni kullanıcıya taşınabilir, ancak kopyalanamaz veya paylaşılamaz. `auto_ptr`Kullanım dışı olan ' nin yerini alır. İle karşılaştırın `boost::scoped_ptr` . `unique_ptr`küçük ve verimlidir; Boyut bir işaretçidir ve C++ standart kitaplık koleksiyonlarından hızlı ekleme ve alma için Rvalue başvurularını destekler. Üst bilgi dosyası: `<memory>` . Daha fazla bilgi için bkz. [nasıl yapılır: oluşturma ve kullanma Unique_ptr örnekleri](how-to-create-and-use-unique-ptr-instances.md) ve [unique_ptr Sınıfı](../standard-library/unique-ptr-class.md).

- `shared_ptr`<br/>
   Başvuru sayımı olan akıllı işaretçi. Birden fazla sahibe tek bir ham işaretçi atamak istediğinizde kullanın, örnek olarak bir kapsayıcıdan işaretçi kopyası döndürüp orijinalini saklamak istediğinizde kullanın. Ham işaretçi, tüm `shared_ptr` sahipler kapsam dışına çıkana veya başka bir şekilde sahiplik verilene kadar silinmez. Boyut iki işaretçi kadardır; biri nesne için ve biri başvuru sayısını içeren paylaşılan denetim bloğu için. Üst bilgi dosyası: `<memory>` . Daha fazla bilgi için bkz. [nasıl yapılır: oluşturma ve kullanma Shared_ptr örnekleri](how-to-create-and-use-shared-ptr-instances.md) ve [shared_ptr Sınıfı](../standard-library/shared-ptr-class.md).

- `weak_ptr`<br/>
    İle birlikte kullanmak için özel durum akıllı işaretçisi `shared_ptr` . `weak_ptr`, Bir veya daha fazla örneğe sahip olan `shared_ptr` , ancak başvuru saymasına katılmayan bir nesneye erişim sağlar. Bir nesneyi görmek istiyorsanız ancak canlı kalmasını istemiyorsanız kullanın. Örnekler arasında döngüsel başvuruları bölmek için bazı durumlarda gereklidir `shared_ptr` . Üst bilgi dosyası: `<memory>` . Daha fazla bilgi için bkz. [nasıl yapılır: oluşturma ve kullanma Weak_ptr örnekleri](how-to-create-and-use-weak-ptr-instances.md) ve [weak_ptr sınıfı](../standard-library/weak-ptr-class.md).

### <a name="smart-pointers-for-com-objects-classic-windows-programming"></a>COM nesneleri için akıllı işaretçiler (Klasik Windows programlama)

COM nesneleriyle çalışırken, arabirim işaretçilerini uygun akıllı işaretçi türüne sarın. Etkin Şablon Kitaplığı (ATL) çeşitli amaçlar için birçok akıllı işaretçi tanımlar. Ayrıca, `_com_ptr_t` derleyicinin. tlb dosyalarından sarmalayıcı sınıflar oluşturduğunda kullandığı akıllı işaretçi türünü de kullanabilirsiniz. ATL üstbilgi dosyalarını eklemek istemediğinizde en iyi seçenektir.

[CComPtr sınıfı](../atl/reference/ccomptr-class.md)<br/>
ATL kullanabiliyorsanız bunu kullanın. Ve yöntemlerini kullanarak başvuru sayımı gerçekleştirir `AddRef` `Release` . Daha fazla bilgi için bkz. [nasıl yapılır: CComPtr ve CComQIPtr örnekleri oluşturma ve kullanma](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md).

[CComQIPtr sınıfı](../atl/reference/ccomqiptr-class.md)<br/>
Benzer `CComPtr` ancak com nesnelerini çağırmak için Basitleştirilmiş sözdizimi de sağlar `QueryInterface` . Daha fazla bilgi için bkz. [nasıl yapılır: CComPtr ve CComQIPtr örnekleri oluşturma ve kullanma](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md).

[CComHeapPtr sınıfı](../atl/reference/ccomheapptr-class.md)<br/>
Belleği boşaltmak için kullanılan nesnelere yönelik akıllı işaretçi `CoTaskMemFree` .

[CComGITPtr sınıfı](../atl/reference/ccomgitptr-class.md)<br/>
Genel arabirim tablosundan (GIT) alınan arabirimler için akıllı işaretçi.

[_com_ptr_t sınıfı](com-ptr-t-class.md)<br/>
`CComQIPtr`İşlevlerde benzerdir ancak ATL üst bilgilerine bağlı değildir.

### <a name="atl-smart-pointers-for-poco-objects"></a>POCO nesneleri için ATL akıllı işaretçileri

ATL, COM nesneleri için akıllı işaretçilere ek olarak, düz eski C++ nesneleri (POCO) için akıllı işaretçiler ve akıllı işaretçiler koleksiyonlarını da tanımlar. Klasik Windows programlamada, özellikle kod taşınabilirliği gerekli olmadığında veya C++ standart kitaplığı ve ATL programlama modellerini karıştırmak istemediğinizde, bu türler C++ standart kitaplığı koleksiyonları için kullanışlı alternatiflerdir.

[CAutoPtr sınıfı](../atl/reference/cautoptr-class.md)<br/>
Sahipliği bir kopyaya aktararak benzersiz sahipliği zorlayan akıllı işaretçi. Kullanım dışı bırakılmış `std::auto_ptr` sınıfla karşılaştırılabilir.

[CHeapPtr sınıfı](../atl/reference/cheapptr-class.md)<br/>
C [malloc](../c-runtime-library/reference/malloc.md) işlevi kullanılarak ayrılan nesneler için akıllı işaretçi.

[CAutoVectorPtr sınıfı](../atl/reference/cautovectorptr-class.md)<br/>
Kullanılarak ayrılan diziler için akıllı işaretçi `new[]` .

[CAutoPtrArray sınıfı](../atl/reference/cautoptrarray-class.md)<br/>
Öğe dizisini kapsülleyen sınıf `CAutoPtr` .

[CAutoPtrList sınıfı](../atl/reference/cautoptrlist-class.md)<br/>
Düğüm listesini düzenleme yöntemlerini kapsülleyen sınıf `CAutoPtr` .

## <a name="see-also"></a>Ayrıca bkz.

[İşaretçiler](pointers-cpp.md)<br/>
[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)
