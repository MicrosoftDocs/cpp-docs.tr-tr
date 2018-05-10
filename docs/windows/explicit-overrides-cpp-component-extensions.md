---
title: Açık geçersiz kılmalar (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, override [C++]
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4eb418a6ded829e4eeeef3bf108894f9faf3d77e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="explicit-overrides--c-component-extensions"></a>Açık Geçersiz Kılmalar (C++ Bileşen Uzantıları)
Bu konuda açıkça temel sınıfta veya arabirimde üye geçersiz kılmak nasıl ele alınmıştır. Adlandırılmış (açık) geçersiz kılma, farklı bir ada sahip bir türetilmiş yöntemiyle bir yöntemini geçersiz kılmak için yalnızca kullanılmalıdır.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 **Sözdizimi**  
  
```  
  
      overriding-function-declarator = type::function [,type::function] { overriding-function-definition }  
overriding-function-declarator = function { overriding-function-definition }  
```  
  
 **Parametreler**  
  
 *geçersiz kılma-işlevi-bildirimcisi*  
 Geçersiz kılma işlevi dönüş türü, adı ve bağımsız değişken listesi.  Geçersiz kılma işlevi kılınmasını işlevi ile aynı ada sahip olmadığını unutmayın.  
  
 *Türü*  
 Geçersiz kılınacak işlevi içeriyor temel türü.  
  
 *İşlevi*  
 Geçersiz kılmak için bir veya daha fazla işlevi adlarının virgülle ayrılmış listesi.  
  
 *geçersiz kılma-işlevi-tanımı*  
 Geçersiz kılma işlevi tanımlayan işlev ifadeleri.  
  
 **Açıklamalar**  
  
 Geçersiz kılmalar yöntemi imza için bir diğer ad oluşturmak veya yöntemleri witht aynı imza için farklı uygulamaları sağlamak için açık kullanın.  
  
 Devralınan türleri ve devralınan tür üyeleri davranışını değiştirme hakkında daha fazla bilgi için bkz: [geçersiz kılma tanımlayıcıları](../windows/override-specifiers-cpp-component-extensions.md).  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Açıklamalar**  
  
 Açık hakkında bilgi geçersiz kılmaları yerel kodda veya derlenmiş kod **/clr:oldSyntax**, bkz: [açık geçersiz kılmalar](../cpp/explicit-overrides-cpp.md).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneğinde basit, örtük geçersiz kılma ve bir üye uyarlamasını temel arabiriminde, açık geçersiz kılmalar kullanmayan gösterir.  
  
```  
// explicit_override_1.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
}  
```  
  
 **Output**  
  
```Output  
X::f override of I1::f  
```  
  
 **Örnek**  
  
 Aşağıdaki kod örneği, ortak bir imza ile tüm arabirim üyeleri açık geçersiz kılma sözdizimini kullanarak uygulayan gösterilmektedir.  
  
```  
  
// explicit_override_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
interface struct I2 {  
   virtual void f();  
};  
  
ref struct X : public I1, I2 {  
   virtual void f() = I1::f, I2::f {  
      System::Console::WriteLine("X::f override of I1::f and I2::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   I2 ^ MyI2 = gcnew X;  
   MyI -> f();  
   MyI2 -> f();  
}  
```  
  
 **Output**  
  
```Output  
X::f override of I1::f and I2::f  
X::f override of I1::f and I2::f  
```  
  
 **Örnek**  
  
 Aşağıdaki kod örneği, nasıl bir işlevi geçersiz kılma uyguladığı işlevden farklı bir ad olabilir gösterir.  
  
```  
// explicit_override_3.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void g() = I1::f {  
      System::Console::WriteLine("X::g");  
   }  
};  
  
int main() {  
   I1 ^ a = gcnew X;  
   a->f();  
}  
```  
  
 **Output**  
  
```Output  
X::g  
```  
  
 **Örnek**  
  
 Aşağıdaki kod örneğinde türü güvenli koleksiyonu uygulayan bir açık arabirim uygulaması gösterir.  
  
```  
// explicit_override_4.cpp  
// compile with: /clr /LD  
using namespace System;  
ref class R : ICloneable {  
   int X;  
  
   virtual Object^ C() sealed = ICloneable::Clone {  
      return this->Clone();  
   }  
  
public:  
   R() : X(0) {}  
   R(int x) : X(x) {}  
  
   virtual R^ Clone() {  
      R^ r = gcnew R;  
      r->X = this->X;  
      return r;  
   }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)