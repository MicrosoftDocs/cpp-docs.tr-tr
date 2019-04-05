---
title: arabirim sınıfı (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- interface_CPP
helpviewer_keywords:
- interface class keyword
- interface struct keyword
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
ms.openlocfilehash: 60e8965e3ef2538554d8c664b35bd0849bd5e69e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035858"
---
# <a name="interface-class--ccli-and-ccx"></a>arabirim sınıfı (C + +/ CLI ve C + +/ CX)

Bir arabirim bildirir.  Yerel arabirimleri hakkında daha fazla bilgi için bkz: [__interface](../cpp/interface.md).

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="syntax"></a>Sözdizimi

```cpp
interface_access
interface class
name :  inherit_accessbase_interface{};interface_accessinterface structname :  inherit_accessbase_interface{};
```

### <a name="parameters"></a>Parametreler

*interface_access*<br/>
Bir arabirimin derleme dışından erişilebilirlik.  Olası değerler **genel** ve **özel**.  **özel** varsayılandır. İç içe geçmiş arabirimleri sahip bir *interface_access* tanımlayıcısı.

*name*<br/>
Arabirimin adı.

*inherit_access*<br/>
Erişilebilirliğini *base_interface*.  Yalnızca izin verilen erişilebilirlik için temel arabirim **genel** (varsayılan).

*base_interface*<br/>
(İsteğe bağlı) Arabirim için temel bir arabirim *adı*.

### <a name="remarks"></a>Açıklamalar

**Arabirim yapı birimi** eşdeğerdir **arabirim sınıfı**.

Bir arabirim bildirimi işlevleri, olayları ve özellikler içerebilir.  Tüm arabirim üyeleri genel erişilebilirlik sahiptir. Bir arabirim statik veri üyeleri, İşlevler, olayları ve özellikleri de içerebilir ve bu statik üyeleri arabiriminde tanımlanması gerekir.

Nasıl bir sınıf uygulanabilir bir arabirim tanımlar. Bir arabirim bir sınıf değil ve sınıfları yalnızca arabirim uygulayabilir. Bir arabirimde bildirilen bir işlevi bir sınıf tanımlar, geçersiz işlevi uygulanır. Bu nedenle, ad arama, arabirim üyeleri içermez.

Bir sınıf veya yapı arabiriminden türetilen arabirimin tüm üyelerini uygulamalıdır. Arabirimi uygulanırken *adı* arabirimleri de uygulamalıdır `base_interface` listesi.

Daha fazla bilgi için bkz.:

- [Arabirim statik Oluşturucusu](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)

- [Genel arabirimler (C + +/ CLI)](generic-interfaces-visual-cpp.md)

Diğer CLR türleri hakkında daha fazla bilgi için bkz. [sınıfları ve yapıları](classes-and-structs-cpp-component-extensions.md).

Bir türü bir arabirim ile ise derleme zamanında algılayabilir `__is_interface_class(type)`. Daha fazla bilgi için [tür özellikleri için derleyici desteği](compiler-support-for-type-traits-cpp-component-extensions.md).

Geliştirme ortamında F1 Yardım bu anahtar sözcükler üzerinde anahtar sözcüğü vurgulayarak alabilirsiniz (`interface class`, örneğin) ve F1 tuşuna basın.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu dil özelliğinin yalnızca Windows çalışma zamanı için geçerli olan açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu dil özelliğinin yalnızca ortak dil çalışma zamanı için geçerli olan açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, bir arabirim bir saat işlevin davranışını nasıl tanımlayabilirsiniz gösterir.

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

Aşağıdaki kod örneği, birden çok arabirimlerde ve bu arabirimler kullanıldığı bir sınıf tarafından bildirilen aynı imzaya sahip işlevler uygulamak için iki yolunu gösterir.

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