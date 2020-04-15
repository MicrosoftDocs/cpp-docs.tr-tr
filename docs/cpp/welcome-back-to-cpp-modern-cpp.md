---
title: C++'ya tekrar hoş geldiniz - Modern C++
description: Modern C++'daki yeni programlama deyimlerini ve bunların mantığını açıklar.
ms.date: 01/10/2020
ms.topic: conceptual
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
ms.openlocfilehash: 7d0fcb623162713b845107bbf00669af7ae5ca98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369501"
---
# <a name="welcome-back-to-c---modern-c"></a>C++'ya tekrar hoş geldiniz - Modern C++

Kuruluşundan bu yana, C++ dünyada en yaygın olarak kullanılan programlama dillerinden biri haline gelmiştir. İyi yazılmış C++ programları hızlı ve verimlidir. Dil diğer dillere göre daha esnektir: En yüksek soyutlama düzeylerinde ve silikon seviyesinde çalışabilir. C++, son derece optimize edilmiş standart kitaplıklar sağlar. Hızı en üst düzeye çıkarmak ve bellek gereksinimlerini en aza indirmek için düşük seviyeli donanım özelliklerine erişim sağlar. C++'ı kullanarak çok çeşitli uygulamalar oluşturabilirsiniz. Oyunlar, cihaz sürücüleri ve yüksek performanslı bilimsel yazılımlar. Gömülü programlar. Windows istemci uygulamaları. Diğer programlama dilleri için kitaplıklar ve derleyiciler bile C++'da yazılır.

C++ için orijinal gereksinimlerden biri C diliyle geriye dönük uyumluluktu. Sonuç olarak, C++, ham işaretçiler, diziler, null-sonlandırılan karakter dizeleri ve diğer özelliklerle C stili programlamaya her zaman izin vermiştir. Bunlar büyük performans sağlayabilir, ancak aynı zamanda hata ve karmaşıklık yumurtlayabilir. C++'ın evrimi, C tarzı deyimlerin kullanılması ihtiyacını büyük ölçüde azaltan özellikleri vurgulamıştır. Eski C programlama tesisleri ihtiyacınız olduğunda vardır, ancak modern C++ kodu ile onlara daha az ve daha az ihtiyaç duymalısınız. Modern C++ kodu daha basit, daha güvenli, daha zarif ve her zamanki gibi hızlıdır.

Aşağıdaki bölümlerde modern C++'ın ana özelliklerihakkında genel bir bakış sağlay.) Aksi belirtilmedikçe, burada listelenen özellikler C++11 ve sonraki yerlerde kullanılabilir. Microsoft C++ derleyicisinde, [/std](../build/reference/std-specify-language-standard-version.md) derleyiciseçeneğini, projeniz için hangi standardın kullanılacağını belirtmek için ayarlayabilirsiniz.

## <a name="resources-and-smart-pointers"></a>Kaynaklar ve akıllı işaretçiler

C tarzı programlama hataların önemli sınıflarından biri *bellek sızıntısı*. Sızıntılar genellikle **yeni**ile ayrılan bellek için **sil** arama hatası neden olur. Modern C++ *kaynak edinme* ilkesinin başlangıç (RAII) olduğunu vurgular. Fikir basit. Kaynaklar (yığın bellek, dosya tutamaçları, soketleri vb.) bir nesneye *ait* olmalıdır. Bu nesne, oluşturucuda yeni ayrılan kaynağı oluşturur veya alır ve onu yıkıcısında siler. RAII ilkesi, sahip olan nesne kapsam dışına çıktığında tüm kaynakların düzgün bir şekilde işletim sistemine döndürülmesini garanti eder.

RAII ilkelerinin kolay benimsenmesini desteklemek için, C++ Standart Kitaplığı üç akıllı işaretçi türü sağlar: [std::unique_ptr](../standard-library/unique-ptr-class.md), [std::shared_ptr](../standard-library/shared-ptr-class.md), ve [std::weak_ptr](../standard-library/weak-ptr-class.md). Akıllı işaretçi, sahip olduğu belleğin tahsisini ve silinmesini işler. Aşağıdaki örnekte, bir dizi üyesi olan bir sınıf, çağrıdaki `make_unique()`yığına ayrılmıştır. **Yeni** ve **silme** çağrıları `unique_ptr` sınıf tarafından kapsüllenir. Bir `widget` nesne kapsam dışına çıktığında, unique_ptr yıkıcı çağrılacak ve dizi için ayrılan belleği serbest bırakacaktır.  

```cpp
#include <memory>
class widget
{
private:
    std::unique_ptr<int> data;
public:
    widget(const int size) { data = std::make_unique<int>(size); }
    void do_something() {}
};

void functionUsingWidget() {
    widget w(1000000);   // lifetime automatically tied to enclosing scope
                // constructs w, including the w.data gadget member
    // ...
    w.do_something();
    // ...
} // automatic destruction and deallocation for w and w.data

```

Mümkün olduğunda, yığın bellek ayırırken akıllı bir işaretçi kullanın. Yeni ve silme işleçlerini açıkça kullanmanız gerekiyorsa, RAII ilkesine uyun. Daha fazla bilgi için [Object yaşam süresi ve kaynak yönetimi (RAII)](object-lifetime-and-resource-management-modern-cpp.md)konusuna bakın.

## <a name="stdstring-and-stdstring_view"></a>std::dize ve std::string_view

C stili dizeleri hataların başka bir önemli kaynağıdır. [Std:string ve std::wstring](../standard-library/basic-string-class.md)kullanarak, C stili dizeleri ile ilişkili hemen hemen tüm hataları ortadan kaldırabilirsiniz. Ayrıca arama, ek, ön bekleme ve benzeri için üye işlevlerin yararına kazanırsınız. Her ikisi de hız için son derece optimize edin. Bir dizeyi yalnızca salt okunur erişim gerektiren bir işleve aktarırken, C++17'de daha fazla performans avantajı için [std::string_view](../standard-library/basic-string-view-class.md) kullanabilirsiniz.

## <a name="stdvector-and-other-standard-library-containers"></a>std::vektör ve diğer Standart Kütüphane kapsayıcıları

Standart Kütüphane kapsayıcılarının tümü RAII ilkesine uyar. Öğelerin güvenli geçiş için yineleyiciler sağlar. Ve performans için son derece optimize edilmiş ve doğruluk açısından kapsamlı bir şekilde test edilmiştir. Bu kapsayıcıları kullanarak, özel veri yapılarında tanıtılan hata veya verimsizlikleri ortadan kaldırırsınız. Ham diziler yerine C++'da sıralı kapsayıcı olarak [vektörü](../standard-library/vector-class.md) kullanın.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Varsayılan bağdaştırıcı kapsayıcı olarak [haritayı](../standard-library/map-class.md) (değil) `unordered_map`kullanın. Dejenere ve [çok](../standard-library/multiset-class.md) durumlar için [set,](../standard-library/set-class.md) [çok eşlilik](../standard-library/multimap-class.md)ve çoklu set kullanın.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

Performans optimizasyonu gerektiğinde şunları kullanmayı düşünün:

- Katıştırma işleminde dizi [türü,](../standard-library/array-class-stl.md) örneğin bir sınıf üyesi olarak önemlidir.

- [unordered_map](../standard-library/unordered-map-class.md)gibi sırasız bağdaştırıcı kaplar. Bunlar daha düşük eleman başına ek yükü ve sabit zamanlı arama var, ancak doğru ve verimli kullanımı daha zor olabilir.

- Sıralanmış. `vector` Daha fazla bilgi için [Algoritmalar'a](../cpp/algorithms-modern-cpp.md)bakın.

C tarzı diziler kullanmayın. Verilere doğrudan erişimi gereken eski API'ler için `f(vec.data(), vec.size());` bunun yerine erişim yöntemleri kullanın. Kapsayıcılar hakkında daha fazla bilgi için [C++ Standart Kitaplık Kapsayıcıları'na](../standard-library/stl-containers.md)bakın.

## <a name="standard-library-algorithms"></a>Standart Kitaplık algoritmaları

Programınız için özel bir algoritma yazmanız gerektiğini varsaymadan önce, önce C++ Standart Kitaplığı [algoritmalarını](../standard-library/algorithm.md)gözden geçirin. Standart Kitaplık, arama, sıralama, filtreleme ve rasgeleleştirme gibi birçok yaygın işlem için sürekli büyüyen bir algoritma yelpazesi içerir. Matematik kütüphanesi geniştir. C++17'den başlayarak birçok algoritmanın paralel sürümleri sağlanır.

Aşağıda bazı önemli örnekler verilmiştir:

- **for_each,** varsayılan geçiş algoritması (döngüler için aralık tabanlı ile birlikte).

- **dönüştürme**, konteyner elemanlarının yerinde olmayan modifikasyonu için

- **find_if,** varsayılan arama algoritması.

- **sıralama,** **lower_bound**ve diğer varsayılan sıralama ve arama algoritmaları.

Bir karşılaştırıcı yazmak için, **<** sıkı kullanın ve zaman zaman *lambdas adlı* kullanın.

```cpp
auto comp = [](const widget& w1, const widget& w2)
     { return w1.weight() < w2.weight(); }

sort( v.begin(), v.end(), comp );

auto i = lower_bound( v.begin(), v.end(), comp );
```

## <a name="auto-instead-of-explicit-type-names"></a>açık tür adları yerine otomatik

C++11 değişken, işlev ve şablon bildirimlerinde kullanılmak üzere [otomatik](auto-cpp.md) anahtar kelimeyi tanıttı. **otomatik,** derleyiciye nesnenin türünü anlamasını söyler, böylece açıkça yazmanız gerekmez. **otomatik** özellikle çıkarılan tür iç içe bir şablon olduğunda yararlıdır:

```cpp
map<int,list<string>>::iterator i = m.begin(); // C-style
auto i = m.begin(); // modern C++
```

## <a name="range-based-for-loops"></a>Döngüler için aralık tabanlı

Diziler ve kapsayıcılar üzerinde C stili yineleme dizin oluşturma hatalarına eğilimlidir ve aynı zamanda türü sıkıcıdır. Bu hataları ortadan kaldırmak ve kodunuzu daha okunabilir hale getirmek için, hem Standart Kitaplık kapsayıcıları hem de ham dizileri içeren döngüler için aralık tabanlı kullanın. Daha fazla bilgi [için ifade için Aralık tabanlı'ya](../cpp/range-based-for-statement-cpp.md)bakın.

```cpp
#include <iostream>
#include <vector>

int main()
{
    std::vector<int> v {1,2,3};

    // C-style
    for(int i = 0; i < v.size(); ++i)
    {
        std::cout << v[i];
    }

    // Modern C++:
    for(auto& num : v)
    {
        std::cout << num;
    }
}
```

## <a name="constexpr-expressions-instead-of-macros"></a>makrolar yerine constexpr ifadeler

C ve C++'daki makrolar, derlemeden önce önişlemci tarafından işlenen belirteçlerdir. Makro belirteci her örneği, dosya derlenmeden önce tanımlı değeri veya ifadesi ile değiştirilir. Makrolar derleme zamanı sabit değerlerini tanımlamak için C stili programlamada yaygın olarak kullanılır. Ancak, makrolar hataya açık ve hata ayıklama zor. Modern C++'da derleme zamanı sabitleri için [constexpr](constexpr-cpp.md) değişkenlerini tercih edmelisiniz:

```cpp
#define SIZE 10 // C-style
constexpr int size = 10; // modern C++
```

### <a name="uniform-initialization"></a>Tekdüze başlatma

Modern C++'da, herhangi bir tür için ayraç başlatma yı kullanabilirsiniz. Bu başlatma biçimi, dizileri, vektörleri veya diğer kapsayıcıları başlatmada özellikle kullanışlıdır. Aşağıdaki örnekte, `v2` üç örnekle başharfe `S`işlenir. `v3`parantez kullanılarak başharflere `S` alınan üç örnekle başharfe işlenir. Derleyici, bildirilen türe göre her öğenin türünü `v3`çıkartıyor.

```cpp
#include <vector>

struct S
{
    std::string name;
    float num;
    S(std::string s, float f) : name(s), num(f) {}
};

int main()
{
    // C-style initialization
    std::vector<S> v;
    S s1("Norah", 2.7);
    S s2("Frank", 3.5);
    S s3("Jeri", 85.9);

    v.push_back(s1);
    v.push_back(s2);
    v.push_back(s3);

    // Modern C++:
    std::vector<S> v2 {s1, s2, s3};

    // or...
    std::vector<S> v3{ {"Norah", 2.7}, {"Frank", 3.5}, {"Jeri", 85.9} };

}
```

Daha fazla bilgi için [Bkz. Ayraç başlatma.](initializing-classes-and-structs-without-constructors-cpp.md)

## <a name="move-semantics"></a>Taşı semantik

Modern C++ gereksiz bellek kopyalarını ortadan kaldırmak mümkün hale *getirmek, taşıma semantik*sağlar. Dilin önceki sürümlerinde, kopyalar bazı durumlarda kaçınılmazdı. *Bir hareket* işlemi, bir kopyasını oluşturmadan kaynağın sahipliğini bir nesneden diğerine aktarın. Bir kaynağa sahip bir sınıf uygularken (yığın bellek, dosya işletmeleri vb. gibi), bir *hareket oluşturucu* tanımlayAbilir ve *atama işlecinin* taşınmasını sağlayabilirsiniz. Derleyici, kopyanın gerekli olmadığı durumlarda aşırı yük çözümü sırasında bu özel üyeleri seçer. Standart Kitaplık kapsayıcı türleri, tanımlanmışsa nesneler üzerinde taşı oluşturucuyu çağırır. Daha fazla bilgi için [bkz.](move-constructors-and-move-assignment-operators-cpp.md)

## <a name="lambda-expressions"></a>Lambda ifadeleri

C stili programlamada, bir *işlev bir işlev işaretçisi*kullanılarak başka bir işleve geçirilebilir. İşlev işaretçileri korumak ve anlamak için sakıncalıdır. Atıfta bulunulan işlev, çağrıldığı noktadan uzakta, kaynak kodun başka bir yerinde tanımlanabilir. Ayrıca, tip güvenli değiller. Modern C++, [()](function-call-operator-parens.md) işleci geçersiz kılan *işlev nesneleri,* sınıflar sağlar ve bu da işlev gibi çağrılmasını sağlar. İşlev nesneleri oluşturmak için en uygun yolu satır içinde [lambda ifadeler](../cpp/lambda-expressions-in-cpp.md)ile. Aşağıdaki örnek, işlev nesnesini geçirmek için lambda ifadesinin `for_each` nasıl kullanılacağını, işlevin vektördeki her öğeyi çağıracağını gösterir:

```cpp
    std::vector<int> v {1,2,3,4,5};
    int x = 2;
    int y = 4;
    auto result = find_if(begin(v), end(v), [=](int i) { return i > x && i < y; });
```

Lambda ifadesi `[=](int i) { return i > x && i < y; }` "tek bir tür `int` bağımsız değişkeni alan ve bağımsız değişkenin daha büyük `x` ve daha `y`az olup olmadığını gösteren bir boolean döndüren işlev" olarak okunabilir. Değişkenlerin `x` ve `y` çevredeki bağlamın lambda kullanılabileceğini unutmayın. Bu `[=]` değişkenlerin değere göre *yakalandığını* belirtir; başka bir deyişle, lambda ifadesi bu değerlerin kendi kopyaları vardır.

## <a name="exceptions"></a>Özel durumlar

Modern C++, hata koşullarını bildirmenin ve işlemenin en iyi yolu olarak hata kodları yerine özel durumları vurgular. Daha fazla bilgi için, [özel durumlar ve hata işleme için Modern C++ en iyi uygulamaları](errors-and-exception-handling-modern-cpp.md)bakın.

## <a name="stdatomic"></a>std::atom

İş parçacıkları arası iletişim mekanizmaları için C++ Standart Kitaplığı [std::atomik](../standard-library/atomic-structure.md) yapı ve ilgili türleri kullanın.

## <a name="stdvariant-c17"></a>std::varyant (C++17)

Birliş genellikle C stili programlamada, farklı türdeki üyelerin aynı bellek konumunu işgal etmesini sağlayarak belleği korumak için kullanılır. Ancak, sendikalar tür güvenli değildir ve programlama hatalarına açıktır. C++17, [std:varyant](../standard-library/variant-class.md) sınıfını birliş için daha sağlam ve güvenli bir alternatif olarak sunar. [Std:visit](../standard-library/variant-functions.md#visit) işlevi, bir tür güvenli bir `variant` şekilde bir türün üyelerine erişmek için kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Referansı](../cpp/cpp-language-reference.md)\
[Lambda İfadeler](../cpp/lambda-expressions-in-cpp.md)\
[C++ Standart Kitaplık](../standard-library/cpp-standard-library-reference.md)\
[Microsoft C++ dil uygunluk tablosu](../overview/visual-cpp-language-conformance.md)
