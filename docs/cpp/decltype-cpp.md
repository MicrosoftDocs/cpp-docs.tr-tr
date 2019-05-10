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
ms.openlocfilehash: 0a4e9eb015df056dfe2a35da18cfa50875ced432
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222462"
---
# <a name="decltype--c"></a>decltype (C++)

**Decltype** tür belirticisi belirtilen ifade türünü ortaya çıkarır. **Decltype** tür tanımlayıcısı ile birlikte [auto anahtar sözcüğü](../cpp/auto-cpp.md), öncelikli olarak şablon kitaplıklarını yazma geliştiriciler için yararlıdır. Kullanım **otomatik** ve **decltype** türü olan dönüş bir şablon işlevi bildirmek için şablon bağımsız değişkenlerinin türlerine bağlıdır. Ya da kullanmak **otomatik** ve **decltype** başka bir işleve bir çağrı sarılır ve ardından sarılı işlevin dönüş türünü döndüren bir şablon işlevi bildirmek için.

## <a name="syntax"></a>Sözdizimi

```
decltype( expression )
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*İfade*|Bir ifade. Daha fazla bilgi için [ifadeleri](../cpp/expressions-cpp.md).|

## <a name="return-value"></a>Dönüş Değeri

Türünü *ifade* parametresi.

## <a name="remarks"></a>Açıklamalar

**Decltype** türü belirticisi, Visual Studio 2010 veya sonraki sürümlerinde desteklenir ve yerel veya yönetilen kod ile kullanılabilir. `decltype(auto)` (c ++ 14) Visual Studio 2015 ve sonraki sürümlerde desteklenir.

Derleyici, türünü belirlemek için aşağıdaki kuralları kullanır. *ifade* parametresi.

- Varsa *ifade* parametresi bir tanımlayıcıdır ya da bir [sınıf üye erişimi](../cpp/member-access-operators-dot-and.md), `decltype(expression)` tarafından adlandırılan varlık türü olduğu *ifade*. Böyle bir varlık yoksa veya *ifade* parametresi aşırı yüklenmiş işlev kümesini adlandırırsa, derleyici bir hata iletisi verir.

- Varsa *ifade* parametresi bir işlev veya bir aşırı yüklenmiş bir işleç işlevinin çağrısı ise `decltype(expression)` işlevin dönüş türü. Aşırı yüklenmiş işlecin etrafındaki parantezler yoksayılır.

- Varsa *ifade* parametresi bir [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` türü *ifade*. Varsa *ifade* parametresi bir [lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` olduğu bir [lvalue başvuru](../cpp/lvalue-reference-declarator-amp.md) türüne *ifade*.

Aşağıdaki kod örneğinde bazı kullanımlarını gösterir **decltype** tür tanımlayıcısı. İlk olarak, aşağıdaki deyimleri kodladığınızı varsayalım.

```cpp
int var;
const int&& fx();
struct A { double x; }
const A* a = new A();
```

Ardından, dört tarafından döndürülen türleri inceleyin **decltype** aşağıdaki tabloda deyimleri.

|Deyim|Tür|Notlar|
|---------------|----------|-----------|
|`decltype(fx());`|`const int&&`|Bir [rvalue başvuru](../cpp/rvalue-reference-declarator-amp-amp.md) için bir **const int**.|
|`decltype(var);`|**int**|`var` değişkeninin türü.|
|`decltype(a->x);`|**double**|Üye erişiminin türü.|
|`decltype((a->x));`|`const double&`|İç parantezler, deyimin bir üye erişimi yerine bir ifade değerlendirilmesine neden olur. Üstelik `a` olarak bildirilen bir `const` işaretçi türü olan bir başvuru **const çift**.|

## <a name="decltype-and-auto"></a>Decltype ve Otomatik

C ++ 14'te, kullandığınız `decltype(auto)` dönüş türü bir şablon işlevi bildirmek için sondaki dönüş türü olmadan, şablon bağımsız değişkenlerinin türlerine bağlıdır.

C ++ 11'de kullanabileceğiniz **decltype** tür belirticisini bitiş dönüş türü üzerinde birlikte **otomatik** dönüş türü bir şablon işlevi bildirmek için anahtar sözcüğü, kendi şablon türlerine bağlıdır bağımsız değişkenler. Örneğin, aşağıdaki kod örneğini dikkate alın, burada şablon işlevin dönüş türü şablon bağımsız değişkenlerinin türlerine bağlıdır. Kod örneğinde, *bilinmeyen* yer tutucu gösteren dönüş türü belirtilemez.

```cpp
template<typename T, typename U>
UNKNOWN func(T&& t, U&& u){ return t + u; };
```

Giriş **decltype** tür belirticisiyle birlikte bir geliştirici şablon işlevinin döndürdüğü ifadenin türünü elde edilir. Kullanım *alternatif işlev bildirim sözdizimi* , daha sonra gösterilecek **otomatik** anahtar sözcüğü ve **decltype** tür belirticisini bildirmek için bir  *sonradan belirtilmiş* dönüş türü. Sonradan belirtilmiş dönüş türü, bildirim kodlandığında değil, derlendiğinde belirlenir.

Aşağıdaki prototip, alternatif bir işlev bildiriminin sözdizimini göstermektedir. Unutmayın **const** ve **geçici** niteleyicileri ve **throw** [özel durum belirtimi](../cpp/exception-specifications-throw-cpp.md) isteğe bağlıdır. *Function_body* yer tutucusu işlevin ne yaptığını belirten bir bileşik deyimi temsil eder. En iyi kodlama uygulaması olarak *ifade* yer tutucu **decltype** deyimi tarafından belirtilen ifadeyle eşleşmelidir **dönüş** varsa deyimi*function_body*.

**Otomatik** *işlev_adı* **(** *parametreleri*<sub>iyileştirilmiş</sub> **)**  **const**<sub>iyileştirilmiş</sub> **geçici**<sub>iyileştirilmiş</sub> **->** **decltype (** *ifade* **)** **throw**<sub>iyileştirilmiş</sub> **{** *function_body* **};**

Aşağıdaki kod örneğinde, `myFunc` şablon işlevinin sonradan belirtilen dönüş türü, `t` ve `u` şablon bağımsız değişkenlerinin türleri tarafından belirlenir. Bir iyi kodlama yöntemi, kod örneğinde ayrıca rvalue başvuruları kullanır ve `forward` destekleyen işlev şablonu *kusursuz iletme*. Daha fazla bilgi için [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

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

## <a name="decltype-and-forwarding-functions-c11"></a>Decltype ve iletme işlevleri (C ++ 11)

İletme işlevleri, diğer işlevlere yapılan çağrıları sarar. Bağımsız değişkenlerini veya o bağımsız değişkenlerle ilişkili bir ifadenin sonuçlarını başka bir işleve ileten bir işlev şablonu düşünün. Ayrıca, ileten işlev diğer işlevin çağrılması sonucunu döndürür. Bu senaryoda, ileten işlevin dönüş türü sarılan işlevin dönüş türü ile aynı olması gerekir.

Bu senaryoda, uygun bir tür ifadesi olmadan yazılamıyor **decltype** tür tanımlayıcısı. **Decltype** tür belirticisiyle birlikte genel iletme işlevlerinin çünkü bir işlevin bir başvuru türü olup olmadığını döndürür hakkında gerekli bilgileri kaybetmez. Bir iletme işlevine ait kod örneği için, önceki `myFunc` şablon işlevi örneğine bakın.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, `Plus()` şablon işlevinin sonradan belirtilen dönüş türünü bildirir. `Plus` İşlevi işler, iki işlenenini **operator +** aşırı yükleme. Sonuç olarak, artı işlecinin (+) yorumlanması ve `Plus` işlevinin dönüş türü işlev bağımsız değişkenlerinin türlerine bağlıdır.

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

**Visual Studio 2017 ve sonraki sürümleri:** Şablonları bildirilen örneği yerine olduğunda derleyici decltype bağımsız değişkenleri ayrıştırır. Sonuç olarak, bağımlı olmayan özelleştirmesi decltype değişkeninde bulunursa, örnekleme zamanı ertelenmiş değil ve hemen işlenir ve ortaya çıkan hataları o anda koydu.

Aşağıdaki örnek, bildirildiği tetiklenir böyle bir derleyici hatası gösterir:

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

Visual Studio 2010 veya sonraki sürümler.

`decltype(auto)` Visual Studio 2015 veya sonraki bir sürümü gerektirir.