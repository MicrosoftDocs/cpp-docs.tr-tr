---
description: 'Şu konuda daha fazla bilgi edinin: rvalue başvuru bildirimci: &amp;&amp;'
title: 'Rvalue başvuru bildirimci: &amp;&amp;'
ms.date: 11/04/2016
f1_keywords:
- '&&'
helpviewer_keywords:
- '&& rvalue reference declarator'
ms.assetid: eab0ce3a-c5a3-4992-aa70-6a8ab1f7491d
ms.openlocfilehash: 6c88116c5834c027d72874d1377e79799faa80ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319384"
---
# <a name="rvalue-reference-declarator-ampamp"></a>Rvalue başvuru bildirimci: &amp;&amp;

Bir rvalue ifadesine bir başvuru tutar.

## <a name="syntax"></a>Syntax

```
type-id && cast-expression
```

## <a name="remarks"></a>Açıklamalar

Rvalue başvuruları, bir lvalue değerini rvalue ile ayırt etmenizi sağlar. Lvalue başvuruları ve Rvalue başvuruları sözdizimsel ve anlamsal olarak benzerdir, ancak biraz farklı kuralları izler. Lvalues ve rvalues hakkında daha fazla bilgi için bkz. [lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md). Lvalue başvuruları hakkında daha fazla bilgi için bkz. [lvalue başvuru bildirimci: &](../cpp/lvalue-reference-declarator-amp.md).

Aşağıdaki bölümlerde, Rvalue başvurularını *taşıma semantiğinin* ve *kusursuz iletme* uygulamasının nasıl desteklediği açıklanır.

## <a name="move-semantics"></a>Taşıma semantiği

Rvalue başvuruları, uygulamalarınızın performansını önemli ölçüde artırabilen *taşıma semantiğinin* uygulanmasını destekler. Taşıma semantiği, kaynakları (dinamik olarak ayrılan bellek gibi) bir nesneden diğerine aktaran bir kod yazmanızı sağlar. Taşıma semantiği, kaynakların programın başka bir yerinde başvuramadığı geçici nesnelerden aktarılmasını sağladığından, bu yüzden.

Taşıma semantiğini uygulamak için, genellikle sınıfınıza bir *taşıma Oluşturucu* ve isteğe bağlı olarak bir taşıma atama işleci (**operator =**) sağlarsınız. Kaynakları rvalues olan kopyalama ve atama işlemleri otomatik olarak taşıma semantiğinin avantajlarından yararlanır. Varsayılan kopya oluşturucusunun aksine, derleyici varsayılan bir taşıma Oluşturucusu sağlamaz. Taşıma oluşturucusu yazma ve uygulamanızda kullanma hakkında daha fazla bilgi için bkz. [Taşıma Oluşturucuları ve taşıma atama işleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).

Ayrıca, taşıma semantiğinin avantajlarından yararlanmak için sıradan işlevleri ve işleçleri aşırı yükleyebilirsiniz. Visual Studio 2010, C++ standart kitaplığı 'na taşıma semantiğini tanıtır. Örneğin, `string` sınıfı taşıma semantiğini gerçekleştiren işlemler uygular. Birkaç dizeyi birleştiren ve sonucu yazdıran aşağıdaki örneği göz önünde bulundurun:

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

Visual Studio 2010 ' den önce, **operator +** öğesine yapılan her çağrı, yeni bir geçici `string` nesne (rvalue) ayırır ve döndürür. **operator +** , kaynak dizelerinin lvalues veya rvalues olduğunu bilmez çünkü bir dizeyi diğerine ekleyemiyor. Kaynak dizeleri her ikisi de ise, programda başka bir yerde bulunabilir ve bu nedenle değiştirilmemelidir. Rvalue başvuruları kullanılarak **işleç +** , programın başka bir yerinde başvurulabilen rvalues alacak şekilde değiştirilebilir. Bu nedenle, **operator +** artık bir dizeyi başka bir dizeye ekleyebilir. Bu, sınıfın gerçekleştirmesi gereken dinamik bellek ayırma sayısını önemli ölçüde azaltabilir `string` . Sınıfı hakkında daha fazla bilgi için `string` bkz. [basic_string sınıfı](../standard-library/basic-string-class.md).

Taşıma semantiği Ayrıca derleyicinin dönüş değeri Iyileştirmesi (RVO) veya adlandırılmış dönüş değeri Iyileştirmesi (NRVO) kullanmasına yardımcı olur. Bu durumlarda, derleyici tür tanımlıyorsa taşıma oluşturucusunu çağırır.

Taşıma semantiğini daha iyi anlamak için, nesnesine bir öğe ekleme örneğini düşünün `vector` . `vector`Nesnenin kapasitesi aşılırsa, `vector` nesnenin, öğeleri için belleği yeniden tahsis etmeniz ve sonra ekleme öğesi için yer açmak üzere her bir öğeyi başka bir bellek konumuna kopyalaması gerekir. Bir ekleme işlemi bir öğeyi kopyaladığında, yeni bir öğe oluşturur, önceki öğeden verileri yeni öğeye kopyalamak için kopyalama oluşturucusunu çağırır ve ardından önceki öğeyi yok eder. Taşıma semantiği, nesneleri pahalı bellek ayırma ve kopyalama işlemleri gerçekleştirmeye gerek kalmadan doğrudan taşımanızı sağlar.

Örnekteki taşıma semantiklerinden faydalanmak için `vector` , verileri bir nesneden diğerine taşımak üzere bir taşıma Oluşturucu yazabilirsiniz.

Visual Studio 2010 ' de C++ standart kitaplığı 'na taşıma semantiğinin tanıtımı hakkında daha fazla bilgi için bkz. [C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md).

## <a name="perfect-forwarding"></a>Kusursuz Iletme

Kusursuz iletme, aşırı yüklenmiş işlevlere gereksinimi azaltır ve iletme sorunundan kaçınmaya yardımcı olur. *İletme sorunu* , parametreleri olarak başvuru alan bir genel işlev yazdığınızda ve bu parametreleri başka bir işleve geçtiğinde (veya *ilettiğinde*) ortaya çıkabilir. Örneğin, genel işlev türünde bir parametre alırsa `const T&` , çağrılan işlev bu parametrenin değerini değiştiremez. Genel işlev türünde bir parametre alırsa `T&` , işlev bir rvalue kullanılarak çağrılamaz (örneğin, geçici bir nesne veya tamsayı sabit değeri).

Normalde, bu sorunu çözmek için, parametrelerinin her biri için hem hem de alan genel işlevin aşırı yüklenmiş sürümlerini sağlamanız gerekir `T&` `const T&` . Sonuç olarak, aşırı yüklenmiş işlevlerin sayısı parametre sayısıyla üstel olarak artar. Rvalue başvuruları, bir işlevin rastgele bağımsız değişkenleri kabul eden bir sürümünü yazmanızı ve diğer işlev doğrudan çağrılmış gibi başka bir işleve iletmelerini sağlar.

Dört tür (,,, ve) bildiren aşağıdaki örneği göz önünde bulundurun `W` `X` `Y` `Z` . Her bir türün Oluşturucusu, **`const`** parametreleri olarak farklı ve lvalue olmayan başvuruların bir birleşimini alır **`const`** .

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

Nesneleri üreten bir genel işlev yazmak istediğinizi varsayalım. Aşağıdaki örnek, bu işlevi yazmanın bir yolunu gösterir:

```cpp
template <typename T, typename A1, typename A2>
T* factory(A1& a1, A2& a2)
{
   return new T(a1, a2);
}
```

Aşağıdaki örnek, işlevine geçerli bir çağrı gösterir `factory` :

```cpp
int a = 4, b = 5;
W* pw = factory<W>(a, b);
```

Ancak, aşağıdaki örnek, `factory` `factory` parametresi olarak değiştirilebilir olan lvalue başvuruları aldığı, ancak rvalues kullanılarak çağrıldığı için işleve geçerli bir çağrı içermez:

```cpp
Z* pz = factory<Z>(2, 2);
```

Normalde, bu sorunu çözmek için, `factory` ve parametrelerinin her birleşimi için işlevin aşırı yüklenmiş bir sürümünü oluşturmanız gerekir `A&` `const A&` . Rvalue başvuruları `factory` , aşağıdaki örnekte gösterildiği gibi işlevin bir sürümünü yazmanızı sağlar:

```cpp
template <typename T, typename A1, typename A2>
T* factory(A1&& a1, A2&& a2)
{
   return new T(std::forward<A1>(a1), std::forward<A2>(a2));
}
```

Bu örnek, işlev için parametre olarak Rvalue başvurularını kullanır `factory` . [Std:: Forward](../standard-library/utility-functions.md#forward) işlevinin amacı, Factory işlevinin parametrelerini şablon sınıfının oluşturucusuna iletmektir.

Aşağıdaki örnek,,, `main` `factory` ve sınıflarının örneklerini oluşturmak için düzeltilmiş işlevi kullanan işlevi gösterir `W` `X` `Y` `Z` . Düzeltilen `factory` işlev parametrelerini (lvalues veya rvalues) uygun sınıf oluşturucusuna iletir.

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

## <a name="additional-properties-of-rvalue-references"></a>Rvalue başvurularının ek özellikleri

**Bir lvalue başvurusu ve rvalue başvurusu almak için bir işlevi aşırı yükleyebilirsiniz.**

Bir lvalue başvurusu veya rvalue başvurusu almak için bir işlevi aşırı yükleyerek **`const`** , değiştirilemeyen nesneler (lvalues) ve değiştirilebilir geçici değerler (rvalues) arasında ayrım yapan bir kod yazabilirsiniz. Nesne olarak işaretlenmedikçe rvalue başvurusunu alan bir işleve nesne geçirebilirsiniz **`const`** . Aşağıdaki örnek, `f` bir lvalue başvurusu ve rvalue başvurusu almak için aşırı yüklenmiş olan işlevini gösterir. `main`İşlev `f` hem lvalues hem de rvalue ile çağrı yapılır.

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

Bu örnek aşağıdaki çıktıyı üretir:

```Output
In f(const MemoryBlock&). This version cannot modify the parameter.
In f(MemoryBlock&&). This version can modify the parameter.
```

Bu örnekte, ilk çağrısı `f` bağımsız değişken olarak yerel bir değişken (bir lvalue) geçirir. İçin ikinci çağrı, `f` bağımsız değişkeni olarak geçici bir nesneyi geçirir. Geçici nesneye programın başka bir yerinde başvurulduğundan, çağrı, `f` nesneyi değiştirmek için boş olan bir rvalue başvurusu alan aşırı yüklenmiş sürümüne bağlanır.

**Derleyici adlandırılmış bir rvalue başvurusunu lvalue olarak ve adlandırılmamış bir rvalue başvurusunu rvalue olarak değerlendirir.**

Parametresi olarak bir rvalue başvurusu alan bir işlev yazdığınızda, bu parametre işlevin gövdesinde lvalue olarak değerlendirilir. Adlandırılmış bir nesneye bir programın birkaç bölümü tarafından başvurulduğundan, derleyici adlandırılmış bir rvalue başvurusunu lvalue olarak değerlendirir; bir programın birden çok bölümünün söz konusu nesneden kaynakları değiştirmesine veya kaldırmasına izin vermek tehlikeli olabilir. Örneğin, bir programın birden çok bölümü kaynakları aynı nesneden aktarmaya çalışıyorsa, yalnızca ilk parça kaynağı başarıyla aktarır.

Aşağıdaki örnek, `g` bir lvalue başvurusu ve rvalue başvurusu almak için aşırı yüklenmiş olan işlevini gösterir. İşlevi, `f` parametresi olarak bir rvalue başvurusu alır (adlandırılmış rvalue başvurusu) ve bir rvalue başvurusu döndürür (adlandırılmamış rvalue başvurusu). `g`' Den ' a yapılan çağrıda `f` , aşırı yükleme çözümlemesi parametresi bir lvalue `g` `f` olarak davrandığı için bir lvalue başvurusu alan sürümünü seçer. `g`' Den ' a yapılan çağrıda `main` , aşırı yükleme çözümlemesi, bir rvalue `g` başvurusu döndürdüğünden, bir rvalue başvurusu alan sürümünü seçer `f` .

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

Bu örnek aşağıdaki çıktıyı üretir:

```cpp
In g(const MemoryBlock&).
In g(MemoryBlock&&).
```

Bu örnekte, `main` işlevi bir rvalue öğesini öğesine geçirir `f` . Gövdesi, `f` adlandırılmış parametresini lvalue olarak değerlendirir. Öğesine çağrısı, `f` `g` parametresini bir lvalue başvurusuna (ilk aşırı yüklenmiş sürümü `g` ) bağlar.

- **Lvalue değerini rvalue başvurusuna çevirebilirsiniz.**

C++ Standart Kitaplığı [std:: Move](../standard-library/utility-functions.md#move) işlevi, bir nesneyi bu nesneye bir rvalue başvurusuna dönüştürmenize olanak sağlar. Alternatif olarak, **`static_cast`** Aşağıdaki örnekte gösterildiği gibi bir lvalue öğesini bir rvalue başvurusuna dönüştürmek için anahtar sözcüğünü kullanabilirsiniz:

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

Bu örnek aşağıdaki çıktıyı üretir:

```cpp
In g(const MemoryBlock&).
In g(MemoryBlock&&).
```

**İşlev şablonları, şablon bağımsız değişken türlerini ve ardından başvuru daraltma kurallarını kullanır.**

Parametrelerini başka bir işleve geçiren (veya *ileten*) bir işlev şablonu yazmak yaygındır. Şablon türü kesintisine, Rvalue başvuruları alan işlev şablonları için nasıl çalıştığını anlamak önemlidir.

İşlev bağımsız değişkeni bir rvalue ise, derleyici bağımsız değişkeni bir rvalue başvurusu olacak şekilde çıkarır. Örneğin, türü bir nesnesine bir rvalue başvurusunu `X` parametresi olarak türü alan bir şablon işlevine geçirirseniz `T&&` , şablon bağımsız değişken kesintisi `T` olur `X` . Bu nedenle, parametrenin türü vardır `X&&` . İşlev bağımsız değişkeni bir lvalue veya lvalue ise **`const`** , derleyici türünü bu türün lvalue başvurusu veya lvalue başvurusu olacak şekilde çıkarır **`const`** .

Aşağıdaki örnek, bir yapı şablonunu bildirir ve bunları çeşitli başvuru türleri için özelleştirir. `print_type_and_value`İşlevi, parametresi olarak bir rvalue başvurusu alır ve yöntemin uygun özel sürümüne iletir `S::print` . `main`İşlevi, yöntemi çağırmak için çeşitli yollar gösterir `S::print` .

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

Bu örnek aşağıdaki çıktıyı üretir:

```cpp
print<T&>: first
print<const T&>: second
print<T&&>: third
print<const T&&>: fourth
```

İşleve yapılan her çağrıyı çözümlemek için `print_type_and_value` , derleyici önce şablon bağımsız değişkeni kesintiini gerçekleştirir. Daha sonra derleyici, parametre türleri için çıkarılan şablon bağımsız değişkenlerini yerine koyar ve başvuru daraltma kuralları uygular. Örneğin, yerel değişkeni `s1` `print_type_and_value` işlevine geçirmek derleyicinin aşağıdaki işlev imzasını üretmesine neden olur:

```cpp
print_type_and_value<string&>(string& && t)
```

Derleyici, imzayı aşağıdaki şekilde azaltmak için başvuru daraltma kuralları kullanır:

```cpp
print_type_and_value<string&>(string& t)
```

İşlevin bu sürümü `print_type_and_value` daha sonra kendi parametresini yönteminin doğru özelleşmiş sürümüne iletir `S::print` .

Aşağıdaki tabloda, şablon bağımsız değişkeni tür kesintisi için başvuru daraltma kuralları özetlenmektedir:

| Genişletilmiş tür | Daraltılmış tür |
|--|--|
| `T& &` | `T&` |
| `T& &&` | `T&` |
| `T&& &` | `T&` |
| `T&& &&` | `T&&` |

Şablon bağımsız değişkeni kesintisi, kusursuz iletme uygulayan önemli bir öğedir. Bu konuda daha önce sunulan, kusursuz iletme başlıklı Bölüm, daha ayrıntılı bir şekilde iletme işlemini açıklar.

## <a name="summary"></a>Özet

Rvalue başvuruları lvalues değerlerini rvalues olarak ayırt edebilir. Bunlar, gereksiz bellek ayırmaları ve kopyalama işlemleri gereksinimini ortadan kaldırarak uygulamalarınızın performansını artırmanıza yardımcı olabilir. Ayrıca, rastgele bağımsız değişkenler kabul eden bir işlevin sürümünü yazmanızı ve diğer işlev doğrudan çağrılmış gibi başka bir işleve iletmelerini sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Lvalue Başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
[Taşıma Oluşturucuları ve Taşıma Atama İşleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)<br/>
[C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)
