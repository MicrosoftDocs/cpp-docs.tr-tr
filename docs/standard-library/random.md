---
title: '&lt;random &gt;'
ms.date: 08/24/2017
f1_keywords:
- <random>
helpviewer_keywords:
- random header
ms.assetid: 60afc25c-b162-4811-97c1-1b65398d4c57
ms.openlocfilehash: fbff6123c810251109dd48d74a5bd4632793be6f
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689097"
---
# <a name="ltrandomgt"></a>&lt;random &gt;

Rastgele sayı oluşturma tesislerini tanımlar, tek düzen dağıtılmış rastgele sayılar oluşturulmasına izin verir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<random >

**Ad alanı:** std

> [!NOTE]
> @No__t_0random > Kitaplığı ' #include < initializer_list > ' ifadesini kullanır.

## <a name="summary"></a>Özet

*Rastgele sayı Oluşturucu* , sözde rastgele değerler dizisi üreten bir nesnedir. Belirli bir aralıkta eşit olarak dağıtılan değerleri oluşturan bir Oluşturucu, *tek bir rastgele sayı Oluşturucu* (URNG). Bir URNG işlevi görecek şekilde tasarlanan bir sınıf şablonu, bu sınıfta daha sonra açıklanan belirli ortak nitelikleri varsa, bir *motor* olarak adlandırılır. Bir URNG, dağıtım tarafından tanımlanan bir şekilde dağıtılan değerler oluşturmak için, dağıtım `operator()` bir bağımsız değişken olarak bir bağımsız değişken olarak geçirerek bir *dağıtım* ile birleştirilir.

Bu bağlantılar, bu makalenin başlıca bölümlerine atlayın:

- [Örnekler](#code)

- [Kategorilere ayrılmış liste](#listing)

- [Altyapılar ve dağıtımlar](#engdist)

- [Açıklamalarının](#comments)

### <a name="quick-tips"></a>Hızlı Ipuçları

@No__t_0random > kullanırken göz önünde bulundurmanız gereken bazı ipuçları aşağıda verilmiştir:

- Çoğu amaçla, URNGs dağıtımlar tarafından şekillendirilmiş olması gereken ham bitleri üretir. (Bunun için bir önemli özel durumu, doğrudan bir URNG kullandığından [std:: karıştır ()](../standard-library/algorithm-functions.md#shuffle) .)

- Bir URNG veya dağıtım çalıştırmak, bir URNG veya dağıtımı çalıştırmak bir değiştirme işlemi olduğundan, bir URNG veya dağıtımın tek bir örneklenmesi güvenli şekilde çağrılamaz. Daha fazla bilgi için bkz. [ C++ standart kitaplıkta iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md).

- Birkaç altyapıya [önceden tanımlanmış tür tanımları](#typedefs) sağlanır; Bu, bir motor kullanılıyorsa bir URNG oluşturmak için tercih edilen yoldur.

- Çoğu uygulama için en yararlı eşleştirme, bu makalenin ilerleyen kısımlarında [kod örneğinde](#code) gösterildiği gibi, `uniform_int_distribution` olan `mt19937` altyapısıdır.

@No__t_0random > üst bilgisinde seçebileceğiniz pek çok seçenek vardır ve bunlardan herhangi biri, eski C çalışma zamanı işlevi `rand()` tercih edilir. @No__t_0 nelerin yanlış olduğu ve \<random > Bu eksiklikleri nasıl ele aldığı hakkında daha fazla bilgi için [Bu videoya](https://go.microsoft.com/fwlink/p/?linkid=397615)bakın.

## <a name="code"></a>Örnekler

Aşağıdaki kod örneğinde, belirleyici olmayan bir çekirdek ile oluşturulan bir Oluşturucu kullanılarak bu örnekte beş bir rastgele sayının nasıl oluşturulacağı gösterilmektedir.

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

Bunlar yüksek kaliteli rastgele sayılar ve bu program her çalıştırıldığında farklı olsa da, yararlı bir aralıkta olması gerekmez. Aralığı denetlemek için aşağıdaki kodda gösterildiği gibi Tekdüzen dağıtım kullanın:

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

Sonraki kod örneği, bir vektör ve dizi içeriğini karıştırarak benzer bir şekilde dağıtılmış rastgele sayı oluşturanlar içeren daha gerçekçi bir kullanım örnekleri kümesi gösterir.

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

Bu kod, bir test şablonu işleviyle, bir tamsayılar vektörünü rastgele olarak ve dizinli veri dizisini karışarak iki farklı randomizations gösterir. Test işlevine yapılan ilk çağrı, şifreleme güvenli, belirleyici olmayan, güvenilir olmayan, yinelenebilir olmayan, tekrarlanabilir ve `random_device`. İkinci test çalışması, 32 bitlik bir sabit çekirdek olan `mersenne_twister_engine` URNG olarak kullanır, bu da sonuçların tekrarlanabilir olduğu anlamına gelir. Üçüncü test çalıştırması çekirdekler, `random_device` 32 bitlik belirleyici olmayan bir sonuçla `mersenne_twister_engine`. Dördüncü test çalışması bunu, 32 bitlik belirleyici olmayan rasgelelik (ancak yine de şifre güvenle) üzerinde etkin bir şekilde sunan `random_device` sonuçlarıyla doldurulmuş bir [çekirdek sırası](../standard-library/seed-seq-class.md) kullanarak genişletir. Daha fazla bilgi için, makalesini okuyun.

## <a name="listing"></a>Kategorilere ayrılmış liste

###  <a name="urngs"></a>Tekdüzen rastgele sayı oluşturucuları

URNGs, genellikle şu özellikler açısından açıklanmıştır:

1. **Süre uzunluğu**: oluşturulan sayı dizisini yinelemek için kaç yineleme sürer. Daha uzun.

2. **Performans**: sayıların ne kadar hızlı üretilebileceğini ve ne kadar bellek aldığını öğrenin. Daha küçük olur.

3. **Kalite**: oluşturulan sıranın gerçek rastgele numaralarına ne kadar yakın olduğunu. Bu genellikle "*rasgelelik*" olarak adlandırılır.

Aşağıdaki bölümlerde, \<random > üstbilgisinde sunulan Tekdüzen rastgele sayı oluşturucuları (URNGs) listelenmektedir.

####  <a name="rd"></a>Belirleyici olmayan Oluşturucu

|||
|-|-|
|[random_device Sınıfı](../standard-library/random-device-class.md)|Dış bir cihaz kullanarak belirleyici olmayan ve şifreli güvenli rastgele bir sıra üretir. Genellikle bir altyapıyı temel almak için kullanılır. Düşük performans, çok yüksek kalite. Daha fazla bilgi için bkz. [açıklamalar](#comments).|

####  <a name="typedefs"></a>Önceden tanımlanmış parametrelerle motor Typedefs

Altyapı ve altyapı bağdaştırıcılarını örnekleniyor. Daha fazla bilgi için bkz. [altyapılar ve dağıtımlar](#engdist).

- varsayılan altyapıyı `default_random_engine`.

    ```cpp
    typedef mt19937 default_random_engine;
    ```

- Knuth altyapısını `knuth_b`.

    ```cpp
    typedef shuffle_order_engine<minstd_rand0, 256> knuth_b;
    ```

- `minstd_rand0` 1988 en düşük standart altyapı (Liwis, Goodman ve Miller, 1969).

    ```cpp
    typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
    ```

- `minstd_rand` minimum standart altyapıyı `minstd_rand0` (Park, Miller ve Stockmeyer, 1993) güncelleştirildi.

    ```cpp
    typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
    ```

- `mt19937` 32-bit Mersenne bükücü Engine (Matsumoto ve ndiimura, 1998).

    ```cpp
    typedef mersenne_twister_engine<
        unsigned int, 32, 624, 397,
        31, 0x9908b0df,
        11, 0xffffffff,
        7, 0x9d2c5680,
        15, 0xefc60000,
        18, 1812433253> mt19937;
    ```

- `mt19937_64` 64-bit Mersenne bükücü Engine (Matsumoto ve ndiimura, 2000).

    ```cpp
    typedef mersenne_twister_engine<
        unsigned long long, 64, 312, 156,
        31, 0xb5026f5aa96619e9ULL,
        29, 0x5555555555555555ULL,
        17, 0x71d67fffeda60000ULL,
        37, 0xfff7eee000000000ULL,
        43, 6364136223846793005ULL> mt19937_64;
    ```

- `ranlux24` 24 bit RANLUX motoru (MarLüscher ve Fred James, 1994).

    ```cpp
    typedef discard_block_engine<ranlux24_base, 223, 23> ranlux24;
    ```

- `ranlux24` için temel olarak kullanılan `ranlux24_base`.

    ```cpp
    typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;
    ```

- `ranlux48` 48-bit RANLUX motoru (MarLüscher ve Fred James, 1994).

    ```cpp
    typedef discard_block_engine<ranlux48_base, 389, 11> ranlux48;
    ```

- `ranlux48` için temel olarak kullanılan `ranlux48_base`.

    ```cpp
    typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;
    ```

####  <a name="eng"></a>Altyapı şablonları

Altyapı şablonları, tek başına URNGs olarak veya [altyapı bağdaştırıcıları](#engadapt)'na geçirilen temel altyapılar olarak kullanılır. Bunlar genellikle [önceden tanımlanmış bir typedef](#typedefs) ve bir [dağıtıma](#distributions)geçirilmiş olarak oluşturulur. Daha fazla bilgi için [altyapılar ve dağıtımlar](#engdist) bölümüne bakın.

|||
|-|-|
|[linear_congruential_engine Sınıfı](../standard-library/linear-congruential-engine-class.md)|Doğrusal congruize algoritmasını kullanarak rastgele bir sıra üretir. En uyarlaması ve en düşük kalite.|
|[mersenne_twister_engine Sınıfı](../standard-library/mersenne-twister-engine-class.md)|Mersenne bükücü algoritmasını kullanarak rastgele bir sıra üretir. En karmaşık ve random_device sınıfı hariç en yüksek kalitedir. Çok hızlı performans.|
|[subtract_with_carry_engine Sınıfı](../standard-library/subtract-with-carry-engine-class.md)|Birlikte çıkart algoritmasını kullanarak rastgele bir sıra üretir. @No__t_0 geliştirmesi, ancak `mersenne_twister_engine` kıyasla daha düşük kalite ve performans.|

####  <a name="engadapt"></a>Motor bağdaştırıcı şablonları

Altyapı bağdaştırıcıları, diğer (temel) altyapıları uyarlayacakları şablonlardır. Bunlar genellikle [önceden tanımlanmış bir typedef](#typedefs) ve bir [dağıtıma](#distributions)geçirilmiş olarak oluşturulur. Daha fazla bilgi için [altyapılar ve dağıtımlar](#engdist) bölümüne bakın.

|||
|-|-|
|[discard_block_engine Sınıfı](../standard-library/discard-block-engine-class.md)|Temel altyapısının döndürdüğü değerleri atarak rastgele bir sıra üretir.|
|[independent_bits_engine Sınıfı](../standard-library/independent-bits-engine-class.md)|Taban altyapısı tarafından döndürülen değerlerden bitleri yeniden paketleyerek belirli bir bit sayısıyla rastgele bir sıra üretir.|
|[shuffle_order_engine Sınıfı](../standard-library/shuffle-order-engine-class.md)|Temel altyapısından döndürülen değerleri yeniden sıralayarak rastgele bir sıra üretir.|

[[Motor şablonları](#eng)]

###  <a name="distributions"></a>Rastgele sayı dağıtımları

Aşağıdaki bölümlerde \<random > üstbilgisinde sunulan dağıtımlar listelenmektedir. Dağıtımlar, genellikle giriş olarak URNG çıkışı kullanan ve çıktıyı tanımlı bir istatistiksel olasılık yoğunluğu işlevine dağıtan bir son işlem mekanizmasıdır. Daha fazla bilgi için [altyapılar ve dağıtımlar](#engdist) bölümüne bakın.

#### <a name="uniform-distributions"></a>Tekdüzen dağıtımları

|||
|-|-|
|[uniform_int_distribution Sınıfı](../standard-library/uniform-int-distribution-class.md)|Kapalı aralıktaki \[a, b] (kapsamlı dahil) bir Aralık boyunca tek bir tamsayı değer dağılımı üretir.|
|[uniform_real_distribution Sınıfı](../standard-library/uniform-real-distribution-class.md)|Yarı açık aralıkta [a, b) (dışlamalı) bir aralığa göre tek biçimli gerçek (kayan nokta) değer dağılımı üretir.|
|[generate_canonical](../standard-library/random-functions.md#generate_canonical)|[0, 1) (dahil) arasında belirli bir duyarlıkta gerçek (kayan nokta) değerlerinin eşit bir şekilde dağıtılmasını üretir.|

[[Rastgele sayı dağıtımları](#distributions)]

#### <a name="bernoulli-distributions"></a>Bernoulli dağıtımları

|||
|-|-|
|[bernoulli_distribution Sınıfı](../standard-library/bernoulli-distribution-class.md)|**Bool** değerlerinin bir Bernoulli dağılımı üretir.|
|[binomial_distribution Sınıfı](../standard-library/binomial-distribution-class.md)|Tamsayı değerlerinin binom dağılımını üretir.|
|[geometric_distribution Sınıfı](../standard-library/geometric-distribution-class.md)|Tamsayı değerlerinin geometrik dağılımını üretir.|
|[negative_binomial_distribution Sınıfı](../standard-library/negative-binomial-distribution-class.md)|Tamsayı değerlerinin negatif binom dağılımını üretir.|

[[Rastgele sayı dağıtımları](#distributions)]

#### <a name="normal-distributions"></a>Normal dağıtımlar

|||
|-|-|
|[cauchy_distribution Sınıfı](../standard-library/cauchy-distribution-class.md)|Gerçek (kayan nokta) değerlerinin bir Cauşy dağılımını üretir.|
|[chi_squared_distribution Sınıfı](../standard-library/chi-squared-distribution-class.md)|Gerçek (kayan nokta) değerlerinin çi-kare dağılımı üretir.|
|[fisher_f_distribution Sınıfı](../standard-library/fisher-f-distribution-class.md)|Gerçek (kayan nokta) değerlerinin bir F dağıtımını (Snedecor 'in F dağıtımı veya Fisher-Snedecor dağıtımı olarak da bilinir) oluşturur.|
|[lognormal_distribution Sınıfı](../standard-library/lognormal-distribution-class.md)|Gerçek (kayan nokta) değerleri için bir günlük-normal dağıtımı üretir.|
|[normal_distribution Sınıfı](../standard-library/normal-distribution-class.md)|Gerçek (kayan nokta) değerlerinin normal (Gauss) dağılımını üretir.|
|[student_t_distribution Sınıfı](../standard-library/student-t-distribution-class.md)|Öğrenci 'nin gerçek (kayan nokta) değerlerinin *t*dağılımı üretir.|

[[Rastgele sayı dağıtımları](#distributions)]

#### <a name="poisson-distributions"></a>Poisson dağıtımları

|||
|-|-|
|[exponential_distribution Sınıfı](../standard-library/exponential-distribution-class.md)|Gerçek (kayan nokta) değerlerinin üstel bir dağılımını üretir.|
|[extreme_value_distribution Sınıfı](../standard-library/extreme-value-distribution-class.md)|Gerçek (kayan nokta) değerleri için aşırı değer dağılımı üretir.|
|[gamma_distribution Sınıfı](../standard-library/gamma-distribution-class.md)|Gerçek (kayan nokta) değerlerinin gama dağılımını üretir.|
|[poisson_distribution Sınıfı](../standard-library/poisson-distribution-class.md)|Tamsayı değerlerinin Poisson dağılımını üretir.|
|[weibull_distribution Sınıfı](../standard-library/weibull-distribution-class.md)|Gerçek (kayan nokta) değerlerinin bir Weibull dağılımını üretir.|

[[Rastgele sayı dağıtımları](#distributions)]

#### <a name="sampling-distributions"></a>Örnekleme dağıtımları

|||
|-|-|
|[discrete_distribution Sınıfı](../standard-library/discrete-distribution-class.md)|Ayrı bir tamsayı dağılımı üretir.|
|[piecewise_constant_distribution Sınıfı](../standard-library/piecewise-constant-distribution-class.md)|Gerçek (kayan nokta) değerlerinin piecewise sabit bir dağılımını üretir.|
|[piecewise_linear_distribution Sınıfı](../standard-library/piecewise-linear-distribution-class.md)|Gerçek (kayan nokta) değerlerinin piecewise doğrusal bir dağılımını üretir.|

[[Rastgele sayı dağıtımları](#distributions)]

### <a name="utility-functions"></a>Yardımcı program Işlevleri

Bu bölümde, \<random > üst bilgisinde sunulan genel yardımcı program işlevleri listelenmektedir.

|||
|-|-|
|[seed_seq Sınıfı](../standard-library/seed-seq-class.md)|Taraflı olmayan, karıştırılmış bir çekirdek sırası üretir. Rastgele değişen akışların çoğaltılmasını önlemek için kullanılır. Altyapılardan birçok URNGs örneği oluşturulduğunda yararlı olur.|

### <a name="operators"></a>İşleçler

Bu bölümde \<random > üst bilgisinde belirtilen işleçler listelenmektedir.

|||
|-|-|
|`operator==`|İşlecin sol tarafındaki URNG 'in sağ taraftaki altyapıya eşit olup olmadığını sınar.|
|`operator!=`|İşlecin sol tarafındaki URNG 'in sağ taraftaki altyapıya eşit olup olmadığını sınar.|
|`operator<<`|Durum bilgilerini bir akışa yazar.|
|`operator>>`|Bir akıştan durum bilgilerini ayıklar.|

## <a name="engdist"></a>Altyapılar ve dağıtımlar

@No__t_0random > tanımlanan bu sınıf şablonu kategorilerinin her biri hakkında daha fazla bilgi için aşağıdaki bölümlere bakın. Bu sınıf şablonu kategorilerinin her ikisi de bir türü bağımsız değişken olarak alır ve gerçek bir bağımsız değişken türü olarak izin verilen türün özelliklerini aşağıda gösterildiği gibi, paylaşılan şablon parametre adlarını kullanır:

- `IntType`, bir **kısa**, **int**, **Long**, **Long Long**, **işaretsiz kısa**, **işaretsiz int**, **imzasız Long**veya **imzasız uzun süreyi**belirtir.

- `UIntType` **İmzasız kısa**, **işaretsiz int**, **imzasız uzun**veya **imzasız uzun süreyi**gösterir.

- `RealType`, **float**, **Double**veya **Long Double**olduğunu gösterir.

### <a name="engines"></a>Yapılarının

[Altyapı şablonları](#eng) ve [altyapı bağdaştırıcısı şablonları](#engadapt) , parametreleri oluşturulan oluşturucuyu özelleştiren şablonlardır.

*Motor* , örnekleri (oluşturucular) en düşük ve en yüksek değer arasında eşit olarak dağıtılan rastgele sayıların kaynağı olarak davranan bir sınıf veya sınıf şablonudur. Bir *altyapı bağdaştırıcısı* , başka bir rastgele sayı altyapısı tarafından oluşturulan değerleri alarak ve bu değerlere bazı tür bir algoritma uygulayarak farklı rastgele özellikleri olan bir değer dizisi sunar.

Her altyapı ve altyapı bağdaştırıcısında aşağıdaki Üyeler bulunur:

- `typedef` `numeric-type` `result_type`, oluşturucunun `operator()` tarafından döndürülen türdür. @No__t_0, örnek oluşturma sırasında bir şablon parametresi olarak geçirilir.

- `result_type operator()`, `min()` ve `max()` arasında eşit olarak dağıtılan değerleri döndürür.

- `result_type min()`, oluşturucunun `operator()` döndürdüğü en küçük değeri döndürür. Altyapı bağdaştırıcıları, temel altyapının `min()` sonucunu kullanır.

- `result_type max()`, oluşturucunun `operator()` döndürdüğü en büyük değeri döndürür. @No__t_0 integral (tamsayı değerli) bir tür olduğunda, `max()` gerçekten döndürülebilecek maksimum değerdir (dahil); `result_type` kayan nokta (gerçek değerli) bir tür olduğunda `max()`, döndürülebilecek tüm değerlerden daha büyük en küçük değerdir (dahil değildir). Altyapı bağdaştırıcıları, temel altyapının `max()` sonucunu kullanır.

- oluşturucuyu çekirdek değer `s` ile `void seed(result_type s)`. Altyapılar için imza varsayılan parametre desteği için `void seed(result_type s = default_seed)` (motor bağdaştırıcıları ayrı bir `void seed()` tanımlar, sonraki alt bölüme bakın).

- [seed_seq](../standard-library/seed-seq-class.md) `Seq` kullanarak oluşturucuyu `template <class Seq> void seed(Seq& q)`.

- @No__t_1 çağırarak bir Oluşturucu oluşturan `result_type x` bağımsız değişkenine sahip açık bir Oluşturucu.

- @No__t_1 çağırarak bir Oluşturucu oluşturan `seed_seq& seq` bağımsız değişkenine sahip açık bir Oluşturucu.

- `void discard(unsigned long long count)` `operator()` `count` sürelerini etkin bir şekilde çağırır ve her değeri atar.

**Altyapı bağdaştırıcıları** Ayrıca bu üyeleri destekler (`Engine`, bir altyapı bağdaştırıcısının ilk şablon parametresidir ve temel altyapının türünü tanımlayarak):

- Oluşturucuyu temel altyapının varsayılan oluşturucusundan gibi başlatmak için varsayılan bir Oluşturucu.

- Bağımsız değişken `const Engine& eng` açık bir Oluşturucu. Bu, temel altyapıyı kullanarak kopyalama oluşumunu destekliyoruz.

- Bağımsız değişken `Engine&& eng` açık bir Oluşturucu. Bu, temel altyapıyı kullanarak oluşturma oluşumunu destekliyoruz.

- oluşturucuyu temel altyapının varsayılan tohum değeri ile Başlatan `void seed()`.

- oluşturucuyu oluşturmak için kullanılan temel altyapıyı döndüren `const Engine& base()` Özellik işlevi.

Her motor, `operator()` için sonraki çağrılar tarafından oluşturulacak değerlerin sırasını belirleyen bir *durum* sağlar. Aynı türdeki altyapılardan oluşturulan iki jeneratların durumları `operator==` ve `operator!=` kullanılarak karşılaştırılabilir. İki durum eşit olarak karşılaştırıldığı takdirde aynı değer dizisini oluşturur. Bir nesnenin durumu, oluşturucunun `operator<<` kullanarak bir akışa 32 bitlik işaretsiz değerler dizisi olarak kaydedilebilir. Durum, kaydederek değiştirilmez. Kaydedilmiş bir durum, `operator>>` kullanılarak aynı türdeki bir altyapıdan örneklenmiş şekilde okunabilir.

### <a name="distributions"></a>Dağıtımları

[Rastgele bir sayı dağıtımları](#distributions) , örnekleri bir altyapıdan alınan bir eşit olarak dağıtılmış rastgele sayıların akışını belirli bir dağıtıma sahip rastgele sayıların akışına dönüştüren bir sınıf veya sınıf şablonudur. Her dağıtım aşağıdaki üyelere sahiptir:

- `typedef` `numeric-type` `result_type`, dağıtımın `operator()` tarafından döndürülen türdür. @No__t_0, örnek oluşturma sırasında bir şablon parametresi olarak geçirilir.

- `template <class URNG> result_type operator()(URNG& gen)`, dağıtım tanımına göre dağıtılan değerleri, bir tek düzen dağıtılmış rastgele değerler kaynağı ve *dağıtımın saklı parametreleri*olarak `gen` kullanarak döndürür.

- `template <class URNG> result_type operator()(URNG& gen, param_type p)`, dağıtım tanımına uygun olarak dağıtılan değerleri, bir tek düzen dağıtılmış rastgele değerler kaynağı ve parametre yapısı `p` `gen` kullanarak döndürür.

- `typedef` `unspecified-type` `param_type`, isteğe bağlı olarak `operator()` geçirilen parametrelerin paketidir ve dönüş değerini oluşturmak için depolanan parametrelerin yerine kullanılır.

- @No__t_0 Oluşturucu, bağımsız değişkeninden saklı parametreleri başlatır.

- `param_type param() const` saklı parametreleri alır.

- `void param(const param_type&)` bağımsız değişkeninden saklı parametreleri ayarlar.

- `result_type min()`, dağıtımın `operator()` tarafından döndürülen en küçük değeri döndürür.

- `result_type max()`, dağıtımın `operator()` tarafından döndürülen en büyük değeri döndürür. @No__t_0 integral (tamsayı değerli) bir tür olduğunda, `max()` gerçekten döndürülebilecek maksimum değerdir (dahil); `result_type` kayan nokta (gerçek değerli) bir tür olduğunda `max()`, döndürülebilecek tüm değerlerden daha büyük en küçük değerdir (dahil değildir).

- `void reset()`, tüm önbelleğe alınan değerleri atar, böylece `operator()` bir sonraki çağrının sonucu, çağrıdan önce altyapıdan alınan değerlere bağlı değildir.

Parametre yapısı, bir dağıtım için gereken tüm parametreleri depolayan bir nesnedir. Şunu içerir:

- Dağıtım türü olan `distribution_type` `distribution-type` `typedef`.

- Dağıtım oluşturucuları ile aynı parametre listelerini alan bir veya daha fazla Oluşturucu.

- Dağıtım olarak aynı parametre erişimi işlevleri.

- Eşitlik ve eşitsizlik karşılaştırma işleçleri.

Daha fazla bilgi için, bu makalede daha önce bağlanılan başvuru alt bilgilerine bakın.

## <a name="comments"></a>Açıklamalarının

Visual Studio 'da (Bu karşılaştırma tablosunda gösterildiği gibi) `mt19937` ve `random_device` olmak üzere iki son derece yararlı URNGs vardır:

|URNG|Hızlı|Şifreleme-güvenli|Seedable|Olmayan|
|----------|-----------|---------------------|---------------|--------------------|
|`mt19937`|Evet|Hayır|Evet|Evet<sup> *</sup>|
|`random_device`|Hayır|Evet|Hayır|Hayır|

<sup>* Bilinen bir çekirdek ile sağlandığında.</sup>

ISO C++ standardı `random_device` şifreli olarak güvenli hale getirmek zorunda olmamasına karşın, Visual Studio 'da şifreli olarak güvenli olacak şekilde uygulanır. ("Şifreli güvenli" terimi, güvence garantisi vermez, ancak en düşük düzey entropi anlamına gelir; bu nedenle, belirli bir rastgele seçme algoritması sağlar. Daha fazla bilgi için bkz. ıkipedi makalesi [şifreli pseudportaıdom numarası Oluşturucu](https://go.microsoft.com/fwlink/p/?linkid=398017).) ISO C++ standardı bunu gerektirmediğinden, diğer platformlar basit bir sözde rastgele sayı üreticisi (şifreli olmayan güvenli değil) olarak `random_device` uygulayabilir ve yalnızca başka bir Oluşturucu için çekirdek kaynağı olarak uygun olabilir. Platformlar arası kodda `random_device` kullanırken bu platformların belgelerini denetleyin.

Tanım olarak `random_device` sonuçları tekrarlanabilir değildir ve yan etkisi diğer URNGs 'ten önemli ölçüde daha yavaş çalışabilir. Şifreli olarak güvenli hale getirmek için gerekli olmayan çoğu uygulama `mt19937` veya benzer bir altyapıyı kullanır, ancak bunu [kod örneğinde](#code)gösterildiği gibi bir `random_device` çağrısıyla çekirdek hale getirmek isteyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
