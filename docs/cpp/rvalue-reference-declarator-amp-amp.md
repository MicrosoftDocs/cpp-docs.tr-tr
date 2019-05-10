---
title: 'Rvalue başvuru Bildirimcisi: &amp;&amp;'
ms.date: 11/04/2016
f1_keywords:
- '&&'
helpviewer_keywords:
- '&& rvalue reference declarator'
ms.assetid: eab0ce3a-c5a3-4992-aa70-6a8ab1f7491d
ms.openlocfilehash: 663b639dbfecf9253547e1dd3b4e40480c27b470
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222037"
---
# <a name="rvalue-reference-declarator-ampamp"></a>Rvalue başvuru Bildirimcisi: &amp;&amp;

Rvalue ifadesi için bir başvuru içerir.

## <a name="syntax"></a>Sözdizimi

```
type-id && cast-expression
```

## <a name="remarks"></a>Açıklamalar

Rvalue başvurular bir lvalue bir rvalue'den ayırt etmek etkinleştirin. Lvalue başvuruları ve rvalue başvuruları sözdizimsel olarak ve anlam olarak benzerdir, ancak bunlar biraz farklı kuralları takip ederler. Lvalues ve rvalues hakkında daha fazla bilgi için bkz: [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md). Ivalue başvuruları hakkında daha fazla bilgi için bkz. [Lvalue başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md).

Aşağıdaki bölümlerde rvalue başvuruları uygulamasını nasıl destekler? *taşıma semantiği* ve *kusursuz iletme*.

## <a name="move-semantics"></a>Taşıma semantiği

Rvalue başvuruları uygulamasını destekler *taşıma semantiği*, önemli ölçüde artıran uygulamalarınızın performansını. Semantiği, kaynakları (örneğin, dinamik olarak ayrılan bellek) aktaran kod yazmanızı sağlayan bir nesneden diğerine taşıyabilirsiniz. Taşıma semantiği programda başka bir yerde başvurulamaz geçici nesnelerden kaynaklar aktarılmasını sağladığından çalışır.

Taşıma semantiği uygulamak için genellikle sınıfınıza bir *taşıma Oluşturucu,* ve isteğe bağlı olarak bir taşıma ataması işleci (**işleç =**), sınıfınıza. Taşıma semantiği, kaynakları rvalues değerleridir sonra otomatik olarak yararlanmak kopyalama ve atama işlemleri. Varsayılan kopya oluşturucusundan farklı olarak, derleyici varsayılan bir taşıma Oluşturucusu sağlamaz. Taşıma Oluşturucusu yazma ve uygulamanızda kullanma hakkında daha fazla bilgi için bkz. [taşıma oluşturucuları ve taşıma atama işleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).

Normal işlevleri de Aşırı yüklenme olabilir ve taşıma semantiği yararlanmak için işleçleri. Visual Studio 2010 içinde taşıma semantiklerini tanıtır C++ standart kitaplığı. Örneğin, `string` sınıfı semantik taşınmasını gerçekleştiren işlemleri uygular. Birkaç dizeyi birleştirmeye ve sonucu yazdırmaya aşağıdaki örneği göz önünde bulundurun:

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

Visual Studio 2010'dan önce her çağrısı **operator +** ayırır ve yeni bir geçici döndürür `string` nesnesini (rvalue). **operator +** kaynak dizelerin lvalues veya rvalues olduğunu bilmediği için bir dizeyi diğerine ekleyemez. Kaynak dizeleri her iki lvalues ise, programda başka bir yerde başvurulabilir ve bu nedenle değiştirilmemelidir. Rvalue başvuruları kullanılarak **operator +** programda başka bir yerde başvurulamaz rvalues değeri alması için değiştirilebilir. Bu nedenle, **operator +** şimdi bir dizeyi başka birine ekleyebilir. Bu dinamik bellek ayırma sayısını önemli ölçüde azaltabilir, `string` sınıfı gerçekleştirmeniz gerekir. Hakkında daha fazla bilgi için `string` sınıfı [basic_string sınıfı](../standard-library/basic-string-class.md).

Derleyici dönüş değeri iyileştirme (RVO) veya adlı dönüş değeri iyileştirme (NRVO) kullanamadığı zaman, taşıma semantiği de yardımcı olur. Bu gibi durumlarda, tür tanımlıyorsa derleyici taşıma yapıcısını çağırır. Adlı dönüş değeri iyileştirme hakkında daha fazla bilgi için bkz: [adlı dönüş değeri iyileştirme Visual Studio 2005](https://msdn.microsoft.com/library/ms364057.aspx).

Taşıma semantiğini daha iyi anlamak için bir öğe ekleme örneği göz önünde bulundurun. bir `vector` nesne. Varsa kapasitesini `vector` nesne aşıldı, `vector` nesnesinin kendi öğeleri için bellek tahsis ve ardından her öğe eklenen öğeye yer açmak için başka bir bellek konumuna kopyalayın. Bir ekleme işlemi bir öğe kopyalarken, yeni bir öğe oluşturur, verileri yeni bir öğe için önceki öğeyi kopyalamak için Kopyala oluşturucusunu çağırır ve ardından önceki öğeyi yok eder. Taşıma semantiği, pahalı bellek ayırması gerçekleştirmek ve kopyalama işlemlerini yapmak zorunda kalmadan nesneleri taşımanıza olanak sağlar.

Örneğinde taşıma semantiklerinden yararlanmak için `vector` örnek, verileri bir nesneden diğerine taşımak amacıyla taşıma yapıcısı yazabilirsiniz.

Giriş semantik taşımayı dahil etme hakkında daha fazla bilgi için C++ Visual Studio 2010, standart kitaplığında bkz [ C++ standart Kitaplığı](../standard-library/cpp-standard-library-reference.md).

## <a name="perfect-forwarding"></a>Kusursuz iletme

Kusursuz iletme aşırı yüklenmiş işlevlere gereksinimini azaltır ve iletme sorunundan yardımcı kaçının. *Sorun iletme* parametre olarak başvuruları alan genel işlevi yazmak ve geçirir oluşabilir (veya *iletir*) Bu parametreleri başka bir işlev. Örneğin jenerik işlev türünde bir parametre alırsa, `const T&`, çağrılan işlev bu parametrenin değerini değiştiremez. Genel işlev türünde bir parametre alırsa `T&`, işlev bir rvalue (örneğin, geçici bir nesne veya değişmez değer tamsayı) kullanılarak çağrılamaz.

Normalde, bu sorunu çözmek için hem de alan genel işlevin aşırı yüklenmiş sürümleri sağlamalısınız `T&` ve `const T&` kendi parametrelerinin her biri için. Sonuç olarak, aşırı yüklenen işlevlerin sayısı, parametre sayısıyla birlikte katlanarak artar. Rvalue başvuruları, rasgele bağımsız değişkenleri kabul eden ve diğer işlev doğrudan çağrılmış gibi bunları başka bir işleve ileten bir işlevin bir sürümünü yazmanıza olanak sağlar.

Dört tür bildiren aşağıdaki örneği göz önünde bulundurun `W`, `X`, `Y`, ve `Z`. Her tür için oluşturucu alan farklı bir birleşimini **const** ve olmayan-**const** parametre olarak lvalue başvuruları.

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

Nesneleri oluşturan genel işlevi yazmak istediğinizi varsayalım. Aşağıdaki örnek, bu işlevi yazmanın bir yöntemi gösterir:

```cpp
template <typename T, typename A1, typename A2>
T* factory(A1& a1, A2& a2)
{
   return new T(a1, a2);
}
```

Aşağıdaki örnek, geçerli bir çağrı gösterir `factory` işlevi:

```cpp
int a = 4, b = 5;
W* pw = factory<W>(a, b);
```

Ancak, aşağıdaki örnekte, geçerli bir çağrı içermiyor `factory` olduğundan işlev `factory` parametrelerini, ancak bunu lvalue başvurularını alır, rvalues kullanarak çağrılır:

```cpp
Z* pz = factory<Z>(2, 2);
```

Normalde, bu sorunu çözmek için aşırı yüklenmiş bir sürümünü oluşturmalısınız `factory` işlevi her birleşimi için `A&` ve `const A&` parametreleri. Rvalue başvuruları bir sürümünü yazmanıza olanak tanır `factory` aşağıdaki örnekte gösterildiği gibi işlev:

```cpp
template <typename T, typename A1, typename A2>
T* factory(A1&& a1, A2&& a2)
{
   return new T(std::forward<A1>(a1), std::forward<A2>(a2));
}
```

Bu örnekte, parametreleri olarak rvalue başvuruları kullanılmaktadır `factory` işlevi. Amacı [std::forward](../standard-library/utility-functions.md#forward) şablonu sınıfının oluşturucusu, Fabrika işlevinin parametrelerini iletecek şekilde işlevdir.

Aşağıdaki örnekte gösterildiği `main` düzenlenen kullanan işlev `factory` örneklerini oluşturmak için işlevi `W`, `X`, `Y`, ve `Z` sınıfları. Düzenlenen `factory` işlevi parametrelerini (lvalues veya rvalues) uygun sınıf oluşturucusuna iletir.

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

## <a name="additional-properties-of-rvalue-references"></a>Rvalue başvuruları ek özellikleri

**Lvalue başvuru ve rvalue başvurusu almak için işleve Aşırı yüklenme olabilir.**

Almak için işleve aşırı yükleme tarafından bir **const** değiştirilebilir geçici değerleri (rvalues) ve lvalue başvurusunu veya rvalue başvurusu değiştirilemez nesnelerle (lvalues) ayıran kod yazabilirsiniz. Nesne olarak işaretlenmediği sürece bir rvalue başvurusu alan bir işlev için bir nesne geçirebilirsiniz **const**. Aşağıdaki örnek işlev gösterir `f`, aşırı yüklenmiş bir lvalue başvurusu ve rvalue başvurusu almak için. `main` İşlev çağrılarında `f` hem lvalues hem de rvalue ile.

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

Bu örnekte, ilk çağrı `f` bağımsız değişken olarak yerel bir değişken (lvalue) geçirir. İçin yapılan ikinci çağrı `f` geçici bir nesne, bağımsız değişkeni olarak geçirir. Geçici bir nesne başka bir programda başvuruda bulunulamaz çünkü çağrıyı aşırı yüklenmiş sürümüne bağlanır `f` nesneyi değiştirmek ücretsiz olarak bir rvalue başvurusunu alır.

**Derleyici, adlandırılmış bir rvalue başvurusunu lvalue olarak ve adlandırılmamış bir rvalue başvurusunu rvalue olarak değerlendirir.**

Rvalue başvurusunu parametre olarak alan bir işlev yazdığınızda, söz konusu parametre işlevin gövdesinde lvalue olarak değerlendirilir. Adlandırılmış bir nesneye bir programın çeşitli parçaları tarafından başvuru yapılabildiği derleyici adlandırılmış bir rvalue başvurusunu lvalue olarak değerlendirebilir; birden fazla bölümü değiştirmek veya o nesneden kaynakları kaldırmak için bir program izin vermek tehlikeli olabilir. Örneğin, bir programın birden çok parçası kaynakları aynı nesneden aktarmaya çalışırsanız yalnızca ilk bölümü başarıyla kaynak aktarın.

Aşağıdaki örnek işlev gösterir `g`, aşırı yüklenmiş bir lvalue başvurusu ve rvalue başvurusu almak için. İşlev `f` bir rvalue başvurusunu kendi parametresi olarak (adlandırılmış bir rvalue Başvurusu) alır ve bir rvalue başvurusuna (adlandırılmamış rvalue Başvurusu) döndürür. Çağrısında `g` gelen `f`, aşırı yükleme çözünürlüğü sürümünü seçer `g` çünkü bir lvalue başvurusuna alan gövdesinin `f` , parametresinin bir lvalue gibi kabul eder. Çağrısında `g` gelen `main`, aşırı yükleme çözünürlüğü sürümünü seçer `g` çünkü bir rvalue başvurusu alan `f` bir rvalue başvurusu döndürür.

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

Bu örnekte, `main` işlevi öğesine rvalue geçirir `f`. Gövdesi `f` adlandırılmış parametresini bir lvalue gibi kabul eder. Çağrısından `f` için `g` parametreyi bir lvalue başvurusuna bağlar (ilk Aşırı yüklenen sürümü `g`).

- **Bir rvalue başvurusuna bir lvalue çevirebilirsiniz.**

C++ Standart Kitaplığı [std::move](../standard-library/utility-functions.md#move) işlevi bir nesne için o nesnenin rvalue başvurusuna dönüştürmenize olanak sağlar. Alternatif olarak, **static_cast** anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi lvalue olarak bir rvalue başvurusuna atanamadı:

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

**İşlev şablonları kendi şablon bağımsız değişken türlerini alır ve ardından başvuru daraltma kuralları kullanın.**

Başarılı bir işlev şablonu yazılması olağandır (veya *iletir*) başka bir işlev parametrelerini. Şablon türü kesintisinin rvalue başvurularını alan işlev şablonları için nasıl çalıştığını anlamak önemlidir.

İşlev bağımsız değişkeni bir rvalue ise, derleyici bağımsız değişkenin rvalue başvurusu olarak anlar. Örneğin, bir nesne türü bir rvalue başvurusunu geçirirseniz `X` türünü alan bir şablon işlevine `T&&` parametre olarak şablon bağımsız değişkeni kesintisi çıkarır `T` olmasını `X`. Bu nedenle, parametre türüne sahip `X&&`. İşlev bağımsız değişkeni bir lvalue ise veya **const** lvalue çıkarır derleyici bir ıvalue başvurusu için türünü veya **const** lvalue başvuru türü.

Aşağıdaki örnek, bir yapı şablonu bildirir ve ardından onu çeşitli başvuru türlerine uzmanlaşmış. `print_type_and_value` İşlevi bir rvalue başvurusunu parametre olarak alan ve ilgili özel sürümüne iletir `S::print` yöntemi. `main` İşlevi çağırmak için çeşitli yollar gösterir `S::print` yöntemi.

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

Her çağrı çözümlenecek `print_type_and_value` işlevi, derleyici önce şablon bağımsız değişkeni kesintisi gerçekleştirir. Derleyici, ardından başvuru daraltma kuralları, çıkarılan şablon bağımsız değişken parametre türleri için yerini alır, uygular. Örneğin, yerel değişken geçirme `s1` için `print_type_and_value` işlevi, derleyicinin aşağıdaki işlev imzasını üretmesine neden olur:

```cpp
print_type_and_value<string&>(string& && t)
```

Derleyici imzayı aşağıdaki hale indirgemek için başvuru daraltma kuralları kullanır:

```cpp
print_type_and_value<string&>(string& t)
```

Bu sürümü `print_type_and_value` işlevi daha sonra parametresini doğru sürümüne iletir `S::print` yöntemi.

Başvuru daraltma kuralları şablon bağımsız değişken türü kesintisi için aşağıdaki tabloda özetlenmiştir:

|||
|-|-|
|Genişletilmiş tür|Daraltılmış tür|
|`T& &`|`T&`|
|`T& &&`|`T&`|
|`T&& &`|`T&`|
|`T&& &&`|`T&&`|

Şablon bağımsız değişkeni kesintisi, kusursuz iletme uygulamanın önemli bir öğedir. Bu konunun önceki bölümlerinde sunulan, kusursuz iletme, bölüm kusursuz iletme bölümünde daha ayrıntılı açıklanmaktadır.

## <a name="summary"></a>Özet

Rvalue başvuruları lvalues rvalues'den ayırt eder. Bunlar, gereksiz bellek ayırma gereksinimini ortadan kaldırarak uygulamalarınızın performansını ve kopyalama işlemlerini yardımcı olabilir. Bunlar ayrıca, rasgele bağımsız değişkenleri kabul eden ve diğer işlev doğrudan çağrılmış gibi bunları başka bir işleve ileten bir işlevin bir sürümünü yazmanıza olanak sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Lvalue Başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Lvalue ve Rvalue’lar](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
[Taşıma Oluşturucuları ve Taşıma Atama İşleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
