---
title: arabirim sınıfı (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- interface_CPP
dev_langs:
- C++
helpviewer_keywords:
- interface class keyword
- interface struct keyword
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 03c081abc457d025ca2818c887deeb5baf4c4de7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="interface-class--c-component-extensions"></a>arabirim sınıfı (C++ Bileşen Uzantıları)
Arabirim bildirir.  Yerel arabirimleri hakkında daha fazla bilgi için bkz: [__interface](../cpp/interface.md).  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 **Sözdizimi**  
  
```  
  
interface_access  
interface class  
 name :  inherit_accessbase_interface{};interface_accessinterface structname :  inherit_accessbase_interface{};  
```  
  
 **Parametreler**  
  
 *interface_access*  
 Derleme dışına arabirim erişilebilirlik.  Olası değerler şunlardır: **ortak** ve `private`.  `private` varsayılandır.  İç içe geçmiş arabirimleri olamaz bir *interface_access* tanımlayıcısı.  
  
 *Adı*  
 Arabirim adı.  
  
 *inherit_access*  
 Erişilebilirliğini *base_interface*.  Yalnızca izin verilen erişilebilirlik temel bir arabirim için `public` (varsayılan).  
  
 *base_interface* (isteğe bağlı)  
 Arabirim için temel bir arabirim *adı*.  
  
 **Açıklamalar**  
  
 **Yapı arabirim** eşdeğerdir **arabirimi sınıfı**.  
  
 Arabirim bildirimleri işlevleri, olayları ve özellikler içerebilir.  Tüm arabirimi üyeler, ortak erişilebilirlik sahiptir. Arabirim statik veri üyeleri, İşlevler, olayları ve özellikleri de içerebilir ve bu statik üyeleri arabiriminde tanımlanması gerekir.  
  
 Bir sınıfın nasıl uygulandığı bir arabirim tanımlar. Bir arabirim bir sınıfı değil ve sınıflar yalnızca arabirimleri uygulayabilir. Bir sınıf bir arabirim, bildirilen bir işlev tanımladığında geçersiz işlevi uygulanır. Bu nedenle, ad araması arabirim üyeleri dahil değildir.  
  
 Bir sınıf ya da bir arabiriminden türeyen yapı tüm üyeleri arabirimi uygulamalıdır. Arabirim uygularken *adı* arabirimleri de uygulamalıdır `base_interface` listesi.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Arabirim statik Oluşturucusu](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)  
  
-   [Genel Arabirimler (Visual C++)](../windows/generic-interfaces-visual-cpp.md)  
  
 Diğer CLR türleri hakkında daha fazla bilgi için bkz: [sınıflar ve yapılar](../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Bir tür arabirimiyle ise derleme zamanında algılayabilir `__is_interface_class(type)`. Daha fazla bilgi için bkz: [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Geliştirme ortamında F1 Yardımı bu anahtar sözcükleri anahtar sözcüğü vurgulayarak alabilirsiniz (`interface class`, örneğin) ve F1 tuşuna basın.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 **Açıklamalar**  
  
 (Yalnızca Windows çalışma zamanı için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Açıklamalar**  
  
 (Yalnızca ortak dil çalışma zamanı için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneğinde, bir arabirim clock işlevi davranışını nasıl tanımlayabilirsiniz gösterilmektedir.  
  
```  
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
  
 **Output**  
  
```Output  
in Function_3  
  
in Function_2  
  
in Function_1  
  
8  
  
OnClick: 7, 3.14159  
  
in Function_1  
```  
  
 **Örnek**  
  
 Aşağıdaki kod örneği birden çok arabirimler içinde ve bu arabirimleri bir sınıf tarafından kullanıldığı bildirilen aynı imzayla işlevlerini gerçekleştirmek için iki yolunu gösterir.  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)