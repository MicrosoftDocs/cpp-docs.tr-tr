---
title: '&lt;Rasgele&gt;'
ms.date: 08/24/2017
f1_keywords:
- <random>
helpviewer_keywords:
- random header
ms.assetid: 60afc25c-b162-4811-97c1-1b65398d4c57
ms.openlocfilehash: 540daa5bafa28b1d56c55daf33f0b5f5461c8ed6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320230"
---
# <a name="ltrandomgt"></a>&lt;Rasgele&gt;

Rasgele sayı oluşturma tesislerini tanımlar ve düzgün cereburlmayı sağlayan rasgele sayıların oluşturulmasını sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi** \<: rastgele>

**Ad alanı:** std

> [!NOTE]
> Rasgele \<> kitaplığı '#include <initializer_list>' ifadesini kullanır.

## <a name="summary"></a>Özet

*Rasgele sayı üreteci,* sözde rasgele değerler dizisi üreten bir nesnedir. Belirli bir aralıkta düzgün bir şekilde dağıtılan değerler üreten bir *jeneratör, Düzgün Rastgele Sayı Üreteci* (URNG) dir. Urng olarak işlev görmek üzere tasarlanmış bir sınıf şablonu, bu sınıfın bu makalede daha sonra tartışılan belirli ortak özelliklere sahipse, *altyapı* olarak adlandırılır. Bir URNG olabilir ve genellikle bir *dağıtım* ile birleştirilmiş tirng dağıtım tarafından `operator()` tanımlanan bir şekilde dağıtılan değerleri üretmek için dağıtım bir argüman olarak geçirerek.

Bu bağlantılar bu makalenin ana bölümlerine atlar:

- [Örnekler](#code)

- [Kategorize Listeleme](#listing)

- [Motorlar ve Dağıtımlar](#engdist)

- [Açıklamalar](#comments)

### <a name="quick-tips"></a>Hızlı İpuçları

Rastgele> kullanırken \<aklınızda bulundurmanız gereken bazı ipuçları şunlardır:

- Url'ler çoğu amaç için dağıtımlara göre şekillendirilmesi gereken ham bitler üretirler. (Doğrudan bir URNG kullandığından bunun önemli bir istisnası [std::shuffle()](../standard-library/algorithm-functions.md#shuffle) 'dır.)

- URNG veya dağıtımın tek bir anlık olarak aynı anda çağrılamaz, çünkü bir URNG veya dağıtım çalıştırmak bir değiştirme işlemidir. Daha fazla bilgi için [C++ Standart Kitaplığı'ndaki İş Parçacığı Güvenliği'ne](../standard-library/thread-safety-in-the-cpp-standard-library.md)bakın.

- Birkaç motorun [önceden tanımlanmış tipdefleri](#typedefs) sağlanır; bir motor kullanılıyorsa, urng oluşturmanın tercih edilen yoludur.

- Çoğu uygulama için en kullanışlı `mt19937` `uniform_int_distribution`eşleştirme, bu makalede daha sonra kod [örneğinde](#code) gösterildiği gibi, ile motordur.

\<Rasgele> üstbilgide seçim yapabileceğiniz birçok seçenek vardır ve bunlardan herhangi biri eski C `rand()`Runtime işlevine tercih edilir. Neyin nesi olduğu `rand()` ve rasgele \<> bu eksiklikleri nasıl giderdi hakkında bilgi için [bu videoyu](https://go.microsoft.com/fwlink/p/?linkid=397615)izleyin.

## <a name="examples"></a><a name="code"></a>Örnekler

Aşağıdaki kod örneği, bu durumda beş tanesi deterministic olmayan tohum ile oluşturulan bir jeneratör kullanarak bazı rasgele sayılar oluşturmak için nasıl gösterir.

```cpp
#include <random>
#include <iostream>

using namespace std;

int main()
{
    random_device rd;   // non-deterministic generator
    mt19937 gen(rd());  // to seed mersenne twister.
                        // replace the call to rd() with a
                        // constant value to get repeatable
                        // results.

    for (int i = 0; i < 5; ++i) {
        cout << gen() << " "; // print the raw output of the generator.
    }
    cout << endl;
}
```

```Output
2430338871 3531691818 2723770500 3252414483 3632920437
```

Bu yüksek kaliteli rasgele sayılar ve farklı bu program çalıştırılır her zaman olsa da, mutlaka yararlı bir aralıkta değildir. Aralığı denetlemek için, aşağıdaki kodda gösterildiği gibi tek düze bir dağılım kullanın:

```cpp
#include <random>
#include <iostream>

using namespace std;

int main()
{
    random_device rd;   // non-deterministic generator
    mt19937 gen(rd());  // to seed mersenne twister.
    uniform_int_distribution<> dist(1,6); // distribute results between 1 and 6 inclusive.

    for (int i = 0; i < 5; ++i) {
        cout << dist(gen) << " "; // pass the generator to the distribution.
    }
    cout << endl;
}
```

```Output
5 1 6 1 2
```

Sonraki kod örneği, bir vektörün ve dizinin içeriğini karıştıran düzgün dağılmış rasgele sayı üreteçleri ile daha gerçekçi bir kullanım örneği kümesini gösterir.

```cpp
// cl.exe /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <array>
#include <iostream>
#include <random>
#include <string>
#include <vector>
#include <functional> // ref()

using namespace std;

template <typename C> void print(const C& c) {
    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

template <class URNG>
void test(URNG& urng) {

    // Uniform distribution used with a vector
    // Distribution is [-5, 5] inclusive
    uniform_int_distribution<int> dist(-5, 5);
    vector<int> v;

    for (int i = 0; i < 20; ++i) {
        v.push_back(dist(urng));
    }

    cout << "Randomized vector: ";
    print(v);

    // Shuffle an array
    // (Notice that shuffle() takes a URNG, not a distribution)
    array<string, 26> arr = { { "H", "He", "Li", "Be", "B", "C", "N", "O", "F",
        "Ne", "Na", "Mg", "Al", "Si", "P", "S", "Cl", "Ar", "K", "Ca", "Sc",
        "Ti", "V", "Cr", "Mn", "Fe" } };

    shuffle(arr.begin(), arr.end(), urng);

    cout << "Randomized array: ";
    print(arr);
    cout << "--" << endl;
}

int main()
{
    // First run: non-seedable, non-deterministic URNG random_device
    // Slower but crypto-secure and non-repeatable.
    random_device rd;
    cout << "Using random_device URNG:" << endl;
    test(rd);

    // Second run: simple integer seed, repeatable results
    cout << "Using constant-seed mersenne twister URNG:" << endl;
    mt19937 engine1(12345);
    test(engine1);

    // Third run: random_device as a seed, different each run
    // (Desirable for most purposes)
    cout << "Using non-deterministic-seed mersenne twister URNG:" << endl;
    mt19937 engine2(rd());
    test(engine2);

    // Fourth run: "warm-up" sequence as a seed, different each run
    // (Advanced uses, allows more than 32 bits of randomness)
    cout << "Using non-deterministic-seed \"warm-up\" sequence mersenne twister URNG:" << endl;
    array<unsigned int, mt19937::state_size> seed_data;
    generate_n(seed_data.begin(), seed_data.size(), ref(rd));
    seed_seq seq(begin(seed_data), end(seed_data));
    mt19937 engine3(seq);
    test(engine3);
}
```

```Output
Using random_device URNG:
Randomized vector: 5 -4 2 3 0 5 -2 0 4 2 -1 2 -4 -3 1 4 4 1 2 -2
Randomized array: O Li V K C Ti N Mg Ne Sc Cl B Cr Mn Ca Al F P Na Be Si Ar Fe S He H
--
Using constant-seed mersenne twister URNG:
Randomized vector: 3 -1 -5 0 0 5 3 -4 -3 -4 1 -3 0 -3 -2 -4 5 1 -1 -1
Randomized array: Al O Ne Si Na Be C N Cr Mn H V F Sc Mg Fe K Ca S Ti B P Ar Cl Li He
--
Using non-deterministic-seed mersenne twister URNG:
Randomized vector: 5 -4 0 2 1 -2 4 4 -4 0 0 4 -5 4 -5 -1 -3 0 0 3
Randomized array: Si Fe Al Ar Na P B Sc H F Mg Li C Ti He N Mn Be O Ca Cr V K Ne Cl S
--
Using non-deterministic-seed "warm-up" sequence mersenne twister URNG:
Randomized vector: -1 3 -2 4 1 3 0 -5 5 -5 0 0 5 0 -3 3 -4 2 5 0
Randomized array: Si C Sc H Na O S Cr K Li Al Ti Cl B Mn He Fe Ne Be Ar V P Ca N Mg F
--
```

Bu kod, bir test şablonu işleviyle iki farklı rasgeleleştirme (tamsayılardan oluşan bir vektörü rasgeleleştirin ve dizili dizinlenmiş verileri karıştırır). Test işlevine yapılan ilk çağrı, kripto güvenli, deterministik olmayan, tohumsuz, tekraredilemez `random_device`URNG'yi kullanır. İkinci test çalışması `mersenne_twister_engine` URNG olarak kullanır, deterministik 32-bit sabit tohum ile, hangi sonuçlar tekrarlanabilir anlamına gelir. Üçüncü test 32-bit non-deterministic sonucu ile tohumları `mersenne_twister_engine` çalıştırın. `random_device` Dördüncü test çalışması, 32 bit'ten fazla `random_device` deterministik olmayan rastgelelik (ancak yine de kripto güvenli değil) veren sonuçlarla dolu bir [tohum dizisi](../standard-library/seed-seq-class.md) kullanarak bu konuda genişler. Daha fazla bilgi için okumaya devam edin.

## <a name="categorized-listing"></a><a name="listing"></a>Kategorize Listeleme

### <a name="uniform-random-number-generators"></a><a name="urngs"></a>Üniforma Rastgele Sayı Jeneratörleri

URL'ler genellikle bu özellikler açısından açıklanır:

1. **Dönem uzunluğu**: Oluşturulan sayıların dizisini yinelemek için kaç yineleme gerekir. Ne kadar uzun sürerse o kadar iyi.

2. **Performans**: Sayıların ne kadar hızlı oluşturulabileceği ve ne kadar bellek gerektiği. Ne kadar küçükse o kadar iyi.

3. **Kalite**: Oluşturulan dizinin gerçek rasgele sayılara ne kadar yakın olduğu. Buna genellikle "*rastgelelik*" denir.

Aşağıdaki \<bölümlerde, rasgele> üstbilgisinde sağlanan tek tip rasgele sayı üreteçleri (URL'ler) listelenerilmiştir.

#### <a name="non-deterministic-generator"></a><a name="rd"></a>Deterministik Olmayan Jeneratör

|||
|-|-|
|[random_device Sınıfı](../standard-library/random-device-class.md)|Harici bir aygıt kullanarak deterministik olmayan, şifreleme açısından güvenli bir rasgele sıra oluşturur. Genellikle bir motor tohum için kullanılır. Düşük performans, çok yüksek kalite. Daha fazla bilgi için [Açıklamalar'a](#comments)bakın.|

#### <a name="engine-typedefs-with-predefined-parameters"></a><a name="typedefs"></a>Önceden Tanımlanmış Parametrelerli Motor Tipleri

Anında motorlar ve motor adaptörleri için. Daha fazla bilgi için [Bkz. Motorlar ve Dağıtımlar.](#engdist)

- `default_random_engine`Varsayılan motor.

    ```cpp
    typedef mt19937 default_random_engine;
    ```

- `knuth_b`Knuth motoru.

    ```cpp
    typedef shuffle_order_engine<minstd_rand0, 256> knuth_b;
    ```

- `minstd_rand0`1988 minimal standart motor (Lewis, Goodman ve Miller, 1969).

    ```cpp
    typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
    ```

- `minstd_rand`Güncellenen minimum `minstd_rand0` standart motor (Park, Miller ve Stockmeyer, 1993).

    ```cpp
    typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
    ```

- `mt19937`32-bit Mersenne twister motoru (Matsumoto ve Nishimura, 1998).

    ```cpp
    typedef mersenne_twister_engine<
        unsigned int, 32, 624, 397,
        31, 0x9908b0df,
        11, 0xffffffff,
        7, 0x9d2c5680,
        15, 0xefc60000,
        18, 1812433253> mt19937;
    ```

- `mt19937_64`64-bit Mersenne twister motoru (Matsumoto ve Nishimura, 2000).

    ```cpp
    typedef mersenne_twister_engine<
        unsigned long long, 64, 312, 156,
        31, 0xb5026f5aa96619e9ULL,
        29, 0x5555555555555555ULL,
        17, 0x71d67fffeda60000ULL,
        37, 0xfff7eee000000000ULL,
        43, 6364136223846793005ULL> mt19937_64;
    ```

- `ranlux24`24-bit RANLUX motoru (Martin Lüscher ve Fred James, 1994).

    ```cpp
    typedef discard_block_engine<ranlux24_base, 223, 23> ranlux24;
    ```

- `ranlux24_base`Için bir üs `ranlux24`olarak kullanılır.

    ```cpp
    typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;
    ```

- `ranlux48`48-bit RANLUX motoru (Martin Lüscher ve Fred James, 1994).

    ```cpp
    typedef discard_block_engine<ranlux48_base, 389, 11> ranlux48;
    ```

- `ranlux48_base`Için bir üs `ranlux48`olarak kullanılır.

    ```cpp
    typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;
    ```

#### <a name="engine-templates"></a><a name="eng"></a>Motor Şablonları

Motor şablonları bağımsız URL olarak veya [motor adaptörlerine](#engadapt)geçirilen taban motorları olarak kullanılır. Genellikle bu [önceden tanımlanmış motor typedef](#typedefs) ile instantiated ve bir [dağıtım](#distributions)geçti. Daha fazla bilgi için [Motorlar ve Dağıtımlar](#engdist) bölümüne bakın.

|||
|-|-|
|[linear_congruential_engine Sınıfı](../standard-library/linear-congruential-engine-class.md)|Doğrusal uyumlu algoritmayı kullanarak rasgele bir dizi oluşturur. En basit ve en düşük kalite.|
|[mersenne_twister_engine Sınıfı](../standard-library/mersenne-twister-engine-class.md)|Mersenne twister algoritmasını kullanarak rastgele bir dizi oluşturur. En karmaşık ve random_device sınıfı dışında en yüksek kalitededir. Çok hızlı performans.|
|[subtract_with_carry_engine Sınıfı](../standard-library/subtract-with-carry-engine-class.md)|Taşıma ile çıkarma algoritmasını kullanarak rasgele bir sıra oluşturur. Bir gelişme `linear_congruential_engine`, ama çok daha `mersenne_twister_engine`düşük kalite ve performans .|

#### <a name="engine-adaptor-templates"></a><a name="engadapt"></a>Motor Adaptörü Şablonları

Motor adaptörleri, diğer (taban) motorları uyarlayan şablonlardır. Genellikle bu [önceden tanımlanmış motor typedef](#typedefs) ile instantiated ve bir [dağıtım](#distributions)geçti. Daha fazla bilgi için [Motorlar ve Dağıtımlar](#engdist) bölümüne bakın.

|||
|-|-|
|[discard_block_engine Sınıfı](../standard-library/discard-block-engine-class.md)|Temel motoru tarafından döndürülen değerleri atarak rasgele bir sıra oluşturur.|
|[independent_bits_engine Sınıfı](../standard-library/independent-bits-engine-class.md)|Temel motoru tarafından döndürülen değerlerden bitleri yeniden paketleyerek belirli sayıda bit içeren rasgele bir sıra oluşturur.|
|[shuffle_order_engine Sınıfı](../standard-library/shuffle-order-engine-class.md)|Temel motorundan döndürülen değerleri yeniden sıralayarak rasgele bir sıra oluşturur.|

[[Motor Şablonları](#eng)]

### <a name="random-number-distributions"></a><a name="distributions"></a>Rastgele Sayı Dağılımları

Aşağıdaki bölümlerde \<rasgele> üstbilgide sağlanan dağılımlar listelenir. Dağıtımlar, genellikle URNG çıktısını girdi olarak kullanan ve çıktıyı tanımlanmış istatistiksel olasılık yoğunluğu işlevi yle dağıtan bir işlem sonrası mekanizmadır. Daha fazla bilgi için [Motorlar ve Dağıtımlar](#engdist) bölümüne bakın.

#### <a name="uniform-distributions"></a>Tektip Dağılımlar

|||
|-|-|
|[uniform_int_distribution Sınıfı](../standard-library/uniform-int-distribution-class.md)|A, b] (dahil-dahil) aralığında \[bir aralık boyunca tek tip bir tamsayı değer dağılımı üretir.|
|[uniform_real_distribution Sınıfı](../standard-library/uniform-real-distribution-class.md)|Yarı açık aralıkta [a, b) (dahil-özel) aralık boyunca tek tip gerçek (kayan nokta) değer dağılımı üretir.|
|[generate_canonical](../standard-library/random-functions.md#generate_canonical)|[0, 1) (dahil-münhasır) arasında belirli bir hassasiyetin gerçek (kayan nokta) değerlerinin eşit dağılımını üretir.|

[[Rastgele Sayı Dağılımları](#distributions)]

#### <a name="bernoulli-distributions"></a>Bernoulli Dağıtımlar

|||
|-|-|
|[bernoulli_distribution Sınıfı](../standard-library/bernoulli-distribution-class.md)|**Bool** değerlerinin Bernoulli dağılımını üretir.|
|[binomial_distribution Sınıfı](../standard-library/binomial-distribution-class.md)|Tamsayı değerlerinin binom dağılımını üretir.|
|[geometric_distribution Sınıfı](../standard-library/geometric-distribution-class.md)|Tamsayı değerlerinin geometrik dağılımını üretir.|
|[negative_binomial_distribution Sınıfı](../standard-library/negative-binomial-distribution-class.md)|Tamsayı değerlerinin negatif binom dağılımını üretir.|

[[Rastgele Sayı Dağılımları](#distributions)]

#### <a name="normal-distributions"></a>Normal Dağılımlar

|||
|-|-|
|[cauchy_distribution Sınıfı](../standard-library/cauchy-distribution-class.md)|Gerçek (kayan nokta) değerlerin Cauchy dağılımını üretir.|
|[chi_squared_distribution Sınıfı](../standard-library/chi-squared-distribution-class.md)|Gerçek (kayan nokta) değerlerin ki-kare dağılımını üretir.|
|[fisher_f_distribution Sınıfı](../standard-library/fisher-f-distribution-class.md)|Gerçek (kayan nokta) değerlerin F dağılımı (Snedecor'un F dağılımı veya Fisher-Snedecor dağılımı olarak da bilinir) üretir.|
|[lognormal_distribution Sınıfı](../standard-library/lognormal-distribution-class.md)|Gerçek (kayan nokta) değerlerin günlük normal dağılımını üretir.|
|[normal_distribution Sınıfı](../standard-library/normal-distribution-class.md)|Gerçek (kayan nokta) değerlerin normal (Gauss) dağılımını üretir.|
|[student_t_distribution Sınıfı](../standard-library/student-t-distribution-class.md)|Öğrencinin gerçek *t*(kayan nokta) değerlerinin t-dağılımını üretir.|

[[Rastgele Sayı Dağılımları](#distributions)]

#### <a name="poisson-distributions"></a>Poisson Dağıtımları

|||
|-|-|
|[exponential_distribution Sınıfı](../standard-library/exponential-distribution-class.md)|Gerçek (kayan nokta) değerlerin üstel dağılımını üretir.|
|[extreme_value_distribution Sınıfı](../standard-library/extreme-value-distribution-class.md)|Gerçek (kayan nokta) değerlerin aşırı değer dağılımını üretir.|
|[gamma_distribution Sınıfı](../standard-library/gamma-distribution-class.md)|Gerçek (kayan nokta) değerlerin gama dağılımını üretir.|
|[poisson_distribution Sınıfı](../standard-library/poisson-distribution-class.md)|Tamsayı değerlerinin Poisson dağılımını üretir.|
|[weibull_distribution Sınıfı](../standard-library/weibull-distribution-class.md)|Gerçek (kayan nokta) değerlerin Weibull dağılımını üretir.|

[[Rastgele Sayı Dağılımları](#distributions)]

#### <a name="sampling-distributions"></a>Örnekleme Dağılımları

|||
|-|-|
|[discrete_distribution Sınıfı](../standard-library/discrete-distribution-class.md)|Ayrı bir tamsayı dağıtımı üretir.|
|[piecewise_constant_distribution Sınıfı](../standard-library/piecewise-constant-distribution-class.md)|Gerçek (kayan nokta) değerlerin parça olarak sabit dağılımını üretir.|
|[piecewise_linear_distribution Sınıfı](../standard-library/piecewise-linear-distribution-class.md)|Gerçek (kayan nokta) değerlerin parça yönünde doğrusal dağılımını üretir.|

[[Rastgele Sayı Dağılımları](#distributions)]

### <a name="utility-functions"></a>Yardımcı Program Fonksiyonları

Bu bölümde, rasgele> üstbilgide sağlanan genel yardımcı program işlevleri listelemektedir. \<

|||
|-|-|
|[seed_seq Sınıfı](../standard-library/seed-seq-class.md)|Önyargılı olmayan bir şifreli tohum dizisi oluşturur. Rasgele variat akışlarının çoğaltılmasını önlemek için kullanılır. Birçok URL motorlardan anında olduğunda kullanışlıdır.|

### <a name="operators"></a>İşleçler

Bu \<bölümde, rasgele> üstbilgisinde sağlanan işleçler listelenir.

|||
|-|-|
|`operator==`|Operatörün sol tarafındaki URNG'nin sağ taraftaki motora eşit olup olmadığını test edin.|
|`operator!=`|Operatörün sol tarafındaki URNG'nin sağ taraftaki motora eşit olup olmadığını test edin.|
|`operator<<`|Bir akışa durum bilgilerini yazar.|
|`operator>>`|Bir akıştan durum bilgilerini ayıklar.|

## <a name="engines-and-distributions"></a><a name="engdist"></a>Motorlar ve Dağıtımlar

\<Rasgele> tanımlanan bu sınıf şablonu kategorilerinin her biri hakkında bilgi için aşağıdaki bölümlere bakın. Bu sınıf şablonu kategorilerinin her ikisi de bir tür bir bağımsız değişken olarak alır ve aşağıdaki gibi, gerçek bir bağımsız değişken türü olarak izin verilen tür özelliklerini açıklamak için paylaşılan şablon parametre adları kullanın:

- `IntType`**kısa,** **int,** **uzun,** **uzun,** **imzasız kısa,** **imzasız int,** **imzasız uzun**veya **imzasız uzun gösterir.**

- `UIntType`**imzasız kısa,** **imzasız int,** **imzasız uzun**veya **imzasız uzun uzun**gösterir.

- `RealType`**float,** **double**veya **long double'ı**gösterir.

### <a name="engines"></a>Motor

[Motor Şablonları](#eng) ve [Motor Adaptörü Şablonları,](#engadapt) parametreleri oluşturulan jeneratörü özelleştiren şablonlardır.

*Motor,* örnekleri (jeneratörler) en az ve maksimum değer arasında eşit olarak dağıtılan rasgele sayıların kaynağı olarak hareket eden bir sınıf veya sınıf şablonudur. Bir *motor adaptörü,* başka bir rasgele sayı motoru tarafından üretilen değerleri alarak ve bu değerlere bir tür algoritma uygulayarak farklı rasgelelik özelliklerine sahip bir dizi değer sunar.

Her motor ve motor adaptörü aşağıdaki üyelere sahiptir:

- `typedef``numeric-type` tarafından `operator()`döndürülen `result_type` türüdür. Anlık `numeric-type` olarak şablon parametresi olarak geçirilir.

- `result_type operator()`ve `min()` `max()`. arasında düzgün bir şekilde dağıtılan değerleri döndürür.

- `result_type min()`jeneratörün tarafından döndürülen minimum değeri `operator()`döndürür. Motor adaptörleri temel motorun `min()` sonucunu kullanır.

- `result_type max()`jeneratörün tarafından döndürülen maksimum değeri `operator()`döndürür. İntegral (ayrılmaz değerli) bir tür `max()` olduğunda, `result_type` gerçekte döndürülebilen (dahil) maksimum değerdir; kayan nokta (gerçek değerli) türü `result_type` olduğunda, `max()` döndürülebilecek tüm değerlerden (dahil olmayan) en küçük değerdir. Motor adaptörleri temel motorun `max()` sonucunu kullanır.

- `void seed(result_type s)`tohum değeri `s`ile jeneratör tohumları . Motorlar için imza `void seed(result_type s = default_seed)` varsayılan parametre desteği içindir (motor `void seed()`adaptörleri ayrı bir tanım tanımlar, sonraki alt bölüme bakın).

- `template <class Seq> void seed(Seq& q)`[tohumlar bir seed_seq](../standard-library/seed-seq-class.md)`Seq`kullanarak jeneratör .

- Çağırarak sanki tohumlu bir jeneratör oluşturur bağımsız değişkeni `result_type x` ile açık bir yapıcı . `seed(x)`

- Çağırarak sanki tohumlu bir jeneratör oluşturur bağımsız değişkeni `seed_seq& seq` ile açık bir yapıcı . `seed(seq)`

- `void discard(unsigned long long count)`zamanları `operator()` `count` etkili bir şekilde çağırır ve her değeri atar.

**Motor adaptörleri** ayrıca bu`Engine` üyeleri destekler (temel motorun türünü atabilen bir motor adaptörünün ilk şablon parametresitir):

- Temel motorun varsayılan oluşturucusundan geliyormuş gibi jeneratörü başlatmayı sağlamak için varsayılan bir oluşturucu.

- Bağımsız değişkeni olan `const Engine& eng`açık bir yapıcı. Bu temel motoru kullanarak kopyalama yapımını desteklemek içindir.

- Bağımsız değişkeni olan `Engine&& eng`açık bir yapıcı. Bu, temel motoru kullanarak taşıma yapımını desteklemektir.

- `void seed()`temel motorun varsayılan tohum değeri ile jeneratörü devreye alır.

- `const Engine& base()`jeneratörü oluşturmak için kullanılan temel motoru döndüren özellik işlevi.

Her motor, *state* sonraki çağrılar tarafından oluşturulacak değerlerin sırasını belirleyen `operator()`bir durum tutar. Aynı tip motorlardan alınan iki jeneratörün durumları kullanılarak `operator==` karşılaştırılabilir ve. `operator!=` İki durum eşit olarak karşılaştırırsa, aynı değer sırasını oluştururlar. Bir nesnenin durumu, üreteci kullanılarak 32 bit imzasız değerler dizisi `operator<<` olarak bir akışa kaydedilebilir. Devlet onu kurtararak değişmez. Kaydedilmiş bir durum kullanılarak `operator>>`aynı türdeki bir motordan anında jeneratör içine okunabilir.

### <a name="distributions"></a>Dağıtım

[Rasgele Sayı Dağılımları,](#distributions) örnekleri, bir motordan elde edilen düzgün dağılmış rasgele sayılar akışını belirli bir dağılıma sahip rasgele sayılar akışına dönüştüren bir sınıf veya sınıf şablonudur. Her dağıtımaşağıdaki üyeleri vardır:

- `typedef``numeric-type` `result_type` `operator()` Anlık `numeric-type` olarak şablon parametresi olarak geçirilir.

- `template <class URNG> result_type operator()(URNG& gen)`eşit olarak dağıtılan rasgele değerlerin kaynağı ve dağıtımın depolanan `gen` *parametreleri*kullanılarak, dağılımın tanımına göre dağıtılan değerleri döndürür.

- `template <class URNG> result_type operator()(URNG& gen, param_type p)`tek tip olarak dağıtılan rasgele değerlerin kaynağı `gen` ve parametreler yapısı `p`olarak kullanarak, dağılımın tanımına uygun olarak dağıtılan değerleri döndürür.

- `typedef`opsiyonel olarak geçirilen parametrelerpaketidir `operator()` ve iade değerini oluşturmak için depolanan parametrelerin yerine kullanılır. `unspecified-type` `param_type`

- Bir `const param&` oluşturucu, depolanan parametreleri bağımsız değişkeninden başolarak çözer.

- `param_type param() const`depolanan parametreleri alır.

- `void param(const param_type&)`depolanan parametreleri bağımsız değişkeninden ayarlar.

- `result_type min()`dağıtımın `operator()`.

- `result_type max()``operator()`dağıtımın. İntegral (ayrılmaz değerli) bir tür `max()` olduğunda, `result_type` gerçekte döndürülebilen (dahil) maksimum değerdir; kayan nokta (gerçek değerli) türü `result_type` olduğunda, `max()` döndürülebilecek tüm değerlerden (dahil olmayan) en küçük değerdir.

- `void reset()`önbelleğe alınan değerleri atar, böylece bir sonraki `operator()` çağrının sonucu çağrıdan önce motordan elde edilen değerlere bağlı değildir.

Parametre yapısı, dağıtım için gereken tüm parametreleri depolayan bir nesnedir. Şunları içerir:

- `typedef``distribution-type` , dağılımının `distribution_type`türüdür.

- Dağıtım oluşturucuları almak aynı parametre listeleri almak bir veya daha fazla oluşturucular.

- Dağıtımla aynı parametre erişim işlevleri.

- Eşitlik ve eşitsizlik karşılaştırma işleçleri.

Daha fazla bilgi için, bu makalede daha önce bağlantılı olan bu alt konuya bakın.

## <a name="remarks"></a><a name="comments"></a>Açıklamalar

Visual Studio'da son derece kullanışlı iki`mt19937` `random_device`URL vardır ve bu karşılaştırma tablosunda gösterildiği gibi:

|ÜRNG|Hızlı|Kripto güvenli|Tohumlanabilir|Belirlenimci|
|----------|-----------|---------------------|---------------|--------------------|
|`mt19937`|Evet|Hayır|Evet|Evet<sup>*</sup>|
|`random_device`|Hayır|Evet|Hayır|Hayır|

<sup>* Bilinen bir tohum ile birlikte verildiğinde.</sup>

ISO C++ Standardı şifreleme `random_device` açısından güvenli olmasını gerektirmese de Visual Studio'da şifreleme açısından güvenli olması için uygulanır. ("Şifreleme açısından güvenli" terimi garanti anlamına gelmez, ancak minimum düzeyde entropi anlamına gelir ve bu nedenle, öngörülebilirlik düzeyi-belirli bir rasgeleleştirme algoritması sağlar. Daha fazla bilgi için, Wikipedia makale [Cryptographically güvenli pseudorandom sayı üreteci](https://go.microsoft.com/fwlink/p/?linkid=398017)bakın .) ISO C++ Standardı bunu gerektirmediği için, `random_device` diğer platformlar basit bir sözde rasgele sayı üreteci (şifreleme olarak güvenli değil) olarak uygulayabilir ve yalnızca başka bir jeneratör için tohum kaynağı olarak uygun olabilir. Platformlar arası kod `random_device` kullanırken bu platformlar için belgeleri kontrol edin.

Tanım olarak, `random_device` sonuçlar tekrarlanabilir değildir ve bir yan etkisi diğer URL'lere göre önemli ölçüde daha yavaş çalışabilir olmasıdır. Şifreleme açısından güvenli kullanım `mt19937` veya benzer bir altyapı olması gerekmeyen çoğu uygulama, kod `random_device` [örneğinde](#code)gösterildiği gibi bir çağrı ile tohumlamak isteyebilirsiniz rağmen.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)
