---
title: C++ Standart Kitaplığı Kapsayıcıları
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, class template containers
- containers, C++ Standard Library
ms.assetid: 8e915ca1-19ba-4f0d-93c8-e2c3bfd638eb
ms.openlocfilehash: 01be754dd7b418f64cf495d7563f65b323265df8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376696"
---
# <a name="c-standard-library-containers"></a>C++ Standart Kitaplığı Kapsayıcıları

Standart Kitaplık, ilgili nesnelerin koleksiyonlarını depolamak için çeşitli tür güvenli kapsayıcılar sağlar. Kapsayıcılar sınıf şablonlarıdır. Bir kapsayıcı değişkenini bildirdiğinizde, kapsayıcının tutacağı öğelerin türünü belirtirsiniz. Konteynerler baş harf listeleri ile oluşturulabilir. Öğeleri eklemek ve kaldırmak ve diğer işlemleri yapmak için üye işlevleri vardır.

Bir kapsayıcıdaki öğeler üzerinde yineleme ve [yineleyiciler](../standard-library/iterators.md)kullanarak tek tek öğelere erişin. Yineleyicileri üye işlevlerini, işleçlerini ve genel işlevlerini kullanarak açıkça kullanabilirsiniz. Bunları, örneğin bir aralık için döngü kullanarak da dolaylı olarak kullanabilirsiniz. Tüm C++ Standart Kitaplık kapsayıcılarının yineleyicileri ortak bir arabirime sahiptir, ancak her kapsayıcı kendi özel yineleyicilerini tanımlar.

Kapsayıcılar üç kategoriye ayrılabilir: sıralı kapsayıcılar, bağşılı kapsayıcılar ve kapsayıcı bağdaştırıcıları.

## <a name="sequence-containers"></a><a name="sequence_containers"></a>Sıra Kapları

Sıra kapsayıcıları, belirttiğiniz eklenen öğelerin sırasını korur.

Kapsayıcı `vector` bir dizi gibi görünür, ancak gerektiğinde otomatik olarak büyüyebilir. Bu rasgele erişim ve bitişik saklanır ve uzunluğu son derece esnektir. Bu nedenlerle ve `vector` daha fazlası için, çoğu uygulama için tercih edilen sıra kapsayıcıdır. Ne tür bir sıra kapsayıcı kullanmak için şüphe, bir vektör kullanarak başlayın! Daha fazla bilgi için [vektör sınıfı'na](../standard-library/vector-class.md)bakın.

Bir `array` konteyner bazı güçlü vardır `vector`, ama uzunluğu kadar esnek değildir. Daha fazla bilgi için [dizi Sınıfı'na](../standard-library/array-class-stl.md)bakın.

(Çift `deque` uçlu sıra) kapsayıcı, kapsayıcının başında ve sonunda hızlı eklemeler ve silmeler sağlar. Rasgele erişim ve esnek uzunlukta avantajları `vector`paylaşır, ancak bitişik değildir. Daha fazla bilgi için [deque Class'a](../standard-library/deque-class.md)bakın.

Kapsayıcı, `list` iki yönlü erişim, hızlı eklemeler ve kapsayıcının herhangi bir yerindeki hızlı silmeleri sağlayan iki yönlü bir listedir, ancak kapsayıcıdaki bir öğeye rasgele erişemezsiniz. Daha fazla bilgi için [liste Sınıfı'na](../standard-library/list-class.md)bakın.

Kapsayıcı, `forward_list` tekil olarak birbirine bağlı bir listedir— `list`. Daha fazla bilgi için [forward_list Sınıfına](../standard-library/forward-list-class.md)bakın.

## <a name="associative-containers"></a>Assosiyatif Konteynerler

Bağşdırıcı kapsayıcılarda, öğeler önceden tanımlanmış bir sıraya (örneğin, artan sıralanmış olarak) eklenir. Sipariş edilmemiş birleşme kapları da mevcuttur. Bağşandırıcı kapsayıcılar iki alt kümeye gruplandırılabilir: haritalar ve kümeler.

A `map`, bazen sözlük olarak adlandırılır, bir anahtar/değer çiftinden oluşur. Anahtar sırayı sıralamak için kullanılır ve değer bu anahtarla ilişkilidir. Örneğin, bir `map` metindeki her benzersiz sözcüğü temsil eden anahtarlar ve her sözcüğün metinde görünme sayısını temsil eden karşılık gelen değerler içerebilir. Sıralanmamış sürümü `map` `unordered_map`. Daha fazla bilgi için [Bkz. harita Sınıf](../standard-library/map-class.md) ve [unordered_map Sınıfı.](../standard-library/unordered-map-class.md)

A, `set` benzersiz öğelerden oluşan yükselen bir kapsayıcıdır- değer de anahtardır. Sıralanmamış sürümü `set` `unordered_set`. Daha fazla bilgi için Sınıf ve unordered_set [Sınıfı kümesi'ne](../standard-library/set-class.md) bakın. [unordered_set Class](../standard-library/unordered-set-class.md)

Her `map` `set` ikisi de ve yalnızca bir anahtar veya öğe örneğinin kapsayıcıya eklenmesine izin verin. Birden fazla öğe örneği gerekiyorsa, `multimap` `multiset`kullanın veya. Sıralanmamış sürümleri ve `unordered_multimap` `unordered_multiset`. Daha fazla bilgi [için, multimap Class,](../standard-library/multimap-class.md) [unordered_multimap Class](../standard-library/unordered-multimap-class.md), [multiset Class](../standard-library/multiset-class.md)ve unordered_multiset [Sınıfı'na](../standard-library/unordered-multiset-class.md)bakın.

Sipariş edilen haritalar ve kümeler çift yönlü yineleyicileri destekler ve sıralanmamış karşılıkları ileri yineleyicileri destekler. Daha fazla bilgi için [bkz.](../standard-library/iterators.md)

### <a name="heterogeneous-lookup-in-associative-containers-c14"></a>Bağdaştırıcı Kaplarda Heterojen Arama (C++14)

Sıralanan etkileşim kapları (harita, çok harita, set ve çok ayarlı) artık heterojen bir aramayı destekliyor, bu da artık üye işlevlerde anahtar veya `find()` `lower_bound()`eleman la aynı nesne türünü geçmeniz gerekolmadığı anlamına geliyor. Bunun yerine, anahtar türüyle karşılaştırma `operator<` yapılmasını sağlayan aşırı yüklü bir türü geçebilirsiniz.

Burada gösterildiği gibi, kapsayıcı değişkenini beyan ederken `std::less<>` `std::greater<>` "elmas functor" karşılaştırıcısını belirtirken heterojen bir arama, tercih bazında etkinleştirilir:

```cpp
std::set<BigObject, std::less<>> myNewSet;
```

Varsayılan karşılaştırıcıyı kullanırsanız, kapsayıcı C++11 ve daha önceki nde olduğu gibi tam olarak görünür.

Aşağıdaki örnek, bir `operator<` `std::set` nesnenin `BigObject::id` kullanıcılarının yalnızca her nesnenin üyesiyle karşılaştırılabilen küçük bir dize geçirerek arama yapmalarını sağlamak için nasıl aşırı yükleneceklerini gösterir.

```cpp
#include <set>
#include <string>
#include <iostream>
#include <functional>

using namespace std;

class BigObject
{
public:
    string id;
    explicit BigObject(const string& s) : id(s) {}
    bool operator< (const BigObject& other) const
    {
        return this->id < other.id;
    }

    // Other members....
};

inline bool operator<(const string& otherId, const BigObject& obj)
{
    return otherId < obj.id;
}

inline bool operator<(const BigObject& obj, const string& otherId)
{
    return obj.id < otherId;
}

int main()
{
    // Use C++14 brace-init syntax to invoke BigObject(string).
    // The s suffix invokes string ctor. It is a C++14 user-defined
    // literal defined in <string>
    BigObject b1{ "42F"s };
    BigObject b2{ "52F"s };
    BigObject b3{ "62F"s };
    set<BigObject, less<>> myNewSet; // C++14
    myNewSet.insert(b1);
    myNewSet.insert(b2);
    myNewSet.insert(b3);
    auto it = myNewSet.find(string("62F"));
    if (it != myNewSet.end())
        cout << "myNewSet element = " << it->id << endl;
    else
        cout << "element not found " << endl;

    // Keep console open in debug mode:
    cout << endl << "Press Enter to exit.";
    string s;
    getline(cin, s);
    return 0;
}

//Output: myNewSet element = 62F
```

Harita, çok harita, set ve çoklu kümedeki aşağıdaki üye işlevler heterojen bir aramayı desteklemek için aşırı yüklendi:

1. find

1. count

1. lower_bound

1. upper_bound

1. equal_range

## <a name="container-adapters"></a>Konteyner Adaptörleri

Kapsayıcı bağdaştırıcısı, basitlik ve netlik için arabirimi kısıtlayan bir dizi veya bağdaştırıcı kapsayıcının varyasyonudur. Konteyner bağdaştırıcıları yineleyicileri desteklemez.

Bir `queue` kapsayıcı FIFO (ilk, ilk çıkan) semantik izler. *Itilen*ilk öğe (yani kuyruğa eklenen) ilk *başlatılan*öğedir — yani kuyruktan kaldırılır. Daha fazla bilgi için [sıra Sınıfı'na](../standard-library/queue-class.md)bakın.

Bir `priority_queue` kapsayıcı, en yüksek değere sahip öğeher zaman sırada ilk olacak şekilde düzenlenir. Daha fazla bilgi için [priority_queue Sınıf'a](../standard-library/priority-queue-class.md)bakın.

Bir `stack` kapsayıcı LIFO (son, ilk çıkan) semantik izler. Yığına itilen son öğe, ilk öğenin patlatılan öğesidir. Daha fazla bilgi için [yığın Sınıfı'na](../standard-library/stack-class.md)bakın.

Kapsayıcı bağdaştırıcılar yineleyicileri desteklemediği için C++ Standart Kitaplık algoritmalarıyla kullanılamazlar. Daha fazla bilgi için [Algoritmalar'a](../standard-library/algorithms.md)bakın.

## <a name="requirements-for-container-elements"></a>Konteyner Elemanları için Gereksinimler

Genel olarak, C++ Standart Kitaplık kapsayıcısına eklenen öğeler, kopyalanabilirse hemen hemen her nesne türünden olabilir. Yalnızca taşınabilir öğeler-örneğin, bu tür `vector<unique_ptr<T>>` kullanarak `unique_ptr<>` oluşturulan lar, bunları kopyalamaya çalışan üye işlevleri aramadığınız sürece çalışır.

Yıkıcının bir istisna yapmasına izin verilmez.

Bu makalede daha önce açıklanan sipariş edilen birleştirici kapsayıcıların bir genel karşılaştırma işleci tanımlanmış olması gerekir. (Varsayılan olarak, `operator<`işleç, ancak çalışmayan `operator<` türleri bile desteklenir.

Kapsayıcılar üzerindeki bazı işlemler de bir genel varsayılan oluşturucu ve bir ortak eşdeğerlik işleci gerektirebilir. Örneğin, sıralanmamış bağştırma kapları eşitlik ve karma için destek gerektirir.

## <a name="accessing-container-elements"></a>Konteyner Elemanlarına Erişim

Kapsayıcıların öğelerine yineleyiciler kullanılarak erişilir. Daha fazla bilgi için [bkz.](../standard-library/iterators.md)

> [!NOTE]
> C++ Standart Kitaplık koleksiyonları üzerinde yinelemek [için döngüler için aralık tabanlı](../cpp/range-based-for-statement-cpp.md) da kullanabilirsiniz.

## <a name="comparing-containers"></a>Kapsayıcıları karşılaştırma

Tüm kapsayıcılar işleci aşırı yükler== aynı türde aynı öğe türüne sahip iki kapsayıcıyı karşılaştırmak için. \<>> bir vektör\<dizesini karşılaştırmak için == kullanabilirsiniz, ancak>\<bir vektör dizesini liste\<\<dizesi\<> veya vektör dizesini> bir vektör idize karşılaştırmak için kullanamazsınız >.  C++98/03'te, farklı kapsayıcı türlerini ve/veya öğe türlerini karşılaştırmak için [std:equal](algorithm-functions.md#equal) veya [std::uyuşmazlık](algorithm-functions.md#mismatch) kullanabilirsiniz. C++11'de [std::is_permutation'ı](algorithm-functions.md#is_permutation)da kullanabilirsiniz. Ancak tüm bu durumlarda işlevler kapsayıcıların aynı uzunlukta olduğunu varsayar. İkinci aralık ilkinden daha kısaysa, tanımlanmamış davranış sonuçları ortaya atılır. İkinci aralık daha uzunsa, karşılaştırma hiçbir zaman ilk aralığın sonuna kadar devam etmediğinden sonuçlar yine de yanlış olabilir.

### <a name="comparing-dissimilar-containers-c14"></a>Farklı kapsayıcıları karşılaştırma (C++14)

C++14 ve sonraki sürümlerinde, iki tam aralık alan `std::equal`, veya `std::mismatch` `std::is_permutation` işlev aşırı yüklerinden birini kullanarak farklı kapsayıcıları ve/veya farklı öğe türlerini karşılaştırabilirsiniz. Bu aşırı yüklemeler, kapları farklı uzunluklarda karşılaştırmanızı sağlar. Bu aşırı yükler kullanıcı hatasına karşı çok daha az duyarlıdır ve farklı uzunluktaki kaplar karşılaştırıldığında sabit zamanda false dönmek için optimize edilebiyileştirilir. Bu nedenle, bu aşırı yüklemeleri kullanmamanız veya çift aralıklı optimizasyonlardan yararlanamayan [std::list](../standard-library/list-class.md) kapsayıcı kullanmadığınız sürece kullanmanızı öneririz.

## <a name="see-also"></a>Ayrıca bkz.

[Paralel Konteynerler](../parallel/concrt/parallel-containers-and-objects.md)\
[\<örnek konteyner>](../standard-library/sample-container.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
