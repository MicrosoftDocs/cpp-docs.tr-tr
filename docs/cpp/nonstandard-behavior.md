---
title: Standart dışı davranış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- compatibility and compliance, nonstandard behavior
- Microsoft-specific, compiler behavior
- nonstandard behavior, compliance and compatibility
ms.assetid: a57dea27-dc79-4f64-8a83-017e84841773
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b7334fdc420c096c42360dd6b75fc400b8b34f3
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941804"
---
# <a name="nonstandard-behavior"></a>Standart Dışı Davranış
Aşağıdaki bölümlerde, C++'nın Visual C++ uygulamasının C++ standartıyla uyumlu olmadığı yerlerin bazıları listelenmiştir. Aşağıda verilen bölüm numaraları C++ 11 standartındaki (ISO/IEC 14882:2011(E)) bölüm numaralarına başvurur.  
  
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
 İlk olarak bir şablon ayrıştırıldığında, Visual C++ derleyici bağımlı olmayan adların bağlanmasını şu anda desteklemez. Bu, C++ ISO belirtiminin 14.6.3 bölümü ile uyumlu değildir. Bu, şablonun görülmesinden sonra (ancak şablon örneği oluşturulmadan önce) aşırı yüklerin bildirilmesine neden olabilir.  
  
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
 C++ standartı [char_traits::eof](../standard-library/char-traits-struct.md#eof) geçerli bir karşılık gelmelidir değil `char_type` değeri. Visual C++ derleyicisi türü için bu kısıtlamayı zorlar **char**, ancak türü `wchar_t`. Bu, C++ ISO belirtiminin 12.1.1 bölümündeki Tablo 62'deki gereksinimlerle uyumlu değildir. Aşağıdaki örnek bunu gösterir.  
  
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
 C++ standardı (bölüm 1.8 paragraph 6) tam C++ nesnelerinin benzersiz konumlara sahip olmasını gerektirir. Ancak Visual C++ ile, veri üyeleri olmayan türlerin bir depolama konumunu nesnenin yaşam süresince diğer türlerle paylaşacağı durumlar vardır.