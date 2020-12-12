---
description: 'Daha fazla bilgi edinin: Interface sınıfı (C++/CLı ve C++/CX)'
title: interface class (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- interface_CPP
helpviewer_keywords:
- interface class keyword
- interface struct keyword
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
ms.openlocfilehash: 8d6fd1eda0ddaaf6ab995e09ad1d84f78fcc91be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119036"
---
# <a name="interface-class--ccli-and-ccx"></a>interface class (C++/CLI ve C++/CX)

Bir arabirim bildirir.  Yerel arabirimler hakkında daha fazla bilgi için bkz. [__interface](../cpp/interface.md).

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="syntax"></a>Sözdizimi

```cpp
interface_access interface class name : inherit_access base_interface {};
interface_access interface struct name : inherit_access base_interface {};
```

### <a name="parameters"></a>Parametreler

*interface_access*<br/>
Derlemenin dışında bir arabirimin erişilebilirliği.  Olası değerler şunlardır **`public`** **`private`** .  **`private`** varsayılandır. İç içe arabirimler *interface_access* tanımlayıcısına sahip olamaz.

*ada*<br/>
Arabirimin adı.

*inherit_access*<br/>
*Base_interface* erişilebilirliği.  Temel arabirim için izin verilen tek erişilebilirlik, **`public`** (varsayılan) olur.

*base_interface*<br/>
Seçim Arabirim *adı* için temel arabirim.

### <a name="remarks"></a>Açıklamalar

**Interface struct** , **Interface sınıfına** eşdeğerdir.

Arabirim, işlevler, olaylar ve özellikler için bildirimler içerebilir.  Tüm arabirim üyelerinin genel erişilebilirliği vardır. Arabirim ayrıca statik veri üyeleri, işlevler, olaylar ve özellikler içerebilir ve bu statik üyelerin arabirimde tanımlanması gerekir.

Arabirim, bir sınıfın nasıl uygulanabileceğini tanımlar. Arabirim bir sınıf değildir ve sınıflar yalnızca arabirimler uygulayabilir. Bir sınıf, bir arabirimde bildirildiği bir işlevi tanımladığında işlev uygulanır, geçersiz kılınmaz. Bu nedenle, ad arama arabirim üyelerini içermez.

Bir arabirimden türetilen bir sınıf veya yapının, arabirimin tüm üyelerini uygulaması gerekir. Arabirim *adı* uygularken, ayrıca listedeki arabirimleri de uygulamalısınız `base_interface` .

Daha fazla bilgi için bkz:

- [Arabirim statik Oluşturucusu](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)

- [Genel Arabirimler (C++/CLI)](generic-interfaces-visual-cpp.md)

Diğer CLR türleri hakkında daha fazla bilgi için bkz. [sınıflar ve yapılar](classes-and-structs-cpp-component-extensions.md).

Bir tür arabirim ise, derleme zamanında tespit edebilirsiniz `__is_interface_class(type)` . Daha fazla bilgi için bkz. [tür nitelikleri Için derleyici desteği](compiler-support-for-type-traits-cpp-component-extensions.md).

Geliştirme ortamında, anahtar sözcüğü vurgulayarak ( **`interface class`** Örneğin,) ve F1 tuşuna basarak bu anahtar sözcükler hakkında F1 yardımı edinebilirsiniz.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu dil özelliği için yalnızca Windows Çalışma Zamanı uygulanan bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu dil özelliği için yalnızca ortak dil çalışma zamanına uygulanan bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, bir arabirimin bir Clock işlevinin davranışını nasıl tanımlayabileceğinizi gösterir.

```cpp
// mcppv2_interface_class.cpp
// compile with: /clr
using namespace System;

public delegate void ClickEventHandler(int, double);

// define interface with nested interface
public interface class Interface_A {
   void Function_1();

   interface class Interface_Nested_A {
      void Function_2();
   };
};

// interface with a base interface
public interface class Interface_B : Interface_A {
   property int Property_Block;
   event ClickEventHandler^ OnClick;
   static void Function_3() { Console::WriteLine("in Function_3"); }
};

// implement nested interface
public ref class MyClass : public Interface_A::Interface_Nested_A {
public:
   virtual void Function_2() { Console::WriteLine("in Function_2"); }
};

// implement interface and base interface
public ref class MyClass2 : public Interface_B {
private:
   int MyInt;

public:
   // implement non-static function
   virtual void Function_1() { Console::WriteLine("in Function_1"); }

   // implement property
   property int Property_Block {
      virtual int get() { return MyInt; }
      virtual void set(int value) { MyInt = value; }
   }
   // implement event
   virtual event ClickEventHandler^ OnClick;

   void FireEvents() {
      OnClick(7, 3.14159);
   }
};

// class that defines method called when event occurs
ref class EventReceiver {
public:
   void OnMyClick(int i, double d) {
      Console::WriteLine("OnClick: {0}, {1}", i, d);
   }
};

int main() {
   // call static function in an interface
   Interface_B::Function_3();

   // instantiate class that implements nested interface
   MyClass ^ x = gcnew MyClass;
   x->Function_2();

   // instantiate class that implements interface with base interface
   MyClass2 ^ y = gcnew MyClass2;
   y->Function_1();
   y->Property_Block = 8;
   Console::WriteLine(y->Property_Block);

   EventReceiver^ MyEventReceiver = gcnew EventReceiver();

   // hook handler to event
   y->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);

   // invoke events
   y->FireEvents();

   // unhook handler to event
   y->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);

   // call implemented function via interface handle
   Interface_A^ hi = gcnew MyClass2();
   hi->Function_1();
}
```

```Output
in Function_3

in Function_2

in Function_1

8

OnClick: 7, 3.14159

in Function_1
```

Aşağıdaki kod örneğinde, birden fazla arabirimde ve bu arabirimlerin bir sınıf tarafından kullanıldığı aynı imzayla işlevleri uygulamak için iki yol gösterilmektedir.

```cpp
// mcppv2_interface_class_2.cpp
// compile with: /clr /c
interface class I {
   void Test();
   void Test2();
};

interface class J : I {
   void Test();
   void Test2();
};

ref struct R : I, J {
   // satisfies the requirement to implement Test in both interfaces
   virtual void Test() {}

   // implement both interface functions with explicit overrides
   virtual void A() = I::Test2 {}
   virtual void B() = J::Test2 {}
};
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
