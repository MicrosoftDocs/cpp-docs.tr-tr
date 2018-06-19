---
title: decltype (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- decltype_cpp
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], decltype
- decltype operator
- operators [C++], type of an expression
- operators [C++], deduce expression type
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac9fe7ebf3d3e406854308e56d38e37567acc07a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418045"
---
# <a name="decltype--c"></a>decltype (C++)
`decltype` tür belirticisi belirtilen ifade türünü ortaya çıkarır. `decltype` İle birlikte tür tanımlayıcısı, [anahtar sözcüğü otomatik](../cpp/auto-cpp.md), öncelikle Şablon Kütüphanesi yazma geliştiriciler için yararlıdır. Kullanım `auto` ve `decltype` şablon işlevi, return bildirmek için şablon değişkenlerinin türlerinde türüne bağlıdır. Veya başka bir işleve yapılan bir çağrıyı saran ve ardından sarılı işlevin dönüş türünü döndüren bir şablon işlevi bildirmek için `auto` ve `decltype` kullanın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
decltype( expression )  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`expression`|Bir ifade. Daha fazla bilgi için bkz: [ifadeleri](../cpp/expressions-cpp.md).|  
  
## <a name="return-value"></a>Dönüş Değeri  
 `expression` parametresinin türü.  
  
## <a name="remarks"></a>Açıklamalar  
 `decltype` türü belirticisi, Visual C++ 2010 veya sonraki sürümlerinde desteklenir ve yerel veya yönetilen kod ile kullanılabilir. `decltype(auto)` (c ++ 14) Visual Studio 2015 ve sonraki sürümlerinde desteklenir.  
  
 Derleyici, `expression` parametresinin türünü belirlemek için aşağıdaki kuralları kullanır.  
  
-   Varsa `expression` parametredir tanımlayıcı veya [sınıf üye erişimi](../cpp/member-access-operators-dot-and.md), `decltype(expression)` tarafından adlı varlık türüdür `expression`. Bu tür bir varlık yoksa veya `expression` parametresi aşırı yüklenmiş bir işlev kümesini adlandırırsa, derleyici bir hata iletisi verir.  
  
-   Varsa `expression` parametredir bir işlev veya aşırı yüklenmiş işleci işlevi çağrısı `decltype(expression)` işlevinin dönüş türü. Aşırı yüklenmiş işlecin etrafındaki parantezler yoksayılır.  
  
-   Varsa `expression` parametresi bir [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` türü `expression`. Varsa `expression` parametresi bir [lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` olan bir [lvalue başvuru](../cpp/lvalue-reference-declarator-amp.md) türüne `expression`.  
  
 Aşağıdaki kod örneği, `decltype` tür belirticisinin bazı kullanımlarını gösterir. İlk olarak, aşağıdaki deyimleri kodladığınızı varsayalım.  
  
```cpp  
int var;  
const int&& fx();   
struct A { double x; }  
const A* a = new A();  
```  
  
 Daha sonra, aşağıdaki tabloda dört `decltype` deyimi tarafından döndürülen türleri inceleyin.  
  
|Deyim|Tür|Notlar|  
|---------------|----------|-----------|  
|`decltype(fx());`|`const int&&`|Bir [rvalue başvuru](../cpp/rvalue-reference-declarator-amp-amp.md) için bir `const int`.|  
|`decltype(var);`|`int`|`var` değişkeninin türü.|  
|`decltype(a->x);`|`double`|Üye erişiminin türü.|  
|`decltype((a->x));`|`const double&`|İç parantezler, deyimin bir üye erişimi yerine bir ifade değerlendirilmesine neden olur. Ve `a` bir `const` işaretçisi olarak bildirildiğinden tür bir `const double` başvurusudur.|  
  
## <a name="decltype-and-auto"></a>Decltype ve Otomatik  
 C ++ 14'te, kullandığınız `decltype(auto)` şablon işlevi, dönüş türü bildirmek için hiçbir sonunda dönüş türüyle kendi şablon bağımsız değişken türlerine bağlıdır.  
  
 C ++ 11'de, kullandığınız `decltype` ile birlikte tür tanımlayıcısı sonunda bir dönüş türü üzerinde `auto` şablon işlevi, dönüş türü bildirmek için anahtar sözcüğü, şablon değişkenlerinin türlerinde bağlıdır. Örneğin, aşağıdaki kod örneğini dikkate alın, burada şablon işlevin dönüş türü şablon bağımsız değişkenlerinin türlerine bağlıdır. Kod örneğinde, *bilinmeyen* yer tutucu gösterir dönüş türü belirtilemez.  
  
```cpp  
template<typename T, typename U>  
UNKNOWN func(T&& t, U&& u){ return t + u; };   
```  
  
 `decltype` tür belirticisiyle birlikte, artık geliştiriciler şablon işlevinin döndürdüğü ifadenin türünü elde edebilirler. Kullanım *alternatif işlev bildirim sözdizimi* , daha sonra gösterilen `auto` anahtar sözcüğü ve `decltype` tür tanımlayıcısı bildirmek için bir *belirtilen geç* dönüş türü. Sonradan belirtilmiş dönüş türü, bildirim kodlandığında değil, derlendiğinde belirlenir.  
  
 Aşağıdaki prototip, alternatif bir işlev bildiriminin sözdizimini göstermektedir. Unutmayın `const` ve `volatile` niteleyicileri ve `throw` [özel durum belirtimi](../cpp/exception-specifications-throw-cpp.md) isteğe bağlıdır. *Function_body* yer tutucu işlevi yaptığı belirten bir bileşik deyim temsil eder. En iyi yöntem, kodlama olarak *ifade* yer tutucu `decltype` deyimi tarafından belirtilen değerle eşleşmelidir `return` deyimi, varsa, *function_body*.  
  
 **Otomatik** *işlev_adı* **(** *parametreleri*<sub>kabul</sub> **)**  **const**<sub>kabul</sub> **volatile**<sub>kabul</sub> **->** **decltype (** *ifade* **)** **throw**<sub>kabul</sub> **{** *function_body* **};**  
  
 Aşağıdaki kod örneğinde, `myFunc` şablon işlevinin sonradan belirtilen dönüş türü, `t` ve `u` şablon bağımsız değişkenlerinin türleri tarafından belirlenir. Alıştırma kodlama en iyi, kod örneği de rvalue başvuru kullanır ve `forward` destek işlevi şablonu *kusursuz iletme*. Daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
```cpp  
//C++11  
 template<typename T, typename U>  
auto myFunc(T&& t, U&& u) -> decltype (forward<T>(t) + forward<U>(u))   
        { return forward<T>(t) + forward<U>(u); };  
  
//C++14  
template<typename T, typename U>  
decltype(auto) myFunc(T&& t, U&& u)   
        { return forward<T>(t) + forward<U>(u); };  
  
```  
  
## <a name="decltype-and-forwarding-functions-c11"></a>Decltype ve yönlendirme işlevleri (C ++ 11)  
 İletme işlevleri, diğer işlevlere yapılan çağrıları sarar. Bağımsız değişkenlerini veya o bağımsız değişkenlerle ilişkili bir ifadenin sonuçlarını başka bir işleve ileten bir işlev şablonu düşünün. Ayrıca, ileten işlev diğer işlevin çağrılması sonucunu döndürür. Bu senaryoda, ileten işlevin dönüş türü sarılan işlevin dönüş türü ile aynı olması gerekir.  
  
 Bu senaryoda, `decltype` tür belirticisi olmadan uygun bir tür ifadesi yazamazsınız. `decltype` tür belirticisi, genel iletme işlevlerinin kullanılmasına olanak verir çünkü bir işlevin bir başvuru döndürüp döndürmeyeceğiyle ilgili gerekli bilgileri kaybetmez. Bir iletme işlevine ait kod örneği için, önceki `myFunc` şablon işlevi örneğine bakın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, `Plus()` şablon işlevinin sonradan belirtilen dönüş türünü bildirir. `Plus` işlevi, iki işlenenini `operator+` aşırı yüküyle işler. Sonuç olarak, artı işlecinin (+) yorumlanması ve `Plus` işlevinin dönüş türü işlev bağımsız değişkenlerinin türlerine bağlıdır.  
  
```cpp  
// decltype_1.cpp  
// compile with: cl /EHsc decltype_1.cpp  
  
#include <iostream>  
#include <string>  
#include <utility>  
#include <iomanip>  
  
using namespace std;  
  
template<typename T1, typename T2>  
auto Plus(T1&& t1, T2&& t2) ->   
   decltype(forward<T1>(t1) + forward<T2>(t2))  
{  
   return forward<T1>(t1) + forward<T2>(t2);  
}  
  
class X  
{  
   friend X operator+(const X& x1, const X& x2)  
   {  
      return X(x1.m_data + x2.m_data);  
   }  
  
public:  
   X(int data) : m_data(data) {}  
   int Dump() const { return m_data;}  
private:  
   int m_data;  
};  
  
int main()  
{  
   // Integer   
   int i = 4;  
   cout <<   
      "Plus(i, 9) = " <<   
      Plus(i, 9) << endl;  
  
   // Floating point  
   float dx = 4.0;  
   float dy = 9.5;  
   cout <<     
      setprecision(3) <<   
      "Plus(dx, dy) = " <<  
      Plus(dx, dy) << endl;  
  
   // String        
   string hello = "Hello, ";  
   string world = "world!";  
   cout << Plus(hello, world) << endl;  
  
   // Custom type  
   X x1(20);  
   X x2(22);  
   X x3 = Plus(x1, x2);  
   cout <<   
      "x3.Dump() = " <<   
      x3.Dump() << endl;  
}  
```  
  
```Output  
Plus(i, 9) = 13
Plus(dx, dy) = 13.5
Hello, world!
x3.Dump() = 42
```
  
## <a name="example"></a>Örnek
**Visual Studio 2017 ve üzeri:** şablonları bildirilen örneği yerine olduğunda derleyici decltype bağımsız değişkenlerini ayrıştırır. Sonuç olarak, bağlı olmayan uzmanlık decltype değişkeninde bulunursa, örnek oluşturma zamanında ertelenmiş değil ve hemen işlenir ve sonuçta ortaya çıkan hataları o anda koydu.

Aşağıdaki örnek, bildirim noktasında tetiklenir böyle bir derleyici hatası gösterir:

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT> class IsCallable
{
public:
   struct BadType {};
   template <class U>
   static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>
   template <class U>
   static BadType Test(...);
   static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

## <a name="requirements"></a>Gereksinimler  
 Visual C++ 2010 veya sonraki sürümleri.  
  
 `decltype(auto)` Visual Studio 2015 veya üstünü gerektirir.  
  
