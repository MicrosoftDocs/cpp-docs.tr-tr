---
title: "Rvalue başvuru Bildirimcisi: &amp; &amp; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '&&'
dev_langs: C++
helpviewer_keywords: '&& rvalue reference declarator'
ms.assetid: eab0ce3a-c5a3-4992-aa70-6a8ab1f7491d
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8d0595078c9515c5c705a1cbfb1ed6b5e55db788
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="rvalue-reference-declarator-ampamp"></a>Rvalue başvuru Bildirimcisi:&amp;&amp;
Rvalue deyim için bir başvuru tutar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
type-id && cast-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Rvalue başvuru bir lvalue bir rvalue ayırt etmek etkinleştirin. Lvalue başvuru ve rvalue başvuru sözdizimsel olarak ve anlam olarak benzerdir, ancak biraz farklı kuralları izleyin. Lvalues ve rvalues hakkında daha fazla bilgi için bkz: [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md). Lvalue başvuru hakkında daha fazla bilgi için bkz: [Lvalue başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md).  
  
 Aşağıdaki bölümlerde rvalue başvuru uygulaması'ı nasıl desteklediğini *semantiği taşıma* ve *kusursuz iletme*.  
  
## <a name="move-semantics"></a>Taşıma semantiği  
 Rvalue başvuru uygulaması Destek *semantiği taşıma*, hangi önemli ölçüde artırabilir uygulamalarınızın performansını. Kaynakları (örneğin, dinamik olarak ayrılan bellek) aktarır kod yazmaya semantiği sağlar bir nesneden diğerine taşıyın. Başka bir programda başvurulamaz geçici nesnelerinden aktarılacak kaynakları sağladığından semantiği çalışır taşıyın.  
  
 Taşıma semantiği uygulamak için genellikle sağladığınız bir *taşıma oluşturucusu,* ve isteğe bağlı olarak bir taşıma atama işleci (`operator=`), sınıfınıza. Kaynaklarının rvalues olan sonra otomatik olarak yararlanmak Kopyala ve atama işlemlerine semantiği taşıyın. Varsayılan kopya Oluşturucu, bir varsayılan taşıma oluşturucusuna derleyici sağlamaz. Bir taşıma oluşturucusuna yazma ve uygulamanızda kullanmak hakkında daha fazla bilgi için bkz: [taşıma oluşturucuları ve taşıma atama işleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).  
  
 Sıradan işlevleri aşırı yüklenebilir ve yararlanmak için işleçleri semantiği taşıyın. Visual C++ 2010 C++ Standart Kitaplığı'na taşıma semantiği tanıtır. Örneğin, `string` sınıfı taşıma semantiği gerçekleştirmek işlemlerini uygular. Birkaç dizesini birleştirir ve sonucu yazdıracak aşağıdaki örneği göz önünde bulundurun:  
  
```  
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
  
 Visual C++ 2010'dan önce her çağrısı `operator+` ayırır ve yeni bir geçici döndürür `string` nesne (rvalue bir). `operator+`Kaynak dizeleri lvalues veya rvalues olduğunu bilmediğinden bir dize diğerine eklenemiyor. Kaynak dizeleri hem lvalues varsa, başka bir programda başvurulan ve bu nedenle değiştirilmemesi gerekir. Rvalue başvuru kullanarak `operator+` başka bir programda başvurulamaz rvalues yapılacak değiştirilebilir. Bu nedenle, `operator+` bir dize diğerine şimdi ekleyebilirsiniz. Bu dinamik bellek ayırma sayısını önemli ölçüde azaltabilir, `string` class gerçekleştirmelisiniz. Hakkında daha fazla bilgi için `string` sınıfı için bkz: [basic_string sınıfı](../standard-library/basic-string-class.md).  
  
 Derleyici dönüş değeri en iyi duruma getirme (RVO) veya adlı dönüş değeri en iyi duruma getirme (NRVO) kullanamazsınız taşıma semantiği de faydalıdır. Bu durumlarda, türü tanımlıyorsa derleyici taşıma oluşturucusuna çağırır. Adlı dönüş değeri en iyi duruma getirme hakkında daha fazla bilgi için bkz: [adlı dönüş değeri en iyi duruma getirme Visual C++ 2005'te](http://go.microsoft.com/fwlink/?LinkId=131571).  
  
 Taşıma semantiği daha iyi anlamak için bir öğeye ekleme örneği göz önünde bulundurun. bir `vector` nesnesi. Varsa kapasitesini `vector` nesne aşıldı `vector` nesne öğeleri için bellek tahsis ve her öğe, eklenen öğesi için yer açmak için başka bir bellek konumuna kopyalayın. Bir ekleme işlemi öğenin kopyaladığında, yeni bir öğesi oluşturur, önceki öğesinden yeni öğe verileri kopyalamak için Kopyala oluşturucuyu çağırır ve önceki öğesi yok eder. Taşıma semantiği pahalı bellek ayırma gerçekleştirmek ve kopyalama işlemlerini yapmak zorunda kalmadan doğrudan nesneleri taşımanızı sağlar.  
  
 Taşıma semantiği yararlanmak için `vector` örnek, verileri bir nesneden taşımak için bir taşıma oluşturucusuna yazabilirsiniz.  
  
 Taşıma semantiği giriş Visual C++ 2010 C++ Standart kitaplığına hakkında daha fazla bilgi için bkz: [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md).  
  
## <a name="perfect-forwarding"></a>Kusursuz iletme  
 Kusursuz iletme aşırı yüklenmiş işlevlerin gereksinimini azaltır ve iletme sorun yardımcı kaçının. *Sorun iletme* başvuru parametreleri olarak isteyen bir genel işlevi yazma ve bunu geçirir oluşabilir (veya *iletir*) Bu parametreleri başka bir işlev. Örneğin, genel işlevi türünde bir parametre sürerse `const T&`, sonra çağrılan işlev bu parametrenin değeri değiştirilemez. Genel işlevi türünde bir parametre sürerse `T&`, sonra da bir rvalue (örneğin, bir geçici nesne veya tamsayı değişmez değer) kullanarak işlevi çağrılamaz.  
  
 Normalde, bu sorunu çözmek için her ikisi de almayan aşırı yüklü sürümü genel işlevi sağlamalısınız `T&` ve `const T&` her parametreleri. Sonuç olarak, aşırı yüklenen işlevler sayısı katlanarak parametre sayısı artar. Rvalue başvuru isteğe bağlı bağımsız değişkenler kabul eder ve diğer işlevi doğrudan çağrısı yaptığını gibi bunları başka bir işleve ileten bir işlev bir sürümünü yazmanızı sağlar.  
  
 Dört tür bildirir aşağıdaki örneği göz önünde bulundurun `W`, `X`, `Y`, ve `Z`. Farklı bir birleşimi her türünün Oluşturucusu alır `const` ve olmayan-`const` lvalue başvuru parametreleri olarak.  
  
```  
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
  
 Nesneleri oluşturur genel bir işlev yazdığınızda istediğinizi varsayalım. Aşağıdaki örnek, bu işlev yazmak için bir yol gösterir:  
  
```  
template <typename T, typename A1, typename A2>  
T* factory(A1& a1, A2& a2)  
{  
   return new T(a1, a2);  
}  
```  
  
 Aşağıdaki örnek, geçerli bir çağrı gösterir `factory` işlevi:  
  
```  
int a = 4, b = 5;  
W* pw = factory<W>(a, b);  
```  
  
 Ancak, aşağıdaki örnek, geçerli bir çağrı içermiyor `factory` çünkü işlev `factory` parametreleri, ancak değiştirilebilir alır lvalue başvuru rvalues kullanarak çağrılır:  
  
```  
Z* pz = factory<Z>(2, 2);  
```  
  
 Normalde, bu sorunu çözmek için aşırı yüklü sürümünü oluşturmalısınız `factory` işlevi her birleşimi için `A&` ve `const A&` parametreleri. Rvalue başvuru etkinleştirmek bir sürümünü yazmanızı `factory` aşağıdaki örnekte gösterildiği gibi işlev:  
  
```  
template <typename T, typename A1, typename A2>  
T* factory(A1&& a1, A2&& a2)  
{  
   return new T(std::forward<A1>(a1), std::forward<A2>(a2));  
}  
```  
  
 Bu örnek için parametre olarak rvalue başvuru kullanır `factory` işlevi. Amacı [std::forward](../standard-library/utility-functions.md#forward) işlevidir şablon sınıf Fabrika işleve parametrelerinin iletmek için.  
  
 Aşağıdaki örnekte gösterildiği `main` düzenlenen kullanan bir işlev `factory` örneklerini oluşturmak üzere işlevini `W`, `X`, `Y`, ve `Z` sınıfları. Düzenlenen `factory` işlevi (lvalues veya rvalues) parametrelerini uygun sınıf oluşturucu iletir.  
  
```  
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
  
## <a name="additional-properties-of-rvalue-references"></a>Rvalue başvuru ek özellikler  
 **Lvalue başvuru ve rvalue başvuru almak için bir işlev aşırı yüklenebilir.**  
  
 Yapılacak bir işlev aşırı yüklemesi tarafından bir `const` lvalue başvuru veya rvalue başvuru, değiştirilebilir olmayan nesneler (lvalues) arasında ayırt kod yazabilirsiniz ve değiştirilebilir geçici değerleri (rvalues). Nesne olarak işaretlenmemişse rvalue başvuru isteyen bir işlevi için bir nesne geçirebilir `const`. Aşağıdaki örnek, işlev gösterir `f`, lvalue başvuru ve rvalue başvuru almak üzere aşırı. `main` İşlev çağrıları `f` lvalues ve bir rvalue.  
  
```  
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
  
 Bu örnek şu çıkışı üretir:  
  
```  
In f(const MemoryBlock&). This version cannot modify the parameter.  
In f(MemoryBlock&&). This version can modify the parameter.  
```  
  
 Bu örnekte, ilk çağrı `f` bağımsız değişken olarak yerel bir değişken (bir lvalue) geçirir. İkinci çağrı `f` geçici bir nesne, bağımsız değişkeni olarak geçirir. Çağrı aşırı yüklü sürümünü bağlar geçici nesne başka bir programda başvurulamaz çünkü `f` nesneyi değiştirmek ücretsiz bir rvalue başvuru alır.  
  
 **Derleyici bir lvalue olarak adlandırılmış rvalue başvuru ve adsız rvalue başvuru bir rvalue davranır.**  
  
 Rvalue başvuru, parametre olarak alan bir işlev yazdığınızda, bu parametre bir lvalue işlev gövdesine olarak kabul edilir. Bir adlandırılmış nesneyi çeşitli bölümlerini bir program tarafından başvurulabilir olduğundan derleyici bir lvalue adlandırılmış rvalue başvuru değerlendirir; birden çok bölümlerini değiştirmek veya bu nesneden kaynakları kaldırmak için bir program izin vermek tehlikeli olabilir. Örneğin, bir program birden fazla bölümü aynı nesneden kaynakları aktarım denerseniz, yalnızca ilk bölümü başarıyla kaynak aktarın.  
  
 Aşağıdaki örnek, işlev gösterir `g`, lvalue başvuru ve rvalue başvuru almak üzere aşırı. İşlev `f` kendi parametre (adlandırılmış rvalue başvuru) olarak rvalue başvuru alır ve bir rvalue başvuru (adlandırılmamış rvalue başvuru) döndürür. Çağrısında `g` gelen `f`, aşırı yükleme çözünürlüğü seçer sürümü `g` çünkü lvalue başvuru alan gövdesini `f` , parametresinin bir lvalue değerlendirir. Çağrısında `g` gelen `main`, aşırı yükleme çözünürlüğü seçer sürümü `g` çünkü rvalue başvuru alan `f` rvalue başvuru döndürür.  
  
```  
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
   return block;  
}  
  
int main()  
{  
   g(f(MemoryBlock()));  
}  
```  
  
 Bu örnek şu çıkışı üretir:  
  
```  
In g(const MemoryBlock&).  
In g(MemoryBlock&&).  
```  
  
 Bu örnekte, `main` işlevi bir rvalue geçirir `f`. Gövdesini `f` adlandırılmış parametre bir lvalue değerlendirir. Çağrısından `f` için `g` bir lvalue başvuru parametreyi bağlar (ilk aşırı yüklü sürümünü `g`).  
  
-   **Rvalue başvuru için bir lvalue çevirebilirsiniz.**  
  
 C++ Standart Kitaplığı [std::move](../standard-library/utility-functions.md#move) işlevi rvalue başvuru, bu nesneye bir nesne Dönüştür olanak sağlar. Alternatif olarak, kullanabileceğiniz `static_cast` anahtar sözcüğü bir lvalue rvalue başvuru için aşağıdaki örnekte gösterildiği gibi dönüştürmek için:  
  
```  
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
  
 Bu örnek şu çıkışı üretir:  
  
```  
In g(const MemoryBlock&).  
In g(MemoryBlock&&).  
```  
  
 **İşlev şablonları kendi şablon bağımsız değişken türleri türetme ve kuralları daraltma başvuru kullanın.**  
  
 Aktardığı işlevi şablon yazma yaygındır (veya *iletir*) başka bir işlev parametreleri. Şablon türü kesintisi rvalue başvuru ele işlev şablonları için nasıl çalıştığını anlamak önemlidir.  
  
 İşlev bağımsız değişkeni bir rvalue ise, derleyici rvalue başvuru olmasını deduces. Örneğin, bir rvalue başvuru türünde bir nesneye geçirirseniz `X` türü isteyen bir şablon işlevi için `T&&` , parametre olarak şablon bağımsız değişken kesintisi deduces `T` olmasını `X`. Bu nedenle, parametre türüne sahip `X&&`. İşlev bağımsız değişkeni bir lvalue ise veya `const` lvalue, derleyici deduces lvalue başvuru türünü veya `const` lvalue başvuru türü.  
  
 Aşağıdaki örnek, bir yapı şablon bildirir ve çeşitli başvuru türleri için uzmanlaşmış. `print_type_and_value` İşlev, parametre olarak rvalue başvuru alır ve uygun özel sürümüne iletir `S::print` yöntemi. `main` İşlevi çağırmak için çeşitli yollar gösterir `S::print` yöntemi.  
  
```  
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
  
 Bu örnek şu çıkışı üretir:  
  
```  
print<T&>: first  
print<const T&>: second  
print<T&&>: third  
print<const T&&>: fourth  
```  
  
 Her çağrı çözümlemek için `print_type_and_value` işlevi, derleyici ilk şablon bağımsız değişken kesintisi gerçekleştirir. Derleyici başvurusu parametre türleri sonucuna varılan şablon bağımsız değişkenleri değiştirir zaman kuralları daraltma sonra uygulanır. Örneğin, yerel değişken geçirme `s1` için `print_type_and_value` işlevi aşağıdaki işlevi imzayı üretmek derleyici neden olur:  
  
```  
print_type_and_value<string&>(string& && t)  
```  
  
 Derleyici imza aşağıdaki azaltmak için başvuru kuralları daraltma kullanır:  
  
```  
print_type_and_value<string&>(string& t)  
```  
  
 Bu sürümü `print_type_and_value` işlevi sonra doğru özel sürümü için kendi parametre iletir `S::print` yöntemi.  
  
 Şablon bağımsız değişken türü kesintisi için kuralları daraltma başvuru aşağıdaki tabloda özetlenmiştir:  
  
|||  
|-|-|  
|Genişletilmiş türü|Daraltılmış türü|  
|`T& &`|`T&`|  
|`T& &&`|`T&`|  
|`T&& &`|`T&`|  
|`T&& &&`|`T&&`|  
  
 Şablon bağımsız değişken kesintisi kusursuz iletme uygulamanın önemli bir öğedir. Alt bölümde, bu konunun önceki bölümlerinde sunulan, kusursuz iletme, kusursuz iletme daha ayrıntılı açıklanmıştır.  
  
## <a name="summary"></a>Özet  
 Rvalue başvuru lvalues rvalues ayırt etmek. Bunlar, gereksiz bellek ayırmaları gereksinimini ortadan kaldırarak, uygulamalarınızın performansını artırmak ve kopyalama işlemlerini yardımcı olabilir. Bunlar ayrıca isteğe bağlı bağımsız değişkenler kabul eder ve diğer işlevi doğrudan çağrısı yaptığını gibi bunları başka bir işleve ileten bir işlev bir sürümünü yazmak etkinleştirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [Lvalue başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md)   
 [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)   
 [Taşıma oluşturucuları ve taşıma atama işleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)   
