---
title: Değer türleri olarak C++ sınıfları
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
ms.openlocfilehash: 1aabcad46e848e1a499a142adaba5002a829bbf5
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246015"
---
# <a name="c-classes-as-value-types"></a>Değer türleri olarak C++ sınıfları

C++sınıflar varsayılan değer türlerdir. Bunlar, nesne odaklı programlamayı desteklemek için polimorfik davranışı etkinleştiren başvuru türleri olarak belirtilebilir. Değer türleri bazen bellek ve düzen denetimi açısından görüntülenir, ancak başvuru türleri temel sınıflar ve sanal işlevler ile polimorfik amaçlar için kullanılır. Varsayılan olarak, değer türleri kopyalanabilir ' dir. Bu, her zaman bir kopya Oluşturucu ve bir kopya atama işleci olduğu anlamına gelir. Başvuru türleri için, sınıfı kopyalanabilir olmayan (kopya oluşturucuyu ve kopyalama atamasını devre dışı bırakın) ve kendi amaçlanan çok biçimliliği destekleyen bir sanal yıkıcı kullanın. Değer türleri aynı zamanda, kopyalandığı zaman, her zaman ayrı olarak değiştirilebilen iki bağımsız değer sağlar. Başvuru türleri kimlik ve ne tür bir nesne? Bu nedenle, "başvuru türleri" de "polimorfik türler" olarak adlandırılır.

Gerçekten başvuru benzeri bir tür istiyorsanız (temel sınıf, sanal işlevler), aşağıdaki koddaki `MyRefType` sınıfında gösterildiği gibi kopyalamayı açıkça devre dışı bırakmanız gerekir.

```cpp
// cl /EHsc /nologo /W4

class MyRefType {
private:
    MyRefType & operator=(const MyRefType &);
    MyRefType(const MyRefType &);
public:
    MyRefType () {}
};

int main()
{
    MyRefType Data1, Data2;
    // ...
    Data1 = Data2;
}
```

Yukarıdaki kodun derlenmesi Şu hataya neden olur:

```Output
test.cpp(15) : error C2248: 'MyRefType::operator =' : cannot access private member declared in class 'MyRefType'
        meow.cpp(5) : see declaration of 'MyRefType::operator ='
        meow.cpp(3) : see declaration of 'MyRefType'
```

## <a name="value-types-and-move-efficiency"></a>Değer türleri ve taşıma verimliliği

Yeni kopya iyileştirmeleri nedeniyle kopya ayırma ek yükünün önlerine izin verilmez. Örneğin, dizelerin bir vektörünün ortasına bir dize eklediğinizde, yeniden ayırma ek yükü yoktur, yalnızca bir taşı, vektör 'nin büyümesine neden olur. Bu aynı zamanda diğer işlemler için de geçerlidir. Örneğin, iki çok büyük nesne üzerinde ekleme işlemi gerçekleştiriliyor. Bu değer işlemi iyileştirmeleri nasıl etkinleştirilir? Bazı C++ derleyicilerde, derleyici bu ayarı sizin için örtülü olarak etkinleştirir, benzer kopya oluşturucuları derleyici tarafından otomatik olarak oluşturulabilir. Bununla birlikte, C++' de sınıfınızın, sınıf tanımınızda bildirerek atama ve oluşturucuları taşıması için "kabul etme" gerekir. Bu, uygun üye işlev bildirimlerinde Double ve (& &) rvalue başvurusu kullanılarak ve taşıma oluşturucusunu ve taşıma atama yöntemlerini tanımlayarak gerçekleştirilir.  Ayrıca, kaynak nesneden "gut" ları çalmak için doğru kodu de eklemeniz gerekir.

Taşıma özelliğinin etkinleştirilmesi gerektiğine nasıl karar verirsiniz? Kopyalama oluşturma özelliğinin etkin olması gerektiğini zaten biliyorsanız, büyük olasılıkla derin bir kopyadan çıkartacıya olması durumunda taşıma özelliğinin etkin olmasını isteyebilirsiniz. Ancak, taşıma desteğinin gerekli olduğunu biliyorsanız, kopyalamanın etkin olmasını istediğiniz anlamına gelmez. Bu ikinci durum, "salt taşıma türü" olarak adlandırılır. Standart kitaplıkta zaten bir örnek `unique_ptr`. Yan bir notta, eski `auto_ptr` kullanım dışı bırakılmıştır ve önceki sürümünde taşıma semantiğinin olmaması nedeniyle `unique_ptr` tam olarak değiştirilmiştir C++.

Taşıma semantiğini kullanarak değer veya ortadaki ekleme yapabilirsiniz. Taşıma, kopyalamanın bir iyileştirmesi. Geçici bir çözüm olarak yığın ayırma gereksinimi vardır. Aşağıdaki sözde kodu göz önünde bulundurun:

```cpp
#include <set>
#include <vector>
#include <string>
using namespace std;

//...
set<widget> LoadHugeData() {
    set<widget> ret;
    // ... load data from disk and populate ret
    return ret;
}
//...
widgets = LoadHugeData();   // efficient, no deep copy

vector<string> v = IfIHadAMillionStrings();
v.insert( begin(v)+v.size()/2, "scott" );   // efficient, no deep copy-shuffle
v.insert( begin(v)+v.size()/2, "Andrei" );  // (just 1M ptr/len assignments)
//...
HugeMatrix operator+(const HugeMatrix& , const HugeMatrix& );
HugeMatrix operator+(const HugeMatrix& ,       HugeMatrix&&);
HugeMatrix operator+(      HugeMatrix&&, const HugeMatrix& );
HugeMatrix operator+(      HugeMatrix&&,       HugeMatrix&&);
//...
hm5 = hm1+hm2+hm3+hm4+hm5;   // efficient, no extra copies
```

### <a name="enabling-move-for-appropriate-value-types"></a>Uygun değer türleri için taşımayı etkinleştirme

Taşımanın derin bir kopyadan benzebileceği bir değer benzeri bir sınıf için, geçiş oluşturmayı etkinleştirin ve atamayı verimlilik açısından taşıyın. Aşağıdaki sözde kodu göz önünde bulundurun:

```cpp
#include <memory>
#include <stdexcept>
using namespace std;
// ...
class my_class {
    unique_ptr<BigHugeData> data;
public:
    my_class( my_class&& other )   // move construction
        : data( move( other.data ) ) { }
    my_class& operator=( my_class&& other )   // move assignment
    { data = move( other.data ); return *this; }
    // ...
    void method() {   // check (if appropriate)
        if( !data )
            throw std::runtime_error("RUNTIME ERROR: Insufficient resources!");
    }
};
```

Kopyalama oluşturma/atamayı etkinleştirirseniz, derin bir kopyadan çıkartacıcıda olması halinde oluşturma/atamayı de etkinleştirin.

*Değer olmayan* bazı türler salt taşınır, örneğin, bir kaynağı kopyalayamıyorum, yalnızca sahipliği aktarabilir. Örnek: `unique_ptr`.

## <a name="see-also"></a>Ayrıca bkz.

[C++tür sistemi](../cpp/cpp-type-system-modern-cpp.md)<br/>
[Uygulamasına geri hoş geldinizC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
