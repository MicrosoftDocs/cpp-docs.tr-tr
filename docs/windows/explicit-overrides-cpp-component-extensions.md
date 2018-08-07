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
ms.openlocfilehash: 225580be17afcc1bda6feab63d3efe79f932b757
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570330"
---
# <a name="explicit-overrides--c-component-extensions"></a>Açık Geçersiz Kılmalar (C++ Bileşen Uzantıları)
Bu konu, temel sınıfta veya arabirimde üye açıkça geçersiz kılma anlatılmaktadır. (Açık) adlandırılmış bir geçersiz kılma, farklı bir ada sahip bir türetilmiş yöntemi ile bir yöntemi geçersiz kılmak için yalnızca kullanılmalıdır.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 **Söz dizimi**  
  
```  
overriding-function-declarator = type::function [,type::function] { overriding-function-definition }  
overriding-function-declarator = function { overriding-function-definition }  
```  
  
 **Parametreler**  
  
 *geçersiz kılma-işlevi-declarator*  
 Geçersiz kılma işlev dönüş türü, adı ve bağımsız değişken listesi.  Geçersiz kılma işlevi geçersiz kılınmasını işlevi aynı ada sahip olmadığını unutmayın.  
  
 *Türü*  
 Geçersiz kılmak için bir işlevi içeren temel türü.  
  
 *İşlevi*  
 Geçersiz kılmak için bir veya daha fazla işlev adlarının virgülle ayrılmış listesi.  
  
 *geçersiz kılma-işlevi-definition*  
 Geçersiz kılma işlevi tanımlayan işlev gövdesi deyimleri.  
  
 **Açıklamalar**  
  
 Geçersiz kılmalar için bir yöntem imzası bir diğer ad oluşturmak veya yöntemleri witht aynı imzaya için farklı uygulamalarını sağlamak için açık kullanın.  
  
 Devralınan türlerin ve devralınan tür üyeleri davranışını değiştirme hakkında daha fazla bilgi için bkz: [geçersiz kılma tanımlayıcıları](../windows/override-specifiers-cpp-component-extensions.md).  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: `/ZW`  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Açıklamalar**  
  
 Açık hakkında bilgi yerel kodda geçersiz kılar veya derlenmiş kodu `/clr:oldSyntax`, bkz: [açık geçersiz kılmalar](../cpp/explicit-overrides-cpp.md).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: `/clr`  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneği basit, örtük geçersiz kılma ve üye uygulaması temel bir arabirimde açık geçersiz kılmalar kullanmayan gösterir.  
  
```cpp  
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
  
 Aşağıdaki kod örneği, ortak bir imzaya sahip tüm arabirim üyelerini açık geçersiz kılma sözdiziminin uygulamak gösterilmektedir.  
  
```cpp  
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
  
 Aşağıdaki kod örneği, türü güvenli koleksiyonu uygulayan açık arabirim uygulaması gösterir.  
  
```cpp  
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