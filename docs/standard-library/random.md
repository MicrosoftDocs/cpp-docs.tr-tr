---
title: '&lt;rastgele&gt;'
ms.date: 08/24/2017
f1_keywords:
- <random>
helpviewer_keywords:
- random header
ms.assetid: 60afc25c-b162-4811-97c1-1b65398d4c57
ms.openlocfilehash: 5b246be02c860ede6691db1c4d21af7e6b4da26a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62369819"
---
# <a name="ltrandomgt"></a>&lt;rastgele&gt;

Tesis birörnek dağıtılmış rastgele sayıdan oluşan oluşturmaya izin verme rastgele sayı üretimi için tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <random>
```

## <a name="summary"></a>Özet

A *rastgele sayı üreticisinin* bir dizi sözde rastgele değer oluşturan nesnedir. Belirtilen bir aralıktaki birörnek dağıtılmış değerleri üreten bir oluşturucu bir *Tekdüzen rastgele sayı üretici* (URNG). Bir URNG işlev görecek şekilde tasarlanmış bir şablon sınıfı olarak adlandırılır bir *altyapısı* Bu sınıf, bu makalenin sonraki bölümlerinde açıklanan bazı ortak özelliklere varsa. Bir URNG olabilir — ve genellikle — birlikte bir *dağıtım* dağıtım URNG bağımsız değişken olarak geçirerek `operator()` dağıtım tarafından tanımlı olacak şekilde dağıtılan değerler üretmek için.

Bu makalede ana bölümleri için bu bağlantıları atla:

- [Örnekler](#code)

- [Kategorilere ayrılmış listesi](#listing)

- [Altyapıları ve dağıtımları](#engdist)

- [Açıklamalar](#comments)

### <a name="quick-tips"></a>Hızlı ipuçları

Kullanırken akılda tutulması gereken bazı ipuçları \<rastgele >:

- Birçok amaç için dağıtımları tarafından şeklinde ham BITS URNGs üretir. (Bu önemli bir istisna [std::shuffle()](../standard-library/algorithm-functions.md#shuffle) bir URNG doğrudan kullandığından.)

- Tek bir örneğini oluşturmada URNG veya dağıtılması için bir güvenli bir şekilde aynı anda bir URNG çalıştırdığından çağrılamaz veya bir değiştirme işlemi dağıtımıdır. Daha fazla bilgi için [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md).

- [Önceden tanımlanmış tür tanımları](#typedefs) birkaç altyapıları sağlanır; Bu, altyapının kullanılıyorsa bir URNG oluşturmak için tercih edilen yoludur.

- Çoğu uygulama için en kullanışlı eşleştirme olduğu `mt19937` ile altyapısını `uniform_int_distribution`gösterildiği [kod örneği](#code) bu makalenin ilerleyen bölümlerinde.

Birçok seçenek içinden seçebileceğiniz \<rastgele > üst bilgi ve bunların hiçbirine eski C çalışma zamanı işleve tercih `rand()`. Sorun nedir hakkında bilgi için `rand()` ve nasıl \<rastgele > Bu eksiklikleri adresleri bkz [bu videoyu](http://go.microsoft.com/fwlink/p/?linkid=397615).

## <a name="code"></a> Örnekleri

Aşağıdaki kod örneği, belirleyici çekirdek ile oluşturulan bir oluşturucuyu kullanarak, bu durumda beş numaraları bazı rastgele oluşturma adımları anlatılmaktadır.

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

Bunlar yüksek kaliteli rastgele sayı ve farklı her zaman bu programı da çalıştırılır, ancak bunlar mutlaka yararlı bir aralıktaki değildir. Aralık denetimi için Tekdüzen bir dağıtım aşağıdaki kodda gösterildiği gibi kullanın:

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

Sonraki kod örneğinde, bir vektör ve bir dizi içeriğini karıştırma birörnek dağıtılmış rastgele sayı üreteçlerinin ile kullanım örneklerini daha gerçekçi bir dizi gösterir.

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

Bu kod, iki farklı randomizations gösterir; bir tamsayı vektörü rastgele yap ve dizinlenmiş verileri bir dizi karışık — test şablon işlevi ile. Şifreleme-secure belirleyici, seedable değil, tekrarlanabilir olmayan URNG test işleve ilk çağrı kullanan `random_device`. İkinci test çalıştırması kullandığı `mersenne_twister_engine` URNG belirleyici 32-bit sabit çekirdek ile başka bir deyişle, sonuçları tekrarlanabilir. Üçüncü bir test çalıştırması hızlarına `mersenne_twister_engine` 32-bit belirleyici sonuçtan ile `random_device`. Dördüncü test çalıştırması bu kullanarak genişletir. bir [temel dizisi](../standard-library/seed-seq-class.md) doldurulmuş `random_device` 32-bit belirleyici doğrulukla değerinden (ancak yine de değil şifreleme-secure) daha etkili bir şekilde sağlayan sonuç. Daha fazla bilgi için okumaya devam edin.

## <a name="listing"></a> Kategorilere ayrılmış listesi

###  <a name="urngs"></a> Tekdüzen rastgele sayı oluşturucuları

URNGs genellikle açısından bu özellikleri açıklanmaktadır:

1. **Dönem uzunluğunu**: Kaç adet yineleme oluşturulan sayıların dizisi Yinele için alır. Uzun daha iyi.

2. **Performans**: Sayı ne kadar hızlı oluşturulabilir ve ne kadar bellek sürer. Daha küçük daha iyi.

3. **Kalite**: Oluşturulan sıralı olan doğru rastgele sayılar yakın nasıl. Buna genellikle denir "*doğrulukla*".

Aşağıdaki bölümlerde sağlanan Tekdüzen rastgele sayı üreteçlerinin (URNGs) listesinde \<rastgele > Üstbilgi.

####  <a name="rd"></a> Belirleyici Oluşturucusu

|||
|-|-|
|[random_device Sınıfı](../standard-library/random-device-class.md)|Harici bir cihaz kullanarak belirleyici, şifreleme açısından güvenli rastgele bir sıra üretir. Genellikle bir altyapısı sağlamak için kullanılır. Düşük performans, çok yüksek kalite. Daha fazla bilgi için [açıklamalar](#comments).|

####  <a name="typedefs"></a> Önceden tanımlanmış parametrelerle altyapısı tür tanımları

Altyapıları örnekleme ve bağdaştırıcıları altyapısı için. Daha fazla bilgi için [altyapıları ve dağıtımları](#engdist).

- `default_random_engine` Varsayılan altyapısı.

    ```cpp
    typedef mt19937 default_random_engine;
    ```

- `knuth_b` Knuth altyapısı.

    ```cpp
    typedef shuffle_order_engine<minstd_rand0, 256> knuth_b;
    ```

- `minstd_rand0` 1988 en az standart altyapısı (Gamze, Goodman ve Miller, 1969).

    ```cpp
    typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
    ```

- `minstd_rand` Güncelleştirilmiş en az standart altyapısını `minstd_rand0` (Park, Miller ve Stockmeyer, 1993).

    ```cpp
    typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
    ```

- `mt19937` 32-bit Mersenne bükücü altyapısı (Matsumoto ve Nishimura, 1998).

    ```cpp
    typedef mersenne_twister_engine<
        unsigned int, 32, 624, 397,
        31, 0x9908b0df,
        11, 0xffffffff,
        7, 0x9d2c5680,
        15, 0xefc60000,
        18, 1812433253> mt19937;
    ```

- `mt19937_64` 64-bit Mersenne bükücü altyapısı (Matsumoto ve Nishimura, 2000).

    ```cpp
    typedef mersenne_twister_engine<
        unsigned long long, 64, 312, 156,
        31, 0xb5026f5aa96619e9ULL,
        29, 0x5555555555555555ULL,
        17, 0x71d67fffeda60000ULL,
        37, 0xfff7eee000000000ULL,
        43, 6364136223846793005ULL> mt19937_64;
    ```

- `ranlux24` 24 bit RANLUX altyapısı (Martin Lüscher ve Fred James, 1994).

    ```cpp
    typedef discard_block_engine<ranlux24_base, 223, 23> ranlux24;
    ```

- `ranlux24_base` İçin bir temel olarak kullanılan `ranlux24`.

    ```cpp
    typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;
    ```

- `ranlux48` 48 bit RANLUX altyapısı (Martin Lüscher ve Fred James, 1994).

    ```cpp
    typedef discard_block_engine<ranlux48_base, 389, 11> ranlux48;
    ```

- `ranlux48_base` İçin bir temel olarak kullanılan `ranlux48`.

    ```cpp
    typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;
    ```

####  <a name="eng"></a> Altyapısı şablonları

Geçirilen temel altyapıları olarak veya tek başına URNGs altyapısı şablonları kullanılan [altyapısı bağdaştırıcıları](#engadapt). Genellikle bu ile örneği bir [altyapısı typedef önceden tanımlanmış](#typedefs) ve geçirilen bir [dağıtım](#distributions). Daha fazla bilgi için [altyapıları ve dağıtımları](#engdist) bölümü.

|||
|-|-|
|[linear_congruential_engine Sınıfı](../standard-library/linear-congruential-engine-class.md)|Çizgisel eşleşik algoritmasını kullanarak rastgele bir sıra üretir. En alıyormuş ve en düşük kalite.|
|[mersenne_twister_engine Sınıfı](../standard-library/mersenne-twister-engine-class.md)|Mersenne bükücü algoritmasını kullanarak rastgele bir sıra üretir. En karmaşık ve yüksek kaliteli random_device sınıfı dışında. Çok hızlı performans.|
|[subtract_with_carry_engine Sınıfı](../standard-library/subtract-with-carry-engine-class.md)|Taşıma ile çıkarma algoritmasını kullanarak rastgele bir sıra üretir. Üzerinde bir iyileştirme `linear_congruential_engine`, ancak çok daha düşük kalitesini ve performansını daha `mersenne_twister_engine`.|

####  <a name="engadapt"></a> Altyapısı bağdaştırıcısı şablonları

Altyapısı, (Temel) diğer altyapıları uyum şablonları başvurularıdır. Genellikle bu ile örneği bir [altyapısı typedef önceden tanımlanmış](#typedefs) ve geçirilen bir [dağıtım](#distributions). Daha fazla bilgi için [altyapıları ve dağıtımları](#engdist) bölümü.

|||
|-|-|
|[discard_block_engine Sınıfı](../standard-library/discard-block-engine-class.md)|Değerleri kendi temel altyapısıyla döndürülen atarak rastgele bir sıra üretir.|
|[independent_bits_engine Sınıfı](../standard-library/independent-bits-engine-class.md)|Kendi temel altyapısıyla döndürülen değerlerden bitleri yeniden paketleyerek belirtilen bir bit sayısıyla rastgele bir sıra üretir.|
|[shuffle_order_engine Sınıfı](../standard-library/shuffle-order-engine-class.md)|Kendi temel altyapısından döndürülen değerlerden yeniden sıralayarak rastgele bir sıra üretir.|

[[Altyapısı şablonları](#eng)]

###  <a name="distributions"></a> Rastgele sayı dağıtımları

Aşağıdaki bölümlerde sağlanan dağıtımları listesinde \<rastgele > Üstbilgi. Dağıtımları, genellikle URNG çıkış giriş olarak kullanan ve çıktı tarafından bir tanımlı istatistiksel olasılık yoğunluğu fonksiyonunu dağıtma işlem sonrası bir mekanizması mevcuttur. Daha fazla bilgi için [altyapıları ve dağıtımları](#engdist) bölümü.

#### <a name="uniform-distributions"></a>Tekdüzen dağıtımları

|||
|-|-|
|[uniform_int_distribution Sınıfı](../standard-library/uniform-int-distribution-class.md)|Kapalı aralık içinde bir aralık boyunca bir Tekdüzen tamsayı değer dağılımı üretir \[a, b] (baştaki).|
|[uniform_real_distribution Sınıfı](../standard-library/uniform-real-distribution-class.md)|Bir Tekdüzen gerçek üretir (kayan nokta) değer dağılımı yarı açık aralığı içinde bir aralık boyunca [a, b) (özel dahil).|
|[generate_canonical](../standard-library/random-functions.md#generate_canonical)|Arasında belirli bir kesinlik (kayan nokta) gerçek değerlerin bir dağılımı üretir [0, 1) (özel dahil).|

[[Rastgele sayı dağıtımları](#distributions)]

#### <a name="bernoulli-distributions"></a>Bernoulli dağıtımları

|||
|-|-|
|[bernoulli_distribution Sınıfı](../standard-library/bernoulli-distribution-class.md)|Bir Bernoulli dağılımı üretir **bool** değerleri.|
|[binomial_distribution Sınıfı](../standard-library/binomial-distribution-class.md)|Tamsayı değerleri bir binom açılımı üretir.|
|[geometric_distribution Sınıfı](../standard-library/geometric-distribution-class.md)|Tamsayı değerleri bir geometrik dağılım üretir.|
|[negative_binomial_distribution Sınıfı](../standard-library/negative-binomial-distribution-class.md)|Tamsayı değerleri bir negatif binom açılımı üretir.|

[[Rastgele sayı dağıtımları](#distributions)]

#### <a name="normal-distributions"></a>Normal dağıtım

|||
|-|-|
|[cauchy_distribution Sınıfı](../standard-library/cauchy-distribution-class.md)|(Kayan nokta) gerçek değerlerin bir Cauchy açılımı üretir.|
|[chi_squared_distribution Sınıfı](../standard-library/chi-squared-distribution-class.md)|(Kayan nokta) gerçek değerlerin bir kikare dağılımı üretir.|
|[fisher_f_distribution Sınıfı](../standard-library/fisher-f-distribution-class.md)|Bir F-(Snedecor'ın F dağılımı veya Fisher Snedecor dağıtım olarak da bilinir) (kayan nokta) gerçek bir değerler dağıtımı verir.|
|[lognormal_distribution Sınıfı](../standard-library/lognormal-distribution-class.md)|(Kayan nokta) gerçek değerlerin bir log-normal dağılımı üretir.|
|[normal_distribution Sınıfı](../standard-library/normal-distribution-class.md)|(Kayan nokta) gerçek değerlerin bir normal (Gauss) dağılımı üretir.|
|[student_t_distribution Sınıfı](../standard-library/student-t-distribution-class.md)|Bir öğrenci üretir *t*-dağıtım (kayan nokta) gerçek değerler.|

[[Rastgele sayı dağıtımları](#distributions)]

#### <a name="poisson-distributions"></a>Poisson dağıtımları

|||
|-|-|
|[exponential_distribution Sınıfı](../standard-library/exponential-distribution-class.md)|(Kayan nokta) gerçek değerlerin bir üstel dağılım üretir.|
|[extreme_value_distribution Sınıfı](../standard-library/extreme-value-distribution-class.md)|(Kayan nokta) gerçek değerlerin aşırı değer dağılımı üretir.|
|[gamma_distribution Sınıfı](../standard-library/gamma-distribution-class.md)|(Kayan nokta) gerçek değerlerin bir gamma dağılımı üretir.|
|[poisson_distribution Sınıfı](../standard-library/poisson-distribution-class.md)|Tamsayı değerleri bir Poisson dağılımı üretir.|
|[weibull_distribution Sınıfı](../standard-library/weibull-distribution-class.md)|(Kayan nokta) gerçek değerlerin bir Weibull dağılım üretir.|

[[Rastgele sayı dağıtımları](#distributions)]

#### <a name="sampling-distributions"></a>Örnekleme dağıtımları

|||
|-|-|
|[discrete_distribution Sınıfı](../standard-library/discrete-distribution-class.md)|Bir ayrık tam sayı dağılımı üretir.|
|[piecewise_constant_distribution Sınıfı](../standard-library/piecewise-constant-distribution-class.md)|Üreten bir piecewise sabiti dağılımı gerçek (kayan nokta) değerleri.|
|[piecewise_linear_distribution Sınıfı](../standard-library/piecewise-linear-distribution-class.md)|Üreten bir piecewise doğrusal dağılımı gerçek (kayan nokta) değerleri.|

[[Rastgele sayı dağıtımları](#distributions)]

### <a name="utility-functions"></a>Yardımcı işlevleri

Bu bölümde sağlanan genel yardımcı işlevleri listeler \<rastgele > Üstbilgi.

|||
|-|-|
|[seed_seq Sınıfı](../standard-library/seed-seq-class.md)|Karıştırılmış çekirdek ağırlıklı olmayan bir sıra üretir. Rastgele değişkenli akışları çoğaltılmasını önlemek için kullanılır. Birçok URNGs motorlarından örneği oluşturulur kullanışlıdır.|

### <a name="operators"></a>İşleçler

Bu bölümde sağlanan işleçleri listelenir \<rastgele > Üstbilgi.

|||
|-|-|
|`operator==`|İşlecin sol tarafındaki URNG sağ tarafındaki motorun eşit olup olmadığını sınar.|
|`operator!=`|İşlecin sol tarafındaki URNG sağ tarafındaki motorun eşit olup olmadığını test eder.|
|`operator<<`|Durum bilgilerini bir akışa yazar.|
|`operator>>`|Durum bilgisini bir akıştan ayıklar.|

## <a name="engdist"></a> Altyapıları ve dağıtımları

Tanımlanan bu şablon sınıfının kategorilerden her biri hakkında bilgi edinmek için aşağıdaki bölümlere bakın \<rastgele >. Bu şablon sınıfının kategorilerin her ikisi de bağımsız değişken olarak bir tür olması ve paylaşılan bir şablon parametresi adları şu şekilde bir gerçek bağımsız değişken türü olarak izin verilen tür özelliklerini tanımlamak için kullanın:

- `IntType` belirten bir **kısa**, **int**, **uzun**, **uzun uzun**, **işaretsiz**,  **işaretsiz int**, **işaretsiz uzun**, veya **işaretsiz long long**.

- `UIntType` gösterir **işaretsiz**, **işaretsiz int**, **işaretsiz uzun**, veya **işaretsiz long long**.

- `RealType` belirten bir **float**, **çift**, veya **uzun çift**.

### <a name="engines"></a>Altyapıları

[Şablonları altyapısı](#eng) ve [altyapısı bağdaştırıcısı şablonları](#engadapt) parametreleri oluşturan üreteci özelleştiren şablonlardır.

Bir *altyapısı* bir minimum ve maksimum değer arasında bir sınıfı veya şablon sınıfıdır örneklere (oluşturucular) hareket rastgele sayı kaynağı olarak eşit dağıtılır. Bir *altyapısı bağdaştırıcısı* bazı diğer rastgele sayı altyapısı tarafından üretilen ve bu değerleri bir algoritma tür uygulama alma değerlere göre farklı doğrulukla özelliklerine sahip değerler sunar.

Her altyapısı ve altyapısı bağdaştırıcısı aşağıdaki üyeleri içerir:

- `typedef` `numeric-type` `result_type` üreticinin tarafından döndürülen türdür `operator()`. `numeric-type` Örnek oluşturma şablon parametre olarak geçirilir.

- `result_type operator()` arasında birörnek dağıtılmış değerleri döndürür `min()` ve `max()`.

- `result_type min()` üreticinin tarafından döndürülen en küçük değerini döndürür `operator()`. Altyapısı bağdaştırıcıları kullanan temel altyapının `min()` sonucu.

- `result_type max()` üreticinin tarafından döndürülen en büyük değerini döndürür `operator()`. Zaman `result_type` integral (tamsayı değerli) türü olan `max()` gerçekten (sınırlar dahil); döndürülebilecek en yüksek değer olduğunda `result_type` bir kayan nokta (gerçek değerli) türüdür `max()` tüm değerlerden büyük en küçük değeri olan (dahil) döndürülebilir. Altyapısı bağdaştırıcıları kullanan temel altyapının `max()` sonucu.

- `void seed(result_type s)` Çekirdek değeriyle oluşturucunun çekirdeğini `s`. İmza altyapılarını olduğu `void seed(result_type s = default_seed)` varsayılan parametre desteği (altyapısı bağdaştırıcıları ayrı bir tanımlama `void seed()`, alt bölümüne bakın).

- `template <class Seq> void seed(Seq& q)` oluşturucuyu kullanarak altyapıyı sınıflar bir [seed_seq](../standard-library/seed-seq-class.md)`Seq`.

- Bağımsız değişkenini içeren açık Oluşturucu `result_type x` çağırır gibi çekirdek değeri oluşturulmuş bir oluşturucuyu oluşturan `seed(x)`.

- Bağımsız değişkenini içeren açık Oluşturucu `seed_seq& seq` çağırır gibi çekirdek değeri oluşturulmuş bir oluşturucuyu oluşturan `seed(seq)`.

- `void discard(unsigned long long count)` etkili bir şekilde çağıran `operator()` `count` zaman ve her değeri atar.

**Altyapısı bağdaştırıcıları** Ayrıca bu üyeleri desteği (`Engine` temel altyapının türünü belirleme bir altyapısı bağdaştırıcısı ilk şablon parametresi):

- Temel altyapının varsayılan oluşturucusundan gibi oluşturucuyu başlatmak için bir varsayılan oluşturucu.

- Bağımsız değişkenini içeren açık Oluşturucu `const Engine& eng`. Bu temel altyapısı kullanılarak kopya oluşumuna desteklemektir.

- Bağımsız değişkenini içeren açık Oluşturucu `Engine&& eng`. Bu temel altyapısı kullanılarak taşıma oluşturma desteklemektir.

- `void seed()` Bu, temel altyapının varsayılan tohum değerle üreticiyi başlatır.

- `const Engine& base()` Oluşturucu oluşturmak için kullanılan temel altyapı döndüren özellik işlev.

Her motor tutan bir *durumu* sonraki aramalarla üretilecek değerler sırasını belirleyen `operator()`. Kullanarak aynı türü motorlarından örneği iki oluşturucuları durumlarını karşılaştırılabilir `operator==` ve `operator!=`. İki durum eşit karşılaştırılırsa, bunlar aynı değer sırasını oluşturur. Bir nesnenin durumu bir akışa 32-bit işeritsiz değerler dizisi olarak kullanarak kaydedilebilir `operator<<` oluşturucunun. Durum kaydetme tarafından değiştirilmez. Kaydedilen bir duruma oluşturucu kullanılarak aynı türde altyapıdan örneği içine okunabilir `operator>>`.

### <a name="distributions"></a>Dağıtımları

A [rastgele sayı dağıtımları](#distributions) örneklere altyapıdan belirli bir dağıtıma sahip rastgele sayıdan oluşan bir akışa alınan eşit dağıtılan rastgele sayıların akışını dönüştüren bir sınıfı veya şablon sınıfıdır. Her dağıtım aşağıdaki üyeleri içerir:

- `typedef` `numeric-type` `result_type` Dağıtım tarafından 's döndürülen türdür `operator()`. `numeric-type` Örnek oluşturma şablon parametre olarak geçirilir.

- `template <class URNG> result_type operator()(URNG& gen)` tanımına göre kullanarak dağıtılmış değerleri döndürür `gen` kaynağı birörnek dağıtılmış rastgele değerler ve depolanmış olarak *dağıtım parametrelerini*.

- `template <class URNG> result_type operator()(URNG& gen, param_type p)` tanımına göre dağıtılmış değerleri döndürür kullanarak `gen` parametreleri yapısı ve birörnek dağıtılmış rastgele değerler kaynağı olarak `p`.

- `typedef` `unspecified-type` `param_type` parametrelerin isteğe bağlı olarak geçirilen `operator()` ve depolanan parametrelerin yerine, kendi dönüş değerini oluşturmak için kullanılır.

- A `const param&` oluşturucu bağımsız değişkeninden depolanan parametre başlatır.

- `param_type param() const` depolanan parametre alır.

- `void param(const param_type&)` depolanan parametrelerin kendi bağımsız değişkeninden ayarlar.

- `result_type min()` Dağıtım tarafından 's döndürülen en küçük değerini döndürür `operator()`.

- `result_type max()` Dağıtım tarafından 's döndürülen en büyük değerini döndürür `operator()`. Zaman `result_type` integral (tamsayı değerli) türü olan `max()` gerçekten (sınırlar dahil); döndürülebilecek en yüksek değer olduğunda `result_type` bir kayan nokta (gerçek değerli) türüdür `max()` tüm değerlerden büyük en küçük değeri olan (dahil) döndürülebilir.

- `void reset()` önbelleğe alınan tüm değerleri atar. böylece sonraki çağrı sonucunu `operator()` çağırmadan önce altyapısından alınan değerleri, bağlı değildir.

Bir parametre yapısı tüm dağıtım için gerekli parametreleri depolayan bir nesnedir. Aşağıdakileri içerir:

- `typedef` `distribution-type` `distribution_type`, kendi dağıtım türü.

- Aynı parametre bir veya daha fazla oluşturucular dağıtım oluşturucularının aldığı gibi listeler.

- Dağıtım olarak aynı parametre erişim işlevleri.

- Eşitlik ve eşitsizlik Karşılaştırma işleçleri.

Daha fazla bilgi için bu makalede daha önce bağlı bunun altındaki başvuru konuları bakın.

## <a name="comments"></a> Açıklamalar

Visual Studio'da iki çok kullanışlı URNGs vardır —`mt19937` ve `random_device`— bu karşılaştırma tabloda gösterildiği gibi:

|URNG|Hızlı|Şifreleme-secure|Seedable|Belirleyici|
|----------|-----------|---------------------|---------------|--------------------|
|`mt19937`|Evet|Hayır|Evet|Evet<sup>*</sup>|
|`random_device`|Hayır|Evet|Hayır|Hayır|

<sup>* İle bilinen bir çekirdek sağlandığında.</sup>

ISO C++ standardı gerektirmez ancak `random_device` şifreleme bakımından güvenli olacak şekilde uygulanan şifreli olarak olmasını Visual Studio'da güvenli. ("Şifreleme bakımından güvenli" terimi garantisi anlamına gelmez, ancak en az bir entropi düzeyine başvuruyor — ve bu nedenle, öngörülebilirlik düzeyini — belirli bir rastgele seçim algoritması sağlar. Daha fazla bilgi için bkz. Wikipedia makalesi [şifreleme bakımından güvenli sözde rastgele sayı üretici](http://go.microsoft.com/fwlink/p/?linkid=398017).) ISO C++ standardı bu gerektirmediğinden, diğer platformlar uygulayabilir `random_device` basit sözde rastgele sayı üreticisinin (şifreleme bakımından güvenli) ve yalnızca Mayıs başka bir oluşturucu için bir çekirdek kaynağı olarak uygun olabilir. Kullanırken bu platformlar için belgelere bakın `random_device` platformlar arası kod.

Tanımına göre `random_device` sonuçları tekrarlanabilir olmayan ve diğer URNGs göre önemli ölçüde daha yavaş çalışabilir yan etkisi olan. Şifreleme bakımından olması gerekmez, çoğu uygulama güvenlidir `mt19937` veya benzer bir altyapısı çağrısıyla temel isteyebilirsiniz ancak `random_device`gösterildiği [kod örneği](#code).

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
