---
title: C++ Standart Kitaplığı kapsayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, template class containers
- containers, C++ Standard Library
ms.assetid: 8e915ca1-19ba-4f0d-93c8-e2c3bfd638eb
caps.latest.revision: 29
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f77cf814dce9065778e64951884ad9c8f1be372e
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="c-standard-library-containers"></a>C++ Standart Kitaplığı kapsayıcıları

Standart Kitaplığı, ilgili nesne koleksiyonları depolamak için çeşitli tür kullanımı uyumlu kapsayıcıları sağlar. Sınıf şablonları kapsayıcılardır; bir kapsayıcı değişkeni bildirirken kapsayıcı tutacak öğelerin türünü belirtin. Başlatıcı Listeleri ile kapsayıcıları oluşturulabilir. Ekleme ve öğeleri kaldırma ve diğer işlemleri gerçekleştirmek için üye işlevleri sahiptirler.

Bir kapsayıcı öğeleri üzerinden yineleme ve ayrı ayrı öğeler kullanarak erişim [yineleyiciler](../standard-library/iterators.md). Kendi üye işlevleri ve işleçler yanı sıra genel işlevleri kullanarak yineleyiciler açıkça kullanabilirsiniz. Ayrıca dolaylı olarak, örneğin bir aralık kullanarak kullanabilmek için-döngü için. Yineleyiciler tüm C++ Standart Kitaplığı kapsayıcıları için ortak bir arabirim sahip ancak kendi özelleştirilmiş yineleyiciler her kapsayıcı tanımlar.

Kapsayıcı üç kategoride bölünmüş: dizisi kapsayıcıları, ilişkilendirilebilir kapsayıcıları ve kapsayıcı bağdaştırıcıları.

## <a name="sequence_containers"></a> Sıra kapsayıcıları

Sıralı kapsayıcı, belirttiğiniz eklenen öğelerin sıralaması korur.

A `vector` kapsayıcı bir dizi gibi davranır, ancak otomatik olarak büyüyebilir gerektiği gibi. Rasgele erişim ve bitişik depolanır ve uzunluğu çok esnektir. Bu nedenle ve hakkında daha fazla bilgi için `vector` çoğu uygulama için tercih edilen dizisi kapsayıcıdır. Zaman şüpheli için ne tür bir sıralı kapsayıcı kullanmak için bir vektör kullanarak başlayın! Daha fazla bilgi için bkz: [vector sınıfı](../standard-library/vector-class.md).

Bir `array` kapsayıcıda varsa bazı gücü `vector`, ancak uzunluğu kadar esnek değildir. Daha fazla bilgi için bkz: [array sınıfı](../standard-library/array-class-stl.md).

A `deque` hızlı eklemeler ve başlangıcını ve bitişini kapsayıcısının silme işlemleri (sıra çift sona erdi) kapsayıcı sağlar. Rasgele erişim ve esnek uzunlukta avantajları paylaşır `vector`, ancak bitişik değil. Daha fazla bilgi için bkz: [deque sınıfı](../standard-library/deque-class.md).

A `list` kapsayıcı çift yönlü erişim, hızlı eklemeleri ve kapsayıcı başka bir yerindeki hızlı silme sağlayan bir listedir karakteriyle bağlı, ancak bir öğe kapsayıcı rastgele erişemez. Daha fazla bilgi için bkz: [sınıf listesi](../standard-library/list-class.md).

A `forward_list` kapsayıcı tek bağlı bir listedir — İleri access sürümü `list`. Daha fazla bilgi için bkz: [forward_list sınıfı](../standard-library/forward-list-class.md).

## <a name="associative-containers"></a>İlişkilendirilebilir kapsayıcıları

Önceden tanımlanmış bir sırada eklenen ilişkilendirilebilir kapsayıcılarında öğeleri — Örneğin, sıralanmış artan olarak. Sırasız ilişkilendirilebilir kapsayıcıları de kullanılabilir. İlişkilendirilebilir kapsayıcıları iki alt kümeler gruplandırılabilir: eşler ve ayarlar.

A `map`, bazen bir sözlük olarak başvurulan, bir anahtar/değer çiftinden oluşur. Anahtar sırasını belirlemek için kullanılır ve bu anahtarla ilişkili bir değerdir. Örneğin, bir `map` temsil eden bir metin ve her sözcüğün metin görünür sayısını temsil eden karşılık gelen değerler benzersiz her word anahtarları içerebilir. Sırasız sürümü `map` olan `unordered_map`. Daha fazla bilgi için bkz: [map sınıfı](../standard-library/map-class.md) ve [unordered_map sınıfı](../standard-library/unordered-map-class.md).

A `set` yalnızca artan bir kapsayıcı benzersiz öğelerinin — ayrıca anahtar değeridir. Sırasız sürümü `set` olan `unordered_set`. Daha fazla bilgi için bkz: [set sınıfı](../standard-library/set-class.md) ve [unordered_set sınıfı](../standard-library/unordered-set-class.md).

Her ikisi de `map` ve `set` yalnızca bir anahtar ya da kapsayıcıya eklenecek öğesi bir örneğine izin verilir. Öğeleri birden çok örneğini gerekirse, kullanın `multimap` veya `multiset`. Sırasız sürümleri `unordered_multimap` ve `unordered_multiset`. Daha fazla bilgi için bkz: [multimap sınıfı](../standard-library/multimap-class.md), [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md), [multiset sınıfı](../standard-library/multiset-class.md), ve [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).

Çift yönlü yineleyiciler sıralı eşlemeleri ve kümelerini destekler ve iletme yineleyiciler sırasız dekiler destekler. Daha fazla bilgi için bkz: [yineleyiciler](../standard-library/iterators.md).

### <a name="heterogeneous-lookup-in-associative-containers-c14"></a>Heterojen arama ilişkilendirilebilir kapsayıcılarında (C ++ 14)

İlişkilendirilebilir kapsayıcıları (harita, multimap, ayarlama ve multiset) şimdi artık anlamına gerekli gibi tam aynı nesne türü olarak anahtar veya üye işlevleri öğesinde geçirmek için destek heterojen arama sıralı `find()` ve `lower_bound()` . Bunun yerine, herhangi bir tür için geçirebilirsiniz aşırı yüklenmiş bir `operator<` tanımlı anahtar türü karşılaştırma sağlar.

Heterogenous arama belirttiğinizde bir katılımı temelinde etkin `std::less<>` veya `std::greater<>` kapsayıcı değişkeni aşağıda gösterildiği gibi bildirirken "functor elmas" karşılaştırıcı:

```cpp
std::set<BigObject, std::less<>> myNewSet;
```

Ardından varsayılan karşılaştırıcı kullanırsanız, kapsayıcı tam olarak C ++ 11 ve daha önce yaptığınız gibi davranır.

Aşağıdaki örnek, aşırı yüklemeyi gösterilmiştir `operator<` kullanıcılarının etkinleştirmek için bir `std::set` yalnızca geçirerek karşılaştırılabilir küçük bir dize her nesnenin için arama yapmak için `BigObject::id` üyesi.

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

Şu member eşlemesinde multimap İşlevler, kümesi ve multiset heterojen arama desteklemek için aşırı yüklü:

1. find

1. count

1. lower_bound

1. upper_bound

1. equal_range

## <a name="container-adapters"></a>Kapsayıcı bağdaştırıcıları

Bir kapsayıcı bağdaştırıcısı dizisi veya arabirim Basitlik ve daha anlaşılır olması için sınırlar ilişkilendirilebilir kapsayıcı çeşididir. Kapsayıcı bağdaştırıcılarını yineleyiciler desteklemez.

A `queue` kapsayıcı FIFO (ilk giren ilk çıkar) semantiği izler. İlk öğe *gönderilen*— diğer bir deyişle, sıraya eklenen — olması için ilk *Sil'i*— diğer bir deyişle, sıradan kaldırıldı. Daha fazla bilgi için bkz: [sınıfı sıraya](../standard-library/queue-class.md).

A `priority_queue` en yüksek değer olan öğeyi her zaman ilk sırada olacak şekilde, kapsayıcı düzenlenir. Daha fazla bilgi için bkz: [priority_queue sınıfı](../standard-library/priority-queue-class.md).

A `stack` kapsayıcı LIFO (son giren ilk çıkar) semantiği izler. Yığına son öğe Sil'i ilk öğedir. Daha fazla bilgi için bkz: [stack sınıfı](../standard-library/stack-class.md).

Kapsayıcı bağdaştırıcıları yineleyiciler desteklemediği için C++ Standart Kitaplığı algoritmalarıyla kullanılamaz. Daha fazla bilgi için bkz: [algoritmaları](../standard-library/algorithms.md).

## <a name="requirements-for-container-elements"></a>Kapsayıcı öğeleri için gereksinimler

Genel olarak, copyable olmaları durumunda öğeleri C++ Standart Kitaplığı kapsayıcıya eklenen her nesne türünde olabilir. Yalnızca taşınabilir öğeleri — Örneğin, olanlar gibi `vector<unique_ptr<T>>` kullanılarak oluşturulan `unique_ptr<>` üye bunları kopyalama işlevlerini çağırın yok sürece çalışmaz.

Yıkıcı bir özel durum izin verilmiyor.

İlişkilendirilebilir kapsayıcıları sıralı — bu makalenin önceki bölümlerinde açıklanan — tanımlı bir ortak karşılaştırma işleci olması gerekir. (Varsayılan olarak, işlecidir `operator<`, ile çalışmaz ancak bile türleri `operator<` desteklenir.

Bazı işlemler kapsayıcılarında ortak varsayılan bir oluşturucu ve bir ortak eşdeğer işleci de gerektirebilir. Örneğin, sırasız ilişkilendirilebilir kapsayıcıları eşitlik ve karma için desteği gerektirir.

## <a name="accessing-container-elements"></a>Kapsayıcı öğelere erişme

Kapsayıcı öğeler yineleyiciler kullanılarak erişilir. Daha fazla bilgi için bkz: [yineleyiciler](../standard-library/iterators.md).

> [!NOTE]
> Aynı zamanda [aralık tabanlı döngüler için](../cpp/range-based-for-statement-cpp.md) C++ Standart Kitaplığı koleksiyon yineleme.

## <a name="comparing-containers"></a>Kapsayıcıları karşılaştırma

Tüm kapsayıcıları işleci aşırı aynı öğe türüne sahip olan iki kapsayıcıları aynı türde karşılaştırmak için ==. Kullanabilirsiniz vektör Karşılaştırılacak ==\<dize > başka bir vektör için\<dize >, ancak bir vektör karşılaştırmak için kullanamazsınız\<dize > listesine\<dize > ya da bir vektör\<dize > vektör için \<char * >.  C ++ 98/03 kullandığınız [std::equal](algorithm-functions.md#equal) veya [std::mismatch](algorithm-functions.md#mismatch) farklı kapsayıcı türleri ve/veya öğe türleri karşılaştırmak için. C ++ 11'de de kullanabilirsiniz [std::is_permutation](algorithm-functions.md#is_permutation). Ancak tüm durumlarda işlevleri kapsayıcıları aynı uzunlukta varsayılmaktadır. İkinci aralığı, ardından tanımsız davranış sonuçları kısa ise. İkinci aralığı uzunsa karşılaştırma hiçbir zaman ilk aralığı sonunun ettiğinden sonuçları hala yanlış olabilir.

### <a name="comparing-dissimilar-containers-c14"></a>Farklı kapsayıcılar (C ++ 14) karşılaştırma

C ++ 14 ve daha sonra farklı kapsayıcılar ve/veya benzer öğeleri türleri birini kullanarak karşılaştırabileceğiniz **std::equal**, **std::mismatch**, veya **std::is_permutation**iki tam aralıkları ele aşırı işlev. Bu aşırı kapsayıcılarını farklı uzunlukta ile karşılaştırmanıza olanak sağlar. Bu aşırı kullanıcı hatalarına daha az açıktır ve ne zaman kapsayıcıları, farklı uzunlukta karşılaştırılır sabit zamanında false döndürmek için iyileştirilmiştir. Bu nedenle, (1) bir açıkça değil nedeniniz veya (2), kullanmakta olduğunuz sürece bu aşırı kullanmanız önerilir bir [std::list](../standard-library/list-class.md) çift aralıklı iyileştirmeler yararlı değil kapsayıcı.

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](../cpp/containers-modern-cpp.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
[\<Örnek kapsayıcı >](../standard-library/sample-container.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
