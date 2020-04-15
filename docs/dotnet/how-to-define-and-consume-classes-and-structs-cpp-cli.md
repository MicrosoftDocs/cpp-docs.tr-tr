---
title: 'Nasıl yapılır: Sınıfları ve Yapıları Tanımlama ve Kullanma (C++/CLI)'
ms.date: 09/12/2018
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
ms.openlocfilehash: 5bec92ce2bd97f11723cdf59c58b7331b39565f2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370191"
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>Nasıl yapılır: Sınıfları ve Yapıları Tanımlama ve Kullanma (C++/CLI)

Bu makalede, C++/CLI'de kullanıcı tanımlı başvuru türleri ve değer türleri nasıl tanımlanılı pişecek ve tüketilir.

## <a name="contents"></a><a name="BKMK_Contents"></a>Içeriği

[Nesne anında](#BKMK_Object_instantiation)

[Örtük soyut sınıflar](#BKMK_Implicitly_abstract_classes)

[Tür görünürlüğü](#BKMK_Type_visibility)

[Üye görünürlüğü](#BKMK_Member_visibility)

[Genel ve özel yerli sınıflar](#BKMK_Public_and_private_native_classes)

[Statik yapıcılar](#BKMK_Static_constructors)

[Bu işaretçinin anlambilimi](#BKMK_Semantics_of_the_this_pointer)

[İmzaya göre gizle işlevleri](#BKMK_Hide_by_signature_functions)

[Kopya yapıcılar](#BKMK_Copy_constructors)

[Yıkıcılar ve sonlandırıcılar](#BKMK_Destructors_and_finalizers)

## <a name="object-instantiation"></a><a name="BKMK_Object_instantiation"></a>Nesne anında

Başvuru (ref) türleri yalnızca yönetilen yığında anlık olarak kullanılabilir, yığında veya yerel yığında değil. Değer türleri yığında veya yönetilen yığında anında kullanılabilir.

```cpp
// mcppv2_ref_class2.cpp
// compile with: /clr
ref class MyClass {
public:
   int i;

   // nested class
   ref class MyClass2 {
   public:
      int i;
   };

   // nested interface
   interface struct MyInterface {
      void f();
   };
};

ref class MyClass2 : public MyClass::MyInterface {
public:
   virtual void f() {
      System::Console::WriteLine("test");
   }
};

public value struct MyStruct {
   void f() {
      System::Console::WriteLine("test");
   }
};

int main() {
   // instantiate ref type on garbage-collected heap
   MyClass ^ p_MyClass = gcnew MyClass;
   p_MyClass -> i = 4;

   // instantiate value type on garbage-collected heap
   MyStruct ^ p_MyStruct = gcnew MyStruct;
   p_MyStruct -> f();

   // instantiate value type on the stack
   MyStruct p_MyStruct2;
   p_MyStruct2.f();

   // instantiate nested ref type on garbage-collected heap
   MyClass::MyClass2 ^ p_MyClass2 = gcnew MyClass::MyClass2;
   p_MyClass2 -> i = 5;
}
```

## <a name="implicitly-abstract-classes"></a><a name="BKMK_Implicitly_abstract_classes"></a>Örtük soyut sınıflar

*Dolaylı olarak soyut* bir sınıf anlık olamaz. Sınıfın temel türü bir arabirim ise ve sınıf arabirimin tüm üye işlevlerini uygulamıyorsa, sınıf örtülü olarak soyuttur.

Arabirimden türetilen bir sınıftan nesneler oluşturamıyorsanız, bunun nedeni sınıfın örtülü olarak soyut olması olabilir. Soyut sınıflar hakkında daha fazla bilgi için [özet](../extensions/abstract-cpp-component-extensions.md)e bakın.

Aşağıdaki kod örneği, işlev `MyClass` `MyClass::func2` uygulanmadığından sınıfın anlık olarak alınamayacağını göstermektedir. Örneğin derlemesini etkinleştirmek için, yorum `MyClass::func2`yapmayı bırakın.

```cpp
// mcppv2_ref_class5.cpp
// compile with: /clr
interface struct MyInterface {
   void func1();
   void func2();
};

ref class MyClass : public MyInterface {
public:
   void func1(){}
   // void func2(){}
};

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;   // C2259
                                          // To resolve, uncomment MyClass::func2.
}
```

## <a name="type-visibility"></a><a name="BKMK_Type_visibility"></a>Tür görünürlüğü

Ortak dil çalışma zamanı (CLR) türlerinin görünürlüğünü, böylece bir derleme başvurulmuşsa, derlemedeki türlerin montaj dışında görünür veya görünmez olmasını sağlayabilirsiniz.

`public`türü içeren derleme için bir yönerge `#using` içeren herhangi bir kaynak dosya tarafından görülebilir olduğunu gösterir.  `private`türü içeren derleme için bir `#using` yönerge içeren kaynak dosyaları için bir türün görünür olmadığını gösterir. Ancak, özel türleri aynı derleme içinde görünür. Varsayılan olarak, bir sınıfın `private`görünürlüğü.

Visual Studio 2005'ten önce varsayılan olarak, yerel türler derleme dışında genel erişilebilirlik tespilere sahipti. Özel yerel türlerin nerede yanlış kullanıldığını görmenize yardımcı olmak için [Derleyici Uyarısı (düzey 1) C4692'yi](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) etkinleştirin. Değiştiremediğiniz bir kaynak kodu dosyasında yerel bir türe genel erişilebilirlik sağlamak için [make_public](../preprocessor/make-public.md) pragmasını kullanın.

Daha fazla bilgi için [#using Yönergesi'ne](../preprocessor/hash-using-directive-cpp.md)bakın.

Aşağıdaki örnek, türlerin nasıl bildirilen ve erişilebilirliklerini belirtin ve daha sonra derleme içinde bu türlere erişmek gösterir. Elbette, özel türleri olan bir derleme kullanılarak `#using`başvurulmuşsa, yalnızca derlemedeki ortak türler görünür.

```cpp
// type_visibility.cpp
// compile with: /clr
using namespace System;
// public type, visible inside and outside assembly
public ref struct Public_Class {
   void Test(){Console::WriteLine("in Public_Class");}
};

// private type, visible inside but not outside assembly
private ref struct Private_Class {
   void Test(){Console::WriteLine("in Private_Class");}
};

// default accessibility is private
ref class Private_Class_2 {
public:
   void Test(){Console::WriteLine("in Private_Class_2");}
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   a->Test();

   Private_Class ^ b = gcnew Private_Class;
   b->Test();

   Private_Class_2 ^ c = gcnew Private_Class_2;
   c->Test();
}
```

**Çıktı**

```Output
in Public_Class
in Private_Class
in Private_Class_2
```

Şimdi, önceki örneği yeniden yazalım, böylece DLL olarak oluşturulacak.

```cpp
// type_visibility_2.cpp
// compile with: /clr /LD
using namespace System;
// public type, visible inside and outside the assembly
public ref struct Public_Class {
   void Test(){Console::WriteLine("in Public_Class");}
};

// private type, visible inside but not outside the assembly
private ref struct Private_Class {
   void Test(){Console::WriteLine("in Private_Class");}
};

// by default, accessibility is private
ref class Private_Class_2 {
public:
   void Test(){Console::WriteLine("in Private_Class_2");}
};
```

Sonraki örnek, derleme dışındaki türlere nasıl erişilenleri gösterir. Bu örnekte, istemci önceki örnekte oluşturulmuş bileşeni tüketir.

```cpp
// type_visibility_3.cpp
// compile with: /clr
#using "type_visibility_2.dll"
int main() {
   Public_Class ^ a = gcnew Public_Class;
   a->Test();

   // private types not accessible outside the assembly
   // Private_Class ^ b = gcnew Private_Class;
   // Private_Class_2 ^ c = gcnew Private_Class_2;
}
```

**Çıktı**

```Output
in Public_Class
```

## <a name="member-visibility"></a><a name="BKMK_Member_visibility"></a>Üye görünürlüğü

Bir genel sınıfın bir üyesine, aynı derleme nin içinden, erişim belirticilerinin `public` `protected`çiftlerini kullanarak, montaj dışından erişimden farklı bir şekilde erişebilirsiniz ve`private`

Bu tablo, çeşitli erişim belirtecilerinin etkisini özetler:

|Belirleyici|Etki|
|---------------|------------|
|public|Üye meclis içinde ve dışında erişilebilir.  Daha fazla bilgi için [genel](../cpp/public-cpp.md) kullanıma bakın.|
|private|Üye, ne içinde ne de dışında, erişilebilir değildir.  Daha fazla bilgi için [özel](../cpp/private-cpp.md) bakın.|
|protected|Üye meclis içinde ve dışında erişilebilir, ancak yalnızca türemiş türleri için.  Daha fazla bilgi için [korumalı](../cpp/protected-cpp.md) bakın.|
|internal|Üye meclis içinde kamu ama meclis dışında özeldir.  `internal`içeriğe duyarlı bir anahtar kelimedir.  Daha fazla bilgi [için, Bağlama Duyarlı Anahtar Kelimeler'e](../extensions/context-sensitive-keywords-cpp-component-extensions.md)bakın.|
|kamu korumalı -veya- korunan kamu|Üye meclis içinde kamu ama meclis dışında korunur.|
|özel korumalı -veya- korunan özel|Üye, montaj içinde ancak montaj dışında özel olarak korunur.|

Aşağıdaki örnek, farklı erişilebilirliklerle bildirilen üyeleri olan ortak bir türü gösterir ve daha sonra bu üyelerin derleme içinden erişmelerini gösterir.

```cpp
// compile with: /clr
using namespace System;
// public type, visible inside and outside the assembly
public ref class Public_Class {
public:
   void Public_Function(){System::Console::WriteLine("in Public_Function");}

private:
   void Private_Function(){System::Console::WriteLine("in Private_Function");}

protected:
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}

internal:
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}

protected public:
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}

public protected:
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}

private protected:
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}

protected private:
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}
};

// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Private_Function();
      Private_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   MyClass ^ b = gcnew MyClass;
   a->Public_Function();
   a->Protected_Public_Function();
   a->Public_Protected_Function();

   // accessible inside but not outside the assembly
   a->Internal_Function();

   // call protected functions
   b->Test();

   // not accessible inside or outside the assembly
   // a->Private_Function();
}
```

**Çıktı**

```Output
in Public_Function
in Protected_Public_Function
in Public_Protected_Function
in Internal_Function
=======================
in function of derived class
in Protected_Function
in Protected_Private_Function
in Private_Protected_Function
exiting function of derived class
=======================
```

Şimdi önceki örneği DLL olarak oluşturalım.

```cpp
// compile with: /clr /LD
using namespace System;
// public type, visible inside and outside the assembly
public ref class Public_Class {
public:
   void Public_Function(){System::Console::WriteLine("in Public_Function");}

private:
   void Private_Function(){System::Console::WriteLine("in Private_Function");}

protected:
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}

internal:
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}

protected public:
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}

public protected:
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}

private protected:
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}

protected private:
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}
};

// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Private_Function();
      Private_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};
```

Aşağıdaki örnek, önceki örnekte oluşturulan bileşeni tüketir ve bu nedenle üyelerin montaj dışından nasıl erişilebildiğini gösterir.

```cpp
// compile with: /clr
#using "type_member_visibility_2.dll"
using namespace System;
// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Public_Function();
      Public_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   MyClass ^ b = gcnew MyClass;
   a->Public_Function();

   // call protected functions
   b->Test();

   // can't be called outside the assembly
   // a->Private_Function();
   // a->Internal_Function();
   // a->Protected_Private_Function();
   // a->Private_Protected_Function();
}
```

**Çıktı**

```Output
in Public_Function
=======================
in function of derived class
in Protected_Function
in Protected_Public_Function
in Public_Protected_Function
exiting function of derived class
=======================
```

## <a name="public-and-private-native-classes"></a><a name="BKMK_Public_and_private_native_classes"></a>Genel ve özel yerli sınıflar

Yerel bir tür yönetilen bir tür başvurulabilir.  Örneğin, yönetilen bir türdeki bir işlev, türü yerel bir yapı olan bir parametre alabilir.  Yönetilen tür ve işlev bir derlemede ortaksa, yerel tür de ortak olmalıdır.

```cpp
// native type
public struct N {
   N(){}
   int i;
};
```

Ardından, yerel türü tüketen kaynak kodu dosyasını oluşturun:

```cpp
// compile with: /clr /LD
#include "mcppv2_ref_class3.h"
// public managed type
public ref struct R {
   // public function that takes a native type
   void f(N nn) {}
};
```

Şimdi, bir istemci derle:

```cpp
// compile with: /clr
#using "mcppv2_ref_class3.dll"

#include "mcppv2_ref_class3.h"

int main() {
   R ^r = gcnew R;
   N n;
   r->f(n);
}
```

## <a name="static-constructors"></a><a name="BKMK_Static_constructors"></a>Statik yapıcılar

Bir CLR türü (örneğin, bir sınıf veya yapı) statik veri üyelerini başlatmada kullanılabilecek statik bir oluşturucuya sahip olabilir.  Statik bir oluşturucu en fazla aynı anda çağrılır ve türün herhangi bir statik üyesine ilk kez erişilmeden önce çağrılır.

Bir örnek oluşturucu her zaman statik bir oluşturucu sonra çalışır.

Derleyici, sınıfın statik bir oluşturucusu varsa, bir oluşturucuya çağrı ekleyemez.  Derleyici, sınıf bir değer türüyse, statik bir oluşturucusu varsa ve örnek oluşturucusu yoksa, herhangi bir üye işleve çağrı yıkamaz.  CLR aramayı satırla yapabilir, ancak derleyici arayagiremez.

Yalnızca CLR tarafından çağrılması amaçlandığı için statik oluşturucuyu özel bir üye işlev olarak tanımlayın.

Statik oluşturucular hakkında daha fazla bilgi için [bkz: Arabirim Statik Oluşturucu (C++/CLI) tanımlayın.](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)

```cpp
// compile with: /clr
using namespace System;

ref class MyClass {
private:
   static int i = 0;

   static MyClass() {
      Console::WriteLine("in static constructor");
      i = 9;
   }

public:
   static void Test() {
      i++;
      Console::WriteLine(i);
   }
};

int main() {
   MyClass::Test();
   MyClass::Test();
}
```

**Çıktı**

```Output
in static constructor
10
11
```

## <a name="semantics-of-the-this-pointer"></a><a name="BKMK_Semantics_of_the_this_pointer"></a>Bu işaretçinin anlambilimi

Türleri tanımlamak için Visual C++ kullanıyorsanız, başvuru türündeki `this` işaretçi "işleç" türündendir. Değer `this` türündeki işaretçi "iç işaretçi" türündendir.

İşaretçin indeksleyicisi `this` çağrıldığında işaretçinin bu farklı semantikleri beklenmeyen davranışlara neden olabilir. Sonraki örnek, hem ref türünde hem de değer türünde varsayılan dizinleyiciye erişmenin doğru yolunu gösterir.

Daha fazla bilgi için bkz.

- [İşlenecek Nesne İşleci (^)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)

- [interior_ptr (C++/CLI)](../extensions/interior-ptr-cpp-cli.md)

```cpp
// compile with: /clr
using namespace System;

ref struct A {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }

   A() {
      // accessing default indexer
      Console::WriteLine("{0}", this[3.3]);
   }
};

value struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
   void Test() {
      // accessing default indexer
      Console::WriteLine("{0}", this->default[3.3]);
   }
};

int main() {
   A ^ mya = gcnew A();
   B ^ myb = gcnew B();
   myb->Test();
}
```

**Çıktı**

```Output
10.89
10.89
```

## <a name="hide-by-signature-functions"></a><a name="BKMK_Hide_by_signature_functions"></a>İmzaya göre gizle işlevleri

Standart C++'da, türemiş sınıf işlevi aynı sayıda veya türde parametreye sahip olmasa bile, taban sınıftaki bir işlev türemiş sınıfta aynı ada sahip bir işlev tarafından gizlenir. Bu, *hide-by-name* semantiği olarak adlandırılır. Başvuru türünde, taban sınıftaki bir işlev yalnızca türemiş bir sınıftaki bir işlev tarafından gizlenebilir, hem ad hem de parametre listesi aynıysa. Bu, *imzaya göre saklambaç* olarak bilinir.

Tüm işlevleri meta verilerde `hidebysig`". Varsayılan olarak, **/clr** altında oluşturulan `hidebysig` tüm sınıfların işlevleri vardır. Bir sınıfın `hidebysig` işlevleri olduğunda, derleyici işlevleri herhangi bir doğrudan temel sınıflarda ada göre gizlemez, ancak derleyici bir devralma zincirinde ada göre bir gizle sınıfla karşılaşırsa, bu ada göre gizleme davranışı devam eder.

İmzayla gizle semantiği altında, bir işlev nesne üzerinde çağrıldığında, derleyici işlev çağrısını karşılayabilen bir işlev içeren en türetilmiş sınıfı tanımlar. Sınıfta aramayı karşılayabilen tek bir işlev varsa, derleyici bu işlevi çağırır. Sınıfta aramayı karşılayabilen birden fazla işlev varsa, derleyici hangi işlevi arayacağını belirlemek için aşırı yükleme çözümleme kurallarını kullanır. Aşırı yükleme kuralları hakkında daha fazla bilgi için [Bkz. İşlev Aşırı Yükleme.](../cpp/function-overloading.md)

Belirli bir işlev çağrısı için, taban sınıftaki bir işlev, türetilmiş bir sınıftaki bir işlevden biraz daha iyi eşleşmesini sağlayan bir imzaya sahip olabilir. Ancak, işlev türemiş sınıfın bir nesnesinde açıkça çağrıldıysa, türemiş sınıftaki işlev çağrılır.

İade değeri bir işlevin imzasının bir parçası olarak kabul edilmeyin, aynı ada sahipse ve geri dönüş değerinin türünde farklılık olsa bile, türemiş sınıf işleviyle aynı sayı ve türdeki bağımsız değişkenleri alıyorsa, taban sınıf işlevi gizlenir.

Aşağıdaki örnek, taban sınıftaki bir işlevin türemiş bir sınıftaki bir işlev tarafından gizlenmediğini gösterir.

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   void Test() {
      Console::WriteLine("Base::Test");
   }
};

ref struct Derived : public Base {
   void Test(int i) {
      Console::WriteLine("Derived::Test");
   }
};

int main() {
   Derived ^ t = gcnew Derived;
   // Test() in the base class will not be hidden
   t->Test();
}
```

**Çıktı**

```Output
Base::Test
```

Sonraki örnek, Microsoft C++ derleyicisinin en çok türetilmiş sınıfta bir işlev çağırdığı (parametrelerden biri veya daha fazlasını eşleştirmek için dönüştürme gerekse ve işlev çağrısı için daha iyi bir eş olan bir taban sınıftaki bir işlevi çağırmasa bile) gösterir.

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   void Test2(Single d) {
      Console::WriteLine("Base::Test2");
   }
};

ref struct Derived : public Base {
   void Test2(Double f) {
      Console::WriteLine("Derived::Test2");
   }
};

int main() {
   Derived ^ t = gcnew Derived;
   // Base::Test2 is a better match, but the compiler
   // calls a function in the derived class if possible
   t->Test2(3.14f);
}
```

**Çıktı**

```Output
Derived::Test2
```

Aşağıdaki örnek, taban sınıf türemiş sınıfla aynı imzaya sahip olsa bile bir işlevi gizlemenin mümkün olduğunu gösterir.

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   int Test4() {
      Console::WriteLine("Base::Test4");
      return 9;
   }
};

ref struct Derived : public Base {
   char Test4() {
      Console::WriteLine("Derived::Test4");
      return 'a';
   }
};

int main() {
   Derived ^ t = gcnew Derived;

   // Base::Test4 is hidden
   int i = t->Test4();
   Console::WriteLine(i);
}
```

**Çıktı**

```Output
Derived::Test4
97
```

## <a name="copy-constructors"></a><a name="BKMK_Copy_constructors"></a>Kopya yapıcılar

C++ standardı, bir nesne taşındığında bir kopya oluşturucunun çağrıldığını, örneğin bir nesnenin aynı adreste oluşturulup yok edildiğini söyler.

Ancak, **/clr** derlemek için kullanıldığında ve MSIL için derlenen bir işlev, yerel sınıfın veya birden fazla sınıfın değere göre geçtiği ve yerel sınıfın bir kopya oluşturucusu ve/veya yıkıcısı olduğu yerel bir işlev olarak adlandırdığında, kopya oluşturucu çağrılmaz ve nesne oluşturulduğu yerden farklı bir adreste yok edilir. Bu, sınıfın içine bir işaretçi varsa veya kod nesneleri adrese göre izliyorsa sorunlara neden olabilir.

Daha fazla bilgi için bkz: [/clr (Ortak Dil Çalışma Zamanı Derlemesi).](../build/reference/clr-common-language-runtime-compilation.md)

Aşağıdaki örnek, bir kopya oluşturucu oluşturulmadığını gösterir.

```cpp
// compile with: /clr
#include<stdio.h>

struct S {
   int i;
   static int n;

   S() : i(n++) {
      printf_s("S object %d being constructed, this=%p\n", i, this);
   }

   S(S const& rhs) : i(n++) {
      printf_s("S object %d being copy constructed from S object "
               "%d, this=%p\n", i, rhs.i, this);
   }

   ~S() {
      printf_s("S object %d being destroyed, this=%p\n", i, this);
   }
};

int S::n = 0;

#pragma managed(push,off)
void f(S s1, S s2) {
   printf_s("in function f\n");
}
#pragma managed(pop)

int main() {
   S s;
   S t;
   f(s,t);
}
```

**Çıktı**

```Output
S object 0 being constructed, this=0018F378
S object 1 being constructed, this=0018F37C
S object 2 being copy constructed from S object 1, this=0018F380
S object 3 being copy constructed from S object 0, this=0018F384
S object 4 being copy constructed from S object 2, this=0018F2E4
S object 2 being destroyed, this=0018F380
S object 5 being copy constructed from S object 3, this=0018F2E0
S object 3 being destroyed, this=0018F384
in function f
S object 5 being destroyed, this=0018F2E0
S object 4 being destroyed, this=0018F2E4
S object 1 being destroyed, this=0018F37C
S object 0 being destroyed, this=0018F378
```

## <a name="destructors-and-finalizers"></a><a name="BKMK_Destructors_and_finalizers"></a>Yıkıcılar ve sonlandırıcılar

Başvuru türündeki yıkıcılar, kaynakların deterministik bir şekilde temizlenmesini gerçekleştirir. Sonlandırıcılar yönetilmeyen kaynakları temizler ve çöp toplayıcı tarafından yıkıcı veya nondeterministically tarafından deterministically çağrılabilir. Standart C++'daki yıkıcılar hakkında bilgi için [bkz.](../cpp/destructors-cpp.md)

```cpp
class classname {
   ~classname() {}   // destructor
   ! classname() {}   // finalizer
};
```

Yönetilen bir Görsel C++ sınıfındaki yıkıcıların davranışı, C++'ın Yönetilen Uzantıları'ndan farklıdır. Bu değişiklik hakkında daha fazla bilgi için, [Yıkıcı Semantics değişiklikler](../dotnet/changes-in-destructor-semantics.md)bakın.

CLR çöp toplayıcı kullanılmayan yönetilen nesneleri siler ve artık gerekli olmadığında belleklerini sbırakır. Ancak, bir tür çöp toplayıcınasıl serbest bırakmak için bilmiyor kaynakları kullanabilirsiniz. Bu kaynaklar yönetilmeyen kaynaklar (örneğin, yerel dosya işlamaları) olarak bilinir. Tüm yönetilmeyen kaynakları sonlandırıcıda serbest bırakmanızı öneririz. Yönetilen kaynaklar çöp toplayıcı tarafından nondeterministically serbest olduğundan, çöp toplayıcı zaten yönetilen kaynak temizlenmiş olması mümkündür, çünkü bir sonlandırıcı yönetilen kaynaklara başvurmak güvenli değildir.

Visual C++ sonlandırıcısı <xref:System.Object.Finalize%2A> yöntemle aynı değildir. (CLR dokümantasyonu sonlandırıcı <xref:System.Object.Finalize%2A> ve eşanlamlı yöntemi kullanır). Yöntem, <xref:System.Object.Finalize%2A> bir sınıf kalıtım zincirindeki her sonikileştiriciyi çağıran çöp toplayıcı tarafından çağrılır. Visual C++ yıkıcılarının aksine, türetilmiş sınıf sonlandırıcı çağrısı derleyicinin tüm temel sınıflarda sonlandırıcıyı çağırmasına neden olmaz.

Microsoft C++ derleyicisi kaynakların deterministic serbest bırakılmasını desteklediğinden, <xref:System.Object.Finalize%2A> kaynakları veya yöntemleri ni uygulamaya çalışmayın. <xref:System.IDisposable.Dispose%2A> Ancak, bu yöntemlere aşinaysanız, visual C++ sonlandırıcıve sonlandırıcı yıçağıran bir yıkıcıyı <xref:System.IDisposable.Dispose%2A> desenin nasıl çağırdığı aşağıda açıklanmıştır:

```cpp
// Visual C++ code
ref class T {
   ~T() { this->!T(); }   // destructor calls finalizer
   !T() {}   // finalizer
};

// equivalent to the Dispose pattern
void Dispose(bool disposing) {
   if (disposing) {
      ~T();
   } else {
      !T();
   }
}
```

Yönetilen bir tür, deterministically serbest bırakmak için tercih edeceğiniz yönetilen kaynakları da kullanabilir ve nesne artık gerekli olduktan sonra bir noktada belirsiz serbest bırakmak için çöp toplayıcısına bırakmayın. Kaynakların deterministik sürümü performansı önemli ölçüde artırabilir.

Microsoft C++ derleyicisi, nesneleri deterministically temizlemek için bir yıkıcı tanımı sağlar. Deterministically serbest bırakmak istediğiniz tüm kaynakları serbest bırakmak için yıkıcı kullanın.  Bir sonlandırıcı varsa, kod çoğaltma önlemek için, yıkıcı dan arayın.

```cpp
// compile with: /clr /c
ref struct A {
   // destructor cleans up all resources
   ~A() {
      // clean up code to release managed resource
      // ...
      // to avoid code duplication,
      // call finalizer to release unmanaged resources
      this->!A();
   }

   // finalizer cleans up unmanaged resources
   // destructor or garbage collector will
   // clean up managed resources
   !A() {
      // clean up code to release unmanaged resources
      // ...
   }
};
```

Türünüzü tüketen kod yıkıcıyı çağırmazsa, çöp toplayıcı sonunda yönetilen tüm kaynakları serbest bırakır.

Bir yıkıcının varlığı bir sonlandırıcının varlığı anlamına gelmez. Ancak, bir sonlandırıcı nın varlığı, bir yıkıcı tanımlamanız ve o yıkıcıdan sonlandırıcıyı çağırmanız gerektiği anlamına gelir. Bu, yönetilmeyen kaynakların deterministik serbest bırakılmasını sağlar.

Nesnenin sonlandırılmasını kullanarak <xref:System.GC.SuppressFinalize%2A>yıkıcıyı bastırma çağrısı. Yıkıcı çağrılmazsa, türün sonlandırıcısı sonunda çöp toplayıcıtarafından çağrılacaktır.

Yıkıcıyı arayarak nesnenizin kaynaklarını deterministically temizlemek CLR nondeterministically nesne sonuçlandırmak izin ile karşılaştırıldığında performansı artırabilir.

Visual C++ ile yazılmış ve **/clr** kullanılarak derlenen kod, bir türün yıkıcısı çalıştırıyor:

- Yığın anlambilimi kullanılarak oluşturulan bir nesne kapsam dışına çıkar. Daha fazla bilgi [için Bkz. Başvuru Türleri için C++ Yığın Anlamları.](../dotnet/cpp-stack-semantics-for-reference-types.md)

- Nesnenin yapısı sırasında bir özel durum atılır.

- Nesne, yıkıcı çalışan bir nesnenin üyesidir.

- Bir tanıtıcıdaki [silme](../cpp/delete-operator-cpp.md) işlecini çağırırsınız ([Nesne Işleci (^) tutamacı).](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)

- Yıkıcıyı açıkça ararsın.

Türünüz başka bir dilde yazılmış bir istemci tarafından tüketiliyorsa, yıkıcı aşağıdaki gibi adlandırılır:

- Bir <xref:System.IDisposable.Dispose%2A>aramada.

- Türüne `Dispose(void)` yapılan bir çağrıda.

- C# `using` deyiminde tür kapsam dışına çıkarsa.

Yönetilen yığında başvuru türünden bir nesne oluşturursanız (başvuru türleri için yığın semantiklerini kullanmazsanız), bir özel durum yıkıcının çalışmasını engellemediğinden emin olmak için [try-finally](../cpp/try-finally-statement.md) sözdizimini kullanın.

```cpp
// compile with: /clr
ref struct A {
   ~A() {}
};

int main() {
   A ^ MyA = gcnew A;
   try {
      // use MyA
   }
   finally {
      delete MyA;
   }
}
```

Türünüzün bir yıkıcısı varsa, derleyici bir `Dispose` yöntem <xref:System.IDisposable>oluşturur. Visual C++'da yazılmış ve başka bir dilden tüketilen bir yıkıcıvarsa, bu `IDisposable::Dispose` türe çağrı yapmak türün yıkıcısının çağrılmasını neden olur. Tür Görsel C++ istemcisinden tüketildiğinde, doğrudan arayama; `Dispose` bunun yerine, işleci kullanarak yıkıcıyı `delete` arayın.

Türünün sonlandırıcısı varsa, derleyici geçersiz `Finalize(void)` kılan <xref:System.Object.Finalize%2A>bir yöntem oluşturur.

Bir türde bir sonlandırıcı veya yıkıcı varsa, derleyici tasarım desenine göre bir `Dispose(bool)` yöntem oluşturur. (Bilgi için [bkz.](/dotnet/standard/design-guidelines/dispose-pattern) Visual C++'da `Dispose(bool)` açıkça yazamaz veya araamazsınız.

Bir türde tasarım desenine uygun bir taban sınıf varsa, türemiş sınıfın yıkıcısı çağrıldığında tüm taban sınıfların yıkıcıları çağrılır. (Türünüz Visual C++'da yazılmışsa, derleyici türlerinizin bu deseni uygulamasını sağlar.) Başka bir deyişle, bir referans sınıfının, C++ standardında belirtildiği şekilde üslerine ve üyelerine zincirler, önce sınıfın yıkıcısı çalıştırılır, sonra üyelerinin inşa edildikleri sıranın tersi, ve son olarak da temel sınıflarının yıkıcıları inşa edildikleri sıranın tersi.

Yıkıcılar ve sonlandırıcılar değer türleri veya arabirimler içinde izin verilmez.

Bir sonlandırıcı yalnızca bir başvuru türünde tanımlanabilir veya bildirilebilir. Bir yapıcı ve yıkıcı gibi, bir sonlandırıcının dönüş türü yoktur.

Bir nesnenin sonlandırıcı sıyrıkları çalıştırdıktan sonra, en az türetilmiş türle başlayan herhangi bir temel sınıftaki sonlandırıcılar da çağrılır. Veri üyeleri için sonlandırıcılar, sınıfın sonlandırıcısı tarafından otomatik olarak zincirlenmez.

Bir sonlandırıcı yönetilen bir türde yerel işaretçiyi silerse, yerel işaretçiye yapılan veya yerel işaretçi aracılığıyla yapılan başvuruların zamanından önce toplanmadığından emin olmalısınız; kullanmak yerine yönetilen türdeki yıkıcıyı çağırın. <xref:System.GC.KeepAlive%2A>

Derleme zamanında, bir türün sonlandırıcısı mı yoksa yok edicimi algılayabilirsiniz. Daha fazla bilgi [için, Tür Özellikleri için Derleyici Desteği'ne](../extensions/compiler-support-for-type-traits-cpp-component-extensions.md)bakın.

Sonraki örnek, biri yönetilmeyen kaynaklara ve diğeri deterministically yayımlanan kaynakları yönetilen iki türü gösterir.

```cpp
// compile with: /clr
#include <vcclr.h>
#include <stdio.h>
using namespace System;
using namespace System::IO;

ref class SystemFileWriter {
   FileStream ^ file;
   array<Byte> ^ arr;
   int bufLen;

public:
   SystemFileWriter(String ^ name) : file(File::Open(name, FileMode::Append)),
                                     arr(gcnew array<Byte>(1024)) {}

   void Flush() {
      file->Write(arr, 0, bufLen);
      bufLen = 0;
   }

   ~SystemFileWriter() {
      Flush();
      delete file;
   }
};

ref class CRTFileWriter {
   FILE * file;
   array<Byte> ^ arr;
   int bufLen;

   static FILE * getFile(String ^ n) {
      pin_ptr<const wchar_t> name = PtrToStringChars(n);
      FILE * ret = 0;
      _wfopen_s(&ret, name, L"ab");
      return ret;
   }

public:
   CRTFileWriter(String ^ name) : file(getFile(name)), arr(gcnew array<Byte>(1024) ) {}

   void Flush() {
      pin_ptr<Byte> buf = &arr[0];
      fwrite(buf, 1, bufLen, file);
      bufLen = 0;
   }

   ~CRTFileWriter() {
      this->!CRTFileWriter();
   }

   !CRTFileWriter() {
      Flush();
      fclose(file);
   }
};

int main() {
   SystemFileWriter w("systest.txt");
   CRTFileWriter ^ w2 = gcnew CRTFileWriter("crttest.txt");
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../extensions/classes-and-structs-cpp-component-extensions.md)<br/>
[Sınıflar ve Yapılar](../extensions/classes-and-structs-cpp-component-extensions.md)
