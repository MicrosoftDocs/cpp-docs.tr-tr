---
title: "Nasıl yapılır: temsilcileri tanımlama ve kullanma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- delegates
ms.assetid: 1cdf3420-89c1-47c0-b796-aa984020e0f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7f400a03f1b9ae877ee7ec681cb038698a92598a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-define-and-use-delegates-ccli"></a>Nasıl yapılır: Temsilcileri Tanımlama ve Kullanma (C++/CLI)
Bu makalede tanımlama ve temsilciler C + kullanma gösterilmektedir +/ CLI.  
  
 Bazen .NET Framework temsilciler sayısı sağlasa da, yeni temsilciler tanımlamak zorunda kalabilirsiniz.  
  
 Aşağıdaki kod örneğinde adlı bir temsilci tanımlar `MyCallback`. Olay işleme kod — bu yeni temsilci başlatıldığında çağrılan işlev — dönüş türüne sahip olmalıdır `void` ve bir <xref:System.String> başvuru.  
  
 Main işlevi tarafından tanımlanan statik bir yöntem kullanır `SomeClass` örneği oluşturmak için `MyCallback` temsilci. Temsilci dizesi "tek" temsilci nesnesine göndererek gösterildiği gibi daha sonra bu işlevi çağırmak için alternatif bir yöntem olur. Daha sonra ek örneklerini `MyCallback` birbirine bağlı ve temsilci nesnesini yapılan bir çağrı tarafından sonra yürütülür.  
  
```  
  
      // use_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
ref class SomeClass  
{  
public:  
   static void Func(String^ str)  
   {  
      Console::WriteLine("static SomeClass::Func - {0}", str);  
   }  
};  
  
ref class OtherClass  
{  
public:  
   OtherClass( Int32 n )   
   {  
      num = n;  
   }  
  
   void Method(String^ str)   
   {  
      Console::WriteLine("OtherClass::Method - {0}, num = {1}",   
         str, num);  
   }  
  
   Int32 num;  
};  
  
delegate void MyCallback(String^ str);  
  
int main( )   
{  
   MyCallback^ callback = gcnew MyCallback(SomeClass::Func);     
   callback("single");   
  
   callback += gcnew MyCallback(SomeClass::Func);     
  
   OtherClass^ f = gcnew OtherClass(99);  
   callback += gcnew MyCallback(f, &OtherClass::Method);  
  
   f = gcnew OtherClass(100);  
   callback += gcnew MyCallback(f, &OtherClass::Method);  
  
   callback("chained");  
  
   return 0;  
}  
```  
  
 **Output**  
  
```Output  
static SomeClass::Func - single  
static SomeClass::Func - chained  
static SomeClass::Func - chained  
OtherClass::Method - chained, num = 99  
OtherClass::Method - chained, num = 100  
```  
  
 Sonraki kod örneği, değer sınıfı üyesi bir temsilci ilişkilendirilecek gösterilmiştir.  
  
```  
// mcppv2_del_mem_value_class.cpp  
// compile with: /clr  
using namespace System;  
public delegate void MyDel();  
  
value class A {  
public:  
   void func1() {  
      Console::WriteLine("test");  
   }  
};  
  
int main() {  
   A a;  
   A^ ah = a;  
   MyDel^ f = gcnew MyDel(a, &A::func1);   // implicit box of a  
   f();  
   MyDel^ f2 = gcnew MyDel(ah, &A::func1);  
   f2();  
}  
```  
  
 **Output**  
  
```Output  
test  
test  
```  
  
## <a name="how-to-compose-delegates"></a>Nasıl temsilci oluşturma  
 Kullanabileceğiniz "`-`" bir bileşen temsilci oluşan bir temsilciyi kaldırmak için işleci.  
  
```  
// mcppv2_compose_delegates.cpp  
// compile with: /clr  
using namespace System;  
  
delegate void MyDelegate(String ^ s);  
  
ref class MyClass {  
public:  
   static void Hello(String ^ s) {  
      Console::WriteLine("Hello, {0}!", s);  
   }  
  
   static void Goodbye(String ^ s) {  
      Console::WriteLine("  Goodbye, {0}!", s);  
   }  
};  
  
int main() {  
  
   MyDelegate ^ a = gcnew MyDelegate(MyClass::Hello);  
   MyDelegate ^ b = gcnew MyDelegate(MyClass::Goodbye);  
   MyDelegate ^ c = a + b;  
   MyDelegate ^ d = c - a;  
  
   Console::WriteLine("Invoking delegate a:");  
   a("A");  
   Console::WriteLine("Invoking delegate b:");  
   b("B");  
   Console::WriteLine("Invoking delegate c:");  
   c("C");  
   Console::WriteLine("Invoking delegate d:");  
   d("D");  
}  
```  
  
 **Output**  
  
```Output  
Invoking delegate a:  
Hello, A!  
Invoking delegate b:  
  Goodbye, B!  
Invoking delegate c:  
Hello, C!  
  Goodbye, C!  
Invoking delegate d:  
  Goodbye, D!  
```  
  
## <a name="pass-a-delegate-to-a-native-function-that-expects-a-function-pointer"></a>Bir temsilci geçirmek ^ işlev işaretçisi bekleyen yerel bir işlevi  
 Yönetilen bir bileşenden burada yerel işlevi yönetilen bileşenin temsilci üye işlevini sonra çağırabilirsiniz işaretçi parametreleri işlevi ile yerel bir işleve çağırabilirsiniz.  
  
 Bu örnek, yerel işlevi dışarı aktarır .dll oluşturur:  
  
```  
// delegate_to_native_function.cpp  
// compile with: /LD  
#include < windows.h >  
extern "C" {  
   __declspec(dllexport)  
   void nativeFunction(void (CALLBACK *mgdFunc)(const char* str)) {  
      mgdFunc("Call to Managed Function");  
   }  
}  
```  
  
 Sonraki örnek .dll kullanır ve bir işlev işaretçisi bekleyen yerel işlevi için bir temsilci tanıtıcı geçirir.  
  
```  
// delegate_to_native_function_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
delegate void Del(String ^s);  
public ref class A {  
public:  
   void delMember(String ^s) {  
      Console::WriteLine(s);  
   }  
};  
  
[DllImportAttribute("delegate_to_native_function", CharSet=CharSet::Ansi)]  
extern "C" void nativeFunction(Del ^d);  
  
int main() {  
   A ^a = gcnew A;  
   Del ^d = gcnew Del(a, &A::delMember);  
   nativeFunction(d);   // Call to native function  
}  
```  
  
 **Output**  
  
```Output  
Call to Managed Function  
```  
  
## <a name="to-associate-delegates-with-unmanaged-functions"></a>Temsilcileri yönetilmeyen işlevlerle ilişkilendirme  
 Temsilci ile yerel bir işleve ilişkilendirmek için yerel işlevi bir yönetilen türü kaydırma ve aracılığıyla çağrılacak işlev bildirme `PInvoke`.  
  
```  
// mcppv2_del_to_umnangd_func.cpp  
// compile with: /clr  
#pragma unmanaged  
extern "C" void printf(const char*, ...);  
class A {  
public:  
   static void func(char* s) {  
      printf(s);  
   }  
};  
  
#pragma managed  
public delegate void func(char*);   
  
ref class B {  
   A* ap;  
  
public:  
   B(A* ap):ap(ap) {}  
   void func(char* s) {  
      ap->func(s);   
   }  
};  
  
int main() {  
   A* a = new A;  
   B^ b = gcnew B(a);  
   func^ f = gcnew func(b, &B::func);  
   f("hello");  
   delete a;  
}  
```  
  
 **Output**  
  
```Output  
hello  
```  
  
## <a name="to-use-unbound-delegates"></a>İlişkisiz temsilciler kullanmak için  
 İlişkisiz bir temsilci işlevi temsilci çağrıldığında aramak istediğiniz türünün bir örneği geçirmek için kullanabilirsiniz.  
  
 İlişkisiz temsilciler koleksiyonundaki nesneleri yinelemek istiyorsanız, özellikle yararlı — kullanarak [her biri için de](../dotnet/for-each-in.md) anahtar sözcükler — ve her örneğinde bir üye işlevini çağırın.  
  
 Şöyle bildirimini, örneği ve çağrısı bağlı ve temsilciler ilişkisiz:  
  
|Eylem|Temsilciler bağlı|İlişkisiz Temsilciler|  
|------------|---------------------|-----------------------|  
|Bildirme|Temsilci imza temsilci çağırmak için istediğiniz işlev imzası eşleşmesi gerekir.|Temsilci imza ilk parametresi türünde `this` çağrısı istediğiniz nesne için.<br /><br /> İlk parametre sonra temsilci imza temsilci çağırmak için istediğiniz işlev imzası eşleşmesi gerekir.|  
|Örneği|İlişkili bir temsilci örneği, bir örnek işlevi veya genel veya statik üye işlevi belirtebilirsiniz.<br /><br /> Bir örnek işlevi belirtmek için ilk parametre üye işlevi aramak istediğiniz türünün bir örneği ve ikinci parametre aramak istediğiniz işlevi adresidir.<br /><br /> Genel veya statik üye işlevini çağırın istiyorsanız, genel bir işlevin adını ya da statik üye işlevin adını geçirmeniz yeterlidir.|İlişkisiz bir temsilci örneği, aramak istediğiniz işlevin adresini geçirmeniz yeterlidir.|  
|Arama|İlişkili bir temsilciyi çağırdığınızda, temsilci imzaya göre gerekli parametreleri geçirmeniz yeterlidir.|Bir sınır aynı temsilci, ancak ilk parametre aramak istediğiniz işlevi içeren nesneyi örneği olması gerektiğini unutmayın.|  
  
 Bu örnek, bildirme, oluşturma ve ilişkisiz temsilciler çağrı gösterilmektedir:  
  
```  
// unbound_delegates.cpp  
// compile with: /clr  
ref struct A {  
   A(){}  
   A(int i) : m_i(i) {}  
   void Print(int i) { System::Console::WriteLine(m_i + i);}  
  
private:  
   int m_i;  
};  
  
value struct V {  
   void Print() { System::Console::WriteLine(m_i);}  
   int m_i;  
};  
  
delegate void Delegate1(A^, int i);  
delegate void Delegate2(A%, int i);  
  
delegate void Delegate3(interior_ptr<V>);  
delegate void Delegate4(V%);  
  
delegate void Delegate5(int i);  
delegate void Delegate6();  
  
int main() {  
   A^ a1 = gcnew A(1);  
   A% a2 = *gcnew A(2);  
  
   Delegate1 ^ Unbound_Delegate1 = gcnew Delegate1(&A::Print);  
   // delegate takes a handle  
   Unbound_Delegate1(a1, 1);  
   Unbound_Delegate1(%a2, 1);  
  
   Delegate2 ^ Unbound_Delegate2 = gcnew Delegate2(&A::Print);  
   // delegate takes a tracking reference (must deference the handle)  
   Unbound_Delegate2(*a1, 1);  
   Unbound_Delegate2(a2, 1);  
  
   // instantiate a bound delegate to an instance member function  
   Delegate5 ^ Bound_Del = gcnew Delegate5(a1, &A::Print);  
   Bound_Del(1);  
  
   // instantiate value types  
   V v1 = {7};  
   V v2 = {8};  
  
   Delegate3 ^ Unbound_Delegate3 = gcnew Delegate3(&V::Print);  
   Unbound_Delegate3(&v1);  
   Unbound_Delegate3(&v2);  
  
   Delegate4 ^ Unbound_Delegate4 = gcnew Delegate4(&V::Print);  
   Unbound_Delegate4(v1);  
   Unbound_Delegate4(v2);  
  
   Delegate6 ^ Bound_Delegate3 = gcnew Delegate6(v1, &V::Print);  
   Bound_Delegate3();  
}  
```  
  
 **Output**  
  
```Output  
2  
3  
2  
3  
2  
7  
8  
7  
8  
7  
```  
  
 İlişkisiz temsilciler kullanmayı sonraki örnek gösterir ve [her biri için de](../dotnet/for-each-in.md) koleksiyonundaki nesneleri yinelemek ve her örneğinde üye işlevi çağırmak için anahtar sözcükler.  
  
```  
// unbound_delegates_2.cpp  
// compile with: /clr  
using namespace System;  
  
ref class RefClass {  
   String^ _Str;  
  
public:  
   RefClass( String^ str ) : _Str( str ) {}  
   void Print() { Console::Write( _Str ); }  
};  
  
delegate void PrintDelegate( RefClass^ );  
  
int main() {  
   PrintDelegate^ d = gcnew PrintDelegate( &RefClass::Print );  
  
   array< RefClass^ >^ a = gcnew array<RefClass^>( 10 );  
  
   for ( int i = 0; i < a->Length; ++i )  
      a[i] = gcnew RefClass( i.ToString() );  
  
   for each ( RefClass^ R in a )  
      d( R );  
  
   Console::WriteLine();  
}  
```  
  
 Bu örnek bir özelliğin erişimci işlevleri ilişkisiz bir temsilciye oluşturur:  
  
```  
// unbound_delegates_3.cpp  
// compile with: /clr  
ref struct B {  
   property int P1 {  
      int get() { return m_i; }  
      void set(int i) { m_i = i; }  
   }  
  
private:  
   int m_i;  
};  
  
delegate void DelBSet(B^, int);  
delegate int DelBGet(B^);  
  
int main() {  
   B^ b = gcnew B;  
  
   DelBSet^ delBSet = gcnew DelBSet(&B::P1::set);  
   delBSet(b, 11);  
  
   DelBGet^ delBGet = gcnew DelBGet(&B::P1::get);     
   System::Console::WriteLine(delBGet(b));  
}  
```  
  
 **Output**  
  
```Output  
11  
```  
  
 Aşağıdaki örnek, burada bir örneğine bağlanır ve bir örnek ilişkisiz bir çok noktaya yayın temsilci çağrılacak gösterilmiştir.  
  
```  
// unbound_delegates_4.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int i) : m_i(i) {}  
  
   void f(R ^ r) {  
      System::Console::WriteLine("in f(R ^ r)");  
   }  
  
   void f() {  
      System::Console::WriteLine("in f()");  
   }  
  
private:  
   int m_i;  
};  
  
delegate void Del(R ^);  
  
int main() {  
   R ^r1 = gcnew R(11);  
   R ^r2 = gcnew R(12);  
  
   Del^ d = gcnew Del(r1, &R::f);  
   d += gcnew Del(&R::f);  
   d(r2);  
};  
```  
  
 **Output**  
  
```Output  
in f(R ^ r)  
in f()  
```  
  
 Sonraki örnek oluşturma ve ilişkisiz bir genel temsilcisi çağrı gösterir.  
  
```  
// unbound_delegates_5.cpp  
// compile with: /clr  
ref struct R {  
   R(int i) : m_i(i) {}  
  
   int f(R ^) { return 999; }  
   int f() { return m_i + 5; }  
  
   int m_i;  
};  
  
value struct V {  
   int f(V%) { return 999; }  
   int f() { return m_i + 5; }   
  
   int m_i;  
};  
  
generic <typename T>  
delegate int Del(T t);  
  
generic <typename T>  
delegate int DelV(T% t);  
  
int main() {     
   R^ hr = gcnew R(7);  
   System::Console::WriteLine((gcnew Del<R^>(&R::f))(hr));  
  
   V v;  
   v.m_i = 9;  
   System::Console::WriteLine((gcnew DelV<V >(&V::f))(v) );  
}  
```  
  
 **Output**  
  
```Output  
12  
14  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [temsilci (C++ Bileşen Uzantıları)](../windows/delegate-cpp-component-extensions.md)