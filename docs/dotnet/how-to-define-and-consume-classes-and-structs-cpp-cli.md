---
title: 'Nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 26e3d1c0a102eda66ced6902a47a97782b3e1e64
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420797"
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>Nasıl yapılır: Sınıfları ve Yapıları Tanımlama ve Kullanma (C++/CLI)

Bu makalede, kullanıcı tarafından tanımlanan başvuru türleri ve değer türleri C + tanımlama ve kullanma işlemi gösterilmektedir +/ CLI.

##  <a name="BKMK_Contents"></a> İçeriği

[Nesne örneklemesini](#BKMK_Object_instantiation)

[Örtük olarak soyut sınıflar](#BKMK_Implicitly_abstract_classes)

[Tür görünürlüğü](#BKMK_Type_visibility)

[Üye görünürlüğü](#BKMK_Member_visibility)

[Genel ve özel yerel sınıflar](#BKMK_Public_and_private_native_classes)

[Statik oluşturucular](#BKMK_Static_constructors)

[Bu semantiği işaretçi](#BKMK_Semantics_of_the_this_pointer)

[İmzaya göre Gizle işlevleri](#BKMK_Hide_by_signature_functions)

[Kopya oluşturucuları](#BKMK_Copy_constructors)

[Yok ediciler ve sonlandırıcılar](#BKMK_Destructors_and_finalizers)

##  <a name="BKMK_Object_instantiation"></a> Nesne örneklemesini

Yönetilen yığın, yığın üzerinde değil veya yerel yığında başvuru (ref) türleri yalnızca oluşturulabilir. Değer türleri, yığın veya yönetilen yığın üzerinde oluşturulabilir.

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

##  <a name="BKMK_Implicitly_abstract_classes"></a> Örtük olarak soyut sınıflar

Bir *örtük olarak soyut sınıf* örneği oluşturulamıyor. Bir sınıfın temel türü bir arabirim ve sınıfın tüm üye işlevleri arabirimin uygulamıyor örtük olarak soyut sınıftır.

Bir arabirimden türetilmiş bir sınıftan nesneleri oluşturmak bulamıyorsanız, örtük olarak soyut sınıf olduğunu neden olabilir. Soyut sınıflar hakkında daha fazla bilgi için bkz: [soyut](../windows/abstract-cpp-component-extensions.md).

Aşağıdaki kod örneği gösteren `MyClass` çünkü sınıfı'nin başlatılamaz olamaz işlevi `MyClass::func2` uygulanmadı. Derlemek örnek etkinleştirmek için açıklama durumundan çıkarın `MyClass::func2`.

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

##  <a name="BKMK_Type_visibility"></a> Tür görünürlüğü

Bir derlemeye başvurulduğundan, bütünleştirilmiş kodundaki türler görünür veya derlemenin dışında görünür olmasını, ortak dil çalışma zamanı (CLR) türleri görünürlüğünü denetleyebilir.

`public` bir türü içeren dilediğiniz kaynak dosyaya görünür olduğunu belirten bir `#using` türü içeren derleme için yönerge.  `private` bir türü içeren kaynak dosyalarını görünür olmadığını belirten bir `#using` türü içeren derleme için yönerge. Ancak, özel türleri aynı derleme içinde görünür. Varsayılan olarak, bir sınıf için görünürlük olan `private`.

Visual C++ 2005 önce varsayılan olarak, yerel türlerde ortak erişilebilirlik derleme dışından vardı. Etkinleştirme [Derleyici Uyarısı (düzey 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) özel yerel türler yanlış kullanıldığı görmenize yardımcı olmak için. Kullanım [make_public](../preprocessor/make-public.md) değiştiremediğiniz bir kaynak kod dosyasında yerel bir tür için ortak erişilebilirlik verilecek pragması.

Daha fazla bilgi için [#using yönergesi](../preprocessor/hash-using-directive-cpp.md).

Aşağıdaki örnek türleri bildirme ve bunların erişilebilirlik belirtin ve ardından derlemenin iç türlerine erişmek nasıl gösterir. Elbette kullanarak özel türler sahip derlemeye başvuruluyorsa `#using`, yalnızca derlemenin genel türlerindeki görülebilir.

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

**Output**

```Output
in Public_Class
in Private_Class
in Private_Class_2
```

Şimdi, DLL olarak oluşturulmuştur, önceki örnek şimdi yeniden yazın.

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

Sonraki örnek, derleme dışından türleri nasıl gösterir. Bu örnekte, önceki örnekte oluşturulan bileşeni istemcisi kullanır.

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

**Output**

```Output
in Public_Class
```

##  <a name="BKMK_Member_visibility"></a> Üye görünürlüğü

Erişim aynı bütünleştirilmiş kod içinde bir ortak sınıf üyesine farklı erişim içinden derleme dışından erişim belirticileri çiftlerini kullanarak yapabileceğiniz `public`, `protected`, ve `private`

Bu tabloda, çeşitli erişim belirticileri etkisini özetlenmektedir:

|Belirleyici|Efekt|
|---------------|------------|
|public|Üye, iç ve derleme dışından erişilebilir.  Bkz: [genel](../cpp/public-cpp.md) daha fazla bilgi için.|
|private|Üye içinde ne derleme dışından erişilebilir değil.  Bkz: [özel](../cpp/private-cpp.md) daha fazla bilgi için.|
|protected|Üye ve derleme dışından, ancak yalnızca türetilmiş türleri içinde erişilebilir.  Bkz: [korumalı](../cpp/protected-cpp.md) daha fazla bilgi için.|
|internal|Derleme içinde geneldir ancak özel derleme dışından üyesidir.  `internal` bağlama duyarlı bir anahtar sözcüktür.  Daha fazla bilgi için [Context-Sensitive Keywords](../windows/context-sensitive-keywords-cpp-component-extensions.md).|
|Genel korumalı - veya - korumalı ortak|Derleme içinde geneldir ancak derleme dışından korumalı üyesidir.|
|Özel korumalı - veya - korumalı özel|Derleme içinde korumalı ancak özel derleme dışından üyesidir.|

Aşağıdaki örnek, farklı erişilebilirlikleri ile bildirilen bir üyesi olan bir genel türü gösterir ve daha sonra bu üyeleri derleme erişme gösterir.

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

**Output**

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

Artık bir DLL olarak önceki örnek oluşturalım.

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

Aşağıdaki örnek, önceki örnekte oluşturulur ve gösterilir böylece üyelerinden derleme dışından erişim bileşeni kullanır.

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

**Output**

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

##  <a name="BKMK_Public_and_private_native_classes"></a> Genel ve özel yerel sınıflar

Yerel bir tür, yönetilen bir türden başvurulabilir.  Örneğin, bir yönetilen türün bir işlevde yerel bir yapı türü olan bir parametre alabilir.  Yönetilen tür ve işlevi bir derlemede genel ise, ardından yerel ayrıca genel türünde olmalıdır.

```cpp
// native type
public struct N {
   N(){}
   int i;
};
```

Ardından, yerel bir tür kullanan kaynak kodu dosyası oluşturun:

```cpp
// compile with: /clr /LD
#include "mcppv2_ref_class3.h"
// public managed type
public ref struct R {
   // public function that takes a native type
   void f(N nn) {}
};
```

Artık, bir istemci derleme:

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

##  <a name="BKMK_Static_constructors"></a> Statik oluşturucular

Bir CLR türü — örneğin, bir sınıf veya yapı — statik veri üyeleri başlatmak için kullanılan bir statik Oluşturucu olabilir.  Statik Oluşturucu, en fazla bir kez çağrılır ve herhangi bir statik üye türü ilk kez erişmeden önce çağrılır.

Bir örnek oluşturucusunda bir statik Oluşturucu sonra her zaman çalışır.

Sınıfı statik Oluşturucusu varsa derleyici satır içi oluşturucu çağrısı olamaz.  Sınıfı bir değer türü, bir statik Oluşturucusu vardır ve bir örnek oluşturucusu yok derleyicinin satır içi herhangi bir üye işlevine bir çağrı yapılamıyor.  Satır içi arama CLR olabilir, ancak derleyicinin olamaz.

Yalnızca CLR tarafından çağrılacak anlamına geldiğinden statik Oluşturucu bir özel üye işlevi tanımlar.

Statik oluşturucular hakkında daha fazla bilgi için bkz: [nasıl yapılır: Arabirim statik oluşturucusunu tanımlama (C + +/ CLI)](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) .

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

**Output**

```Output
in static constructor
10
11
```

##  <a name="BKMK_Semantics_of_the_this_pointer"></a> Bu semantiği işaretçi

Türleri tanımlamak için Visual C++ kullanırken `this` işaretçisidir bir başvuru türü olarak "tanıtıcısı" tür. `this` İşaretçisidir bir değer türü olarak "işaretçiye" tür.

Bu farklı semantikleri `this` varsayılan dizin oluşturucu çağrıldığında, işaretçi beklenmeyen davranışlara neden olabilir. Sonraki örnek, bir başvuru türü hem de bir değer türü varsayılan bir oluşturucuda erişmek için doğru şekilde gösterir.

Daha fazla bilgi için bkz.

- [İşlenecek nesne işleci (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)

- [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)

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

**Output**

```Output
10.89
10.89
```

##  <a name="BKMK_Hide_by_signature_functions"></a> İmzaya göre Gizle işlevleri

Türetilmiş sınıf işlevi aynı sayıda veya tür parametreleri yok bile standard C++ içinde taban sınıfında bir işlev türetilmiş bir sınıf içinde aynı ada sahip bir işlev tarafından gizlenir. Bu olarak adlandırılır *ada göre Gizle* semantiği. Hem adı hem de parametre listesi aynıysa, bir başvuru türünün bir temel sınıfta bir işlev yalnızca türetilen bir sınıfta bir işleve göre gizlenebilir. Bu olarak bilinir *imzaya göre Gizle* semantiği.

Tüm işlevlerini meta verilerinde ' işaretlenmiş bir sınıf bir imzaya göre Gizle sınıf olarak kabul edilir `hidebysig`. Varsayılan olarak, altında oluşturulan tüm sınıflar **/CLR** sahip `hidebysig` işlevleri. Bir sınıf olduğunda `hidebysig` İşlevler, derleyici değil Gizle işlevleri herhangi bir doğrudan temel sınıf adı, ancak derleyici, bir devralma zincirini ada göre Gizle sınıfında karşılaşılırsa, bu ada göre Gizle davranışı devam eder.

Bir nesne üzerinde bir işlev çağrıldığında imzaya göre Gizle semantiği altında derleyici işlev çağrısı karşılayan bir işlevi içeren en çok türetilen sınıf tanımlar. Çağrı karşılayan sınıfta yalnızca bir işlev ise, derleyici bu işlevi çağırır. Çağrı karşılayan sınıfta birden fazla işlevi varsa, derleyici kullandığı çözümleme kurallarını, hangi işlevi çağırmak için belirlemek için aşırı yükleme. Aşırı yükleme kuralları hakkında daha fazla bilgi için bkz. [işlev aşırı yüklemesi](../cpp/function-overloading.md).

Verilen işlevi çağrısı, bir işlevde bir temel sınıf, türetilen bir sınıfta bir işlevi daha biraz daha iyi bir eşleşme sunan bir imza olabilir. Ancak, işlevi açıkça türetilmiş sınıfın bir nesnede çağrıldı, türetilmiş sınıf içinde işlev çağrılır.

Dönüş değeri işlevin imzasının parçası olarak kabul edilmez olduğundan, aynı ada sahip ve bir türetilmiş sınıf işlevi aynı sayıda ve türde bağımsız değişkenleri alır dönüş değerinin türü farklı olsa bile bir temel sınıf işlev gizlenir.

Aşağıdaki örnek, bir temel sınıfta bir işlev türetilen bir sınıfta bir işleve göre gizli olmayan gösterir.

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

**Output**

```Output
Base::Test
```

Sonraki örnek, Visual C++ Derleyici en çok türetilen sınıfta bir işlev çağırır gösterir; bir veya daha fazla parametre eşleştirmek için bir dönüştürme gerekli olsa bile — ve daha iyi bir eşleşme işlev çağrısı için bir temel sınıfı bir işlevi çağırmayı değil.

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

**Output**

```Output
Derived::Test2
```

Aşağıdaki örnek, temel sınıfın türetilmiş sınıf aynı imzaya sahip olsa bile bir işlev gizlenecek mümkün olduğunu gösterir.

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

**Output**

```Output
Derived::Test4
97
```

##  <a name="BKMK_Copy_constructors"></a> Kopya oluşturucuları

C++ Standart ifadesini içeren bir nesne taşındığında bir nesne oluşturulur ve aynı adresindeki yok şekilde bir kopya Oluşturucu çağrılır.

Ancak, **/CLR** derleme ve yerel bir işlev bir yerel sınıf burada MSIL çağrıları için derlenmiş bir işlev kullanılır — ya da birden fazla — değeri ve yerel sınıf sahip olduğu bir kopya oluşturucu ve/veya yok edici, bir kopya tarafından geçirilir. Oluşturucu çağrılır ve nesne oluşturulduğu yere göre farklı bir adresten yok. Sınıfın içine kendisi bir işaretçi varsa ya da kod adresine göre izleme nesneleri bu sorunlara neden olabilir.

Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

Aşağıdaki örnek, bir kopya Oluşturucu oluşturulmuyor gösterir.

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

**Output**

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

##  <a name="BKMK_Destructors_and_finalizers"></a> Yok ediciler ve sonlandırıcılar

Bir başvuru türü içinde yok ediciler bir belirleyici temizleme kaynakların gerçekleştirin. Sonlandırıcılar yönetilmeyen kaynakları temizlemek ve yok edici veya belirleyici olmayan şekilde çöp toplayıcı tarafından belirleyici çağrılabilir. Standart c++ yıkıcıları hakkında daha fazla bilgi için bkz. [yok ediciler](../cpp/destructors-cpp.md).

```cpp
class classname {
   ~classname() {}   // destructor
   ! classname() {}   // finalizer
};
```

Yönetilen bir Visual C++ sınıf yıkıcılarda davranışını C++ için Yönetilen Uzantılar'dan farklıdır. Bu değişiklik hakkında daha fazla bilgi için bkz. [yok edici anlamlarında yapılan değişiklikler](../dotnet/changes-in-destructor-semantics.md).

CLR çöp toplayıcısı kullanılmayan yönetilen nesneleri siler ve artık gerekmiyorsa, belleği serbest bırakır. Ancak, bir tür çöp toplayıcı, serbest bırakma bilmez kaynakları kullanabilir. Yönetilmeyen kaynaklar olarak bilinen bu kaynaklar (yerel dosya işleme, örneğin). Sonlandırıcı tüm yönetilmeyen kaynakları serbest bırakmak öneririz. Yönetilen kaynaklar çöp toplayıcı tarafından belirleyici olmayan şekilde serbest olduğundan mümkün olduğundan bir sonlandırıcı yönetilen kaynaklarını atık toplayıcı yönetilen bu kaynağı zaten temizledi başvurmak güvenli değildir.

Visual C++ sonlandırıcıda aynı değil <xref:System.Object.Finalize%2A> yöntemi. (CLR belgeleri Sonlandırıcı kullanır ve <xref:System.Object.Finalize%2A> yöntemi maliyetle aynı anlamda). <xref:System.Object.Finalize%2A> Yöntemi çağıran bir sınıf devralma zincirinde her Sonlandırıcı çöp toplayıcı tarafından çağrılır. Visual C++ yıkıcıları, tüm temel sınıflar, sonlandırıcı çağırmak derleyicinin bir türetilen sınıf Sonlandırıcı çağrı neden olmaz.

Visual C++ derleyicisi, kaynakların belirli şekilde serbest desteklediğinden, uygulamak çalışmayın <xref:System.IDisposable.Dispose%2A> veya <xref:System.Object.Finalize%2A> yöntemleri. Ancak, bu yöntemlerle ilgili bilgi sahibi değilseniz, işte için Visual C++ sonlandırıcıda ve sonlandırıcı çağıran bir yıkıcı nasıl eşleştiği <xref:System.IDisposable.Dispose%2A> Desen:

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

Yönetilen bir tür belirleyici sürüm ve nesne artık gerekli değil sonra belirli bir noktada belirleyici olmayan şekilde serbest bırakmak için çöp toplayıcı bırakmamaya tercih yönetilen kaynaklar olarak da kullanabilirsiniz. Kaynakların belirli şekilde serbest bırakılmasını performansını önemli ölçüde artırabilir.

Visual C++ derleyicisi, belirleyici nesneleri temizlemek için bir yok edici tanımını sağlar. Yok edici belirleyici serbest bırakmak istediğiniz tüm kaynakları serbest bırakmak için kullanın.  Bir sonlandırıcı varsa, kod yinelemesinden kaçınmak için yok edici çağırın.

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

Yok edici, türü tüketen kod çağırmaz, çöp toplayıcı sonunda tüm yönetilen kaynakları serbest bırakır.

Varlığı bir yok edici, bir sonlandırıcı varlığını göstermez. Ancak, bir sonlandırıcı varlığını bir yok ediciyi tanımlayın ve bu yıkıcıdan Sonlandırıcı çağrısı anlamına gelir. Bu, yönetilmeyen kaynakların belirli şekilde serbest için sağlar.

Yok edici çağırma bastırır — kullanarak <xref:System.GC.SuppressFinalize%2A>— sonlandırma nesne. Yok Edicisi çağrılır değil ise, türün Sonlandırıcısı çöp toplayıcı tarafından sonunda çağrılır.

Belirleyici yok Edicisi çağırarak nesnenizin kaynakları temizleme nesne belirleyici olmayan şekilde sonlandırma CLR izin vererek ile karşılaştırıldığında performansı artırabilir.

Visual C++ programında yazılan ve kullanarak derlenmiş kod **/CLR** türün yok Edicisi çalışır:

- Yığın anlamları kullanılarak oluşturulan bir nesne kapsam dışına gider. Daha fazla bilgi için [başvuru türleri için C++ yığın anlamları](../dotnet/cpp-stack-semantics-for-reference-types.md).

- Nesne oluşturma sırasında bir özel durum oluşturulur.

- Nesne, yok Edicisi çalıştıran bir nesne içindeki üyeye ' dir.

- Çağırmanızı [Sil](../cpp/delete-operator-cpp.md) bir tanıtıcı işlecinin ([işlemek nesne işleci (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)).

- Yok ediciyi açıkça çağırmak.

Türünüz başka bir dilde yazılmış bir istemci tarafından Tüketilmekte olan, yok Edicisi şu şekilde adlandırılır:

- Çağırması <xref:System.IDisposable.Dispose%2A>.

- Çağırması `Dispose(void)` türü.

- Tür C# kapsam dışına gider, `using` deyimi.

(Başvuru türleri için yığın anlamları kullanmayan) yönetilen yığında başvuru türünde bir nesne oluşturursanız, kullanın [try-finally](../cpp/try-finally-statement.md) bir özel durum yok Edicisi çalışmasını engellemez emin olmak için söz dizimi.

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

Türünüzün bir yok Edicisi varsa, derleyici oluşturur bir `Dispose` uygulayan yöntemi <xref:System.IDisposable>. Visual C++ programında yazılan ve başka bir dilden kullanılan bir yok Edicisi olan bir tür, çağırma `IDisposable::Dispose` o türde çağrılacak türün yok Edicisi neden olur. Visual C++ istemciden türü kullanıldığında, doğrudan çağıramazsınız `Dispose`; bunun yerine, yok edici kullanarak çağırma `delete` işleci.

Türünüzün bir sonlandırıcı varsa, derleyici oluşturur bir `Finalize(void)` geçersiz kılan yöntemi <xref:System.Object.Finalize%2A>.

Bir tür, bir sonlandırıcı ya da bir yok Edicisi varsa, derleyici oluşturur bir `Dispose(bool)` tasarım deseni göre yöntemi. (Bilgi için [Dispose deseni](/dotnet/standard/design-guidelines/dispose-pattern)). Açıkça Yazar arayın veya silemeyeceğiniz `Dispose(bool)` Visual C++'ta.

Bir tasarım desenine uyduğunu temel bir sınıf türündeyse, türetilmiş sınıf için yok edici çağrıldığında tüm temel sınıflar için Yıkıcılar çağrılır. (Visual c++'ta türünüz yazılmışsa, derleyici türlerinizi bu düzeni uygulama sağlar.) Bir başvuru sınıfının yıkıcısı kendi tabanları ve üyeleri C++ standardı tarafından belirtilen diğer bir deyişle, zincirine bağlı — sınıfın yok Edicisi olan çalıştırın ve ardından, bunlar yapılmış, siparişin ters üyeleri için Yıkıcılar ilk ve son olarak oluşturulmuş siparişin ters kendi temel sınıflar için Yıkıcılar.

Yok ediciler ve sonlandırıcılar değer türleri veya arabirimleri içinde izin verilmiyor.

Bir sonlandırıcı yalnızca tanımlanan veya bir başvuru türü bildirilmiş. Bir oluşturucunun ve yıkıcının gibi bir sonlandırıcı yok dönüş türüne sahip.

Bir nesnenin Sonlandırıcısı çalıştırıldıktan sonra tüm temel sınıflar, bir sonlandırıcı Ayrıca, en az türetilen tür ile başlayan çağrılır. Sonlandırıcılar veri üyeleri için otomatik olarak için bir sınıfın Sonlandırıcı tarafından zincirlendiği değil.

Bir sonlandırıcı yönetilen bir tür içinde yerel bir işaretçi silerse, başvurular için veya yerel işaretçisi aracılığıyla zamanından önce toplanmaz emin olmanız gerekir; call yok Edicisi kullanmak yerine yönetilen türü <xref:System.GC.KeepAlive%2A>.

Derleme zamanında bir sonlandırıcı ya da bir yok edici bir tür olup olmadığını tespit edebilirsiniz. Daha fazla bilgi için [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

Sonraki örnek, iki tür, yönetilmeyen kaynaklar içeren diğeri belirleyici yayımlanan kaynakları yönetilen olan gösterir.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)
