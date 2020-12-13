---
description: 'Daha fazla bilgi edinin: &lt; Random&gt;'
title: '&lt;Fi&gt;'
ms.date: 08/24/2017
f1_keywords:
- <random>
helpviewer_keywords:
- random header
ms.assetid: 60afc25c-b162-4811-97c1-1b65398d4c57
ms.openlocfilehash: 4080e305620dbe4b8fa1674762c27ece4eccd0a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337967"
---
# <a name="ltrandomgt"></a>&lt;Fi&gt;

Rastgele sayı oluşturma tesislerini tanımlar, tek düzen dağıtılmış rastgele sayılar oluşturulmasına izin verir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<random>

**Ad alanı:** std

> [!NOTE]
> \<random>Kitaplık ' #include <initializer_list> ' ifadesini kullanır.

## <a name="summary"></a>Özet

*Rastgele sayı Oluşturucu* , sözde rastgele değerler dizisi üreten bir nesnedir. Belirli bir aralıkta eşit olarak dağıtılan değerleri oluşturan bir Oluşturucu, *tek bir rastgele sayı Oluşturucu* (URNG). Bir URNG işlevi görecek şekilde tasarlanan bir sınıf şablonu, bu sınıfta daha sonra açıklanan belirli ortak nitelikleri varsa, bir *motor* olarak adlandırılır. Bir URNG, dağıtım tarafından tanımlanan bir şekilde dağıtılan değerler oluşturmak için, bir dağıtım ile birlikte, dağıtım tarafından bir bağımsız değişken olarak  `operator()` dağıtılır.

Bu bağlantılar, bu makalenin başlıca bölümlerine atlayın:

- [Örnekler](#code)

- [Kategorilere ayrılmış liste](#listing)

- [Altyapılar ve dağıtımlar](#engdist)

- [Açıklamalar](#comments)

### <a name="quick-tips"></a>Hızlı Ipuçları

Kullanırken şunları göz önünde bulundurmanız gereken bazı ipuçları aşağıda verilmiştir \<random> :

- Çoğu amaçla, URNGs dağıtımlar tarafından şekillendirilmiş olması gereken ham bitleri üretir. (Bunun için bir önemli özel durumu, doğrudan bir URNG kullandığından [std:: karıştır ()](../standard-library/algorithm-functions.md#shuffle) .)

- Bir URNG veya dağıtım çalıştırmak, bir URNG veya dağıtımı çalıştırmak bir değiştirme işlemi olduğundan, bir URNG veya dağıtımın tek bir örneklenmesi güvenli şekilde çağrılamaz. Daha fazla bilgi için bkz. [C++ standart kitaplığı 'Nda Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md).

- Birkaç altyapıya [önceden tanımlanmış tür tanımları](#typedefs) sağlanır; Bu, bir motor kullanılıyorsa bir URNG oluşturmak için tercih edilen yoldur.

- Çoğu uygulama için en yararlı eşleştirme, `mt19937` `uniform_int_distribution` Bu makalenin ilerleyen kısımlarında [kod örneğinde](#code) gösterildiği gibi, ile altyapısıdır.

Üst bilgide aralarından seçim yapabileceğiniz pek çok seçenek vardır \<random> ve bunlardan herhangi biri, eski C çalışma zamanı işlevine tercih edilir `rand()` . İle ilgili nelerin yanlış olduğu ve bu eksiklikleri nasıl ele aldığı hakkında daha fazla bilgi için `rand()` \<random> [Bu videoya](https://go.microsoft.com/fwlink/p/?linkid=397615)bakın.

## <a name="examples"></a><a name="code"></a> Örnekler

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

Bu kod, bir test şablonu işleviyle, bir tamsayılar vektörünü rastgele olarak ve dizinli veri dizisini karışarak iki farklı randomizations gösterir. Test işlevine yapılan ilk çağrı, şifre güvenli, belirleyici olmayan, güvenilir olmayan, yinelenebilir olmayan, tekrarlamayan bir URNG kullanır `random_device` . İkinci test çalıştırması `mersenne_twister_engine` , belirleyici bir 32 bitlik sabit çekirdek olan URNG olarak kullanılır, bu da sonuçların tekrarlanabilir olduğu anlamına gelir. Üçüncü test çalıştırması, ' `mersenne_twister_engine` den 32 bitlik belirleyici olmayan bir sonuçla sahiptir `random_device` . Dördüncü test çalıştırması, sonuçlarla doldurulmuş bir [çekirdek sırası](../standard-library/seed-seq-class.md) kullanarak `random_device` , 32 bitlik belirleyici olmayan rasgelelik (ancak yine de şifre güvenli) olarak daha fazla değer veren bir çekirdek sıra kullanarak bunu genişletir. Daha fazla bilgi için, makalesini okuyun.

## <a name="categorized-listing"></a><a name="listing"></a> Kategorilere ayrılmış liste

### <a name="uniform-random-number-generators"></a><a name="urngs"></a> Tekdüzen rastgele sayı oluşturucuları

URNGs, genellikle şu özellikler açısından açıklanmıştır:

1. **Süre uzunluğu**: oluşturulan sayı dizisini yinelemek için kaç yineleme sürer. Daha uzun.

2. **Performans**: sayıların ne kadar hızlı üretilebileceğini ve ne kadar bellek aldığını öğrenin. Daha küçük olur.

3. **Kalite**: oluşturulan sıranın gerçek rastgele numaralarına ne kadar yakın olduğunu. Bu genellikle "*rasgelelik*" olarak adlandırılır.

Aşağıdaki bölümlerde, üst bilgide sunulan Tekdüzen rastgele sayı oluşturucuları (URNGs) listelenmektedir \<random> .

#### <a name="non-deterministic-generator"></a><a name="rd"></a> Belirleyici olmayan Oluşturucu

[random_device sınıfı](../standard-library/random-device-class.md)\
Dış bir cihaz kullanarak belirleyici olmayan ve şifreli güvenli rastgele bir sıra üretir. Genellikle bir altyapıyı temel almak için kullanılır. Düşük performans, çok yüksek kalite. Daha fazla bilgi için bkz. [açıklamalar](#comments).

#### <a name="engine-typedefs-with-predefined-parameters"></a><a name="typedefs"></a> Önceden tanımlanmış parametrelerle motor Typedefs

Altyapı ve altyapı bağdaştırıcılarını örnekleniyor. Daha fazla bilgi için bkz. [altyapılar ve dağıtımlar](#engdist).

- `default_random_engine` Varsayılan motor.

    ```cpp
    typedef mt19937 default_random_engine;
    ```

- `knuth_b` Knuth altyapısı.

    ```cpp
    typedef shuffle_order_engine<minstd_rand0, 256> knuth_b;
    ```

- `minstd_rand0` 1988 en düşük standart altyapı (Liwis, Goodman ve Miller, 1969).

    ```cpp
    typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
    ```

- `minstd_rand` Minimum standart motor `minstd_rand0` (Park, Miller ve Stockmeyer, 1993) güncelleştirildi.

    ```cpp
    typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
    ```

- `mt19937` 32-bit Mersenne bükücü altyapısı (Matsumoto ve ndiimura, 1998).

    ```cpp
    typedef mersenne_twister_engine<
        unsigned int, 32, 624, 397,
        31, 0x9908b0df,
        11, 0xffffffff,
        7, 0x9d2c5680,
        15, 0xefc60000,
        18, 1812433253> mt19937;
    ```

- `mt19937_64` 64-bit Mersenne bükücü altyapısı (Matsumoto ve ndiimura, 2000).

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

- `ranlux24_base` İçin temel olarak kullanılır `ranlux24` .

    ```cpp
    typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;
    ```

- `ranlux48` 48-bit RANLUX motoru (MarLüscher ve Fred James, 1994).

    ```cpp
    typedef discard_block_engine<ranlux48_base, 389, 11> ranlux48;
    ```

- `ranlux48_base` İçin temel olarak kullanılır `ranlux48` .

    ```cpp
    typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;
    ```

#### <a name="engine-templates"></a><a name="eng"></a> Altyapı şablonları

Altyapı şablonları, tek başına URNGs olarak veya [altyapı bağdaştırıcıları](#engadapt)'na geçirilen temel altyapılar olarak kullanılır. Bunlar genellikle [önceden tanımlanmış bir typedef](#typedefs) ve bir [dağıtıma](#distributions)geçirilmiş olarak oluşturulur. Daha fazla bilgi için [altyapılar ve dağıtımlar](#engdist) bölümüne bakın.

|Ad|Açıklama|
|-|-|
|[linear_congruential_engine sınıfı](../standard-library/linear-congruential-engine-class.md)|Doğrusal congruize algoritmasını kullanarak rastgele bir sıra üretir. En uyarlaması ve en düşük kalite.|
|[mersenne_twister_engine sınıfı](../standard-library/mersenne-twister-engine-class.md)|Mersenne bükücü algoritmasını kullanarak rastgele bir sıra üretir. En karmaşıktır ve random_device sınıfı hariç en yüksek kalitedir. Çok hızlı performans.|
|[subtract_with_carry_engine sınıfı](../standard-library/subtract-with-carry-engine-class.md)|Birlikte çıkart algoritmasını kullanarak rastgele bir sıra üretir. Üzerinde bir geliştirme `linear_congruential_engine` , ancak çok daha düşük kalite ve performans `mersenne_twister_engine` .|

#### <a name="engine-adaptor-templates"></a><a name="engadapt"></a> Motor bağdaştırıcı şablonları

Altyapı bağdaştırıcıları, diğer (temel) altyapıları uyarlayacakları şablonlardır. Bunlar genellikle [önceden tanımlanmış bir typedef](#typedefs) ve bir [dağıtıma](#distributions)geçirilmiş olarak oluşturulur. Daha fazla bilgi için [altyapılar ve dağıtımlar](#engdist) bölümüne bakın.

|Ad|Açıklama|
|-|-|
|[discard_block_engine sınıfı](../standard-library/discard-block-engine-class.md)|Temel altyapısının döndürdüğü değerleri atarak rastgele bir sıra üretir.|
|[independent_bits_engine sınıfı](../standard-library/independent-bits-engine-class.md)|Taban altyapısı tarafından döndürülen değerlerden bitleri yeniden paketleyerek belirli bir bit sayısıyla rastgele bir sıra üretir.|
|[shuffle_order_engine sınıfı](../standard-library/shuffle-order-engine-class.md)|Temel altyapısından döndürülen değerleri yeniden sıralayarak rastgele bir sıra üretir.|

[[Motor şablonları](#eng)]

### <a name="random-number-distributions"></a><a name="distributions"></a> Rastgele sayı dağıtımları

Aşağıdaki bölümlerde, üst bilgide sunulan dağıtımlar listelenmektedir \<random> . Dağıtımlar, genellikle giriş olarak URNG çıkışı kullanan ve çıktıyı tanımlı bir istatistiksel olasılık yoğunluğu işlevine dağıtan bir son işlem mekanizmasıdır. Daha fazla bilgi için [altyapılar ve dağıtımlar](#engdist) bölümüne bakın.

#### <a name="uniform-distributions"></a>Tekdüzen dağıtımları

|Ad|Açıklama|
|-|-|
|[uniform_int_distribution sınıfı](../standard-library/uniform-int-distribution-class.md)|Kapalı aralıktaki \[ a, b] (kapsamlı) bir aralıktaki tek bir tamsayı değer dağılımı üretir.|
|[uniform_real_distribution sınıfı](../standard-library/uniform-real-distribution-class.md)|Yarı açık aralıkta [a, b) (dışlamalı) bir aralığa göre tek biçimli gerçek (kayan nokta) değer dağılımı üretir.|
|[generate_canonical](../standard-library/random-functions.md#generate_canonical)|[0, 1) (dahil) arasında belirli bir duyarlıkta gerçek (kayan nokta) değerlerinin eşit bir şekilde dağıtılmasını üretir.|

[[Rastgele sayı dağıtımları](#distributions)]

#### <a name="bernoulli-distributions"></a>Bernoulli dağıtımları

|Ad|Açıklama|
|-|-|
|[bernoulli_distribution Sınıfı](../standard-library/bernoulli-distribution-class.md)|Değerlerin bir Bernoulli dağılımı üretir **`bool`** .|
|[binomial_distribution sınıfı](../standard-library/binomial-distribution-class.md)|Tamsayı değerlerinin binom dağılımını üretir.|
|[geometric_distribution sınıfı](../standard-library/geometric-distribution-class.md)|Tamsayı değerlerinin geometrik dağılımını üretir.|
|[negative_binomial_distribution sınıfı](../standard-library/negative-binomial-distribution-class.md)|Tamsayı değerlerinin negatif binom dağılımını üretir.|

[[Rastgele sayı dağıtımları](#distributions)]

#### <a name="normal-distributions"></a>Normal dağıtımlar

|Ad|Açıklama|
|-|-|
|[cauchy_distribution sınıfı](../standard-library/cauchy-distribution-class.md)|Gerçek (kayan nokta) değerlerinin bir Cauşy dağılımını üretir.|
|[chi_squared_distribution sınıfı](../standard-library/chi-squared-distribution-class.md)|Gerçek (kayan nokta) değerlerinin çi-kare dağılımı üretir.|
|[fisher_f_distribution sınıfı](../standard-library/fisher-f-distribution-class.md)|Gerçek (kayan nokta) değerlerinin bir F dağıtımını (Snedecor 'in F dağıtımı veya Fisher-Snedecor dağıtımı olarak da bilinir) oluşturur.|
|[lognormal_distribution sınıfı](../standard-library/lognormal-distribution-class.md)|Gerçek (kayan nokta) değerleri için bir günlük-normal dağıtımı üretir.|
|[normal_distribution sınıfı](../standard-library/normal-distribution-class.md)|Gerçek (kayan nokta) değerlerinin normal (Gauss) dağılımını üretir.|
|[student_t_distribution sınıfı](../standard-library/student-t-distribution-class.md)|Öğrenci 'nin gerçek (kayan nokta) değerlerinin *t* dağılımı üretir.|

[[Rastgele sayı dağıtımları](#distributions)]

#### <a name="poisson-distributions"></a>Poisson dağıtımları

|Ad|Açıklama|
|-|-|
|[exponential_distribution sınıfı](../standard-library/exponential-distribution-class.md)|Gerçek (kayan nokta) değerlerinin üstel bir dağılımını üretir.|
|[extreme_value_distribution sınıfı](../standard-library/extreme-value-distribution-class.md)|Gerçek (kayan nokta) değerleri için aşırı değer dağılımı üretir.|
|[gamma_distribution sınıfı](../standard-library/gamma-distribution-class.md)|Gerçek (kayan nokta) değerlerinin gama dağılımını üretir.|
|[poisson_distribution sınıfı](../standard-library/poisson-distribution-class.md)|Tamsayı değerlerinin Poisson dağılımını üretir.|
|[weibull_distribution sınıfı](../standard-library/weibull-distribution-class.md)|Gerçek (kayan nokta) değerlerinin bir Weibull dağılımını üretir.|

[[Rastgele sayı dağıtımları](#distributions)]

#### <a name="sampling-distributions"></a>Örnekleme dağıtımları

|Ad|Açıklama|
|-|-|
|[discrete_distribution sınıfı](../standard-library/discrete-distribution-class.md)|Ayrı bir tamsayı dağılımı üretir.|
|[piecewise_constant_distribution sınıfı](../standard-library/piecewise-constant-distribution-class.md)|Gerçek (kayan nokta) değerlerinin piecewise sabit bir dağılımını üretir.|
|[piecewise_linear_distribution sınıfı](../standard-library/piecewise-linear-distribution-class.md)|Gerçek (kayan nokta) değerlerinin piecewise doğrusal bir dağılımını üretir.|

[[Rastgele sayı dağıtımları](#distributions)]

### <a name="utility-functions"></a>Yardımcı program Işlevleri

Bu bölümde, üst bilgide sunulan genel yardımcı program işlevleri listelenir \<random> .

|Ad|Açıklama|
|-|-|
|[seed_seq sınıfı](../standard-library/seed-seq-class.md)|Taraflı olmayan, karıştırılmış bir çekirdek sırası üretir. Rastgele değişen akışların çoğaltılmasını önlemek için kullanılır. Altyapılardan birçok URNGs örneği oluşturulduğunda yararlı olur.|

### <a name="operators"></a>İşleçler

Bu bölümde, üst bilgide belirtilen işleçler listelenmektedir \<random> .

|Ad|Açıklama|
|-|-|
|`operator==`|İşlecin sol tarafındaki URNG 'in sağ taraftaki altyapıya eşit olup olmadığını sınar.|
|`operator!=`|İşlecin sol tarafındaki URNG 'in sağ taraftaki altyapıya eşit olup olmadığını sınar.|
|`operator<<`|Durum bilgilerini bir akışa yazar.|
|`operator>>`|Bir akıştan durum bilgilerini ayıklar.|

## <a name="engines-and-distributions"></a><a name="engdist"></a> Altyapılar ve dağıtımlar

İçinde tanımlanan bu sınıf şablonu kategorilerinin her biri hakkında bilgi edinmek için aşağıdaki bölümlere bakın \<random> . Bu sınıf şablonu kategorilerinin her ikisi de bir türü bağımsız değişken olarak alır ve gerçek bir bağımsız değişken türü olarak izin verilen türün özelliklerini aşağıda gösterildiği gibi, paylaşılan şablon parametre adlarını kullanır:

- `IntType` ,,,, **`short`** **`int`** **`long`** **`long long`** **`unsigned short`** , **`unsigned int`** , **`unsigned long`** , veya belirtir **`unsigned long long`** .

- `UIntType` , **`unsigned short`** , **`unsigned int`** **`unsigned long`** veya belirtir **`unsigned long long`** .

- `RealType`**`float`**, veya belirtir **`double`** **`long double`** .

### <a name="engines"></a>Yapılarının

[Altyapı şablonları](#eng) ve [altyapı bağdaştırıcısı şablonları](#engadapt) , parametreleri oluşturulan oluşturucuyu özelleştiren şablonlardır.

*Motor* , örnekleri (oluşturucular) en düşük ve en yüksek değer arasında eşit olarak dağıtılan rastgele sayıların kaynağı olarak davranan bir sınıf veya sınıf şablonudur. Bir *altyapı bağdaştırıcısı* , başka bir rastgele sayı altyapısı tarafından oluşturulan değerleri alarak ve bu değerlere bazı tür bir algoritma uygulayarak farklı rastgele özellikleri olan bir değer dizisi sunar.

Her altyapı ve altyapı bağdaştırıcısında aşağıdaki Üyeler bulunur:

- **`typedef`**, `numeric-type` `result_type` oluşturucunun tarafından döndürülen türdür `operator()` . , `numeric-type` Örnek oluşturma sırasında şablon parametresi olarak geçirilir.

- `result_type operator()` ve arasında eşit olarak dağıtılan değerleri döndürür `min()` `max()` .

- `result_type min()` oluşturucunun tarafından döndürülen en küçük değeri döndürür `operator()` . Altyapı bağdaştırıcıları, temel altyapının sonucunu kullanır `min()` .

- `result_type max()` oluşturucunun tarafından döndürülen en büyük değeri döndürür `operator()` . `result_type`Bir integral (tamsayı değerli) türü olduğunda, `max()` gerçekte döndürülebilecek maksimum değerdir (dahil); `result_type` kayan nokta (gerçek değerli) türünde olduğunda, `max()` döndürülebilecek tüm değerlerden daha büyük en küçük değerdir (dahil değildir). Altyapı bağdaştırıcıları, temel altyapının sonucunu kullanır `max()` .

- `void seed(result_type s)` Generator, çekirdek değeri ile birlikte `s` . Altyapılar için imza `void seed(result_type s = default_seed)` varsayılan parametre desteği içindir (motor bağdaştırıcıları ayrı bir tanımlama `void seed()` , sonraki alt bölüm).

- `template <class Seq> void seed(Seq& q)`Oluşturucuyu bir [seed_seq](../standard-library/seed-seq-class.md)kullanarak yapın `Seq` .

- `result_type x`Çağırarak, çağırarak bir Oluşturucu oluşturan bağımsız değişkenine sahip açık bir Oluşturucu `seed(x)` .

- `seed_seq& seq`Çağırarak, çağırarak bir Oluşturucu oluşturan bağımsız değişkenine sahip açık bir Oluşturucu `seed(seq)` .

- `void discard(unsigned long long count)` süreleri etkin bir şekilde çağırır `operator()` `count` ve her değeri atar.

**Altyapı bağdaştırıcıları** Ayrıca bu üyeleri destekler ( `Engine` bir altyapı bağdaştırıcısının ilk şablon parametresi, temel altyapının türünü tanımlayarak):

- Oluşturucuyu temel altyapının varsayılan oluşturucusundan gibi başlatmak için varsayılan bir Oluşturucu.

- Bağımsız değişkenli açık bir Oluşturucu `const Engine& eng` . Bu, temel altyapıyı kullanarak kopyalama oluşumunu destekliyoruz.

- Bağımsız değişkenli açık bir Oluşturucu `Engine&& eng` . Bu, temel altyapıyı kullanarak oluşturma oluşumunu destekliyoruz.

- `void seed()` Bu, oluşturucuyu temel altyapının varsayılan tohum değeri ile başlatır.

- `const Engine& base()` oluşturucuyu oluşturmak için kullanılan temel altyapıyı döndüren Özellik işlevi.

Her altyapı, için sonraki çağrılar tarafından oluşturulacak değerlerin sırasını belirleyen bir *durum* sağlar `operator()` . Aynı türdeki altyapılardan oluşturulan iki üretemeyen durumlar, ve kullanılarak karşılaştırılabilir `operator==` `operator!=` . İki durum eşit olarak karşılaştırıldığı takdirde aynı değer dizisini oluşturur. Bir nesnenin durumu, oluşturucunun ' i kullanılarak 32 bitlik işaretsiz değerler dizisi olarak bir akışa kaydedilebilir `operator<<` . Durum, kaydederek değiştirilmez. Kaydedilmiş bir durum, kullanılarak aynı türdeki bir altyapıdan örneklenmiş şekilde okunabilir `operator>>` .

### <a name="distributions"></a>Dağıtımları

[Rastgele bir sayı dağıtımları](#distributions) , örnekleri bir altyapıdan alınan bir eşit olarak dağıtılmış rastgele sayıların akışını belirli bir dağıtıma sahip rastgele sayıların akışına dönüştüren bir sınıf veya sınıf şablonudur. Her dağıtım aşağıdaki üyelere sahiptir:

- **`typedef`**, `numeric-type` `result_type` dağıtımın tarafından döndürülen türdür `operator()` . , `numeric-type` Örnek oluşturma sırasında şablon parametresi olarak geçirilir.

- `template <class URNG> result_type operator()(URNG& gen)``gen`bir tek düzen dağıtılmış rastgele değerler kaynağı ve *dağıtımın saklı parametreleri* olarak kullanarak, dağıtımın tanımına göre dağıtılan değerleri döndürür.

- `template <class URNG> result_type operator()(URNG& gen, param_type p)``gen`yapısal olarak dağıtılmış rastgele değerlerin ve parametre yapısının kaynağı olarak kullanarak, dağıtımın tanımına uygun olarak dağıtılmış değerleri döndürür `p` .

- **`typedef`**, `unspecified-type` `param_type` isteğe bağlı olarak öğesine geçirilen parametrelerin paketidir `operator()` ve dönüş değerini oluşturmak için depolanan parametrelerin yerine kullanılır.

- Bir `const param&` Oluşturucu, saklı parametreleri bağımsız değişkeninden başlatır.

- `param_type param() const` saklı parametreleri alır.

- `void param(const param_type&)` bağımsız değişkeninden saklı parametreleri ayarlar.

- `result_type min()` Dağıtım tarafından döndürülen en küçük değeri döndürür `operator()` .

- `result_type max()` Dağıtım tarafından döndürülen en büyük değeri döndürür `operator()` . `result_type`Bir integral (tamsayı değerli) türü olduğunda, `max()` gerçekte döndürülebilecek maksimum değerdir (dahil); `result_type` kayan nokta (gerçek değerli) türünde olduğunda, `max()` döndürülebilecek tüm değerlerden daha büyük en küçük değerdir (dahil değildir).

- `void reset()` sonraki çağrının sonucunun `operator()` çağrıdan önce altyapıdan alınan değerlere bağlı olmaması için, önbelleğe alınmış tüm değerleri atar.

Parametre yapısı, bir dağıtım için gereken tüm parametreleri depolayan bir nesnedir. Şunları içerir:

- **`typedef`**`distribution-type` `distribution_type` Bu, dağıtımının türüdür.

- Dağıtım oluşturucuları ile aynı parametre listelerini alan bir veya daha fazla Oluşturucu.

- Dağıtım olarak aynı parametre erişimi işlevleri.

- Eşitlik ve eşitsizlik karşılaştırma işleçleri.

Daha fazla bilgi için, bu makalede daha önce bağlanılan başvuru alt bilgilerine bakın.

## <a name="remarks"></a><a name="comments"></a> Açıklamalarının

Visual Studio 'da `mt19937` ve `random_device` Bu karşılaştırma tablosunda gösterildiği gibi, yüksek oranda yararlı Iki-NGS vardır:

|URNG|Hızlı|Şifreleme-güvenli|Seedable|Belirlenimci|
|----------|-----------|---------------------|---------------|--------------------|
|`mt19937`|Evet|Hayır|Evet|Yes<sup>*</sup>|
|`random_device`|Hayır|Evet|Hayır|Hayır|

<sup>* Bilinen bir çekirdek ile sağlandığında.</sup>

ISO C++ standardı şifreli olarak güvenli olmasını gerektirmese de `random_device` , Visual Studio 'da şifreli olarak güvenli olacak şekilde uygulanır. ("Şifreli güvenli" terimi, güvence garantisi vermez, ancak en düşük düzey entropi anlamına gelir; bu nedenle, belirli bir rastgele seçme algoritması sağlar. Daha fazla bilgi için bkz. ıkipedi makalesi [şifreli pseudportaıdom numarası Oluşturucu](https://go.microsoft.com/fwlink/p/?linkid=398017).) ISO C++ standardı bunu gerektirmediğinden, diğer platformlar `random_device` basit bir sözde rastgele sayı üreticisi (şifreli olmayan güvenli değil) olarak uygulayabilir ve yalnızca başka bir Oluşturucu için çekirdek kaynağı olarak uygun olabilir. Platformlar arası kodda kullanırken bu platformların belgelerini denetleyin `random_device` .

Tanım olarak, `random_device` sonuçlar tekrarlanabilir değildir ve yan etkisi diğer URNGs 'ten önemli ölçüde daha yavaş çalışabilir. Şifreleme açısından güvenli hale getirmek için gerekli olmayan çoğu uygulama `mt19937` veya benzer bir altyapı, `random_device` [kod örneğinde](#code)gösterildiği gibi, bir çağrısı ile çekirdek hale getirmek isteyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
