---
title: 'Nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C++/CLı)'
description: C++/CLı kodunda Kullanıcı tanımlı sınıf ve yapı türleri oluşturma ve kullanma.
ms.date: 09/25/2020
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
ms.openlocfilehash: 17d0885d42febc1d2789c8711b54a76066ee8176
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414587"
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>Nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C++/CLı)

Bu makalede, C++/CLI'DE Kullanıcı tanımlı başvuru türlerinin ve değer türlerinin nasıl tanımlanacağı ve kullanılacağı gösterilir.

## <a name="object-instantiation"></a><a name="BKMK_Object_instantiation"></a> Nesne örneklemesi

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

## <a name="implicitly-abstract-classes"></a><a name="BKMK_Implicitly_abstract_classes"></a> Örtülü olarak soyut sınıflar

*Örtük olarak soyut bir sınıf* örneği oluşturulamıyor. Bir sınıf şu durumlarda örtülü soyuttur:

- sınıfın temel türü bir arabirimdir ve
- sınıfı, tüm arabirimin üye işlevlerini uygulamaz.

Bir arabirimden türetilmiş bir sınıftan nesneler oluşturmeyebilirsiniz. Bunun nedeni, sınıfın örtük olarak soyut olması olabilir. Soyut sınıflar hakkında daha fazla bilgi için bkz. [abstract](../extensions/abstract-cpp-component-extensions.md).

Aşağıdaki kod örneği, `MyClass` işlev uygulanamadığı için sınıfın örneklenemez olduğunu gösterir `MyClass::func2` . Derlemek için örneği etkinleştirmek üzere, açıklamasını kaldırın `MyClass::func2` .

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

## <a name="type-visibility"></a><a name="BKMK_Type_visibility"></a> Tür görünürlüğü

Ortak dil çalışma zamanı (CLR) türlerinin görünürlüğünü kontrol edebilirsiniz. Derlemenizin başvurduğu zaman, derlemedeki türlerin görünür olup olmadığını ve derleme dışında görünüp görünmediğini kontrol edersiniz.

`public` bir türün `#using` türü içeren derleme için bir yönerge içeren herhangi bir kaynak dosyaya görünür olduğunu gösterir.  `private` bir türün `#using` türü içeren derleme için bir yönerge içeren kaynak dosyalara görünür olmadığını gösterir. Ancak, özel türler aynı derleme içinde görünür. Varsayılan olarak, bir sınıfın görünürlüğü `private` .

Varsayılan olarak, Visual Studio 2005 ' den önce yerel türlerin derleme dışında genel erişilebilirliği vardır. Özel yerel türlerin yanlış kullanıldığını görbaşlamanıza yardımcı olması için [derleyici uyarısını etkinleştirin (düzey 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) . Değiştiremeyeceğiniz bir kaynak kod dosyasında yerel bir türe genel erişilebilirlik sağlamak için [make_public](../preprocessor/make-public.md) pragma kullanın.

Daha fazla bilgi için bkz. [#using yönergesi](../preprocessor/hash-using-directive-cpp.md).

Aşağıdaki örnek, türlerin nasıl bildirilemeyeceğini ve bunların erişilebilirliğini nasıl belirtmekte ve sonra bu türlere derleme içinde nasıl erişmekte olduğunu gösterir. Özel türlerine sahip bir derlemeye kullanılarak başvuruluyorsa `#using` , yalnızca derlemedeki ortak türler görünür olur.

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

## <a name="member-visibility"></a><a name="BKMK_Member_visibility"></a> Üye görünürlüğü

Erişim Belirticilerinin çiftlerini kullanarak, bir ortak sınıfın bir üyesine, derlemenin dışından farklı bir şekilde erişim sağlayabilirsiniz, **`public`** **`protected`** ve **`private`**

Bu tablo çeşitli erişim Belirticilerinin etkisini özetler:

|Belirleyici|Etki|
|---------------|------------|
|`public`|Üyeye derleme içinde ve dışında erişilebilir. Daha fazla bilgi için bkz. [`public`](../cpp/public-cpp.md).|
|`private`|Üyeye, derleme içinde ve dışında erişilemez.  Daha fazla bilgi için bkz. [`private`](../cpp/private-cpp.md).|
|`protected`|Üyeye, derleme içinde ve dışında erişilebilir, ancak yalnızca türetilmiş türlere erişilebilir. Daha fazla bilgi için bkz. [`protected`](../cpp/protected-cpp.md).|
|`internal`|Üye derleme içinde ortak ve derleme dışında özel. `internal` bağlama duyarlı bir anahtar sözcüktür.  Daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](../extensions/context-sensitive-keywords-cpp-component-extensions.md).|
|`public protected` veya `protected public`|Üye, derleme içinde ortak ve derleme dışında korunuyor.|
|`private protected` veya `protected private`|Üye derleme içinde korunuyor, ancak derleme dışında özel.|

Aşağıdaki örnek, farklı erişim belirticileri kullanılarak tanımlanmış üyelere sahip ortak bir türü gösterir. Ardından, derleme içinden bu üyelere erişimi gösterir.

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

Aşağıdaki örnek, önceki örnekte oluşturulan bileşeni kullanır. Üyenin, derlemenin dışından nasıl erişebileceğini gösterir.

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

## <a name="public-and-private-native-classes"></a><a name="BKMK_Public_and_private_native_classes"></a> Ortak ve özel yerel sınıflar

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

## <a name="static-constructors"></a><a name="BKMK_Static_constructors"></a> Statik oluşturucular

Bir CLR türü — örneğin, bir sınıf veya yapı — statik veri üyelerini başlatmak için kullanılabilen statik bir oluşturucuya sahip olabilir.  Statik bir Oluşturucu en fazla bir kez çağrılır ve türün herhangi bir statik üyesine ilk kez erişilmek için çağırılır.

Örnek Oluşturucu her zaman bir statik oluşturucudan sonra çalışır.

Sınıfta bir statik Oluşturucu varsa derleyici bir oluşturucuya çağrı satır içi olarak ayarlanamaz. Sınıf bir değer türü ise, statik bir oluşturucuya sahiptir ve örnek Oluşturucusu yoksa, derleyici herhangi bir üye işlevine bir çağrıyı satır içine almaz. CLR çağrıyı satır içine alabilir, ancak derleyici olamaz.

Yalnızca CLR tarafından çağrılması amaçlanmış olduğundan, bir statik oluşturucuyu özel üye işlevi olarak tanımlayın.

Statik oluşturucular hakkında daha fazla bilgi için bkz. [nasıl yapılır: Arabirim statik Oluşturucusu tanımlama (C++/CLI)](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) .

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

## <a name="semantics-of-the-this-pointer"></a><a name="BKMK_Semantics_of_the_this_pointer"></a>`this`İşaretçinin semantiği

Tür tanımlamak için C++ \CLı kullandığınızda, **`this`** başvuru türündeki işaretçi *tanıtıcı*türtürdür. **`this`** Değer türündeki işaretçi *iç işaretçisidir*.

**`this`** Varsayılan bir Dizin Oluşturucu çağrıldığında işaretçinin bu farklı semantiklerinden beklenmedik davranışa neden olabilir. Sonraki örnekte, bir başvuru türü ve değer türü içinde varsayılan bir dizin oluşturucuya erişmenin doğru yolu gösterilmektedir.

Daha fazla bilgi için bkz. [işleme Için nesne işleci (^)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) ve [interior_ptr (C++/CLI)](../extensions/interior-ptr-cpp-cli.md)

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

## <a name="hide-by-signature-functions"></a><a name="BKMK_Hide_by_signature_functions"></a> İmza gizleme işlevleri

Standart C++ ' da, türetilmiş sınıf işlevi aynı türe veya parametre sayısına sahip olmasa bile, temel sınıftaki bir işlev türetilmiş sınıfta aynı ada sahip bir işlev tarafından gizlenir. Bu, *ad gizleme* semantiği olarak bilinir. Bir başvuru türünde, temel sınıftaki bir işlev yalnızca, hem ad hem de parametre listesi aynı ise türetilmiş bir sınıftaki bir işlev tarafından gizlenir. *İmza gizleme* semantiği olarak bilinir.

Bir sınıf, tüm işlevleri meta verilerde olarak işaretlendiğinde, bir gizleme sınıfı olarak değerlendirilir `hidebysig` . Varsayılan olarak, altında oluşturulan tüm sınıfların **`/clr`** `hidebysig` işlevleri vardır. Bir sınıfın işlevleri olduğunda `hidebysig` , derleyici herhangi bir doğrudan temel sınıfta işlevleri ada göre gizlemez, ancak derleyici devralma zincirinde bir gizleme sınıfı ile karşılaştığında, bu durum, bu yana gizleme davranışına devam eder.

İmza gizleme semantiğinin altında, bir işlev bir nesne üzerinde çağrıldığında, derleyici işlev çağrısını karşılayabilecek bir işlevi içeren en fazla türetilmiş sınıfı tanımlar. Yalnızca çağrıyı karşılayan sınıfta tek bir işlev varsa, derleyici bu işlevi çağırır. Sınıfta çağrıyı karşılayabilecek birden fazla işlev varsa, derleyici hangi işlevin çağrılacağını belirleyen aşırı yükleme çözümleme kuralları kullanır. Aşırı yükleme kuralları hakkında daha fazla bilgi için bkz. [Işlev aşırı yüklemesi](../cpp/function-overloading.md).

Belirli bir işlev çağrısı için, temel sınıftaki bir işlev, türetilmiş bir sınıftaki bir işlevden biraz daha iyi eşleşme yapan bir imzaya sahip olabilir. Ancak, işlev türetilmiş sınıfın bir nesnesi üzerinde açıkça çağrılırsa, türetilmiş sınıftaki işlev çağrılır.

Dönüş değeri bir işlevin imzasının bir parçası olmadığı için, aynı ada sahip olması ve dönüş değerinin türüne farklı olsa da, türetilmiş sınıf işlevi olarak aynı türü ve sayıda bağımsız değişkeni alırsa, temel sınıf işlev gizli alır.

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

Sonraki örnek, Microsoft C++ derleyicisinin bir veya daha fazla parametre eşleşmesi için gerekli olsa bile, bir işlevin bir veya daha fazlasını eşleştirmek için gereklidir ve işlev çağrısı için daha iyi bir eşleşme olan temel sınıfta bir işlevi çağırmayın.

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

## <a name="copy-constructors"></a><a name="BKMK_Copy_constructors"></a> Kopya oluşturucular

C++ standardı, bir nesne taşındığında bir kopya oluşturucusunun, bir nesnenin oluşturulduğu ve aynı adreste yok edileceği şekilde çağrıldığını söyler.

Ancak, MSIL 'ye derlenen bir işlev, yerel bir sınıfın (veya birden fazla) bir değere göre geçirilir ve yerel sınıfta bir kopya Oluşturucusu ya da yıkıcı varsa, hiçbir kopya Oluşturucu çağrılmaz ve nesne oluşturulduğu yerden farklı bir adreste yok edilir. Bu davranış, sınıfın kendine işaretçi varsa veya kod nesneleri adrese göre izleirse soruna neden olabilir.

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

Aşağıdaki örnek, bir kopya oluşturucunun ne zaman oluşturuldığının gösterir.

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

## <a name="destructors-and-finalizers"></a><a name="BKMK_Destructors_and_finalizers"></a> Yok ediciler ve sonlandırıcılar

Başvuru türündeki Yıkıcılar, kaynakların kararlı bir şekilde temizlenmesini ister. Sonlandırıcılar yönetilmeyen kaynakları temizleyerek yıkıcı veya çöp toplayıcı tarafından belirleyici olmayan şekilde çağrılabilir. Standart C++ ' ta yok ediciler hakkında bilgi için bkz. [Yıkıcılar](../cpp/destructors-cpp.md).

```cpp
class classname {
   ~classname() {}   // destructor
   ! classname() {}   // finalizer
};
```

CLR atık toplayıcısı kullanılmayan yönetilen nesneleri siler ve artık gerekli olmadığında belleği serbest bırakır. Ancak, bir tür çöp toplayıcısının nasıl serbest yapılacağını bilemeyen kaynakları kullanabilir. Bu kaynaklar, *yönetilmeyen* kaynaklar (örneğin, yerel dosya işleyicileri) olarak bilinir. Sonlandırıcının tüm yönetilmeyen kaynaklarını yayınlanmasını öneririz. Çöp toplayıcı yönetilen kaynakları belirleyici olmayan şekilde yayımlar, bu nedenle bir sonlandırıcının yönetilen kaynaklarına başvurmak güvenli değildir. Bunun nedeni, çöp toplayıcısının zaten temizlenmiş olması olabilir.

Visual C++ sonlandırıcısı, yöntemiyle aynı değildir <xref:System.Object.Finalize%2A> . (CLR belgeleri Sonlandırıcı ve <xref:System.Object.Finalize%2A> terimler yöntemini kullanır). <xref:System.Object.Finalize%2A>Yöntemi, bir sınıf devralma zincirindeki her sonlandırıcıyı çağıran çöp toplayıcı tarafından çağırılır. Visual C++ yıkıcılarından farklı olarak, türetilmiş sınıf Sonlandırıcı çağrısı derleyicinin tüm temel sınıflarda sonlandırıcıyı çağırmasına neden olmaz.

Microsoft C++ derleyicisi kaynakların kararlı sürümünü desteklediğinden, veya yöntemlerini uygulamayı denemeyin <xref:System.IDisposable.Dispose%2A> <xref:System.Object.Finalize%2A> . Ancak, bu yöntemlerle ilgili bilgi sahibiyseniz, bir Visual C++ sonlandırıcısı ve bu modele Sonlandırıcı eşlemesini çağıran yok ediciyi aşağıda görebilirsiniz <xref:System.IDisposable.Dispose%2A> :

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

Yönetilen bir tür, belirli bir şekilde serbest bırakmayı tercih ettiğiniz yönetilen kaynakları da kullanabilir. Çöp toplayıcısının bir nesneyi, nesne artık gerekli olmadığında bir noktada belirleyici olmayan bir şekilde serbest bırakmamasıyla istemeyebilirsiniz. Kaynakların belirleyici sürümü performansı önemli ölçüde iyileştirebilir.

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

Yazdığınız kod yıkıcıyı çağırmazsa, çöp toplayıcı sonunda tüm yönetilen kaynakları yayınlar.

Yıkıcının varlığı, sonlandırıcının varlığını göstermez. Ancak, sonlandırıcının varlığı, bir yıkıcı tanımlamanız ve bu yıkıcının sonlandırıcısını çağırmanız gerektiğini gösterir. Bu çağrı, yönetilmeyen kaynakların belirleyici sürümü için sağlar.

Yıkıcının çağrılması, nesnenin sonlandırılması gibi — kullanarak bastırır <xref:System.GC.SuppressFinalize%2A> . Yıkıcı çağrılmazsa, türün Sonlandırıcı sonunda çöp toplayıcı tarafından çağrılır.

Nesne kaynaklarını kesin bir şekilde temizlemek için yıkıcıyı çağırarak, CLR 'nin nesneyi belirleyici olmayan şekilde sonlandırmalarına izin vermek yerine, performansı artırabilirsiniz.

Visual C++ yazılan ve kullanılarak derlenen kod **`/clr`** , şu durumlarda bir tür yıkıcısı çalıştırır:

- Yığın semantiği kullanılarak oluşturulan bir nesne kapsam dışına çıkar. Daha fazla bilgi için bkz. [başvuru türleri için C++ yığın semantiği](../dotnet/cpp-stack-semantics-for-reference-types.md).

- Nesnenin oluşturulması sırasında bir özel durum oluşturuldu.

- Nesnesi, yıkıcısı çalıştıran bir nesne içindeki üyesidir.

- [Delete](../cpp/delete-operator-cpp.md) işlecini bir tanıtıcı üzerinde ([nesne işleci (^) olarak işle](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)) çağırabilirsiniz.

- Yok ediciyi açıkça çağırın.

Başka bir dilde yazılmış bir istemci, kendi türünü kullanırsa, yok edicisi aşağıdaki gibi çağırılır:

- Bir çağrısında <xref:System.IDisposable.Dispose%2A> .

- `Dispose(void)`Yazın.

- Tür bir C# deyimindeki kapsam dışına çıkar **`using`** .

Başvuru türleri için yığın semantiğini kullanmıyorsanız ve yönetilen yığında başvuru türünde bir nesne oluşturursanız, bir özel durumun yıkıcının çalışmasını önleyemediğinden emin olmak için [try-finally](../cpp/try-finally-statement.md) söz dizimini kullanın.

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

Türü bir yıkıcı içeriyorsa, derleyici `Dispose` uygulayan bir yöntem oluşturur <xref:System.IDisposable> . Visual C++ yazılmış bir tür ve başka bir dilden tüketilen bir yıkıcı varsa, `IDisposable::Dispose` Bu tür üzerinde yapılan çağrı, türün yıkıcının çağrılmasına neden olur. Tür Visual C++ bir istemciden tüketildiği zaman, doğrudan çağrılamaz `Dispose` ; bunun yerine işleci kullanarak yıkıcıyı çağırın **`delete`** .

Türünün bir sonlandırıcısı varsa, derleyici `Finalize(void)` geçersiz kılan bir yöntem oluşturur <xref:System.Object.Finalize%2A> .

Bir türün Sonlandırıcı ya da yok edicisi varsa, derleyici `Dispose(bool)` Tasarım düzenine göre bir yöntem oluşturur. (Bilgi için bkz. [Dispose model](/dotnet/standard/design-guidelines/dispose-pattern)). Visual C++ açıkça yazamıyor veya arayamıyoruz `Dispose(bool)` .

Bir türün tasarım düzenine uygun bir temel sınıfı varsa, türetilmiş sınıf için yıkıcı çağrıldığında tüm temel sınıfların yıkıcıları çağrılır. (Türü Visual C++ yazılmışsa, derleyici türlerinizi bu düzenin uygulanmasını sağlar.) Diğer bir deyişle, başvuru sınıfının yıkıcısı, temel ve üyelerine C++ standardı tarafından belirtilen şekilde zincirler. İlk olarak, sınıfın yıkıcısı çalıştırılır. Daha sonra, üyeleri için Yıkıcılar oluşturuldukları sıranın tersine doğru çalışır. Son olarak, temel sınıflarının yıkıcıları, oluşturuldukları sıranın tersine doğru çalışır.

Değer türlerinin veya arabirimlerin içinde yok ediciler ve sonlandırıcılar kullanılamaz.

Sonlandırıcısı yalnızca bir başvuru türünde tanımlanabilir veya bildirilebilecek. Bir Oluşturucu ve yıkıcı gibi, sonlandırıcının dönüş türü yoktur.

Bir nesnenin Sonlandırıcı çalıştıktan sonra, herhangi bir temel sınıfta sonlandırıcılar, en az türetilmiş türle başlayarak de çağrılır. Veri üyeleri için sonlandırıcılar, bir sınıfın sonlandırıcısı tarafından otomatik olarak zincirleme değildir.

Bir Sonlandırıcı yönetilen bir türdeki yerel bir işaretçiyi silerse, yerel işaretçiyle veya bu işaretçiden bu işaretçiye yapılan başvuruların zamanından önce toplanmadığından emin olmalısınız. Kullanmak yerine, yönetilen tür üzerinde yıkıcıyı çağırın <xref:System.GC.KeepAlive%2A> .

Derleme zamanında, bir türün Sonlandırıcı veya yıkıcısı olup olmadığını tespit edebilirsiniz. Daha fazla bilgi için bkz. [tür nitelikleri Için derleyici desteği](../extensions/compiler-support-for-type-traits-cpp-component-extensions.md).

Sonraki örnek iki tür gösterir: yönetilmeyen kaynakları olan biri ve bir şekilde serbest bırakılmış yönetilen kaynakları olan bir.

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

[Sınıflar ve yapılar](../extensions/classes-and-structs-cpp-component-extensions.md)
