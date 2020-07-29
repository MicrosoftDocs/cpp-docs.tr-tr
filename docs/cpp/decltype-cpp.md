---
title: decltype  (C++)
ms.date: 11/04/2016
f1_keywords:
- decltype_cpp
helpviewer_keywords:
- operators [C++], decltype
- decltype operator
- operators [C++], type of an expression
- operators [C++], deduce expression type
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
ms.openlocfilehash: abcc18ee29e2dcb09ca15ae77219ae5dd4d74c65
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228940"
---
# <a name="decltype--c"></a>decltype  (C++)

**`decltype`** Tür belirleyicisi belirtilen ifadenin türünü verir. **`decltype`** [ `auto` Anahtar sözcüğü](../cpp/auto-cpp.md)ile birlikte tür Belirleyicisi, öncelikle şablon kitaplıklarını yazan geliştiriciler için yararlıdır. **`auto`** **`decltype`** Dönüş türü, şablon bağımsız değişkenlerinin türlerine bağlı olan bir şablon işlevi bildirmek için ve kullanın. Veya, **`auto`** başka bir **`decltype`** işleve yapılan çağrıyı sarmalayan bir şablon işlevi bildirmek için ve öğesini kullanın ve ardından Sarmalanan işlevin dönüş türünü döndürür.

## <a name="syntax"></a>Sözdizimi

> **`decltype(`***ifade***`)`**

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ifadesini*|Bir ifade. Daha fazla bilgi için bkz. [ifadeler](../cpp/expressions-cpp.md).|

## <a name="return-value"></a>Dönüş Değeri

*İfade* parametresinin türü.

## <a name="remarks"></a>Açıklamalar

**`decltype`** Tür belirleyicisi Visual Studio 2010 veya sonraki sürümlerde desteklenir ve yerel veya yönetilen kodla kullanılabilir. `decltype(auto)`(C++ 14), Visual Studio 2015 ve üzeri sürümlerde desteklenir.

Derleyici, *ifade* parametresinin türünü belirleyebilmek için aşağıdaki kuralları kullanır.

- *İfade* parametresi bir tanımlayıcı veya [sınıf üyesi erişimsiyse](../cpp/member-access-operators-dot-and.md), `decltype(expression)` *ifadesi*tarafından adlandırılan varlığın türüdür. Böyle bir varlık yoksa veya *ifade* parametresi bir dizi aşırı yüklenmiş işlev olarak isimlendiriyor ise, derleyici bir hata iletisi verir.

- *İfade* parametresi bir işleve veya aşırı yüklenmiş bir operatör işlevine yapılan bir çağrıdır, `decltype(expression)` işlevin dönüş türüdür. Aşırı yüklenmiş işlecin etrafındaki parantezler yoksayılır.

- *İfade* parametresi bir [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)ise, `decltype(expression)` *ifadenin*türüdür. *İfade* parametresi bir [lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)ise, `decltype(expression)` *ifadenin*türüne bir [lvalue başvurusudur](../cpp/lvalue-reference-declarator-amp.md) .

Aşağıdaki kod örneği, **`decltype`** tür belirticisinin bazı kullanımlarını gösterir. İlk olarak, aşağıdaki deyimleri kodladığınızı varsayalım.

```cpp
int var;
const int&& fx();
struct A { double x; }
const A* a = new A();
```

Ardından, aşağıdaki tablodaki dört deyim tarafından döndürülen türleri inceleyin **`decltype`** .

|Deyim|Tür|Notlar|
|---------------|----------|-----------|
|`decltype(fx());`|`const int&&`|Bir [rvalue başvurusu](../cpp/rvalue-reference-declarator-amp-amp.md) **`const int`** .|
|`decltype(var);`|**`int`**|`var` değişkeninin türü.|
|`decltype(a->x);`|**`double`**|Üye erişiminin türü.|
|`decltype((a->x));`|`const double&`|İç parantezler, deyimin bir üye erişimi yerine bir ifade değerlendirilmesine neden olur. Çünkü `a` bir işaretçi olarak bildirildiği **`const`** için, türü öğesine bir başvurudur **`const double`** .|

## <a name="decltype-and-auto"></a>Decltype ve Otomatik

C++ 14 ' te, `decltype(auto)` dönüş türü şablon bağımsız değişkenlerinin türlerine bağlı olan bir şablon işlevi bildirmek için bitiş dönüş türü olmadan kullanabilirsiniz.

C++ 11 ' de, **`decltype`** **`auto`** dönüş türü kendi şablon bağımsız değişkenlerinin türlerine bağlı olan bir şablon işlevi bildirmek için, bir bitiş dönüş türü üzerinde tür belirleyicisi ile birlikte anahtar sözcüğünü kullanabilirsiniz. Örneğin, aşağıdaki kod örneğini dikkate alın, burada şablon işlevin dönüş türü şablon bağımsız değişkenlerinin türlerine bağlıdır. Kod örneğinde, *Bilinmeyen* yer tutucu, dönüş türünün belirtimediğini belirtir.

```cpp
template<typename T, typename U>
UNKNOWN func(T&& t, U&& u){ return t + u; };
```

**`decltype`** Tür belirticisinin giriş geliştiricisi, bir geliştiricinin şablon işlevinin döndürdüğü ifadenin türünü almasını sağlar. *alternative function declaration syntax* **`auto`** **`decltype`** *Geç belirtilen* bir dönüş türü bildirmek için daha sonra, anahtar sözcüğü ve tür belirticisinden daha sonra gösterilen alternatif işlev bildirimi sözdizimini kullanın. Sonradan belirtilmiş dönüş türü, bildirim kodlandığında değil, derlendiğinde belirlenir.

Aşağıdaki prototip, alternatif bir işlev bildiriminin sözdizimini göstermektedir. **`const`** Ve **`volatile`** niteleyicileri ve **`throw`** [özel durum belirtiminin](../cpp/exception-specifications-throw-cpp.md) isteğe bağlı olduğunu unutmayın. *Function_body* yer tutucusu, işlevin ne yaptığını belirten bileşik bir ifadeyi temsil eder. En iyi kodlama uygulaması olarak, deyimindeki *ifade* yer tutucusu, **`decltype`** varsa, deyimi tarafından belirtilen ifadeyle eşleşmelidir ( **`return`** varsa, *function_body*.

**`auto`***function_name* **`(`** *Parametreler*<sub>opt</sub> kabul etme **`)`** **`const`** <sub>opt</sub> **`volatile`** <sub>opt</sub> **`->`** **`decltype(`** *ifadesi* **`)`** **`noexcept`** <sub>opt</sub> **`{`** *function_body***`};`**

Aşağıdaki kod örneğinde, `myFunc` şablon işlevinin sonradan belirtilen dönüş türü, `t` ve `u` şablon bağımsız değişkenlerinin türleri tarafından belirlenir. En iyi kodlama uygulaması olarak, kod örneği aynı zamanda tam olarak iletmeyi destekleyen Rvalue başvurularını ve `forward` işlev şablonunu kullanır *perfect forwarding*. Daha fazla bilgi için bkz. [rvalue başvuru bildirimci:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

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

## <a name="decltype-and-forwarding-functions-c11"></a>Decltype ve Iletme Işlevleri (C++ 11)

İletme işlevleri, diğer işlevlere yapılan çağrıları sarar. Bağımsız değişkenlerini veya o bağımsız değişkenlerle ilişkili bir ifadenin sonuçlarını başka bir işleve ileten bir işlev şablonu düşünün. Ayrıca, ileten işlev diğer işlevin çağrılması sonucunu döndürür. Bu senaryoda, ileten işlevin dönüş türü sarılan işlevin dönüş türü ile aynı olması gerekir.

Bu senaryoda, tür belirleyicisi olmadan uygun bir tür ifadesi yazılamaz **`decltype`** . **`decltype`** Tür Belirleyicisi, bir işlevin bir başvuru türü döndürüp döndürmediği hakkında gerekli bilgileri kaybetmediğinden, genel iletme işlevlerine izin verir. Bir iletme işlevine ait kod örneği için, önceki `myFunc` şablon işlevi örneğine bakın.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, `Plus()` şablon işlevinin sonradan belirtilen dönüş türünü bildirir. `Plus`İşlevi iki işlenenini aşırı yükleme ile işler **`operator+`** . Sonuç olarak, artı işlecinin ( **`+`** ) ve işlevin dönüş türünün yorumu, `Plus` işlev bağımsız değişkenlerinin türlerine bağlıdır.

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

**Visual Studio 2017 ve üzeri:** Derleyici, **`decltype`** şablon örneği oluşturulması yerine bildirildiği zaman bağımsız değişkenleri ayrıştırır. Sonuç olarak, bağımsız değişkende bağımlı olmayan bir özelleştirme bulunursa **`decltype`** , örnek oluşturma süresine ertelenir ve anında işlenir ve sonuçta ortaya çıkan hatalar bu sırada tanılanabilir.

Aşağıdaki örnekte, bildirim noktasında oluşan bir derleyici hatası gösterilmektedir:

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

Visual Studio 2010 veya sonraki sürümleri.

`decltype(auto)`Visual Studio 2015 veya üstünü gerektirir.
