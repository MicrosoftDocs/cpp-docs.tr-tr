---
title: Derleyici Hatası C2259
ms.date: 11/04/2016
f1_keywords:
- C2259
helpviewer_keywords:
- C2259
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
ms.openlocfilehash: 0310f20854185a6f8a5ccb0ce7b087c4d7c5f29d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387077"
---
# <a name="compiler-error-c2259"></a>Derleyici Hatası C2259

'class': soyut sınıfın örneği oluşturulamıyor

Kod bir soyut sınıfın veya yapının örneğini bildirir.

Bir sınıf veya yapı en az bir saf sanal işlevler içeren örneği oluşturulamıyor. Türetilmiş bir sınıf türetilmiş bir sınıfın nesnelerini örneklemek için her bir saf sanal işlevi geçersiz kılmanız gerekir.

Daha fazla bilgi için [örtük olarak soyut sınıflar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes).

Aşağıdaki örnek, C2259 oluşturur:

```
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

Bir arabirimden türetilir ve dışındaki ortak erişim izinleri ile türetilmiş sınıf içinde arabirim yöntemlerini uygulamaz her C2259 alabilirsiniz.  Bu durum, derleyicinin ortak erişimi için türetilmiş sınıf içinde uygulanan arabirim yöntemleri bekliyor kaynaklanır. Üye işlevleri daha kısıtlayıcı erişim izinleri olan bir arabirim için uyguladığınızda, derleyici bunları sırayla bir soyut sınıfı türetilen sınıfın getiren arabirim içinde tanımlanmış arabirim yöntemleri için uygulamaları olarak dikkate almaz.

Sorunun iki olası geçici çözümler vardır:

- Erişim izinleri uygulanan yöntemleri için genel yapın.

- Arabirimin adını uygulanan yöntem adıyla nitelemek için türetilmiş sınıf içinde uygulanan arabirim yöntemleri için kapsam çözünürlük işlecini kullanın.

C2259 görselde yapıldığı uyumluluğu iş sonucu olarak da gerçekleşebilir C++ 2005 **/ZC: wchar_t** artık varsayılan olarak açıktır. Bu durumda, C2599 göre ya da ile derleme çözümlenebilir **/Zc:wchar_t-**, önceki sürümlerden veya kuruluşunuzla uyumlu olduğundan türlerinizi güncelleştirerek davranışı sağlamak için. Daha fazla bilgi için [/ZC: wchar_t (wchar_t yerel türü olduğu)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

Aşağıdaki örnek, C2259 oluşturur:

```
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

Aşağıdaki örnek, C2259 oluşturur:

```
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
