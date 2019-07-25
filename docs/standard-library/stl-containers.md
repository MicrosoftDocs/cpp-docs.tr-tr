---
title: C++Standart Kitaplık kapsayıcıları
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, template class containers
- containers, C++ Standard Library
ms.assetid: 8e915ca1-19ba-4f0d-93c8-e2c3bfd638eb
ms.openlocfilehash: 6077ff76e04e6f078946eed0856723e2a9998f58
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449604"
---
# <a name="c-standard-library-containers"></a>C++Standart Kitaplık kapsayıcıları

Standart Kitaplık ilgili nesnelerin koleksiyonlarını depolamak için çeşitli tür açısından güvenli kapsayıcılar sağlar. Kapsayıcılar sınıf şablonlardır; bir kapsayıcı değişkeni bildirdiğinizde kapsayıcının tutacağız öğelerin türünü belirtirsiniz. Kapsayıcılar, başlatıcı listeleriyle oluşturulabilir. Öğe ekleme ve kaldırma ve diğer işlemleri gerçekleştirme için üye işlevleri vardır.

Bir kapsayıcıdaki öğelerin üzerinde yineleme yapın ve [yineleyiciler](../standard-library/iterators.md)kullanarak ayrı öğelere erişin. Yineleyiciler, üye işlevlerini ve işleçlerini ve genel işlevleri kullanarak açıkça kullanabilirsiniz. Ayrıca, örneğin bir Aralık for döngüsü kullanarak bunları örtülü olarak da kullanabilirsiniz. Tüm C++ standart kitaplık kapsayıcıları için yineleyiciler ortak bir arabirime sahiptir ancak her kapsayıcı kendi özel yineleyicilerini tanımlar.

Kapsayıcılar üç kategoriye ayrılabilir: dizi kapsayıcıları, ilişkilendirilebilir kapsayıcılar ve kapsayıcı bağdaştırıcıları.

## <a name="sequence_containers"></a>Dizi kapsayıcıları

Sıra kapsayıcıları, belirttiğiniz eklenen öğelerin sıralamasını korur.

Bir `vector` kapsayıcı bir dizi gibi davranır, ancak gerektiğinde otomatik olarak büyüyebilir. Rastgele erişime ve bitişik olarak depolanır ve uzunluk oldukça esnektir. Bu nedenlerden dolayı, `vector` çoğu uygulama için tercih edilen sıra kapsayıcısıdır. Ne tür bir dizi kapsayıcısının kullanılacağı konusunda şüpheli olduğunda, bir vektör kullanarak başlayın! Daha fazla bilgi için bkz. [vektör sınıfı](../standard-library/vector-class.md).

Bir `array` kapsayıcıda bazı `vector`güçleri vardır, ancak uzunluk esnek değildir. Daha fazla bilgi için bkz. [dizi sınıfı](../standard-library/array-class-stl.md).

A `deque` (çift uçlu kuyruk) kapsayıcısı, kapsayıcının başındaki ve sonundaki hızlı ekleme ve silme işlemlerine izin verir. Rastgele erişim ve esnek uzunlukta avantajları `vector`paylaşır, ancak bitişik değildir. Daha fazla bilgi için bkz. [deque Sınıfı](../standard-library/deque-class.md).

Kapsayıcı, kapsayıcıda her yerde çift yönlü erişim, hızlı eklemeler ve hızlı silme işlemleri sağlayan, ancak kapsayıcıdaki bir öğeye rastgele erişim sağlayan, birbirine bağlı bir liste olan bir kapsayıcıdır.`list` Daha fazla bilgi için bkz. [list Class](../standard-library/list-class.md).

Bir `forward_list` kapsayıcı, ' nin `list`ileri erişimli bir listedir bağlantılı listesidir. Daha fazla bilgi için bkz. [forward_list Class](../standard-library/forward-list-class.md).

## <a name="associative-containers"></a>İlişkilendirilebilir kapsayıcılar

İlişkilendirilebilir kapsayıcılar içinde, öğeler önceden tanımlanmış bir sıraya eklenir — Örneğin, artan düzende sıralanır. Sıralanmamış ilişkilendirilebilir kapsayıcılar da kullanılabilir. İlişkilendirilebilir kapsayıcılar iki alt küme halinde gruplandırılabilir: haritalar ve kümeler.

Bazen `map`sözlük olarak da adlandırılan bir anahtar/değer çiftinden oluşur. Anahtar, diziyi sıralamak için kullanılır ve değer bu anahtarla ilişkilendirilir. Örneğin, bir `map` metindeki her benzersiz sözcüğü temsil eden anahtarlar ve her sözcüğün metinde görünme sayısını temsil eden karşılık gelen değerleri içerebilir. `map` Öğesinin`unordered_map`sırasız sürümü. Daha fazla bilgi için bkz. [Map Class](../standard-library/map-class.md) and [unordered_map Class](../standard-library/unordered-map-class.md).

`set` Yalnızca, benzersiz öğelerin artan bir kapsayıcısıdır — değer de anahtardır. `set` Öğesinin`unordered_set`sırasız sürümü. Daha fazla bilgi için bkz. [set Class](../standard-library/set-class.md) and [unordered_set Class](../standard-library/unordered-set-class.md).

Her `map` ikisi `set` ve yalnızca bir anahtar veya öğe örneğinin kapsayıcıya eklenmesine izin verir. Birden çok öğe örneği gerekliyse, veya `multimap` `multiset`kullanın. Sıralanmamış sürümler ve ' `unordered_multimap` `unordered_multiset`dir. Daha fazla bilgi için bkz. [multimap Class](../standard-library/multimap-class.md), [unordered_multimap Class](../standard-library/unordered-multimap-class.md), [multıset Class](../standard-library/multiset-class.md)ve [unordered_multiset Class](../standard-library/unordered-multiset-class.md).

Sıralı haritalar ve kümeler çift yönlü yineleyiciler destekler ve sıralanmamış karşılıkları ileri yineleyiciler destekler. Daha fazla bilgi için bkz. [yineleyiciler](../standard-library/iterators.md).

### <a name="heterogeneous-lookup-in-associative-containers-c14"></a>Ilişkilendirilebilir kapsayıcılarda heterojen arama (C++ 14)

Sıralı ilişkilendirilebilir kapsayıcılar (eşleme, multimap, küme ve çoklu küme) artık, `find()` ve `lower_bound()` gibi üye işlevlerdeki anahtar veya öğeyle tam olarak aynı nesne türünü geçirmek için gerekli olmayan heterojen aramayı destekliyor. . Bunun yerine, anahtar türüyle karşılaştırmayı sağlayan aşırı yüklenmiş `operator<` bir türü geçirebilirsiniz.

Heterojen arama, burada gösterildiği gibi kapsayıcı değişkenini bildirirken `std::less<>` veya `std::greater<>` "elmas functor" karşılaştırıcısı belirttiğinizde, kabul etme temelinde etkinleştirilir:

```cpp
std::set<BigObject, std::less<>> myNewSet;
```

Varsayılan karşılaştırıcısı kullanırsanız, kapsayıcı tam olarak C++ 11 ve önceki sürümlerde olduğu gibi davranır.

Aşağıdaki örnek, her bir nesnenin `operator<` `BigObject::id` üyesiyle karşılaştırılabilmek için küçük bir dizeyi `std::set` geçirerek, bir, kullanıcılarının arama yapması için nasıl aşırı yükleneceğini gösterir.

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

Eşleme, multimap, set ve multııd içindeki aşağıdaki üye işlevleri, heterojen aramayı destekleyecek şekilde aşırı yüklendi:

1. find

1. count

1. lower_bound

1. upper_bound

1. equal_range

## <a name="container-adapters"></a>Kapsayıcı bağdaştırıcıları

Kapsayıcı bağdaştırıcı, arabirimi basitlik ve açıklık için kısıtlayan bir dizi veya ilişkilendirilebilir kapsayıcının çeşitidir. Kapsayıcı bağdaştırıcıları yineleyiciler desteklemez.

Bir `queue` kapsayıcı FIFO (ilk, ilk çıkar) semantiğini izler. *Gönderilen*ilk öğe — sıraya eklenen (yani, kuyruğa eklenen) ilk çıkarılım, yani kuyruktan kaldırılır. Daha fazla bilgi için bkz. [Queue Class](../standard-library/queue-class.md).

Bir `priority_queue` kapsayıcı, en yüksek değere sahip olan öğe sırada her zaman ilk başta olacak şekilde düzenlenir. Daha fazla bilgi için bkz. [priority_queue Class](../standard-library/priority-queue-class.md).

Bir `stack` kapsayıcı, LIFO (son, ilk çıkar) semantiğini izler. Yığına gönderilen son öğe, ilk öğe olarak belirlenir. Daha fazla bilgi için bkz. [Stack sınıfı](../standard-library/stack-class.md).

Kapsayıcı bağdaştırıcıları yineleyiciler desteklemediğinden, C++ standart kitaplık algoritmalarıyla kullanılamaz. Daha fazla bilgi için bkz. [algoritmalar](../standard-library/algorithms.md).

## <a name="requirements-for-container-elements"></a>Kapsayıcı öğeleri için gereksinimler

Genel olarak, standart bir C++ kitaplık kapsayıcısına eklenen öğeler, kopyalanabilir olmaları durumunda yalnızca herhangi bir nesne türü hakkında olabilir. Yalnızca taşınabilir öğeler (örneğin, kullanılarak `vector<unique_ptr<T>>` `unique_ptr<>` oluşturulan gibi), onları kopyalamaya çalışan üye işlevlerini çağırmazsanız sürece çalışacaktır.

Yok edicinin özel durum oluşturması için izin verilmez.

Bu makalede daha önce açıklanan sıralı ilişkilendirilebilir kapsayıcılar, bir genel karşılaştırma işlecinin tanımlanmış olması gerekir. (Varsayılan olarak işleç olur `operator<`, ancak birlikte `operator<` çalışmayan türler de desteklenir.

Kapsayıcılardaki bazı işlemler ortak bir varsayılan Oluşturucu ve genel denklik işleci de gerektirebilir. Örneğin, sıralanmamış ilişkilendirilebilir kapsayıcılar eşitlik ve karma için destek gerektirir.

## <a name="accessing-container-elements"></a>Kapsayıcı öğelerine erişme

Kapsayıcıların öğelerine yineleyiciler kullanılarak erişilir. Daha fazla bilgi için bkz. [yineleyiciler](../standard-library/iterators.md).

> [!NOTE]
> Standart Kitaplık koleksiyonlarını yinelemek için [Aralık tabanlı döngüleri](../cpp/range-based-for-statement-cpp.md) de kullanabilirsiniz. C++

## <a name="comparing-containers"></a>Kapsayıcıları karşılaştırma

Tüm kapsayıcılar aynı öğe türüne sahip aynı türde iki kapsayıcıyı karşılaştırmak için = = işlecini aşırı yükler. Bir\<vektör dizesi > başka bir vektör\<dizesi > karşılaştırmak için = = kullanabilirsiniz, ancak bir vektör dize > bir liste\<dizesi > veya\<bir\<vector String > bir vektör dizesiyle karşılaştırmak için kullanamazsınız \<char * >.  C++ 98/03 ' de, benzer olmayan kapsayıcı türlerini ve/veya öğe türlerini karşılaştırmak için [std:: eşittir](algorithm-functions.md#equal) veya [std:: uyuşmazlığını](algorithm-functions.md#mismatch) kullanabilirsiniz. C++ 11 ' de [std:: is_permutation](algorithm-functions.md#is_permutation)' i de kullanabilirsiniz. Ancak tüm bu durumlarda, işlevler kapsayıcıların aynı uzunlukta olduğunu varsaymaktadır. İkinci Aralık birinciden kısaysa, tanımsız davranış sonuçları olur. İkinci Aralık daha uzunsa, karşılaştırma hiçbir şekilde ilk aralığın sonundan önce devam ettiğinden sonuçlar yine de hatalı olabilir.

### <a name="comparing-dissimilar-containers-c14"></a>Benzemez kapsayıcıları karşılaştırma (C++ 14)

C++ 14 ve sonraki sürümlerinde, iki ayrı Aralık alan `std::equal`, veya `std::is_permutation` işlev aşırı yüklemelerinin birini kullanarak, `std::mismatch`benzer kapsayıcıları ve/veya benzer olmayan öğe türlerini karşılaştırabilirsiniz. Bu aşırı yüklemeler, kapsayıcıları farklı uzunluklara göre karşılaştırmanızı sağlar. Bu aşırı yüklemeler Kullanıcı hatasına çok daha az açıktır ve Farklı uzunluklardaki kapsayıcılar karşılaştırıldığı zaman sabit zamanlı olarak false döndürecek şekilde iyileştirilir. Bu nedenle, (1) çok açık bir nedeniniz yoksa veya (2) çift aralıklı iyileştirmelerin avantajına sahip olmayan bir [std:: List](../standard-library/list-class.md) kapsayıcısı kullandığınız müddetçe bu aşırı yüklemeleri kullanmanızı öneririz.

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcıları](../cpp/containers-modern-cpp.md)\
[C++Standart kitaplık başvurusu](../standard-library/cpp-standard-library-reference.md)\
[\<örnek kapsayıcı >](../standard-library/sample-container.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
