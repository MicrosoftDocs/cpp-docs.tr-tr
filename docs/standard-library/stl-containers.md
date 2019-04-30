---
title: C++ Standart Kitaplığı kapsayıcıları
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, template class containers
- containers, C++ Standard Library
ms.assetid: 8e915ca1-19ba-4f0d-93c8-e2c3bfd638eb
ms.openlocfilehash: a6f4da35468143e6d7c3dda684ed93f33e29b21d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412416"
---
# <a name="c-standard-library-containers"></a>C++ Standart Kitaplığı kapsayıcıları

Standart kitaplık, birbiriyle ilgili nesnelerden oluşan koleksiyonları depolamak için çeşitli tür-güvenli kapsayıcılar sağlar. Sınıf şablonlarının kapsayıcılardır; bir kapsayıcı değişken bildirdiğinizde, kapsayıcı tutacak öğelerin türünü belirtin. Kapsayıcılar, başlatıcı listeleri ile oluşturulabilir. Üye işlevleri ekleyerek ve öğelerin kaldırılması ve diğer işlemleri gerçekleştirmek için sahiptirler.

Bir kapsayıcı içindeki öğeleri üzerinde yinelemek ve ayrı ayrı öğeler kullanılarak erişim [yineleyiciler](../standard-library/iterators.md). Yineleyicilerin kendi üye işlevleri ve işleçleri yanı sıra genel işlevleri kullanarak açıkça kullanabilirsiniz. Ayrıca, örneğin bir aralığı kullanarak kullanabilmek için-for döngüsü. Yineleyiciler tüm C++ Standart Kitaplığı kapsayıcıları için ortak bir arabirim sahiptir ancak kendi özelleştirilmiş yineleyiciler her kapsayıcı tanımlar.

Kapsayıcılar üç kategoriye ayrılabilir: sıra kapsayıcıları, ilişkisel kapsayıcılar ve kapsayıcı bağdaştırıcıları.

## <a name="sequence_containers"></a> Sıra kapsayıcılar

Sıra kapsayıcılar belirttiğiniz eklenmiş öğelerin sıralamasını korur.

A `vector` kapsayıcı bir dizi gibi davranır, ancak otomatik olarak büyüyebilir gerektiğinde. Rastgele erişilir ve sürekli depolanır ve uzunluk son derece esnektir. Bu nedenlerden ve daha fazlası için `vector` uygulamalarının çoğu için tercih edilen dizi kapsayıcısıdır. Emin olamadığınız durumlarda kullanılacak dizisi kapsayıcısı ne tür için farklı bir vektör kullanarak başlayın! Daha fazla bilgi için [vector sınıfı](../standard-library/vector-class.md).

Bir `array` kapsayıcı olan bazı güçlerini `vector`, ancak uzunluğu kadar esnek değildir. Daha fazla bilgi için [array sınıfı](../standard-library/array-class-stl.md).

A `deque` hızlı eklemeler ve silmeler başlangıcına ve sonuna kapsayıcı (çift uçlu sorgu) kapsayıcısı sağlar. Rastgele erişim ve esnek uzunluk avantajlarını paylaşır `vector`, ancak bitişik değil. Daha fazla bilgi için [deque sınıfı](../standard-library/deque-class.md).

A `list` kapsayıcıdır iki yönlü erişime, hızlı eklemelere ve hızlı kapsayıcının herhangi bir yerindeki sağlayan karakteriyle bağlı bir liste ancak kapsayıcı içindeki bir öğeyi rastgele erişemezsiniz. Daha fazla bilgi için [list sınıfı](../standard-library/list-class.md).

A `forward_list` kapsayıcıdır ayrı olarak bağlı bir liste — ileriye doğru erişim sürümünü `list`. Daha fazla bilgi için [forward_list sınıfı](../standard-library/forward-list-class.md).

## <a name="associative-containers"></a>İlişkilendirilebilir kapsayıcılar

İlişkisel kapsayıcılarda, öğeler bir öntanımlı sıraya eklenir; örneğin artan şekilde sıralanır. Sıralanmamış ilişkisel kapsayıcılar da kullanılabilir. İlişkisel kapsayıcılar iki alt kümede gruplandırılabilir: eşler ve ayarlar.

A `map`, bazen bir sözlük olarak başvurulan, bir anahtar/değer çiftinden oluşur. Anahtar diziyi sıralamak için kullanılır ve bu anahtar ile ilişkili bir değerdir. Örneğin, bir `map` bir metin ve her sözcüğün metinde görünür sayısını temsil eden ilgili değerleri her benzersiz sözcüğü temsil eden tuşları içerebilir. İn sıralanmamış sürümü `map` olduğu `unordered_map`. Daha fazla bilgi için [map sınıfı](../standard-library/map-class.md) ve [unordered_map sınıfı](../standard-library/unordered-map-class.md).

A `set` yalnızca artan bir kapsayıcı benzersiz öğeleri; değer ayrıca anahtardır. İn sıralanmamış sürümü `set` olduğu `unordered_set`. Daha fazla bilgi için [set sınıfı](../standard-library/set-class.md) ve [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Her ikisi de `map` ve `set` yalnızca bir anahtar veya kapsayıcıya eklenecek öğe bir örneğini izin verin. Birden çok öğe örneği gerekiyorsa, kullanın `multimap` veya `multiset`. Sıralanmamış sürümler `unordered_multimap` ve `unordered_multiset`. Daha fazla bilgi için [multimap sınıfı](../standard-library/multimap-class.md), [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md), [multiset sınıfı](../standard-library/multiset-class.md), ve [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Sıralanmış Haritalar ve kümeler iki yönlü yineleyicileri destekler ve bunların sıralanmamış karşılıkları İleri yönde yineleyicileri destekler. Daha fazla bilgi için [yineleyiciler](../standard-library/iterators.md).

### <a name="heterogeneous-lookup-in-associative-containers-c14"></a>İlişkilendirilebilir kapsayıcılar (C ++ 14) içinde heterojen arama

İlişkilendirilebilir kapsayıcılar (harita, multimap, küme ve multiset) artık anlamına gerekli gibi aynı nesne türünü tam olarak anahtar veya üye işlevleri öğesinde geçirmek için heterojen arama desteği, artık sipariş `find()` ve `lower_bound()` . Bunun yerine, herhangi bir tür için geçirebilirsiniz aşırı yüklenmiş bir `operator<` tanımlanır, anahtar türü karşılaştırma sağlar.

Heterojen arama, bir katılım temelinde etkinse, belirttiğiniz zaman `std::less<>` veya `std::greater<>` kapsayıcı değişkeni burada gösterildiği gibi bildirirken "functor elmas" karşılaştırıcı:

```cpp
std::set<BigObject, std::less<>> myNewSet;
```

Ardından, varsayılan karşılaştırıcı kullanmanız durumunda kapsayıcı tam C ++ 11 ve daha önce yaptığınız gibi davranır.

Aşağıdaki örnek, aşırı yükleme işlemi gösterilmektedir `operator<` kullanıcıları etkinleştirmek için bir `std::set` yalnızca geçirerek karşılaştırılabilir küçük bir dizedeki her nesne için arama yapmak için `BigObject::id` üyesi.

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

Haritada multimap aşağıdaki üye işlevleri, kümesi ve multiset heterojen arama desteklemek için aşırı yüklenmiş:

1. find

1. count

1. lower_bound

1. upper_bound

1. equal_range

## <a name="container-adapters"></a>Kapsayıcı bağdaştırıcıları

Bir kapsayıcı bağdaştırıcısı, bir sıra veya Basitlik ve Anlaşılırlık için arabirimi kısıtlayan seçimin ilişkili kapsayıcısı çeşididir. Kapsayıcı bağdaştırıcıları yineleyicileri desteklemez.

A `queue` kapsayıcısı FIFO (ilk giren ilk çıkar) semantiği izler. İlk öğeyi *gönderilen*— diğer bir deyişle, sıraya eklenen — ilk olan *POP*— diğer bir deyişle, kuyruktan kaldırılır. Daha fazla bilgi için [sınıfı sıra](../standard-library/queue-class.md).

A `priority_queue` kapsayıcı en yüksek değere sahip öğe her zaman kuyrukta ilk sırada olacağı şekilde düzenlenir. Daha fazla bilgi için [priority_queue sınıfı](../standard-library/priority-queue-class.md).

A `stack` kapsayıcısı LIFO (son giren ilk çıkar) semantiği izler. Yığına itildi son öğeyi POP ilk öğedir. Daha fazla bilgi için [stack sınıfı](../standard-library/stack-class.md).

Kapsayıcı bağdaştırıcıları yineleyicileri desteklemediğinden bunlar standart C++ Kitaplığı algoritmaları ile kullanılamaz. Daha fazla bilgi için [algoritmaları](../standard-library/algorithms.md).

## <a name="requirements-for-container-elements"></a>Kapsayıcı öğeleri için gereksinimler

Genel olarak, bir C++ Standart Kitaplığı kapsayıcısına girilen öğeler, kopyalanabiliyorlarsa neredeyse her nesne türünde olabilir. Yalnızca taşınabilir öğeler — Örneğin, bu gibi `vector<unique_ptr<T>>` kullanarak oluşturulan `unique_ptr<>` bunları kopyalamaya işlevleri üye Remove() çağırmayın sürece çalışmaz.

Yıkıcı bir özel durum oluşturmasına izin verilmez.

İlişkilendirilebilir kapsayıcılar sıralı — bu makalenin önceki bölümlerinde açıklanan — tanımlanmış bir genel karşılaştırma işlecine sahip olmalıdır. (Varsayılan işleç olarak `operator<`, ile çalışmayan türler bile ancak `operator<` desteklenir.

Kapsayıcılarda yapılan bazı işlemler de genel bir varsayılan oluşturucu ve genel bir denklik işleci gerektirebilir. Örneğin sırasız ilişki kapsayıcıları, eşitliği ve karmayı desteklemeyi desteği gerektirir.

## <a name="accessing-container-elements"></a>Kapsayıcı öğelerine erişiliyor

Kapsayıcı öğelerine yineleyiciler kullanılarak erişilir. Daha fazla bilgi için [yineleyiciler](../standard-library/iterators.md).

> [!NOTE]
> Ayrıca [aralığa dayalı for döngüleri](../cpp/range-based-for-statement-cpp.md) C++ Standart Kitaplığı koleksiyonu yineleme yapmak için.

## <a name="comparing-containers"></a>Kapsayıcılar ile karşılaştırma

Tüm kapsayıcıları işleci aşırı aynı türde ve aynı öğe türüne sahip iki kapsayıcı karşılaştırmak için ==. Kullanabilirsiniz bir vektör Karşılaştırılacak ==\<dizesi > için başka bir vektör\<dize >, ancak bir vektör karşılaştırmak için kullanamazsınız\<dize > listesine\<dize > ya da bir vektör\<dize > bir vektör için \<char * >.  C ++ 98/03 kullanabileceğiniz [std::equal](algorithm-functions.md#equal) veya [std::mismatch](algorithm-functions.md#mismatch) benzemez kapsayıcı türleri ve/veya öğe türleri karşılaştırmak için. C ++ 11'de de kullanabilirsiniz [std::is_permutation](algorithm-functions.md#is_permutation). Ancak, tüm durumlarda işlevleri kapsayıcıları aynı uzunlukta olduğunu varsayar. İkinci aralığı, ardından tanımsız davranış sonuçlarından daha kısa ise. İkinci aralığı uzunsa, karşılaştırma ilk aralığın sonunu hiçbir zaman devam ettiğinden sonuçlar yine de yanlış olabilir.

### <a name="comparing-dissimilar-containers-c14"></a>Farklı kapsayıcılar (C ++ 14) karşılaştırma

C ++ 14 ve daha sonra farklı kapsayıcılar ve/veya benzer öğeleri türleri birini kullanarak karşılaştırabileceğiniz `std::equal`, `std::mismatch`, veya `std::is_permutation` işlev iki tam aralık alan aşırı yüklemeler. Bu aşırı yüklemeler farklı uzunluktaki kapsayıcılarla karşılaştırmanızı sağlar. Bu aşırı yüklemeler için kullanıcı hatası çok daha az açıktır ve benzer uzunluklarının kapsayıcıları ne zaman karşılaştırılır Sabit sürede false döndürmek için iyileştirilmiştir. Bu nedenle, (1) için çok açık bir neden olması veya (2), kullandığınız sürece bu aşırı yüklemeler kullanmanızı öneririz bir [std::list](../standard-library/list-class.md) çift aralıklı iyileştirmeleri fayda kapsayıcı.

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](../cpp/containers-modern-cpp.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
[\<Örnek kapsayıcı >](../standard-library/sample-container.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
