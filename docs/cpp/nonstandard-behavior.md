---
title: Standart Dışı Davranış
ms.date: 05/06/2019
helpviewer_keywords:
- compatibility and compliance, nonstandard behavior
- Microsoft-specific, compiler behavior
- nonstandard behavior, compliance and compatibility
ms.assetid: a57dea27-dc79-4f64-8a83-017e84841773
ms.openlocfilehash: 82c5faae68f9da747017119d76578cc88163d8bb
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222034"
---
# <a name="nonstandard-behavior"></a>Standart Dışı Davranış

Aşağıdaki bölümlerde yerlerden bazıları listelenmiştir burada Microsoft uyarlamasını C++ ile uyumlu değil C++ standart. Aşağıda verilen bölüm numaraları C++ 11 standartındaki (ISO/IEC 14882:2011(E)) bölüm numaralarına başvurur.

C++ standartında farklı derleyici sınırlarının listesi verilir [derleyici sınırları](../cpp/compiler-limits.md).

## <a name="covariant-return-types"></a>Birlikte Değişken Dönüş Türleri

Sanal işlevde bağımsız değişkenlerin bir değişken sayısı olduğunda, sanal taban sınıfları birlikte değişken dönüş türleri olarak desteklenmez. Bu, ISO C++ belirtimi 10.3 bölümü, paragraf 7 ile uyumlu değildir. Aşağıdaki örnek derleme yapmaz, derleyici hatası [C2688](../error-messages/compiler-errors-2/compiler-error-c2688.md)

```cpp
// CovariantReturn.cpp
class A
{
   virtual A* f(int c, ...);   // remove ...
};

class B : virtual A
{
   B* f(int c, ...);   // C2688 remove ...
};
```

## <a name="binding-nondependent-names-in-templates"></a>Şablonlarda Bağımlı Olmayan Adları Bağlama

Microsoft C++ derleyici desteklememektedir şablonlarda bağımlı olmayan adları bağlama başlangıçta şablon ayrıştırılırken. Bu, C++ ISO belirtiminin 14.6.3 bölümü ile uyumlu değildir. Bu, şablonun görülmesinden sonra (ancak şablon örneği oluşturulmadan önce) aşırı yüklerin bildirilmesine neden olabilir.

```cpp
#include <iostream>
using namespace std;

namespace N {
   void f(int) { cout << "f(int)" << endl;}
}

template <class T> void g(T) {
    N::f('a');   // calls f(char), should call f(int)
}

namespace N {
    void f(char) { cout << "f(char)" << endl;}
}

int main() {
    g('c');
}
// Output: f(char)
```

## <a name="function-exception-specifiers"></a>İşlev Özel Durum Belirleyicileri.

Özel durum tanımlayıcıları dışındaki işlev `throw()` ayrıştırılır ancak kullanılmaz. Bu, ISO C++ belirtiminin 15.4 bölümü ile uyumlu değildir. Örneğin:

```cpp
void f() throw(int); // parsed but not used
void g() throw();    // parsed and used
```

Özel durum belirtimleri hakkında daha fazla bilgi için bkz. [özel durum belirtimleri](../cpp/exception-specifications-throw-cpp.md).

## <a name="chartraitseof"></a>char_traits::eof()

C++ Standart durumları [char_traits::eof](../standard-library/char-traits-struct.md#eof) geçerli bir karşılık gelmelidir değil `char_type` değeri. Microsoft C++ derleyici türü için bu kısıtlamayı zorlar **char**, ancak türü **wchar_t**. Bu, C++ ISO belirtiminin 12.1.1 bölümündeki Tablo 62'deki gereksinimlerle uyumlu değildir. Aşağıdaki örnek bunu gösterir.

```cpp
#include <iostream>

int main()
{
    using namespace std;

    char_traits<char>::int_type int2 = char_traits<char>::eof();
    cout << "The eof marker for char_traits<char> is: " << int2 << endl;

    char_traits<wchar_t>::int_type int3 = char_traits<wchar_t>::eof();
    cout << "The eof marker for char_traits<wchar_t> is: " << int3 << endl;
}
```

## <a name="storage-location-of-objects"></a>Nesnelerin Depolama Konumu

C++ standardı (bölüm 1.8 paragraph 6) tam C++ nesnelerinin benzersiz konumlara sahip olmasını gerektirir. Ancak Microsoft ile C++, veri üyeleri olmayan türlerin paylaşacağı bir depolama konumu diğer türlerle nesne ömrü boyunca durumlar vardır.