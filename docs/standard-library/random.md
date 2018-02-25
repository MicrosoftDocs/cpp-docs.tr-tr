---
title: '&lt;rastgele&gt; | Microsoft Docs'
ms.custom: 
ms.date: 08/24/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <random>
dev_langs:
- C++
helpviewer_keywords:
- random header
ms.assetid: 60afc25c-b162-4811-97c1-1b65398d4c57
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af48357ff276df90333d066cf6585a031b572914
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltrandomgt"></a>&lt;random&gt;
Tesis hep dağıtılmış rastgele sayılar oluşturulmasına izin vererek rastgele sayı oluşturma için tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <random>  
```  
  
## <a name="summary"></a>Özet  
 A *rastgele sayı üreticisinin* sözde rastgele değerleri dizisi üretir bir nesnedir. Belirtilen bir aralıkta hep dağıtılmış değerleri üreten bir oluşturucusu bir *Tekdüzen rastgele sayı üretici* (URNG). URNG çalışması için tasarlanmış bir şablon sınıfı olarak adlandırılır bir *altyapısı* o sınıfın bu makalenin sonraki bölümlerinde ele alınan belirli ortak nitelikler varsa. Bir URNG olabilir — ve genellikle — birlikte bir *dağıtım* dağıtımına ait URNG bağımsız değişken olarak geçirerek `operator()` dağıtımı tarafından tanımlanan bir şekilde dağıtılmış değeri oluşturmak üzere.  
  
 Bu bağlantılar için bu makalenin ana bölümleri atla:  
  
- [Örnekler](#code)  
  
- [Kategorilere ayrılmış listeleme](#listing)  
  
- [Motorları ve dağıtımları](#engdist)  
  
- [Açıklamalar](#comments)  
  
### <a name="quick-tips"></a>Hızlı ipuçları  
 Kullanırken dikkate alınması gereken bazı ipuçları `<random>`:  
  
-   Çoğu amaç için URNGs dağıtımları tarafından şeklinde ham biti üretir. (Bu önemli bir özel durum [std::shuffle()](../standard-library/algorithm-functions.md#shuffle) bir URNG doğrudan kullandığından.)  
  
-   Tek bir örnek oluşturma URNG veya dağıtım güvenle eşzamanlı olarak çalışan bir URNG olduğundan çağrılamaz veya dağıtım değiştirme bir işlemdir. Daha fazla bilgi için bkz: [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md).  
  
- [Önceden tanımlanmış tür tanımları](#typedefs) birkaç altyapılarını sağlanır; Bu, altyapının kullanılıyorsa bir URNG oluşturmak için tercih edilen yöntemdir.  
  
-   Çoğu uygulama için en kullanışlı eşleştirme olduğu `mt19937` ile altyapısını `uniform_int_distribution`gösterildiği gibi [kod örneğinde](#code) bu makalenin ilerisinde yer.  
  
 De nereden seçmek için pek çok seçenek `<random>` üstbilgi ve bunlardan herhangi birinin eski C çalışma zamanı işlevine tercih `rand()`. Sorun nedir hakkında bilgi için `rand()` ve nasıl `<random>` bu eksik adresleri bkz [bu videoyu](http://go.microsoft.com/fwlink/p/?linkid=397615).  
  
##  <a name="code">Örnekler</a>  
 Aşağıdaki kod örneği, belirleyici olmayan çekirdek ile oluşturulan bir oluşturucuyu kullanarak bunları, bu durumda beş rastgele sayılar oluşturma gösterilmektedir.  
  
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
  
 Bunlar yüksek kaliteli rastgele sayı ve farklı her zaman bu programı çalıştırılır olsa da, bunlar mutlaka yararlı bir aralık içinde olup olmadığı. Aralığın denetlemek için aşağıdaki kodda gösterildiği gibi bir Tekdüzen dağıtım kullanın:  
  
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
  
 Sonraki kod örneği bir vektör ve bir dizi içeriğini karıştırılması hep dağıtılmış rastgele sayı Oluşturucuları ile kullanım durumları daha gerçekçi bir dizi gösterir.  
  
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
  
Bu kod, iki farklı randomizations gösterir — tamsayıların vektör rasgele yap ve dizinlenmiş veri dizisi karışık — test şablon işlevi ile. Test işlevi ilk çağrıda crypto güvenli, belirleyici olmayan, not seedable, tekrarlanabilir olmayan URNG kullanan `random_device`. İkinci testi kullanır `mersenne_twister_engine` URNG belirleyici 32-bit sabit çekirdek ile başka bir deyişle, sonuçları yinelenebilir. Üçüncü testi oluştururken çekirdeği `mersenne_twister_engine` 32-bit belirleyici sonucundan ile `random_device`. Dördüncü testi bu kullanarak genişletir. bir [temel sıralı](../standard-library/seed-seq-class.md) doldurulmuş `random_device` etkili bir şekilde daha 32-bit belirleyici rastgele'den (ancak hala değil crypto güvenli) verir sonuçları. Daha fazla bilgi için okumaya devam edin.  
  
##  <a name="listing">Kategorilere ayrılmış listeleme</a>  
  
###  <a name="urngs"></a> Tekdüzen rastgele sayı oluşturucuları  
 URNGs genellikle açısından bu özellikleri açıklanmıştır:  
  
1. **Dönem uzunluğu**: sürdüğünü oluşturulan sayıların dizisi Yinele için kaç yineleme. Uzun iyi olur.  
  
2. **Performans**: sayı ne kadar hızlı oluşturulabilir ve ne kadar bellek alır. Daha küçük iyi olur.  
  
3. **Kalite**: nasıl oluşturulan sıra true rastgele sayılar yakın. Bu genellikle adlandırılır "*rastgele*".  
  
 Aşağıdaki bölümlerde sağlanan Tekdüzen rastgele sayı oluşturucuları (URNGs) listesinde `<random>` üstbilgi.  
  
####  <a name="rd"></a> Belirleyici olmayan Oluşturucusu  
  
|||  
|-|-|  
|[random_device Sınıfı](../standard-library/random-device-class.md)|Harici bir cihaz kullanarak belirleyici, şifreleme açısından güvenli rastgele bir sıra oluşturur. Genellikle bir altyapısı oluşturmak için kullanılır. Düşük performans, çok yüksek kaliteli. Daha fazla bilgi için bkz: [açıklamalar](#comments).|  
  
####  <a name="typedefs"></a> Önceden tanımlanmış parametrelerle altyapısı tür tanımları  
 Örnek oluşturma motorları ve altyapısı bağdaştırıcıları için. Daha fazla bilgi için bkz: [motorları ve dağıtımları](#engdist).  
  
- `default_random_engine` Varsayılan altyapısı.   
 `typedef mt19937 default_random_engine;`  
  
- `knuth_b` Knuth altyapısı.   
 `typedef shuffle_order_engine<minstd_rand0, 256> knuth_b;`  
  
- `minstd_rand0` 1988 en az standart altyapısı (Gamze, Goodman ve Mert, 1969).   
 `typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;`  
  
- `minstd_rand` Güncelleştirilmiş en az standart altyapısını `minstd_rand0` (Park, Mert ve Stockmeyer, 1993).   
 `typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;`  
  
- `mt19937` 32-bit Mersenne twister altyapısı (Matsumoto ve Nishimura, 1998).   
 `typedef mersenne_twister_engine<unsigned int, 32, 624, 397,      31, 0x9908b0df,      11, 0xffffffff,      7, 0x9d2c5680,      15, 0xefc60000,      18, 1812433253> mt19937;`  
  
- `mt19937_64` 64-bit Mersenne twister altyapısı (Matsumoto ve Nishimura, 2000).   
 `typedef mersenne_twister_engine<unsigned long long, 64, 312, 156,      31, 0xb5026f5aa96619e9ULL,      29, 0x5555555555555555ULL,      17, 0x71d67fffeda60000ULL,      37, 0xfff7eee000000000ULL,      43, 6364136223846793005ULL> mt19937_64;`  
  
- `ranlux24` 24 bit RANLUX altyapısı (Martin Lüscher ve Gamze Ahmet, 1994).   
 `typedef discard_block_engine<ranlux24_base, 223, 23> ranlux24;`  
  
- `ranlux24_base` İçin temel olarak kullanılan `ranlux24`.   
 `typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`  
  
- `ranlux48` 48 bit RANLUX altyapısı (Martin Lüscher ve Gamze Ahmet, 1994).   
 `typedef discard_block_engine<ranlux48_base, 389, 11> ranlux48;`  
  
- `ranlux48_base` İçin temel olarak kullanılan `ranlux48`.   
 `typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`  
  
####  <a name="eng"></a> Altyapısı şablonları  
 Geçirilen temel altyapıları olarak veya tek başına URNGs altyapısı şablonları kullanılır [altyapısı bağdaştırıcıları](#engadapt). Genellikle bu ile örneği bir [altyapısı typedef önceden tanımlanmış](#typedefs) ve geçirilen bir [dağıtım](#distributions). Daha fazla bilgi için bkz: [motorları ve dağıtımları](#engdist) bölümü.  
  
|||  
|-|-|  
|[linear_congruential_engine Sınıfı](../standard-library/linear-congruential-engine-class.md)|Doğrusal congruential algoritması kullanılarak rastgele bir sıra oluşturur. En simplistic ve en düşük kalitesi.|  
|[mersenne_twister_engine Sınıfı](../standard-library/mersenne-twister-engine-class.md)|Mersenne twister algoritması kullanılarak rastgele bir sıra oluşturur. En karmaşık ve en yüksek kaliteli random_device sınıfı dışında. Çok hızlı performans sağlar.|  
|[subtract_with_carry_engine Sınıfı](../standard-library/subtract-with-carry-engine-class.md)|Carry ile çıkarma algoritması kullanılarak rastgele bir sıra oluşturur. Üzerinde bir geliştirme `linear_congruential_engine`, ancak daha düşük kalitesini ve performansını daha `mersenne_twister_engine`.|  
  
####  <a name="engadapt"></a> Motoru bağdaştırıcı şablonları  
 Altyapısı bağdaştırıcıları (Temel) diğer motorları uyum şablonlarıdır. Genellikle bu ile örneği bir [altyapısı typedef önceden tanımlanmış](#typedefs) ve geçirilen bir [dağıtım](#distributions). Daha fazla bilgi için bkz: [motorları ve dağıtımları](#engdist) bölümü.  
  
|||  
|-|-|  
|[discard_block_engine Sınıfı](../standard-library/discard-block-engine-class.md)|Kendi temel altyapı tarafından döndürülen değer atarak rastgele bir sıra oluşturur.|  
|[independent_bits_engine Sınıfı](../standard-library/independent-bits-engine-class.md)|BITS, temel altyapı tarafından döndürülen değerlerinden repacking tarafından belirtilen bit sayısı ile rastgele bir sıra oluşturur.|  
|[shuffle_order_engine Sınıfı](../standard-library/shuffle-order-engine-class.md)|Kendi temel altyapısı döndürdüğü değer sıralayarak rastgele bir sıra oluşturur.|  
  
 [[Altyapısı şablonları](#eng)]  
  
###  <a name="distributions"></a> Rastgele sayı dağıtımları  
 Aşağıdaki bölümlerde sağlanan dağıtımları listesinde `<random>` üstbilgi. Dağıtımları genellikle URNG çıkış giriş olarak kullanan ve çıktı tarafından tanımlanan istatistiksel olasılık yoğunluğu fonksiyonunu dağıtma işlem sonrası bir mekanizma ' dir. Daha fazla bilgi için bkz: [motorları ve dağıtımları](#engdist) bölümü.  
  
#### <a name="uniform-distributions"></a>Tekdüzen dağıtımları  
  
|||  
|-|-|  
|[uniform_int_distribution Sınıfı](../standard-library/uniform-int-distribution-class.md)|Kapalı aralığı içindeki bir aralık boyunca Tekdüzen tamsayı değeri dağıtım üreten \[a, b] (kapsayıcı-kapsayıcı).|  
|[uniform_real_distribution Sınıfı](../standard-library/uniform-real-distribution-class.md)|Bir Tekdüzen gerçek üretir (kayan nokta) değeri dağıtım yarı açık aralığı içindeki bir aralık boyunca [a, b) (özel dahil).|  
|[generate_canonical](../standard-library/random-functions.md#generate_canonical)|Belirtilen duyarlık arasında (kayan nokta) gerçek değerlerin bile bir dağıtım üreten [0, 1) (özel dahil).|  
  
 [[Rastgele sayı dağıtımları](#distributions)]  
  
#### <a name="bernoulli-distributions"></a>Bernoulli dağıtımları  
  
|||  
|-|-|  
|[bernoulli_distribution Sınıfı](../standard-library/bernoulli-distribution-class.md)|Bernoulli dağıtımını üreten `bool` değerleri.|  
|[binomial_distribution Sınıfı](../standard-library/binomial-distribution-class.md)|Tamsayı değerleri terimli dağıtımını üretir.|  
|[geometric_distribution Sınıfı](../standard-library/geometric-distribution-class.md)|Tamsayı değerleri geometrik dağıtımını üretir.|  
|[negative_binomial_distribution Sınıfı](../standard-library/negative-binomial-distribution-class.md)|Tamsayı değerleri negatif terimli dağıtımını üretir.|  
  
 [[Rastgele sayı dağıtımları](#distributions)]  
  
#### <a name="normal-distributions"></a>Normal dağıtımları  
  
|||  
|-|-|  
|[cauchy_distribution Sınıfı](../standard-library/cauchy-distribution-class.md)|(Kayan nokta) gerçek değerlerin Cauchy dağıtım üretir.|  
|[chi_squared_distribution Sınıfı](../standard-library/chi-squared-distribution-class.md)|Bir kikare dağılımı (kayan nokta) gerçek değerlerin üretir.|  
|[fisher_f_distribution Sınıfı](../standard-library/fisher-f-distribution-class.md)|Bir F-dağıtım (Snedecor'ın F dağıtım veya Fisher Snedecor dağıtım olarak da bilinir) (kayan nokta) gerçek değerlerin üretir.|  
|[lognormal_distribution Sınıfı](../standard-library/lognormal-distribution-class.md)|Günlük normal dağıtım (kayan nokta) gerçek değerlerin üretir.|  
|[normal_distribution Sınıfı](../standard-library/normal-distribution-class.md)|Normal bir (Gauss) dağıtım (kayan nokta) gerçek değerlerin üretir.|  
|[student_t_distribution Sınıfı](../standard-library/student-t-distribution-class.md)|Öğrencinin üreten *t*-(kayan nokta) gerçek değerlerin dağıtım.|  
  
 [[Rastgele sayı dağıtımları](#distributions)]  
  
#### <a name="poisson-distributions"></a>Poisson dağıtımları  
  
|||  
|-|-|  
|[exponential_distribution Sınıfı](../standard-library/exponential-distribution-class.md)|(Kayan nokta) gerçek değerlerin bir üstel dağılımı üretir.|  
|[extreme_value_distribution Sınıfı](../standard-library/extreme-value-distribution-class.md)|Extreme değer dağıtımı (kayan nokta) gerçek değerlerin üretir.|  
|[gamma_distribution Sınıfı](../standard-library/gamma-distribution-class.md)|Gama dağıtım (kayan nokta) gerçek değerlerin üretir.|  
|[poisson_distribution Sınıfı](../standard-library/poisson-distribution-class.md)|Tamsayı değerleri Poisson dağıtımını üretir.|  
|[weibull_distribution Sınıfı](../standard-library/weibull-distribution-class.md)|(Kayan nokta) gerçek değerlerin WEIBULL dağıtım üretir.|  
  
 [[Rastgele sayı dağıtımları](#distributions)]  
  
#### <a name="sampling-distributions"></a>Örnekleme dağıtımları  
  
|||  
|-|-|  
|[discrete_distribution Sınıfı](../standard-library/discrete-distribution-class.md)|Bir ayrık tamsayı dağıtım üretir.|  
|[piecewise_constant_distribution Sınıfı](../standard-library/piecewise-constant-distribution-class.md)|Bir piecewise üretir (kayan nokta) gerçek değerlerin sabit dağıtım.|  
|[piecewise_linear_distribution Sınıfı](../standard-library/piecewise-linear-distribution-class.md)|Bir piecewise üretir (kayan nokta) gerçek değerlerin doğrusal dağıtım.|  
  
 [[Rastgele sayı dağıtımları](#distributions)]  
  
### <a name="utility-functions"></a>Yardımcı işlevleri  
 Bu bölümde sağlanan genel yardımcı işlevleri listeler `<random>` üstbilgi.  
  
|||  
|-|-|  
|[seed_seq Sınıfı](../standard-library/seed-seq-class.md)|Ağırlıklı olmayan karıştırılmış çekirdek dizisi oluşturur. Rastgele variate akışları çoğaltılmasını önlemek için kullanılır. Birçok URNGs motorlarından örneği kullanışlıdır.|  
  
### <a name="operators"></a>İşleçler  
 Bu bölümde sağlanan işleçleri listeler `<random>` üstbilgi.  
  
|||  
|-|-|  
|`operator==`|İşlecinin sol tarafındaki URNG sağ tarafında altyapısı eşit olup olmadığını sınar.|  
|`operator!=`|İşlecinin sol tarafındaki URNG sağ tarafında altyapısı eşit olup olmadığını sınar.|  
|`operator<<`|Durum bilgilerini bir akışa yazar.|  
|`operator>>`|Durum bilgilerini bir akıştan ayıklar.|  
  
##  <a name="engdist">Motorları ve dağıtımları</a>  
 Her tanımlanan bu şablon sınıf kategorileri hakkında bilgi için aşağıdaki bölümlere bakın `<random>`. Bu şablon sınıf kategorileri her ikisinin bir tür bağımsız değişkeni olarak alın ve gerçek bağımsız değişken türü olarak, aşağıdaki gibi izin verilen türünün özelliklerini tanımlamak için paylaşılan şablon parametresi adları kullanın:  
  
- `IntType` gösteren bir `short`, `int`, `long`, `long long`, `unsigned short`, `unsigned int`, `unsigned long`, veya `unsigned long long`.  
  
- `UIntType` gösterir `unsigned short`, `unsigned int`, `unsigned long`, veya `unsigned long long`.  
  
- `RealType` gösteren bir `float`, `double`, veya `long double`.  
  
### <a name="engines"></a>Altyapıları  
 [Altyapısını şablonları](#eng) ve [motoru bağdaştırıcı şablonları](#engadapt) parametreleri özelleştirmek oluşturulan Oluşturucu şablonlarıdır.  
  
 Bir *altyapısı* bir sınıf veya Şablon sınıfı (oluşturucuları) örneklerinin işlem rastgele sayılar kaynağı olarak hep minimum ve maksimum değer arasında dağıtılır. Bir *motoru bağdaştırıcı* bazı diğer rastgele sayı altyapısı tarafından üretilen ve herhangi bir türdeki bir algoritma bu değerleri uygulamaya alma değerlere göre farklı rastgele özelliklere sahip değerleri dizisi sunar.  
  
 Her altyapısı ve motoru bağdaştırıcı aşağıdaki üyeleri vardır:  
  
- `typedef` `numeric-type` `result_type` Oluşturucu tarafından 's döndürülen tür `operator()`. `numeric-type` Örneklemesi üzerinde şablon parametresi olarak geçirilir.  
  
- `result_type operator()` arasında hep dağıtılmış değerleri döndürür `min()` ve `max()`.  
  
- `result_type min()` Oluşturucu tarafından 's döndürülen en küçük değeri döndürür `operator()`. Altyapısı bağdaştırıcıları kullanmak temel altyapısının `min()` sonucu.  
  
- `result_type max()` Oluşturucu tarafından 's döndürülen en büyük değeri verir `operator()`. Zaman `result_type` bir tam sayı (tamsayı değerli) türü, `max()` gerçekten (dahil); döndürülebilecek en büyük değer olduğunda `result_type` bir kayan nokta (gerçek değerli) türü, `max()` en küçük değer tüm değerden büyüktür (dahil olmayan) döndürülebilir. Altyapısı bağdaştırıcıları kullanmak temel altyapısının `max()` sonucu.  
  
- `void seed(result_type s)` Çekirdek değeri ile oluşturucunun çekirdeğini oluşturur `s`. İmza altyapılarını olduğu `void seed(result_type s = default_seed)` varsayılan parametre desteği (altyapısı bağdaştırıcıları tanımlamak ayrı bir `void seed()`, sonraki alt bölümüne bakın).  
  
- `template <class Seq> void seed(Seq& q)` Oluşturucunun çekirdeğini oluşturur kullanarak bir [seed_seq](../standard-library/seed-seq-class.md)`Seq`.  
  
-   Bir açık oluşturucu bağımsız değişkeni ile `result_type x` göre çağırma sanki sağlanmış bir oluşturucuyu oluşturan `seed(x)`.  
  
-   Bir açık oluşturucu bağımsız değişkeni ile `seed_seq& seq` göre çağırma sanki sağlanmış bir oluşturucuyu oluşturan `seed(seq)`.  
  
- `void discard(unsigned long long count)` etkili bir şekilde çağırır `operator()` `count` zaman ve her bir değeri atar.  
  
 **Altyapısını bağdaştırıcıları** Ayrıca bu üyeleri desteği (`Engine` şablonu öğesinin ilk parametresi, temel altyapısının türünü belirleme bir motoru bağdaştırıcı olduğu):  
  
-   Temel altyapısının varsayılan oluşturucusundan gibi oluşturucunun başlatmak için varsayılan bir oluşturucu.  
  
-   Bir açık oluşturucu bağımsız değişkeni ile `const Engine& eng`. Bu temel altyapısını kullanarak kopyalama yapım desteklemektir.  
  
-   Bir açık oluşturucu bağımsız değişkeni ile `Engine&& eng`. Bu temel altyapısını kullanarak taşıma yapım desteklemektir.  
  
- `void seed()` Bu oluşturucu temel altyapısının varsayılan çekirdek değeri ile başlatır.  
  
- `const Engine& base()` Oluşturucu oluşturmak için kullanılan temel altyapısı döndürür özelliği işlev.  
  
 Her altyapısı tutan bir *durumu* yapılan sonraki çağrılar tarafından üretilen değerler sırasını belirleyen `operator()`. Aynı türde motorlarından örneği iki oluşturucuları durumlarını kullanarak karşılaştırılabilir `operator==` ve `operator!=`. İki durumlu eşit olarak karşılaştırırsanız, bunların değerleri aynı dizisini oluşturur. Bir nesnenin durumu bir akışa 32-bit işaretsiz değerleri dizisi olarak kullanarak kaydedilebilir `operator<<` oluşturucunun. Durum kaydetme tarafından değiştirilmez. Kaydedilen bir duruma kullanarak aynı türde bir altyapısı örneği Oluşturucu içine okunabilir `operator>>`.  
  
### <a name="distributions"></a>Dağıtımları  
 A [rastgele sayı dağıtımları](#distributions) bir sınıf ya da şablon sınıf örneklerinin dönüştürme altyapısı, bir belirli dağıtım paylaşımınız rastgele sayılar akışa elde hep dağıtılmış rastgele sayılar akışı. Her dağıtım aşağıdaki üyeleri vardır:  
  
- `typedef` `numeric-type` `result_type` Dağıtım tarafından 's döndürülen tür `operator()`. `numeric-type` Örneklemesi üzerinde şablon parametresi olarak geçirilir.  
  
- `template <class URNG> result_type operator()(URNG& gen)` Dağıtım 's tanımı göre kullanılarak dağıtılır değerleri döndürür `gen` hep dağıtılmış rastgele değerler ve depolanan bir kaynak olarak *dağıtım parametrelerinin*.  
  
- `template <class URNG> result_type operator()(URNG& gen, param_type p)` Dağıtılmış dağıtım 's tanımını uygun değerleri döndürür kullanarak `gen` hep dağıtılmış rastgele değerler ve parametreleri yapısı bir kaynak olarak `p`.  
  
- `typedef` `unspecified-type` `param_type` Paket parametrelerinin isteğe bağlı olarak geçirilir `operator()` ve saklı parametreleri yerine dönüş değeri üretmek için kullanılır.  
  
-   A `const param&` oluşturucu bağımsız değişkeni saklı parametrelerinden başlatır.  
  
- `param_type param() const` saklı parametreleri alır.  
  
- `void param(const param_type&)` kendi bağımsız değişkende depolanan parametreleri ayarlar.  
  
- `result_type min()` Dağıtım tarafından 's döndürülen en düşük değer verir `operator()`.  
  
- `result_type max()` Dağıtım tarafından 's döndürülen en büyük değeri verir `operator()`. Zaman `result_type` bir tam sayı (tamsayı değerli) türü, `max()` gerçekten (dahil); döndürülebilecek en büyük değer olduğunda `result_type` bir kayan nokta (gerçek değerli) türü, `max()` en küçük değer tüm değerden büyüktür (dahil olmayan) döndürülebilir.  
  
- `void reset()` herhangi bir önbelleğe alınan değeri atar böylece sonraki çağrı sonucunu `operator()` çağırmadan önce altyapısından alınan değerlere bağlı değildir.  
  
 Bir parametre yapısı tüm dağıtım için gerekli parametreleri depolayan bir nesnedir. Aşağıdakileri içerir:  
  
- `typedef` `distribution-type` `distribution_type`, kendi dağıtım türündeki.  
  
-   Aynı parametre alan bir veya daha fazla oluşturucular dağıtım oluşturucular Al listeler.  
  
-   Dağıtım aynı parametre erişim işlevleri.  
  
-   Eşitlik ve eşitsizlik Karşılaştırma işleçleri.  
  
 Daha fazla bilgi için bu makalede daha önce bağlı bunun altındaki başvuru konuları bakın.  
  
##  <a name="comments">Açıklamalar</a>  
 Visual Studio'da iki çok yararlı URNGs vardır —`mt19937` ve `random_device`— bu karşılaştırma tabloda gösterildiği gibi:  
  
|URNG|Hızlı|Şifreleme güvenli|Seedable|Belirleyici|  
|----------|-----------|---------------------|---------------|--------------------|  
|`mt19937`|Evet|Hayır|Evet|Evet<sup>*</sup>|  
|`random_device`|Hayır|Evet|Hayır|Hayır|  
  
 <sup>* Bilinen bir çekirdek ile sağlandığında.</sup>  
  
 ISO C++ Standart gerektirmez rağmen `random_device` şifreli olarak güvenli olacak şekilde uygulanan şifreleme açısından olacak şekilde Visual Studio'da güvenli. ("Şifreleme açısından güvenli" terimi garanti anlamına gelmez, ancak en az bir entropi düzeyine başvuruyor — ve bu nedenle, öngörülebilirlik düzeyi — verilen rastgele algoritması sağlar. Daha fazla bilgi için Wikipedia makalesine bakın [şifreleme açısından güvenli geçici rastgele sayı üreticisinin](http://go.microsoft.com/fwlink/p/?linkid=398017).) ISO C++ Standart bu gerektirmediğinden, diğer platformlar uygulayabilir `random_device` basit sözde rastgele sayı üreticisinin (şifreleme açısından güvenli) ve yalnızca may başka bir oluşturucu için bir çekirdek kaynağı olarak uygun olabilir. Kullanırken bu platformlar için sağlanan belgeleri gözden `random_device` platformlar arası kod.  
  
 Tanımı tarafından `random_device` sonuçları tekrarlanabilir değildir ve bir yan etkisi olan diğer URNGs önemli ölçüde yavaş çalışabilir. Şifreleme açısından olması için gerekli olmayan uygulamaların çoğu kullanım güvenli `mt19937` veya benzer bir altyapıya çağrısıyla çekirdek isteyebilirsiniz ancak `random_device`gösterildiği gibi [kod örneğinde](#code).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)

