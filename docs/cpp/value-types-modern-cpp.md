---
title: Değer Türleri (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
ms.openlocfilehash: 3589541f5b6fca736329e1d6fcb8929418fca132
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628962"
---
# <a name="value-types-modern-c"></a>Değer Türleri (Modern C++)

C++, varsayılan değer türleri tarafından sınıflardır. Bu konu, değer türleri ve kullanımlarıyla sorunları tanıtıcı genel bakış sağlar.

## <a name="value-vs-reference-types"></a>Değer başvuru türleri

Daha önce belirtildiği gibi C++ sınıflarının varsayılan değer türleri olan. Nesne yönelimli programlama desteklemek çok biçimli davranışları etkinleştirmek başvuru türleri olarak belirtilebilir. Başvuru türleri temel sınıflar ve sanal işlevler hakkında çok biçimli amacıyla oysa değer türleri, bellek ve düzen denetimi perspektifinden bazen görüntülenir. Varsayılan olarak, her zaman bir kopya oluşturucu ve kopya atama işlecine anlamına gelir, değer türleri kopyalanabilir,. Başvuru türleri için sınıfı kopyalanamaz yapın (kopya oluşturucu ve kopya atama işleci devre dışı bırakın) ve bunların hedeflenen çok biçimlilik destekleyen sanal bir yıkıcı kullanın. Değer türleri kopyalanırlar olduğunda, her zaman ayrı ayrı değiştirilebilir iki bağımsız değer erişmenizi sağlayan içeriği hakkında da var. Başvuru türleri, hangi nesne çeşidi olduğu kimlik hakkında - misiniz? Bu nedenle, "türleri başvurusu" "çok biçimli türler olarak" de denir.

Bir başvuru benzeri türü (sanal işlevler, temel sınıf) istediğinizden açıkça kopyalama, devre dışı bırakmak gösterildiği gerekirse `MyRefType` aşağıdaki kodda sınıfı.

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

Yukarıdaki kod derleme şu hatayla sonuçlanır:

```Output
test.cpp(15) : error C2248: 'MyRefType::operator =' : cannot access private member declared in class 'MyRefType'
        meow.cpp(5) : see declaration of 'MyRefType::operator ='
        meow.cpp(3) : see declaration of 'MyRefType'
```

## <a name="value-types-and-move-efficiency"></a>Değer türleri ve verimliliği Taşı

Yeni kopya iyileştirmeleri nedeniyle kopyalama ayırma yükü önlenmiş olur. Örneğin, dizelerden oluşan bir vektörü ortasında bir dize eklediğinizde, olacaktır kopyalama yeniden ayırma zahmetine, yalnızca bir move - bile vektör bir Büyüt sonuçlanır. Bu örneği için bir ekleme işlemi iki çok büyük nesneler üzerinde gerçekleştirmek, diğer işlemler için de geçerlidir. Bu değer işlemi iyileştirmeleri nasıl etkinleştirebilirim? Çok kopya oluşturucuları otomatik olarak derleyici tarafından oluşturulabilir gibi bazı C++ Derleyicileri, derleyici bu sizin için örtük olarak etkinleştirir. Ancak, Visual C++'da, kendi sınıfınızı "atama ve Oluşturucular, sınıf tanımında bildirerek taşımak için katılım" gerekir. Bu çift ve işareti kullanılarak elde edilir (& &) uygun üyesini rvalue başvurusu işlev bildirimleri ve tanımlayan bir taşıma oluşturucusuna ve taşıma ataması yöntemlerinde.  Ayrıca "dışında kaynak nesnesi guts çalmak için" doğru kod eklemeniz gerekir.

Etkin taşıma varsa nasıl karar verebilirim? Zaten etkin yapı kopyalamanız biliyorsanız, muhtemelen derin kopya ucuz olabilir, etkin taşımak istersiniz. Destek taşıma olduğunu biliyorsanız, ancak bunu mutlaka etkin kopyalama istediğiniz anlamına gelmez. Bu ikinci durumda, bir "yalnızca taşıma türü" adlı. Standart Kitaplığı'nda zaten bir örnek `unique_ptr`. Yan Not, eski olarak `auto_ptr` kullanım dışıdır ve tarafından değiştirildi `unique_ptr` tam C++'ın önceki sürümünü taşıma semantiği desteği eksikliği nedeniyle.

Taşıma semantiği kullanarak Ekle-Orta ya da dönüş değeri gerçekleştirebilirsiniz. Taşıma bir kopyalama iyileştirmesi ' dir. Yığın ayırma geçici bir çözüm olarak gerek yoktur. Aşağıdaki sözde kod göz önünde bulundurun:

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

### <a name="enabling-move-for-appropriate-value-types"></a>Taşıma için uygun değer türleri etkinleştirme

Burada, taşıma derin kopya ucuz olabilir bir değer benzeri sınıf için taşıma oluşturma etkinleştirin ve verimlilik için atama taşıma. Aşağıdaki sözde kod göz önünde bulundurun:

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

Kopya oluşturma/atama etkinleştirirseniz, derin kopya ucuz olabilir, ayrıca taşıma yapımı/atama etkinleştirin.

Bazı *değer olmayan* türleri yalnızca Aktarım sahipliği bir kaynak olduğunda kopyalanamıyor gibi yalnızca taşınabilir,. Örnek: `unique_ptr`.

## <a name="section"></a>Bölüm

İçerik

## <a name="see-also"></a>Ayrıca bkz.

[C++ tür sistemi](../cpp/cpp-type-system-modern-cpp.md)<br/>
[C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)