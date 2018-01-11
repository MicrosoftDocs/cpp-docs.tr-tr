---
title: "Nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a0a276854c9f2e27439c2c16e9299d4eaa9243d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>Nasıl yapılır: Sınıfları ve Yapıları Tanımlama ve Kullanma (C++/CLI)
Bu makalede kullanıcı tanımlı başvuru türleri ve türlerin C + tanımlama ve kullanma gösterilmektedir +/ CLI.  
  
##  <a name="BKMK_Contents"></a>İçeriği  
 [Nesne örnek oluşturma](#BKMK_Object_instantiation)  
  
 [Örtük olarak soyut sınıflar](#BKMK_Implicitly_abstract_classes)  
  
 [Tür görünürlüğü](#BKMK_Type_visibility)  
  
 [Üye görünürlüğü](#BKMK_Member_visibility)  
  
 [Ortak ve özel yerel sınıfları](#BKMK_Public_and_private_native_classes)  
  
 [Statik oluşturucular](#BKMK_Static_constructors)  
  
 [Bu semantiği işaretçi](#BKMK_Semantics_of_the_this_pointer)  
  
 [İmzaya göre Gizle işlevleri](#BKMK_Hide_by_signature_functions)  
  
 [Kopya oluşturucuları](#BKMK_Copy_constructors)  
  
 [Yok ediciler ve sonlandırıcılar](#BKMK_Destructors_and_finalizers)  
  
##  <a name="BKMK_Object_instantiation"></a>Nesne örnek oluşturma  
 Başvuru (ref) türleri ve değer türleri, yalnızca yönetilen yığında, yığında veya yerel yığında oluşturulabilir.  
  
```  
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
  
##  <a name="BKMK_Implicitly_abstract_classes"></a>Örtük olarak soyut sınıflar  
 Bir *örtük olarak soyut sınıf* örneği oluşturulamıyor. Bir sınıfın temel türü bir arabirim ise ve sınıf tüm arabiriminin üye işlevleri uygulamıyor örtük olarak soyut sınıftır.  
  
 Arabirimden türetilen bir sınıftan nesneleri oluşturmak erişemiyorsanız sınıfı örtük olarak soyut neden olabilir. Soyut sınıflar hakkında daha fazla bilgi için bkz: [soyut](../windows/abstract-cpp-component-extensions.md).  
  
 Aşağıdaki kod örneğinde gösteren `MyClass` çünkü sınıfı'nin başlatılamaz olamaz işlevi `MyClass::func2` uygulanmadı. Açıklamadan kaldırmasına derlemek örnek etkinleştirmek için `MyClass::func2`.  
  
```  
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
 Bir derlemeyi başvurulduğunda derlemesindeki türler görünür veya derleme dışına görünür olmasını, ortak dil çalışma zamanı (CLR) türleri görünürlüğünü kontrol edebilirsiniz.  
  
 `public`bir tür içeren kaynak dosyası görünür olduğunu belirten bir `#using` türünü içeren derleme için yönerge.  `private`bir türü içeren kaynak dosyaları için görünür olmamasını gösterir bir `#using` türünü içeren derleme için yönerge. Ancak, özel türleri aynı bütünleştirilmiş kodda içinde görünür. Varsayılan olarak, bir sınıf için görünürlük olduğu `private`.  
  
 Visual C++ 2005 önce varsayılan olarak, yerel türler derleme dışına ortak erişilebilirlik vardı. Etkinleştirme [Derleyici Uyarısı (düzey 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) özel yerel türler yanlış kullanıldığı görmenize yardımcı olmak için. Kullanım [make_public](../preprocessor/make-public.md) pragma değiştiremeyeceğiniz bir kaynak kodu dosyasının yerel tür ortak erişilebilirlik vermek için.  
  
 Daha fazla bilgi için bkz: [#using yönergesi](../preprocessor/hash-using-directive-cpp.md).  
  
 Aşağıdaki örnek, türlerinizi ve bunların erişilebilirlik belirtin ve bu derleme türlerinde erişim gösterilmektedir. Kuşkusuz özel türlerine sahip bir derleme kullanarak başvuruluyorsa `#using`, yalnızca genel türler görünür.  
  
```  
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
  
 Şimdi, böylece DLL olarak oluşturulmuş önceki örnek şimdi yeniden yazın.  
  
```  
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
  
 Sonraki örnek türleri derleme dışına erişim gösterilmektedir. Bu örnekte, istemci önceki örnekte yerleşik bileşeni kullanır.  
  
```  
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
  
##  <a name="BKMK_Member_visibility"></a>Üye görünürlüğü  
 Erişim aynı bütünleştirilmiş kod içinde bir ortak sınıf üyesi için farklı erişim içinden derleme dışına erişim tanımlayıcıları çiftlerini kullanarak yapabileceğiniz `public`, `protected`, ve`private`  
  
 Bu tabloda, çeşitli erişim tanımlayıcıları etkisini özetlenmektedir:  
  
|Belirleyici|Efekt|  
|---------------|------------|  
|public|Üye içinden ve dışından derleme erişilebilir.  Bkz: [ortak](../cpp/public-cpp.md) daha fazla bilgi için.|  
|private|Üye içinde ne derleme dışına erişilebilir değil.  Bkz: [özel](../cpp/private-cpp.md) daha fazla bilgi için.|  
|protected|Üye içinde ve derleme dışına, ancak yalnızca türetilmiş türler erişilebilir.  Bkz: [korumalı](../cpp/protected-cpp.md) daha fazla bilgi için.|  
|internal|Derleme içindeki ortak ancak derleme dışına özel üyesidir.  `internal`bağlama duyarlı bir anahtar sözcüktür.  Daha fazla bilgi için bkz: [Context-Sensitive anahtar sözcükleri](../windows/context-sensitive-keywords-cpp-component-extensions.md).|  
|Genel korumalı - veya - korumalı ortak|Derleme içindeki ortak ancak derleme dışına korumalı üyesidir.|  
|Özel korumalı - veya - korumalı özel|Üye derlemesi içinde korumalı ancak derleme dışına özel değildir.|  
  
 Aşağıdaki örnek ile farklı eriþebilirlik bildirilen üyeleri olan bir ortak türü gösterir ve bu üyeleri derlemesi içinde erişme gösterir.  
  
```  
  
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
  
 Şimdi şimdi DLL olarak önceki örnek derleme.  
  
```  
  
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
  
 Aşağıdaki örnek, önceki örnekte oluşturulur ve böylece nasıl üyelerinden derleme dışına erişeceğinizi gösterir bileşen tüketir.  
  
```  
  
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
  
##  <a name="BKMK_Public_and_private_native_classes"></a>Ortak ve özel yerel sınıfları  
 Yerel tür yönetilen türünden başvurulabilir.  Örneğin, bir yönetilen türü işlevinde yerel yapı türü olan bir parametre alabilir.  Yönetilen tür ve işlevi bir derlemede ortak sonra yerel tür Ayrıca ortak olması gerekir.  
  
```  
  
// native type  
public struct N {  
   N(){}  
   int i;  
};  
```  
  
 Ardından, yerel tür tüketir kaynak kodu dosyası oluşturun:  
  
```  
  
// compile with: /clr /LD  
#include "mcppv2_ref_class3.h"  
// public managed type  
public ref struct R {  
   // public function that takes a native type  
   void f(N nn) {}  
};  
```  
  
 Şimdi, bir istemci derleyin:  
  
```  
  
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
 Bir CLR türü — örneğin, bir sınıf veya yapı — statik veri üyeleri başlatmak için kullanılan statik bir oluşturucuya sahip.  Statik Oluşturucu en fazla bir kez çağrılır ve türü herhangi bir statik üyenin ilk kez erişmeden önce çağrılır.  
  
 Örnek oluşturucu statik Oluşturucu sonra her zaman çalışır.  
  
 Sınıfı statik Oluşturucu varsa derleyici satır içi bir oluşturucu için bir çağrı yapılamıyor.  Sınıfı bir değer türü ise, statik bir oluşturucuya sahip ve bir örnek oluşturucu yok derleyici hiçbir üye işlevi çağrısı satır içi yapılamıyor.  Satır içi çağrı CLR olabilir, ancak derleyici olamaz.  
  
 Yalnızca CLR tarafından çağrılacak anlamına geldiğinden statik Oluşturucusu bir özel üye fonksiyonu tanımlayın.  
  
 Statik oluşturucular hakkında daha fazla bilgi için bkz: [nasıl yapılır: Arabirim statik oluşturucusunu tanımlama (C + +/ CLI)](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) .  
  
```  
  
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
  
##  <a name="BKMK_Semantics_of_the_this_pointer"></a>Bu semantiği işaretçi  
 Visual C++ türlerini tanımlamak için kullandığınız zaman `this` işaretçidir bir başvuru türü "tanıtıcısı" tür. `this` İşaretçidir değer türünde "iç işaretçi" tür.  
  
 Bu farklı semantiği `this` işaretçi varsayılan dizin oluşturucu çağrıldığında beklenmeyen davranışlara neden olabilir. Sonraki örnek hem ref türü hem de bir değer türü varsayılan oluşturucuda erişmek için doğru bir şekilde gösterir.  
  
 Daha fazla bilgi için bkz.  
  
-   [Nesne işleci (^) işleme](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)  
  
-   [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)  
  
```  
  
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
  
##  <a name="BKMK_Hide_by_signature_functions"></a>İmzaya göre Gizle işlevleri  
 Türetilmiş sınıf işlevi aynı sayıda veya parametre türünü bile yoksa standart C++'da, bir taban sınıf işlevinde türetilen bir sınıfta aynı ada sahip bir işlev tarafından gizlenmiş. Bu olarak adlandırılır *ada göre Gizle* semantiği. Hem adı hem de parametre listesi aynı olması durumunda bir başvuru türü bir taban sınıf işlevinde yalnızca türetilmiş bir sınıf içindeki bir işlev tarafından gizlenebilir. Bu olarak bilinir *imzaya göre Gizle* semantiği.  
  
 Tüm işlevlerini meta veriler işaretlendiğinde bir sınıf bir imzaya göre Gizle sınıf olarak kabul edilir `hidebysig`. Varsayılan olarak, altında oluşturulan tüm sınıflar **/CLR** sahip `hidebysig` işlevleri. Bir sınıf olduğunda `hidebysig` İşlevler, derleyici değil Gizle işlevleri doğrudan tüm temel sınıflar ada göre ancak bir devralma zincirini ada göre Gizle sınıfında derleyici karşılaşırsa, bu ada göre Gizle davranışı devam eder.  
  
 Bir nesne üzerinde bir işlev çağrıldığında imzaya göre Gizle semantiği altında derleyici işlev çağrısı karşılayan işlevi içeriyor en çok türetilen sınıfı tanımlar. Çağrı karşılamak sınıfında yalnızca bir işlevi ise derleyici bu işlevi çağırır. Çağrı karşılamak sınıf içinde birden fazla işlev ise derleyici kullandığı çözümleme kurallarını çağırmak için hangi işlevi belirlemek için aşırı yükleme. Aşırı kuralları hakkında daha fazla bilgi için bkz: [işlev aşırı yüklemesi](../cpp/function-overloading.md).  
  
 Belirtilen işlev çağrısı için bir temel sınıf işlevinde biraz daha iyi bir eşleşme işlevi'den türetilen bir sınıfta kolaylaştıran bir imza olabilir. Ancak, işlevi açıkça türetilen sınıfın bir nesnesi üzerinde çağrıldı, türetilmiş sınıf içinde işlev çağrılır.  
  
 Dönüş değeri bir işlevin imza bir parçası olarak kabul edilmez çünkü dönüş değeri türünde farklı olsa bile aynı ada sahip ve aynı sayıda ve bağımsız değişkenler tür türetilmiş sınıf işlevi alır, bir temel sınıf işlevi gizlenir.  
  
 Aşağıdaki örnek, bir taban sınıf işlevinde bir türetilmiş sınıfta bir işlev tarafından gizli değil gösterir.  
  
```  
  
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
  
 Visual C++ derleyicisi en çok türetilen sınıfta bir işlevi çağırdığı sonraki örnek gösterir — bir dönüştürme bir veya daha fazla parametre eşleştirmek için gerekli olsa bile — ve daha iyi bir eşleşme işlev çağrısı için bir temel sınıfı bir işlevi çağırmak değil.  
  
```  
  
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
  
 Aşağıdaki örnek, temel sınıf türetilmiş bir sınıf olarak aynı imzaya sahip olsa bile bir işlev gizlemek mümkün olduğunu gösterir.  
  
```  
  
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
  
##  <a name="BKMK_Copy_constructors"></a>Kopya oluşturucuları  
 C++ standart bir nesne taşındığında sağlayacak şekilde bir nesne oluşturulur ve aynı adresinde yok kopya Oluşturucu çağrılır söyler.  
  
 Ancak, ne zaman **/CLR** derleme ve yerel bir işlev yerel sınıfı burada MSIL çağrıları için derlenmiş bir işlev için kullanılan — ya da birden fazla — değer ve yerel sınıfı sahip olduğu bir kopya oluşturucu ve/veya yıkıcı, hiçbir kopya tarafından geçirilen Oluşturucu çağrılır ve nesne oluşturulduğu daha farklı adresindeki yok. Sınıfın bir işaretçi kendisini içine varsa ya da kod adresine göre izleme nesnelerini bu sorunlara neden olabilir.  
  
 Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Aşağıdaki örnek, bir kopya Oluşturucu değil oluşturulduğunda gösterir.  
  
```  
  
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
  
##  <a name="BKMK_Destructors_and_finalizers"></a>Yok ediciler ve sonlandırıcılar  
 Bir başvuru türü yıkıcılarda bir belirleyici temizleyin kaynakların gerçekleştirin. Sonlandırıcılar yönetilmeyen kaynakları temizlemek ve belirleyici biçimde yıkıcı veya belirleyici olmayan şekilde atık toplayıcı tarafından çağrılabilir. Standart c++ Yıkıcılar hakkında daha fazla bilgi için bkz: [Yıkıcılar](../cpp/destructors-cpp.md).  
  
```  
class classname {  
   ~classname() {}   // destructor  
   ! classname() {}   // finalizer  
};  
```  
  
 Yönetilen bir Visual C++ sınıfta Yıkıcılar davranışını C++ için Yönetilen Uzantılar'dan farklıdır. Bu değişiklik hakkında daha fazla bilgi için bkz: [yok edici Anlamlarında yapılan değişiklikler](../dotnet/changes-in-destructor-semantics.md).  
  
 CLR atık toplayıcı kullanılmayan yönetilen nesneleri siler ve bunlar artık gerekli olduğunda kendi belleği serbest bırakır. Ancak, bir tür atık toplayıcı serbest bırakma bilmez kaynakları kullanabilir. Bu kaynaklar yönetilmeyen kaynaklar olarak adlandırılır (yerel dosya işleme, örneğin). Sonlandırıcıyı tüm yönetilmeyen kaynakları serbest öneririz. Yönetilen kaynaklar belirleyici olmayan şekilde atık toplayıcısı tarafından yayımlanan olduğundan mümkün olduğundan bir sonlandırıcı yönetilen kaynaklarında atık toplayıcı o yönetilen kaynak zaten temizledi başvurmak güvenli değil.  
  
 Visual C++ sonlandırıcıyı aynı değil <xref:System.Object.Finalize%2A> yöntemi. (CLR belgelerine sonlandırıcıyı kullanır ve <xref:System.Object.Finalize%2A> yöntemi maliyetle aynı anlamda). <xref:System.Object.Finalize%2A> Yöntemi, bir sınıf devralma zincirindeki her sonlandırıcıyı çağırır atık toplayıcı tarafından çağrılır. Visual C++ Yıkıcılar, türetilmiş sınıf sonlandırıcıyı çağrı tüm temel sınıflar sonlandırıcıyı çağrılacak derleyici neden olmaz.  
  
 Visual C++ derleyicisi kaynakların belirleyici yayın desteklediğinden, uygulamak denemeyin <xref:System.IDisposable.Dispose%2A> veya <xref:System.Object.Finalize%2A> yöntemleri. Ancak, bu yöntemlerle sahibiyseniz, işte nasıl bir Visual C++ Sonlandırıcı ve sonlandırıcıyı çağıran bir yıkıcı Eşle <xref:System.IDisposable.Dispose%2A> Desen:  
  
```  
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
  
 Yönetilen tür belirleyici biçimde bırakın ve nesne artık gerekli değil sonra belirli bir noktada belirleyici olmayan şekilde yayımlamayı atık toplayıcı bırakmak değil için tercih ettiğiniz yönetilen kaynaklar de kullanabilirsiniz. Kaynakları belirleyici sürümü performansı önemli ölçüde iyileştirebilen.  
  
 Visual C++ derleyicisi belirleyici biçimde nesneleri temizlemek için bir yıkıcı tanımını sağlar. Yok Edicisi belirleyici biçimde serbest bırakmak istediğiniz tüm kaynakları serbest bırakmak için kullanın.  Bir sonlandırıcı varsa, kod yinelemesinden kaçınmak için yıkıcı çağırın.  
  
```  
  
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
  
 Türünüz tüketir kod yıkıcı çağırmaz, atık toplayıcı sonunda tüm yönetilen kaynakları serbest bırakır.  
  
 Bir yıkıcı varlığını bir sonlandırıcı varlığını göstermez. Ancak, bir sonlandırıcı varlığını yıkıcı tanımlamak ve bu yıkıcı sonlandırıcıyı çağrı anlamına gelir. Bu, yönetilmeyen kaynakları belirleyici sürüm için sağlar.  
  
 Yıkıcı çağırma bastırır — kullanarak <xref:System.GC.SuppressFinalize%2A>— nesnenin sonlandırma. Yok Edicisi çağrılmazsa türünüz 's sonlandırıcıyı sonunda atık toplayıcısı tarafından çağrılır.  
  
 Belirleyici biçimde yıkıcı çağırarak, nesnenin kaynakları temizleme nesne belirleyici olmayan şekilde Sonlandır CLR izin vererek ile karşılaştırıldığında performansı artırabilir.  
  
 Visual C++'da yazılmış ve kullanarak derlenmiş kod **/CLR** bir türün yıkıcı çalıştırır:  
  
-   Yığın anlamları kullanılarak oluşturulan bir nesne kapsam dışında gider. Daha fazla bilgi için bkz: [başvuru türleri için C++ yığın anlamları](../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
-   Nesne oluşturma sırasında özel durum oluşur.  
  
-   Nesne üyesi olan yıkıcı çalıştıran bir nesne değil.  
  
-   Çağırmanız [silmek](../cpp/delete-operator-cpp.md) bir tanıtıcı işlecinin ([işlemek nesne işleci (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)).  
  
-   Yıkıcı açıkça çağırın.  
  
 Türünüz başka bir dilde yazılmış bir istemci tarafından kullanılan, yıkıcı gibi çağrılır:  
  
-   Çağrı sırasında <xref:System.IDisposable.Dispose%2A>.  
  
-   Çağrı sırasında `Dispose(void)` türünde.  
  
-   C# kapsam dışında türü giderilmediğine `using` deyimi.  
  
 (Yığın anlamları başvuru türlerinde kullanmayan) yönetilen yığında başvuru türünde bir nesne oluşturursanız, kullanın [try-finally](../cpp/try-finally-statement.md) bir özel durum yıkıcı çalışmasını engellemez emin olmak için sözdizimini.  
  
```  
  
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
  
 Bir yıkıcı türünüz varsa, derleyici oluşturur bir `Dispose` uygulayan yöntemi <xref:System.IDisposable>. Visual C++ ile yazılmış ve başka bir dilden tüketilen yıkıcı olan bir tür değilse, çağırma `IDisposable::Dispose` o türde tür yıkıcı çağrılmasına neden olur. Türü bir Visual C++ istemciden kullanıldığında, doğrudan çağıramazsınız `Dispose`; bunun yerine, kullanarak yıkıcı çağırma `delete` işleci.  
  
 Derleyici, türünün bir Sonlandırıcısı varsa oluşturur bir `Finalize(void)` geçersiz kılmaları yöntemi <xref:System.Object.Finalize%2A>.  
  
 Bir türünün bir Sonlandırıcısı ya da bir yıkıcı varsa derleyici oluşturur bir `Dispose(bool)` tasarım deseni göre yöntemi. (Bilgi için bkz: [Dispose düzeni](/dotnet/standard/design-guidelines/dispose-pattern)). Siz açıkça author çağrısı veya olamaz `Dispose(bool)` Visual C++'ta.  
  
 Bir tür için tasarım deseni uyan bir taban sınıf varsa, türetilmiş sınıf yıkıcı çağrıldığında tüm temel sınıflar için Yıkıcılar denir. (Visual c++'ta türünüz yazılmışsa, derleyici türlerinizi bu deseni uygulayan sağlar.) Diğer bir deyişle, kendi tabanları ve üyeleri C++ Standart belirtildiği için bir başvuru sınıfı yıkıcısı zincir — sınıfının yıkıcı olan çalıştırın, ardından üyelerine, bunlar yapılmış, sırasını tersine için Yıkıcılar ilk ve son olarak oluşturulan sırasını tersine, temel sınıflar için Yıkıcılar.  
  
 Yok ediciler ve sonlandırıcılar değer türleri veya arabirimler içinde izin verilmiyor.  
  
 Bir sonlandırıcı yalnızca tanımlı veya bir başvuru türü bildirilmedi. Oluşturucu ve yıkıcı gibi bir sonlandırıcı hiçbir dönüş türüne sahip.  
  
 Bir nesnenin sonlandırıcıyı çalıştıktan sonra tüm temel sınıflar sonlandırıcılar Ayrıca, en az türetilen tür ile başlayan adı verilir. Veri üyeleri için sonlandırıcılar otomatik olarak için sınıf sonlandırıcıyı tarafından Zincirli değil.  
  
 Bir sonlandırıcı yönetilen türü bir yerel işaretçiden silerse, başvurular için veya yerel işaretçiden aracılığıyla değil erken toplanır emin olmalısınız; yok Edicisi kullanmak yerine yönetilen türü çağırmak <xref:System.GC.KeepAlive%2A>.  
  
 Derleme zamanında bir türü bir sonlandırıcı veya bir yıkıcı sahip olup olmadığını algılayabilir. Daha fazla bilgi için bkz: [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Sonraki örnek, iki tür, yönetilmeyen kaynakları olan diğeri belirleyici biçimde yayımlanan kaynaklar yönetilen olan gösterir.  
  
```  
  
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
 [Sınıflar ve yapılar](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)