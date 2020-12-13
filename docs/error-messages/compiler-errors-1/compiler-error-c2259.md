---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2259'
title: Derleyici hatası C2259
ms.date: 11/04/2016
f1_keywords:
- C2259
helpviewer_keywords:
- C2259
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
ms.openlocfilehash: 640349f5870cd818019029c7f04db3e33a068ec9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134699"
---
# <a name="compiler-error-c2259"></a>Derleyici hatası C2259

' class ': soyut sınıfın örneği oluşturulamıyor

Kod, bir soyut sınıf veya yapının örneğini bildirir.

Bir veya daha fazla saf sanal işlev ile bir sınıf veya yapı örneği oluşturamazsınız. Türetilmiş bir sınıfın nesnelerinin örneğini oluşturmak için, türetilmiş sınıf her bir saf sanal işlevi geçersiz kılmalıdır.

Daha fazla bilgi için bkz. [örtülü olarak soyut sınıflar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes).

Aşağıdaki örnek C2259 oluşturur:

```cpp
// C2259.cpp
// compile with: /c
class V {
public:
   void virtual func() = 0;
};
class A : public V {};
class B : public V {
public:
   void func();
};
V v;  // C2259, V is an abstract class
A a;  // C2259, A inherits func() as pure virtual
B b;  // OK, B defines func()
```

Bir arabirimden türettiğinizde ve arabirim yöntemlerini ortak dışında erişim izinleriyle türetilmiş sınıfta uyguladığınızda, C2259 alabilirsiniz.  Bu durum, derleyici türetilmiş sınıfta uygulanan arabirim yöntemlerinin ortak erişime sahip olmasını beklediği için oluşur. Daha kısıtlayıcı erişim izinleri olan bir arabirim için üye işlevlerini uyguladığınızda, derleyici bunları arabirimde tanımlanan arabirim yöntemleri için uygulamalar olarak kabul etmez, bu da türetilmiş sınıfı bir soyut sınıf yapar.

Soruna yönelik iki olası geçici çözüm vardır:

- Uygulanan yöntemler için erişim izinlerini genel hale getirin.

- Uygulanan yöntem adını arabirimin adıyla nitelemek için türetilmiş sınıfta uygulanan arabirim yöntemleri için kapsam çözümleme işlecini kullanın.

C2259, Visual Studio 2005 ' de yapılan uygunluk işinin sonucu olarak da gerçekleşebilir, **/Zc: wchar_t** artık varsayılan olarak açık durumdadır. Bu durumda C2599, önceki sürümlerden veya tercihen uyumlu olmaları için türlerinizi güncelleyerek, bir önceki sürümden davranışı almak için **/Zc: wchar_t-** ile derlenerek çözülebilir. Daha fazla bilgi için bkz. [/Zc: wchar_t (wchar_t yerel tür)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

Aşağıdaki örnek C2259 oluşturur:

```cpp
// C2259b.cpp
// compile with: /c
#include <windows.h>

class MyClass {
public:
   // WCHAR now typedef'ed to wchar_t
   virtual void func(WCHAR*) = 0;
};

class MyClass2 : MyClass {
public:
   void func(unsigned short*);
};

MyClass2 x;   // C2259

// OK
class MyClass3 {
public:
   virtual void func(WCHAR*) = 0;
   virtual void func2(wchar_t*) = 0;
   virtual void func3(unsigned short*) = 0;
};

class MyClass4 : MyClass3 {
public:
   void func(WCHAR*) {}
   void func2(wchar_t*) {}
   void func3(unsigned short*) {}
};

MyClass4 y;
```

Aşağıdaki örnek C2259 oluşturur:

```cpp
// C2259c.cpp
// compile with: /clr
interface class MyInterface {
   void MyMethod();
};

ref class MyDerivedClass: public MyInterface {
private:
   // Uncomment the following line to resolve.
   // public:
   void MyMethod(){}
   // or the following line
   // void MyInterface::MyMethod() {};
};

int main() {
   MyDerivedClass^ instance = gcnew MyDerivedClass; // C2259
}
```
