---
title: Rvalue Başvuru Beyanörü:&amp;&amp;
ms.date: 11/04/2016
f1_keywords:
- '&&'
helpviewer_keywords:
- '&& rvalue reference declarator'
ms.assetid: eab0ce3a-c5a3-4992-aa70-6a8ab1f7491d
ms.openlocfilehash: 53729cca7c259bc2d3b792ddc3509d5fc3bd255a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749832"
---
# <a name="rvalue-reference-declarator-ampamp"></a>Rvalue Başvuru Beyanörü:&amp;&amp;

Rvalue ifadesine başvuru tutar.

## <a name="syntax"></a>Sözdizimi

```
type-id && cast-expression
```

## <a name="remarks"></a>Açıklamalar

Rvalue başvuruları bir lvalue'ı rvalue'dan ayırt etmenizi sağlar. Lvalue başvuruları ve rvalue başvuruları sözdizimsel ve anlamsal olarak benzerdir, ancak biraz farklı kurallar izlerler. Lvalues ve rvalues hakkında daha fazla bilgi için, [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)bakın. Lvalue başvuruları hakkında daha fazla bilgi için [Bkz. Lvalue Başvuru Beyanörü: &. ](../cpp/lvalue-reference-declarator-amp.md)

Aşağıdaki bölümlerde rvalue başvurularının *taşıma semantikve* *mükemmel iletme*uygulamasını nasıl desteklediği açıklanmıştır.

## <a name="move-semantics"></a>Taşı Semantik

Rvalue referansları, uygulamalarınızın performansını önemli ölçüde artırabilecek *taşıma semantiklerinin*uygulanmasını destekler. Semantik taşıma, kaynakları (dinamik olarak ayrılmış bellek gibi) bir nesneden diğerine aktaran kod yazmanızı sağlar. Programın başka bir yerinde başvurulanamayan geçici nesnelerden kaynakların aktarılmasını sağladığından anlambilimi taşıyın çalışır.

Taşıma semantikini uygulamak için genellikle bir *hareket oluşturucusu* ve isteğe bağlı olarak bir taşıma atama işleci **(işleç=**), sınıfınıza sağlarsınız. Kaynakları rvalues olan kopyalama ve atama işlemleri sonra otomatik olarak taşıma semantik yararlanmak. Varsayılan kopya oluşturucunun aksine, derleyici varsayılan bir hareket oluşturucu sağlamaz. Bir hareket oluşturucusu nasıl yazılabilen ve uygulamanızda nasıl kullanılacağı hakkında daha fazla bilgi için [bkz.](../cpp/move-constructors-and-move-assignment-operators-cpp.md)

Ayrıca, taşıma semantikyararlanmak için sıradan işlevleri ve işleçleri aşırı yükleyebilirsiniz. Visual Studio 2010, C++ Standart Kitaplığı'na anlambilimi taşır. Örneğin, `string` sınıf taşıma semantik gerçekleştiren işlemleri uygular. Birkaç dizeleri birleştirir ve sonucu yazdırır aşağıdaki örneği düşünün:

```cpp
// string_concatenation.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
using namespace std;

int main()
{
   string s = string("h") + "e" + "ll" + "o";
   cout << s << endl;
}
```

Visual Studio 2010'dan önce, **operatör+** için yapılan `string` her çağrı yeni bir geçici nesne (bir rvalue) ayırır ve döndürür. **işleç+** kaynak dizelerin lvalues veya rvalues olup olmadığını bilmediği için bir dizeyi diğerine ekleyemez. Kaynak dizeleri her iki lvalues ise, programın başka bir yerinde başvurulabilir ve bu nedenle değiştirilmemelidir. Rvalue referansları kullanılarak, **operatör+** programın başka bir yerinde başvurulanamayan rvalues alacak şekilde değiştirilebilir. Bu nedenle, **işleç+** artık bir dizeyi diğerine ekleyebilir. Bu, `string` sınıfın gerçekleştirmesi gereken dinamik bellek ayırmalarının sayısını önemli ölçüde azaltabilir. Sınıf hakkında daha fazla bilgi için [basic_string Sınıfı'na](../standard-library/basic-string-class.md)bakın. `string`

Taşıma semantik de derleyici Return Value Optimizasyonu (RVO) veya Adlandırılmış İade Değeri Optimizasyonu (NRVO) kullanamazsınız yardımcı olur. Bu gibi durumlarda, derleyici, tür tanımlıyorsa taşı oluşturucuyu çağırır.

Taşıma semantikini daha iyi anlamak için, bir öğeyi nesneye `vector` ekleme örneğini düşünün. `vector` Nesnenin kapasitesi aşılırsa, nesnenin `vector` öğeleri için belleği yeniden tahsis etmesi ve eklenen öğeye yer açmak için her öğeyi başka bir bellek konumuna kopyalaması gerekir. Ekleme işlemi bir öğeyi kopyaladığında, yeni bir öğe oluşturur, önceki öğedeki verileri kopyalaması için kopya oluşturucuyu çağırır ve önceki öğeyi yok eder. Taşıma semantik pahalı bellek ayırma ve kopyalama işlemleri gerçekleştirmek zorunda kalmadan nesneleri doğrudan taşımak için izin sağlar.

`vector` Örnekteki anlambilimi taşımaavantajından yararlanmak için, verileri bir nesneden diğerine taşımak için bir hareket oluşturucu yazabilirsiniz.

Visual Studio 2010'daki C++ Standart Kitaplığı'na taşıma semantiklerinin tanıtımı hakkında daha fazla bilgi için [C++ Standart Kitaplığı'na](../standard-library/cpp-standard-library-reference.md)bakın.

## <a name="perfect-forwarding"></a>Mükemmel Yönlendirme

Mükemmel yönlendirme, aşırı yüklü fonksiyonlar gereksinimini azaltır ve iletme problemini önlemeye yardımcı olur. *İletme sorunu,* referansları parametreleri olarak alan ve bu parametreleri başka bir işleve geçen (veya *ileten)* genel bir işlev yazdığınızda oluşabilir. Örneğin, genel işlev bir tür `const T&`parametresi alıyorsa, çağrılan işlev bu parametrenin değerini değiştiremez. Genel işlev bir tür `T&`parametresi alırsa, işlev bir rvalue (geçici bir nesne veya tamsayı literal gibi) kullanılarak çağrılamaz.

Normalde, bu sorunu çözmek `T&` `const T&` için, hem de parametrelerinin her biri için genel işlevin aşırı yüklü sürümlerini sağlamanız gerekir. Sonuç olarak, aşırı yüklenen işlevlerin sayısı parametre sayısı ile katlanarak artar. Rvalue başvuruları, rasgele bağımsız değişkenleri kabul eden ve diğer işlev doğrudan çağrılmış gibi başka bir işleve ileten bir işlevin bir sürümünü yazmanızı sağlar.

`W`Dört tür, , `X`, `Y`ve `Z`. Her tür için oluşturucu, parametreleri olarak **const** ve**const** olmayan lvalue başvurularının farklı bir birleşimini alır.

```cpp
struct W
{
   W(int&, int&) {}
};

struct X
{
   X(const int&, int&) {}
};

struct Y
{
   Y(int&, const int&) {}
};

struct Z
{
   Z(const int&, const int&) {}
};
```

Nesneleri oluşturan genel bir işlev yazmak istediğinizi varsayalım. Aşağıdaki örnek, bu işlevi yazmanın bir yolunu gösterir:

```cpp
template <typename T, typename A1, typename A2>
T* factory(A1& a1, A2& a2)
{
   return new T(a1, a2);
}
```

Aşağıdaki örnek, işleve geçerli `factory` bir çağrı gösterir:

```cpp
int a = 4, b = 5;
W* pw = factory<W>(a, b);
```

Ancak, aşağıdaki `factory` örnek, parametreleri olarak değiştirilebilir `factory` lvalue başvuruları aldığından, işleviçin geçerli bir çağrı içermez, ancak rdeğerleri kullanılarak çağrılır:

```cpp
Z* pz = factory<Z>(2, 2);
```

Normalde, bu sorunu çözmek için, her bir diziliş `factory` `A&` ve `const A&` parametreler için işlevin aşırı yüklü bir sürümünü oluşturmanız gerekir. Rvalue başvuruları, aşağıdaki örnekte `factory` gösterildiği gibi işlevin bir sürümünü yazmanızı sağlar:

```cpp
template <typename T, typename A1, typename A2>
T* factory(A1&& a1, A2&& a2)
{
   return new T(std::forward<A1>(a1), std::forward<A2>(a2));
}
```

Bu örnek, işlevin parametreleri `factory` olarak rvalue başvurularını kullanır. [Std::forward](../standard-library/utility-functions.md#forward) işlevinin amacı, fabrika işlevinin parametrelerini şablon sınıfının oluşturucuya iletmektir.

Aşağıdaki örnek, `main` `factory` `W`, `X`, `Y`ve `Z` sınıflar örnekleri oluşturmak için gözden geçirilmiş işlevi kullanan işlevi gösterir. Gözden `factory` geçirilen işlev parametrelerini (lvalues veya rvalues) uygun sınıf oluşturucuya iletir.

```cpp
int main()
{
   int a = 4, b = 5;
   W* pw = factory<W>(a, b);
   X* px = factory<X>(2, b);
   Y* py = factory<Y>(a, 2);
   Z* pz = factory<Z>(2, 2);

   delete pw;
   delete px;
   delete py;
   delete pz;
}
```

## <a name="additional-properties-of-rvalue-references"></a>Rvalue Başvurularının Ek Özellikleri

**Bir lvalue başvurusu ve bir rvalue başvurusu almak için bir işlevi aşırı yükleyebilirsiniz.**

Const lvalue başvurusu **const** veya rvalue başvurusu almak için bir işlevi aşırı yükleyerek, değiştirilemeyen nesneler (lvalues) ve değiştirilebilir geçici değerler (rvalues) arasında ayrım yapan kod yazabilirsiniz. Nesne **const**olarak işaretlenmediği sürece bir nesneyi rvalue başvurusu alan bir işleve geçirebilirsiniz. Aşağıdaki örnek, bir `f`lvalue başvurusu ve bir rvalue başvurusu almak için aşırı yüklenen işlevi gösterir. İşlev `main` `f` hem lvalues hem de bir rvalue ile çağırır.

```cpp
// reference-overload.cpp
// Compile with: /EHsc
#include <iostream>
using namespace std;

// A class that contains a memory resource.
class MemoryBlock
{
   // TODO: Add resources for the class here.
};

void f(const MemoryBlock&)
{
   cout << "In f(const MemoryBlock&). This version cannot modify the parameter." << endl;
}

void f(MemoryBlock&&)
{
   cout << "In f(MemoryBlock&&). This version can modify the parameter." << endl;
}

int main()
{
   MemoryBlock block;
   f(block);
   f(MemoryBlock());
}
```

Bu örnek, aşağıdaki çıktıyı üretir:

```Output
In f(const MemoryBlock&). This version cannot modify the parameter.
In f(MemoryBlock&&). This version can modify the parameter.
```

Bu örnekte, ilk `f` çağrı bağımsız değişkenolarak yerel bir değişkeni (bir lvalue) geçirir. İkinci çağrı `f` bağımsız değişkenolarak geçici bir nesne geçer. Geçici nesne programın başka bir yerine başvurulamayacağından, çağrı, nesneyi `f` değiştirmek için ücretsiz bir rvalue başvurusu alır, bunun aşırı yüklenen sürümüne bağlanır.

**Derleyici, adlandırılmış bir rvalue başvuruyu bir lvalue ve advers bir rvalue referansını rvalue olarak değerlendirir.**

Parametresi olarak rvalue referansı alan bir işlev yazdığınızda, bu parametre işlevin gövdesinde bir lvalue olarak kabul edilir. Derleyici, adlandırılmış bir nesne bir programın çeşitli bölümleri tarafından başvurulabileceğinden, adlandırılmış rvalue başvuruyu bir lvalue olarak değerlendirir; bir programın birden çok bölümünün kaynakları değiştirmesine veya bu nesneden kaldırmasına izin vermek tehlikeli olabilir. Örneğin, bir programın birden çok bölümü aynı nesneden kaynak aktarmayı denerse, yalnızca ilk bölümü kaynağı başarıyla aktaracaktır.

Aşağıdaki örnek, bir `g`lvalue başvurusu ve bir rvalue başvurusu almak için aşırı yüklenen işlevi gösterir. İşlev, `f` parametresi (adlandırılmış rvalue başvurusu) olarak bir rvalue başvurusu alır ve bir rvalue referansı (adsız rvalue başvurusu) döndürür. `g` Gelen `f`çağrıda, aşırı yük çözünürlüğü, `g` parametresini bir lvalue `f` olarak ele aldığından, bunun bir lvalue referansı aldığı sürümünü seçer. `g` Gelen `main`çağrıda, aşırı yük çözünürlüğü, `g` bir rvalue başvurusu `f` döndürdüğünden, bunun bir rvalue başvurusu aldığı sürümünü seçer.

```cpp
// named-reference.cpp
// Compile with: /EHsc
#include <iostream>
using namespace std;

// A class that contains a memory resource.
class MemoryBlock
{
   // TODO: Add resources for the class here.
};

void g(const MemoryBlock&)
{
   cout << "In g(const MemoryBlock&)." << endl;
}

void g(MemoryBlock&&)
{
   cout << "In g(MemoryBlock&&)." << endl;
}

MemoryBlock&& f(MemoryBlock&& block)
{
   g(block);
   return move(block);
}

int main()
{
   g(f(MemoryBlock()));
}
```

Bu örnek, aşağıdaki çıktıyı üretir:

```cpp
In g(const MemoryBlock&).
In g(MemoryBlock&&).
```

Bu örnekte, `main` işlev bir rvalue geçer `f`. Gövde, `f` adlandırılmış parametresini bir lvalue olarak ele adatır. Aramadan `f` gelen `g` arama, parametreyi bir lvalue başvurusuna (ilk `g`aşırı yüklenen sürümü) bağlar.

- **Bir rvalue başvurusuna bir lvalue döküm yapabilirsiniz.**

C++ Standart Kitaplık [std::move](../standard-library/utility-functions.md#move) işlevi, bir nesneyi o nesneye rvalue başvurusuna dönüştürmenizi sağlar. Alternatif olarak, aşağıdaki örnekte gösterildiği gibi, bir rvalue başvurusuna bir lvalue dökmek için **static_cast** anahtar sözcük kullanabilirsiniz:

```cpp
// cast-reference.cpp
// Compile with: /EHsc
#include <iostream>
using namespace std;

// A class that contains a memory resource.
class MemoryBlock
{
   // TODO: Add resources for the class here.
};

void g(const MemoryBlock&)
{
   cout << "In g(const MemoryBlock&)." << endl;
}

void g(MemoryBlock&&)
{
   cout << "In g(MemoryBlock&&)." << endl;
}

int main()
{
   MemoryBlock block;
   g(block);
   g(static_cast<MemoryBlock&&>(block));
}
```

Bu örnek, aşağıdaki çıktıyı üretir:

```cpp
In g(const MemoryBlock&).
In g(MemoryBlock&&).
```

**İşlev şablonları şablon bağımsız değişken türlerini aldatıcı ve ardından başvuru daraltma kurallarını kullanır.**

Parametrelerini başka bir işleve geçen *forwards*(veya ileten) bir işlev şablonu yazmak yaygındır. Rvalue başvuruları alan işlev şablonları için şablon türü tümdengeliminin nasıl çalıştığını anlamak önemlidir.

İşlev bağımsız değişkeni bir rvalue ise, derleyici bağımsız değişkeni bir rvalue başvurusu olarak görür. Örneğin, bir rvalue başvurucunu bir tür `X` nesnesine aktarıyorsanız, bir şablon işlevine parametresi olarak türü `T&&` alır, şablon bağımsız değişken çıkarımı `T` . `X` Bu nedenle, parametre `X&&`türü vardır. İşlev bağımsız değişkeni bir lvalue veya **const** lvalue ise, derleyici türünü bu türbir lvalue başvurusu veya **const** lvalue başvurusu olarak görür.

Aşağıdaki örnek, bir yapı şablonu bildirir ve sonra çeşitli başvuru türleri için özel. İşlev, `print_type_and_value` parametresi olarak bir rvalue referansı alır ve `S::print` yöntemin uygun özel sürümüne iletir. İşlev, `main` `S::print` yöntemi çağırmanın çeşitli yollarını gösterir.

```cpp
// template-type-deduction.cpp
// Compile with: /EHsc
#include <iostream>
#include <string>
using namespace std;

template<typename T> struct S;

// The following structures specialize S by
// lvalue reference (T&), const lvalue reference (const T&),
// rvalue reference (T&&), and const rvalue reference (const T&&).
// Each structure provides a print method that prints the type of
// the structure and its parameter.

template<typename T> struct S<T&> {
   static void print(T& t)
   {
      cout << "print<T&>: " << t << endl;
   }
};

template<typename T> struct S<const T&> {
   static void print(const T& t)
   {
      cout << "print<const T&>: " << t << endl;
   }
};

template<typename T> struct S<T&&> {
   static void print(T&& t)
   {
      cout << "print<T&&>: " << t << endl;
   }
};

template<typename T> struct S<const T&&> {
   static void print(const T&& t)
   {
      cout << "print<const T&&>: " << t << endl;
   }
};

// This function forwards its parameter to a specialized
// version of the S type.
template <typename T> void print_type_and_value(T&& t)
{
   S<T&&>::print(std::forward<T>(t));
}

// This function returns the constant string "fourth".
const string fourth() { return string("fourth"); }

int main()
{
   // The following call resolves to:
   // print_type_and_value<string&>(string& && t)
   // Which collapses to:
   // print_type_and_value<string&>(string& t)
   string s1("first");
   print_type_and_value(s1);

   // The following call resolves to:
   // print_type_and_value<const string&>(const string& && t)
   // Which collapses to:
   // print_type_and_value<const string&>(const string& t)
   const string s2("second");
   print_type_and_value(s2);

   // The following call resolves to:
   // print_type_and_value<string&&>(string&& t)
   print_type_and_value(string("third"));

   // The following call resolves to:
   // print_type_and_value<const string&&>(const string&& t)
   print_type_and_value(fourth());
}
```

Bu örnek, aşağıdaki çıktıyı üretir:

```cpp
print<T&>: first
print<const T&>: second
print<T&&>: third
print<const T&&>: fourth
```

İşlevdeki her `print_type_and_value` çağrıyı çözmek için derleyici önce şablon bağımsız değişken çıkarımı gerçekleştirir. Derleyici daha sonra parametre türleri için çıkarılan şablon bağımsız değişkenlerinin yerine başvuru daraltma kuralları uygular. Örneğin, yerel değişkenin `s1` `print_type_and_value` işleve geçirilmesi derleyicinin aşağıdaki işlev imzasını oluşturmasına neden olur:

```cpp
print_type_and_value<string&>(string& && t)
```

Derleyici, imzayı aşağıdakilere düşürmek için başvuru daraltma kurallarını kullanır:

```cpp
print_type_and_value<string&>(string& t)
```

İşlevin `print_type_and_value` bu sürümü daha sonra parametresini `S::print` yöntemin doğru özelleştirilmiş sürümüne iletir.

Aşağıdaki tabloda şablon bağımsız değişken türü tümleç için başvuru daraltma kuralları özetlenir:

|||
|-|-|
|Genişletilmiş tür|Daraltılmış tür|
|`T& &`|`T&`|
|`T& &&`|`T&`|
|`T&& &`|`T&`|
|`T&& &&`|`T&&`|

Şablon bağımsız değişken tümdengelimi, mükemmel iletme uygulamanın önemli bir öğesidir. Bu konuda daha önce sunulan Perfect Forwarding bölümü, daha ayrıntılı olarak mükemmel iletme açıklar.

## <a name="summary"></a>Özet

Rvalue başvuruları lvalues'i r değerlerinden ayırır. Gereksiz bellek ayırma ve kopyalama işlemleri gereksinimini ortadan kaldırarak uygulamalarınızın performansını artırmanıza yardımcı olabilir. Ayrıca, rasgele bağımsız değişkenleri kabul eden ve diğer işlev doğrudan çağrılmış gibi başka bir işleve ileten bir işlevin bir sürümünü yazmanızı sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Lvalue Başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
[Taşıma Oluşturucuları ve Taşıma Atama İşleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)<br/>
[C++ Standart Kitaplık](../standard-library/cpp-standard-library-reference.md)
