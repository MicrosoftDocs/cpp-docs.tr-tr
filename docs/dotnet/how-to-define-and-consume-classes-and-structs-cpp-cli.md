---
title: 'Nasıl yapılır: Sınıfları ve Yapıları Tanımlama ve Kullanma (C++/CLI)'
ms.date: 09/12/2018
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
ms.openlocfilehash: 5fe7d6876b094c84fe3d4cdbba417106edcca528
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855792"
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>Nasıl yapılır: Sınıfları ve Yapıları Tanımlama ve Kullanma (C++/CLI)

Bu makalede,/Cli'de C++Kullanıcı tanımlı başvuru türlerini ve değer türlerini tanımlama ve kullanma gösterilmektedir.

##  <a name="BKMK_Contents"></a>Dekiler

[Nesne örneklemesi](#BKMK_Object_instantiation)

[Örtülü olarak soyut sınıflar](#BKMK_Implicitly_abstract_classes)

[Tür görünürlüğü](#BKMK_Type_visibility)

[Üye görünürlüğü](#BKMK_Member_visibility)

[Ortak ve özel yerel sınıflar](#BKMK_Public_and_private_native_classes)

[Statik oluşturucular](#BKMK_Static_constructors)

[Bu işaretçinin semantiği](#BKMK_Semantics_of_the_this_pointer)

[İmza gizleme işlevleri](#BKMK_Hide_by_signature_functions)

[Kopya oluşturucular](#BKMK_Copy_constructors)

[Yok ediciler ve sonlandırıcılar](#BKMK_Destructors_and_finalizers)

##  <a name="BKMK_Object_instantiation"></a>Nesne örneklemesi

Başvuru (Ref) türleri, yığın üzerinde veya yerel yığında değil, yalnızca yönetilen yığında oluşturulabilir. Değer türleri, yığında veya yönetilen yığında oluşturulabilir.

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

##  <a name="BKMK_Implicitly_abstract_classes"></a>Örtülü olarak soyut sınıflar

*Örtük olarak soyut bir sınıf* örneği oluşturulamıyor. Sınıfın temel türü bir arabirim ise ve sınıf tüm arabirimin üye işlevlerini gerçekleştirmezse, bir sınıf örtülü olarak soyuttur.

Bir arabirimden türetilmiş bir sınıftan nesneler oluşturmanızın nedeni, sınıfın örtük olarak soyut olması olabilir. Soyut sınıflar hakkında daha fazla bilgi için bkz. [abstract](../extensions/abstract-cpp-component-extensions.md).

Aşağıdaki kod örneği, işlev `MyClass::func2` uygulanamadığı için `MyClass` sınıfının örneklenmediği gösterilmektedir. Derlemek için örneği etkinleştirmek üzere `MyClass::func2`açıklamasını kaldırın.

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

##  <a name="BKMK_Type_visibility"></a>Tür görünürlüğü

Ortak dil çalışma zamanı (CLR) türlerinin görünürlüğünü denetlemek için, bir derlemeye başvuruluyorsa, derlemedeki türlerin, derleme dışında görünür veya görünür hale görünebilmesini sağlayabilirsiniz.

`public`, türü içeren derleme için `#using` yönergesini içeren herhangi bir kaynak dosyasında görünür olduğunu gösterir.  `private`, türü içeren derleme için bir `#using` yönergesi içeren kaynak dosyalara görünür olmadığını gösterir. Ancak, özel türler aynı derleme içinde görünür. Varsayılan olarak, bir sınıfın görünürlüğü `private`.

Varsayılan olarak, Visual Studio 2005 ' den önceki yerel türlerin derleme dışında genel erişilebilirliği vardır. Özel yerel türlerin yanlış kullanıldığını görbaşlamanıza yardımcı olması için [derleyici uyarısını etkinleştirin (düzey 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) . Değiştiremeyeceğiniz bir kaynak kod dosyasında yerel bir türe genel erişilebilirlik sağlamak için [make_public](../preprocessor/make-public.md) pragma kullanın.

Daha fazla bilgi için bkz. [#using yönergesi](../preprocessor/hash-using-directive-cpp.md).

Aşağıdaki örnek, türlerin nasıl bildirilemeyeceğini ve bunların erişilebilirliğini nasıl belirtmekte ve sonra bu türlere derleme içinde nasıl erişmekte olduğunu gösterir. Kuşkusuz, özel türlerine sahip bir derlemeye `#using`kullanılarak başvuruluyorsa, yalnızca derlemedeki ortak türler görünür olur.

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

Şimdi, önceki örneği bir DLL olarak inşa edilecek şekilde yeniden yazalım.

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

Sonraki örnek, derleme dışındaki türlerin nasıl erişebileceğini gösterir. Bu örnekte istemci, önceki örnekte oluşturulan bileşeni kullanır.

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

##  <a name="BKMK_Member_visibility"></a>Üye görünürlüğü

Bir ortak sınıfın bir üyesine, derleme dışından, `public`, `protected`ve `private` erişim Belirticilerinin çiftlerini kullanarak erişimi fark edebilirsiniz.

Bu tablo çeşitli erişim Belirticilerinin etkisini özetler:

|Belirleyici|Etki|
|---------------|------------|
|public|Üyeye derleme içinde ve dışında erişilebilir.  Daha fazla bilgi için bkz. [genel](../cpp/public-cpp.md) .|
|private|Üyeye, derleme içinde veya dışında hiçbir yerde erişilemiyor.  Daha fazla bilgi için bkz. [özel](../cpp/private-cpp.md) .|
|protected|Üyeye, derleme içinde ve dışında erişilebilir, ancak yalnızca türetilmiş türlere erişilebilir.  Daha fazla bilgi için bkz. [korumalı](../cpp/protected-cpp.md) .|
|internal|Üye derleme içinde ortak ve derleme dışında özel.  `internal`, bağlama duyarlı bir anahtar sözcüktür.  Daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](../extensions/context-sensitive-keywords-cpp-component-extensions.md).|
|ortak korumalı veya korumalı genel|Üye, derleme içinde ortak ve derleme dışında korunuyor.|
|özel korumalı veya korumalı özel|Üye derleme içinde korunuyor, ancak derleme dışında özel.|

Aşağıdaki örnek, farklı erişilebilir üyelere sahip ortak bir tür gösterir ve ardından bu üyelerin derlemenin içinden erişimini gösterir.

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

Aşağıdaki örnek, önceki örnekte oluşturulan bileşeni kullanır ve bu nedenle, üyenin derleme dışından nasıl erişebileceğini gösterir.

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

##  <a name="BKMK_Public_and_private_native_classes"></a>Ortak ve özel yerel sınıflar

Bir yerel türe, yönetilen bir türden başvurulabilir.  Örneğin, yönetilen türdeki bir işlev, türü yerel bir struct olan bir parametre alabilir.  Yönetilen tür ve işlev bir derlemede ortak ise, yerel tür de genel olmalıdır.

```cpp
// native type
public struct N {
   N(){}
   int i;
};
```

Sonra, yerel türünü tüketen kaynak kodu dosyasını oluşturun:

```cpp
// compile with: /clr /LD
#include "mcppv2_ref_class3.h"
// public managed type
public ref struct R {
   // public function that takes a native type
   void f(N nn) {}
};
```

Şimdi bir istemci derleyin:

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

##  <a name="BKMK_Static_constructors"></a>Statik oluşturucular

Bir CLR türü — örneğin, bir sınıf veya yapı — statik veri üyelerini başlatmak için kullanılabilen statik bir oluşturucuya sahip olabilir.  Statik bir Oluşturucu en fazla bir kez çağrılır ve türün herhangi bir statik üyesine ilk kez erişilmek için çağırılır.

Örnek Oluşturucu her zaman bir statik oluşturucudan sonra çalışır.

Sınıfta bir statik Oluşturucu varsa derleyici bir oluşturucuya çağrı satır içi olamaz.  Sınıf bir değer türü ise, statik bir oluşturucuya sahiptir ve bir örnek Oluşturucusu yoksa, derleyici herhangi bir üye işlevine bir çağrıyı satır içine alamaz.  CLR çağrıyı satır içine alabilir, ancak derleyici kullanamaz.

Yalnızca CLR tarafından çağrılması amaçlanmış olduğundan, bir statik oluşturucuyu özel üye işlevi olarak tanımlayın.

Statik oluşturucular hakkında daha fazla bilgi için bkz. [nasıl yapılır: Arabirim statik Oluşturucusu (C++/CLI) tanımlama](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) .

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

##  <a name="BKMK_Semantics_of_the_this_pointer"></a>Bu işaretçinin semantiği

Türleri tanımlamak için görsel C++ kullandığınızda, başvuru türündeki `this` işaretçisi "tanıtıcı" türündedir. Değer türündeki `this` işaretçi "iç işaretçi" türündedir.

`this` işaretçisinin bu farklı semantiklerinden biri, varsayılan bir Dizin Oluşturucu çağrıldığında beklenmeyen davranışlara neden olabilir. Sonraki örnekte, bir başvuru türü ve değer türü içinde varsayılan bir dizin oluşturucuya erişmenin doğru yolu gösterilmektedir.

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

##  <a name="BKMK_Hide_by_signature_functions"></a>İmza gizleme işlevleri

Standart C++olarak, bir temel sınıftaki bir işlev türetilmiş sınıfta aynı ada sahip bir işlev tarafından gizlenir, türetilmiş sınıf işlevi aynı sayıda veya türde parametreye sahip olmasa bile. Bu, *ad ile gizleme* semantiği olarak adlandırılır. Bir başvuru türünde, temel sınıftaki bir işlev yalnızca, hem ad hem de parametre listesi aynı ise türetilmiş bir sınıftaki bir işlevle gizlenebilir. Bu, *imza gizleme* semantiği olarak bilinir.

Bir sınıf, tüm işlevleri meta verilerde `hidebysig`olarak işaretlendiğinde, bir gizleme sınıfı olarak değerlendirilir. Varsayılan olarak, **/clr** altında oluşturulan tüm sınıfların `hidebysig` işlevleri vardır. Bir sınıfta `hidebysig` işlevleri olduğunda, derleyici herhangi bir doğrudan temel sınıfta işlevleri ada göre gizlemez, ancak derleyici devralma zincirinde bir gizleme sınıfı ile karşılaştığında, bu, ad ile gizleme davranışına devam eder.

İmza gizleme semantiğinin altında, bir işlev bir nesne üzerinde çağrıldığında, derleyici işlev çağrısını karşılayabilecek bir işlevi içeren en fazla türetilmiş sınıfı tanımlar. Sınıfta çağrıyı karşılayabilecek yalnızca bir işlev varsa, derleyici bu işlevi çağırır. Sınıfta çağrıyı karşılayabilecek birden fazla işlev varsa, derleyici hangi işlevin çağrılacağını belirleyen aşırı yükleme çözümleme kuralları kullanır. Aşırı yükleme kuralları hakkında daha fazla bilgi için bkz. [Işlev aşırı yüklemesi](../cpp/function-overloading.md).

Belirli bir işlev çağrısı için, temel sınıftaki bir işlev, türetilmiş bir sınıftaki bir işlevden biraz daha iyi eşleşme yapan bir imzaya sahip olabilir. Ancak, işlev türetilmiş sınıfın bir nesnesi üzerinde açıkça çağrılırsa, türetilmiş sınıftaki işlev çağrılır.

Dönüş değeri bir işlevin imzasının bir parçası olmadığından, bir temel sınıf işlev aynı ada sahipse ve bir türetilmiş sınıf işleviyle aynı sayıda ve türde bağımsız değişken alırsa, bu değer dönüş değerinin türüne farklı olsa bile gizlenir.

Aşağıdaki örnek, bir temel sınıftaki bir işlevin türetilmiş sınıftaki bir işlevle gizlenmediğini gösterir.

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

Sonraki örnek, Microsoft C++ derleyicisinin, bir veya daha fazla parametre eşleşmesi için bir dönüştürme gerektirse ve işlev çağrısı için daha iyi bir eşleşme olan temel sınıfta bir işlev çağırmasa bile, en türetilmiş sınıfta bir işlevi çağırdığı gösterilmektedir.

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

Aşağıdaki örnek, temel sınıf türetilmiş sınıfla aynı imzaya sahip olsa bile bir işlevin gizlenmesi mümkün olduğunu gösterir.

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

##  <a name="BKMK_Copy_constructors"></a>Kopya oluşturucular

Standart C++ , bir nesne taşındığında bir kopya oluşturucunun, bir nesnenin oluşturulduğu ve aynı adreste yok edileceği şekilde çağrıldığını söyler.

Bununla birlikte, derlemek için **/clr** KULLANıLDıĞıNDA ve MSIL 'ye derlenen bir işlev, yerel bir sınıfın (veya birden fazla) bir kopya Oluşturucusu ve/veya yok edicisi olduğu ve yerel sınıfta bir kopya Oluşturucusu ve/veya yıkıcısı olduğu, bir kopya Oluşturucusu çağrılmadıkça ve nesne oluşturulduğu yerden farklı bir adreste yok edildiğinde, bir yerel işlevi çağırır. Bu, sınıfın kendine işaretçi varsa veya kod nesneleri adrese göre izleirse soruna neden olabilir.

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

Aşağıdaki örnek, bir kopya oluşturucusunun üretildiğini gösterir.

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

##  <a name="BKMK_Destructors_and_finalizers"></a>Yok ediciler ve sonlandırıcılar

Başvuru türündeki Yıkıcılar, kaynakların kararlı bir şekilde temizlenmesini gerçekleştirir. Sonlandırıcılar yönetilmeyen kaynakları temizleyerek yıkıcı veya çöp toplayıcı tarafından belirleyici olmayan şekilde çağrılabilir. Standart C++olan yok ediciler hakkında bilgi için bkz. [Yıkıcılar](../cpp/destructors-cpp.md).

```cpp
class classname {
   ~classname() {}   // destructor
   ! classname() {}   // finalizer
};
```

Yönetilen bir görsel C++ sınıftaki yok edicilerin davranışı Için C++Yönetilen Uzantılardan farklıdır. Bu değişiklik hakkında daha fazla bilgi için bkz. [yıkıcı semantikleri değişiklikler](../dotnet/changes-in-destructor-semantics.md).

CLR atık toplayıcısı kullanılmayan yönetilen nesneleri siler ve artık gerekli olmadığında belleği serbest bırakır. Ancak, bir tür çöp toplayıcısının nasıl yayınlanmayacağını bilemeyen kaynakları kullanabilir. Bu kaynaklar, yönetilmeyen kaynaklar (örneğin, yerel dosya işleyicileri) olarak bilinir. Sonlandırıcıdaki tüm yönetilmeyen kaynakları yayınlanmasını öneririz. Yönetilen kaynaklar çöp toplayıcı tarafından belirleyici olmayan şekilde serbest bırakıldığı için, Atık toplayıcısının o yönetilen kaynağı zaten temizlediğini mümkün olduğu için bir sonlandırıcının yönetilen kaynaklarına başvurmak güvenli değildir.

Görsel C++ Sonlandırıcı <xref:System.Object.Finalize%2A> yöntemiyle aynı değildir. (CLR belgeleri Sonlandırıcı ve <xref:System.Object.Finalize%2A> yöntemi terimler) kullanır. <xref:System.Object.Finalize%2A> yöntemi, bir sınıf devralma zincirindeki her sonlandırıcıyı çağıran çöp toplayıcı tarafından çağırılır. Görsel C++ Yıkıcılardan farklı olarak, türetilmiş sınıf Sonlandırıcı çağrısı derleyicinin tüm temel sınıflarda sonlandırıcıyı çağırmasına neden olmaz.

Microsoft C++ derleyicisi kaynakların kararlı sürümünü desteklediğinden, <xref:System.IDisposable.Dispose%2A> veya <xref:System.Object.Finalize%2A> yöntemleri uygulamayı denemeyin. Bununla birlikte, bu yöntemlerle ilgili bilgi sahibiyseniz, bir görsel C++ sonlandırıcı ve <xref:System.IDisposable.Dispose%2A> deseninin Sonlandırıcı eşlemesini çağıran bir yıkıcıdır:

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

Yönetilen bir tür Ayrıca, belirli bir şekilde serbest bırakmak için tercih ettiğiniz yönetilen kaynakları kullanabilir ve nesne artık gerekli olmadıktan sonra belirleyici olmayan bir noktada serbest bırakmak için çöp toplayıcısına ayrılmayabilir. Kaynakların belirleyici sürümü performansı önemli ölçüde iyileştirebilir.

Microsoft C++ derleyicisi, nesneleri kesin olarak temizlemek için yıkıcının tanımını sağlar. Kesin olarak yayınlamak istediğiniz tüm kaynakları serbest bırakmak için yıkıcıyı kullanın.  Bir Sonlandırıcı varsa, kod çoğaltmasını önlemek için bunu yıkıcıdan çağırın.

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

Türü tüketen kod yıkıcıyı çağırmaz, çöp toplayıcı sonunda tüm yönetilen kaynakları yayınlar.

Yok edicinin varlığı, sonlandırıcının varlığını göstermez. Ancak, sonlandırıcının varlığı, bir yıkıcı tanımlamanız ve bu yıkıcının sonlandırıcısını çağırmanız gerektiğini gösterir. Bu, yönetilmeyen kaynakların belirleyici sürümü için sağlar.

Yok edicinin çağrılması — <xref:System.GC.SuppressFinalize%2A>kullanarak nesnesinin sonlandırılmasını önler. Yıkıcı çağrılmadıysanız, türün Sonlandırıcı sonunda çöp toplayıcı tarafından çağrılır.

Yıkıcının çağırarak nesnenin kaynaklarını kesin bir şekilde temizlemek, CLR 'nin nesneyi belirleyici olmayan şekilde sonlandırmalarına izin vererek performansı iyileştirebilir.

Visual C++ 'te yazılmış ve **/clr** kullanılarak derlenen kod, şu durumlarda bir türün yıkıcısı çalıştırır:

- Yığın semantiği kullanılarak oluşturulan bir nesne kapsam dışına çıkar. Daha fazla bilgi için bkz [ C++ . başvuru türleri için yığın semantiği](../dotnet/cpp-stack-semantics-for-reference-types.md).

- Nesnenin oluşturulması sırasında bir özel durum oluşturuldu.

- Nesnesi, yıkıcısı çalıştıran bir nesne içindeki üyesidir.

- [Delete](../cpp/delete-operator-cpp.md) işlecini bir tanıtıcı üzerinde ([nesne işleci (^) olarak işle](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)) çağırabilirsiniz.

- Yok ediciyi açıkça çağırın.

Eğer tür, başka bir dilde yazılmış bir istemci tarafından tüketiliyorsa, yıkıcı aşağıdaki gibi çağrılır:

- <xref:System.IDisposable.Dispose%2A>çağrısında.

- `Dispose(void)` bir çağrıda yazın.

- Tür bir C# `using` deyimindeki kapsam dışına çıkar.

Yönetilen yığında bir başvuru türünde bir nesne oluşturursanız (başvuru türleri için yığın semantiğini kullanmıyor), bir özel durumun yıkıcının çalışmasını önleyemediğinden emin olmak için [try-finally](../cpp/try-finally-statement.md) söz dizimini kullanın.

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

Eğer tür bir yıkıcı içeriyorsa, derleyici <xref:System.IDisposable>uygulayan bir `Dispose` yöntemi oluşturur. Görselde C++ yazılmış bir tür ve başka bir dilden tüketilen bir yıkıcı varsa, bu tür üzerinde `IDisposable::Dispose` çağrısı, türün yıkıcının çağrılmasına neden olur. Tür bir görsel C++ istemciden tüketildiği zaman, `Dispose`doğrudan çağrılamaz; Bunun yerine, `delete` işlecini kullanarak yıkıcıyı çağırın.

Türünün bir sonlandırıcısı varsa, derleyici <xref:System.Object.Finalize%2A>geçersiz kılan bir `Finalize(void)` yöntemi oluşturur.

Bir türün Sonlandırıcı ya da yok edicisi varsa, derleyici tasarım düzenine göre bir `Dispose(bool)` yöntemi oluşturur. (Bilgi için bkz. [Dispose model](/dotnet/standard/design-guidelines/dispose-pattern)). Visual C++içinde `Dispose(bool)` açıkça yazamaz veya çağrılamaz.

Bir türün tasarım düzenine uygun bir temel sınıfı varsa, türetilmiş sınıf için yıkıcı çağrıldığında tüm temel sınıfların yıkıcıları çağrılır. (Türü görselde C++yazılmışsa, derleyici türlerinizi bu düzenin uygulanmasını sağlar.) Diğer bir deyişle, bir başvuru sınıfının yok edicisi, C++ standart tarafından belirtildiği gibi temellerine ve üyelerine zincirdir — ilk olarak sınıfın yıkıcısı çalıştırılır, daha sonra oluşturuldukları sıranın tersine, üyeleri için yok ediciler ve son olarak oluşturuldukları sıranın tersine, temel sınıfları için Yıkıcılar.

Değer türlerinin veya arabirimlerin içinde yok ediciler ve sonlandırıcılar kullanılamaz.

Sonlandırıcısı yalnızca bir başvuru türünde tanımlanabilir veya bildirilebilecek. Bir Oluşturucu ve yıkıcı gibi, sonlandırıcının dönüş türü yoktur.

Bir nesnenin Sonlandırıcı çalıştıktan sonra, herhangi bir temel sınıfta sonlandırıcılar, en az türetilmiş türle başlayarak de çağrılır. Veri üyeleri için sonlandırıcılar, bir sınıfın sonlandırıcısı tarafından otomatik olarak zincirlenebilir.

Bir Sonlandırıcı yönetilen bir türdeki yerel bir işaretçiyi silerse, yerel işaretçiyle veya bu işaretçiden bu işaretçiye olan başvuruların zamanından önce toplanmadığından emin olmanız gerekir. <xref:System.GC.KeepAlive%2A>kullanmak yerine, yönetilen tür üzerinde yıkıcıyı çağırın.

Derleme zamanında, bir türün Sonlandırıcı veya yıkıcısı olup olmadığını tespit edebilirsiniz. Daha fazla bilgi için bkz. [tür nitelikleri Için derleyici desteği](../extensions/compiler-support-for-type-traits-cpp-component-extensions.md).

Bir sonraki örnek, yönetilmeyen kaynakları olan ve bir yönetilen kaynakları belirleyici olarak yayınlanan iki tür gösterir.

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
