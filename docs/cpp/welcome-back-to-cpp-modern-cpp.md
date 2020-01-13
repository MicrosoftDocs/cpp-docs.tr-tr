---
title: Modern 'e C++ geri hoş geldinizC++
description: Modern C++ ve bu kişilerin korsiyondaki yeni programlama ILT OMS 'leri açıklar.
ms.date: 01/10/2020
ms.topic: conceptual
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
ms.openlocfilehash: 9630322024e639f9e5db1888dac5a1530befc716
ms.sourcegitcommit: ba129dc55dc3ff638f3af5ac0e87ec2ca1cb2674
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75869727"
---
# <a name="welcome-back-to-c---modern-c"></a>Modern 'e C++ geri hoş geldinizC++

Oluşturulduktan sonra, C++ dünyanın en yaygın olarak kullanılan programlama dillerinden biri haline geldi. İyi yazılmış C++ programlar hızlı ve verimlidir. Dil diğer dillerden daha esnektir: Bu, en yüksek soyutlama düzeylerinde ve Silicon 'in düzeyinde çalışabilir. C++yüksek oranda iyileştirilmiş standart kitaplıklar sağlar. Düşük düzeyli donanım özelliklerine erişim sağlar ve hızı en üst düzeye çıkarabilir ve bellek gereksinimlerini en aza indirir. Kullanarak C++, çok çeşitli uygulamalar oluşturabilirsiniz. Oyunlar, cihaz sürücüleri ve yüksek performanslı bilimsel yazılımlar. Katıştırılmış programlar. Windows istemci uygulamaları. Diğer programlama dillerine yönelik kitaplıklar ve derleyiciler de ' de C++yazılmıştır.

İçin C++ özgün gereksinimlerinden biri, C diliyle geriye dönük uyumlulukta. Sonuç olarak, C++ ham işaretçiler, diziler, null ile sonlandırılmış karakter dizeleri ve diğer özelliklerle, her zaman C stili programlamaya izin verilir. Harika performansı etkinleştirebilirler, ancak Ayrıca hata ve karmaşıklık oluşturabilir. ' İn C++ gelişiminde, C stili ıoms kullanma gereksinimini önemli ölçüde azaltan vurgulanmış özellikler vardır. Eski C programlama olanakları bunlara ihtiyacınız olduğunda, ancak modern C++ kod ile daha az ve daha az ihtiyacınız olması gerekir. Modern C++ kod daha basit, daha güvenli, daha zarif ve yine de her zamankinden daha hızlı.

Aşağıdaki bölümlerde modern C++'ın ana özelliklerine genel bir bakış sağlanmaktadır. Aksi belirtilmedikçe, burada listelenen özellikler C++ 11 ve üzeri sürümlerde kullanılabilir. Microsoft C++ derleyicisinde, [/STD](../build/reference/std-specify-language-standard-version.md) derleyici seçeneğini, projeniz için hangi standart sürümünün kullanılacağını belirtmek için ayarlayabilirsiniz.

## <a name="resources-and-smart-pointers"></a>Kaynaklar ve akıllı işaretçiler

C stili programlamada önemli hata sınıflarından biri *bellek sızıntısı*. Sızıntı genellikle, **Yeni**ile ayrılmış bellek için **silme** çağrısı başarısız olur. Modern C++ *kaynak alımı başlatma* (Rat) ilkesini vurgular. Fikir basittir. Kaynaklar (yığın belleği, dosya tanıtıcıları, yuvalar vb.) bir nesneye *ait* olmalıdır. Bu nesne, Oluşturucu içinde yeni ayrılmış kaynağı oluşturur veya alır ve yıkıcısında siler. Aii 'nin prensibi, sahip olduğu nesne kapsam dışına geçtiğinde tüm kaynakların işletim sistemine doğru bir şekilde döndürüldüğünden emin garanti eder.

AII ilkelerinin C++ kolay benimsenmesini desteklemek Için standart kitaplık üç akıllı işaretçi türü sağlar: [std:: unique_ptr](../standard-library/unique-ptr-class.md), [std:: shared_ptr](../standard-library/shared-ptr-class.md)ve [std:: weak_ptr](../standard-library/weak-ptr-class.md). Akıllı işaretçi, sahip olduğu belleği ayırmayı ve silmeyi işler. Aşağıdaki örnek, `make_unique()`çağrısında yığında ayrılan bir dizi üyesine sahip bir sınıfı gösterir. **New** ve **Delete** çağrıları `unique_ptr` sınıfıyla kapsüllenir. `widget` nesne kapsam dışına geçtiğinde, unique_ptr yok edicisi çağrılır ve dizi için ayrılan belleği serbest bırakılır.  

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

Mümkün olduğunda, yığın belleği ayrılırken akıllı bir işaretçi kullanın. New ve DELETE işleçlerini açık bir şekilde kullanmanız gerekiyorsa, RAYıı 'nin ilkesini izleyin. Daha fazla bilgi için bkz. [nesne yaşam süresi ve kaynak yönetimi (ÇII)](object-lifetime-and-resource-management-modern-cpp.md).

## <a name="stdstring-and-stdstring_view"></a>std:: String ve std:: string_view

C stili dizeler, başka bir büyük hata kaynağıdır. [Std:: String ve std:: wstring](../standard-library/basic-string-class.md)kullanarak, C stili dizeleriyle ilişkili tüm hataları ortadan kaldırabilirsiniz. Ayrıca, arama, ekleme, ön bekleyen gibi üye işlevlerinin avantajına sahip olursunuz. Her ikisi de hız için en iyi duruma getirilmiştir. Bir dizeyi yalnızca salt okuma erişimi gerektiren bir işleve geçirirken, C++ 17 ' de, daha da fazla performans avantajı sağlamak için [std:: string_view](../standard-library/basic-string-view-class.md) kullanabilirsiniz.

## <a name="stdvector-and-other-standard-library-containers"></a>std:: vector ve diğer standart kitaplık kapsayıcıları

Standart Kitaplık kapsayıcıları tüm Rat ilkesini izler. Bunlar, öğelerin güvenli çapraz geçişi için yineleyiciler sağlar. Ayrıca, performans için yüksek oranda iyileştirilmiştir ve doğruluk açısından tamamen test edilmiştir. Bu kapsayıcıları kullanarak, özel veri yapılarında ortaya çıkabilecek hatalara veya verimsizlikleri potansiyelini ortadan kaldırabilirsiniz. Ham diziler yerine [vektör](../standard-library/vector-class.md) 'yi içinde C++sıralı bir kapsayıcı olarak kullanın.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Varsayılan ilişkilendirilebilir kapsayıcı olarak [eşleme](../standard-library/map-class.md) (`unordered_map`değil) kullanın. Bozuk ve çok sayıda servis talebi için [set](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md)ve [multıuse](../standard-library/multiset-class.md) kullanın.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

Performans iyileştirmesi gerektiğinde şunu kullanmayı göz önünde bulundurun:

- Gömme önemli olduğunda [dizi](../standard-library/array-class-stl.md) türü, örneğin bir sınıf üyesi olarak.

- [Unordered_map](../standard-library/unordered-map-class.md)gibi sırasız ilişkilendirilebilir kapsayıcılar. Bunlar, öğe başına ek yüke ve sabit zamanlı aramaya sahiptir, ancak doğru ve verimli bir şekilde kullanılması daha zor olabilir.

- Sıralanmış `vector`. Daha fazla bilgi için bkz. [algoritmalar](../cpp/algorithms-modern-cpp.md).

C stili dizileri kullanmayın. Verilere doğrudan erişmesi gereken eski API 'Ler için, bunun yerine `f(vec.data(), vec.size());` gibi erişimci yöntemlerini kullanın. Kapsayıcılar hakkında daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

## <a name="standard-library-algorithms"></a>Standart Kitaplık algoritmaları

Programınız için özel bir algoritma yazmanız gerektiğini varsaymadan önce, önce C++ standart kitaplık [algoritmalarını](../standard-library/algorithm.md)gözden geçirin. Standart Kitaplık, arama, sıralama, filtreleme ve rastgele hale getirme gibi yaygın birçok işlem için sürekli büyüyen bir algoritma içerir. Matematik kitaplığı kapsamlıdır. C++ 17 ' den başlayarak birçok algoritmaların paralel sürümleri sağlanır.

Aşağıda bazı önemli örnekler verilmiştir:

- **for_each**, varsayılan çapraz geçiş algoritması (döngüler için Aralık tabanlı ile birlikte).

- kapsayıcı öğelerinin yerinde değiştirilmesi için **dönüştürme**

- Varsayılan arama algoritması **find_if**.

- **sıralayın**, **lower_bound**ve diğer varsayılan sıralama ve arama algoritmalarından.

Bir karşılaştırıcı yazmak için, katı **<** kullanın ve olanak varsa *adlandırılmış lambdaları* kullanın.

```cpp
auto comp = [](const widget& w1, const widget& w2)
     { return w1.weight() < w2.weight(); }

sort( v.begin(), v.end(), comp );

auto i = lower_bound( v.begin(), v.end(), comp );
```

## <a name="auto-instead-of-explicit-type-names"></a>Açık tür adları yerine Auto

C++ 11, değişken, işlev ve şablon bildirimlerinde kullanılmak üzere [Auto](auto-cpp.md) anahtar sözcüğünü kullanıma sunmuştur. **Auto** , derleyiciye nesne türünü vermesini söyler, böylece açıkça yazmanız gerekmez. yalnızca çıkarılan tür iç içe geçmiş bir şablon olduğunda **Otomatik** olarak faydalıdır:

```cpp
map<int,list<string>>::iterator i = m.begin(); // C-style
auto i = m.begin(); // modern C++
```

## <a name="range-based-for-loops"></a>Aralık tabanlı for döngüleri

Diziler ve kapsayıcılar üzerinde C stili yineleme, hataları dizinlemeye ve ayrıca yazmak için de sıkıcı olur. Bu hataları ortadan kaldırmak ve kodunuzu daha okunabilir hale getirmek için, standart kitaplık kapsayıcıları ve ham diziler ile Aralık tabanlı döngüler kullanın. Daha fazla bilgi için bkz. [Aralık tabanlı for deyimleri](../cpp/range-based-for-statement-cpp.md).

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

## <a name="constexpr-expressions-instead-of-macros"></a>makrolar yerine constexpr ifadeleri

C ve C++ içindeki makrolar, derlemeden önce Önişlemci tarafından işlenen belirteçlerdir. Bir makro belirtecinin her örneği, dosya derlenmesinden önce tanımlı değeri veya ifadesiyle değiştirilmiştir. Makrolar, derleme zamanı sabit değerlerini tanımlamak için genellikle C stili programlamada kullanılır. Ancak, makrolar hata verebilir ve hata ayıklaması zor bir hatadır. Modern C++' de, derleme zamanı sabitleri için [constexpr](constexpr-cpp.md) değişkenlerini tercih etmelisiniz:

```cpp
#define SIZE 10 / C-style
constexpr int size = 10; // modern C++
```

### <a name="uniform-initialization"></a>Tekdüzen başlatma

Modern C++bir tür için küme ayracı başlatma kullanabilirsiniz. Bu başlatma biçimi, diziler, vektörler veya diğer kapsayıcıları başlatırken özellikle kullanışlıdır. Aşağıdaki örnekte `v2` üç `S`örneği ile başlatılır. `v3`, kendilerine küme ayraçları kullanılarak başlatılan üç `S` örneği ile başlatılır. Derleyici, her öğenin türünü, belirtilen `v3`türünü temel alır.

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

Daha fazla bilgi için bkz. [küme ayracı başlatma](initializing-classes-and-structs-without-constructors-cpp.md).

## <a name="move-semantics"></a>Taşıma semantiği

Modern C++ , gereksiz bellek kopyalarının ortadan kaldırılmasına olanak sağlayan *taşıma semantiğini*sağlar. Önceki dilin sürümlerinde, bazı durumlarda kopyalara kaçınılmaz. *Taşıma* işlemi, bir kaynağın sahipliğini bir kopya oluşturmadan bir nesneden bir sonrakine aktarır. Bir kaynağa (yığın belleği, dosya tutamaçları vb.) sahip bir sınıf uygularken, onun için bir *Taşıma oluşturucusu* ve *taşıma atama işleci* tanımlayabilirsiniz. Derleyici, bir kopyanın gerekli olmadığı durumlarda aşırı yükleme çözümlemesi sırasında bu özel üyeleri seçer. Standart Kitaplık kapsayıcı türleri, varsa nesneler üzerinde taşıma oluşturucusunu çağırır. Daha fazla bilgi için bkz. [Taşıma Oluşturucuları ve taşıma atama işleçleriC++()](move-constructors-and-move-assignment-operators-cpp.md).

## <a name="lambda-expressions"></a>Lambda ifadeleri

C stili programlamada, bir işlev bir işlev *işaretçisi*kullanılarak başka bir işleve geçirilebilir. İşlev işaretçilerinin bakımı ve anlaşılması uygun değildir. Başvurduğu işlev, kaynak kodda başka bir yerde, çağrıldığı noktadan uzakta tanımlanmış olabilir. Ayrıca, tür kullanımı uyumlu değildir. Modern C++ , işlev *nesneleri*, bir işlev gibi çağrılmasına olanak sağlayan [()](function-call-operator-parens.md) işlecini geçersiz kılan sınıflar sağlar. İşlev nesneleri oluşturmanın en kolay yolu, satır içi [lambda ifadeleridir](../cpp/lambda-expressions-in-cpp.md). Aşağıdaki örnek, bir işlev nesnesini iletmek için bir lambda ifadesinin nasıl kullanılacağını gösterir, `for_each` işlevi Vektördeki her öğede çağırılır:

```cpp
    std::vector<int> v {1,2,3,4,5};
    int x = 2;
    int y = 4;
    auto result = find_if(begin(v), end(v), [=](int i) { return i > x && i < y; });
```

`[=](int i) { return i > x && i < y; }` lambda ifadesi, `int` türünde tek bir bağımsız değişken alan ve bağımsız değişkenin `y``x` daha büyük olup olmadığını belirten bir Boole değeri olan bir Boolean döndürür. " Çevreleyen bağlamdaki `x` ve `y` değişkenlerin lambda içinde kullanılabileceğini unutmayın. `[=]`, bu değişkenlerin değere göre *yakalandığını* belirtir; diğer bir deyişle, lambda ifadesinin bu değerlerin kendi kopyaları vardır.

## <a name="exceptions"></a>Özel Durumlar

Modern C++ hata koşullarını raporlamak ve işlemek için en iyi yol olarak hata kodları yerine özel durumları vurgular. Daha fazla bilgi için bkz [. C++ özel durumlar ve hata işleme için modern en iyi uygulamalar](errors-and-exception-handling-modern-cpp.md).

## <a name="stdatomic"></a>std:: atomik

C++ Standart kitaplık [std:: atomik](../standard-library/atomic-structure.md) yapı ve iş parçacıkları arası iletişim mekanizmaları için ilgili türleri kullanın.

## <a name="stdvariant-c17"></a>std:: Variant (C++ 17)

Birleşimler, farklı türlerin üyelerinin aynı bellek konumunu kaplamasına olanak tanıyarak belleği korumak için genellikle C stili programlamada kullanılır. Ancak, birleşimler tür açısından güvenli değildir ve programlama hatalarına açıktır. C++ 17, birleşimlerin daha sağlam ve güvenli bir alternatifi olarak [std:: Variant](../standard-library/variant-class.md) sınıfını tanıtır. [Std:: ziyaretişlevi](../standard-library/variant-functions.md#visit) bir `variant` türünün üyelerine tür açısından güvenli bir şekilde erişmek için kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[ C++ Dil başvurusu](../cpp/cpp-language-reference.md)\
[Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md)\
[ C++ Standart kitaplık](../standard-library/cpp-standard-library-reference.md)\
[Microsoft C++ dil uygunluk tablosu](../overview/visual-cpp-language-conformance.md)
