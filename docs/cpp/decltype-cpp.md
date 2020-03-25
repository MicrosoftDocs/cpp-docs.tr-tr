---
title: decltype (C++)
ms.date: 11/04/2016
f1_keywords:
- decltype_cpp
helpviewer_keywords:
- operators [C++], decltype
- decltype operator
- operators [C++], type of an expression
- operators [C++], deduce expression type
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
ms.openlocfilehash: 1ed07b8987df7b621ea2809409069cc1121fa24f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180218"
---
# <a name="decltype--c"></a>decltype (C++)

**Decltype** tür Belirleyicisi, belirtilen bir ifadenin türünü verir. [Auto anahtar sözcüğü](../cpp/auto-cpp.md)ile birlikte, **decltype** tür Belirleyicisi, öncelikle şablon kitaplıklarını yazan geliştiriciler için yararlıdır. Dönüş türü, şablon bağımsız değişkenlerinin türlerine bağlı olan bir şablon işlevi bildirmek için **Auto** ve **decltype** kullanın. Ya da **Otomatik** ve **decltype** kullanarak başka bir işleve yapılan çağrıyı sarmalayan bir şablon işlevi bildirir ve ardından Sarmalanan işlevin dönüş türünü döndürür.

## <a name="syntax"></a>Sözdizimi

```
decltype( expression )
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ifadesini*|Bir ifade. Daha fazla bilgi için bkz. [ifadeler](../cpp/expressions-cpp.md).|

## <a name="return-value"></a>Dönüş Değeri

*İfade* parametresinin türü.

## <a name="remarks"></a>Açıklamalar

**Decltype** tür Belirleyicisi, Visual Studio 2010 veya sonraki sürümlerinde desteklenir ve yerel veya yönetilen kodla kullanılabilir. `decltype(auto)` (C++ 14), Visual Studio 2015 ve üzeri sürümlerde desteklenir.

Derleyici, *ifade* parametresinin türünü belirleyebilmek için aşağıdaki kuralları kullanır.

- *İfade* parametresi bir tanımlayıcı veya [sınıf üyesi erişimsiyse](../cpp/member-access-operators-dot-and.md), `decltype(expression)` *ifadesi*tarafından adlandırılan varlığın türüdür. Böyle bir varlık yoksa veya *ifade* parametresi bir dizi aşırı yüklenmiş işlev olarak isimlendiriyor ise, derleyici bir hata iletisi verir.

- *İfade* parametresi bir işleve veya aşırı yüklenmiş bir operatör işlevine yapılan bir çağrıdır, `decltype(expression)` işlevin dönüş türüdür. Aşırı yüklenmiş işlecin etrafındaki parantezler yoksayılır.

- *İfade* parametresi bir [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)ise, `decltype(expression)` *ifadenin*türüdür. *İfade* parametresi bir [lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)ise, `decltype(expression)` *ifade*türüne bir [lvalue başvurusudur](../cpp/lvalue-reference-declarator-amp.md) .

Aşağıdaki kod örneği, **decltype** tür belirticisinin bazı kullanımlarını gösterir. İlk olarak, aşağıdaki deyimleri kodladığınızı varsayalım.

```cpp
int var;
const int&& fx();
struct A { double x; }
const A* a = new A();
```

Ardından, aşağıdaki tabloda yer alan dört **decltype** deyimi tarafından döndürülen türleri inceleyin.

|Deyim|Tür|Notlar|
|---------------|----------|-----------|
|`decltype(fx());`|`const int&&`|Bir **const int**'e bir [rvalue başvurusu](../cpp/rvalue-reference-declarator-amp-amp.md) .|
|`decltype(var);`|**int**|`var` değişkeninin türü.|
|`decltype(a->x);`|**double**|Üye erişiminin türü.|
|`decltype((a->x));`|`const double&`|İç parantezler, deyimin bir üye erişimi yerine bir ifade değerlendirilmesine neden olur. `a` bir `const` işaretçisi olarak bildirildiği için, tür **const Double**' a bir başvurudur.|

## <a name="decltype-and-auto"></a>Decltype ve Otomatik

C++ 14 ' te, dönüş türü şablon bağımsız değişkenlerinin türlerine bağlı olan bir şablon işlevi bildirmek için, sondaki dönüş türü olmayan `decltype(auto)` kullanabilirsiniz.

C++ 11 ' de, dönüş türü kendi şablon bağımsız değişkenlerinin türlerine bağlı olan bir şablon işlevi bildirmek için, bir sondaki dönüş türü üzerinde, **Otomatik** anahtar sözcüğüyle birlikte **decltype** tür belirleyicisi ' ni kullanabilirsiniz. Örneğin, aşağıdaki kod örneğini dikkate alın, burada şablon işlevin dönüş türü şablon bağımsız değişkenlerinin türlerine bağlıdır. Kod örneğinde, *Bilinmeyen* yer tutucu, dönüş türünün belirtimediğini belirtir.

```cpp
template<typename T, typename U>
UNKNOWN func(T&& t, U&& u){ return t + u; };
```

**Decltype** türü belirticisinin tanıtımı, bir geliştiricinin şablon işlevinin döndürdüğü ifadenin türünü almasını sağlar. *Geç belirtilen* bir dönüş türü bildirmek için, daha sonra, **Auto** anahtar sözcüğü ve **decltype** tür belirticisinden gösterilen *Alternatif işlev bildirimi sözdizimini* kullanın. Sonradan belirtilmiş dönüş türü, bildirim kodlandığında değil, derlendiğinde belirlenir.

Aşağıdaki prototip, alternatif bir işlev bildiriminin sözdizimini göstermektedir. **Const** ve **volatile** niteleyicilerinin ve **throw** [özel durum belirtiminin](../cpp/exception-specifications-throw-cpp.md) isteğe bağlı olduğunu unutmayın. *Function_body* yer tutucusu, işlevin ne yaptığını belirten bileşik bir ifadeyi temsil eder. En iyi kodlama uygulaması olarak, **decltype** deyimindeki *ifade* yer tutucusu, *function_body*varsa, **Return** deyimi tarafından belirtilen ifadeyle eşleşmelidir.

**Auto** *function_name* **(** *Parameters*<sub>opt</sub> **)** **const**<sub>opt</sub> **geçici**<sub>opt</sub> **->** **decltype (** *Expression* **)** **throw**<sub>opt</sub> **{** *function_body* **};**

Aşağıdaki kod örneğinde, `myFunc` şablon işlevinin sonradan belirtilen dönüş türü, `t` ve `u` şablon bağımsız değişkenlerinin türleri tarafından belirlenir. En iyi kodlama uygulaması olarak, kod örneği Ayrıca, *tam olarak iletmeyi*destekleyen Rvalue başvurularını ve `forward` işlev şablonunu kullanır. Daha fazla bilgi için bkz. [rvalue başvuru bildirimci: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

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

Bu senaryoda, **decltype** tür belirleyicisi olmadan uygun bir tür ifadesi yazılamaz. **Decltype** tür Belirleyicisi, bir işlevin bir başvuru türü döndürüp döndürmediği hakkında gerekli bilgileri kaybetmediğinden, genel iletme işlevlerine izin verir. Bir iletme işlevine ait kod örneği için, önceki `myFunc` şablon işlevi örneğine bakın.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, `Plus()` şablon işlevinin sonradan belirtilen dönüş türünü bildirir. `Plus` işlevi iki işleneni **işleç +** aşırı yükleme ile işler. Sonuç olarak, artı işlecinin (+) yorumlanması ve `Plus` işlevinin dönüş türü işlev bağımsız değişkenlerinin türlerine bağlıdır.

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

**Visual Studio 2017 ve üzeri:** Derleyici, şablon örneği yerine bildirildiğinde, decltype bağımsız değişkenlerini ayrıştırır. Sonuç olarak, decltype bağımsız değişkeninde bağımlı olmayan bir özelleştirme bulunursa, örnek oluşturma süresine ertelenir ve anında işlenir ve sonuçta ortaya çıkan hatalar bu sırada tanılanabilir.

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

`decltype(auto)`, Visual Studio 2015 veya üstünü gerektirir.
